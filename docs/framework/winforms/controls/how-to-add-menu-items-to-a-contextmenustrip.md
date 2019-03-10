---
title: 'Vorgehensweise: Hinzufügen von Menüelementen zu einem ContextMenuStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrips [Windows Forms], adding menu items
- shortcut menus [Windows Forms], adding items
- context menus [Windows Forms], adding menu items
ms.assetid: 1ec14776-3ea2-4752-bd22-4fae0fd19e1a
ms.openlocfilehash: a12a201ac73c86bf391d39f47baa47c87bf96095
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716756"
---
# <a name="how-to-add-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="0ed42-102">Vorgehensweise: Hinzufügen von Menüelementen zu einem ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="0ed42-102">How to: Add Menu Items to a ContextMenuStrip</span></span>
<span data-ttu-id="0ed42-103">Sie können nur ein Menüelement oder mehrere Elemente gleichzeitig Hinzufügen einer <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="0ed42-103">You can add just one menu item or several items at a time to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-add-a-single-menu-item-to-a-contextmenustrip"></a><span data-ttu-id="0ed42-104">Ein einzelnes Menüelement zu einem ContextMenuStrip hinzufügen</span><span class="sxs-lookup"><span data-stu-id="0ed42-104">To add a single menu item to a ContextMenuStrip</span></span>  
  
-   <span data-ttu-id="0ed42-105">Verwenden der <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> Methode, um ein Menüelement zum Hinzufügen einer <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="0ed42-105">Use the <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add one menu item to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
    ```vb  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### <a name="to-add-several-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="0ed42-106">Hinzufügen von mehrere Menüelemente zu einem ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="0ed42-106">To add several menu items to a ContextMenuStrip</span></span>  
  
-   <span data-ttu-id="0ed42-107">Verwenden der <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> Methode, um mehrere Menüelemente Hinzufügen einer <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="0ed42-107">Use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> method to add several menu items to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
    ```vb  
    Me.contextMenuStrip1.Items.AddRange(New _  
       System.Windows.Forms.ToolStripItem() {Me.toolStripMenuItem1, _  
          Me.toolStripMenuItem2})  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.AddRange(new   
       System.Windows.Forms.ToolStripItem[] {  
          this.toolStripMenuItem1, this.toolStripMenuItem2});  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0ed42-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ed42-108">See also</span></span>
- [<span data-ttu-id="0ed42-109">ContextMenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0ed42-109">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
