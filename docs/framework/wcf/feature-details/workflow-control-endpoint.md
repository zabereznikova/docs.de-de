---
title: Workflowsteuerungsendpunkt
ms.date: 03/30/2017
ms.assetid: 1b883334-1590-4fbb-b0d6-65197efe0700
ms.openlocfilehash: 40fec2902598daed178e070b02c1067c308507c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33502591"
---
# <a name="workflow-control-endpoint"></a>Workflowsteuerungsendpunkt
Der Workflowsteuerungsendpunkt ermöglicht Entwicklern das Aufrufen von Steuerungsvorgängen, um mit <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostete Workflowinstanzen remote zu steuern. Diese Funktion kann verwendet werden, um Steuerungsvorgänge wie das Anhalten, Fortsetzen und Beenden programmgesteuert auszuführen.  
  
> [!WARNING]
>  Wenn der Workflowsteuerungsendpunkt innerhalb einer Transaktion verwendet wird und der gesteuerte Workflow eine <xref:System.Activities.Statements.Persist>-Aktivität enthält, bleibt die Workflowinstanz bis zum Timeout der Transaktion hängen.  
  
## <a name="workflow-instance-management"></a>Workflowinstanzverwaltung  
 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] definiert einen neuen Vertrag mit dem Namen <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement>. Dieser Vertrag definiert eine Reihe von Steuerungsvorgängen, mit denen Sie von <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostete Workflowinstanzen remote steuern können. <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> ist ein Standardendpunkt, der eine Implementierung des <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement>-Vertrags bereitstellt. <xref:System.ServiceModel.Activities.WorkflowControlClient> ist eine Klasse, über die Steuerungsvorgänge an den <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> gesendet werden.  
  
 Workflowinstanzen können einen der folgenden Zustände aufweisen:  
  
 Aktiv  
 Dies ist der Zustand einer Workflowinstanz vor dem Zustand "Abgeschlossen", falls diese nicht den Zustand "Angehalten" aufweist. In diesem Zustand wird die Workflowinstanz ausgeführt und verarbeitet Anwendungsmeldungen.  
  
 Angehalten  
 In diesem Zustand wird die Workflowinstanz nicht ausgeführt. Dies gilt auch, wenn Aktivitäten vorhanden sind, deren Ausführung noch nicht gestartet wurde oder die nur teilweise ausgeführt wurden.  
  
 Abgeschlossen  
 Der Endzustand einer Workflowinstanz. Die Workflowinstanz kann nicht ausgeführt werden, nachdem sie den Zustand "Abgeschlossen" erreicht hat.  
  
## <a name="iworkflowinstancemanagement"></a>IWorkflowInstanceManagement  
 Die <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement>-Schnittstelle definiert einen Satz von Steuerungsvorgängen mit synchronen und asynchronen Versionen. Die transaktiven Versionen erfordern die Verwendung einer Bindung, die Transaktionen verarbeiten kann. In der folgenden Tabelle sind die unterstützten Steuerungsvorgänge aufgelistet.  
  
|Steuerungsvorgang|Beschreibung|  
|-----------------------|-----------------|  
|Abbrechen|Erzwingt, dass Ausführung der Workflowinstanz beendet wird.|  
|Abbrechen|Bewirkt, dass eine Workflowinstanz aus dem Zustand "Aktiv" oder "Angehalten" in den Zustand "Abgeschlossen" wechselt.|  
|Run|Ermöglicht, dass eine Workflowinstanz ausgeführt wird.|  
|Suspend (Anhalten)|Bewirkt, dass eine Workflowinstanz aus dem Zustand "Aktiv" in den Zustand "Angehalten" wechselt.|  
|Beenden|Bewirkt, dass eine Workflowinstanz aus dem Zustand "Aktiv" oder "Angehalten" in den Zustand "Abgeschlossen" wechselt.|  
|Unsuspend (Fortsetzen)|Bewirkt, dass eine Workflowinstanz aus dem Zustand "Angehalten" in den Zustand "Aktiv" wechselt.|  
|TransactedCancel|Führt den Vorgang „Abbrechen“ im Rahmen einer Transaktion (per Transaktionsfluss vom Client oder lokal erstellt) aus. Wenn das System den permanenten Zustand der Workflowinstanz beibehält, muss die Workflowinstanz während der Ausführung dieses Vorgangs beibehalten werden.|  
|TransactedRun|Führt den Vorgang „Ausführen“ im Rahmen einer Transaktion (per Transaktionsfluss vom Client oder lokal erstellt) aus. Wenn das System den permanenten Zustand der Workflowinstanz beibehält, muss die Workflowinstanz während der Ausführung dieses Vorgangs beibehalten werden.|  
|TransactedSuspend|Führt den Vorgang "Anhalten" im Rahmen einer Transaktion (per Transaktionsfluss vom Client oder lokal erstellt) aus. Wenn das System den permanenten Zustand der Workflowinstanz beibehält, muss die Workflowinstanz während der Ausführung dieses Vorgangs beibehalten werden.|  
|TransactedTerminate|Führt den Vorgang „Beenden“ im Rahmen einer Transaktion (per Transaktionsfluss vom Client oder lokal erstellt) aus. Wenn das System den permanenten Zustand der Workflowinstanz beibehält, muss die Workflowinstanz während der Ausführung dieses Vorgangs beibehalten werden.|  
|TransactedUnsuspend|Führt den Vorgang "Fortsetzen" im Rahmen einer Transaktion (per Transaktionsfluss vom Client oder lokal erstellt) aus. Wenn das System den permanenten Zustand der Workflowinstanz beibehält, muss die Workflowinstanz während der Ausführung dieses Vorgangs beibehalten werden.|  
  
 Mit dem <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement>-Vertrag können Sie keine neue Workflowinstanz erstellen, sondern nur vorhandene Workflowinstanzen verwalten. Weitere Informationen zu Remote Erstellen einer neuen Workflowinstanz, finden Sie unter [Erweiterbarkeit des Workflowdiensthosts](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).  
  
## <a name="workflowcontrolendpoint"></a>WorkflowControlEndpoint  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> ist ein Standardendpunkt mit einem festen Vertrag (<xref:System.ServiceModel.Activities.IWorkflowInstanceManagement>). Wenn dieser Endpunkt einer <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Instanz hinzugefügt wird, kann er zum Senden von Befehlsvorgängen an eine beliebige Workflowinstanz verwendet werden, die von der Hostinstanz gehostet wird. Weitere Informationen zu Standardendpunkten, finden Sie unter [Standardendpunkte](../../../../docs/framework/wcf/feature-details/standard-endpoints.md).  
  
## <a name="workflowcontrolclient"></a>WorkflowControlClient  
 <xref:System.ServiceModel.Activities.WorkflowControlClient> ist eine Klasse, mit der Sie Steuerungsmeldungen an einen <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> auf einem <xref:System.ServiceModel.Activities.WorkflowServiceHost> senden können. Die Klasse enthält eine Methode für jeden einzelnen Vorgang, der vom <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement>-Vertrag unterstützt wird, mit Ausnahme der transaktiven Vorgänge. <xref:System.ServiceModel.Activities.WorkflowControlClient> verwendet die Ambient-Transaktion, um zu ermitteln, ob ein transaktiver Vorgang verwendet werden soll.
