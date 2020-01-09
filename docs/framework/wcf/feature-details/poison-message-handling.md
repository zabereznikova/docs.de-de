---
title: Behandlung nicht verarbeitbarer Nachrichten
ms.date: 03/30/2017
ms.assetid: 8d1c5e5a-7928-4a80-95ed-d8da211b8595
ms.openlocfilehash: ff1eaec99308b06250722b290b7005ac21731570
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337647"
---
# <a name="poison-message-handling"></a>Behandlung nicht verarbeitbarer Nachrichten
Eine nicht verarbeitbare *Nachricht* ist eine Nachricht, die die maximale Anzahl von Übermittlungs versuchen an die Anwendung überschritten hat. Diese Situation kann auftreten, wenn eine warteschlangenbasierte Anwendung aufgrund der Fehler keine Nachricht verarbeiten kann. Um Zuverlässigkeitsforderungen zu erfüllen, empfängt eine in der Warteschlange stehende Anwendung Nachrichten unter einer Transaktion. Beim Abbrechen der Transaktion, in der eine in der Warteschlange stehende Nachricht empfangen wurde, bleibt die Nachricht in der Warteschlange und wird dann unter einer neuen Transaktion wiederholt. Wenn das Problem, das zum Abbrechen der Transaktion geführt hat, nicht korrigiert wird, kann die empfangende Anwendung in einer Schleife hängen bleiben, in der sie dieselbe Nachricht immer wieder empfängt und abbricht, bis die maximale Anzahl der Zustellversuche überschritten ist. Auf diese Weise entsteht eine nicht verarbeitbare Nachricht.  
  
 Eine Nachricht kann aus vielen Gründen zu einer nicht verarbeitbaren Nachrichten werden. Die häufigsten Ursachen sind anwendungsspezifisch. Wenn beispielsweise eine Anwendung eine Nachricht aus einer Warteschlange liest und dann Datenbankprozesse durchführt, kann es vorkommen, dass von der Anwendung keine Sperre für die Datenbank bewirkt werden kann. Dies führt dann dazu, dass sie die Transaktion abbricht. Da die Datenbanktransaktion abgebrochen wurde, verbleibt die Nachricht in der Warteschlange, wodurch die Nachricht von der Anwendung ein zweites Mal gelesen und ein neuer Versuch gestartet wird, eine Sperrung der Datenbank zu bewirken. Nachrichten können auch nicht verarbeitbar werden, wenn sie ungültige Informationen enthalten. So enthält z. B. eine Bestellung möglicherweise eine ungültige Kundennummer. In diesen Fällen kann die Anwendung die Transaktion freiwillig abbrechen und die Nachricht zwingen, eine nicht verarbeitbare Nachricht zu werden.  
  
 Bei seltenen Gelegenheiten können Nachrichten nicht zur Anwendung weitergeleitet werden. Die Windows Communication Foundation (WCF)-Ebene kann ein Problem mit der Nachricht feststellen, z. b. wenn die Nachricht den falschen Rahmen hat, ungültige Meldungs Anmelde Informationen angefügt sind, oder einen ungültigen Aktions Header. In diesen Fällen empfängt die Anwendung die Nachricht niemals; trotzdem kann die Nachricht noch zu einer nicht verarbeitbaren Nachricht werden, die manuell verarbeitet werden kann.  
  
## <a name="handling-poison-messages"></a>Behandeln von nicht verarbeitbaren Nachrichten  
 In WCF bietet die Behandlung von nicht verarbeitbaren Nachrichten einen Mechanismus, mit dem eine empfangende Anwendung Nachrichten verarbeiten kann, die nicht an die Anwendung weitergeleitet werden können, oder Nachrichten, die an die Anwendung gesendet werden, die jedoch aufgrund anwendungsspezifischer rechtlichen. Die Konfiguration der Behandlung nicht verarbeitbarer Nachrichten erfolgt in jeder der verfügbaren, in der Warteschlange stehenden Bindungen durch die folgenden Eigenschaften:  
  
- `ReceiveRetryCount`. Ein Ganzzahlwert, die die maximale Anzahl der Neuversuche für den Versand einer Nachricht von der Anwendungswarteschlange zu der Anwendung angibt. Der Standardwert ist 5. Dieser Wert ist in Fällen ausreichend, in denen eine sofortige Wiederholung das Problem behebt, beispielsweise wenn ein temporärer Deadlock für eine Datenbank vorliegt.  
  
- `MaxRetryCycles`. Ein Ganzzahlwert, der die maximale Anzahl der Wiederholungszyklen angibt. Ein Wiederholungszyklus umfasst die Übertragung einer Nachricht von der Anwendungswarteschlange zur untergeordneten Wiederholungswarteschlange und – nach einer konfigurierbaren Verzögerung – die Rückübertragung der Nachricht aus der untergeordneten Wiederholungswarteschlange zur Anwendungswarteschlange, um einen erneuten Zustellversuch zu unternehmen. Der Standardwert ist 2. Unter Windows Vista wird die Nachricht maximal (`ReceiveRetryCount` + 1) * (`MaxRetryCycles` + 1) mal ausprobiert. `MaxRetryCycles` wird unter Windows Server 2003 und [!INCLUDE[wxp](../../../../includes/wxp-md.md)]ignoriert.  
  
- `RetryCycleDelay`. Die Verzögerungszeit für Wiederholungszyklen. Der Standardwert beträgt 30 Minuten. `MaxRetryCycles` und `RetryCycleDelay` bieten gemeinsam einen Mechanismus zur Behandlung des Problems, wenn eine Wiederholung nach einer periodischen Verzögerung das Problem behebt. Damit wird z. B. ein gesperrtes Rowset bei einem in SQL Server anstehenden Transaktionscommit behandelt.  
  
- `ReceiveErrorHandling`. Eine Enumeration, die angibt, welche Aktion für eine Nachricht erfolgen soll, deren Zustellung auch nach der maximalen Anzahl von Wiederholungen fehlgeschlagen ist. Die Werte können „Fehler“, „Ablegen“, „Ablehnen“ und „Verschieben“ sein. Die Standardoption ist "Fehler".  
  
- Fehler. Diese Option sendet einen Fehler an den Listener, der bewirkt hat, dass der `ServiceHost` fehlerhaft agiert. Die Nachricht muss durch einen externen Mechanismus aus der Anwendungswarteschlange entfernt werden, bevor die Anwendung mit der Verarbeitung von Nachrichten aus der Warteschlange fortfahren kann.  
  
- Drop. Diese Option legt die nicht verarbeitbare Nachricht ab, und die Nachricht wird der Anwendung nie zugestellt. Wenn die Eigenschaft `TimeToLive` der Nachricht zu diesem Zeitpunkt bereits abgelaufen ist, kann die Nachricht in der Warteschlange für unzustellbare Nachrichten des Absenders angezeigt werden. Andernfalls wird die Nachricht nirgendwo angezeigt. Diese Option gibt an, dass vom Benutzer keine Aktion für den Fall angegeben wurde, dass die Nachricht verloren geht.  
  
- Ablehnen. Diese Option ist nur unter Windows Vista verfügbar. Damit wird das Message Queuing (MSMQ) angewiesen, eine negative Bestätigung mit dem Hinweis, dass die Anwendung die Nachricht nicht empfangen kann, an den sendenden Warteschlangen-Manager zu senden. Die Nachricht wird in die Warteschlange für unzustellbare Nachrichten des sendenden Warteschlangen-Managers eingefügt.  
  
- Verschieben. Diese Option ist nur unter Windows Vista verfügbar. Damit wird die nicht verarbeitbare Nachricht in eine Warteschlange für potenziell schädliche Nachrichten verschoben, sodass sie später durch eine Anwendung zur Behandlung nicht verarbeitbarer Nachrichten verarbeitet werden kann. Die Warteschlange für potenziell schädliche Nachrichten ist eine untergeordnete Warteschlange der Anwendungswarteschlange. Bei einer Anwendung mit nicht verarbeitbaren Nachrichten kann es sich um einen WCF-Dienst handeln, der Nachrichten aus der Warteschlange für Die Warteschlange für nicht verarbeitbare Nachrichten ist eine unter Warteschlange der Anwendungs Warteschlange und kann als net. MSMQ://\<*Computername*>/*applicationQueue*;p Oison adressiert werden, wobei Computer *Name* der Name des Computers ist, auf dem sich die Warteschlange befindet, und *applicationQueue* der Name der anwendungsspezifischen Warteschlange ist.  
  
 Im Folgenden ist die maximale Anzahl von für eine Nachricht durchgeführten Übermittlungsversuchen dargestellt:  
  
- ((ReceiveRetryCount + 1) * (MaxRetryCycles + 1)) unter Windows Vista.  
  
- (ReceiveRetryCount + 1) unter Windows Server 2003 und [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
> [!NOTE]
> Für eine Nachricht, die erfolgreich zugestellt wird, werden keine Wiederholungen durchgeführt.  
  
 Um zu verfolgen, wie oft versucht wird, eine Nachricht zu lesen, verwaltet Windows Vista eine permanente Nachrichten Eigenschaft, die die Anzahl der Abbrüche und eine Verschiebungs Anzahl-Eigenschaft zählt, die zählt, wie oft die Nachricht zwischen der Anwendungs Warteschlange und den unter Warteschlangen bewegt wird. Der WCF-Kanal verwendet diese, um die Anzahl der empfangenen Wiederholungs Versuche und die Anzahl der Wiederholungs Zyklen zu berechnen. Unter Windows Server 2003 und [!INCLUDE[wxp](../../../../includes/wxp-md.md)]wird die Abbruch Anzahl im Arbeitsspeicher durch den WCF-Kanal beibehalten und wird zurückgesetzt, wenn die Anwendung fehlschlägt. Außerdem kann der WCF-Kanal die Abbruchs-Zähler für bis zu 256 Nachrichten im Arbeitsspeicher jederzeit enthalten. Wenn eine 257. Nachricht gelesen wird, dann wird die Abbruchanzahl der ältesten Nachricht zurückgesetzt.  
  
 Die Abbruchanzahl- und Verschiebungsanzahleigenschaften stehen dem Dienstvorgang durch den Vorgangskontext zur Verfügung. Im folgenden Codebeispiel wird der Zugriff darauf veranschaulicht.  
  
 [!code-csharp[S_UE_MSMQ_Poison#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ue_msmq_poison/cs/service.cs#1)]  
  
 WCF stellt zwei Standard Bindungen in der Warteschlange bereit:  
  
- <xref:System.ServiceModel.NetMsmqBinding>. Eine .NET Framework Bindung, die für die Durchführung der Warteschlangen basierten Kommunikation mit anderen WCF-Endpunkten geeignet ist.  
  
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>. Eine Bindung, die zur Kommunikation mit vorhandenen Message Queuing-Anwendungen geeignet ist.  
  
> [!NOTE]
> Sie können Eigenschaften in diesen Bindungen basierend auf den Anforderungen des WCF-Dienstanbieter ändern. Der gesamte Mechanismus zur Behandlung nicht verarbeitbarer Nachrichten ist zur empfangenden Anwendung lokal. Der Prozess ist für die sendende Anwendung unsichtbar, es sei denn, die empfangende Anwendung beendet den Vorgang und sendet eine negative Bestätigung an den Absender zurück. In diesem Fall wird die Nachricht in die Warteschlange für unzustellbare Nachrichten des Absenders verschoben.  
  
## <a name="best-practice-handling-msmqpoisonmessageexception"></a>Empfohlene Vorgehensweise: Behandlung MsmqPoisonMessageException  
 Wenn der Dienst feststellt, dass eine Nachricht nicht verarbeitbar ist, löst der Warteschlangentransport eine <xref:System.ServiceModel.MsmqPoisonMessageException> aus, die die `LookupId` der nicht verarbeitbaren Nachricht enthält.  
  
 Eine empfangende Anwendung kann die <xref:System.ServiceModel.Dispatcher.IErrorHandler>-Schnittstelle implementieren, um alle Fehler zu behandeln, die die Anwendung erfordert. Weitere Informationen finden Sie unter [Erweitern der Kontrolle über Fehlerbehandlung und Bericht](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md)Erstellung.  
  
 Die Anwendung erfordert möglicherweise eine bestimmte automatische Behandlung von nicht verarbeitbaren Nachrichten, mit der die nicht verarbeitbaren Nachrichten in eine entsprechende Warteschlange verschoben werden, sodass der Dienst auf die restlichen Nachrichten in der Warteschlange zugreifen kann. Das einzige Szenario, in dem der Fehlerbehandlungsmechanismus zum Abhören auf Ausnahmen für nicht verarbeitbare Nachrichten verwendet werden kann, liegt vor, wenn die <xref:System.ServiceModel.Configuration.MsmqBindingElementBase.ReceiveErrorHandling%2A>-Einstellung auf <xref:System.ServiceModel.ReceiveErrorHandling.Fault> festgelegt ist. Das Beispiel der nicht verarbeitbaren Nachricht für Message Queuing 3.0 veranschaulicht dieses Verhalten. Im Folgenden werden die Schritte zur Behandlung nicht verarbeitbarer Nachrichten, einschließlich empfohlener Vorgehensweisen, umrissen:  
  
1. Stellen Sie sicher, dass die Einstellungen für nicht verarbeitbare Nachrichten den Anforderungen Ihrer Anwendung entsprechen. Wenn Sie mit den Einstellungen arbeiten, stellen Sie sicher, dass Sie die Unterschiede zwischen den Funktionen von Message Queuing unter Windows Vista, Windows Server 2003 und [!INCLUDE[wxp](../../../../includes/wxp-md.md)]verstehen.  
  
2. Implementieren Sie falls erforderlich den `IErrorHandler`, um Fehler mit nicht verarbeitbaren Nachrichten zu behandeln. Das das Festlegen von `ReceiveErrorHandling` auf `Fault` einen manuellen Mechanismus zum Verschieben der nicht verarbeitbaren Nachricht aus der Warteschlange oder zum Korrigieren eines Problems mit externen Abhängigkeiten erfordert, besteht die typische Nutzung darin, den `IErrorHandler` zu implementieren, wenn `ReceiveErrorHandling` auf `Fault` festgelegt ist, wie im folgenden Code gezeigt:  
  
     [!code-csharp[S_UE_MSMQ_Poison#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ue_msmq_poison/cs/poisonerrorhandler.cs#2)]  
  
3. Erstellen Sie ein `PoisonBehaviorAttribute`, das das Dienstverhalten verwenden kann. Das Verhalten installiert den `IErrorHandler` auf dem Verteiler. Siehe nachstehendes Codebeispiel.  
  
     [!code-csharp[S_UE_MSMQ_Poison#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ue_msmq_poison/cs/poisonbehaviorattribute.cs#3)]  
  
4. Stellen Sie sicher, dass der Dienst mit dem Verhaltensattribut für nicht verarbeitbare Nachrichten kommentiert wird.  

 Wenn außerdem das `ReceiveErrorHandling` auf `Fault` festgelegt ist, tritt beim `ServiceHost` ein Fehler auf, wenn dieser auf die nicht verarbeitbare Nachricht stößt. Sie können sich dem Fehlerereignis zuwenden und den Dienst herunterfahren, Korrekturmaßnahmen treffen und neu starten. Beispielsweise kann die `LookupId` in der <xref:System.ServiceModel.MsmqPoisonMessageException>, die an den `IErrorHandler` weitergegeben wurde, notiert werden. Tritt nun beim Diensthost ein Fehler auf, können Sie die `System.Messaging`-API verwenden, um die Nachricht mithilfe der `LookupId` aus der Warteschlange zu empfangen, die Nachricht aus der Warteschlange zu entfernen und die Nachricht in einem externen Speicher oder einer anderen Warteschlange zu speichern. Sie können dann den `ServiceHost` neu starten, um die normale Verarbeitung fortzusetzen. Die Behandlung nicht verarbeitbarer nach [richten in MSMQ 4,0](../../../../docs/framework/wcf/samples/poison-message-handling-in-msmq-4-0.md) veranschaulicht dieses Verhalten.  
  
## <a name="transaction-time-out-and-poison-messages"></a>Transaktionstimeout und nicht verarbeitbare Nachrichten  
 Eine Klasse von Fehlern kann zwischen dem Wartenschlangentransportkanal und dem Benutzercode auftreten. Diese Fehler können durch Zwischenschichten erkannt werden, beispielsweise die Nachrichtensicherheitsschicht oder die Dienstverteilungslogik. So stellen beispielsweise ein in der SOAP-Sicherheitsschicht erkanntes fehlendes X.509-Zertifikat und eine fehlende Aktion Fälle dar, in denen die Nachricht nicht an die Anwendung verteilt wird. In diesem Fall wird die Nachricht durch das Dienstmodell wieder abgelegt. Da die Nachricht in einer Transaktion gelesen wird und ein Ergebnis für diese Transaktion nicht geliefert werden kann, kommt es letztlich zum Timeout der Transaktion, sie wird abgebrochen, und die Nachricht wird wieder in die Warteschlange zurückgestellt. Anders ausgedrückt: für eine bestimmte Fehler Klasse wird die Transaktion nicht sofort abgebrochen, sondern bis zum Timeout der Transaktion gewartet. Mit <xref:System.ServiceModel.ServiceBehaviorAttribute>können Sie das Transaktions Timeout für einen Dienst ändern.  
  
 Um das Transaktions Timeout auf Computer Ebene zu ändern, ändern Sie die Datei Machine. config, und legen Sie das entsprechende Transaktions Timeout fest. Es ist wichtig zu beachten, dass die Transaktion, abhängig vom in der Transaktion festgelegten Timeout, letztendlich abbricht und zur Warteschlange zurückkehrt und die Abbruch Anzahl inkrementiert wird. Schließlich wird die Nachricht nicht verarbeitbar, und die richtige Disposition wird entsprechend den Benutzereinstellungen gewählt.  
  
## <a name="sessions-and-poison-messages"></a>Sitzungen und nicht verarbeitbare Nachrichten  
 Eine Sitzung durchläuft die gleichen Wiederholungsprozeduren und Prozeduren zur Behandlung nicht verarbeitbarer Nachrichten wie eine einzelne Nachricht. Die zuvor aufgeführten Eigenschaften für nicht verarbeitbare Nachrichten gelten auch für die ganze Sitzung, d. h., dass die gesamte Sitzung wiederholt wird und schließlich in einer Warteschlange für potenziell schädliche Nachrichten oder in der Absenderwarteschlange für unzustellbare Nachrichten platziert wird, wenn die Nachricht abgelehnt wird.  
  
## <a name="batching-and-poison-messages"></a>Batchverarbeitung und nicht verarbeitbare Nachrichten  
 Wenn eine Nachricht zu einer nicht verarbeitbaren Nachricht wird und Teil eines Batches ist, wird für den gesamten Batch ein Rollback durchgeführt, und der Kanal kehrt zum Lesen einzelner Nachrichten zurück. Weitere Informationen zur Batch Verarbeitung finden Sie unter [Batch Verarbeitung von Nachrichten in einer Transaktion](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md) .  
  
## <a name="poison-message-handling-for-messages-in-a-poison-queue"></a>Behandlung nicht verarbeitbarer Nachrichten für Nachrichten in einer Warteschlange für potenziell schädliche Nachrichten  
 Die Behandlung nicht verarbeitbarer Nachrichten ist nicht damit beendet, dass eine Nachricht in die Warteschlange für potenziell schädliche Nachrichten eingefügt wird. Die Nachrichten in der Warteschlange für potenziell schädliche Nachrichten müssen immer noch gelesen und behandelt werden. Beim Lesen von Nachrichten aus der endgültigen Warteschlange für potenziell schädliche Nachrichten können Sie eine Teilmenge der Einstellungen zur Behandlung nicht verarbeitbarer Nachrichten verwenden. Die anwendbaren Einstellungen sind `ReceiveRetryCount` und `ReceiveErrorHandling`. Sie können `ReceiveErrorHandling` auf "Drop", "Reject" oder "Fault" festlegen. `MaxRetryCycles` wird ignoriert, und es wird eine Ausnahme ausgelöst, wenn `ReceiveErrorHandling` auf {3&gt;Move&lt;3} festgelegt wird.  
  
## <a name="windows-vista-windows-server-2003-and-windows-xp-differences"></a>Unterschiede zwischen Windows Vista, Windows Server 2003 und Windows XP  
 Wie bereits erwähnt, gelten nicht alle Einstellungen für die Behandlung nicht verarbeitbarer Nachrichten für Windows Server 2003 und [!INCLUDE[wxp](../../../../includes/wxp-md.md)]. Die folgenden Hauptunterschiede zwischen Message Queuing unter Windows Server 2003, [!INCLUDE[wxp](../../../../includes/wxp-md.md)]und Windows Vista sind für die Behandlung nicht verarbeitbarer Nachrichten relevant:  
  
- Message Queuing in Windows Vista unterstützt untergeordnete Warteschlangen, während Windows Server 2003 und [!INCLUDE[wxp](../../../../includes/wxp-md.md)] keine untergeordneten Warteschlangen unterstützen. Untergeordnete Warteschlangen werden zur Behandlung nicht verarbeitbarer Nachrichten verwendet. Die Wiederholungswarteschlangen und die Warteschlange für potenziell schädliche Nachrichten sind untergeordnete Warteschlangen der Anwendungswarteschlange, die basierend auf den Einstellungen für die Behandlung nicht verarbeitbarer Nachrichten erstellt wird. Die Eigenschaft `MaxRetryCycles` bestimmt, wie viele untergeordnete Wiederholungwarteschlangen erstellt werden sollen. Daher werden `MaxRetryCycles` bei Ausführung unter Windows Server 2003 oder [!INCLUDE[wxp](../../../../includes/wxp-md.md)]ignoriert, und `ReceiveErrorHandling.Move` ist nicht zulässig.  
  
- Message Queuing in Windows Vista unterstützt negative Bestätigungen, während Windows Server 2003 und [!INCLUDE[wxp](../../../../includes/wxp-md.md)] nicht. Eine negative Bestätigung vom empfangenden Warteschlangen-Manager bewirkt, dass der sendende Warteschlangen-Manager die abgelehnte Nachricht in die Warteschlange für unzustellbare Nachrichten einstellt. Daher ist `ReceiveErrorHandling.Reject` bei Windows Server 2003 und [!INCLUDE[wxp](../../../../includes/wxp-md.md)]nicht zulässig.  
  
- Message Queuing in Windows Vista unterstützt eine Nachrichten Eigenschaft, die die Anzahl der Versuche der Nachrichtenübermittlung beibehält. Diese Abbruch Anzahl Eigenschaft ist auf Windows Server 2003 und [!INCLUDE[wxp](../../../../includes/wxp-md.md)]nicht verfügbar. WCF behält die Abbruch Anzahl im Arbeitsspeicher bei, sodass diese Eigenschaft möglicherweise keinen exakten Wert enthält, wenn dieselbe Nachricht von mehr als einem WCF-Dienst in einer Farm gelesen wird.  
  
## <a name="see-also"></a>Siehe auch

- [Warteschlangenübersicht](../../../../docs/framework/wcf/feature-details/queues-overview.md)
- [Unterschiede zwischen den Warteschlangenfunktionen in Windows Vista, Windows Server 2003 und Windows XP](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md)
- [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
