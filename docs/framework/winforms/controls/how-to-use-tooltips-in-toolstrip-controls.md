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
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a><span data-ttu-id="d39cd-102">Vorgehensweise: Verwenden von QuickInfos in ToolStrip-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="d39cd-102">How to: Use ToolTips in ToolStrip Controls</span></span>
<span data-ttu-id="d39cd-103"><xref:System.Windows.Forms.ToolTip> Sie können ein-Objekt für <xref:System.Windows.Forms.ToolStrip> das gewünschte Steuerelement anzeigen, indem Sie <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> die- `true`Eigenschaft des-Steuer Elements auf festlegen.</span><span class="sxs-lookup"><span data-stu-id="d39cd-103">You can display a <xref:System.Windows.Forms.ToolTip> for the <xref:System.Windows.Forms.ToolStrip> control you want by setting the control's <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property to `true`.</span></span>  
  
### <a name="to-display-a-tooltip"></a><span data-ttu-id="d39cd-104">So zeigen Sie eine QuickInfo an</span><span class="sxs-lookup"><span data-stu-id="d39cd-104">To display a ToolTip</span></span>  
  
- <span data-ttu-id="d39cd-105">Legen Sie <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> die-Eigenschaft des- `true`Steuer Elements auf fest.</span><span class="sxs-lookup"><span data-stu-id="d39cd-105">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the control to `true`.</span></span>  
  
     <span data-ttu-id="d39cd-106">Der Standardwert von <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> ist `true`, und der Standardwert von <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> und <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> ist `false`.</span><span class="sxs-lookup"><span data-stu-id="d39cd-106">The default value of <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `true`, and the default value of <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `false`.</span></span>  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a><span data-ttu-id="d39cd-107">So verwenden Sie die ToolTipText-Eigenschaft für den QuickInfo-Text eines ToolStripButton</span><span class="sxs-lookup"><span data-stu-id="d39cd-107">To use the ToolTipText property for the ToolTip text of a ToolStripButton</span></span>  
  
1. <span data-ttu-id="d39cd-108">Legen Sie <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> die-Eigenschaft der Schalt `true`Fläche auf fest.</span><span class="sxs-lookup"><span data-stu-id="d39cd-108">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the button to `true`.</span></span>  
  
2. <span data-ttu-id="d39cd-109">Legen Sie <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> die-Eigenschaft der Schalt `false`Fläche auf fest.</span><span class="sxs-lookup"><span data-stu-id="d39cd-109">Set the <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> property of the button to `false`.</span></span>  
  
     <span data-ttu-id="d39cd-110">Die `AutoToolTip` -Eigenschaft `true` ist standardmäßig <xref:System.Windows.Forms.ToolStripButton>für <xref:System.Windows.Forms.ToolStripDropDownButton>, und <xref:System.Windows.Forms.ToolStripSplitButton>.</span><span class="sxs-lookup"><span data-stu-id="d39cd-110">The `AutoToolTip` property is `true` by default for <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, and <xref:System.Windows.Forms.ToolStripSplitButton>.</span></span>  
  
     <span data-ttu-id="d39cd-111">Verwendet standardmäßig die- <xref:System.Windows.Forms.ToolTip> EigenschaftfürdenText.`Text` <xref:System.Windows.Forms.ToolStripButton></span><span class="sxs-lookup"><span data-stu-id="d39cd-111">A <xref:System.Windows.Forms.ToolStripButton> uses its `Text` property for the <xref:System.Windows.Forms.ToolTip> text by default.</span></span> <span data-ttu-id="d39cd-112">Verwenden Sie dieses Verfahren, um benutzerdefinierten Text <xref:System.Windows.Forms.ToolStripButton>in einem <xref:System.Windows.Forms.ToolTip>anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d39cd-112">Use this procedure to display custom text in a <xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d39cd-113">Wenn Sie auf <xref:System.Windows.Forms.ToolStripItemDisplayStyle> <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> oder<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>festlegen, wird kein Text auf der Schaltfläche angezeigt, aber die QuickInfo wird weiterhin angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d39cd-113">If you set <xref:System.Windows.Forms.ToolStripItemDisplayStyle> to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no text will appear on the button, but the tool tip still appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d39cd-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d39cd-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [<span data-ttu-id="d39cd-115">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d39cd-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
