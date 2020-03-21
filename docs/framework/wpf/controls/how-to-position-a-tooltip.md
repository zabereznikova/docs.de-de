---
title: 'Gewusst wie: Positionieren einer QuickInfo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: 0f52703e4fe127daa40f220280f084b2026580cc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186940"
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="0be44-102">Gewusst wie: Positionieren einer QuickInfo</span><span class="sxs-lookup"><span data-stu-id="0be44-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="0be44-103">In diesem Beispiel wird gezeigt, wie Sie die Position einer QuickInfo auf dem Bildschirm angeben.</span><span class="sxs-lookup"><span data-stu-id="0be44-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0be44-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0be44-104">Example</span></span>  
 <span data-ttu-id="0be44-105">Sie können eine QuickInfo positionieren, indem Sie einen Satz <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> von fünf Eigenschaften verwenden, die sowohl in der als auch in den Klassen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="0be44-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="0be44-106">Die folgende Tabelle zeigt diese beiden Sätze von fünf Eigenschaften und enthält Links zu ihrer Referenzdokumentation nach Klasse.</span><span class="sxs-lookup"><span data-stu-id="0be44-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="0be44-107">Entsprechende QuickInfo-Eigenschaften nach Klasse</span><span class="sxs-lookup"><span data-stu-id="0be44-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="0be44-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>Klasseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="0be44-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="0be44-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>Klasseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="0be44-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="0be44-110">Wenn Sie den Inhalt einer QuickInfo <xref:System.Windows.Controls.ToolTip> mithilfe eines Objekts definieren, können Sie die Eigenschaften einer der beiden Klassen verwenden. Die <xref:System.Windows.Controls.ToolTipService> Eigenschaften haben jedoch Vorrang.</span><span class="sxs-lookup"><span data-stu-id="0be44-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="0be44-111">Verwenden <xref:System.Windows.Controls.ToolTipService> Sie die Eigenschaften für QuickInfos, die nicht als <xref:System.Windows.Controls.ToolTip> Objekte definiert sind.</span><span class="sxs-lookup"><span data-stu-id="0be44-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="0be44-112">Die folgenden Abbildungen zeigen, wie Sie eine QuickInfo mithilfe dieser Eigenschaften positionieren.</span><span class="sxs-lookup"><span data-stu-id="0be44-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="0be44-113">Obwohl die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiele in diesen Abbildungen zeigen, wie die <xref:System.Windows.Controls.ToolTip> Eigenschaften festgelegt werden, <xref:System.Windows.Controls.ToolTipService> die von der Klasse definiert werden, folgen die entsprechenden Eigenschaften der Klasse den gleichen Layoutregeln.</span><span class="sxs-lookup"><span data-stu-id="0be44-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="0be44-114">Weitere Informationen zu den möglichen Werten für die Placement-Eigenschaft finden Sie unter [Popup-Platzierungsverhalten](popup-placement-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="0be44-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](popup-placement-behavior.md).</span></span>  

 <span data-ttu-id="0be44-115">Die folgende Abbildung zeigt die Platzierung von QuickInfos mithilfe der Placement-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="0be44-115">The following image shows tooltip placement by using the Placement property:</span></span>  
  
 ![Diagramm, das die QuickInfo-Platzierung mithilfe der Placement-Eigenschaft anzeigt.](./media/how-to-position-a-tooltip/tooltip-placement-property.png)

 <span data-ttu-id="0be44-117">Die folgende Abbildung zeigt die Platzierung von QuickInfos mithilfe der Eigenschaften Placement und PlacementRectangle:</span><span class="sxs-lookup"><span data-stu-id="0be44-117">The following image shows tooltip placement by using the Placement and PlacementRectangle properties:</span></span>

 ![Diagramm, das die QuickInfo-Platzierung mithilfe einer PlacementRectangle-Eigenschaft anzeigt.](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  

 <span data-ttu-id="0be44-119">Die folgende Abbildung zeigt die Platzierung von QuickInfos mithilfe der Eigenschaften Platzierung, PlatzierungSrechteck und Versatz:</span><span class="sxs-lookup"><span data-stu-id="0be44-119">The following image shows tooltip placement by using the Placement, PlacementRectangle, and Offset properties:</span></span>
  
 ![Diagramm, das die QuickInfo-Platzierung mithilfe der Offset-Eigenschaft anzeigt.](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 <span data-ttu-id="0be44-121">Das folgende Beispiel zeigt, <xref:System.Windows.Controls.ToolTip> wie sie die Eigenschaften verwenden, um <xref:System.Windows.Controls.ToolTip> die Position einer QuickInfo anzugeben, deren Inhalt ein Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="0be44-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="0be44-122">Das folgende Beispiel zeigt, <xref:System.Windows.Controls.ToolTipService> wie sie die Eigenschaften verwenden, um <xref:System.Windows.Controls.ToolTip> die Position einer QuickInfo anzugeben, deren Inhalt kein Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="0be44-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="0be44-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0be44-123">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="0be44-124">How-to-Themen</span><span class="sxs-lookup"><span data-stu-id="0be44-124">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="0be44-125">Übersicht über QuickInfo</span><span class="sxs-lookup"><span data-stu-id="0be44-125">ToolTip Overview</span></span>](tooltip-overview.md)
