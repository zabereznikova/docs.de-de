---
title: 'Gewusst wie: Erkennen des Mauszeigers auf einem ToolStripItem'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 15a7562efd9a86a029754610ffd9e77c372d1ac2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a>Gewusst wie: Erkennen des Mauszeigers auf einem ToolStripItem
Verwenden Sie das folgende Verfahren um zu erkennen, wenn der Mauszeiger über ein <xref:System.Windows.Forms.ToolStripItem>.  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a>Erkennen, wenn der Mauszeiger über einem ToolStripItem befindet  
  
-   Verwenden der <xref:System.Windows.Forms.ToolStripItem.Selected%2A> für Elemente in der Eigenschaft <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> ist `true`.  
  
     Dadurch wird verhindert, Sie synchronisieren müssen die <xref:System.Windows.Forms.ToolStripItem.MouseEnter> und <xref:System.Windows.Forms.ToolStripItem.MouseLeave> Ereignisse.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripItem.Selected%2A>  
 [Übersicht über das ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
