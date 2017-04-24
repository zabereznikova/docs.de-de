---
title: "Vorgehensweise: Sichern eines Dienstes mit Windows-Anmeldeinformationen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF, Sicherheit"
ms.assetid: d171b5ca-96ef-47ff-800c-c138023cf76e
caps.latest.revision: 26
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 26
---
# Vorgehensweise: Sichern eines Dienstes mit Windows-Anmeldeinformationen
In diesem Thema wird gezeigt, wie die Übertragungssicherheit für einen [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Dienst in einer Windows-Domäne aktiviert und von Clients in der gleichen Domäne aufgerufen wird. [!INCLUDE[crabout](../../../includes/crabout-md.md)]Dieses Szenario finden Sie unter [Transportsicherheit mit Windows-Authentifizierung](../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md). Eine beispielanwendung finden Sie unter der [WSHttpBinding](../../../docs/framework/wcf/samples/wshttpbinding.md) Beispiel.  
  
 In diesem Thema wird vorausgesetzt, dass Sie über eine vorhandene Vertragsschnittstelle verfügen und die Implementierung bereits definiert wurde, da hier auf diese beiden Punkte aufgebaut wird. Sie können auch einen vorhandenen Dienst und Client ändern.  
  
 Sie können einen Dienst mit Windows-Anmeldeinformationen vollständig im Code sichern. Alternativ können Sie bei Verwendung einer Konfigurationsdatei einige Teile des Codes weglassen. In diesem Thema werden beide Methoden gezeigt. Verwenden Sie jedoch stets nur eine der Methoden.  
  
 In den ersten drei Prozeduren wird gezeigt, wie der Dienst unter Verwendung von Code gesichert wird. Die vierte und fünfte Prozedur zeigen, wie dies mit einer Konfigurationsdatei erreicht wird.  
  
## <a name="using-code"></a>Mithilfe von Code  
 Den vollständigen Code für Dienst und Client finden Sie im Beispielabschnitt am Ende dieses Themas.  
  
 Die erste Prozedur führt durch Erstellen und Konfigurieren einer <xref:System.ServiceModel.WSHttpBinding> -Klasse im Code. Für die Bindung wird der HTTP-Transport verwendet. Die gleiche Bindung wird auf dem Client verwendet.  
  
#### <a name="to-create-a-wshttpbinding-that-uses-windows-credentials-and-message-security"></a>So erstellen Sie eine WSHttpBinding, die Windows-Anmeldeinformationen und Nachrichtensicherheit verwendet  
  
1.  Der Code dieser Prozedur wird im Dienstcode des Beispielabschnitts am Anfang der `Run`-Methode der `Test`-Klasse eingefügt.  
  
2.  Erstellen Sie eine Instanz der <xref:System.ServiceModel.WSHttpBinding> Klasse.  
  
3.  Festlegen der <xref:System.ServiceModel.WsHttpSecurity.Mode%2A> Eigenschaft der <xref:System.ServiceModel.WsHttpSecurity> Klasse <xref:System.ServiceModel.SecurityMode>.  
  
4.  Festlegen der <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> Eigenschaft der <xref:System.ServiceModel.MessageSecurityOverHttp> Klasse <xref:System.ServiceModel.MessageCredentialType>.  
  
5.  Für diese Prozedur wird der folgende Code verwendet:  
  
     [!code-csharp[c_SecureWindowsService#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#1)]
     [!code-vb[c_SecureWindowsService#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#1)]  
  
### <a name="using-the-binding-in-a-service"></a>Verwenden der Bindung in einem Dienst  
 Dies ist die zweite Prozedur; in dieser Prozedur wird die Verwendung der Bindung in einem selbst gehosteten Dient veranschaulicht. [!INCLUDE[crabout](../../../includes/crabout-md.md)]Hosten von Diensten finden Sie unter [Hostingdienste](../../../docs/framework/wcf/hosting-services.md).  
  
##### <a name="to-use-a-binding-in-a-service"></a>So verwenden Sie eine Bindung in einem Dienst  
  
1.  Fügen Sie den Code dieser Prozedur nach dem Code der vorherigen Prozedur ein.  
  
2.  Erstellen einer <xref:System.Type> Variable mit dem Namen `contractType` und den Typ der Schnittstelle zuweisen (`ICalculator`). Verwenden Sie für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] den Operator `GetType` und für C# das Schlüsselwort `typeof`.  
  
3.  Erstellen Sie eine zweite `Type`-Variable mit der Bezeichnung `serviceType`, und weisen Sie ihr den Typ des implementierten Vertrags (`Calculator`) zu.  
  
4.  Erstellen Sie eine Instanz der <xref:System.Uri> Klasse mit dem Namen `baseAddress` mit der Basisadresse des Diensts. Die Basisadresse muss ein Schema haben, das mit dem Transport übereinstimmt. In diesem Fall ist das Transportschema HTTP, und die Adresse enthält den speziellen Uniform Resource Identifier (URI) "localhost" und eine Anschlussnummer (8036) sowie eine Basisendpunktadresse ("serviceModelSamples/): http://localhost:8036/serviceModelSamples/.  
  
5.  Erstellen Sie eine Instanz von der <xref:System.ServiceModel.ServiceHost> Klasse, wobei die `serviceType` und `baseAddress` Variablen.  
  
6.  Fügen Sie dem Dienst einen Endpunkt mit `contractType`, Bindung und einem Endpunktnamen (secureCalculator) hinzu. Ein Client muss beim Initiieren eines Aufrufs zum Dienst die Basisadresse und den Endpunktnamen verketten.  
  
7.  Rufen Sie die <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> Methode, um den Dienst zu starten. Der Code für diese Prozedur wird hier gezeigt:  
  
     [!code-csharp[c_SecureWindowsService#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#2)]
     [!code-vb[c_SecureWindowsService#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#2)]  
  
### <a name="using-the-binding-in-a-client"></a>Verwenden der Bindung in einem Client  
 Diese Prozedur zeigt die Generierung eines Proxys, der mit dem Dienst kommuniziert. Der Proxy wird generiert, mit der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) die Metadaten des Diensts verwendet, um den Proxy zu erstellen.  
  
 Diese Prozedur erstellt außerdem eine Instanz der <xref:System.ServiceModel.WSHttpBinding> Klasse, um die Kommunikation mit dem Dienst, und ruft dann den Dienst.  
  
 In diesem Beispiel wird zum Erstellen des Clients nur Code verwendet. Alternativ können Sie eine Konfigurationsdatei verwenden. Dies wird im Abschnitt nach dieser Prozedur veranschaulicht.  
  
##### <a name="to-use-a-binding-in-a-client-with-code"></a>So verwenden Sie eine Bindung in einem Client mit Code  
  
1.  Verwenden Sie das SvcUtil.exe-Tool, um den Proxycode aus den Metadaten des Diensts zu generieren. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Gewusst wie: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md). Der generierte Proxycode erbt von der <xref:System.ServiceModel.ClientBase%601> -Klasse, die stellt sicher, dass alle Clients die erforderlichen Konstruktoren, Methoden und Eigenschaften für die Kommunikation mit einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service. In diesem Beispiel enthält der generierte Code die `CalculatorClient`-Klasse, die die `ICalculator`-Schnittstelle für die Kompatibilität mit dem Dienstcode implementiert.  
  
2.  Der Code dieser Prozedur wird am Anfang der `Main`-Methode des Clientprogramms eingefügt.  
  
3.  Erstellen Sie eine Instanz der <xref:System.ServiceModel.WSHttpBinding> -Klasse und legen Sie deren Sicherheitsmodus auf `Message` und den Typ der Clientanmeldeinformationen `Windows`. Im Beispiel wird die Variable `clientBinding` genannt.  
  
4.  Erstellen Sie eine Instanz der <xref:System.ServiceModel.EndpointAddress> Klasse mit dem Namen `serviceAddress`. Initialisieren Sie die Instanz mit der mit dem Endpunktnamen verketteten Basisadresse.  
  
5.  Erstellen Sie eine Instanz der generierten Clientklasse mit der `serviceAddress`-Variablen und der `clientBinding`-Variablen.  
  
6.  Rufen Sie die <xref:System.ServiceModel.ClientBase%601.Open%2A> Methode, wie im folgenden Code gezeigt.  
  
7.  Rufen Sie den Dienst auf, und zeigen Sie die Ergebnisse an.  
  
     [!code-csharp[c_secureWindowsClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#1)]
     [!code-vb[c_secureWindowsClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#1)]  
  
## <a name="using-the-configuration-file"></a>Verwenden der Konfigurationsdatei  
 Anstelle der Erstellung der Bindung mithilfe von prozeduralem Code können Sie auch den folgenden Code für den Bindungsabschnitt der Konfigurationsdatei verwenden.  
  
 Wenn Sie bereits einen Dienst definiert keinen, finden Sie unter [entwerfen und Implementieren von Diensten](../../../docs/framework/wcf/designing-and-implementing-services.md), und [Konfigurieren von Diensten](../../../docs/framework/wcf/configuring-services.md).  
  
 **Hinweis** dieser Konfigurationscode wird in den Dienst und die Client-Konfigurationsdateien verwendet.  
  
#### <a name="to-enable-transfer-security-on-a-service-in-a-windows-domain-using-configuration"></a>So aktivieren Sie mit der Konfiguration Übertragungssicherheit für einen Dienst in einer Windows-Domäne  
  
1.  Hinzufügen einer [ <> \> ](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Element der [ <> \> ](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Element-Abschnitt der Konfigurationsdatei.  
  
2.  Fügen Sie dem <`binding`>-Element ein <`WSHttpBinding`>-Element hinzu, und legen Sie das `configurationName`-Attribut auf einen für Ihre Anwendung geeigneten Wert fest.  
  
3.  Fügen Sie ein <`security`>-Element hinzu, und legen Sie das `mode`-Attribut auf "Message" fest.  
  
4.  Fügen Sie ein <`message`>-Element hinzu, und legen Sie das `clientCredentialType`-Attribut auf "Windows" fest.  
  
5.  Ersetzen Sie in der Konfigurationsdatei des Diensts den `<bindings>`-Abschnitt durch den folgenden Code. Wenn Sie nicht bereits über eine Dienstkonfigurationsdatei verfügen, finden Sie unter [Verwendung von Bindungen für Dienste konfigurieren und Clients](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).  
  
    ```  
    <bindings>  
      <wsHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    ```  
  
### <a name="using-the-binding-in-a-client"></a>Verwenden der Bindung in einem Client  
 In dieser Prozedur wird die Generierung zweier Dateien veranschaulicht: einem Proxy, der mit dem Dienst kommuniziert, und einer Konfigurationsdatei. Darüber hinaus werden auch Änderungen am Clientprogramm beschrieben &#8211; der dritten Datei, die auf dem Client verwendet wird.  
  
##### <a name="to-use-a-binding-in-a-client-with-configuration"></a>So verwenden Sie eine Bindung für einen Client mit Konfiguration  
  
1.  Verwenden Sie das SvcUtil.exe-Tool, um den Proxycode und die Konfigurationsdatei aus den Metadaten des Diensts zu generieren. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Gewusst wie: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
2.  Ersetzen Sie die [ <> \> ](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Abschnitt der generierten Konfigurationsdatei durch den Konfigurationscode aus dem vorherigen Abschnitt.  
  
3.  Prozeduraler Code wird am Anfang der `Main`-Methode des Clientprogramms eingefügt.  
  
4.  Erstellen Sie eine Instanz der generierten Clientklasse, und geben Sie den Namen der Bindung in der Konfigurationsdatei als Eingabeparameter weiter.  
  
5.  Rufen Sie die <xref:System.ServiceModel.ClientBase%601.Open%2A> Methode, wie im folgenden Code gezeigt.  
  
6.  Rufen Sie den Dienst auf, und zeigen Sie die Ergebnisse an.  
  
     [!code-csharp[c_secureWindowsClient#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#2)]  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[c_SecureWindowsService#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#0)]  
  
 [!code-csharp[c_SecureWindowsClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#0)]
 <!-- TODO: review snippet reference [!code-vb[c_SecureWindowsClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#0)]  -->  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.WSHttpBinding>   
 [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Gewusst wie: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)   
 [Sichern von Diensten](../../../docs/framework/wcf/securing-services.md)   
 [Übersicht über die Sicherheit](../../../docs/framework/wcf/feature-details/security-overview.md)