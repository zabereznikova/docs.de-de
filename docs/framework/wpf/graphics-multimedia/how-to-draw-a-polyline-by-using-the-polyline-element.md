---
title: 'Vorgehensweise: Zeichnen einer Polylinie mithilfe des Polylinien-Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: fb5220082989a9d0a22c4998bb79c0a196067e7e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934959"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Vorgehensweise: Zeichnen einer Polylinie mithilfe des Polylinien-Elements
In diesem Beispiel wird gezeigt, wie Sie mithilfe des <xref:System.Windows.Shapes.Polyline> -Elements eine Polylinie zeichnen, bei der es sich um eine Reihe verbundener Linien handelt.  
  
 Um eine Polylinie zu zeichnen, erstellen <xref:System.Windows.Shapes.Polyline> Sie ein-Element <xref:System.Windows.Shapes.Polyline.Points%2A> , und verwenden Sie die-Eigenschaft, um die Form Scheitel Punkte anzugeben. Verwenden Sie abschließend die <xref:System.Windows.Shapes.Shape.Stroke%2A> - <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaft und die-Eigenschaft, um die polyliniengliederung zu beschreiben, da eine Linie ohne Strich unsichtbar ist.  
  
> [!NOTE]
> Da das <xref:System.Windows.Shapes.Polyline> -Element keine geschlossene Form ist, hat <xref:System.Windows.Shapes.Shape.Fill%2A> die-Eigenschaft keine Auswirkung, auch wenn Sie die Form Gliederung absichtlich schließen. Um eine geschlossene Form mit einem <xref:System.Windows.Shapes.Shape.Fill%2A>zu erstellen, verwenden Sie ein <xref:System.Windows.Shapes.Polygon> -Element.  
  
 Im folgenden Beispiel werden zwei <xref:System.Windows.Shapes.Polyline> -Elemente in <xref:System.Windows.Controls.Canvas>einem-Element gezeichnet.  
  
## <a name="example"></a>Beispiel  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ist die gültige Syntax für Punkte eine durch Leerzeichen getrennte Liste mit durch Trennzeichen getrennten x-und y-Koordinatenpaaren.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Obwohl in diesem Beispiel ein <xref:System.Windows.Controls.Canvas> -Element verwendet wird, das die Polylinien enthält, können Sie polylinienelemente (und alle anderen Shape <xref:System.Windows.Controls.Panel> - <xref:System.Windows.Controls.Control> Elemente) mit beliebigen oder verwenden, die nicht Text Inhalt unterstützen.  
  
 Dieses Beispiel ist Teil einer größeren Stichprobe. Das komplette Beispiel finden Sie unter [Beispiel für Shape-Elemente](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [Beispiel für Shape-Elemente](https://go.microsoft.com/fwlink/?LinkID=160037)
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](shapes-and-basic-drawing-in-wpf-overview.md)
