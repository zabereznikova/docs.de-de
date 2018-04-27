---
title: 'Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cd21013331e19fa9e18ad7cbee0a7bb07abaf3d2
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a>Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung
In dieser Aufgabe wird eine leere Windows Presentation Foundation (WPF)-Anwendung mithilfe der WPF-Anwendung Visual Studio-Vorlage erstellen und fügen Sie Verweise auf die entsprechende [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] Workflowassemblys.  
  
### <a name="to-create-the-wpf-application-project"></a>So erstellen Sie das WPF-Anwendungsprojekt  
  
1.  Öffnen Sie Visual Studio und klicken Sie auf die **Datei** Sie im Menü **neu**, und klicken Sie dann auf **Projekt**.  
  
2.  In der **neues Projekt** Dialogfeld wählen **Visual C#-** oder **Visual Basic** aus der **installierte Vorlagen** Bereich auf der linken Seite des das Feld ein. Wenn die Sprache Ihrer Wahl nicht angezeigt wird, suchen Sie unter **andere Sprachen**.  
  
3.  Wählen Sie **Windows** in der **installierte Vorlagen** Bereich.  
  
4.  Vergewissern Sie sich, die im oberen Bereich (Standardwert) **.NET Framework 4** im Dropdown-Listenfeld ausgewählt ist, und wählen Sie dann **WPF-Anwendung**.  
  
5.  Legen Sie den Namen des Projekts, um **HostingApplication** am unteren Rand des Fensters.  
  
6.  Legen Sie den Namen der Projektmappe auf **RehostingTheDesigner**.  
  
7.  Klicken Sie auf **OK** das Anwendungsprojekt zu erstellen. Visual Studio erstellt eine einfache WPF UI für Ihre Anwendung und die entsprechende XAML sowie Code-Behind-Dateien enthält.  
  
8.  Fügen Sie Verweise auf **WorkflowModel** Assemblys. Klicken Sie hierzu in **Projektmappen-Explorer**, mit der rechten Maustaste die **HostingApplication** Projekt, und wählen Sie **Verweis hinzufügen**.  
  
9. In der **Verweis hinzufügen** (Dialogfeld), klicken Sie auf die **.NET** Registerkarte, halten Sie die STRG-Taste, wählen Sie die folgenden Assemblys, und klicken Sie dann auf **OK**:  
  
    -   System.Activities  
  
    -   System.Activities.Presentation  
  
    -   System.Activities.Core.Presentation  
  
10. Klicken Sie auf **OK**.  
  
11. Finden Sie unter [Aufgabe 2: Hosten des Workflow-Designers](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md) Informationen zum Hosten der Designer entwurfszeichnungsbereich des Workflows.  
  
## <a name="see-also"></a>Siehe auch  
 [Erneutes Hosten des Workflow-Designers](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [Aufgabe 2: Hosten des Workflow-Designers](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)
