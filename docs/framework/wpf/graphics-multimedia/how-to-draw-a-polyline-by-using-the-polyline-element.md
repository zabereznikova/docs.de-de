---
title: 'Gewusst wie: Zeichnen einer Polylinie mithilfe des Polylinien-Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: d065d3cead1ed9746a9615ce2bb6d3ec4cbd614d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43394415"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Gewusst wie: Zeichnen einer Polylinie mithilfe des Polylinien-Elements
Dieses Beispiel zeigt, wie Sie das Zeichnen einer Polylinie, wird eine Reihe von miteinander verbundenen Linien mit dem <xref:System.Windows.Shapes.Polyline> Element.  
  
 Zum Zeichnen einer Polylinie erstellen Sie eine <xref:System.Windows.Shapes.Polyline> -Element, und verwenden die <xref:System.Windows.Shapes.Polyline.Points%2A> Eigenschaft, um die Form Scheitelpunkte anzugeben. Verwenden Sie abschließend die <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaften, die beschreiben des Polyline-Objekt zu beschreiben, da eine Zeile ohne einen Strich nicht sichtbar ist.  
  
> [!NOTE]
>  Da die <xref:System.Windows.Shapes.Polyline> Element ist keine geschlossene Form, die <xref:System.Windows.Shapes.Shape.Fill%2A> Eigenschaft hat keine Auswirkungen, auch wenn Sie absichtlich die Formkontur schließen. Erstellen Sie eine geschlossene Form mit einer <xref:System.Windows.Shapes.Shape.Fill%2A>, verwenden Sie eine <xref:System.Windows.Shapes.Polygon> Element.  
  
 Das folgende Beispiel zeichnet zwei <xref:System.Windows.Shapes.Polyline> Elemente innerhalb einer <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Beispiel  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], gültiger Syntax für Punkte ist eine durch Leerzeichen getrennte Liste von durch Trennzeichen getrennte x und y-Koordinate-Paaren.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Obwohl dieses Beispiel verwendet eine <xref:System.Windows.Controls.Canvas> die Polylinien, können Sie Polyline-Elemente (und alle anderen Formelemente) mit einem <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> , die nicht-Text-Inhalt unterstützt.  
  
 Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Formelemente](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Shapes.Polygon>  
 <xref:System.Windows.Shapes.Shape>  
 [Formelemente](https://go.microsoft.com/fwlink/?LinkID=160037)  
 [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
