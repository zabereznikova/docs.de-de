---
title: 'Vorgehensweise: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 515ff2bd4ab0f4fa93eada61396bd45c587cded6
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703568"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>Vorgehensweise: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms
Die Windows-Formulare <xref:System.Windows.Forms.TreeView> -Steuerelement Symbole neben den einzelnen Knoten können angezeigt werden. Die Symbole werden unmittelbar links neben den Knotentext positioniert. Um diese Symbole anzuzeigen, müssen Sie in der Strukturansicht mit Zuordnen einer <xref:System.Windows.Forms.ImageList> Steuerelement. Weitere Informationen zu Bildlisten, finden Sie unter [ImageList-Komponente](imagelist-component-windows-forms.md) und [Vorgehensweise: Hinzufügen oder Entfernen von Bildern mit der Windows Forms ImageList-Komponente](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
> [!NOTE]
>  Ein Fehler in Microsoft .NET Framework, Version 1.1 wird verhindert, dass es sich bei Bildern aus <xref:System.Windows.Forms.TreeView> Knoten aus, wenn die Anwendung aufruft <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. Um dieses Problem zu umgehen, rufen Sie <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in Ihre `Main` Methode sofort nach dem Aufruf <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>. Dieses Problem wurde behoben, im [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
### <a name="to-display-images-in-a-tree-view"></a>Zum Anzeigen von Bildern in einer Strukturansicht  
  
1.  Legen Sie die <xref:System.Windows.Forms.TreeView> des Steuerelements <xref:System.Windows.Forms.TreeView.ImageList%2A> Eigenschaft, um die vorhandene <xref:System.Windows.Forms.ImageList> Kontrolle, die Sie verwenden möchten.  
  
     Diese Eigenschaften können im Designer mit dem Fenster "Eigenschaften" oder im Code festgelegt werden.  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2.  Festlegen des Knotens <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> und <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> Eigenschaften. Die <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> Eigenschaft bestimmt, das für den normalen und erweiterten Status des Knotens angezeigte Bild und die <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> Eigenschaft bestimmt, das für den ausgewählten Zustand des Knotens angezeigte Bild.  
  
     Diese Eigenschaften können im Code oder in der TreeNode-Editor festgelegt werden. Um die TreeNode-Editor zu öffnen, klicken Sie auf die Schaltfläche mit den Auslassungspunkten ( ![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png "VbEllipsesButton")) neben dem <xref:System.Windows.Forms.TreeView.Nodes%2A> Eigenschaft im Eigenschaftenfenster.  
  
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
- [Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Vorgehensweise: Durchlaufen Sie aller Knoten eines Windows Forms TreeView-Steuerelements](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Vorgehensweise: Ermitteln des per Mausklick ausgewählten TreeView-Knotens](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
