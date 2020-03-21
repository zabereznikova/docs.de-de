---
title: Batchverarbeitung von Nachrichten in einer Transaktion
ms.date: 03/30/2017
helpviewer_keywords:
- batching messages [WCF]
ms.assetid: 53305392-e82e-4e89-aedc-3efb6ebcd28c
ms.openlocfilehash: be9661525c960ae558d21b05781007b81b8a3f56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185442"
---
# <a name="batching-messages-in-a-transaction"></a>Batchverarbeitung von Nachrichten in einer Transaktion
Anwendungen, die mit Warteschlangen arbeiten, verwenden Transaktionen, um eine richtige und zuverlässige Zustellung der Nachrichten zu gewährleisten. Transaktionen sind jedoch teuer und können den Nachrichtendurchsatz stark senken. Eine Möglichkeit, den Nachrichtendurchsatz zu verbessern, ist, dass mehrere Nachrichten in einer Transaktion von einer Anwendung gelesen und verarbeitet werden. Dabei muss zwischen Leistung und Wiederherstellungsaufwand abgewogen werden: Je mehr Nachrichten sich in einem Batch befinden, desto umfangreicher ist die Wiederherstellungsarbeit, die anfällt, falls Transaktionen zurückgesetzt werden. Beachten Sie dabei den Unterschied zwischen der Batchverarbeitung von Nachrichten in einer Transaktion und in Sitzungen. Eine *Sitzung* ist eine Gruppierung verwandter Nachrichten, die von einer einzelnen Anwendung verarbeitet und als eine Einheit festgeschrieben werden. Sitzungen werden in der Regel verwendet, wenn eine Gruppe verwandter Nachrichten gemeinsam verarbeitet werden muss. Ein Beispiel hierfür ist eine Website für Online-Shopping. *Batches* werden verwendet, um mehrere, nicht verknüpfte Nachrichten so zu verarbeiten, dass der Nachrichtendurchsatz erhöht wird. Weitere Informationen zu Sitzungen finden Sie unter [Gruppieren von Warteschlangennachrichten in einer Sitzung](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md). Nachrichten in einem Batch werden auch nur von einer Anwendung verarbeitet und als Einheit festgeschrieben (COMMIT), die Nachrichten im Batch stehen jedoch ggf. in keinem Zusammenhang zueinander. Die Batchverarbeitung von Nachrichten in einer Transaktion ist eine Optimierung, die sich nicht auf die Ausführung der Anwendung auswirkt.  
  
## <a name="entering-batching-mode"></a>Aktivieren des Batchmodus  
 Die Batchverarbeitung wird durch das <xref:System.ServiceModel.Description.TransactedBatchingBehavior>-Endpunktverhalten gesteuert. Das Hinzufügen dieses Endpunktverhaltens zu einem Dienstendpunkt weist Windows Communication Foundation (WCF) an Batchnachrichten in einer Transaktion. Nicht alle Nachrichten erfordern eine Transaktion, daher werden nur Nachrichten, die eine Transaktion `TransactionScopeRequired`  =  `true` erfordern, in einem Batch platziert, und nur Nachrichten, die von Vorgängen gesendet werden, die mit einem Batch markiert sind und `TransactionAutoComplete`  =  `true` für diesen berücksichtigt werden. Wenn alle Vorgänge im Servicevertrag `TransactionScopeRequired`  =  `false` `TransactionAutoComplete`  =  `false`mit und gekennzeichnet sind, wird der Stapelverarbeitungsmodus nie eingegeben.  
  
## <a name="committing-a-transaction"></a>Commitausführung für eine Transaktion  
 Bei Batchtransaktionen werden Commits auf Grundlage der folgenden Punkte durchgeführt:  
  
- `MaxBatchSize`. Eine Eigenschaft des <xref:System.ServiceModel.Description.TransactedBatchingBehavior>-Verhaltens. Durch diese Eigenschaft wird die maximale Anzahl von Nachrichten in einen Batch bestimmt. Sobald diese Anzahl erreicht ist, wird ein Commit für den Batch durchgeführt. Es handelt sich bei diesem Wert allerdings um einen flexiblen Grenzwert, das heißt, dass für einen Batch auch schon vor Erreichen dieser Anzahl von Nachrichten ein Commit durchgeführt werden kann.  
  
- `Transaction Timeout`. Sobald 80 Prozent des Transaktionstimeouts verstrichen sind, wird ein Commit für den Batch durchgeführt und ein neuer Batch erstellt. Das heißt, dass der Commit für den Batch durchgeführt wird, sobald nur noch maximal 20 Prozent der für die Transaktion erlaubten Zeit übrig sind.  
  
- `TransactionScopeRequired`. Wenn WCF beim Verarbeiten eines Nachrichtenstapels `TransactionScopeRequired`  =  `false`eine mit einem feststellt, wird der Batch festgemacht `TransactionScopeRequired`  =  `true` `TransactionAutoComplete`  = und beim Empfang der ersten Nachricht mit und `true`erneut ein neuer Batch geöffnet.  
  
- Falls die Warteschlange keine weiteren Nachrichten mehr enthält, wird ein Commit für den aktuellen Batch durchgeführt, selbst wenn `MaxBatchSize` noch nicht erreicht wurde bzw. noch keine 80 Prozent des Transaktionstimeouts verstrichen sind.  
  
## <a name="leaving-batching-mode"></a>Deaktivieren des Batchmodus  
 Falls die Transaktion durch eine Nachricht in einem Batch abgebrochen wird, werden die folgenden Schritte durchlaufen:  
  
1. Der gesamte Nachrichtenbatch wird zurückgesetzt.  
  
2. Die Nachrichten werden solange einzeln nacheinander gelesen, bis die Anzahl der gelesenen Nachrichten die doppelte maximale Batchgröße überschritten hat.  
  
3. Der Batchmodus wird wieder aufgenommen.  
  
## <a name="choosing-the-batch-size"></a>Auswählen der Batchgröße  
 Die Größe eines Batches ist abhängig von der Anwendung. Mit einem empirischen Vorgehen lässt sich die optimale Batchgröße für die Anwendung am besten bestimmen. Wählen Sie die Batchgröße immer entsprechend dem tatsächlichen Bereitstellungsmodell Ihrer Anwendung. Wenn beispielsweise bei der Bereitstellung der Anwendung ein SQL-Server auf einem Remotecomputer und eine Transaktion als Brücke zwischen Warteschlange und SQL-Server erforderlich sind, lässt sich die Batchgröße am besten durch Ausführen genau dieser Konfiguration ermitteln.  
  
## <a name="concurrency-and-batching"></a>Parallelität und Batchverarbeitung  
 Um den Durchsatz zu erhöhen, können auch viele Batches gleichzeitig ausgeführt werden. Die parallele Batchverarbeitung wird aktiviert, indem Sie `ConcurrencyMode.Multiple` auf `ServiceBehaviorAttribute` setzen.  
  
 *Die Diensteinschränkung* ist ein Dienstverhalten, das verwendet wird, um anzugeben, wie viele maximale gleichzeitige Aufrufe für den Dienst durchgeführt werden können. Im Zusammenhang mit der Batchverarbeitung legt dieses Verhalten fest, wie viele Batches gleichzeitig ausgeführt werden dürfen. Wenn die Diensteinschränkung nicht festgelegt ist, verwendet WCF standardmäßig die maximalen gleichzeitigen Aufrufe auf 16. Wird zudem standardmäßig noch das Batchverarbeitungsverhalten hinzugefügt, bedeutet dies, dass maximal 16 Batches gleichzeitig aktiv sein können. Optimieren Sie die Diensteinschränkung und die Batchverarbeitung möglichst auf Grundlage Ihrer Kapazitäten. Wenn die Warteschlange beispielsweise 100 Nachrichten enthält und ein Batch 20 Nachrichten umfassen soll, ist es nicht sinnvoll, maximal 16 parallele Aufrufe festzulegen, da in diesem Fall je nach Durchsatz 16 Transaktion aktiv sein können, was einer Deaktivierung der Batchverarbeitung gleichkommen würde. Um eine optimale Leistung zu erzielen, müssen Sie daher entweder die parallele Batchverarbeitung deaktivieren oder bei aktivierter paralleler Verarbeitung die richtige Größe für die Diensteinschränkung auswählen.  
  
## <a name="batching-and-multiple-endpoints"></a>Batchverarbeitung und mehrere Endpunkte  
 Ein Endpunkt besteht aus einer Adresse und einem Vertrag. Mehrere Endpunkte können die gleiche Bindung verwenden. Zwei Endpunkte können die gleiche Bindung und den gleichen Abhör-URI (Uniform Resource Identifier) bzw. die gleiche Warteschlangenadresse verwenden. Falls zwei Endpunkte aus derselben Warteschlange lesen und für beide Endpunkte wird transaktives Batchverarbeitungsverhalten hinzugefügt, kann es zu einem Konflikt zwischen den angegebenen Batchgrößen kommen. Dieser Konflikt lässt sich lösen, indem die Batchverarbeitung mit der kleinsten zwischen den beiden transaktiven Batchverarbeitungsverhalten angegebenen Batchgröße implementiert wird. In diesem Szenario wird an keinem Endpunkt eine Batchverarbeitung durchgeführt, wenn für einen Endpunkt keine transaktive Batchverarbeitung angegeben wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie `TransactedBatchingBehavior` in einer Konfigurationsdatei angeben können.  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="TransactedBatchingBehavior"
              maxBatchSize="100" />
  </endpointBehaviors>
</behaviors>
```  
  
 Im folgenden Beispiel wird gezeigt, wie Sie <xref:System.ServiceModel.Description.TransactedBatchingBehavior> im Code angeben können.  
  
```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))
{
     ServiceEndpoint sep = ServiceHost.AddServiceEndpoint(typeof(IOrderProcessor), new NetMsmqBinding(), "net.msmq://localhost/private/ServiceModelSamplesTransacted");
     sep.Behaviors.Add(new TransactedBatchingBehavior(100));

     // Open the ServiceHost to create listeners and start listening for messages.
    serviceHost.Open();
  
    // The service can now be accessed.
    Console.WriteLine("The service is ready.");
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.WriteLine();
    Console.ReadLine();
  
    // Close the ServiceHostB to shut down the service.
    serviceHost.Close();
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Warteschlangenübersicht](../../../../docs/framework/wcf/feature-details/queues-overview.md)
- [Warteschlangen in WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)
