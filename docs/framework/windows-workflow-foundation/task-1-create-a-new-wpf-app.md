---
title: 'Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a207b09ff7124bb161678627f365a6fa4021a38d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a>Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung
In dieser Aufgabe erstellen Sie eine leere [!INCLUDE[avalon1](../../../includes/avalon1-md.md)]-Anwendung mithilfe der WPF-Anwendungsvorlage von Visual Studio und fügen Verweise auf die entsprechenden [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]-Workflowassemblys hinzu.  
  
### <a name="to-create-the-wpf-application-project"></a>So erstellen Sie das WPF-Anwendungsprojekt  
  
1.  Open [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] und klicken Sie auf die **Datei** Sie im Menü **neu**, und klicken Sie dann auf **Projekt**.  
  
2.  In der **neues Projekt** Dialogfeld wählen **Visual C#-** oder **Visual Basic** aus der **installierte Vorlagen** Bereich auf der linken Seite des das Feld ein. Wenn die Sprache Ihrer Wahl nicht angezeigt wird, suchen Sie unter **andere Sprachen**.  
  
3.  Wählen Sie **Windows** in der **installierte Vorlagen** Bereich.  
  
4.  Vergewissern Sie sich, die im oberen Bereich (Standardwert) **.NET Framework 4** im Dropdown-Listenfeld ausgewählt ist, und wählen Sie dann **WPF-Anwendung**.  
  
5.  Legen Sie den Namen des Projekts, um **HostingApplication** am unteren Rand des Fensters.  
  
6.  Legen Sie den Namen der Projektmappe auf **RehostingTheDesigner**.  
  
7.  Klicken Sie auf **OK** das Anwendungsprojekt zu erstellen. [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] erstellt eine einfache WPF-Benutzeroberfläche für Ihre Anwendung und fügt die entsprechende XAML sowie Code-Behind-Dateien hinzu.  
  
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
