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
# <a name="how-to-position-a-tooltip"></a>Gewusst wie: Positionieren einer QuickInfo
In diesem Beispiel wird gezeigt, wie Sie die Position einer QuickInfo auf dem Bildschirm angeben.  
  
## <a name="example"></a>Beispiel  
 Sie können eine QuickInfo positionieren, indem Sie einen Satz <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> von fünf Eigenschaften verwenden, die sowohl in der als auch in den Klassen definiert sind. Die folgende Tabelle zeigt diese beiden Sätze von fünf Eigenschaften und enthält Links zu ihrer Referenzdokumentation nach Klasse.  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a>Entsprechende QuickInfo-Eigenschaften nach Klasse  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>Klasseneigenschaften|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>Klasseneigenschaften|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 Wenn Sie den Inhalt einer QuickInfo <xref:System.Windows.Controls.ToolTip> mithilfe eines Objekts definieren, können Sie die Eigenschaften einer der beiden Klassen verwenden. Die <xref:System.Windows.Controls.ToolTipService> Eigenschaften haben jedoch Vorrang. Verwenden <xref:System.Windows.Controls.ToolTipService> Sie die Eigenschaften für QuickInfos, die nicht als <xref:System.Windows.Controls.ToolTip> Objekte definiert sind.  
  
 Die folgenden Abbildungen zeigen, wie Sie eine QuickInfo mithilfe dieser Eigenschaften positionieren. Obwohl die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiele in diesen Abbildungen zeigen, wie die <xref:System.Windows.Controls.ToolTip> Eigenschaften festgelegt werden, <xref:System.Windows.Controls.ToolTipService> die von der Klasse definiert werden, folgen die entsprechenden Eigenschaften der Klasse den gleichen Layoutregeln. Weitere Informationen zu den möglichen Werten für die Placement-Eigenschaft finden Sie unter [Popup-Platzierungsverhalten](popup-placement-behavior.md).  

 Die folgende Abbildung zeigt die Platzierung von QuickInfos mithilfe der Placement-Eigenschaft:  
  
 ![Diagramm, das die QuickInfo-Platzierung mithilfe der Placement-Eigenschaft anzeigt.](./media/how-to-position-a-tooltip/tooltip-placement-property.png)

 Die folgende Abbildung zeigt die Platzierung von QuickInfos mithilfe der Eigenschaften Placement und PlacementRectangle:

 ![Diagramm, das die QuickInfo-Platzierung mithilfe einer PlacementRectangle-Eigenschaft anzeigt.](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  

 Die folgende Abbildung zeigt die Platzierung von QuickInfos mithilfe der Eigenschaften Platzierung, PlatzierungSrechteck und Versatz:
  
 ![Diagramm, das die QuickInfo-Platzierung mithilfe der Offset-Eigenschaft anzeigt.](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 Das folgende Beispiel zeigt, <xref:System.Windows.Controls.ToolTip> wie sie die Eigenschaften verwenden, um <xref:System.Windows.Controls.ToolTip> die Position einer QuickInfo anzugeben, deren Inhalt ein Objekt ist.  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.Controls.ToolTipService> wie sie die Eigenschaften verwenden, um <xref:System.Windows.Controls.ToolTip> die Position einer QuickInfo anzugeben, deren Inhalt kein Objekt ist.  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [How-to-Themen](tooltip-how-to-topics.md)
- [Übersicht über QuickInfo](tooltip-overview.md)
