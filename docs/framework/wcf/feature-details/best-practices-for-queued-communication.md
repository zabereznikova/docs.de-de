---
title: Bewährte Methoden für die Kommunikation unter Verwendung von Warteschlangen
ms.date: 03/30/2017
helpviewer_keywords:
- queues [WCF], best practices
- best practices [WCF], queued communication
ms.assetid: 446a6383-cae3-4338-b193-a33c14a49948
ms.openlocfilehash: af9ed7d64a60042297e071262be7610c4d791a51
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601347"
---
# <a name="best-practices-for-queued-communication"></a>Bewährte Methoden für die Kommunikation unter Verwendung von Warteschlangen
Dieses Thema enthält empfohlene Vorgehensweisen für die Kommunikation in der Warteschlange in Windows Communication Foundation (WCF). In den folgenden Abschnitten werden bewährte Methoden aus der Perspektive eines Szenarios vorgestellt.  
  
## <a name="fast-best-effort-queued-messaging"></a>Schnelles Warteschlangen-Messaging nach dem Best-Effort-Prinzip  
 Falls Sie die Vorzüge der Nachrichtentrennung beim Warteschlangen-Messaging nutzen möchten und auf einen schnellen, leistungsfähigen Nachrichtenaustausch mit einer Best-Effort-Zusicherung angewiesen sind, verwenden Sie eine Warteschlange, bei der es sich nicht um eine Transaktionswarteschlange handelt, und legen Sie die <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>-Eigenschaft auf `false` fest.  
  
 Darüber hinaus können Sie die <xref:System.ServiceModel.MsmqBindingBase.Durable%2A>-Eigenschaft auf `false` festlegen, um die Kosten, die beim Schreiben auf einen Datenträger entstehen, zu umgehen.  
  
 Die Sicherheit wirkt sich auf die Leistung aus. Weitere Informationen finden Sie unter [Überlegungen zur Leistung](performance-considerations.md).  
  
## <a name="reliable-end-to-end-queued-messaging"></a>Zuverlässiges End-to-End-Warteschlangen-Messaging  
 In den folgenden Abschnitten werden bewährte Methoden für Szenarien beschrieben, in denen ein zuverlässiges End-to-End-Messaging erforderlich ist.  
  
### <a name="basic-reliable-transfer"></a>Grundlegende zuverlässige Übertragung  
 Um eine zuverlässige End-to-End-Übertragung zu gewährleisten, legen Sie die <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>-Eigenschaft auf den Wert `true` fest Die <xref:System.ServiceModel.MsmqBindingBase.Durable%2A>-Eigenschaft kann je nach Anforderungen auf `true` oder `false` festgelegt werden. (Die Standardeinstellung ist `true`.) Im Allgemeinen wird für die <xref:System.ServiceModel.MsmqBindingBase.Durable%2A>-Eigenschaft der Wert `true` gewählt, wenn eine zuverlässige End-to-End-Übertragung gewünscht wird. Dies geht zwar auf Kosten der Leistung, Meldungen gehen bei dieser Einstellung jedoch nicht verloren, falls ein Warteschlangen-Manager einmal abstürzen sollte.  
  
### <a name="use-of-transactions"></a>Verwendung von Transaktionen  
 Sie müssen Transaktionen verwenden, um eine zuverlässige End-to-End-Übertragung zu gewährleisten. `ExactlyOnce`-Zusicherungen gewährleisten nur, dass Nachrichten an die Zielwarteschlange gesendet werden. Um sicherzustellen, dass die Nachricht auch empfangen wird, verwenden Sie Transaktionen. Ohne Transaktionen geht bei einem Absturz des Diensts die gerade zugestellte Nachricht verloren, wobei sie jedoch an die Anwendung gesendet wird.  
  
### <a name="use-of-dead-letter-queues"></a>Verwendung von Warteschlangen für unzustellbare Nachrichten  
 Bei Verwendung von Warteschlangen für unzustellbare Nachrichten werden Sie benachrichtigt, falls eine Nachricht nicht in die Zielwarteschlange gestellt werden kann. Sie können die vom System bereitgestellte oder Ihre eigene Warteschlange für unzustellbare Nachrichten verwenden. Im Allgemeinen empfiehlt sich die Verwendung Ihrer eigenen Warteschlange für unzustellbare Nachrichten, da Sie die nicht zustellbaren Nachrichten einer Anwendung dann an eine bestimmte Warteschlange für unzustellbare Nachrichten senden können. Andernfalls werden alle nicht zustellbaren Nachrichten aller Anwendungen auf dem System in eine einzige Warteschlange gestellt. In diesem Fall muss dann jede Anwendung in der Warteschlange für unzustellbare Nachrichten nach den für sie relevanten unzustellbaren Nachrichten suchen. Gelegentlich können keine benutzerdefinierten Warteschlangen für unzustellbare Nachrichten verwendet werden, zum Beispiel bei MSMQ&#160;3.0.  
  
 Es wird davon abgeraten, Warteschlangen für unzustellbare Nachrichten für eine zuverlässige End-to-End-Kommunikation zu deaktivieren.  
  
 Weitere Informationen finden [Sie unter Verwenden von Warteschlangen für unzustellbare Nachrichten zur Behandlung von Nachrichten Übertragungsfehlern](using-dead-letter-queues-to-handle-message-transfer-failures.md).  
  
### <a name="use-of-poison-message-handling"></a>Handhabung beschädigter (nicht verarbeitbarer) Nachrichten  
 Die Handhabung beschädigter Nachrichten gibt Ihnen die Möglichkeit zur Wiederherstellung nach Fehlern bei der Nachrichtenverarbeitung.  
  
 Wenn Sie die Funktion für die Handhabung beschädigter Nachrichten verwenden, muss die <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A>-Eigenschaft auf den richtigen Wert festgelegt werden. Bei <xref:System.ServiceModel.ReceiveErrorHandling.Drop> gehen die Daten verloren. Andererseits wird bei der Einstellung <xref:System.ServiceModel.ReceiveErrorHandling.Fault> auf dem Diensthost ein Fehler ausgegeben, wenn dieser auf eine beschädigte (nicht verarbeitbare) Nachricht stößt. Bei MSMQ&#160;3.0 ist die Einstellung <xref:System.ServiceModel.ReceiveErrorHandling.Fault> die beste Option, um Datenverluste zu vermeiden und die beschädigte Nachricht zu eliminieren. Bei Verwendung von MSMQ 4.0 ist <xref:System.ServiceModel.ReceiveErrorHandling.Move> die empfohlene Vorgehensweise. Durch <xref:System.ServiceModel.ReceiveErrorHandling.Move> wird die kritische Nachricht aus der Warteschlange verschoben, sodass neue Nachrichten verarbeitet werden können. Die beschädigte Nachricht kann dann separat vom Dienst für beschädigte Nachrichten verarbeitet werden.  
  
 Weitere Informationen finden Sie unter [Behandlung](poison-message-handling.md)von nicht verarbeitbaren Nachrichten.  
  
## <a name="achieving-high-throughput"></a>Hoher Durchsatz  
 Verwenden Sie Folgendes, um bei einem einzelnen Endpunkt einen hohen Durchsatz zu erreichen:  
  
- Transaktive Batchverarbeitung: Bei der transaktiven Batchverarbeitung ist sichergestellt, dass viele Nachrichten in einer einzelnen Transaktion gelesen werden können. Hierdurch werden die Commits für Transaktionen optimiert und die Gesamtleistung verbessert. Nachteil der Batchverarbeitung: Tritt bei einer Nachricht im Batch ein Fehler auf, wird der gesamte Batch zurückgesetzt, und die Nachrichten müssen so lange einzeln verarbeitet werden, bis die Batchverarbeitung wieder sicher aufgenommen werden kann. Da beschädigte Nachrichten in der Regel nur selten auftreten, ist die Batchverarbeitung die bevorzugte Methode, die Systemleistung zu verbessern, insbesondere dann, wenn noch andere Ressourcen-Manager an der Transaktion beteiligt sind. Weitere Informationen finden Sie unter [Batch Verarbeitung von Nachrichten in einer Transaktion](batching-messages-in-a-transaction.md).  
  
- Parallelität: Parallelität erhöht den Durchsatz, verschärft jedoch auch den Wettstreit um freigegebene Ressourcen. Weitere Informationen finden Sie unter [Parallelität.](../samples/concurrency.md)  
  
- Einschränkung: Schränken Sie die Anzahl der Nachrichten in der Verteilerpipeline ein, um eine optimale Leistung zu erzielen. Ein Beispiel hierfür finden Sie unter [Drosselung](../samples/throttling.md).  
  
 Beachten Sie bei der Batchverarbeitung, dass Parallelität und Einschränkung zu simultanen Batches führen.  
  
 Um einen höheren Durchsatz und Verfügbarkeit zu erreichen, verwenden Sie eine Farm von WCF-Diensten, die aus der Warteschlange lesen. Hierfür müssen diese Dienste denselben Vertrag auf demselben Endpunkt verfügbar machen. Eine Dienstefarm ist am besten bei Anwendungen geeignet, die sehr viele Nachrichten produzieren, da dann mehrere Dienste aus derselben Warteschlange lesen können.  
  
 Beachten Sie bei der Verwendung von Farmen, dass MSMQ&#160;3.0 keine remote durchgeführten Lesevorgänge unterstützt. MSMQ&#160;4.0 dagegen unterstützt remote durchgeführte Lesevorgänge.  
  
 Weitere Informationen finden Sie unter [Batch Verarbeitung von Nachrichten in einer Transaktion](batching-messages-in-a-transaction.md) und [Unterschiede in den Warteschlangen Funktionen in Windows Vista, Windows Server 2003 und Windows XP](diff-in-queue-in-vista-server-2003-windows-xp.md).  
  
## <a name="queuing-with-unit-of-work-semantics"></a>Warteschlangen und Arbeitseinheitssemantik  
 Gelegentlich können die Nachrichten in einer Gruppe von Nachrichten in der Warteschlange miteinander verwandt sein, das heißt, dass die Reihenfolge dieser Nachrichten von Bedeutung ist. In diesen Szenarien sollte die Gruppe der verwandten Nachrichten als Einheit verarbeitet werden, das heißt, es werden entweder alle oder keine Nachrichten verarbeitet. Verwenden Sie zur Implementierung dieses Verhaltens Sitzungen mit Warteschlangen.  
  
 Weitere Informationen finden Sie unter [Gruppieren von Nachrichten in der Warteschlange in einer Sitzung](grouping-queued-messages-in-a-session.md).  
  
## <a name="correlating-request-reply-messages"></a>Korrelieren von Anforderung-Antwort-Nachrichten  
 Warteschlangen sind zwar im Allgemeinen unidirektional, es kann jedoch vorkommen, dass Sie eine empfangene Antwort zu einer zuvor gesendeten Anforderung in Bezug setzen möchten. Falls eine solche Zuordnung erforderlich ist, sollten Sie, wenn möglich, mit der Nachricht Ihren eigenen SOAP-Nachrichtenheader mit Zuordnungsinformationen verwenden. In der Regel wird dieser Header vom Sender an die Nachricht angehängt. Beim Empfänger wird der Nachrichtenheader mit den Zuordnungsinformationen dann während der Verarbeitung der Nachricht an die Antwortnachricht, die als neue Nachricht an eine Antwortwarteschlange gesendet wird, angehängt, sodass die Antwortnachricht beim Sender der Anforderungsnachricht zugeordnet werden kann.  
  
## <a name="integrating-with-non-wcf-applications"></a>Integrieren von Nicht-WCF-Anwendungen  
 Verwenden Sie, `MsmqIntegrationBinding` Wenn Sie WCF-Dienste oder-Clients mit nicht-WCF-Diensten oder-Clients integrieren. Bei der nicht-WCF-Anwendung kann es sich um eine mit System. Messaging, com+, Visual Basic oder C++ geschriebene MSMQ-Anwendung handeln.  
  
 Beachten Sie bei der Verwendung von `MsmqIntegrationBinding` folgende Punkte:  
  
- Ein WCF-Nachrichtentext ist nicht mit dem Text der MSMQ-Nachricht identisch. Beim Senden einer WCF-Nachricht mit einer Bindung in der Warteschlange wird der WCF-Nachrichtentext in einer MSMQ-Nachricht abgelegt. In der MSMQ-Infrastruktur wird diese Zusatzinformation jedoch nicht wahrgenommen, MSMQ sieht lediglich die MSMQ-Nachricht.  
  
- `MsmqIntegrationBinding` unterstützt die gängigen Serialisierungstypen. Je nach Serialisierungstyp nimmt der Texttyp der generischen Nachricht - <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601> - unterschiedliche Typparameter an. So ist bei <xref:System.ServiceModel.MsmqIntegration.MsmqMessageSerializationFormat.ByteArray> zum Beispiel `MsmqMessage\<byte[]>`<xref:System.ServiceModel.MsmqIntegration.MsmqMessageSerializationFormat.Stream> und bei `MsmqMessage<Stream>` der Parameter erforderlich.  
  
- Mit der XML-Serialisierung können Sie den bekannten Typ mithilfe des- `KnownTypes` Attributs für das-Element angeben, [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) das dann verwendet wird, um zu bestimmen, wie die XML-Nachricht deserialisiert werden soll.  
  
## <a name="see-also"></a>Weitere Informationen

- [Warteschlangen in WCF](queuing-in-wcf.md)
- [Vorgehensweise: Austauschen von Nachrichten in einer Warteschlange mit WCF-Endpunkten](how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen](how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- [Gruppieren von Nachrichten in der Warteschlange einer Sitzung](grouping-queued-messages-in-a-session.md)
- [Batchverarbeitung von Nachrichten in einer Transaktion](batching-messages-in-a-transaction.md)
- [Verwenden von Warteschlangen für unzustellbare Nachrichten zur Handhabung von Nachrichtenübertragungsfehlern](using-dead-letter-queues-to-handle-message-transfer-failures.md)
- [Behandlung nicht verarbeitbarer Nachrichten](poison-message-handling.md)
- [Unterschiede zwischen den Warteschlangenfunktionen in Windows Vista, Windows Server 2003 und Windows XP](diff-in-queue-in-vista-server-2003-windows-xp.md)
- [Sichern von Nachrichten mit Transportsicherheit](securing-messages-using-transport-security.md)
- [Sichern von Nachrichten mithilfe der Nachrichtensicherheit](securing-messages-using-message-security.md)
- [Problembehandlung bei Nachrichtenwarteschlangen](troubleshooting-queued-messaging.md)
