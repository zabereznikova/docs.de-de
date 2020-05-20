---
title: Nachverfolgung und Ablaufverfolgung für Workflows
description: Die Windows-Workflow Überwachung ist eine .NET Framework 4.6.1-Funktion, die eine Überwachungsinfrastruktur bereitstellt, um die Ausführung einer Workflow Instanz zu verfolgen.
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], tracking and tracing
ms.assetid: b965ded6-370a-483d-8790-f794f65b137e
ms.openlocfilehash: f88ff68a361bf3882d75bc2d5fb21903fd283a4d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421292"
---
# <a name="workflow-tracking-and-tracing"></a>Nachverfolgung und Ablaufverfolgung für Workflows
Die Windows Workflow-Überwachung ist eine [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]-Funktion, die für Sichtbarkeit in die Workflowausführung ausgelegt ist. Sie stellt eine Überwachungsinfrastruktur bereit, um die Ausführung einer Workflowinstanz nachzuverfolgen. Die Infrastruktur für die WF-Überwachung verwendet auf transparente Weise einen Workflow, um während der Ausführung Datensätze auszugeben, die Schlüsselereignisse festhalten. Diese Funktionalität ist standardmäßig für alle [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]-Workflows verfügbar. An einem [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]-Workflow müssen keine Änderungen vorgenommen werden, damit eine Überwachung erfolgt. Es geht nur darum, zu entscheiden, wie viele Überwachungsdaten Sie empfangen möchten. Wenn eine Workflowinstanz gestartet oder abgeschlossen wird, werden die zugehörigen Überwachungsdatensätze ausgegeben. Die Überwachung kann auch geschäftsrelevante, den Workflowvariablen zugeordnete Daten extrahieren. Wenn zum Beispiel der Workflow ein System zur Verarbeitung von Bestellungen darstellt, kann die Bestellungs-ID zusammen mit dem <xref:System.Activities.Tracking.TrackingRecord>-Objekt extrahiert werden. Im Allgemeinen erleichtert die WF-Überwachung den Zugriff auf Diagnose- oder Geschäftsanalysedaten über eine Workflowausführung.  
  
 Diese nach Verfolgungs Komponenten entsprechen dem Überwachungsdienst in WinFX. Die [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] wurde die Leistung für die WF-Überwachungsfunktion erhöht und das Programmiermodell dafür vereinfacht. Die Überwachungslaufzeit verwendet eine Workflowinstanz, um Ereignisse in Verbindung mit dem Workflow-Lebenszyklus, den Workflowaktivitäten und benutzerdefinierten Ereignissen auszugeben.  
  
 Windows Server AppFabric bietet auch die Möglichkeit, die Ausführung von WCF und Workflowdiensten zu überwachen. Weitere Informationen finden Sie unter [Windows Server App Fabric-Überwachung](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10)) und- [Überwachung Anwendungen mit Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10)) .  
  
 Zur Fehlerbehandlung der Workflowlaufzeit können Sie die Workflow-Ablaufverfolgung zur Diagnose aktivieren. Weitere Informationen finden Sie unter [Workflow-Ablauf Verfolgung](workflow-tracing.md).  
  
 Für ein besseres Verständnis des Programmiermodells werden in diesem Thema die Hauptkomponenten der Überwachungsinfrastruktur erläutert:  
  
- Von der Workflowlaufzeit ausgegebene <xref:System.Activities.Tracking.TrackingRecord>-Objekte. Weitere Informationen finden Sie unter nach [Verfolgungs Datensätze](tracking-records.md).  
  
- <xref:System.Activities.Tracking.TrackingParticipant>-Objekte abonnieren <xref:System.Activities.Tracking.TrackingRecord>-Objekte. Die Überwachungsteilnehmer enthalten die Logik zur Verarbeitung der Nutzdaten der <xref:System.Activities.Tracking.TrackingRecord>-Objekte (beispielsweise für das Schreiben in eine Datei). Weitere Informationen finden Sie unter nach [Verfolgung von Teilnehmern](tracking-participants.md).  
  
- <xref:System.Activities.Tracking.TrackingProfile>-Objekte filtern die von einer Workflowinstanz ausgegebenen Überwachungsdatensätze. Weitere Informationen finden Sie unter nach [Verfolgungs profile](tracking-profiles.md).  
  
## <a name="workflow-tracking-infrastructure"></a>Infrastruktur für Workflowüberwachung  
 Die Infrastruktur für die Workflowüberwachung erfolgt als Veröffentlichen-und-Abonnieren-Paradigma. Die Workflowinstanz ist der Verleger von Überwachungsdatensätzen, während Abonnenten der Überwachungsdatensätze als Erweiterungen des Workflows registriert werden. Diese Erweiterungen, die <xref:System.Activities.Tracking.TrackingRecord>-Objekte abonnieren, werden als Überwachungsteilnehmer bezeichnet. Überwachungsteilnehmer sind Erweiterbarkeitspunkte mit Zugriff auf <xref:System.Activities.Tracking.TrackingRecord>-Objekte. Sie verarbeiten diese auf jede Weise, die Ihnen angegeben wird. Die Überwachungsinfrastruktur ermöglicht die Anwendung eines Filters für ausgehende Überwachungsdatensätze, sodass ein Teilnehmer eine Teilmenge der Datensätze abonnieren kann. Dieser Filtermechanismus wird durch eine Überwachungsprofildatei erzielt.  
  
 In der folgenden Abbildung wird ein allgemeiner Überblick über die Überwachungsinfrastruktur angezeigt:  
  
 ![Screenshot, der die Infrastruktur für die Workflow Nachverfolgung zeigt](./media/workflow-tracking-and-tracing/workflow-tracking-infrastructure.gif "WV")  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Nachverfolgungsdatensätze](tracking-records.md)  
 Beschreibt die Überwachungsdatensätze, die von der Workflowlaufzeit ausgegeben werden.  
  
 [Überwachungsprofile](tracking-profiles.md)  
 Erläutert die Verwendung von Überwachungsprofilen.  
  
 [Überwachungsteilnehmer](tracking-participants.md)  
 Beschreibt, wie ein vom System bereitgestellter Überwachungsteilnehmer verwendet wird oder wie benutzerdefinierte Überwachungsteilnehmer erstellt werden.  
  
 [Konfigurieren der Nachverfolgung für einen Workflow](configuring-tracking-for-a-workflow.md)  
 Beschreibt, wie die Überwachung des Workflows konfiguriert wird.  
  
 [Workflowüberwachung](workflow-tracing.md)  
 Beschreibt die zwei Möglichkeiten, die Debugüberwachung eines Workflows zu aktivieren.  
  
## <a name="see-also"></a>Siehe auch

- [SQL-Nachverfolgung](./samples/sql-tracking.md)
