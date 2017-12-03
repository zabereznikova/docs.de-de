---
title: "Übersicht über den WCF-Client"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: clients [WCF], architecture
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6333db92d010eab7765cfc62a9f64601d5b82d55
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-client-overview"></a>Übersicht über den WCF-Client
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
 In [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Dienst- und Clientmodellverträge mit verwalteten Attributen, Schnittstellen und Methoden. Soll eine Verbindung zu einem Dienst in einer Clientanwendung hergestellt werden, muss der Informationstyp für den Dienstvertrag abgerufen werden. In der Regel wird Sie zu diesem Zweck die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), konvertiert es in eine verwaltete Quellcodedatei in der Sprache Ihrer Wahl der Metadaten vom Dienst heruntergeladen, und erstellt einen Client Anwendungskonfigurationsdatei, die Sie verwenden können, so konfigurieren Sie Ihre [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Clientobjekt. Falls Sie beispielsweise ein [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientobjekt erstellen, um `MyCalculatorService` aufzurufen und wissen, dass die Metadaten für diesen Dienst unter `http://computerName/MyCalculatorService/Service.svc?wsdl` veröffentlicht werden, wird im folgenden Codebeispiel die Verwendung von Svcutil.exe zum Abrufen einer Datei vom Typ `ClientCode.vb` gezeigt, die den Dienstvertrag in verwaltetem Code beinhaltet.  
  
```  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 Dieser Vertragscode kann entweder in der Clientanwendung oder einer anderen Assembly kompiliert werden, die von der Clientanwendung anschließend zum Erstellen eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientobjekts verwendet werden kann. Sie können die Konfigurationsdatei zum Konfigurieren des Clientobjekts verwenden, um eine ordnungsgemäße Verbindung zum Dienst herzustellen.  
  
 Ein Beispiel dieses Prozesses finden Sie unter [Vorgehensweise: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md). Weitere Informationen zu Verträgen, finden Sie unter [Verträge](../../../docs/framework/wcf/feature-details/contracts.md).  
  
## <a name="create-a-wcf-client-object"></a>Erstellen eines WCF-Clientobjekts  
 Ein [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Client ist ein lokales Objekt, das einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst in einer Form darstellt, die sich für den Client zum Kommunizieren mit dem Remotedienst eignet. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clienttypen implementieren den Zieldienstvertrag, sodass Dienstvorgänge nach dem Erstellen und Konfigurieren eines Vertrags direkt mit dem Clientobjekt aufgerufen werden können. Die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Laufzeit konvertiert die Methode Methodenaufrufe in Nachrichten, sendet diese an den Dienst, hört die Antwort und gibt diese Werte in der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Clientobjekt als Rückgabewerte oder `out` oder `ref` Parameter.  
  
 Sie können auch mit [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientkanalobjekten eine Verbindung zu Diensten herstellen und diese verwenden. Weitere Informationen finden Sie unter [WCF-Clientarchitektur](../../../docs/framework/wcf/feature-details/client-architecture.md).  
  
#### <a name="creating-a-new-wcf-object"></a>Erstellen eines neuen WCF-Objekts  
 Wenn Sie die Verwendung einer <xref:System.ServiceModel.ClientBase%601>-Klasse darstellen möchten, nehmen Sie an, dass der folgende einfache Dienstvertrag von einer Dienstanwendung generiert wurde.  
  
> [!NOTE]
>  Wird zum Erstellen des [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Clients [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] verwendet, werden Objekte beim Hinzufügen eines Dienstverweises zum Projekt automatisch in den Objektkatalog geladen.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Wird [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] nicht verwendet, prüfen Sie den generierten Vertragscode, um den Typ zu suchen, durch den <xref:System.ServiceModel.ClientBase%601> und die Dienstvertragsschnittstelle `ISampleService` erweitert werden. In diesem Fall entspricht der Typ dem folgenden Code:  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 Diese Klasse kann als lokales Objekt mithilfe eines der Konstruktoren erstellt, konfiguriert und anschließend zum Herstellen einer Verbindung zu einem Dienst vom Typ `ISampleService` verwendet werden.  
  
 Es wird empfohlen, zuerst das [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientobjekt zu erstellen, es anschließend zu verwenden und in einem einzelnen try/catch-Block zu schließen. Verwenden Sie nicht die `using`-Anweisung (`Using` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), da Ausnahmen in bestimmten Fehlermodi möglicherweise nicht angezeigt werden. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]den folgenden Abschnitten werden auch als [Vermeiden von Problemen mit der Using-Anweisung](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
### <a name="contracts-bindings-and-addresses"></a>Verträge, Bindungen und Adressen  
 Bevor ein [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientobjekt erstellt werden kann, ist eine Konfiguration des Clientobjekts erforderlich. Insbesondere benötigen sie einen Dienst *Endpunkt* verwenden. Ein Endpunkt ist die Kombination eines Dienstvertrags, einer Bindung und einer Adresse. ([!INCLUDE[crabout](../../../includes/crabout-md.md)] Endpunkte finden Sie unter [Endpunkte: Adressen, Bindungen und Verträge](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md).) In der Regel befindet sich diese Informationen den [ \<Endpunkt >](../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md) Element in einer Konfigurationsdatei der Clientanwendung, beispielsweise das Tool "Svcutil.exe" generiert und wird automatisch geladen, wenn Sie Ihren Client erstellen -Objekt. Beide [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clienttypen verfügen auch über Überladungen, die das programmgesteuerte Angeben dieser Informationen ermöglichen.  
  
 Beispielsweise beinhaltet eine generierte Konfigurationsdatei für einen in den vorherigen Beispielen verwendeten `ISampleService` die folgenden Endpunktinformationen.  
  
 [!code-xml[C_GeneratedCodeFiles#19](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  
  
 Mit dieser Konfigurationsdatei wird ein Zielendpunkt im `<client>`-Element angegeben. [!INCLUDE[crabout](../../../includes/crabout-md.md)] das Verwenden mehrerer Zielendpunkte finden Sie im <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType>-Konstruktor oder im <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType>-Konstruktor.  
  
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
  
 Sie können Vorgänge durch Erstellen eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientobjekts und durch Aufrufen der Methoden aufrufen (siehe folgendes Beispiel). Das Öffnen, Aufrufen und Schließen des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientobjekts erfolgt innerhalb eines einzelnen try/catch-Blocks. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Den Zugriff auf Dienste mithilfe eines WCF-Clients](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md) und [Vermeiden von Problemen mit der Using-Anweisung](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a>Behandeln von Fehlern  
 Ausnahmen können in einer Clientanwendung unter folgenden Bedingungen auftreten: beim Öffnen des zugrunde liegenden Kanals (entweder explizit oder automatisch durch Aufrufen eines Vorgangs), beim Aufrufen von Vorgängen mit dem Client- oder Kanalobjekt oder beim Schließen des zugrunde liegenden Clientkanals. Anwendungen sollten zumindest erwarten, mögliche <xref:System.TimeoutException?displayProperty=nameWithType>-Ausnahmen und <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>-Ausnahmen sowie jegliche <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>-Objekte zu behandeln, die infolge von durch Vorgänge zurückgegebenen SOAP-Fehlern ausgelöst werden. Im Vorgangsvertrag angegebene SOAP-Fehler werden als <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> zu Clientanwendungen heraufgestuft, wobei der Typparameter der Detailtyp des SOAP-Fehlers ist. [!INCLUDE[crabout](../../../includes/crabout-md.md)]Behandlung von fehlerbedingungen in einer Clientanwendung, finden Sie unter [senden und Empfangen von Fehlern](../../../docs/framework/wcf/sending-and-receiving-faults.md). Ein vollständiges Beispiel für das Behandeln von Fehlern in einem Client, finden Sie unter [Ausnahmen erwartet](../../../docs/framework/wcf/samples/expected-exceptions.md).  
  
## <a name="configuring-and-securing-clients"></a>Konfigurieren und Sichern von Clients  
 Das Konfigurieren eines Clients beginnt mit dem erforderlichen Laden von Zielendpunktinformationen für das Client- oder Kanalobjekt (in der Regel von einer Konfigurationsdatei), obwohl diese Informationen auch programmgesteuert mithilfe der Clientkonstruktoren und -eigenschaften geladen werden können. Allerdings sind zusätzliche Konfigurationsschritte erforderlich, um ein bestimmtes Clientverhalten zu ermöglichen und zahlreichen Sicherheitsszenarien gerecht zu werden.  
  
 Beispielsweise werden Sicherheitsanforderungen für Dienstverträge in der Dienstvertragschnittstelle deklariert, und falls mit Svcutil.exe eine Konfigurationsdatei erstellt wurde, beinhaltet diese Datei normalerweise eine Bindung, die den Sicherheitsanforderungen des Diensts entspricht. In einigen Fällen sind jedoch möglicherweise zusätzliche Sicherheitskonfigurationen erforderlich, zum Beispiel die Konfiguration von Clientanmeldeinformationen. Vollständige Informationen zur Konfiguration der Sicherheit für [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Clients finden Sie [Sichern von Clients](../../../docs/framework/wcf/securing-clients.md).  
  
 Zudem können einige benutzerdefinierte Änderungen in Clientanwendungen aktiviert werden, zum Beispiel benutzerdefiniertes Laufzeitverhalten. [!INCLUDE[crabout](../../../includes/crabout-md.md)]zum Konfigurieren eines benutzerdefinierten Clientverhaltens finden Sie unter [Konfigurieren von Clientverhalten](../../../docs/framework/wcf/configuring-client-behaviors.md).  
  
## <a name="creating-callback-objects-for-duplex-services"></a>Erstellen von Rückrufobjekten für Duplexdienste  
 Mit Duplexdiensten wird ein Rückrufvertrag angegeben, den die Clientanwendung implementieren muss, um gemäß den Vertragsanforderungen ein Rückrufobjekt für den aufzurufenden Dienst bereitzustellen. Obgleich es sich bei Rückrufobjekten nicht um vollständige Dienste handelt (beispielsweise kann ein Kanal nicht mit einem Rückrufobjekt initiiert werden), können Sie zu Implementierungs- und Konfigurationszwecken als eine Art Dienst betrachtet werden.  
  
 Clients von Duplexdiensten müssen folgende Vorgänge ausführen:  
  
-   Eine Rückrufvertragsklasse implementieren.  
  
-   Eine Instanz der Implementierungsklasse des Rückrufvertrags erstellen und diese zum Erstellen des <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>-Objekts verwenden, das an den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientkonstruktor übergeben wird.  
  
-   Vorgänge aufrufen und Vorgangsrückrufe behandeln.  
  
 Duplex-[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientobjekte funktionieren wie ihre Gegenstücke ohne Duplex, mit der Einschränkung, dass sie zur Unterstützung von Rückrufen erforderliche Funktionen verfügbar machen (einschließlich der Konfiguration des Rückrufdiensts).  
  
 Beispielsweise können verschiedene Aspekte des Laufzeitverhaltens des Rückrufobjekts mithilfe der Eigenschaften des <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>-Attributs in der Rückrufklasse gesteuert werden. Ein weiteres Beispiel ist die Verwendung der <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType>-Klasse, um die Rückgabe von Ausnahmeinformationen an Dienste, die das Rückrufobjekt aufrufen, zu ermöglichen. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Duplexdienste](../../../docs/framework/wcf/feature-details/duplex-services.md). Ein vollständiges Beispiel finden Sie unter [Duplex](../../../docs/framework/wcf/samples/duplex.md).  
  
 Auf Windows XP-Computern, auf denen Internetinformationsdienste (IIS) 5.1 ausgeführt wird, muss von Duplexclients eine Clientbasisadresse mithilfe der <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>-Klasse angegeben werden, da andernfalls eine Ausnahme ausgelöst wird. Im folgenden Codebeispiel wird die entsprechende Umsetzung in Code veranschaulicht.  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 Im folgenden Codebeispiel wird die entsprechende Umsetzung in einer Konfigurationsdatei veranschaulicht.  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a>Asynchrones Aufrufen von Diensten  
 Die Art und Weise eines Vorgangsaufrufs ist ausschließlich Angelegenheit des Cliententwicklers. Dies liegt daran, dass die Nachrichten, aus denen sich ein Vorgang zusammensetzt, bei der Darstellung in verwaltetem Code entweder synchronen oder asynchronen Methoden zugeordnet werden können. Wenn Sie einen Client erstellen möchten, mit dem Vorgänge asynchron aufgerufen werden, können Sie daher mit Svcutil.exe und der Option `/async` asynchronen Clientcode generieren. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Wie: Asynchrones Aufrufen von Dienstvorgängen](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).  
  
## <a name="calling-services-using-wcf-client-channels"></a>Aufrufen von Diensten mithilfe der WCF-Clientkanäle.  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clienttypen erweitern <xref:System.ServiceModel.ClientBase%601>, die wiederum von der <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>-Schnittstelle abgeleitet wird, um das zugrunde liegende Kanalsystem verfügbar zu machen. Sie können Dienste aufrufen, indem Sie den Zieldienstvertrag mit der <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>-Klasse verwenden. Weitere Informationen finden Sie unter [WCF-Clientarchitektur](../../../docs/framework/wcf/feature-details/client-architecture.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>  
 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
