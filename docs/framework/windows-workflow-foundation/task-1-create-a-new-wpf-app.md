---
title: 'Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 533b4a1030ab5f47eb96ca62dc2805eae7933b9b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711885"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a>Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung
In dieser Aufgabe, Sie erstellen eine leere Windows Presentation Foundation (WPF)-Anwendung mithilfe der WPF-Anwendungsvorlage von Visual Studio-Vorlage und fügen Sie Verweise auf die entsprechenden [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] Workflowassemblys.  
  
### <a name="to-create-the-wpf-application-project"></a>So erstellen Sie das WPF-Anwendungsprojekt  
  
1.  Öffnen Sie Visual Studio und klicken Sie auf die **Datei** Startmenü **neu**, und klicken Sie dann auf **Projekt**.  
  
2.  In der **neues Projekt** Dialogfeld wählen **Visual C#**  oder **Visual Basic** aus der **installierte Vorlagen** im linken Bereich die Seite des Felds. Wenn die Sprache Ihrer Wahl nicht angezeigt wird, suchen Sie unter **andere Sprachen**.  
  
3.  Wählen Sie **Windows** in die **installierte Vorlagen** Bereich.  
  
4.  Im oberen Bereich sicher, dass (Standardwert) **.NET Framework 4** wurde, und wählen Sie dann im Dropdown-Listenfeld ausgewählte **WPF-Anwendung**.  
  
5.  Legen Sie den Namen des Projekts, das **HostingApplication** am unteren Rand des Fensters.  
  
6.  Legen Sie den Namen der Projektmappe auf **RehostingTheDesigner**.  
  
7.  Klicken Sie auf **OK** das Anwendungsprojekt zu erstellen. Visual Studio eine einfache WPF-UI für Ihre Anwendung erstellt und enthält die entsprechende XAML und Code-Behind-Dateien.  
  
8.  Fügen Sie Verweise auf **WorkflowModel** Assemblys. Klicken Sie hierzu in **Projektmappen-Explorer**, mit der rechten Maustaste die **HostingApplication** Projekt, und wählen **Verweis hinzufügen**.  
  
9. In der **Verweis hinzufügen** Dialogfeld klicken Sie auf die **.NET** , halten Sie die STRG-Taste gedrückt, wählen Sie die folgenden Assemblys, und klicken Sie dann auf **OK**:  
  
    -   System.Activities  
  
    -   System.Activities.Presentation  
  
    -   System.Activities.Core.Presentation  
  
10. Klicken Sie auf **OK**.  
  
11. Finden Sie unter [Aufgabe 2: Hosten des Workflow-Designers](task-2-host-the-workflow-designer.md) erfahren, wie die Workflow-Designer-Entwurfs-Canvas zu hosten.  
  
## <a name="see-also"></a>Siehe auch
- [Erneutes Hosten des Workflow-Designers](rehosting-the-workflow-designer.md)
- [Task 2: Hosten des Workflowdesigners](task-2-host-the-workflow-designer.md)
