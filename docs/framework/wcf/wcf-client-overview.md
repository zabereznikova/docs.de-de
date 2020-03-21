---
title: Übersicht über den WCF-Client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], architecture
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
ms.openlocfilehash: 7905d540e0f06dd2863cf80381210307e3021918
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183062"
---
# <a name="wcf-client-overview"></a>Übersicht über den WCF-Client
In diesem Abschnitt wird beschrieben, was Clientanwendungen tun, wie sie einen Windows Communication Foundation(WCF)-Client konfigurieren, erstellen und verwenden und wie Clientanwendungen gesichert werden.  
  
## <a name="using-wcf-client-objects"></a>Verwenden von WCF-Clientobjekten  
 Eine Clientanwendung ist eine verwaltete Anwendung, die einen WCF-Client verwendet, um mit einer anderen Anwendung zu kommunizieren. Zum Erstellen einer Clientanwendung für einen WCF-Dienst sind die folgenden Schritte erforderlich:  
  
1. Abrufen des Dienstvertrags, der Bindungen und der Adressinformationen für einen Dienstendpunkt.  
  
2. Erstellen Sie einen WCF-Client mit diesen Informationen.  
  
3. Aufrufen von Vorgängen.  
  
4. Schließen Sie das WCF-Clientobjekt.  
  
 In den folgenden Abschnitten finden Sie eine Erläuterung dieser Schritte und kurze Einführungen in die folgenden Probleme:  
  
- Behandeln von Fehlern  
  
- Konfigurieren und Sichern von Clients.  
  
- Erstellen von Rückrufobjekten für Duplexdienste  
  
- Asynchrones Aufrufen von Diensten.  
  
- Aufrufen von Diensten mithilfe von Clientkanälen.  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a>Abrufen von Dienstvertrag, Bindungen und Adressen  
 In WCF modellieren Dienste und Clients Verträge mithilfe verwalteter Attribute, Schnittstellen und Methoden. Soll eine Verbindung zu einem Dienst in einer Clientanwendung hergestellt werden, muss der Informationstyp für den Dienstvertrag abgerufen werden. In der Regel verwenden Sie das [ServiceModel Metadata Utility Tool (Svcutil.exe),](servicemodel-metadata-utility-tool-svcutil-exe.md)das Metadaten aus dem Dienst herunterlädt, in eine verwaltete Quellcodedatei in der Sprache Ihrer Wahl konvertiert und eine Clientanwendungskonfigurationsdatei erstellt, mit der Sie Ihr WCF-Clientobjekt konfigurieren können. Wenn Sie z. B. ein WCF-Clientobjekt `MyCalculatorService`erstellen, um eine aufzurufen, und `http://computerName/MyCalculatorService/Service.svc?wsdl`Sie wissen, dass die Metadaten für diesen Dienst unter `ClientCode.vb` veröffentlicht werden, wird im folgenden Codebeispiel gezeigt, wie Sie Svcutil.exe verwenden, um eine Datei zu erhalten, die den Dienstvertrag in verwaltetem Code enthält.  
  
```console  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 Sie können diesen Vertragscode entweder in die Clientanwendung oder in eine andere Assembly kompilieren, die die Clientanwendung dann zum Erstellen eines WCF-Clientobjekts verwenden kann. Sie können die Konfigurationsdatei zum Konfigurieren des Clientobjekts verwenden, um eine ordnungsgemäße Verbindung zum Dienst herzustellen.  
  
 Ein Beispiel für diesen Prozess finden Sie unter [Gewusst wie: Erstellen eines Clients](how-to-create-a-wcf-client.md). Weitere Informationen zu Verträgen finden Sie unter [Verträge](./feature-details/contracts.md).  
  
## <a name="create-a-wcf-client-object"></a>Erstellen eines WCF-Clientobjekts  
 Ein WCF-Client ist ein lokales Objekt, das einen WCF-Dienst in einer Form darstellt, die der Client für die Kommunikation mit dem Remotedienst verwenden kann. WCF-Clienttypen implementieren den Zieldienstvertrag, sodass Sie beim Erstellen und Konfigurieren des Clientobjekts direkt Dienstvorgänge aufrufen können. Die WCF-Laufzeit konvertiert die Methodenaufrufe in Nachrichten, sendet sie an den Dienst, überwacht die Antwort und gibt `out` `ref` diese Werte als Rückgabewerte oder Parameter an das WCF-Clientobjekt zurück.  
  
 Sie können auch WCF-Clientkanalobjekte verwenden, um eine Verbindung mit Diensten herzustellen und diese zu verwenden. Weitere Informationen finden Sie unter [WCF Client Architecture](./feature-details/client-architecture.md).  
  
#### <a name="creating-a-new-wcf-object"></a>Erstellen eines neuen WCF-Objekts  
 Wenn Sie die Verwendung einer <xref:System.ServiceModel.ClientBase%601>-Klasse darstellen möchten, nehmen Sie an, dass der folgende einfache Dienstvertrag von einer Dienstanwendung generiert wurde.  
  
> [!NOTE]
> Wenn Sie Visual Studio zum Erstellen ihres WCF-Clients verwenden, werden Objekte automatisch in den Objektbrowser geladen, wenn Sie dem Projekt einen Dienstverweis hinzufügen.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Wenn Sie Visual Studio nicht verwenden, überprüfen Sie den generierten Vertragscode, um den Typ zu finden, der erweitert wird, <xref:System.ServiceModel.ClientBase%601> und die Servicevertragsschnittstelle `ISampleService`. In diesem Fall entspricht der Typ dem folgenden Code:  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 Diese Klasse kann als lokales Objekt mithilfe eines der Konstruktoren erstellt, konfiguriert und anschließend zum Herstellen einer Verbindung zu einem Dienst vom Typ `ISampleService` verwendet werden.  
  
 Es wird empfohlen, zuerst Ihr WCF-Clientobjekt zu erstellen, es dann zu verwenden und in einem einzelnen try/catch-Block zu schließen. Sie sollten die `using` Anweisung`Using` (in Visual Basic) nicht verwenden, da sie Ausnahmen in bestimmten Fehlermodi maskieren kann. Weitere Informationen finden Sie in den folgenden Abschnitten sowie [Verwenden von Schließen und Abbrechen zum Freigeben von WCF-Clientressourcen](./samples/use-close-abort-release-wcf-client-resources.md).  
  
### <a name="contracts-bindings-and-addresses"></a>Verträge, Bindungen und Adressen  
 Bevor Sie ein WCF-Clientobjekt erstellen können, müssen Sie das Clientobjekt konfigurieren. Insbesondere muss es über einen *Dienstendpunkt* verfügen, den es verwenden kann. Ein Endpunkt ist die Kombination eines Dienstvertrags, einer Bindung und einer Adresse. (Weitere Informationen zu Endpunkten finden Sie unter [Endpunkte: Adressen, Bindungen und Verträge](./feature-details/endpoints-addresses-bindings-and-contracts.md).) In der Regel befinden sich diese Informationen im [ \<Endpunkt>](../configure-apps/file-schema/wcf/endpoint-of-client.md) Element in einer Clientanwendungskonfigurationsdatei, z. B. die, die das Tool Svcutil.exe generiert, und werden beim Erstellen des Clientobjekts automatisch geladen. Beide WCF-Clienttypen verfügen auch über Überladungen, mit denen Sie diese Informationen programmgesteuert angeben können.  
  
 Beispielsweise beinhaltet eine generierte Konfigurationsdatei für einen in den vorherigen Beispielen verwendeten `ISampleService` die folgenden Endpunktinformationen.  
  
 [!code-xml[C_GeneratedCodeFiles#19](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  
  
 Mit dieser Konfigurationsdatei wird ein Zielendpunkt im `<client>`-Element angegeben. Weitere Informationen zur Verwendung mehrerer Zielendpunkte finden Sie unter <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType> oder die <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType> Konstruktoren.  
  
## <a name="calling-operations"></a>Aufrufen von Vorgängen  
 Nachdem Sie ein Clientobjekt erstellt und konfiguriert haben, erstellen Sie einen try/catch-Block, rufen Sie Vorgänge auf die gleiche Weise auf, wie Wenn das Objekt lokal wäre, und schließen Sie das WCF-Clientobjekt. Wenn die Clientanwendung den ersten Vorgang aufruft, öffnet WCF automatisch den zugrunde liegenden Kanal, und der zugrunde liegende Kanal wird geschlossen, wenn das Objekt wiederverwendet wird. (Es besteht auch die Möglichkeit, den Kanal vor oder nach dem Aufruf anderer Vorgänge explizit zu öffnen und zu schließen.)  
  
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
  
 Sie können Vorgänge aufrufen, indem Sie ein WCF-Clientobjekt erstellen und seine Methoden aufrufen, wie das folgende Codebeispiel veranschaulicht. Beachten Sie, dass das Öffnen, Aufrufen und Schließen des WCF-Clientobjekts innerhalb eines einzelnen try/catch-Blocks erfolgt. Weitere Informationen finden Sie unter [Zugreifen auf Dienste mithilfe eines WCF-Clients](./feature-details/accessing-services-using-a-client.md) und Verwenden von Schließen und Abbrechen zum Freigeben von [WCF-Clientressourcen](./samples/use-close-abort-release-wcf-client-resources.md).  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a>Behandlung von Fehlern  
 Ausnahmen können in einer Clientanwendung unter folgenden Bedingungen auftreten: beim Öffnen des zugrunde liegenden Kanals (entweder explizit oder automatisch durch Aufrufen eines Vorgangs), beim Aufrufen von Vorgängen mit dem Client- oder Kanalobjekt oder beim Schließen des zugrunde liegenden Clientkanals. Anwendungen sollten zumindest erwarten, mögliche <xref:System.TimeoutException?displayProperty=nameWithType>-Ausnahmen und <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>-Ausnahmen sowie jegliche <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>-Objekte zu behandeln, die infolge von durch Vorgänge zurückgegebenen SOAP-Fehlern ausgelöst werden. Im Vorgangsvertrag angegebene SOAP-Fehler werden als <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> zu Clientanwendungen heraufgestuft, wobei der Typparameter der Detailtyp des SOAP-Fehlers ist. Weitere Informationen zum Behandeln von Fehlerbedingungen in einer Clientanwendung finden Sie unter [Senden und Empfangen](sending-and-receiving-faults.md)von Fehlern . Ein vollständiges Beispiel finden Sie unter Erwartete [Ausnahmen.](./samples/expected-exceptions.md)  
  
## <a name="configuring-and-securing-clients"></a>Konfigurieren und Sichern von Clients  
 Das Konfigurieren eines Clients beginnt mit dem erforderlichen Laden von Zielendpunktinformationen für das Client- oder Kanalobjekt (in der Regel von einer Konfigurationsdatei), obwohl diese Informationen auch programmgesteuert mithilfe der Clientkonstruktoren und -eigenschaften geladen werden können. Allerdings sind zusätzliche Konfigurationsschritte erforderlich, um ein bestimmtes Clientverhalten zu ermöglichen und zahlreichen Sicherheitsszenarien gerecht zu werden.  
  
 Beispielsweise werden Sicherheitsanforderungen für Dienstverträge in der Dienstvertragschnittstelle deklariert, und falls mit „Svcutil.exe“ eine Konfigurationsdatei erstellt wurde, beinhaltet diese Datei normalerweise eine Bindung, die den Sicherheitsanforderungen des Diensts entspricht. In einigen Fällen sind jedoch möglicherweise zusätzliche Sicherheitskonfigurationen erforderlich, zum Beispiel die Konfiguration von Clientanmeldeinformationen. Vollständige Informationen zur Konfiguration der Sicherheit für WCF-Clients finden Sie unter Sichern von [Clients](securing-clients.md).  
  
 Zudem können einige benutzerdefinierte Änderungen in Clientanwendungen aktiviert werden, zum Beispiel benutzerdefiniertes Laufzeitverhalten. Weitere Informationen zum Konfigurieren eines benutzerdefinierten Clientverhaltens finden Sie unter [Konfigurieren von Clientverhalten](configuring-client-behaviors.md).  
  
## <a name="creating-callback-objects-for-duplex-services"></a>Erstellen von Rückrufobjekten für Duplexdienste  
 Mit Duplexdiensten wird ein Rückrufvertrag angegeben, den die Clientanwendung implementieren muss, um gemäß den Vertragsanforderungen ein Rückrufobjekt für den aufzurufenden Dienst bereitzustellen. Obgleich es sich bei Rückrufobjekten nicht um vollständige Dienste handelt (beispielsweise kann ein Kanal nicht mit einem Rückrufobjekt initiiert werden), können Sie zu Implementierungs- und Konfigurationszwecken als eine Art Dienst betrachtet werden.  
  
 Clients von Duplexdiensten müssen folgende Vorgänge ausführen:  
  
- Eine Rückrufvertragsklasse implementieren.  
  
- Erstellen Sie eine Instanz der Rückrufvertragsimplementierungsklasse, <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> und erstellen Sie es, um das Objekt zu erstellen, das Sie an den WCF-Clientkonstruktor übergeben.  
  
- Vorgänge aufrufen und Vorgangsrückrufe behandeln.  
  
 Duplex-WCF-Clientobjekte funktionieren wie ihre nichtduplex-Entsprechungen, mit der Ausnahme, dass sie die Funktionen verfügbar machen, die zum Unterstützen von Rückrufen erforderlich sind, einschließlich der Konfiguration des Rückrufdienstes.  
  
 Beispielsweise können verschiedene Aspekte des Laufzeitverhaltens des Rückrufobjekts mithilfe der Eigenschaften des <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>-Attributs in der Rückrufklasse gesteuert werden. Ein weiteres Beispiel ist die Verwendung der <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType>-Klasse, um die Rückgabe von Ausnahmeinformationen an Dienste, die das Rückrufobjekt aufrufen, zu ermöglichen. Weitere Informationen finden Sie unter [Duplexdienste](./feature-details/duplex-services.md). Ein vollständiges Beispiel finden Sie unter [Duplex](./samples/duplex.md).  
  
 Auf Windows XP-Computern, auf denen Internetinformationsdienste (IIS) 5.1 ausgeführt wird, muss von Duplexclients eine Clientbasisadresse mithilfe der <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>-Klasse angegeben werden, da andernfalls eine Ausnahme ausgelöst wird. Im folgenden Codebeispiel wird die entsprechende Umsetzung in Code veranschaulicht.  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 Im folgenden Codebeispiel wird die entsprechende Umsetzung in einer Konfigurationsdatei veranschaulicht.  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a>Asynchrones Aufrufen von Diensten  
 Die Art und Weise eines Vorgangsaufrufs ist ausschließlich Angelegenheit des Cliententwicklers. Dies liegt daran, dass die Nachrichten, aus denen sich ein Vorgang zusammensetzt, bei der Darstellung in verwaltetem Code entweder synchronen oder asynchronen Methoden zugeordnet werden können. Wenn Sie einen Client erstellen möchten, mit dem Vorgänge asynchron aufgerufen werden, können Sie daher mit Svcutil.exe und der Option `/async` asynchronen Clientcode generieren. Weitere Informationen finden Sie unter [Gewusst wie: Asynchronaufrufen von Dienstvorgängen](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).  
  
## <a name="calling-services-using-wcf-client-channels"></a>Aufrufen von Diensten mithilfe der WCF-Clientkanäle.  
 WCF-Clienttypen <xref:System.ServiceModel.ClientBase%601>erweitern , die <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> selbst von der Schnittstelle ableiten, um das zugrunde liegende Kanalsystem verfügbar zu machen. Sie können Dienste aufrufen, indem Sie den Zieldienstvertrag mit der <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>-Klasse verwenden. Weitere Informationen finden Sie unter [WCF Client Architecture](./feature-details/client-architecture.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
