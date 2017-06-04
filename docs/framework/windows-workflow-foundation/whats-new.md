---
title: "Neues in Windows Workflow Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WF [WF], Neues"
  - "Windows Workflow Foundation [WF], Neues"
ms.assetid: 11f96014-001e-41a0-bcc2-d0684a52fa43
caps.latest.revision: 29
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 29
---
# Neues in Windows Workflow Foundation
Zahlreiche Entwicklungsmuster früherer Versionen wurden für [!INCLUDE[wf](../../../includes/wf-md.md)] in [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)] überholt.Workflows sind jetzt einfacher zu erstellen, auszuführen und zu warten und implementieren eine Vielzahl neuer Funktionen.[!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Migrieren von .NET 3.0 und .NET 3.5\-Workflowanwendungen, sodass sie die neueste Version verwenden, finden Sie unter [Migrationsanleitung](../../../docs/framework/windows-workflow-foundation//migration-guidance.md).  
  
## Workflowaktivitätsmodell  
 Statt der <xref:System.Workflow.Activities.SequentialWorkflowActivity>\-Klasse oder der <xref:System.Workflow.Activities.StatemachineWorkflowActivity>\-Klasse ist die Aktivität jetzt die Basiseinheit beim Erstellen eines Workflows.Die <xref:System.Activities.Activity>\-Klasse stellt die Basisabstraktion des Workflowverhaltens bereit.Aktivitätsautoren können dann <xref:System.Activities.CodeActivity> für eine grundlegende benutzerdefinierte Aktivitätsfunktionalität oder <xref:System.Activities.NativeActivity> für eine benutzerdefinierte Aktivitätsfunktionalität, die alle zur Laufzeit verfügbaren Funktionen verwendet, implementieren.Die <xref:System.Activities.Activity>\-Klasse wird von Aktivitätsautoren verwendet, um neue Verhaltensweisen deklarativ mittels anderer <xref:System.Activities.NativeActivity>\-Objekte, <xref:System.Activities.CodeActivity>\-Objekte, <xref:System.Activities.AsyncCodeActivity>\-Objekte oder <xref:System.Activities.DynamicActivity>\-Objekte auszudrücken, die entweder selbst entwickelt wurden oder in der [Integrierte Aktivitätsbibliothek](../../../docs/framework/windows-workflow-foundation//net-framework-4-5-built-in-activity-library.md) enthalten sind.  
  
## Umfangreiche zusammengesetzte Aktivitätsoptionen  
 <xref:System.Activities.Statements.Flowchart> ist eine leistungsstarke neue Ablaufsteuerungsaktivität, die es Autoren ermöglicht, beliebige Schleifen und bedingte Verzweigungen zu modellieren.<xref:System.Activities.Statements.Flowchart> stellt ein ereignisgesteuertes Programmiermodell bereit, das zuvor nur mit <xref:System.Workflow.Activities.StateMachineWorkflowActivity> implementiert werden konnte.Verfahrensworkflows profitieren von neuen Flusssteuerungsaktivitäten, die herkömmliche Flusssteuerungsstrukturen modellieren, z. B. <xref:System.Activities.Statements.TryCatch> und <xref:System.Activities.Statements.Switch%601>.  
  
## Erweiterte integrierte Aktivitätsbibliothek  
 Die Aktivitätsbibliothek bietet u. a. die folgenden neuen Funktionen:  
  
-   Neue Flusssteuerungsaktivitäten, z. B. <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.Pick>, <xref:System.Activities.Statements.TryCatch>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Switch%601> und <xref:System.Activities.Statements.ParallelForEach%601>.  
  
-   Aktivitäten zum Bearbeiten von Memberdaten, z. B. <xref:System.Activities.Statements.Assign>, sowie Auflistungsaktivitäten, z. B. <xref:System.Activities.Statements.AddToCollection%601>.  
  
-   Aktivitäten zum Steuern von Transaktionen, z. B. <xref:System.Activities.Statements.TransactionScope> und <xref:System.Activities.Statements.Compensate>.  
  
-   Neue Messagingaktivitäten, z. B. <xref:System.ServiceModel.Activities.SendContent> und <xref:System.ServiceModel.Activities.ReceiveReply>.  
  
## Explizites Aktivitätsdatenmodell  
 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] umfasst neue Optionen zum Speichern und Verschieben von Daten.Daten können mit <xref:System.Activities.Variable> in einer Aktivität gespeichert werden.Beim Verschieben von Daten in und aus einer Aktivität wird mittels spezialisierter Argumenttypen die Verschieberichtung bestimmt.Dies sind die Typen <xref:System.Activities.InArgument>, <xref:System.Activities.InOutArgument> und <xref:System.Activities.OutArgument>.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Windows Workflow Foundation\-Datenmodell](../../../docs/framework/windows-workflow-foundation//data-model.md).  
  
## Verbesserte Hosting\-, Persistenz\- und Nachverfolgungsoptionen  
 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] bietet Erweiterungen der Persistenz, wie beispielsweise:  
  
-   Mehr Optionen zum Ausführen von Workflows, darunter <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.Activities.WorkflowApplication> und <xref:System.Activities.WorkflowInvoker>.  
  
-   Workflowzustandsdaten können mit der <xref:System.Activities.Statements.Persist>\-Aktivität explizit in den Persistenzspeicher verschoben werden.  
  
-   Ein Host kann ein <xref:System.Activities.ActivityInstance>\-Objekt ohne Entladen in den Persistenzspeicher verschieben.  
  
-   Beim Arbeiten mit Daten, die nicht in den Persistenzspeicher verschoben werden können, kann ein Workflow Zonen ohne Persistenz angeben, um den Vorgang zu verschieben, bis die Zone ohne Persistenz beendet wird.  
  
-   Das <xref:System.Activities.Statements.TransactionScope>\-Objekt ermöglicht den Transaktionsfluss in einen Workflow.  
  
-   Die Nachverfolgung wird mit dem <xref:System.Activities.Tracking.TrackingParticipant>\-Objekt vereinfacht.  
  
-   Die Nachverfolgung im Systemereignisprotokoll wird mit dem <xref:System.Activities.Tracking.EtwTrackingParticipant>\-Objekt bereitgestellt.  
  
-   Das Fortsetzen ausstehender Workflows kann jetzt mit dem <xref:System.Activities.Bookmark>\-Objekt verwaltet werden.  
  
## Vereinfachte Erweiterung der WF\-Designer\-Umgebung  
 Der neue WF\-Designer basiert auf [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] und stellt ein einfacheres Modell zum erneuten Hosten des WF\-Designers außerhalb von Visual Studio sowie einfachere Mechanismen zum Erstellen benutzerdefinierter Aktivitäts\-Designer bereit.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Anpassen des Workflowentwurfsvorgangs](../../../docs/framework/windows-workflow-foundation//customizing-the-workflow-design-experience.md).