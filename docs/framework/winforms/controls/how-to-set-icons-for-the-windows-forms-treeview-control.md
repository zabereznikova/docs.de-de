---
title: "Gewusst wie: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5abe07a80e457c4a0254b4c1a734cba2f6ed1766
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>Gewusst wie: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms
Windows Forms <xref:System.Windows.Forms.TreeView> -Steuerelement Symbole neben den einzelnen Knoten können angezeigt werden. Die Symbole werden unmittelbar links von den Knotentext positioniert. Um diese Symbole anzuzeigen, müssen Sie die Strukturansicht mit Zuordnen einer <xref:System.Windows.Forms.ImageList> Steuerelement. Weitere Informationen zu Bildlisten, finden Sie unter [ImageList-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) und [wie: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
> [!NOTE]
>  Ein Fehler in Microsoft .NET Framework, Version 1.1 wird verhindert, dass Bilder enthalten sind, auf <xref:System.Windows.Forms.TreeView> Knoten, wenn die Anwendung aufruft <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. Um diesen Fehler zu umgehen, rufen <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in Ihrer `Main` Methode sofort nach dem Aufruf <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>. Dieser Fehler weist ein festes [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
### <a name="to-display-images-in-a-tree-view"></a>Anzeige von Bildern in einer Strukturansicht an  
  
1.  Legen Sie die <xref:System.Windows.Forms.TreeView> des Steuerelements <xref:System.Windows.Forms.TreeView.ImageList%2A> Eigenschaft, um die vorhandene <xref:System.Windows.Forms.ImageList> Steuerelement, die Sie verwenden möchten.  
  
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
  
2.  Legen Sie des Knotens <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> und <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> Eigenschaften. Die <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> Eigenschaft bestimmt, das für den Knoten normalen und erweiterten Status angezeigte Bild und die <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> -Eigenschaft bestimmt das Bild für den ausgewählten Zustand des Knotens angezeigt.  
  
     Diese Eigenschaften können im Code oder innerhalb des TreeNode-Editors festgelegt werden. Um den TreeNode-Editor zu öffnen, klicken Sie auf die Schaltfläche mit den Auslassungspunkten ( ![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben dem <xref:System.Windows.Forms.TreeView.Nodes%2A> Eigenschaft im Eigenschaftenfenster.  
  
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
 [Übersicht über das TreeView-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [Gewusst wie: Hinzufügen oder Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)  
 [Gewusst wie: Durchlaufen aller Knoten eines TreeView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [Gewusst wie: Ermitteln des per Mausklick ausgewählten TreeView-Knotens](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
