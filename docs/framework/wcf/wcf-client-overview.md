---
title: Übersicht über den WCF-Client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], architecture
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
ms.openlocfilehash: 03a9580bee6308ef53c7d2bc6e9dbe619c2048f7
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="wcf-client-overview"></a>Übersicht über den WCF-Client
In diesem Abschnitt wird beschrieben, was Clientanwendungen ausgeführten Aktionen, wie Sie konfigurieren, erstellen und Verwenden eines Windows Communication Foundation (WCF)-Clients und zum Sichern von Clientanwendungen.  
  
## <a name="using-wcf-client-objects"></a>Verwenden von WCF-Clientobjekten  
 Eine Clientanwendung ist eine verwaltete Anwendung, die einen WCF-Client verwendet, um die Kommunikation mit einer anderen Anwendung. Zum Erstellen von eines Clients erfordert die Anwendung für einen WCF-Dienst die folgenden Schritte aus:  
  
1.  Abrufen des Dienstvertrags, der Bindungen und der Adressinformationen für einen Dienstendpunkt.  
  
2.  Erstellen Sie einen WCF-Clients, die mithilfe dieser Informationen.  
  
3.  Aufrufen von Vorgängen.  
  
4.  Schließen Sie den WCF-Clientobjekts.  
  
 In den folgenden Abschnitten finden Sie eine Erläuterung dieser Schritte und kurze Einführungen in die folgenden Probleme:  
  
-   Behandeln von Fehlern.  
  
-   Konfigurieren und Sichern von Clients.  
  
-   Erstellen von Rückrufobjekten für Duplexdienste  
  
-   Asynchrones Aufrufen von Diensten.  
  
-   Aufrufen von Diensten mithilfe von Clientkanälen.  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a>Abrufen von Dienstvertrag, Bindungen und Adressen  
 In WCF modellieren Dienste und Clients Verträge mit verwalteten Attributen, Schnittstellen und Methoden. Soll eine Verbindung zu einem Dienst in einer Clientanwendung hergestellt werden, muss der Informationstyp für den Dienstvertrag abgerufen werden. In der Regel wird Sie zu diesem Zweck die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), konvertiert es in eine verwaltete Quellcodedatei in der Sprache Ihrer Wahl der Metadaten vom Dienst heruntergeladen, und erstellt einen Client Anwendungskonfigurationsdatei, die Sie zum Konfigurieren des WCF-Clientobjekts verwenden können. Z. B., wenn Sie beabsichtigen, erstellen Sie einen WCF-Clientobjekts zum Aufrufen einer `MyCalculatorService`, und Sie wissen, dass die Metadaten für diesen Dienst an veröffentlicht wird `http://computerName/MyCalculatorService/Service.svc?wsdl`, und dann das folgende Codebeispiel zeigt, wie von Svcutil.exe zum Abrufen einer `ClientCode.vb` -Datei mit enthält den Dienstvertrag in verwaltetem Code.  
  
```  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 Dieser Vertragscode kann entweder kompiliert werden, in der Clientanwendung oder einer anderen Assembly, die die Clientanwendung anschließend zum Erstellen eines WCF-Client-Objekts verwenden können. Sie können die Konfigurationsdatei zum Konfigurieren des Clientobjekts verwenden, um eine ordnungsgemäße Verbindung zum Dienst herzustellen.  
  
 Ein Beispiel dieses Prozesses finden Sie unter [Vorgehensweise: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md). Weitere Informationen zu Verträgen, finden Sie unter [Verträge](../../../docs/framework/wcf/feature-details/contracts.md).  
  
## <a name="create-a-wcf-client-object"></a>Erstellen eines WCF-Clientobjekts  
 Ein WCF-Client ist ein lokales Objekt, das einen WCF-Dienst in einer Form darstellt, die der Client zur Kommunikation mit dem Remotedienst verwenden können. WCF-Clienttypen implementieren den Vertrag, damit beim Erstellen und konfigurieren Sie dann das Clientobjekt verwenden können direkt, um Dienstvorgänge aufzurufen. Der WCF-Laufzeit konvertiert die Methodenaufrufe in Nachrichten, sendet diese an den Dienst, hört die Antwort und gibt diese Werte mit dem WCF-Client-Objekt als Rückgabewerte oder `out` oder `ref` Parameter.  
  
 Sie können auch WCF-clientkanalobjekten herstellen und diese Dienste verwenden. Weitere Informationen finden Sie unter [WCF-Clientarchitektur](../../../docs/framework/wcf/feature-details/client-architecture.md).  
  
#### <a name="creating-a-new-wcf-object"></a>Erstellen eines neuen WCF-Objekts  
 Wenn Sie die Verwendung einer <xref:System.ServiceModel.ClientBase%601>-Klasse darstellen möchten, nehmen Sie an, dass der folgende einfache Dienstvertrag von einer Dienstanwendung generiert wurde.  
  
> [!NOTE]
>  Wenn Sie Visual Studio zum Erstellen von WCF-Client verwenden, werden Objekte beim Hinzufügen eines Dienstverweises zum Projekt automatisch in den Objektkatalog geladen.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Wenn Sie Visual Studio nicht verwenden, überprüfen Sie den generierten Vertragscode, um den Typ zu suchen, die erweitert <xref:System.ServiceModel.ClientBase%601> und die dienstvertragsschnittstelle `ISampleService`. In diesem Fall entspricht der Typ dem folgenden Code:  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 Diese Klasse kann als lokales Objekt mithilfe eines der Konstruktoren erstellt, konfiguriert und anschließend zum Herstellen einer Verbindung zu einem Dienst vom Typ `ISampleService` verwendet werden.  
  
 Es wird empfohlen, dass Sie Ihre WCF-Clientobjekts zunächst erstellen, und klicken Sie dann verwenden, und in einem einzelnen Try/Catch-Block zu schließen. Verwenden Sie nicht die `using` Anweisung (`Using` in Visual Basic) da Ausnahmen in bestimmten Fehlermodi möglicherweise. Weitere Informationen finden Sie unter den folgenden Abschnitten sowie [Vermeiden von Problemen mit der Using-Anweisung](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
### <a name="contracts-bindings-and-addresses"></a>Verträge, Bindungen und Adressen  
 Bevor Sie einen WCF-Clientobjekts erstellen können, müssen Sie das Clientobjekt konfigurieren. Insbesondere benötigen sie einen Dienst *Endpunkt* verwenden. Ein Endpunkt ist die Kombination eines Dienstvertrags, einer Bindung und einer Adresse. (Weitere Informationen über Endpunkte finden Sie unter [Endpunkte: Adressen, Bindungen und Verträge](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md).) In der Regel befindet sich diese Informationen den [ \<Endpunkt >](../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md) Element in einer Konfigurationsdatei der Clientanwendung, beispielsweise das Tool "Svcutil.exe" generiert und wird automatisch geladen, wenn Sie Ihren Client erstellen -Objekt. Beide WCF-Clienttypen verfügen auch Überladungen, die Ihnen ermöglichen, das programmgesteuerte angeben dieser Informationen.  
  
 Beispielsweise beinhaltet eine generierte Konfigurationsdatei für einen in den vorherigen Beispielen verwendeten `ISampleService` die folgenden Endpunktinformationen.  
  
 [!code-xml[C_GeneratedCodeFiles#19](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  
  
 Mit dieser Konfigurationsdatei wird ein Zielendpunkt im `<client>`-Element angegeben. Weitere Informationen zum Verwenden mehrerer Zielendpunkte finden Sie unter der <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType> oder <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType> Konstruktoren.  
  
## <a name="calling-operations"></a>Aufrufen von Vorgängen  
 Nach Sie verfügen über eine Clientobjekt erstellt und konfiguriert ist, erstellen Sie einen Try/Catch-Block, Aufrufen von Vorgängen auf die gleiche Weise, die Sie auch, wenn das Objekt lokal wären und schließen Sie die WCF-Clientobjekts. Wenn die Clientanwendung den ersten Vorgang aufgerufen wird, WCF öffnet automatisch den zugrunde liegenden Kanal und der zugrunde liegenden Kanal wird geschlossen, wenn das Objekt wiederverwendet wird. (Es besteht auch die Möglichkeit, den Kanal vor oder nach dem Aufruf anderer Vorgänge explizit zu öffnen und zu schließen.)  
  
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
  
 Sie können Vorgänge durch Erstellen eines WCF-Client-Objekts aufrufen, und ihre Methoden aufrufen, wie im folgenden Codebeispiel wird veranschaulicht. Beachten Sie, dass das Öffnen, aufrufen, und Schließen des WCF-Clientobjekts erfolgt innerhalb eines einzelnen Try/Catch-Blocks. Weitere Informationen finden Sie unter [beim Zugriff auf Dienste, die mithilfe eines WCF-Clients](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md) und [Vermeiden von Problemen mit der Using-Anweisung](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a>Behandeln von Fehlern  
 Ausnahmen können in einer Clientanwendung unter folgenden Bedingungen auftreten: beim Öffnen des zugrunde liegenden Kanals (entweder explizit oder automatisch durch Aufrufen eines Vorgangs), beim Aufrufen von Vorgängen mit dem Client- oder Kanalobjekt oder beim Schließen des zugrunde liegenden Clientkanals. Anwendungen sollten zumindest erwarten, mögliche <xref:System.TimeoutException?displayProperty=nameWithType>-Ausnahmen und <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>-Ausnahmen sowie jegliche <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>-Objekte zu behandeln, die infolge von durch Vorgänge zurückgegebenen SOAP-Fehlern ausgelöst werden. Im Vorgangsvertrag angegebene SOAP-Fehler werden als <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> zu Clientanwendungen heraufgestuft, wobei der Typparameter der Detailtyp des SOAP-Fehlers ist. Weitere Informationen zur Behandlung von fehlerbedingungen in einer Clientanwendung finden Sie unter [senden und Empfangen von Fehlern](../../../docs/framework/wcf/sending-and-receiving-faults.md). Ein vollständiges Beispiel für das Behandeln von Fehlern in einem Client, finden Sie unter [Ausnahmen erwartet](../../../docs/framework/wcf/samples/expected-exceptions.md).  
  
## <a name="configuring-and-securing-clients"></a>Konfigurieren und Sichern von Clients  
 Das Konfigurieren eines Clients beginnt mit dem erforderlichen Laden von Zielendpunktinformationen für das Client- oder Kanalobjekt (in der Regel von einer Konfigurationsdatei), obwohl diese Informationen auch programmgesteuert mithilfe der Clientkonstruktoren und -eigenschaften geladen werden können. Allerdings sind zusätzliche Konfigurationsschritte erforderlich, um ein bestimmtes Clientverhalten zu ermöglichen und zahlreichen Sicherheitsszenarien gerecht zu werden.  
  
 Beispielsweise werden Sicherheitsanforderungen für Dienstverträge in der Dienstvertragschnittstelle deklariert, und falls mit Svcutil.exe eine Konfigurationsdatei erstellt wurde, beinhaltet diese Datei normalerweise eine Bindung, die den Sicherheitsanforderungen des Diensts entspricht. In einigen Fällen sind jedoch möglicherweise zusätzliche Sicherheitskonfigurationen erforderlich, zum Beispiel die Konfiguration von Clientanmeldeinformationen. Vollständige Informationen zur Konfiguration der Sicherheit für WCF-Clients finden Sie unter [Sichern von Clients](../../../docs/framework/wcf/securing-clients.md).  
  
 Zudem können einige benutzerdefinierte Änderungen in Clientanwendungen aktiviert werden, zum Beispiel benutzerdefiniertes Laufzeitverhalten. Weitere Informationen zum Konfigurieren eines benutzerdefinierten Clientverhaltens finden Sie unter [Konfigurieren von Clientverhalten](../../../docs/framework/wcf/configuring-client-behaviors.md).  
  
## <a name="creating-callback-objects-for-duplex-services"></a>Erstellen von Rückrufobjekten für Duplexdienste  
 Mit Duplexdiensten wird ein Rückrufvertrag angegeben, den die Clientanwendung implementieren muss, um gemäß den Vertragsanforderungen ein Rückrufobjekt für den aufzurufenden Dienst bereitzustellen. Obgleich es sich bei Rückrufobjekten nicht um vollständige Dienste handelt (beispielsweise kann ein Kanal nicht mit einem Rückrufobjekt initiiert werden), können Sie zu Implementierungs- und Konfigurationszwecken als eine Art Dienst betrachtet werden.  
  
 Clients von Duplexdiensten müssen folgende Vorgänge ausführen:  
  
-   Eine Rückrufvertragsklasse implementieren.  
  
-   Eine Instanz der Implementierungsklasse Rückrufvertrags erstellen und verwenden sie zum Erstellen der <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> -Objekt, das Sie für den WCF-Client-Konstruktor übergeben.  
  
-   Vorgänge aufrufen und Vorgangsrückrufe behandeln.  
  
 Duplex WCF Client Objekte funktionieren wie ihre Gegenstücke, mit der Ausnahme, dass sie die erforderlichen Funktionen zur Unterstützung von Rückrufen, einschließlich der Konfiguration des rückrufdiensts verfügbar machen.  
  
 Beispielsweise können verschiedene Aspekte des Laufzeitverhaltens des Rückrufobjekts mithilfe der Eigenschaften des <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>-Attributs in der Rückrufklasse gesteuert werden. Ein weiteres Beispiel ist die Verwendung der <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType>-Klasse, um die Rückgabe von Ausnahmeinformationen an Dienste, die das Rückrufobjekt aufrufen, zu ermöglichen. Weitere Informationen finden Sie unter [Duplexdienste](../../../docs/framework/wcf/feature-details/duplex-services.md). Ein vollständiges Beispiel finden Sie unter [Duplex](../../../docs/framework/wcf/samples/duplex.md).  
  
 Auf Windows XP-Computern, auf denen Internetinformationsdienste (IIS) 5.1 ausgeführt wird, muss von Duplexclients eine Clientbasisadresse mithilfe der <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>-Klasse angegeben werden, da andernfalls eine Ausnahme ausgelöst wird. Im folgenden Codebeispiel wird die entsprechende Umsetzung in Code veranschaulicht.  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 Im folgenden Codebeispiel wird die entsprechende Umsetzung in einer Konfigurationsdatei veranschaulicht.  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a>Asynchrones Aufrufen von Diensten  
 Die Art und Weise eines Vorgangsaufrufs ist ausschließlich Angelegenheit des Cliententwicklers. Dies liegt daran, dass die Nachrichten, aus denen sich ein Vorgang zusammensetzt, bei der Darstellung in verwaltetem Code entweder synchronen oder asynchronen Methoden zugeordnet werden können. Wenn Sie einen Client erstellen möchten, mit dem Vorgänge asynchron aufgerufen werden, können Sie daher mit Svcutil.exe und der Option `/async` asynchronen Clientcode generieren. Weitere Informationen finden Sie unter [Vorgehensweise: Aufrufen Service Vorgänge asynchron](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).  
  
## <a name="calling-services-using-wcf-client-channels"></a>Aufrufen von Diensten mithilfe der WCF-Clientkanäle.  
 WCF-Clienttypen erweitern <xref:System.ServiceModel.ClientBase%601>, die selbst leitet sich von <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> Schnittstelle, um die zugrunde liegende kanalsystem verfügbar zu machen. Sie können Dienste aufrufen, indem Sie den Zieldienstvertrag mit der <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>-Klasse verwenden. Weitere Informationen finden Sie unter [WCF-Clientarchitektur](../../../docs/framework/wcf/feature-details/client-architecture.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>  
 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
