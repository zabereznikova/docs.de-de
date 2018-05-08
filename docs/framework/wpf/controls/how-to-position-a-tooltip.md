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
ms.openlocfilehash: 218d8814cf75cd80a63c94397ed00e92c6a9a8fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-position-a-tooltip"></a>Gewusst wie: Positionieren einer QuickInfo
Dieses Beispiel zeigt, wie die Position einer QuickInfo auf dem Bildschirm an.  
  
## <a name="example"></a>Beispiel  
 Sie können eine QuickInfo mit einem Satz von fünf Eigenschaften, die in beiden definiert sind Positionieren der <xref:System.Windows.Controls.ToolTip> und <xref:System.Windows.Controls.ToolTipService> Klassen. Die folgende Tabelle zeigt diese zwei Sätze von fünf Eigenschaften und Links in der entsprechenden Referenzdokumentation nach der Klasse.  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a>Nach der Klasse entsprechende QuickInfo-Eigenschaften  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> Eigenschaften der Objektklassen|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> Eigenschaften der Objektklassen|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 Wenn Sie den Inhalt einer QuickInfo mit definieren eine <xref:System.Windows.Controls.ToolTip> -Objekt können Sie die Eigenschaften der jeweiligen Klasse, aber die <xref:System.Windows.Controls.ToolTipService> Eigenschaften haben Vorrang vor. Verwenden der <xref:System.Windows.Controls.ToolTipService> Eigenschaften für QuickInfos, die nicht als definierten Fehlerklassen <xref:System.Windows.Controls.ToolTip> Objekte.  
  
 Die folgenden Abbildungen zeigen, wie eine QuickInfo positioniert wird, unter Verwendung dieser Eigenschaften. Obwohl, die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiele in diesen Abbildungen zeigen, wie zum Festlegen der Eigenschaften, die von definiert sind die <xref:System.Windows.Controls.ToolTip> Klasse, die entsprechenden Eigenschaften des der <xref:System.Windows.Controls.ToolTipService> Klasse gelten die gleichen Layout-Regeln. Weitere Informationen zu den möglichen Werten für die Eigenschaft für die Platzierung finden Sie unter [das Verhalten der Platzierung Popup](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).  
  
 ![QuickInfo-Platzierung](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")  
Mithilfe der Eigenschaft zum Bestimmen der QuickInfo-Platzierung  
  
 ![Platzieren einer QuickInfo mithilfe eines Platzierungsrechtecks](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")  
QuickInfo-Platzierung mithilfe der Eigenschaften Placement und PlacementRectangle  
  
 ![QuickInfo-platzierungsdiagramm](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")  
QuickInfo-Platzierung mithilfe der Platzierung PlacementRectangle und Offset-Eigenschaften  
  
 Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Controls.ToolTip> Eigenschaft, um die Position des eine QuickInfo anzugeben, deren Inhalt, eine <xref:System.Windows.Controls.ToolTip> Objekt.  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Controls.ToolTipService> Eigenschaft, um die Position des eine QuickInfo anzugeben, deren Inhalt nicht ist, einem <xref:System.Windows.Controls.ToolTip> Objekt.  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [Übersicht über QuickInfo](../../../../docs/framework/wpf/controls/tooltip-overview.md)  
 [Verwenden Sie die ContextMenuService- und ToolTipService](http://msdn.microsoft.com/library/809b0e9c-d612-4cda-b8af-1a698c68f4d1)
