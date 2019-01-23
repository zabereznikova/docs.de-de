---
title: 'Vorgehensweise: Erstellen einer zusammengesetzten Zeichnung'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
ms.openlocfilehash: 886956b03bd3e17360283cee1bc0e4db1d2a4731
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491414"
---
# <a name="how-to-create-a-composite-drawing"></a>Vorgehensweise: Erstellen einer zusammengesetzten Zeichnung
Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.DrawingGroup> komplexe Zeichnungen erstellen, durch die Kombination mehrerer <xref:System.Windows.Media.Drawing> Objekte in einer zusammengesetzten Zeichnung.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingGroup> erstellen Sie eine zusammengesetzte Zeichnung aus der <xref:System.Windows.Media.GeometryDrawing> und <xref:System.Windows.Media.ImageDrawing> Objekte. In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![Eine DrawingGroup mit mehreren Zeichnungen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "Graphicsmm_simple")  
Eine zusammengesetzte Zeichnung, die erstellt wird, mithilfe von DrawingGroup  
  
 Beachten Sie den grauen Rahmen, der die Begrenzungen der Zeichnung anzeigt.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Können Sie eine <xref:System.Windows.Media.DrawingGroup> Anwenden einer <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> festlegen, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, oder <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> auf die Zeichnungen, er enthält. Da eine <xref:System.Windows.Media.DrawingGroup> ist auch eine <xref:System.Windows.Media.Drawing>, andere <xref:System.Windows.Media.DrawingGroup> Objekte.  
  
 Im folgende Beispiel ähnelt dem vorherigen Beispiel, jedoch zusätzliche verwendet <xref:System.Windows.Media.DrawingGroup> Objekte Bitmapeffekten und eine Deckkraftmaske auf einige der Zeichnungen anwenden. In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![Eine DrawingGroup mit mehreren Zeichnungen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.jpg "Graphicsmm_multiple")  
Zusammengesetzte Zeichnung, die über mehrere DrawingGroup-Objekte verfügt.  
  
 Beachten Sie den grauen Rahmen, der die Begrenzungen der Zeichnung anzeigt.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 Weitere Informationen zu <xref:System.Windows.Media.Drawing> Objekten finden Sie [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>
- <xref:System.Windows.Media.DrawingGroup.Transform%2A>
- <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>
- <xref:System.Windows.Media.DrawingGroup.Opacity%2A>
- <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>
- <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>
- [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
