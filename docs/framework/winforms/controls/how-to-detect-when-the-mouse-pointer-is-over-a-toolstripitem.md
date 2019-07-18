---
title: 'Vorgehensweise: Erkennen des Mauszeigers auf einem ToolStripItem'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: f01a9acb3a566be40d65fb075c8487d4e9cb6e73
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623639"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a>Vorgehensweise: Erkennen des Mauszeigers auf einem ToolStripItem
Verwenden Sie das folgende Verfahren, um die erkennen, wenn der Mauszeiger über einem <xref:System.Windows.Forms.ToolStripItem>.  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a>Erkennen, wenn der Mauszeiger über einem ToolStripItem befindet  
  
- Verwenden der <xref:System.Windows.Forms.ToolStripItem.Selected%2A> -Eigenschaft für Elemente, in denen <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> ist `true`.  
  
     Dies hindert Sie synchronisieren müssen dem <xref:System.Windows.Forms.ToolStripItem.MouseEnter> und <xref:System.Windows.Forms.ToolStripItem.MouseLeave> Ereignisse.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [Übersicht über das ToolStrip-Steuerelement](toolstrip-control-overview-windows-forms.md)
