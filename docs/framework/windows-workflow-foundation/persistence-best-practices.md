---
title: Empfohlene Vorgehensweisen für die Persistenz
ms.date: 03/30/2017
ms.assetid: 6974c5a4-1af8-4732-ab53-7d694608a3a0
ms.openlocfilehash: 950a5d5c742b7882db93d71f3e7f205009f2a863
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246146"
---
# <a name="persistence-best-practices"></a>Empfohlene Vorgehensweisen für die Persistenz

In diesem Dokument werden empfohlene Vorgehensweisen für Entwurf und Konfiguration von Workflows bezüglich der Workflowpersistenz behandelt.  
  
## <a name="design-and-implementation-of-durable-workflows"></a>Entwurf und Implementierung von permanenten Workflows  

 Im Allgemeinen wechseln sich bei einem Workflow kurze Phasen, in denen Arbeit ausgeführt wird, mit Phasen ab, die durch Leerlauf und das Warten auf ein Ereignis gekennzeichnet sind. Ein solches Ereignis kann beispielsweise eine Nachricht oder ein ablaufender Zeitgeber sein. Um die Workflowinstanz beim Wechsel in den Leerlauf entladen zu können, muss diese vom Diensthost beibehalten werden. Dies ist nur dann möglich, wenn sich die Workflowinstanz nicht in einer Zone ohne Persistenz befindet (z. B. beim Warten auf den Abschluss einer Transaktion oder auf einen asynchronen Rückruf). Um das Entladen von Workflowinstanzen im Leerlauf zu ermöglichen, sollten Workflowautoren Transaktionsbereiche und asynchrone Aktivitäten nur bei Aktionen mit kurzer Laufzeit verwenden. Insbesondere sollten Verzögerungsaktivitäten in Zonen ohne Persistenz so wenig Zeit wie möglich in Anspruch nehmen.  
  
 Workflows können nur beibehalten werden, wenn alle verwendeten Datentypen serialisierbar sind. Außerdem müssen benutzerdefinierte Typen in beibehaltenen Workflows mit <xref:System.Runtime.Serialization.NetDataContractSerializer> serialisiert werden können, damit sie von <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> gespeichert werden können.  
  
 Beim einem Host- oder Computerausfall können Workflowinstanzen, die nicht beibehalten wurden, nicht wiederhergestellt werden. Im Allgemeinen wird daher empfohlen, Workflowinstanzen in der Frühphase des Workflowlebenszyklus persistent zu speichern.  
  
 Bei Workflows, die über einen langen Zeitraum ausgelastet sind, wird empfohlen, die Workflowinstanz in diesem Zeitraum regelmäßig persistent zu speichern. Hierzu können Sie <xref:System.Activities.Statements.Persist>-Aktivitäten in der Abfolge von Aktivitäten einfügen, durch die die Workflowinstanz ausgelastet ist. Bei einer Wiederherstellung der Anwendungsdomäne oder einem Ausfall des Hosts oder Computers wird das System dann nicht wieder auf den Anfang des Auslastungszeitraums zurückgesetzt. Bedenken Sie, dass das Hinzufügen von <xref:System.Activities.Statements.Persist>-Aktivitäten zum Workflow zu Leistungseinbußen führen kann.  
  
 Windows Server AppFabric erleichtert die Konfiguration und Verwendung von Persistenz erheblich. Weitere Informationen finden Sie unter [Windows Server App Fabric-Persistenz](/previous-versions/appfabric/ee677272(v=azure.10)) .  
  
## <a name="configuration-of-scalability-parameters"></a>Konfiguration von Skalierbarkeitsparametern  

 Die Einstellungen der folgenden Parameter hängen von den Anforderungen an die Skalierbarkeit und Leistung ab:  
  
- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A>  
  
- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A>  
  
- <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior.InstanceLockedExceptionAction%2A>  
  
 Diese Parameter sollten in Abhängigkeit vom aktuellen Szenario wie nachfolgend angegeben festgelegt werden.  
  
### <a name="scenario-a-small-number-of-workflow-instances-that-require-optimal-response-time"></a>Szenario: Wenige Workflowinstanzen, die eine optimale Reaktionszeit erfordern  

 Bei diesem Szenario sollten alle Workflowinstanzen auch im Leerlauf geladen bleiben. Legen Sie <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> auf einen hohen Wert fest. Diese Einstellung verhindert eine Verschiebung von Workflowinstanzen zwischen Computern. Verwenden Sie diese Einstellung nur, wenn mindestens eine der folgenden Bedingungen erfüllt ist:  
  
- Eine Workflowinstanz empfängt eine einzelne Nachricht während des Lebenszyklus.  
  
- Alle Workflowinstanzen werden auf einem Computer ausgeführt.  
  
- Alle Nachrichten, die von einer Workflowinstanz empfangen werden, werden auf demselben Computer empfangen.  
  
 Verwenden Sie <xref:System.Activities.Statements.Persist>-Aktivitäten, oder legen Sie <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> auf 0 (null) fest, um eine Wiederherstellung der Workflowinstanz nach einem Ausfall des Diensthosts oder Computers zu ermöglichen.  
  
### <a name="scenario-workflow-instances-are-idle-for-long-periods-of-time"></a>Szenario: Workflowinstanzen befinden sich über lange Zeiträume im Leerlauf  

 Legen Sie <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> in diesem Szenario auf 0 (null) fest, um Ressourcen so bald wie möglich freizugeben.  
  
### <a name="scenario-workflow-instances-receive-multiple-messages-in-a-short-period-of-time"></a>Szenario: Workflowinstanzen empfangen mehrere Nachrichten in einem kurzen Zeitraum  

 Legen Sie <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> in diesem Szenario auf 60 Sekunden fest, wenn die Nachrichten auf demselben Computer empfangen werden. Dadurch wird auch eine rasche Abfolge des Entladens und Ladens einer Workflowinstanz verhindert. Gleichzeitig verbleibt die Instanz nicht unnötig lange im Speicher.  
  
 Legen Sie <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> auf 0 (null) fest, und legen Sie <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior.InstanceLockedExceptionAction%2A> auf BasicRetry oder AggressiveRetry fest, wenn die Nachrichten auf verschiedenen Computern empfangen werden können. Dadurch kann die Workflowinstanz von einem anderen Computer geladen werden.  
  
### <a name="scenario-workflow-uses-delay-activities-with-short-durations"></a>Szenario: Workflow mit Verzögerungsaktivitäten und kurzen Zeitspannen  

 In diesem Szenario wird die Persistenzdatenbank vom <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> in regelmäßigen Abständen nach Instanzen abgefragt, die aufgrund einer abgelaufenen <xref:System.Activities.Statements.Delay>-Aktivität geladen werden sollen. Wenn <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> einen Timer ermittelt, der während des nächsten Abrufintervalls abläuft, wird das Abrufintervall vom SQL-Workflowinstanzspeicher verkürzt. Der nächste Abruf erfolgt dann unmittelbar nach Ablauf des Timers. Auf diese Weise erreicht der SQL-Workflowinstanzspeicher eine hohe Genauigkeit für Timer, deren Ausführungsdauer das Abfrageintervall übersteigt, das durch <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A> festgelegt ist. Damit eine rechtzeitige Verarbeitung kürzerer Verzögerungen gewährleistet ist, muss die Workflowinstanz mindestens für ein Abfrageintervall im Speicher verbleiben.  
  
 Legen Sie <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> auf 0 (null) fest, um die Ablaufzeit in die Persistenzdatenbank zu schreiben.  
  
 Legen Sie <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> auf <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A> oder einen längeren Zeitraum fest, damit die Instanz mindestens für ein Abfrageintervall im Speicher verbleibt.  
  
 Es wird nicht empfohlen, <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A> zu verkürzen, da dies zu einer erhöhten Auslastung der Persistenzdatenbank führt. Bei allen Diensthosts, die den <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> verwenden, wird die Datenbank einmal im Erkennungszeitraum abgefragt. Wenn Sie <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A> auf ein zu kurzes Zeitintervall festlegen, kann es bei einer großen Anzahl an Diensthosts zu Einbußen bei der Systemleistung kommen.  
  
## <a name="configuring-the-sql-workflow-instance-store"></a>Konfigurieren des SQL-Workflowinstanzspeichers  

 Der SQL-Workflowinstanzspeicher verfügt über folgende Konfigurationsparameter:  
  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceEncodingOption%2A>  
 Mit diesem Parameter wird der <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> angewiesen, den Zustand der Workflowinstanz zu komprimieren. Durch die Komprimierung müssen weniger Daten in der Persistenzdatenbank gespeichert werden. Dies verringert den Netzwerkdatenverkehr, wenn sich die Persistenzdatenbank auf einem dedizierten Datenbankserver befindet. Wenn die Komprimierung verwendet wird, sind entsprechende Berechnungsressourcen zur Komprimierung und Extrahierung des Instanzzustands erforderlich. Durch die Komprimierung wird i. d. R. eine höhere Leistung erreicht.  
  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceCompletionAction%2A>  
 Mit diesem Parameter wird der <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> angewiesen, abgeschlossene Instanzen entweder zu speichern oder zu löschen. Durch die Beibehaltung abgeschlossener Instanzen steigen die Speicheranforderungen an die Persistenzdatenbank. Außerdem nimmt die Tabellengröße zu, und Suchvorgänge in Tabellen dauern länger. Wenn Sie abgeschlossene Instanzen nicht zum Debuggen oder Überwachen benötigen, sollte der <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> so konfiguriert sein, dass abgeschlossene Instanzen gelöscht werden. Gelöschte Instanzen sollten nur beibehalten werden, wenn vom Benutzer ein Prozess eingerichtet wird, um diese letztendlich zu löschen. Solange abgeschlossene Workflowinstanzen im Instanzspeicher verbleiben, können Korrelationsschlüssel nicht wiederverwendet werden.  
  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A>  
 Mit diesem Parameter wird das maximale Zeitintervall definiert, in dem die Persistenzdatenbank von <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> nach Instanzen abgefragt wird, die bei Ablauf einer <xref:System.Activities.Statements.Delay>-Aktivität geladen werden sollen. Wenn <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> einen Timer ermittelt, der während des nächsten Abrufintervalls abläuft, wird das Abrufintervall verkürzt, sodass die folgende Abfrage unmittelbar nach Ablauf des Timers durchgeführt wird. Auf diese Weise erreicht der SQL-Workflowinstanzspeicher eine hohe Genauigkeit für Zeitgeber, deren Ausführungsdauer die <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A> übersteigt.  
  
 Es wird nicht empfohlen, <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A> zu verkürzen, da dies zu einer erhöhten Auslastung der Persistenzdatenbank führt. Bei allen Diensthosts, die den <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> verwenden, wird die Datenbank einmal im Erkennungszeitraum abgefragt. Wenn Sie <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A> auf ein zu kurzes Intervall festlegen, kann es bei einer großen Anzahl an Diensthosts zu Einbußen bei der Systemleistung kommen.  
  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.HostLockRenewalPeriod%2A>  
 Dieser Parameter definiert das Intervall zur Erneuerung der Hostsperre in der Persistenzdatenbank. Durch eine Verkürzung dieses Intervalls wird eine schnellere Wiederherstellung von Workflowinstanzen bei einem Host- oder Computerausfall ermöglicht. Allerdings wird durch kurze Erneuerungszeiträume für Sperren die Auslastung der Persistenzdatenbank erhöht. Alle Diensthosts, die den <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> verwenden, aktualisieren ihre Sperren in der Datenbank einmal pro Erneuerungszeitraum. Bei Computern mit vielen Diensthosts sollte sichergestellt werden, dass sich die Sperrerneuerungen nicht negativ auf die Systemleistung auswirken. Verkürzen Sie andernfalls die <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.HostLockRenewalPeriod%2A>.  
  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceLockedExceptionAction%2A>  
 Wenn diese Einstellung aktiviert ist, wird von <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 30 Sekunden lang versucht, eine gesperrte Instanz erneut zu laden. Legen Sie <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceLockedExceptionAction%2A> auf BasicRetry oder AggressiveRetry fest, wenn der Workflow mehrere Nachrichten innerhalb kurzer Zeit empfängt und die Nachrichten von verschiedenen Computern empfangen werden.  
  
 Da durch den Mechanismus zum Wiederholen des Ladevorgangs kein Leistungsmehraufwand verursacht wird, solange der Mechanismus nicht tatsächlich ausgeführt wird, sollte <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceLockedExceptionAction%2A> in jedem Fall aktiviert sein.
