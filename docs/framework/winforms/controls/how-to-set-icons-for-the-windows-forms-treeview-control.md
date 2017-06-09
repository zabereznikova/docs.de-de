---
title: "Gewusst wie: Festlegen von Symbolen f&#252;r das TreeView-Steuerelement in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Beispiele [Windows Forms], TreeView-Steuerelement"
  - "Symbole, Festlegen für das TreeView-Steuerelement"
  - "ImageList-Komponente [Windows Forms], Hinzufügen von Grafiken"
  - "Strukturknoten im TreeView-Steuerelement, Symbole"
  - "TreeView-Steuerelement [Windows Forms], Knotensymbole"
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Gewusst wie: Festlegen von Symbolen f&#252;r das TreeView-Steuerelement in Windows&#160;Forms
Mit dem <xref:System.Windows.Forms.TreeView>\-Steuerelement in Windows Forms können neben jedem Knoten Symbole angezeigt werden.  Die Symbole werden unmittelbar links neben dem Knotentext positioniert.  Die Strukturansicht muss mit einem <xref:System.Windows.Forms.ImageList>\-Steuerelement verbunden werden, um diese Symbole anzuzeigen.  Weitere Informationen über Bildlisten finden Sie unter [ImageList\-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) und [Gewusst wie: Hinzufügen oder Entfernen von Bildern mit der ImageList\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
> [!NOTE]
>  Ein Fehler in Microsoft .NET Framework Version 1.1 verhindert, dass beim Aufrufen von <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName> durch die Anwendung Bilder an <xref:System.Windows.Forms.TreeView>\-Knoten angezeigt werden.  Um diesen Fehler zu umgehen, rufen Sie nach dem Aufrufen von <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> sofort <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName> in Ihrer `Main`\-Methode auf.  Dieser Fehler wird in [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] behoben.  
  
### So zeigen Sie Bilder in einer Strukturansicht an  
  
1.  Legen Sie für die <xref:System.Windows.Forms.TreeView.ImageList%2A>\-Eigenschaft des <xref:System.Windows.Forms.TreeView>\-Steuerelements das vorhandene <xref:System.Windows.Forms.ImageList>\-Steuerelement fest, das Sie verwenden möchten.  
  
     Diese Eigenschaften können entweder im Eigenschaftenfenster des Designers oder programmgesteuert festgelegt werden.  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2.  Legen Sie die Eigenschaften <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> und <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> des Knotens fest.  Mit der <xref:System.Windows.Forms.TreeNode.ImageIndex%2A>\-Eigenschaft können die Bilder bestimmt werden, die im normalen und erweiterten Zustand des Knotens angezeigt werden. Dagegen wird mit der <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A>\-Eigenschaft bestimmt, welches Bild im aktivierten Zustand des Knotens angezeigt wird.  
  
     Diese Eigenschaften können entweder programmgesteuert oder innerhalb des TreeNode\-Editors festgelegt werden.  Klicken Sie im Eigenschaftenfenster neben der <xref:System.Windows.Forms.TreeView.Nodes%2A>\-Eigenschaft auf die Schaltfläche mit drei Punkten \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), um den TreeNode\-Editor zu öffnen.  
  
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
  
## Siehe auch  
 [Übersicht über das TreeView\-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)   
 [Gewusst wie: Hinzufügen oder Entfernen von Knoten mit dem TreeView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)   
 [Gewusst wie: Durchlaufen aller Knoten eines TreeView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)   
 [Gewusst wie: Ermitteln des per Mausklick ausgewählten TreeView\-Knotens](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)   
 [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView\- oder ListView\-Steuerelement \(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)