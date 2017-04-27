---
title: "&#220;bersicht &#252;ber den WCF-Client | Microsoft Docs"
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
  - "Clients [WCF], Architektur"
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# &#220;bersicht &#252;ber den WCF-Client
In diesem Abschnitt werden die von Clientanwendungen ausgeführten Aktionen sowie das Konfigurieren, Erstellen und Verwenden eines [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Clients und das Sichern von Clientanwendungen erläutert.  
  
## <a name="using-wcf-client-objects"></a>Verwenden von WCF-Clientobjekten  
 Eine Clientanwendung ist eine verwaltete Anwendung, die einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Client zur Kommunikation mit anderen Anwendungen verwendet. Das Erstellen einer Clientanwendung für einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst erfordert die folgenden Schritte:  
  
1.  Abrufen des Dienstvertrags, der Bindungen und der Adressinformationen für einen Dienstendpunkt.  
  
2.  Erstellen eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clients mithilfe dieser Informationen.  
  
3.  Aufrufen von Vorgängen.  
  
4.  Schließen des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientobjekts.  
  
 In den folgenden Abschnitten finden Sie eine Erläuterung dieser Schritte und kurze Einführungen in die folgenden Probleme:  
  
-   Behandeln von Fehlern.  
  
-   Konfigurieren und Sichern von Clients.  
  
-   Erstellen von Rückrufobjekten für Duplexdienste  
  
-   Asynchrones Aufrufen von Diensten.  
  
-   Aufrufen von Diensten mithilfe von Clientkanälen.  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a>Abrufen von Dienstvertrag, Bindungen und Adressen  
 In [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Dienst- und Clientmodellverträge mit verwalteten Attributen, Schnittstellen und Methoden. Soll eine Verbindung zu einem Dienst in einer Clientanwendung hergestellt werden, muss der Informationstyp für den Dienstvertrag abgerufen werden. In der Regel Sie dazu die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), Herunterladen von Metadaten aus dem Dienst, konvertiert es auf einem verwalteten Quellcode Datei in der Sprache Ihrer Wahl, und erstellt eine Konfigurationsdatei der Clientanwendung, können Sie konfigurieren die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Clientobjekt. Falls Sie beispielsweise ein [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientobjekt erstellen, um `MyCalculatorService` aufzurufen und wissen, dass die Metadaten für diesen Dienst unter `http://computerName/MyCalculatorService/Service.svc?wsdl` veröffentlicht werden, wird im folgenden Codebeispiel die Verwendung von Svcutil.exe zum Abrufen einer Datei vom Typ `ClientCode.vb` gezeigt, die den Dienstvertrag in verwaltetem Code beinhaltet.  
  
```  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 Dieser Vertragscode kann entweder in der Clientanwendung oder einer anderen Assembly kompiliert werden, die von der Clientanwendung anschließend zum Erstellen eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientobjekts verwendet werden kann. Sie können die Konfigurationsdatei zum Konfigurieren des Clientobjekts verwenden, um eine ordnungsgemäße Verbindung zum Dienst herzustellen.  
  
 Ein Beispiel dieses Prozesses finden Sie unter [Gewusst wie: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md). Weitere Informationen zu Verträgen finden Sie unter [Verträge](../../../docs/framework/wcf/feature-details/contracts.md).  
  
## <a name="create-a-wcf-client-object"></a>Erstellen eines WCF-Clientobjekts  
 Ein [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Client ist ein lokales Objekt, das einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst in einer Form darstellt, die sich für den Client zum Kommunizieren mit dem Remotedienst eignet. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clienttypen implementieren den Zieldienstvertrag, sodass Dienstvorgänge nach dem Erstellen und Konfigurieren eines Vertrags direkt mit dem Clientobjekt aufgerufen werden können. Die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Laufzeit konvertiert die Methode Methodenaufrufe in Nachrichten, sendet sie an den Dienst, hört die Antwort und gibt diese Werte in der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Clientobjekt als Rückgabewerte oder `out` oder `ref` Parameter.  
  
 Sie können auch mit [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientkanalobjekten eine Verbindung zu Diensten herstellen und diese verwenden. Weitere Informationen finden Sie unter [WCF-Clientarchitektur](../../../docs/framework/wcf/feature-details/client-architecture.md).  
  
#### <a name="creating-a-new-wcf-object"></a>Erstellen eines neuen WCF-Objekts  
 Erläutern der Verwendung von einer <xref:System.ServiceModel.ClientBase%601> Klasse, nehmen Sie an, die folgende einfache Dienstvertrag von einer dienstanwendung generiert wurde.  
  
> [!NOTE]
>  Wird zum Erstellen des [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Clients [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] verwendet, werden Objekte beim Hinzufügen eines Dienstverweises zum Projekt automatisch in den Objektkatalog geladen.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Wenn Sie nicht arbeiten [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], untersuchen Sie den generierten Vertragscode, um den Typ zu suchen, die erweitert <xref:System.ServiceModel.ClientBase%601> und die dienstvertragsschnittstelle `ISampleService`. In diesem Fall entspricht der Typ dem folgenden Code:  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 Diese Klasse kann als lokales Objekt mithilfe eines der Konstruktoren erstellt, konfiguriert und anschließend zum Herstellen einer Verbindung zu einem Dienst vom Typ `ISampleService` verwendet werden.  
  
 Es wird empfohlen, zuerst das [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientobjekt zu erstellen, es anschließend zu verwenden und in einem einzelnen try/catch-Block zu schließen. Verwenden Sie nicht die `using`-Anweisung (`Using` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), da Ausnahmen in bestimmten Fehlermodi möglicherweise nicht angezeigt werden. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]den folgenden Abschnitten werden auch als [Vermeiden von Problemen mit der Using-Anweisung](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
### <a name="contracts-bindings-and-addresses"></a>Verträge, Bindungen und Adressen  
 Bevor ein [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientobjekt erstellt werden kann, ist eine Konfiguration des Clientobjekts erforderlich. Insbesondere müssen sie einen Dienst *Endpunkt* verwenden. Ein Endpunkt ist die Kombination eines Dienstvertrags, einer Bindung und einer Adresse. ([!INCLUDE[crabout](../../../includes/crabout-md.md)] Endpunkte finden Sie unter [Endpunkte: Adressen, Bindungen und Verträge](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md).) In der Regel befindet sich diese Informationen der [ <> \> ](../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md) Element in einer Konfigurationsdatei der Clientanwendung, beispielsweise das Tool "Svcutil.exe" generiert und wird automatisch geladen, wenn Sie Ihre Clientobjekt erstellen. Beide [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clienttypen verfügen auch über Überladungen, die das programmgesteuerte Angeben dieser Informationen ermöglichen.  
  
 Beispielsweise beinhaltet eine generierte Konfigurationsdatei für einen in den vorherigen Beispielen verwendeten `ISampleService` die folgenden Endpunktinformationen.  
  
 <!-- TODO: review snippet reference [!code[C_GeneratedCodeFiles#19](../../../samples/snippets/common/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  -->  
  
 Mit dieser Konfigurationsdatei wird ein Zielendpunkt im `<client>`-Element angegeben. [!INCLUDE[crabout](../../../includes/crabout-md.md)]Verwenden mehrerer Zielendpunkte finden Sie unter der <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=fullName> oder <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=fullName> Konstruktoren.  
  
## <a name="calling-operations"></a>Aufrufen von Vorgängen  
 Erstellen Sie nach dem Erstellen und Konfigurieren eines Clientobjekts einen try/catch-Block, rufen Sie Vorgänge ebenso auf, als handelte es sich um ein lokales Objekt, und schließen Sie das [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientobjekt. Beim Aufruf des ersten Vorgangs durch die Clientanwendung öffnet [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] automatisch den zugrunde liegenden Kanal. Dieser wird bei Wiederverwendung des Objekts geschlossen. (Es besteht auch die Möglichkeit, den Kanal vor oder nach dem Aufruf anderer Vorgänge explizit zu öffnen und zu schließen.)  
  
 Beispiel: Sie verfügen über den folgenden Dienstvertrag:  
  
```csharp  
namespace Microsoft.ServiceModel.Samples  
{  
    using System;  
    using System.ServiceModel;  
  
    [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
    public interface ICalculator  
   {  
        [OperationContract]  
        double Add(double n1, double n2);  
        [OperationContract]  
        double Subtract(double n1, double n2);  
        [OperationContract]  
        double Multiply(double n1, double n2);  
        [OperationContract]  
        double Divide(double n1, double n2);  
    }  
}  
```  
  
```vb  
Namespace Microsoft.ServiceModel.Samples  
  
    Imports System  
    Imports System.ServiceModel  
  
    <ServiceContract(Namespace:= _  
    "http://Microsoft.ServiceModel.Samples")> _   
   Public Interface ICalculator  
        <OperationContract> _   
        Function Add(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
        Function Subtract(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
        Function Multiply(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
     Function Divide(n1 As Double, n2 As Double) As Double  
End Interface  
```  
  
 Sie können Vorgänge durch Erstellen eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientobjekts und durch Aufrufen der Methoden aufrufen (siehe folgendes Beispiel). Das Öffnen, Aufrufen und Schließen des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientobjekts erfolgt innerhalb eines einzelnen try/catch-Blocks. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Zugreifen auf Dienste mithilfe eines WCF-Clients](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md) und [zur Vermeidung von Problemen mit der Using-Anweisung](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a>Behandeln von Fehlern  
 Ausnahmen können in einer Clientanwendung unter folgenden Bedingungen auftreten: beim Öffnen des zugrunde liegenden Kanals (entweder explizit oder automatisch durch Aufrufen eines Vorgangs), beim Aufrufen von Vorgängen mit dem Client- oder Kanalobjekt oder beim Schließen des zugrunde liegenden Clientkanals. Es sollten mindestens Applikationen erwarten, behandeln mögliche <xref:System.TimeoutException?displayProperty=fullName> und <xref:System.ServiceModel.CommunicationException?displayProperty=fullName> -Ausnahmen sowie jegliche <xref:System.ServiceModel.FaultException?displayProperty=fullName> Objekte, die infolge von durch Vorgänge zurückgegebenen SOAP-Fehler ausgelöst. Im Vorgangsvertrag angegebene SOAP-Fehler werden ausgelöst, um den Clientanwendungen als eine <xref:System.ServiceModel.FaultException%601?displayProperty=fullName> , in dem der Typparameter der Detailtyp des SOAP-Fehlers ist. [!INCLUDE[crabout](../../../includes/crabout-md.md)]Behandeln von Fehlerzuständen in einer Clientanwendung finden Sie unter [senden und Empfangen von Fehlern](../../../docs/framework/wcf/sending-and-receiving-faults.md). Ein vollständiges Beispiel für das Behandeln von Fehlern in einem Client, finden Sie unter [Ausnahmen erwartet](../../../docs/framework/wcf/samples/expected-exceptions.md).  
  
## <a name="configuring-and-securing-clients"></a>Konfigurieren und Sichern von Clients  
 Das Konfigurieren eines Clients beginnt mit dem erforderlichen Laden von Zielendpunktinformationen für das Client- oder Kanalobjekt (in der Regel von einer Konfigurationsdatei), obwohl diese Informationen auch programmgesteuert mithilfe der Clientkonstruktoren und -eigenschaften geladen werden können. Allerdings sind zusätzliche Konfigurationsschritte erforderlich, um ein bestimmtes Clientverhalten zu ermöglichen und zahlreichen Sicherheitsszenarien gerecht zu werden.  
  
 Beispielsweise werden Sicherheitsanforderungen für Dienstverträge in der Dienstvertragschnittstelle deklariert, und falls mit Svcutil.exe eine Konfigurationsdatei erstellt wurde, beinhaltet diese Datei normalerweise eine Bindung, die den Sicherheitsanforderungen des Diensts entspricht. In einigen Fällen sind jedoch möglicherweise zusätzliche Sicherheitskonfigurationen erforderlich, zum Beispiel die Konfiguration von Clientanmeldeinformationen. Vollständige Informationen zur Konfiguration der Sicherheit für [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Clients finden Sie unter [Schützen von Clients](../../../docs/framework/wcf/securing-clients.md).  
  
 Zudem können einige benutzerdefinierte Änderungen in Clientanwendungen aktiviert werden, zum Beispiel benutzerdefiniertes Laufzeitverhalten. [!INCLUDE[crabout](../../../includes/crabout-md.md)]zum Konfigurieren eines benutzerdefinierten Clientverhaltens finden Sie unter [Konfigurieren von Clientverhalten](../../../docs/framework/wcf/configuring-client-behaviors.md).  
  
## <a name="creating-callback-objects-for-duplex-services"></a>Erstellen von Rückrufobjekten für Duplexdienste  
 Mit Duplexdiensten wird ein Rückrufvertrag angegeben, den die Clientanwendung implementieren muss, um gemäß den Vertragsanforderungen ein Rückrufobjekt für den aufzurufenden Dienst bereitzustellen. Obgleich es sich bei Rückrufobjekten nicht um vollständige Dienste handelt (beispielsweise kann ein Kanal nicht mit einem Rückrufobjekt initiiert werden), können Sie zu Implementierungs- und Konfigurationszwecken als eine Art Dienst betrachtet werden.  
  
 Clients von Duplexdiensten müssen folgende Vorgänge ausführen:  
  
-   Eine Rückrufvertragsklasse implementieren.  
  
-   Erstellen Sie eine Instanz der Implementierungsklasse des Rückrufs und zur Erstellung der <xref:System.ServiceModel.InstanceContext?displayProperty=fullName> -Objekt, das Sie übergeben den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] clientkonstruktor.  
  
-   Vorgänge aufrufen und Vorgangsrückrufe behandeln.  
  
 Duplex-[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientobjekte funktionieren wie ihre Gegenstücke ohne Duplex, mit der Einschränkung, dass sie zur Unterstützung von Rückrufen erforderliche Funktionen verfügbar machen (einschließlich der Konfiguration des Rückrufdiensts).  
  
 Beispielsweise können Sie verschiedene Aspekte des Laufzeitverhaltens Rückruf steuern, indem Sie mithilfe der Eigenschaften der der <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=fullName> -Attribut für die Rückrufklasse. Ein weiteres Beispiel ist die Verwendung der <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=fullName> Klasse, um die Rückgabe von Ausnahmeinformationen an Dienste zu ermöglichen, die das Rückrufobjekt aufrufen. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Duplexdienste](../../../docs/framework/wcf/feature-details/duplex-services.md). Ein vollständiges Beispiel finden Sie unter [Duplex](../../../docs/framework/wcf/samples/duplex.md).  
  
 Auf Windows XP-Computern, die mit Internet Information Services (IIS) 5.1, muss von duplexclients eine clientbasisadresse mithilfe der <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=fullName> Klasse oder eine Ausnahme ausgelöst. Im folgenden Codebeispiel wird die entsprechende Umsetzung in Code veranschaulicht.  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 Im folgenden Codebeispiel wird die entsprechende Umsetzung in einer Konfigurationsdatei veranschaulicht.  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a>Asynchrones Aufrufen von Diensten  
 Die Art und Weise eines Vorgangsaufrufs ist ausschließlich Angelegenheit des Cliententwicklers. Dies liegt daran, dass die Nachrichten, aus denen sich ein Vorgang zusammensetzt, bei der Darstellung in verwaltetem Code entweder synchronen oder asynchronen Methoden zugeordnet werden können. Wenn Sie einen Client erstellen möchten, mit dem Vorgänge asynchron aufgerufen werden, können Sie daher mit Svcutil.exe und der Option `/async` asynchronen Clientcode generieren. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Gewusst wie: Asynchrones Aufrufen von Dienstvorgängen](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).  
  
## <a name="calling-services-using-wcf-client-channels"></a>Aufrufen von Diensten mithilfe der WCF-Clientkanäle.  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clienttypen erweitern <xref:System.ServiceModel.ClientBase%601>, die wiederum leitet sich von <xref:System.ServiceModel.IClientChannel?displayProperty=fullName> das zugrunde liegende kanalsystem verfügbar gemacht. Sie können Dienste aufrufen, verwenden Sie den zieldienstvertrag mit der <xref:System.ServiceModel.ChannelFactory%601?displayProperty=fullName> Klasse. Weitere Informationen finden Sie unter [WCF-Clientarchitektur](../../../docs/framework/wcf/feature-details/client-architecture.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.ClientBase%601?displayProperty=fullName>   
 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=fullName>