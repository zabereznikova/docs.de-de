---
title: Festlegen von Symbolen für das TreeView-Steuerelement
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
ms.openlocfilehash: e3d7fc35c6d9f70822cdd0b69dd12f3d469f4ffa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737263"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>Gewusst wie: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms
Das Windows Forms <xref:System.Windows.Forms.TreeView>-Steuerelement kann Symbole neben den einzelnen Knoten anzeigen. Die Symbole werden direkt links neben dem Knoten Text positioniert. Um diese Symbole anzuzeigen, müssen Sie die Strukturansicht einem <xref:System.Windows.Forms.ImageList>-Steuerelement zuordnen. Weitere Informationen zu Bildlisten finden Sie unter [ImageList-Komponente](imagelist-component-windows-forms.md) und Gewusst [wie: Hinzufügen oder Entfernen von Bildern mit der Windows Forms ImageList-Komponente](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
> [!NOTE]
> Ein Fehler in Microsoft .NET Framework Version 1,1 verhindert, dass Bilder auf <xref:System.Windows.Forms.TreeView> Knoten angezeigt werden, wenn die Anwendung <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>aufruft. Um diesen Fehler zu umgehen, rufen Sie <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> direkt nach dem Aufrufen von <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>in der `Main`-Methode auf. Dieser Fehler wurde in .NET Framework 2,0 behoben.  
  
### <a name="to-display-images-in-a-tree-view"></a>So zeigen Sie Bilder in einer Strukturansicht an  
  
1. Legen Sie die <xref:System.Windows.Forms.TreeView.ImageList%2A>-Eigenschaft des <xref:System.Windows.Forms.TreeView> Steuer Elements auf das vorhandene <xref:System.Windows.Forms.ImageList> Steuerelement fest, das Sie verwenden möchten.  
  
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
  
2. Legen Sie die Eigenschaften des Knotens <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> und <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> fest. Die <xref:System.Windows.Forms.TreeNode.ImageIndex%2A>-Eigenschaft bestimmt das Bild, das für den normalen und erweiterten Status des Knotens angezeigt wird, und die <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A>-Eigenschaft bestimmt das Bild, das für den ausgewählten Knoten des Knotens angezeigt wird.  
  
     Diese Eigenschaften können im Code oder im TreeNode-Editor festgelegt werden. Um den TreeNode-Editor zu öffnen, klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (![der Schaltfläche mit den Auslassungs Punkten (...) im Eigenschaftenfenster von Visual Studio.](./media/visual-studio-ellipsis-button.png)) neben der <xref:System.Windows.Forms.TreeView.Nodes%2A>-Eigenschaft des Eigenschaftenfenster.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über das TreeView-Steuerelement](treeview-control-overview-windows-forms.md)
- [Gewusst wie: Hinzufügen oder Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Gewusst wie: Durchlaufen aller Knoten eines TreeView-Steuerelements in Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Gewusst wie: Ermitteln des per Mausklick ausgewählten TreeView-Knotens](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
