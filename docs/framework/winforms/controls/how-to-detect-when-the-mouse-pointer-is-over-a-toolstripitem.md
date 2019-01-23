---
title: 'Vorgehensweise: Erkennen Sie, wenn der Mauszeiger über einem ToolStripItem'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 20fbc91773f431fc68f606f8aa9f24f4c0cc06bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539596"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a>Vorgehensweise: Erkennen Sie, wenn der Mauszeiger über einem ToolStripItem
Verwenden Sie das folgende Verfahren, um die erkennen, wenn der Mauszeiger über einem <xref:System.Windows.Forms.ToolStripItem>.  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a>Erkennen, wenn der Mauszeiger über einem ToolStripItem befindet  
  
-   Verwenden der <xref:System.Windows.Forms.ToolStripItem.Selected%2A> -Eigenschaft für Elemente, in denen <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> ist `true`.  
  
     Dies hindert Sie synchronisieren müssen dem <xref:System.Windows.Forms.ToolStripItem.MouseEnter> und <xref:System.Windows.Forms.ToolStripItem.MouseLeave> Ereignisse.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [Übersicht über das ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
