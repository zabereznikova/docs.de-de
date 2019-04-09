---
title: 'Vorgehensweise: Bestimmen der Mausklick ausgewählten TreeView-Knotens (Windows Forms)'
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
ms.openlocfilehash: 073b953d2a39b27081020c56399ea3beae2083e5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189572"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>Vorgehensweise: Bestimmen der Mausklick ausgewählten TreeView-Knotens (Windows Forms)
Bei der Arbeit mit der Windows Forms <xref:System.Windows.Forms.TreeView> -Steuerelement, eine häufige Aufgabe besteht darin zu bestimmen, welcher Knoten auf den geklickt wurde, und entsprechend reagieren.  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>Zum Ermitteln des per Mausklick ausgewählten TreeView-Knotens  
  
1.  Verwenden der <xref:System.EventArgs> Objekts, das einen Verweis auf das geklickt wurde Node-Objekt zurückgegeben.  
  
2.  Bestimmen, welche Knoten geklickt wurde, indem Sie überprüfen die <xref:System.Windows.Forms.TreeViewEventArgs> -Klasse, die Daten, die im Zusammenhang mit der das Ereignis enthält.  
  
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
    >  Als Alternative können Sie die <xref:System.Windows.Forms.MouseEventArgs> von der <xref:System.Windows.Forms.Control.MouseDown> oder <xref:System.Windows.Forms.Control.MouseUp> abzurufenden Ereignisses die <xref:System.Drawing.Point.X%2A> und <xref:System.Drawing.Point.Y%2A> -Koordinatenwerte von der <xref:System.Drawing.Point> , an der geklickt wurde. Verwenden Sie dann die <xref:System.Windows.Forms.TreeView> des Steuerelements <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> Methode, um zu bestimmen, welcher Knoten geklickt wurde.  
  
## <a name="see-also"></a>Siehe auch

- [TreeView-Steuerelement](treeview-control-windows-forms.md)
