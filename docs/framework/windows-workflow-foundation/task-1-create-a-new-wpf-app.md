---
title: 'Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 5576d6f893aa405d454758387334b85a473b0c73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517948"
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
