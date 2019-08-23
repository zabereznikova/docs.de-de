---
title: 'Vorgehensweise: Ermitteln, auf welchen TreeView-Knoten geklickt wurde (Windows Forms)'
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
ms.openlocfilehash: ab93158daf987e2f19516b8fb3abf80bfe79a12c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967345"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>Vorgehensweise: Ermitteln, auf welchen TreeView-Knoten geklickt wurde (Windows Forms)
Beim Arbeiten mit dem Windows Forms <xref:System.Windows.Forms.TreeView> -Steuerelement besteht eine gängige Aufgabe darin, zu ermitteln, auf welchen Knoten geklickt wurde, und entsprechend zu reagieren.  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>So bestimmen Sie, auf welchen TreeView-Knoten geklickt wurde  
  
1. Verwenden Sie <xref:System.EventArgs> das-Objekt, um einen Verweis auf das angeklickte Knoten Objekt zurückzugeben.  
  
2. Bestimmen Sie, auf welchen Knoten geklickt wurde <xref:System.Windows.Forms.TreeViewEventArgs> , indem Sie die-Klasse überprüfen, die auf das ereignisbezogene Daten enthält.  
  
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
    > Als Alternative können <xref:System.Windows.Forms.MouseEventArgs> Sie den <xref:System.Windows.Forms.Control.MouseDown> des-Ereignisses oder <xref:System.Windows.Forms.Control.MouseUp> das-Ereignis verwenden <xref:System.Drawing.Point> , um <xref:System.Drawing.Point.X%2A> die <xref:System.Drawing.Point.Y%2A> -und-Koordinaten Werte des-Werts zu erhalten, in dem der Klick aufgetreten ist. Verwenden Sie dann die <xref:System.Windows.Forms.TreeView> - <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> Methode des Steuer Elements, um zu ermitteln, auf welchen Knoten geklickt wurde.  
  
## <a name="see-also"></a>Siehe auch

- [TreeView-Steuerelement](treeview-control-windows-forms.md)
