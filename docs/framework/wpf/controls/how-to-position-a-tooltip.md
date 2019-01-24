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
# <a name="how-to-position-a-tooltip"></a>Vorgehensweise: Positionieren einer QuickInfo
Dieses Beispiel zeigt, wie Sie die Position einer QuickInfo auf dem Bildschirm angeben.  
  
## <a name="example"></a>Beispiel  
 Sie können die Positionieren einer QuickInfo mithilfe eines Satzes von fünf Eigenschaften, die in beiden definiert sind die <xref:System.Windows.Controls.ToolTip> und <xref:System.Windows.Controls.ToolTipService> Klassen. In der folgende Tabelle werden diese beiden Sätze von fünf Eigenschaften sowie Links zu ihrer Referenzdokumentation gemäß der Klasse.  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a>Nach der Klasse entsprechende QuickInfo-Eigenschaften  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> Eigenschaften der-Klasse|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> Eigenschaften der-Klasse|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 Wenn Sie den Inhalt einer QuickInfo mit definieren eine <xref:System.Windows.Controls.ToolTip> -Objekts verwenden Sie die Eigenschaften einer Klasse, aber die <xref:System.Windows.Controls.ToolTipService> Eigenschaften haben Vorrang vor. Verwenden der <xref:System.Windows.Controls.ToolTipService> Eigenschaften für QuickInfos, die nicht als definiert sind <xref:System.Windows.Controls.ToolTip> Objekte.  
  
 Die folgenden Abbildungen zeigen, wie Sie eine QuickInfo zu positionieren, indem Sie mit diesen Eigenschaften. Zwar, wird die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiele in den folgenden Abbildungen zeigen, wie zum Festlegen der Eigenschaften, die von definiert sind die <xref:System.Windows.Controls.ToolTip> Klasse, die entsprechenden Eigenschaften der <xref:System.Windows.Controls.ToolTipService> Klasse, gelten dieselben Layoutregeln. Weitere Informationen zu den möglichen Werten für die Placement-Eigenschaft finden Sie unter [Verhalten beim Platzieren von Popups](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).  
  
 ![QuickInfo-Platzierung](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")  
QuickInfo-Platzierung mit der Platzierung-Eigenschaft  
  
 ![Platzieren einer QuickInfo mithilfe eines Platzierungsrechtecks](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")  
QuickInfo-Platzierung mit den Eigenschaften für Platzierung und "PlacementRectangle"  
  
 ![QuickInfo-platzierungsdiagramm](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")  
QuickInfo-Platzierung mithilfe der Platzierung und "PlacementRectangle" Offset-Eigenschaften  
  
 Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.ToolTip> Eigenschaft, um die Position einer QuickInfo anzugeben, deren Inhalt, eine <xref:System.Windows.Controls.ToolTip> Objekt.  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.ToolTipService> Eigenschaft, um die Position einer QuickInfo anzugeben, deren Inhalt nicht ist, einer <xref:System.Windows.Controls.ToolTip> Objekt.  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
- [Übersicht über QuickInfo](../../../../docs/framework/wpf/controls/tooltip-overview.md)
- [Verwenden Sie die ContextMenuService- und ToolTipService](https://msdn.microsoft.com/library/809b0e9c-d612-4cda-b8af-1a698c68f4d1)
