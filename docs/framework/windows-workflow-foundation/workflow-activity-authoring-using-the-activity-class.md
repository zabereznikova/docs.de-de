---
title: Erstellen von Workflowaktivitäten mit der Aktivitätsklasse
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 21f1c8b1249d41029fa7a19360e96ad866c823a7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293844"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a>Erstellen von Workflowaktivitäten mit der Aktivitätsklasse

Die einfachste Möglichkeit zum Erstellen einer Aktivität mithilfe von Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] besteht darin, eine Klasse zu erstellen, die von erbt, die durch das Zusammenstellen von <xref:System.Activities.Activity> benutzerdefinierten Aktivitäten oder Aktivitäten aus der [integrierten Aktivitäts Bibliothek](net-framework-4-5-built-in-activity-library.md)eine Funktionalität erstellt. In diesem Thema wird veranschaulicht, wie eine Aktivität erstellt wird, die zwei Meldungen in die Konsole schreibt.

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a>So erstellen Sie eine benutzerdefinierte Aktivität mit dem Aktivitätsdesigner

1. Öffnen Sie Visual Studio 2012.

2. Wählen Sie "Datei", "Neu" und "Projekt" aus. Wählen Sie im Fenster **Projekttypen** unter **Visual c#** die Option **Workflow 4,0** aus, und wählen Sie den Knoten **v2010** aus. Wählen Sie im Fenster **Vorlagen** die Option **Aktivitäts Bibliothek** aus. Geben Sie dem neuen Projekt den Namen "HelloActivity".

3. Öffnen Sie die neue Aktivität.  Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität von der Toolbox auf die Designeroberfläche.

4. Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität in die <xref:System.Activities.Statements.Sequence>-Aktivität. Geben Sie `"Hello World"` (mit Anführungszeichen) in das **Textfeld** ein.

5. Ziehen Sie eine zweite <xref:System.Activities.Statements.WriteLine>-Aktivität in die <xref:System.Activities.Statements.Sequence>-Aktivität (unter die erste). Geben Sie `"Goodbye"` (mit Anführungszeichen) in das **Textfeld** ein.
