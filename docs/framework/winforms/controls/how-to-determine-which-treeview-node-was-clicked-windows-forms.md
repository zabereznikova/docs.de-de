---
title: 'Gewusst wie: Ermitteln des per Mausklick ausgewählten TreeView-Knotens'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TreeNode
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- tree nodes in TreeView control [Windows Forms], determining node clicked
- TreeView control [Windows Forms], determining node clicked
ms.assetid: 06a4a191-d918-42af-9f49-956c93eff261
ms.openlocfilehash: 7a0e2b69bbec0eb03d40bee2c8e2d4bc9c3558f9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742013"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>Gewusst wie: Ermitteln des per Mausklick ausgewählten TreeView-Knotens (Windows Forms)
Beim Arbeiten mit dem Windows Forms <xref:System.Windows.Forms.TreeView>-Steuerelement besteht eine gängige Aufgabe darin, zu ermitteln, auf welchen Knoten geklickt wurde, und entsprechend zu reagieren.  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>So bestimmen Sie, auf welchen TreeView-Knoten geklickt wurde  
  
1. Verwenden Sie das <xref:System.EventArgs>-Objekt, um einen Verweis auf das angeklickte Knoten Objekt zurückzugeben.  
  
2. Bestimmen Sie, auf welchen Knoten geklickt wurde, indem Sie die <xref:System.Windows.Forms.TreeViewEventArgs>-Klasse überprüfen, die auf das ereignisbezogene Daten enthält.  
  
    ```vb  
    Private Sub TreeView1_AfterSelect(ByVal sender As System.Object, _  
    ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       ' Determine by checking the Node property of the TreeViewEventArgs.  
       MessageBox.Show(e.Node.Text)  
    End Sub  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,   
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       // Determine by checking the Text property.  
       MessageBox.Show(e.Node.Text);  
    }  
    ```  
  
    ```cpp  
    private:  
       void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          // Determine by checking the Text property.  
          MessageBox::Show(e->Node->Text);  
       }  
    ```  
  
    > [!NOTE]
    > Als Alternative können Sie den <xref:System.Windows.Forms.MouseEventArgs> des <xref:System.Windows.Forms.Control.MouseDown> oder <xref:System.Windows.Forms.Control.MouseUp> Ereignisses verwenden, um die <xref:System.Drawing.Point.X%2A> und <xref:System.Drawing.Point.Y%2A> Koordinaten Werte des <xref:System.Drawing.Point> zu erhalten, in dem der Klick aufgetreten ist. Verwenden Sie dann die <xref:System.Windows.Forms.TreeView.GetNodeAt%2A>-Methode des <xref:System.Windows.Forms.TreeView>-Steuer Elements, um zu ermitteln, auf welchen Knoten geklickt wurde.  
  
## <a name="see-also"></a>Weitere Informationen

- [TreeView-Steuerelement](treeview-control-windows-forms.md)
