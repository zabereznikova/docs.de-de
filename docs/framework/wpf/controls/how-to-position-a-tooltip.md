---
title: 'Gewusst wie: Positionieren einer QuickInfo'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62e86f2adfbe8f8aac000d653e955555c7def750
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="7e9cb-102">Gewusst wie: Positionieren einer QuickInfo</span><span class="sxs-lookup"><span data-stu-id="7e9cb-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="7e9cb-103">Dieses Beispiel zeigt, wie die Position einer QuickInfo auf dem Bildschirm an.</span><span class="sxs-lookup"><span data-stu-id="7e9cb-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e9cb-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7e9cb-104">Example</span></span>  
 <span data-ttu-id="7e9cb-105">Sie können eine QuickInfo mit einem Satz von fünf Eigenschaften, die in beiden definiert sind Positionieren der <xref:System.Windows.Controls.ToolTip> und <xref:System.Windows.Controls.ToolTipService> Klassen.</span><span class="sxs-lookup"><span data-stu-id="7e9cb-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="7e9cb-106">Die folgende Tabelle zeigt diese zwei Sätze von fünf Eigenschaften und Links in der entsprechenden Referenzdokumentation nach der Klasse.</span><span class="sxs-lookup"><span data-stu-id="7e9cb-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="7e9cb-107">Nach der Klasse entsprechende QuickInfo-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7e9cb-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="7e9cb-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>Eigenschaften der Objektklassen</span><span class="sxs-lookup"><span data-stu-id="7e9cb-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="7e9cb-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>Eigenschaften der Objektklassen</span><span class="sxs-lookup"><span data-stu-id="7e9cb-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="7e9cb-110">Wenn Sie den Inhalt einer QuickInfo mit definieren eine <xref:System.Windows.Controls.ToolTip> -Objekt können Sie die Eigenschaften der jeweiligen Klasse, aber die <xref:System.Windows.Controls.ToolTipService> Eigenschaften haben Vorrang vor.</span><span class="sxs-lookup"><span data-stu-id="7e9cb-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="7e9cb-111">Verwenden der <xref:System.Windows.Controls.ToolTipService> Eigenschaften für QuickInfos, die nicht als definierten Fehlerklassen <xref:System.Windows.Controls.ToolTip> Objekte.</span><span class="sxs-lookup"><span data-stu-id="7e9cb-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="7e9cb-112">Die folgenden Abbildungen zeigen, wie eine QuickInfo positioniert wird, unter Verwendung dieser Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="7e9cb-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="7e9cb-113">Obwohl, die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiele in diesen Abbildungen zeigen, wie zum Festlegen der Eigenschaften, die von definiert sind die <xref:System.Windows.Controls.ToolTip> Klasse, die entsprechenden Eigenschaften des der <xref:System.Windows.Controls.ToolTipService> Klasse gelten die gleichen Layout-Regeln.</span><span class="sxs-lookup"><span data-stu-id="7e9cb-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="7e9cb-114">Weitere Informationen zu den möglichen Werten für die Eigenschaft für die Platzierung finden Sie unter [das Verhalten der Platzierung Popup](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="7e9cb-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span></span>  
  
 <span data-ttu-id="7e9cb-115">![QuickInfo-Platzierung](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span><span class="sxs-lookup"><span data-stu-id="7e9cb-115">![ToolTip placement](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span></span>  
<span data-ttu-id="7e9cb-116">Mithilfe der Eigenschaft zum Bestimmen der QuickInfo-Platzierung</span><span class="sxs-lookup"><span data-stu-id="7e9cb-116">ToolTip placement by using the Placement property</span></span>  
  
 <span data-ttu-id="7e9cb-117">![Platzieren einer QuickInfo mithilfe eines Platzierungsrechtecks](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span><span class="sxs-lookup"><span data-stu-id="7e9cb-117">![Placing a ToolTip by using a placement rectangle](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span></span>  
<span data-ttu-id="7e9cb-118">QuickInfo-Platzierung mithilfe der Eigenschaften Placement und PlacementRectangle</span><span class="sxs-lookup"><span data-stu-id="7e9cb-118">ToolTip placement by using the Placement and PlacementRectangle properties</span></span>  
  
 <span data-ttu-id="7e9cb-119">![QuickInfo-platzierungsdiagramm](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span><span class="sxs-lookup"><span data-stu-id="7e9cb-119">![ToolTip placement diagram](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span></span>  
<span data-ttu-id="7e9cb-120">QuickInfo-Platzierung mithilfe der Platzierung PlacementRectangle und Offset-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7e9cb-120">ToolTip placement by using the Placement, PlacementRectangle, and Offset properties</span></span>  
  
 <span data-ttu-id="7e9cb-121">Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Controls.ToolTip> Eigenschaft, um die Position des eine QuickInfo anzugeben, deren Inhalt, eine <xref:System.Windows.Controls.ToolTip> Objekt.</span><span class="sxs-lookup"><span data-stu-id="7e9cb-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="7e9cb-122">Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Controls.ToolTipService> Eigenschaft, um die Position des eine QuickInfo anzugeben, deren Inhalt nicht ist, einem <xref:System.Windows.Controls.ToolTip> Objekt.</span><span class="sxs-lookup"><span data-stu-id="7e9cb-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="7e9cb-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e9cb-123">See Also</span></span>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [<span data-ttu-id="7e9cb-124">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="7e9cb-124">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [<span data-ttu-id="7e9cb-125">Übersicht über QuickInfo</span><span class="sxs-lookup"><span data-stu-id="7e9cb-125">ToolTip Overview</span></span>](../../../../docs/framework/wpf/controls/tooltip-overview.md)  
 [<span data-ttu-id="7e9cb-126">Verwenden Sie die ContextMenuService- und ToolTipService</span><span class="sxs-lookup"><span data-stu-id="7e9cb-126">Use the ContextMenuService and ToolTipService</span></span>](http://msdn.microsoft.com/en-us/809b0e9c-d612-4cda-b8af-1a698c68f4d1)
