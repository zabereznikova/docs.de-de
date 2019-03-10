---
title: Erstellen von Workflowaktivitäten mit der Aktivitätsklasse
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: abdabc46aa54e19d5a04c5b34d6d2b9be07488d6
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711862"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a>Erstellen von Workflowaktivitäten mit der Aktivitätsklasse
Die einfachste Möglichkeit zum Erstellen einer Aktivität, die mithilfe von Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] besteht darin, eine Klasse erstellen, die von erbt <xref:System.Activities.Activity> dieses erzeugt Funktionalität durch Zusammenstellen von benutzerdefinierten Aktivitäten oder Aktivitäten aus der [integrierte Aktivitätsbibliothek](net-framework-4-5-built-in-activity-library.md). In diesem Thema wird veranschaulicht, wie eine Aktivität erstellt wird, die zwei Meldungen in die Konsole schreibt.

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a>So erstellen Sie eine benutzerdefinierte Aktivität mit dem Aktivitätsdesigner

1.  Öffnen Sie Visual Studio 2012.

2.  Wählen Sie "Datei", "Neu" und "Projekt" aus. Wählen Sie **Workflow 4.0** unter **Visual C#-** in die **Projekttypen** , und wählen die **v2010** Knoten. Wählen Sie **Aktivitätsbibliothek** in die **Vorlagen** Fenster. Geben Sie dem neuen Projekt den Namen "HelloActivity".

3.  Öffnen Sie die neue Aktivität.  Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität von der Toolbox auf die Designeroberfläche.

4.  Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität in die <xref:System.Activities.Statements.Sequence>-Aktivität. Geben Sie `"Hello World"` (mit Anführungszeichen) in der **Text** Feld.

5.  Ziehen Sie eine zweite <xref:System.Activities.Statements.WriteLine>-Aktivität in die <xref:System.Activities.Statements.Sequence>-Aktivität (unter die erste). Geben Sie `"Goodbye"` (mit Anführungszeichen) in der **Text** Feld.
