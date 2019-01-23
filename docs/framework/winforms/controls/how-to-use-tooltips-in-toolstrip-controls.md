---
title: 'Vorgehensweise: Verwenden von QuickInfos in ToolStrip-Steuerelementen'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 60d024dcb023b3d6cfafb68263291acefb38e14a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519161"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a><span data-ttu-id="f070f-102">Vorgehensweise: Verwenden von QuickInfos in ToolStrip-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="f070f-102">How to: Use ToolTips in ToolStrip Controls</span></span>
<span data-ttu-id="f070f-103">Anzeigen einer <xref:System.Windows.Forms.ToolTip> für die <xref:System.Windows.Forms.ToolStrip> Steuerelement durch Festlegen des Steuerelements verwendet werden soll <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="f070f-103">You can display a <xref:System.Windows.Forms.ToolTip> for the <xref:System.Windows.Forms.ToolStrip> control you want by setting the control's <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property to `true`.</span></span>  
  
### <a name="to-display-a-tooltip"></a><span data-ttu-id="f070f-104">Um eine QuickInfo anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="f070f-104">To display a ToolTip</span></span>  
  
-   <span data-ttu-id="f070f-105">Legen Sie die <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> Eigenschaft des Steuerelements `true`.</span><span class="sxs-lookup"><span data-stu-id="f070f-105">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the control to `true`.</span></span>  
  
     <span data-ttu-id="f070f-106">Der Standardwert von <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> ist `true`, und der Standardwert von <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> und <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> ist `false`.</span><span class="sxs-lookup"><span data-stu-id="f070f-106">The default value of <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `true`, and the default value of <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `false`.</span></span>  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a><span data-ttu-id="f070f-107">ToolTipText-Eigenschaft für den QuickInfo-Text eines ToolStripButton verwenden</span><span class="sxs-lookup"><span data-stu-id="f070f-107">To use the ToolTipText property for the ToolTip text of a ToolStripButton</span></span>  
  
1.  <span data-ttu-id="f070f-108">Legen Sie die <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> Eigenschaft der Schaltfläche auf `true`.</span><span class="sxs-lookup"><span data-stu-id="f070f-108">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the button to `true`.</span></span>  
  
2.  <span data-ttu-id="f070f-109">Legen Sie die <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> Eigenschaft der Schaltfläche auf `false`.</span><span class="sxs-lookup"><span data-stu-id="f070f-109">Set the <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> property of the button to `false`.</span></span>  
  
     <span data-ttu-id="f070f-110">Die `AutoToolTip` Eigenschaft `true` standardmäßig für <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, und <xref:System.Windows.Forms.ToolStripSplitButton>.</span><span class="sxs-lookup"><span data-stu-id="f070f-110">The `AutoToolTip` property is `true` by default for <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, and <xref:System.Windows.Forms.ToolStripSplitButton>.</span></span>  
  
     <span data-ttu-id="f070f-111">Ein <xref:System.Windows.Forms.ToolStripButton> verwendet die `Text` -Eigenschaft für die <xref:System.Windows.Forms.ToolTip> Text standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="f070f-111">A <xref:System.Windows.Forms.ToolStripButton> uses its `Text` property for the <xref:System.Windows.Forms.ToolTip> text by default.</span></span> <span data-ttu-id="f070f-112">Verwenden Sie dieses Verfahren zum Anzeigen von benutzerdefinierten Texts in einem <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip>.</span><span class="sxs-lookup"><span data-stu-id="f070f-112">Use this procedure to display custom text in a <xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f070f-113">Setzen Sie <xref:System.Windows.Forms.ToolStripItemDisplayStyle> zu <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> oder <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, auf die Schaltfläche wird kein Text angezeigt, aber die QuickInfo immer noch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f070f-113">If you set <xref:System.Windows.Forms.ToolStripItemDisplayStyle> to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no text will appear on the button, but the tool tip still appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f070f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f070f-114">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [<span data-ttu-id="f070f-115">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f070f-115">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
