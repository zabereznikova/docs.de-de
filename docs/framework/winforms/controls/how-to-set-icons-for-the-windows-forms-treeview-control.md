---
title: 'Vorgehensweise: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
ms.openlocfilehash: 451f9ab2b35ad1fbbe9401dacbc8aab44e302701
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909811"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>Vorgehensweise: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms
Das Windows Forms <xref:System.Windows.Forms.TreeView> Steuerelement kann Symbole neben den einzelnen Knoten anzeigen. Die Symbole werden direkt links neben dem Knoten Text positioniert. Um diese Symbole anzuzeigen, müssen Sie die Strukturansicht einem <xref:System.Windows.Forms.ImageList> -Steuerelement zuordnen. Weitere Informationen zu Bildlisten finden Sie unter [ImageList](imagelist-component-windows-forms.md) -Komponente [und Gewusst wie: Hinzufügen oder Entfernen von Bildern mit der Windows Forms ImageList-Komponente](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
> [!NOTE]
> Ein Fehler in Microsoft .NET Framework-Version 1,1 verhindert, dass Bilder <xref:System.Windows.Forms.TreeView> auf Knoten angezeigt werden, <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>wenn die Anwendung aufruft. Um diesen Fehler zu umgehen, rufen <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> Sie direkt `Main` nach dem Aufrufen <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>von in ihrer-Methode auf. Dieser Fehler wurde in .NET Framework 2,0 behoben.  
  
### <a name="to-display-images-in-a-tree-view"></a>So zeigen Sie Bilder in einer Strukturansicht an  
  
1. Legen Sie <xref:System.Windows.Forms.TreeView> die- <xref:System.Windows.Forms.TreeView.ImageList%2A> Eigenschaft des Steuer Elements <xref:System.Windows.Forms.ImageList> auf das vorhandene Steuerelement fest, das Sie verwenden möchten.  
  
     Diese Eigenschaften können im Designer mit dem Eigenschaftenfenster oder im Code festgelegt werden.  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. Legen Sie die Eigenschaften <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> und <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> des Knotens fest. Die <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> -Eigenschaft bestimmt das Bild, das für den normalen und erweiterten Status des Knotens <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> angezeigt wird, und die-Eigenschaft bestimmt das Bild, das für den ausgewählten Status des Knotens angezeigt wird.  
  
     Diese Eigenschaften können im Code oder im TreeNode-Editor festgelegt werden. Um den TreeNode-Editor zu öffnen, klicken Sie auf die ![Schaltfläche mit den Auslassungs Zeichen (...) im Eigenschaftenfenster von Visual](./media/visual-studio-ellipsis-button.png)Studio.) neben <xref:System.Windows.Forms.TreeView.Nodes%2A> der-Eigenschaft auf der Eigenschaftenfenster.  
  
    ```vb  
    ' (Assumes that ImageList1 contains at least two images and  
    ' the TreeView control contains a selected image.)  
    TreeView1.SelectedNode.ImageIndex = 0  
    TreeView1.SelectedNode.SelectedImageIndex = 1  
    ```  
  
    ```csharp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1.SelectedNode.ImageIndex = 0;  
    treeView1.SelectedNode.SelectedImageIndex = 1;  
    ```  
  
    ```cpp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1->SelectedNode->ImageIndex = 0;  
    treeView1->SelectedNode->SelectedImageIndex = 1;  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über das TreeView-Steuerelement](treeview-control-overview-windows-forms.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem Windows Forms TreeView-Steuerelement](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Vorgehensweise: Iterieren aller Knoten eines Windows Forms TreeView-Steuer Elements](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Vorgehensweise: Ermitteln, auf welchen TreeView-Knoten geklickt wurde](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Vorgehensweise: Hinzufügen von benutzerdefinierten Informationen zu einem TreeView-oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
