---
title: 'Vorgehensweise: Verwenden von QuickInfos in ToolStrip-Steuerelementen'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 3f383b6cccba7825637ea65a0e13280b91b406c9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939733"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a>Vorgehensweise: Verwenden von QuickInfos in ToolStrip-Steuerelementen
<xref:System.Windows.Forms.ToolTip> Sie können ein-Objekt für <xref:System.Windows.Forms.ToolStrip> das gewünschte Steuerelement anzeigen, indem Sie <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> die- `true`Eigenschaft des-Steuer Elements auf festlegen.  
  
### <a name="to-display-a-tooltip"></a>So zeigen Sie eine QuickInfo an  
  
- Legen Sie <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> die-Eigenschaft des- `true`Steuer Elements auf fest.  
  
     Der Standardwert von <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> ist `true`, und der Standardwert von <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> und <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> ist `false`.  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a>So verwenden Sie die ToolTipText-Eigenschaft für den QuickInfo-Text eines ToolStripButton  
  
1. Legen Sie <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> die-Eigenschaft der Schalt `true`Fläche auf fest.  
  
2. Legen Sie <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> die-Eigenschaft der Schalt `false`Fläche auf fest.  
  
     Die `AutoToolTip` -Eigenschaft `true` ist standardmäßig <xref:System.Windows.Forms.ToolStripButton>für <xref:System.Windows.Forms.ToolStripDropDownButton>, und <xref:System.Windows.Forms.ToolStripSplitButton>.  
  
     Verwendet standardmäßig die- <xref:System.Windows.Forms.ToolTip> EigenschaftfürdenText.`Text` <xref:System.Windows.Forms.ToolStripButton> Verwenden Sie dieses Verfahren, um benutzerdefinierten Text <xref:System.Windows.Forms.ToolStripButton>in einem <xref:System.Windows.Forms.ToolTip>anzuzeigen.  
  
> [!NOTE]
> Wenn Sie auf <xref:System.Windows.Forms.ToolStripItemDisplayStyle> <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> oder<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>festlegen, wird kein Text auf der Schaltfläche angezeigt, aber die QuickInfo wird weiterhin angezeigt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [Übersicht über das ToolStrip-Steuerelement](toolstrip-control-overview-windows-forms.md)
