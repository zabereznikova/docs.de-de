---
title: Neues in Windows Workflow Foundation
description: Erfahren Sie mehr über Windows Workflow Foundation Änderungen in .NET Framework 4. Workflows sind einfacher zu erstellen, auszuführen und zu warten.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Workflow Foundation [WF], what's new
- WF [WF], what's new
ms.assetid: 11f96014-001e-41a0-bcc2-d0684a52fa43
ms.openlocfilehash: d6a3cda7b9334ca4710ada5aa0848eb5be815b0a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293831"
---
# <a name="whats-new-in-windows-workflow-foundation"></a>Neues in Windows Workflow Foundation

Windows Workflow Foundation (WF) in .NET Framework 4 ändert mehrere Entwicklungsparadigmen aus früheren Versionen. Workflows sind jetzt einfacher zu erstellen, auszuführen und zu warten und implementieren eine Vielzahl neuer Funktionen. Weitere Informationen zum Migrieren von .NET Framework 3,0-und .NET Framework 3,5-Workflow Anwendungen zur Verwendung der neuesten Version finden Sie in der [Migrations Anleitung](migration-guidance.md).

## <a name="workflow-activity-model"></a>Workflowaktivitätsmodell

 Statt der <xref:System.Workflow.Activities.SequentialWorkflowActivity>-Klasse oder der <xref:System.Workflow.Activities.StateMachineWorkflowActivity>-Klasse ist die Aktivität jetzt die Basiseinheit beim Erstellen eines Workflows. Die <xref:System.Activities.Activity>-Klasse stellt die Basisabstraktion des Workflowverhaltens bereit. Aktivitätsautoren können dann <xref:System.Activities.CodeActivity> für eine grundlegende benutzerdefinierte Aktivitätsfunktionalität oder <xref:System.Activities.NativeActivity> für eine benutzerdefinierte Aktivitätsfunktionalität, die alle zur Laufzeit verfügbaren Funktionen verwendet, implementieren. <xref:System.Activities.Activity> ist eine Klasse, die von Aktivitäts Autoren verwendet wird, um neue Verhalten deklarativ in Bezug auf andere-,-,- <xref:System.Activities.NativeActivity> <xref:System.Activities.CodeActivity> <xref:System.Activities.AsyncCodeActivity> oder <xref:System.Activities.DynamicActivity> -Objekte auszudrücken, unabhängig davon, ob Sie Benutzer definiert oder in der [integrierten Aktivitäts Bibliothek](net-framework-4-5-built-in-activity-library.md)enthalten sind.

## <a name="rich-composite-activity-options"></a>Umfangreiche zusammengesetzte Aktivitätsoptionen

 <xref:System.Activities.Statements.Flowchart> ist eine leistungsstarke neue Ablaufsteuerungsaktivität, die es Autoren ermöglicht, beliebige Schleifen und bedingte Verzweigungen zu modellieren. <xref:System.Activities.Statements.Flowchart> stellt ein ereignisgesteuertes Programmiermodell bereit, das zuvor nur mit <xref:System.Workflow.Activities.StateMachineWorkflowActivity> implementiert werden konnte. Verfahrensworkflows profitieren von neuen Flusssteuerungsaktivitäten, die herkömmliche Flusssteuerungsstrukturen modellieren, z. B. <xref:System.Activities.Statements.TryCatch> und <xref:System.Activities.Statements.Switch%601>.

## <a name="expanded-built-in-activity-library"></a>Erweiterte integrierte Aktivitätsbibliothek

 Die Aktivitätsbibliothek bietet u. a. die folgenden neuen Funktionen:

- Neue Flusssteuerungsaktivitäten, z. B. <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.Pick>, <xref:System.Activities.Statements.TryCatch>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Switch%601> und <xref:System.Activities.Statements.ParallelForEach%601>.

- Aktivitäten zum Bearbeiten von Memberdaten, z. B. <xref:System.Activities.Statements.Assign>, sowie Auflistungsaktivitäten, z. B. <xref:System.Activities.Statements.AddToCollection%601>.

- Aktivitäten zum Steuern von Transaktionen, z. B. <xref:System.Activities.Statements.TransactionScope> und <xref:System.Activities.Statements.Compensate>.

- Neue Messagingaktivitäten, z. B. <xref:System.ServiceModel.Activities.SendContent> und <xref:System.ServiceModel.Activities.ReceiveReply>.

## <a name="explicit-activity-data-model"></a>Explizites Aktivitätsdatenmodell

 .NET Framework 4 enthält neue Optionen zum Speichern oder Verschieben von Daten. Daten können mit <xref:System.Activities.Variable> in einer Aktivität gespeichert werden. Beim Verschieben von Daten in und aus einer Aktivität wird mittels spezialisierter Argumenttypen die Verschieberichtung bestimmt. Dies sind die Typen <xref:System.Activities.InArgument>, <xref:System.Activities.InOutArgument> und <xref:System.Activities.OutArgument>. Weitere Informationen finden Sie unter [Windows Workflow Foundation-Datenmodell](data-model.md).

## <a name="enhanced-hosting-persistence-and-tracking-options"></a>Verbesserte Hosting-, Persistenz- und Nachverfolgungsoptionen

 .NET Framework 4 enthält persistenzverbesserungen wie die folgenden:

- Mehr Optionen zum Ausführen von Workflows, darunter <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.Activities.WorkflowApplication> und <xref:System.Activities.WorkflowInvoker>.

- Workflowzustandsdaten können mit der <xref:System.Activities.Statements.Persist>-Aktivität explizit in den Persistenzspeicher verschoben werden.

- Ein Host kann ein <xref:System.Activities.ActivityInstance>-Objekt ohne Entladen in den Persistenzspeicher verschieben.

- Beim Arbeiten mit Daten, die nicht in den Persistenzspeicher verschoben werden können, kann ein Workflow Zonen ohne Persistenz angeben, um den Vorgang zu verschieben, bis die Zone ohne Persistenz beendet wird.

- Das <xref:System.Activities.Statements.TransactionScope>-Objekt ermöglicht den Transaktionsfluss in einen Workflow.

- Die Nachverfolgung wird mit dem <xref:System.Activities.Tracking.TrackingParticipant>-Objekt vereinfacht.

- Die Nachverfolgung im Systemereignisprotokoll wird mit dem <xref:System.Activities.Tracking.EtwTrackingParticipant>-Objekt bereitgestellt.

- Das Fortsetzen ausstehender Workflows kann jetzt mit dem <xref:System.Activities.Bookmark>-Objekt verwaltet werden.

## <a name="easier-ability-to-extend-wf-designer-experience"></a>Vereinfachte Erweiterung der WF-Designer-Umgebung

 Der neue WF-Designer basiert auf Windows Presentation Foundation (WPF) und bietet ein einfacheres Modell, das Sie verwenden können, wenn Sie den WF-Designer außerhalb von Visual Studio neu starten und außerdem einfachere Mechanismen zum Erstellen von benutzerdefinierten Aktivitäts Designern bereitstellen. Weitere Informationen finden Sie unter [Anpassen des Workflow Entwurfs Erlebnisses](customizing-the-workflow-design-experience.md).
