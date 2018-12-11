---
title: Übersicht über den WCF-Client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], architecture
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
ms.openlocfilehash: e6e7d9fe6764120e3d676b9d2cbd248e7491e504
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152629"
---
# <a name="wcf-client-overview"></a>Übersicht über den WCF-Client
Dieser Abschnitt beschreibt das vorgehen, Client-Anwendungen, wie Sie konfigurieren, erstellen und verwenden Sie einen Windows Communication Foundation (WCF)-Client und Client-Anwendungen zu sichern.  
  
## <a name="using-wcf-client-objects"></a>Verwenden von WCF-Clientobjekten  
 Eine Clientanwendung ist eine verwaltete Anwendung, die einen WCF-Client, die für die Kommunikation mit einer anderen Anwendung verwendet. Erstellen einer Clientanwendung erfordert die Anwendung für einen WCF-Dienst die folgenden Schritte aus:  
  
1.  Abrufen des Dienstvertrags, der Bindungen und der Adressinformationen für einen Dienstendpunkt.  
  
2.  Erstellen Sie einen WCF-Clients, die mithilfe dieser Informationen.  
  
3.  Aufrufen von Vorgängen.  
  
4.  Schließen Sie das WCF-Client-Objekt.  
  
 In den folgenden Abschnitten finden Sie eine Erläuterung dieser Schritte und kurze Einführungen in die folgenden Probleme:  
  
-   Behandeln von Fehlern.  
  
-   Konfigurieren und Sichern von Clients.  
  
-   Erstellen von Rückrufobjekten für Duplexdienste  
  
-   Asynchrones Aufrufen von Diensten.  
  
-   Aufrufen von Diensten mithilfe von Clientkanälen.  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a>Abrufen von Dienstvertrag, Bindungen und Adressen  
 In WCF Modellieren Sie Dienste und Clients Verträge, die über verwaltete Attribute, Schnittstellen und Methoden. Soll eine Verbindung zu einem Dienst in einer Clientanwendung hergestellt werden, muss der Informationstyp für den Dienstvertrag abgerufen werden. In der Regel Sie dazu die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), konvertiert es in eine verwaltete Quellcodedatei in der Sprache Ihrer Wahl der Metadaten vom Dienst heruntergeladen, und erstellt einen Client Konfigurationsdatei der Anwendung, die Sie zum Konfigurieren des WCF-Clientobjekts verwenden können. Z. B., wenn Sie beabsichtigen, zum Erstellen eines WCF-Clientobjekts zum Aufrufen einer `MyCalculatorService`, und Sie wissen, dass die Metadaten für diesen Dienst an veröffentlicht werden `http://computerName/MyCalculatorService/Service.svc?wsdl`, wird im folgenden Codebeispiel wird veranschaulicht, wie von Svcutil.exe zum Abrufen einer `ClientCode.vb` Datei, enthält den Dienstvertrag in verwaltetem Code.  
  
```  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 Sie können entweder diese Contract-Code kompilieren, in die Clientanwendung oder einer anderen Assembly, die die Clientanwendung dann zum Erstellen eines WCF-Client-Objekts verwenden können. Sie können die Konfigurationsdatei zum Konfigurieren des Clientobjekts verwenden, um eine ordnungsgemäße Verbindung zum Dienst herzustellen.  
  
 Ein Beispiel hierzu finden Sie unter [Vorgehensweise: Erstellen Sie einen Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md). Ausführlichere Informationen zu Verträgen finden Sie unter [Verträge](../../../docs/framework/wcf/feature-details/contracts.md).  
  
## <a name="create-a-wcf-client-object"></a>Erstellen eines WCF-Clientobjekts  
 Ein WCF-Client ist ein lokales Objekt, das einen WCF-Dienst in einer Form, die der Client verwenden kann darstellt, für die Kommunikation mit dem Remotedienst. WCF-Clienttypen implementieren den Zieldienst Vertrag, sodass bei dem Erstellen und konfigurieren Sie ihn, Sie dann das Clientobjekt verwenden können direkt, um Dienstvorgänge aufzurufen. Der WCF-Laufzeit konvertiert die Methodenaufrufe in Nachrichten, sendet sie an den Dienst, hört die Antwort und gibt diese Werte an das WCF-Clientobjekt als Rückgabewerte oder `out` oder `ref` Parameter.  
  
 Sie können auch WCF-clientkanalobjekten herstellen und diese Dienste verwenden. Weitere Informationen finden Sie unter [WCF-Clientarchitektur](../../../docs/framework/wcf/feature-details/client-architecture.md).  
  
#### <a name="creating-a-new-wcf-object"></a>Erstellen eines neuen WCF-Objekts  
 Wenn Sie die Verwendung einer <xref:System.ServiceModel.ClientBase%601>-Klasse darstellen möchten, nehmen Sie an, dass der folgende einfache Dienstvertrag von einer Dienstanwendung generiert wurde.  
  
> [!NOTE]
>  Wenn Sie Visual Studio zum Erstellen des WCF-Clients verwenden, werden Objekte automatisch in den Objektkatalog geladen, wenn Sie einen Dienstverweis auf Ihrem Projekt hinzufügen.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Wenn Sie Visual Studio nicht verwenden, überprüfen Sie den generierten Vertragscode, um den Typ zu suchen, die erweitert <xref:System.ServiceModel.ClientBase%601> und die dienstvertragsschnittstelle `ISampleService`. In diesem Fall entspricht der Typ dem folgenden Code:  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 Diese Klasse kann als lokales Objekt mithilfe eines der Konstruktoren erstellt, konfiguriert und anschließend zum Herstellen einer Verbindung zu einem Dienst vom Typ `ISampleService` verwendet werden.  
  
 Es wird empfohlen, dass Sie Ihre WCF-Clientobjekt zuerst erstellen, und klicken Sie dann verwenden, und schließen Sie sie in einem einzelnen Try/Catch-Block. Verwenden Sie nicht die `using` Anweisung (`Using` in Visual Basic) da Ausnahmen in bestimmten Fehlermodi möglicherweise. Weitere Informationen finden Sie unter den folgenden Abschnitten als auch [verwenden schließen "und" Abort, um WCF-Client-Ressourcen freizugeben](../../../docs/framework/wcf/samples/use-close-abort-release-wcf-client-resources.md).  
  
### <a name="contracts-bindings-and-addresses"></a>Verträge, Bindungen und Adressen  
 Bevor Sie einen WCF-Clientobjekt erstellen können, müssen Sie das Clientobjekt konfigurieren. Insbesondere benötigen sie einen Dienst *Endpunkt* verwenden. Ein Endpunkt ist die Kombination eines Dienstvertrags, einer Bindung und einer Adresse. (Weitere Informationen zu Endpunkten finden Sie unter [Endpunkte: Adressen, Bindungen und Verträge](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md).) In der Regel befindet sich diese Informationen in den [ \<Endpunkt >](../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md) Element in einer Konfigurationsdatei der Clientanwendung, wie das Tool Svcutil.exe generiert und wird automatisch geladen, wenn Sie einen Client erstellen -Objekt. Beide Arten der WCF-Client haben auch Überladungen, mit die Sie programmgesteuert auf diese Informationen angeben können.  
  
 Beispielsweise beinhaltet eine generierte Konfigurationsdatei für einen in den vorherigen Beispielen verwendeten `ISampleService` die folgenden Endpunktinformationen.  
  
 [!code-xml[C_GeneratedCodeFiles#19](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  
  
 Mit dieser Konfigurationsdatei wird ein Zielendpunkt im `<client>`-Element angegeben. Weitere Informationen zum Verwenden mehrerer Zielendpunkte finden Sie unter den <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType> oder <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType> Konstruktoren.  
  
## <a name="calling-operations"></a>Aufrufen von Vorgängen  
 Sobald Sie haben ein Clientobjekt erstellt und konfiguriert haben, erstellen Sie einen Try/Catch-Block-Vorgänge aufrufen, auf die gleiche Weise, die bei der das Objekt eine lokale Datei und schließen Sie das WCF-Client-Objekt. Wenn die Clientanwendung den ersten Vorgang aufruft, WCF automatisch den zugrunde liegenden Kanal geöffnet, und der zugrunde liegenden Kanal geschlossen wird, wenn das Objekt wiederverwendet wird. (Es besteht auch die Möglichkeit, den Kanal vor oder nach dem Aufruf anderer Vorgänge explizit zu öffnen und zu schließen.)  
  
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
  
 Sie können Vorgänge durch Erstellen eines WCF-Client-Objekts aufrufen und ihre Methoden aufrufen, wie im folgenden Codebeispiel wird veranschaulicht. Beachten Sie, dass das Öffnen, aufrufen, und Schließen des WCF-Clientobjekts erfolgt innerhalb eines einzelnen Try/Catch-Blocks. Weitere Informationen finden Sie unter [Zugriff auf Dienste, die mithilfe eines WCF-Clients](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md) und [verwenden schließen "und" Abort, um WCF-Client-Ressourcen freizugeben](../../../docs/framework/wcf/samples/use-close-abort-release-wcf-client-resources.md).  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a>Behandeln von Fehlern  
 Ausnahmen können in einer Clientanwendung unter folgenden Bedingungen auftreten: beim Öffnen des zugrunde liegenden Kanals (entweder explizit oder automatisch durch Aufrufen eines Vorgangs), beim Aufrufen von Vorgängen mit dem Client- oder Kanalobjekt oder beim Schließen des zugrunde liegenden Clientkanals. Anwendungen sollten zumindest erwarten, mögliche <xref:System.TimeoutException?displayProperty=nameWithType>-Ausnahmen und <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>-Ausnahmen sowie jegliche <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>-Objekte zu behandeln, die infolge von durch Vorgänge zurückgegebenen SOAP-Fehlern ausgelöst werden. Im Vorgangsvertrag angegebene SOAP-Fehler werden als <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> zu Clientanwendungen heraufgestuft, wobei der Typparameter der Detailtyp des SOAP-Fehlers ist. Weitere Informationen zur Behandlung von fehlerbedingungen in einer Clientanwendung finden Sie unter [Sending and Receiving Faults](../../../docs/framework/wcf/sending-and-receiving-faults.md). Ein vollständiges Beispiel für das Behandeln von Fehlern in einem Client, finden Sie unter [Ausnahmen erwartet](../../../docs/framework/wcf/samples/expected-exceptions.md).  
  
## <a name="configuring-and-securing-clients"></a>Konfigurieren und Sichern von Clients  
 Das Konfigurieren eines Clients beginnt mit dem erforderlichen Laden von Zielendpunktinformationen für das Client- oder Kanalobjekt (in der Regel von einer Konfigurationsdatei), obwohl diese Informationen auch programmgesteuert mithilfe der Clientkonstruktoren und -eigenschaften geladen werden können. Allerdings sind zusätzliche Konfigurationsschritte erforderlich, um ein bestimmtes Clientverhalten zu ermöglichen und zahlreichen Sicherheitsszenarien gerecht zu werden.  
  
 Beispielsweise werden Sicherheitsanforderungen für Dienstverträge in der Dienstvertragschnittstelle deklariert, und falls mit Svcutil.exe eine Konfigurationsdatei erstellt wurde, beinhaltet diese Datei normalerweise eine Bindung, die den Sicherheitsanforderungen des Diensts entspricht. In einigen Fällen sind jedoch möglicherweise zusätzliche Sicherheitskonfigurationen erforderlich, zum Beispiel die Konfiguration von Clientanmeldeinformationen. Vollständige Informationen zur Konfiguration der Sicherheit für WCF-Clients finden Sie [Schützen von Clients](../../../docs/framework/wcf/securing-clients.md).  
  
 Zudem können einige benutzerdefinierte Änderungen in Clientanwendungen aktiviert werden, zum Beispiel benutzerdefiniertes Laufzeitverhalten. Weitere Informationen zum Konfigurieren eines benutzerdefinierten Clientverhaltens finden Sie unter [Konfigurieren von Clientverhalten](../../../docs/framework/wcf/configuring-client-behaviors.md).  
  
## <a name="creating-callback-objects-for-duplex-services"></a>Erstellen von Rückrufobjekten für Duplexdienste  
 Mit Duplexdiensten wird ein Rückrufvertrag angegeben, den die Clientanwendung implementieren muss, um gemäß den Vertragsanforderungen ein Rückrufobjekt für den aufzurufenden Dienst bereitzustellen. Obgleich es sich bei Rückrufobjekten nicht um vollständige Dienste handelt (beispielsweise kann ein Kanal nicht mit einem Rückrufobjekt initiiert werden), können Sie zu Implementierungs- und Konfigurationszwecken als eine Art Dienst betrachtet werden.  
  
 Clients von Duplexdiensten müssen folgende Vorgänge ausführen:  
  
-   Eine Rückrufvertragsklasse implementieren.  
  
-   Erstellen Sie eine Instanz der Implementierung der rückrufvertragsklasse und erstellen die <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> -Objekt, das Sie für den WCF-Client-Konstruktor übergeben.  
  
-   Vorgänge aufrufen und Vorgangsrückrufe behandeln.  
  
 Duplex WCF Objekte Clientfunktion wie ihre Gegenstücke, mit der Ausnahme, dass sie die erforderlichen Funktionen zur Unterstützung von Rückrufen, einschließlich der Konfiguration des rückrufdiensts verfügbar machen.  
  
 Beispielsweise können verschiedene Aspekte des Laufzeitverhaltens des Rückrufobjekts mithilfe der Eigenschaften des <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>-Attributs in der Rückrufklasse gesteuert werden. Ein weiteres Beispiel ist die Verwendung der <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType>-Klasse, um die Rückgabe von Ausnahmeinformationen an Dienste, die das Rückrufobjekt aufrufen, zu ermöglichen. Weitere Informationen finden Sie unter [Duplexdienste](../../../docs/framework/wcf/feature-details/duplex-services.md). Ein vollständiges Beispiel finden Sie unter [Duplex](../../../docs/framework/wcf/samples/duplex.md).  
  
 Auf Windows XP-Computern, auf denen Internetinformationsdienste (IIS) 5.1 ausgeführt wird, muss von Duplexclients eine Clientbasisadresse mithilfe der <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>-Klasse angegeben werden, da andernfalls eine Ausnahme ausgelöst wird. Im folgenden Codebeispiel wird die entsprechende Umsetzung in Code veranschaulicht.  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 Im folgenden Codebeispiel wird die entsprechende Umsetzung in einer Konfigurationsdatei veranschaulicht.  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a>Asynchrones Aufrufen von Diensten  
 Die Art und Weise eines Vorgangsaufrufs ist ausschließlich Angelegenheit des Cliententwicklers. Dies liegt daran, dass die Nachrichten, aus denen sich ein Vorgang zusammensetzt, bei der Darstellung in verwaltetem Code entweder synchronen oder asynchronen Methoden zugeordnet werden können. Wenn Sie einen Client erstellen möchten, mit dem Vorgänge asynchron aufgerufen werden, können Sie daher mit Svcutil.exe und der Option `/async` asynchronen Clientcode generieren. Weitere Informationen finden Sie unter [Vorgehensweise: Asynchrones Aufrufen von Dienstvorgängen](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).  
  
## <a name="calling-services-using-wcf-client-channels"></a>Aufrufen von Diensten mithilfe der WCF-Clientkanäle.  
 WCF-Clienttypen erweitern <xref:System.ServiceModel.ClientBase%601>, die wiederum leitet sich von <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> Schnittstelle, um das zugrunde liegende kanalsystem verfügbar zu machen. Sie können Dienste aufrufen, indem Sie den Zieldienstvertrag mit der <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>-Klasse verwenden. Weitere Informationen finden Sie unter [WCF-Clientarchitektur](../../../docs/framework/wcf/feature-details/client-architecture.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>  
 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
