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
ms.openlocfilehash: d960eaae2aa479e0be74e9a5e4fdbfec8ff411c1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182176"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>Gewusst wie: Ermitteln des per Mausklick ausgewählten TreeView-Knotens (Windows Forms)
Bei der Arbeit <xref:System.Windows.Forms.TreeView> mit dem Windows Forms-Steuerelement besteht eine häufige Aufgabe darin, zu bestimmen, auf welchen Knoten geklickt wurde, und entsprechend zu reagieren.  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>So bestimmen Sie, auf welchen TreeView-Knoten geklickt wurde  
  
1. Verwenden <xref:System.EventArgs> Sie das Objekt, um einen Verweis auf das angeklickte Knotenobjekt zurückzugeben.  
  
2. Bestimmen Sie, auf welchen <xref:System.Windows.Forms.TreeViewEventArgs> Knoten geklickt wurde, indem Sie die Klasse überprüfen, die Daten enthält, die sich auf das Ereignis beziehen.  
  
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
    > Alternativ <xref:System.Windows.Forms.MouseEventArgs> können Sie die des <xref:System.Windows.Forms.Control.MouseDown> oder-Ereignisses <xref:System.Windows.Forms.Control.MouseUp> <xref:System.Drawing.Point.X%2A> verwenden, um die Und-Koordinaten-Werte <xref:System.Drawing.Point.Y%2A> des <xref:System.Drawing.Point> Ortes abzudateien, an dem der Klick aufgetreten ist. Verwenden Sie <xref:System.Windows.Forms.TreeView> dann die <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> Methode des Steuerelements, um zu bestimmen, auf welchen Knoten geklickt wurde.  
  
## <a name="see-also"></a>Weitere Informationen

- [TreeView-Steuerelement](treeview-control-windows-forms.md)
