---
title: Übersicht über den WCF-Client
description: Informieren Sie sich über die Funktionen von Client Anwendungen, über das konfigurieren, erstellen und Verwenden eines WCF-Clients und über das Sichern von Client Anwendungen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], architecture
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
ms.openlocfilehash: 1330861b0f6c1d6e41fdd4bba3876654c57d89f7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240783"
---
# <a name="wcf-client-overview"></a>Übersicht über WCF-Clients

In diesem Abschnitt wird beschrieben, was Client Anwendungen tun, wie ein Windows Communication Foundation (WCF)-Client konfiguriert, erstellt und verwendet wird und wie Client Anwendungen gesichert werden.  
  
## <a name="using-wcf-client-objects"></a>Verwenden von WCF-Clientobjekten  

 Eine Client Anwendung ist eine verwaltete Anwendung, die einen WCF-Client für die Kommunikation mit einer anderen Anwendung verwendet. Zum Erstellen einer Client Anwendung für einen WCF-Dienst sind die folgenden Schritte erforderlich:  
  
1. Abrufen des Dienstvertrags, der Bindungen und der Adressinformationen für einen Dienstendpunkt.  
  
2. Erstellen Sie mithilfe dieser Informationen einen WCF-Client.  
  
3. Aufrufen von Vorgängen.  
  
4. Schließen Sie das WCF-Client Objekt.  
  
In den folgenden Abschnitten finden Sie eine Erläuterung dieser Schritte und kurze Einführungen in die folgenden Probleme:  
  
- Behandeln von Fehlern  
  
- Konfigurieren und Sichern von Clients.  
  
- Erstellen von Rückrufobjekten für Duplexdienste  
  
- Asynchrones Aufrufen von Diensten.  
  
- Aufrufen von Diensten mithilfe von Clientkanälen.  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a>Abrufen von Dienstvertrag, Bindungen und Adressen  

 In WCF modellieren Dienste und Clients Verträge mithilfe verwalteter Attribute, Schnittstellen und Methoden. Soll eine Verbindung zu einem Dienst in einer Clientanwendung hergestellt werden, muss der Informationstyp für den Dienstvertrag abgerufen werden. In der Regel erhalten Sie Typinformationen für den Dienstvertrag mit dem [Service Model Metadata Utility-Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md). Das Hilfsprogramm lädt Metadaten aus dem Dienst herunter, konvertiert sie in eine verwaltete Quell Code Datei in der Sprache Ihrer Wahl und erstellt eine Konfigurationsdatei für die Client Anwendung, die Sie zum Konfigurieren des WCF-Client Objekts verwenden können. Wenn Sie z. b. ein WCF-Client Objekt zum Aufrufen von erstellen `MyCalculatorService` und wissen, dass die Metadaten für diesen Dienst unter veröffentlicht werden, wird `http://computerName/MyCalculatorService/Service.svc?wsdl` im folgenden Codebeispiel gezeigt, wie Sie mit Svcutil.exe eine Datei abrufen, die `ClientCode.vb` den Dienstvertrag in verwaltetem Code enthält.  
  
```console  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 Sie können diesen Vertrags Code entweder in die Client Anwendung oder in eine andere Assembly kompilieren, die von der Client Anwendung zum Erstellen eines WCF-Client Objekts verwendet werden kann. Sie können die Konfigurationsdatei zum Konfigurieren des Clientobjekts verwenden, um eine ordnungsgemäße Verbindung zum Dienst herzustellen.  
  
 Ein Beispiel für diesen Prozess finden Sie unter Gewusst [wie: Erstellen eines Clients](how-to-create-a-wcf-client.md). Ausführlichere Informationen zu Verträgen finden Sie unter [Verträge](./feature-details/contracts.md).  
  
## <a name="create-a-wcf-client-object"></a>Erstellen eines WCF-Clientobjekts  

 Ein WCF-Client ist ein lokales Objekt, das einen WCF-Dienst in einer Form darstellt, die der Client für die Kommunikation mit dem Remote Dienst verwenden kann. WCF-Client Typen implementieren den Ziel Dienstvertrag. Wenn Sie also einen erstellen und konfigurieren, können Sie das Client Objekt direkt zum Aufrufen von Dienst Vorgängen verwenden. Die WCF-Laufzeit konvertiert die Methodenaufrufe in Nachrichten, sendet Sie an den Dienst, lauscht auf die Antwort und gibt diese Werte als Rückgabewerte oder Parameter an das WCF-Client Objekt zurück `out` `ref` .  
  
 Sie können auch WCF-Client Kanal Objekte verwenden, um eine Verbindung mit Diensten herzustellen und diese zu verwenden. Weitere Informationen finden Sie unter [WCF-Client Architektur](./feature-details/client-architecture.md).  
  
#### <a name="creating-a-new-wcf-object"></a>Erstellen eines neuen WCF-Objekts  

 Wenn Sie die Verwendung einer <xref:System.ServiceModel.ClientBase%601>-Klasse darstellen möchten, nehmen Sie an, dass der folgende einfache Dienstvertrag von einer Dienstanwendung generiert wurde.  
  
> [!NOTE]
> Wenn Sie den WCF-Client mithilfe von Visual Studio erstellen, werden Objekte automatisch in den Objektkatalog geladen, wenn Sie dem Projekt einen Dienst Verweis hinzufügen.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Wenn Sie Visual Studio nicht verwenden, überprüfen Sie den generierten Vertrags Code, um den Typ zu finden, der erweitert, <xref:System.ServiceModel.ClientBase%601> und die Dienstvertragschnittstelle `ISampleService` . In diesem Fall entspricht der Typ dem folgenden Code:  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 Diese Klasse kann als lokales Objekt mithilfe eines der Konstruktoren erstellt, konfiguriert und anschließend zum Herstellen einer Verbindung zu einem Dienst vom Typ `ISampleService` verwendet werden.  
  
 Es wird empfohlen, zuerst das WCF-Client Objekt zu erstellen und es dann zu verwenden und in einem einzelnen try/catch-Block zu schließen. Verwenden Sie die- `using` Anweisung ( `Using` in Visual Basic) nicht, da Ausnahmen in bestimmten Fehlermodi maskiert werden können. Weitere Informationen finden Sie in den folgenden Abschnitten sowie [unter schließen und Abbrechen, um WCF-Client Ressourcen freizugeben](./samples/use-close-abort-release-wcf-client-resources.md).  
  
### <a name="contracts-bindings-and-addresses"></a>Verträge, Bindungen und Adressen  

 Bevor Sie ein WCF-Client Objekt erstellen können, müssen Sie das-Client Objekt konfigurieren. Insbesondere muss Sie über einen Dienst *Endpunkt* verfügen, der verwendet werden kann. Ein Endpunkt ist die Kombination eines Dienstvertrags, einer Bindung und einer Adresse. (Weitere Informationen zu Endpunkten finden Sie unter [Endpunkte: Adressen, Bindungen und Verträge](./feature-details/endpoints-addresses-bindings-and-contracts.md).) Normalerweise befinden sich diese Informationen im- [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-of-client.md) Element in einer Konfigurationsdatei der Client Anwendung, z. b. der, die das Svcutil.exe Tool generiert, und werden automatisch geladen, wenn Sie das-Client Objekt erstellen. Beide WCF-Client Typen verfügen auch über über Ladungen, die es Ihnen ermöglichen, diese Informationen Programm gesteuert anzugeben.  
  
 Beispielsweise beinhaltet eine generierte Konfigurationsdatei für einen in den vorherigen Beispielen verwendeten `ISampleService` die folgenden Endpunktinformationen.  
  
 [!code-xml[C_GeneratedCodeFiles#19](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  
  
 Mit dieser Konfigurationsdatei wird ein Zielendpunkt im `<client>`-Element angegeben. Weitere Informationen zum Verwenden mehrerer Ziel Endpunkte finden Sie unter <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> oder in den <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> Konstruktoren.  
  
## <a name="calling-operations"></a>Aufrufen von Vorgängen  

 Wenn Sie ein Client Objekt erstellt und konfiguriert haben, erstellen Sie einen try/catch-Block, rufen Sie Vorgänge auf die gleiche Weise auf wie bei einem lokalen Objekt, und schließen Sie das WCF-Client Objekt. Wenn die Client Anwendung den ersten Vorgang aufruft, öffnet WCF automatisch den zugrunde liegenden Kanal, und der zugrunde liegende Kanal wird geschlossen, wenn das Objekt wieder verwendet wird. (Es besteht auch die Möglichkeit, den Kanal vor oder nach dem Aufruf anderer Vorgänge explizit zu öffnen und zu schließen.)  
  
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
  
 Sie können Vorgänge aufrufen, indem Sie ein WCF-Client Objekt erstellen und dessen Methoden aufrufen, wie im folgenden Codebeispiel veranschaulicht. Das Öffnen, aufrufen und Schließen des WCF-Client Objekts erfolgt innerhalb eines einzelnen try/catch-Blocks. Weitere Informationen finden Sie unter [zugreifen auf Dienste mithilfe eines WCF-Clients](./feature-details/accessing-services-using-a-client.md) und [Verwenden von schließen und Abbrechen, um WCF-Client Ressourcen freizugeben](./samples/use-close-abort-release-wcf-client-resources.md).  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a>Behandeln von Fehlern  

 Ausnahmen können in einer Clientanwendung unter folgenden Bedingungen auftreten: beim Öffnen des zugrunde liegenden Kanals (entweder explizit oder automatisch durch Aufrufen eines Vorgangs), beim Aufrufen von Vorgängen mit dem Client- oder Kanalobjekt oder beim Schließen des zugrunde liegenden Clientkanals. Anwendungen sollten zumindest erwarten, mögliche <xref:System.TimeoutException?displayProperty=nameWithType>-Ausnahmen und <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>-Ausnahmen sowie jegliche <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>-Objekte zu behandeln, die infolge von durch Vorgänge zurückgegebenen SOAP-Fehlern ausgelöst werden. Im Vorgangsvertrag angegebene SOAP-Fehler werden als <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> zu Clientanwendungen heraufgestuft, wobei der Typparameter der Detailtyp des SOAP-Fehlers ist. Weitere Informationen zur Behandlung von Fehlerbedingungen in einer Client Anwendung finden Sie unter [senden und empfangen von Fehlern](sending-and-receiving-faults.md). Ein umfassendes Beispiel, das zeigt, wie Fehler in einem Client behandelt werden, finden Sie unter [erwartete Ausnahmen](./samples/expected-exceptions.md).  
  
## <a name="configuring-and-securing-clients"></a>Konfigurieren und Sichern von Clients  

 Das Konfigurieren eines Clients beginnt mit dem erforderlichen Laden von Zielendpunktinformationen für das Client- oder Kanalobjekt (in der Regel von einer Konfigurationsdatei), obwohl diese Informationen auch programmgesteuert mithilfe der Clientkonstruktoren und -eigenschaften geladen werden können. Allerdings sind zusätzliche Konfigurationsschritte erforderlich, um ein bestimmtes Clientverhalten zu ermöglichen und zahlreichen Sicherheitsszenarien gerecht zu werden.  
  
 Beispielsweise werden Sicherheitsanforderungen für Dienstverträge in der Dienstvertragschnittstelle deklariert, und falls mit „Svcutil.exe“ eine Konfigurationsdatei erstellt wurde, beinhaltet diese Datei normalerweise eine Bindung, die den Sicherheitsanforderungen des Diensts entspricht. In einigen Fällen sind jedoch möglicherweise zusätzliche Sicherheitskonfigurationen erforderlich, zum Beispiel die Konfiguration von Clientanmeldeinformationen. Umfassende Informationen zur Konfiguration der Sicherheit für WCF-Clients finden Sie unter [Sichern von Clients](securing-clients.md).  
  
 Zudem können einige benutzerdefinierte Änderungen in Clientanwendungen aktiviert werden, zum Beispiel benutzerdefiniertes Laufzeitverhalten. Weitere Informationen zum Konfigurieren eines benutzerdefinierten Client Verhaltens finden Sie unter [Konfigurieren von Client](configuring-client-behaviors.md)Verhalten.  
  
## <a name="creating-callback-objects-for-duplex-services"></a>Erstellen von Rückrufobjekten für Duplexdienste  

 Mit Duplexdiensten wird ein Rückrufvertrag angegeben, den die Clientanwendung implementieren muss, um gemäß den Vertragsanforderungen ein Rückrufobjekt für den aufzurufenden Dienst bereitzustellen. Obgleich es sich bei Rückrufobjekten nicht um vollständige Dienste handelt (beispielsweise kann ein Kanal nicht mit einem Rückrufobjekt initiiert werden), können Sie zu Implementierungs- und Konfigurationszwecken als eine Art Dienst betrachtet werden.  
  
 Clients von Duplexdiensten müssen folgende Vorgänge ausführen:  
  
- Eine Rückrufvertragsklasse implementieren.  
  
- Erstellen Sie eine Instanz der Rückruf Vertrags Implementierungs Klasse, und verwenden Sie Sie zum Erstellen des- <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> Objekts, das Sie an den WCF-Clientkonstruktor übergeben.  
  
- Vorgänge aufrufen und Vorgangsrückrufe behandeln.  
  
 Duplex-WCF-Client Objekte funktionieren wie ihre nicht-Duplex-Gegenstücke, mit der Ausnahme, dass Sie die für die Unterstützung von Rückrufen erforderliche Funktionalität verfügbar machen, einschließlich der Konfiguration des Rückruf Dienstanbieter.  
  
 Beispielsweise können verschiedene Aspekte des Laufzeitverhaltens des Rückrufobjekts mithilfe der Eigenschaften des <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>-Attributs in der Rückrufklasse gesteuert werden. Ein weiteres Beispiel ist die Verwendung der <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType>-Klasse, um die Rückgabe von Ausnahmeinformationen an Dienste, die das Rückrufobjekt aufrufen, zu ermöglichen. Weitere Informationen finden Sie unter [Duplex Dienste](./feature-details/duplex-services.md). Ein umfassendes Beispiel finden Sie unter [Duplex](./samples/duplex.md).  
  
 Auf Windows XP-Computern, auf denen Internetinformationsdienste (IIS) 5.1 ausgeführt wird, muss von Duplexclients eine Clientbasisadresse mithilfe der <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>-Klasse angegeben werden, da andernfalls eine Ausnahme ausgelöst wird. Im folgenden Codebeispiel wird die entsprechende Umsetzung in Code veranschaulicht.  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 Im folgenden Codebeispiel wird die entsprechende Umsetzung in einer Konfigurationsdatei veranschaulicht.  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a>Asynchrones Aufrufen von Diensten  

 Die Art und Weise eines Vorgangsaufrufs ist ausschließlich Angelegenheit des Cliententwicklers. Dies liegt daran, dass die Nachrichten, aus denen sich ein Vorgang zusammensetzt, bei der Darstellung in verwaltetem Code entweder synchronen oder asynchronen Methoden zugeordnet werden können. Wenn Sie einen Client erstellen möchten, mit dem Vorgänge asynchron aufgerufen werden, können Sie daher mit Svcutil.exe und der Option `/async` asynchronen Clientcode generieren. Weitere Informationen finden Sie unter Vorgehensweise [: Asynchrones Abrufen von Dienst Vorgängen](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).  
  
## <a name="calling-services-using-wcf-client-channels"></a>Aufrufen von Diensten mithilfe der WCF-Clientkanäle.  

 WCF-Client Typen erweitern <xref:System.ServiceModel.ClientBase%601> , die selbst von <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> der-Schnittstelle abgeleitet werden, um das zugrunde liegende Channel-System verfügbar Sie können Dienste aufrufen, indem Sie den Zieldienstvertrag mit der <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>-Klasse verwenden. Weitere Informationen finden Sie unter [WCF-Client Architektur](./feature-details/client-architecture.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
