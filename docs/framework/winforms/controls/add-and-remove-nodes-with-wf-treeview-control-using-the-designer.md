---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: 3407b4636a9b9a6074a3721ee185504d8e6c0210
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2019
ms.locfileid: "56304920"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a>Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms mithilfe des Designers
Da die Windows Forms <xref:System.Windows.Forms.TreeView> Steuerelement Knoten auf hierarchische Weise angezeigt, beim Hinzufügen eines Knotens muss darauf geachtet werden, was mit seinem übergeordneten Knoten ist.  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.TreeView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-or-remove-nodes-in-the-designer"></a>Hinzufügen oder Entfernen von Knoten im designer  
  
1.  Wählen Sie das <xref:System.Windows.Forms.TreeView>-Steuerelement.  
  
2.  In der **Eigenschaften** Fenster, klicken Sie auf die **Auslassungspunkte** (![VisualStudioEllipsesButton-bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben die <xref:System.Windows.Forms.TreeView.Nodes%2A> Eigenschaft.  
  
     Die **TreeNode-Editor** angezeigt wird.  
  
3.  Zum Hinzufügen von Knoten muss ein Stammknoten vorhanden. Wenn Sie noch nicht vorhanden ist, müssen Sie zunächst einen Stamm hinzufügen, indem Sie auf die **Stamm hinzufügen** Schaltfläche. Anschließend können Sie untergeordnete Knoten hinzufügen, indem die Stamm- oder einem anderen Knoten und dann auf die **untergeordnetes Element hinzufügen** Schaltfläche.  
  
4.  Zum Löschen von Knoten, wählen Sie den Knoten löschen, und klicken Sie dann auf die **löschen** Schaltfläche.  
  
## <a name="see-also"></a>Siehe auch
- [TreeView-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
- [Übersicht über das TreeView-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)
- [Vorgehensweise: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Vorgehensweise: Durchlaufen Sie aller Knoten eines Windows Forms TreeView-Steuerelements](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Vorgehensweise: Ermitteln des per Mausklick ausgewählten TreeView-Knotens](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
