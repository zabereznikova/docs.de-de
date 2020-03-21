---
title: 'Gewusst wie: Hinzufügen von Menüelementen zu einem ContextMenuStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrips [Windows Forms], adding menu items
- shortcut menus [Windows Forms], adding items
- context menus [Windows Forms], adding menu items
ms.assetid: 1ec14776-3ea2-4752-bd22-4fae0fd19e1a
ms.openlocfilehash: 7e3480c5a56170ce94d5b5bde0208542c82e7702
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182310"
---
# <a name="how-to-add-menu-items-to-a-contextmenustrip"></a>Gewusst wie: Hinzufügen von Menüelementen zu einem ContextMenuStrip
Sie können nur ein Menüelement oder mehrere <xref:System.Windows.Forms.ContextMenuStrip>Elemente gleichzeitig zu einem hinzufügen.  
  
### <a name="to-add-a-single-menu-item-to-a-contextmenustrip"></a>So fügen Sie einem ContextMenuStrip ein einzelnes Menüelement hinzu  
  
- Verwenden <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> Sie die Methode, um <xref:System.Windows.Forms.ContextMenuStrip>einem ein Menüelement hinzuzufügen.  
  
    ```vb  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### <a name="to-add-several-menu-items-to-a-contextmenustrip"></a>So fügen Sie einem ContextMenuStrip mehrere Menüelemente hinzu  
  
- Verwenden <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> Sie die Methode, um <xref:System.Windows.Forms.ContextMenuStrip>einer mehrere Menüelemente hinzuzufügen.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [ContextMenuStrip-Steuerelement](contextmenustrip-control.md)
