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
ms.openlocfilehash: 802367c26562d1b5aaf2398ed122cb97afbff255
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580110"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a><span data-ttu-id="37577-102">Vorgehensweise: Bestimmen der Mausklick ausgewählten TreeView-Knotens (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="37577-102">How to: Determine Which TreeView Node Was Clicked (Windows Forms)</span></span>
<span data-ttu-id="37577-103">Bei der Arbeit mit der Windows Forms <xref:System.Windows.Forms.TreeView> -Steuerelement, eine häufige Aufgabe besteht darin zu bestimmen, welcher Knoten auf den geklickt wurde, und entsprechend reagieren.</span><span class="sxs-lookup"><span data-stu-id="37577-103">When working with the Windows Forms <xref:System.Windows.Forms.TreeView> control, a common task is to determine which node was clicked, and respond appropriately.</span></span>  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a><span data-ttu-id="37577-104">Zum Ermitteln des per Mausklick ausgewählten TreeView-Knotens</span><span class="sxs-lookup"><span data-stu-id="37577-104">To determine which TreeView node was clicked</span></span>  
  
1.  <span data-ttu-id="37577-105">Verwenden der <xref:System.EventArgs> Objekts, das einen Verweis auf das geklickt wurde Node-Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="37577-105">Use the <xref:System.EventArgs> object to return a reference to the clicked node object.</span></span>  
  
2.  <span data-ttu-id="37577-106">Bestimmen, welche Knoten geklickt wurde, indem Sie überprüfen die <xref:System.Windows.Forms.TreeViewEventArgs> -Klasse, die Daten, die im Zusammenhang mit der das Ereignis enthält.</span><span class="sxs-lookup"><span data-stu-id="37577-106">Determine which node was clicked by checking the <xref:System.Windows.Forms.TreeViewEventArgs> class, which contains data related to the event.</span></span>  
  
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
    >  <span data-ttu-id="37577-107">Als Alternative können Sie die <xref:System.Windows.Forms.MouseEventArgs> von der <xref:System.Windows.Forms.Control.MouseDown> oder <xref:System.Windows.Forms.Control.MouseUp> abzurufenden Ereignisses die <xref:System.Drawing.Point.X%2A> und <xref:System.Drawing.Point.Y%2A> -Koordinatenwerte von der <xref:System.Drawing.Point> , an der geklickt wurde.</span><span class="sxs-lookup"><span data-stu-id="37577-107">As an alternative, you can use the <xref:System.Windows.Forms.MouseEventArgs> of the <xref:System.Windows.Forms.Control.MouseDown> or <xref:System.Windows.Forms.Control.MouseUp> event to get the <xref:System.Drawing.Point.X%2A> and <xref:System.Drawing.Point.Y%2A> coordinate values of the <xref:System.Drawing.Point> where the click occurred.</span></span> <span data-ttu-id="37577-108">Verwenden Sie dann die <xref:System.Windows.Forms.TreeView> des Steuerelements <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> Methode, um zu bestimmen, welcher Knoten geklickt wurde.</span><span class="sxs-lookup"><span data-stu-id="37577-108">Then, use the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> method to determine which node was clicked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37577-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37577-109">See also</span></span>
- [<span data-ttu-id="37577-110">TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="37577-110">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
