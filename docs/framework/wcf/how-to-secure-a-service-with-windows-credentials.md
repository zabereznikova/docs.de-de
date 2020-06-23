---
title: 'Vorgehensweise: Sichern eines Diensts mit Windows-Anmeldeinformationen'
description: Erfahren Sie, wie Sie die Transportsicherheit für einen WCF-Dienst aktivieren, der sich in einer Windows-Domäne befindet und von Clients in derselben Domäne aufgerufen wird.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
ms.assetid: d171b5ca-96ef-47ff-800c-c138023cf76e
ms.openlocfilehash: 8ef164e1475bfd5f047a99426a2bed43a7aa7353
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244632"
---
# <a name="how-to-secure-a-service-with-windows-credentials"></a>Vorgehensweise: Sichern eines Diensts mit Windows-Anmeldeinformationen

In diesem Thema wird gezeigt, wie die Transportsicherheit für einen Windows Communication Foundation (WCF)-Dienst aktiviert wird, der sich in einer Windows-Domäne befindet und von Clients in derselben Domäne aufgerufen wird. Weitere Informationen zu diesem Szenario finden Sie unter [Transport Sicherheit mit Windows-Authentifizierung](./feature-details/transport-security-with-windows-authentication.md). Eine Beispielanwendung finden Sie im [WSHttpBinding](./samples/wshttpbinding.md) -Beispiel.

In diesem Thema wird vorausgesetzt, dass Sie über eine vorhandene Vertragsschnittstelle verfügen und die Implementierung bereits definiert wurde, da hier auf diese beiden Punkte aufgebaut wird. Sie können auch einen vorhandenen Dienst und Client ändern.

Sie können einen Dienst mit Windows-Anmeldeinformationen vollständig im Code sichern. Alternativ können Sie bei Verwendung einer Konfigurationsdatei einige Teile des Codes weglassen. In diesem Thema werden beide Methoden gezeigt. Verwenden Sie jedoch stets nur eine der Methoden.

In den ersten drei Prozeduren wird gezeigt, wie der Dienst unter Verwendung von Code gesichert wird. Die vierte und fünfte Prozedur zeigen, wie dies mit einer Konfigurationsdatei erreicht wird.

## <a name="using-code"></a>Mithilfe von Code

Den vollständigen Code für Dienst und Client finden Sie im Beispielabschnitt am Ende dieses Themas.

Die erste Prozedur führt Sie durch die Schritte zum Erstellen und Konfigurieren einer <xref:System.ServiceModel.WSHttpBinding>-Klasse im Code. Für die Bindung wird der HTTP-Transport verwendet. Die gleiche Bindung wird auf dem Client verwendet.

#### <a name="to-create-a-wshttpbinding-that-uses-windows-credentials-and-message-security"></a>So erstellen Sie eine WSHttpBinding, die Windows-Anmeldeinformationen und Nachrichtensicherheit verwendet

1. Der Code dieser Prozedur wird im Dienstcode des Beispielabschnitts am Anfang der `Run`-Methode der `Test`-Klasse eingefügt.

2. Erstellen Sie eine Instanz der <xref:System.ServiceModel.WSHttpBinding>-Klasse.

3. Legen Sie die <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>-Eigenschaft der <xref:System.ServiceModel.WSHttpSecurity>-Klasse auf <xref:System.ServiceModel.SecurityMode.Message> fest.

4. Legen Sie die <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A>-Eigenschaft der <xref:System.ServiceModel.MessageSecurityOverHttp>-Klasse auf <xref:System.ServiceModel.MessageCredentialType.Windows> fest.

5. Für diese Prozedur wird der folgende Code verwendet:

    [!code-csharp[c_SecureWindowsService#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#1)]
    [!code-vb[c_SecureWindowsService#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#1)]

### <a name="using-the-binding-in-a-service"></a>Verwenden der Bindung in einem Dienst

Dies ist die zweite Prozedur; in dieser Prozedur wird die Verwendung der Bindung in einem selbst gehosteten Dient veranschaulicht. Weitere Informationen zu Hostingdiensten finden Sie unter [Hosting-Dienste](hosting-services.md).

##### <a name="to-use-a-binding-in-a-service"></a>So verwenden Sie eine Bindung in einem Dienst

1. Fügen Sie den Code dieser Prozedur nach dem Code der vorherigen Prozedur ein.

2. Erstellen Sie eine <xref:System.Type>-Variable mit der Bezeichnung `contractType`, und weisen Sie ihr den Typ der Schnittstelle (`ICalculator`) zu. Wenn Sie Visual Basic verwenden, verwenden Sie den- `GetType` Operator; Wenn Sie c# verwenden, verwenden Sie das- `typeof` Schlüsselwort.

3. Erstellen Sie eine zweite <xref:System.Type>-Variable mit der Bezeichnung `serviceType`, und weisen Sie ihr den Typ des implementierten Vertrags (`Calculator`) zu.

4. Erstellen Sie eine Instanz der <xref:System.Uri>-Klasse mit der Bezeichnung `baseAddress` mit der Basisadresse des Dienstes. Die Basisadresse muss ein Schema haben, das mit dem Transport übereinstimmt. In diesem Fall ist das Transport Schema "http", und die Adresse enthält den speziellen Uniform Resource Identifier (URI) "localhost" und eine Portnummer (8036) sowie eine Basis Endpunkt Adresse ("Service Model Samples/"): `http://localhost:8036/serviceModelSamples/` .

5. Erstellen Sie eine Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse mit der `serviceType`-Variablen und der `baseAddress`-Variablen.

6. Fügen Sie dem Dienst einen Endpunkt mit `contractType`, Bindung und einem Endpunktnamen (secureCalculator) hinzu. Ein Client muss beim Initiieren eines Aufrufs zum Dienst die Basisadresse und den Endpunktnamen verketten.

7. Starten Sie den Dienst, indem Sie die <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>-Methode aufrufen. Der Code für diese Prozedur wird hier gezeigt:

    [!code-csharp[c_SecureWindowsService#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#2)]
    [!code-vb[c_SecureWindowsService#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#2)]

### <a name="using-the-binding-in-a-client"></a>Verwenden der Bindung in einem Client

Diese Prozedur zeigt die Generierung eines Proxys, der mit dem Dienst kommuniziert. Der Proxy wird mit dem Service [Model Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) generiert, das die Dienst Metadaten zum Erstellen des Proxys verwendet.

Durch diese Prozedur wird auch eine Instanz der <xref:System.ServiceModel.WSHttpBinding>-Klasse erstellt, um mit dem Dienst zu kommunizieren. Anschließend wird der Dienst aufgerufen.

In diesem Beispiel wird zum Erstellen des Clients nur Code verwendet. Alternativ können Sie eine Konfigurationsdatei verwenden. Dies wird im Abschnitt nach dieser Prozedur veranschaulicht.

#### <a name="to-use-a-binding-in-a-client-with-code"></a>So verwenden Sie eine Bindung in einem Client mit Code

1. Verwenden Sie das SvcUtil.exe-Tool, um den Proxycode aus den Metadaten des Diensts zu generieren. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen eines Clients](how-to-create-a-wcf-client.md). Der generierte Proxy Code erbt von der- <xref:System.ServiceModel.ClientBase%601> Klasse, wodurch sichergestellt wird, dass jeder Client über die erforderlichen Konstruktoren, Methoden und Eigenschaften für die Kommunikation mit einem WCF-Dienst verfügt. In diesem Beispiel enthält der generierte Code die `CalculatorClient`-Klasse, die die `ICalculator`-Schnittstelle für die Kompatibilität mit dem Dienstcode implementiert.

2. Der Code dieser Prozedur wird am Anfang der `Main`-Methode des Clientprogramms eingefügt.

3. Erstellen Sie eine Instanz der <xref:System.ServiceModel.WSHttpBinding>-Klasse und legen Sie ihren Sicherheitsmodus auf `Message` und ihren Clientanmeldeinformationstyp auf `Windows` fest. Im Beispiel wird die Variable `clientBinding` genannt.

4. Erstellen Sie eine Instanz der <xref:System.ServiceModel.EndpointAddress>-Klasse mit der Bezeichnung `serviceAddress`. Initialisieren Sie die Instanz mit der mit dem Endpunktnamen verketteten Basisadresse.

5. Erstellen Sie eine Instanz der generierten Clientklasse mit der `serviceAddress`-Variablen und der `clientBinding`-Variablen.

6. Rufen Sie die <xref:System.ServiceModel.ClientBase%601.Open%2A>-Methode auf, wie im folgenden Code dargestellt:

7. Rufen Sie den Dienst auf, und zeigen Sie die Ergebnisse an.

    [!code-csharp[c_secureWindowsClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#1)]
    [!code-vb[c_secureWindowsClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#1)]

## <a name="using-the-configuration-file"></a>Verwenden der Konfigurationsdatei

Anstelle der Erstellung der Bindung mithilfe von prozeduralem Code können Sie auch den folgenden Code für den Bindungsabschnitt der Konfigurationsdatei verwenden.

Wenn Sie noch keinen Dienst definiert haben, finden Sie weitere Informationen unter [Entwerfen und Implementieren von Diensten](designing-and-implementing-services.md)und [Konfigurieren von Diensten](configuring-services.md).

> [!NOTE]
> Dieser Konfigurations Code wird sowohl in den Dienst-als auch in den Client Konfigurationsdateien verwendet.

#### <a name="to-enable-transfer-security-on-a-service-in-a-windows-domain-using-configuration"></a>So aktivieren Sie mit der Konfiguration Übertragungssicherheit für einen Dienst in einer Windows-Domäne

1. Fügen Sie [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) dem- [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) Element Abschnitt der Konfigurationsdatei ein-Element hinzu.

2. Fügen Sie `binding` dem <> Element ein <>-Element hinzu, `WSHttpBinding` und legen Sie das- `configurationName` Attribut auf einen für Ihre Anwendung geeigneten Wert fest.

3. Fügen Sie ein <`security`> Element hinzu, und legen Sie das- `mode` Attribut auf Message fest.

4. Fügen Sie ein <`message`> Element hinzu, und legen Sie das- `clientCredentialType` Attribut auf Windows fest.

5. Ersetzen Sie in der Konfigurationsdatei des Diensts den `<bindings>`-Abschnitt durch den folgenden Code. Wenn Sie nicht bereits über eine Dienst Konfigurationsdatei verfügen, finden Sie weitere Informationen unter [Verwenden von Bindungen zum Konfigurieren von Diensten und Clients](using-bindings-to-configure-services-and-clients.md).

    ```xml
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

#### <a name="to-use-a-binding-in-a-client-with-configuration"></a>So verwenden Sie eine Bindung für einen Client mit Konfiguration

1. Verwenden Sie das SvcUtil.exe-Tool, um den Proxycode und die Konfigurationsdatei aus den Metadaten des Diensts zu generieren. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen eines Clients](how-to-create-a-wcf-client.md).

2. Ersetzen Sie den- [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) Abschnitt der generierten Konfigurationsdatei durch den Konfigurations Code aus dem vorherigen Abschnitt.

3. Prozeduraler Code wird am Anfang der `Main`-Methode des Clientprogramms eingefügt.

4. Erstellen Sie eine Instanz der generierten Clientklasse, und geben Sie den Namen der Bindung in der Konfigurationsdatei als Eingabeparameter weiter.

5. Rufen Sie die <xref:System.ServiceModel.ClientBase%601.Open%2A>-Methode auf, wie im folgenden Code dargestellt:

6. Rufen Sie den Dienst auf, und zeigen Sie die Ergebnisse an.

    [!code-csharp[c_secureWindowsClient#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#2)]

## <a name="example"></a>Beispiel

[!code-csharp[c_SecureWindowsService#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#0)]

[!code-csharp[c_SecureWindowsClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#0)]
[!code-vb[c_SecureWindowsClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#0)]

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.WSHttpBinding>
- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Vorgehensweise: Erstellen eines Clients](how-to-create-a-wcf-client.md)
- [Sichern von Diensten](securing-services.md)
- [Sicherheitsübersicht](./feature-details/security-overview.md)
