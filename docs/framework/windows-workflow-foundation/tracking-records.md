---
title: Nachverfolgungsdatensätze
ms.date: 03/30/2017
ms.assetid: 51adbda3-bd8b-4892-a8ea-d343186472d2
ms.openlocfilehash: c9c0d7d8c29d89ab47957c271444740f5f2f9b7f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650944"
---
# <a name="tracking-records"></a>Nachverfolgungsdatensätze
Die Workflowlaufzeit ist so instrumentiert, dass Überwachungsdatensätze im Zusammenhang mit der Ausführung einer Workflowinstanz ausgegeben werden.  
  
## <a name="tracking-records"></a>Nachverfolgungsdatensätze  
 In der folgenden Tabelle sind die Überwachungsdatensätze aufgeführt, die von der Workflowlaufzeit ausgegeben werden.  
  
|Überwachungsdatensatz|Beschreibung|  
|---------------------|-----------------|  
|Datensätze zum Workflowlebenszyklus|Werden in verschiedenen Phasen des Lebenszyklus der Workflowinstanz ausgegeben. Z. B. Datensätze, die beim Starten oder Beenden des Workflows ausgegeben werden.|  
|Datensätze zum Aktivitätslebenszyklus|Führen Einzelheiten zur Aktivitätsausführung auf. Diese Datensätze geben den Zustand einer Workflowaktivität an, z. B. wenn eine Aktivität geplant oder abgeschlossen wird oder wenn ein Fehler auftritt.|  
|Datensätze zur Wiederaufnahme von Lesezeichen.|Wird immer dann ausgegeben, wenn ein Lesezeichen in einer Workflowinstanz wieder aufgenommen wird.|  
|Benutzerdefinierte Überwachungsdatensätze|Ein Workflowautor kann benutzerdefinierte Überwachungsdatensätze erstellen und in einer benutzerdefinierten Aktivität ausgeben.|  
  
 Alle überwachungsbezogenen Datensätze, die von der WF-Laufzeit ausgegeben werden, leiten sich von der <xref:System.Activities.Tracking.TrackingRecord>-Basisklasse ab, die den allgemeinen Satz von Daten enthält. Überwachungsdatensätze zeigen den Lebenszyklus eines einfachen Workflows an. Jeder Überwachungsdatensatz enthält Details zum zugeordneten Überwachungsereignis, z. B. das <xref:System.Activities.Tracking.TrackingRecord.InstanceId%2A>-Objekt, das <xref:System.Activities.Tracking.TrackingRecord.RecordNumber%2A>-Objekt und weitere Informationen, die spezifisch für den Typ des Überwachungsdatensatzes sind.  
  
 Die folgenden <xref:System.Activities.Tracking.TrackingRecord>-Objekttypen werden von der Workflowlaufzeit ausgegeben:  
  
- **WorkflowInstanceRecord** : dieses <xref:System.Activities.Tracking.TrackingRecord> beschreiben den Lebenszyklus der Workflowinstanz. Es wird unter anderem ein Datensatz ausgegeben, wenn der Workflow gestartet oder abgeschlossen wird. Der Datensatz enthält den Zustand der Workflowinstanz. Die Details dieses Datensatzes werden im <xref:System.Activities.Tracking.WorkflowInstanceRecord>-Objekt angezeigt.  
  
- **WorkflowInstanceAbortedRecord** : dieses <xref:System.Activities.Tracking.TrackingRecord> wird ausgegeben, wenn eine Workflowinstanz abgebrochen. Der Datensatz enthält den Grund für den Abbruch der Workflowinstanz. Die Details dieses Datensatzes werden im <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>-Objekt angezeigt.  
  
- **WorkflowInstanceUnhandledExceptionRecord** : dieses <xref:System.Activities.Tracking.TrackingRecord> wird ausgegeben, wenn eine Ausnahme tritt auf, in der Workflowinstanz und nicht von einer Aktivität behandelt. Der Datensatz enthält die Details zur Ausnahme. Die Details dieses Datensatzes werden im <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>-Objekt angezeigt.  
  
- **WorkflowInstanceSuspendedRecord** : dieses <xref:System.Activities.Tracking.TrackingRecord> wird ausgegeben, wenn eine Workflowinstanz angehalten wird. Der Datensatz enthält den Grund für das Anhalten der Workflowinstanz. Die Details dieses Datensatzes werden im <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>-Objekt angezeigt.  
  
- **WorkflowInstanceTerminatedRecord** : dieses <xref:System.Activities.Tracking.TrackingRecord> wird ausgegeben, wenn eine Workflowinstanz beendet wird. Der Datensatz enthält den Grund für das Beenden der Workflowinstanz. Die Details dieses Datensatzes werden im <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>-Objekt angezeigt.  
  
- **ActivityStateRecord** : dieses <xref:System.Activities.Tracking.TrackingRecord> wird ausgegeben, wenn eine Aktivität in einem Workflow ausgeführt wird. Diese Datensätze geben den Zustand der Aktivität innerhalb der Workflowinstanz an. Die Details dieses Datensatzes werden im <xref:System.Activities.Tracking.ActivityStateRecord>-Objekt angezeigt.  
  
- **ActivityScheduledRecord** : dieses <xref:System.Activities.Tracking.TrackingRecord> wird ausgegeben, wenn eine Aktivität eine untergeordnete Aktivität plant. Dieser Datensatz enthält Details für die übergeordnete Aktivität (Planungsaktivität) und die untergeordnete Aktivität (geplante Aktivität). Die Details dieses Datensatzes werden im <xref:System.Activities.Tracking.ActivityScheduledRecord>-Objekt angezeigt.  
  
- **FaultPropagationRecord** : dieses <xref:System.Activities.Tracking.TrackingRecord> wird ausgegeben, für jeden Handler, die den Datensatz untersucht werden soll, bis er behandelt wird. Es wird verwendet, um den Pfad eines Fehlers innerhalb der Workflowinstanz zu bezeichnen. Die Details dieses Datensatzes werden im <xref:System.Activities.Tracking.FaultPropagationRecord>-Objekt angezeigt.  
  
- **CancelRequestedRecord** : dieses <xref:System.Activities.Tracking.TrackingRecord> wird ausgegeben, wenn eine Aktivität versucht, das Abbrechen einer untergeordneten Aktivität. Dieser Datensatz enthält Details für die übergeordnete Aktivität und die untergeordnete Aktivität, die abgebrochen wird. Die Details dieses Datensatzes werden im <xref:System.Activities.Tracking.CancelRequestedRecord>-Objekt angezeigt.  
  
- **BookmarkResumptionRecord** : dieses <xref:System.Activities.Tracking.TrackingRecord> verfolgt alle Lesezeichen aus, die erfolgreich fortgesetzt wird. Die Details dieses Datensatzes werden im <xref:System.Activities.Tracking.BookmarkResumptionRecord>-Objekt angezeigt.  
  
- **CustomTrackingRecord** : dieses <xref:System.Activities.Tracking.TrackingRecord> erstellt und von einem workflowautor in einer benutzerdefinierten Workflowaktivität ausgegeben. Benutzerdefinierte Überwachungsdatensätze können mit Daten aufgefüllt werden, die mit den Datensätzen ausgegeben werden. Die Details dieses Datensatzes werden im <xref:System.Activities.Tracking.CustomTrackingRecord>-Objekt angezeigt.  
  
 Beispielsweise könnte eine einfache <xref:System.Activities.Statements.Sequence>-Aktivität vorhanden sein, die einen <xref:System.Activities.Statements.WriteLine>-Vorgang mit Überwachungsdatensätzen enthält, die in der folgenden Reihenfolge ausgegeben werden:  
  
1. Das <xref:System.Activities.Tracking.WorkflowInstanceRecord>-Objekt gibt an, dass der Workflow gestartet wird.  
  
2. Das <xref:System.Activities.Tracking.ActivityScheduledRecord>-Objekt gibt an, dass eine Aktivität geplant wurde. In diesem Fall handelt es sich um eine <xref:System.Activities.Statements.Sequence>-Aktivität.  
  
3. Das <xref:System.Activities.Tracking.ActivityScheduledRecord>-Objekts stellt die <xref:System.Activities.Statements.WriteLine>-Aktivität dar.  
  
4. Es gibt zwei <xref:System.Activities.Tracking.ActivityStateRecord>-Datensätze, die die zwei Aktivitäten darstellen, die abgeschlossen werden.  
  
5. Das <xref:System.Activities.Tracking.WorkflowInstanceRecord>-Objekt gibt an, dass der Workflow abgeschlossen wird.  
  
## <a name="see-also"></a>Siehe auch

- [Windows Server App Fabric-Überwachung](https://go.microsoft.com/fwlink/?LinkId=201273)
- [Überwachen von Anwendungen mit AppFabric](https://go.microsoft.com/fwlink/?LinkId=201275)
