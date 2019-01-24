---
title: 'Vorgehensweise: Positionieren einer QuickInfo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: 403b070e782a6f243fd5a420e569daa02044dbb1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727702"
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="0e58a-102">Vorgehensweise: Positionieren einer QuickInfo</span><span class="sxs-lookup"><span data-stu-id="0e58a-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="0e58a-103">Dieses Beispiel zeigt, wie Sie die Position einer QuickInfo auf dem Bildschirm angeben.</span><span class="sxs-lookup"><span data-stu-id="0e58a-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e58a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e58a-104">Example</span></span>  
 <span data-ttu-id="0e58a-105">Sie können die Positionieren einer QuickInfo mithilfe eines Satzes von fünf Eigenschaften, die in beiden definiert sind die <xref:System.Windows.Controls.ToolTip> und <xref:System.Windows.Controls.ToolTipService> Klassen.</span><span class="sxs-lookup"><span data-stu-id="0e58a-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="0e58a-106">In der folgende Tabelle werden diese beiden Sätze von fünf Eigenschaften sowie Links zu ihrer Referenzdokumentation gemäß der Klasse.</span><span class="sxs-lookup"><span data-stu-id="0e58a-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="0e58a-107">Nach der Klasse entsprechende QuickInfo-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0e58a-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="0e58a-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> Eigenschaften der-Klasse</span><span class="sxs-lookup"><span data-stu-id="0e58a-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="0e58a-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> Eigenschaften der-Klasse</span><span class="sxs-lookup"><span data-stu-id="0e58a-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="0e58a-110">Wenn Sie den Inhalt einer QuickInfo mit definieren eine <xref:System.Windows.Controls.ToolTip> -Objekts verwenden Sie die Eigenschaften einer Klasse, aber die <xref:System.Windows.Controls.ToolTipService> Eigenschaften haben Vorrang vor.</span><span class="sxs-lookup"><span data-stu-id="0e58a-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="0e58a-111">Verwenden der <xref:System.Windows.Controls.ToolTipService> Eigenschaften für QuickInfos, die nicht als definiert sind <xref:System.Windows.Controls.ToolTip> Objekte.</span><span class="sxs-lookup"><span data-stu-id="0e58a-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="0e58a-112">Die folgenden Abbildungen zeigen, wie Sie eine QuickInfo zu positionieren, indem Sie mit diesen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="0e58a-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="0e58a-113">Zwar, wird die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiele in den folgenden Abbildungen zeigen, wie zum Festlegen der Eigenschaften, die von definiert sind die <xref:System.Windows.Controls.ToolTip> Klasse, die entsprechenden Eigenschaften der <xref:System.Windows.Controls.ToolTipService> Klasse, gelten dieselben Layoutregeln.</span><span class="sxs-lookup"><span data-stu-id="0e58a-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="0e58a-114">Weitere Informationen zu den möglichen Werten für die Placement-Eigenschaft finden Sie unter [Verhalten beim Platzieren von Popups](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="0e58a-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span></span>  
  
 <span data-ttu-id="0e58a-115">![QuickInfo-Platzierung](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span><span class="sxs-lookup"><span data-stu-id="0e58a-115">![ToolTip placement](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span></span>  
<span data-ttu-id="0e58a-116">QuickInfo-Platzierung mit der Platzierung-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0e58a-116">ToolTip placement by using the Placement property</span></span>  
  
 <span data-ttu-id="0e58a-117">![Platzieren einer QuickInfo mithilfe eines Platzierungsrechtecks](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span><span class="sxs-lookup"><span data-stu-id="0e58a-117">![Placing a ToolTip by using a placement rectangle](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span></span>  
<span data-ttu-id="0e58a-118">QuickInfo-Platzierung mit den Eigenschaften für Platzierung und "PlacementRectangle"</span><span class="sxs-lookup"><span data-stu-id="0e58a-118">ToolTip placement by using the Placement and PlacementRectangle properties</span></span>  
  
 <span data-ttu-id="0e58a-119">![QuickInfo-platzierungsdiagramm](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span><span class="sxs-lookup"><span data-stu-id="0e58a-119">![ToolTip placement diagram](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span></span>  
<span data-ttu-id="0e58a-120">QuickInfo-Platzierung mithilfe der Platzierung und "PlacementRectangle" Offset-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0e58a-120">ToolTip placement by using the Placement, PlacementRectangle, and Offset properties</span></span>  
  
 <span data-ttu-id="0e58a-121">Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.ToolTip> Eigenschaft, um die Position einer QuickInfo anzugeben, deren Inhalt, eine <xref:System.Windows.Controls.ToolTip> Objekt.</span><span class="sxs-lookup"><span data-stu-id="0e58a-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="0e58a-122">Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.ToolTipService> Eigenschaft, um die Position einer QuickInfo anzugeben, deren Inhalt nicht ist, einer <xref:System.Windows.Controls.ToolTip> Objekt.</span><span class="sxs-lookup"><span data-stu-id="0e58a-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="0e58a-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e58a-123">See also</span></span>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="0e58a-124">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="0e58a-124">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
- [<span data-ttu-id="0e58a-125">Übersicht über QuickInfo</span><span class="sxs-lookup"><span data-stu-id="0e58a-125">ToolTip Overview</span></span>](../../../../docs/framework/wpf/controls/tooltip-overview.md)
- [<span data-ttu-id="0e58a-126">Verwenden Sie die ContextMenuService- und ToolTipService</span><span class="sxs-lookup"><span data-stu-id="0e58a-126">Use the ContextMenuService and ToolTipService</span></span>](https://msdn.microsoft.com/library/809b0e9c-d612-4cda-b8af-1a698c68f4d1)
