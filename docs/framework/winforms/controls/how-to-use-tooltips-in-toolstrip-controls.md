---
title: 'Vorgehensweise: Verwenden von QuickInfos in ToolStrip-Steuerelementen'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 884fb75d53e425702cdef46615a16394b835518f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076472"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a>Vorgehensweise: Verwenden von QuickInfos in ToolStrip-Steuerelementen
Anzeigen einer <xref:System.Windows.Forms.ToolTip> für die <xref:System.Windows.Forms.ToolStrip> Steuerelement durch Festlegen des Steuerelements verwendet werden soll <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> Eigenschaft `true`.  
  
### <a name="to-display-a-tooltip"></a>Um eine QuickInfo anzuzeigen  
  
-   Legen Sie die <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> Eigenschaft des Steuerelements `true`.  
  
     Der Standardwert von <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> ist `true`, und der Standardwert von <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> und <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> ist `false`.  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a>ToolTipText-Eigenschaft für den QuickInfo-Text eines ToolStripButton verwenden  
  
1.  Legen Sie die <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> Eigenschaft der Schaltfläche auf `true`.  
  
2.  Legen Sie die <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> Eigenschaft der Schaltfläche auf `false`.  
  
     Die `AutoToolTip` Eigenschaft `true` standardmäßig für <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, und <xref:System.Windows.Forms.ToolStripSplitButton>.  
  
     Ein <xref:System.Windows.Forms.ToolStripButton> verwendet die `Text` -Eigenschaft für die <xref:System.Windows.Forms.ToolTip> Text standardmäßig. Verwenden Sie dieses Verfahren zum Anzeigen von benutzerdefinierten Texts in einem <xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>.  
  
> [!NOTE]
>  Setzen Sie <xref:System.Windows.Forms.ToolStripItemDisplayStyle> zu <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> oder <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, auf die Schaltfläche wird kein Text angezeigt, aber die QuickInfo immer noch angezeigt wird.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [Übersicht über das ToolStrip-Steuerelement](toolstrip-control-overview-windows-forms.md)
