---
title: Was&#39;s neu in Windows Workflow Foundation
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Workflow Foundation [WF], what's new
- WF [WF], what's new
ms.assetid: 11f96014-001e-41a0-bcc2-d0684a52fa43
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 73f4364d92c366dc6750144668f722fea93bca2b
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="what39s-new-in-windows-workflow-foundation"></a>Was&#39;s neu in Windows Workflow Foundation
Windows Workflow Foundation (WF) in [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)] zahlreiche Entwicklungsmuster ändert sich von früheren Versionen. Workflows sind jetzt einfacher zu erstellen, auszuführen und zu warten und implementieren eine Vielzahl neuer Funktionen. Weitere Informationen zum Migrieren von .NET 3.0 und .NET 3.5-workflowanwendungen auf die neueste Version verwenden, finden Sie unter [Migrationsanleitung](../../../docs/framework/windows-workflow-foundation/migration-guidance.md).  
  
## <a name="workflow-activity-model"></a>Workflowaktivitätsmodell  
 Statt der <xref:System.Workflow.Activities.SequentialWorkflowActivity>-Klasse oder der <xref:System.Workflow.Activities.StateMachineWorkflowActivity>-Klasse ist die Aktivität jetzt die Basiseinheit beim Erstellen eines Workflows. Die <xref:System.Activities.Activity>-Klasse stellt die Basisabstraktion des Workflowverhaltens bereit. Aktivitätsautoren können dann <xref:System.Activities.CodeActivity> für eine grundlegende benutzerdefinierte Aktivitätsfunktionalität oder <xref:System.Activities.NativeActivity> für eine benutzerdefinierte Aktivitätsfunktionalität, die alle zur Laufzeit verfügbaren Funktionen verwendet, implementieren. <xref:System.Activities.Activity> ist eine Klasse, die von aktivitätsautoren verwendet, um das neue Verhalten deklarativ im Hinblick auf andere express <xref:System.Activities.NativeActivity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, oder <xref:System.Activities.DynamicActivity> -Objekte, ab, ob sie benutzerdefinierte entwickelt oder im enthalten sind die [integrierten Aktivität Bibliothek](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).  
  
## <a name="rich-composite-activity-options"></a>Umfangreiche zusammengesetzte Aktivitätsoptionen  
 <xref:System.Activities.Statements.Flowchart> ist eine leistungsstarke neue Ablaufsteuerungsaktivität, die es Autoren ermöglicht, beliebige Schleifen und bedingte Verzweigungen zu modellieren. <xref:System.Activities.Statements.Flowchart> stellt ein ereignisgesteuertes Programmiermodell bereit, das zuvor nur mit <xref:System.Workflow.Activities.StateMachineWorkflowActivity> implementiert werden konnte. Verfahrensworkflows profitieren von neuen Flusssteuerungsaktivitäten, die herkömmliche Flusssteuerungsstrukturen modellieren, z. B. <xref:System.Activities.Statements.TryCatch> und <xref:System.Activities.Statements.Switch%601>.  
  
## <a name="expanded-built-in-activity-library"></a>Erweiterte integrierte Aktivitätsbibliothek  
 Die Aktivitätsbibliothek bietet u. a. die folgenden neuen Funktionen:  
  
-   Neue Flusssteuerungsaktivitäten, z. B. <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.Pick>, <xref:System.Activities.Statements.TryCatch>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Switch%601> und <xref:System.Activities.Statements.ParallelForEach%601>.  
  
-   Aktivitäten zum Bearbeiten von Memberdaten, z. B. <xref:System.Activities.Statements.Assign>, sowie Auflistungsaktivitäten, z. B. <xref:System.Activities.Statements.AddToCollection%601>.  
  
-   Aktivitäten zum Steuern von Transaktionen, z. B. <xref:System.Activities.Statements.TransactionScope> und <xref:System.Activities.Statements.Compensate>.  
  
-   Neue Messagingaktivitäten, z. B. <xref:System.ServiceModel.Activities.SendContent> und <xref:System.ServiceModel.Activities.ReceiveReply>.  
  
## <a name="explicit-activity-data-model"></a>Explizites Aktivitätsdatenmodell  
 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] umfasst neue Optionen zum Speichern und Verschieben von Daten. Daten können mit <xref:System.Activities.Variable> in einer Aktivität gespeichert werden. Beim Verschieben von Daten in und aus einer Aktivität wird mittels spezialisierter Argumenttypen die Verschieberichtung bestimmt. Dies sind die Typen <xref:System.Activities.InArgument>, <xref:System.Activities.InOutArgument> und <xref:System.Activities.OutArgument>. Weitere Informationen finden Sie unter [Windows Workflow Foundation-Datenmodell](../../../docs/framework/windows-workflow-foundation/data-model.md).  
  
## <a name="enhanced-hosting-persistence-and-tracking-options"></a>Verbesserte Hosting-, Persistenz- und Nachverfolgungsoptionen  
 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] bietet Erweiterungen der Persistenz, wie beispielsweise:  
  
-   Mehr Optionen zum Ausführen von Workflows, darunter <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.Activities.WorkflowApplication> und <xref:System.Activities.WorkflowInvoker>.  
  
-   Workflowzustandsdaten können mit der <xref:System.Activities.Statements.Persist>-Aktivität explizit in den Persistenzspeicher verschoben werden.  
  
-   Ein Host kann ein <xref:System.Activities.ActivityInstance>-Objekt ohne Entladen in den Persistenzspeicher verschieben.  
  
-   Beim Arbeiten mit Daten, die nicht in den Persistenzspeicher verschoben werden können, kann ein Workflow Zonen ohne Persistenz angeben, um den Vorgang zu verschieben, bis die Zone ohne Persistenz beendet wird.  
  
-   Das <xref:System.Activities.Statements.TransactionScope>-Objekt ermöglicht den Transaktionsfluss in einen Workflow.  
  
-   Die Nachverfolgung wird mit dem <xref:System.Activities.Tracking.TrackingParticipant>-Objekt vereinfacht.  
  
-   Die Nachverfolgung im Systemereignisprotokoll wird mit dem <xref:System.Activities.Tracking.EtwTrackingParticipant>-Objekt bereitgestellt.  
  
-   Das Fortsetzen ausstehender Workflows kann jetzt mit dem <xref:System.Activities.Bookmark>-Objekt verwaltet werden.  
  
## <a name="easier-ability-to-extend-wf-designer-experience"></a>Vereinfachte Erweiterung der WF-Designer-Umgebung  
 Der neue WF-Designer basiert auf Windows Presentation Foundation (WPF) und stellt ein einfacheres Modell zu verwenden, wenn die WF-Designer außerhalb von Visual Studio erneutes hosten und bietet auch einfachere Mechanismen zum Erstellen benutzerdefinierter Aktivitäts-Designer. Weitere Informationen finden Sie unter [Anpassen des Workflowentwurfsvorgangs](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md).
