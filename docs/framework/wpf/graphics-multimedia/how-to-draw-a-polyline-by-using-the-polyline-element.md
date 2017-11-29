---
title: 'Gewusst wie: Zeichnen einer Polylinie mithilfe des Polylinien-Elements'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5fa8cafdaf7856e95129f648da1d4b4ccb2f54eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Gewusst wie: Zeichnen einer Polylinie mithilfe des Polylinien-Elements
In diesem Beispiel wird gezeigt, wie zum Zeichnen einer Polylinie, also eine Reihe von miteinander verbundenen Linien mit dem <xref:System.Windows.Shapes.Polyline> Element.  
  
 Erstellen Sie zum Zeichnen einer Polylinie ein <xref:System.Windows.Shapes.Polyline> Element- und verwenden seiner <xref:System.Windows.Shapes.Polyline.Points%2A> Eigenschaft, um die Form Scheitelpunkte anzugeben. Verwenden Sie abschließend die <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaften beschreiben die Polylinie gliedern, da eine Linie ohne einen Strich nicht sichtbar ist.  
  
> [!NOTE]
>  Da die <xref:System.Windows.Shapes.Polyline> Element ist keine geschlossene Form der <xref:System.Windows.Shapes.Shape.Fill%2A> Eigenschaft hat keine Auswirkung, auch wenn Sie die Kontur der Form absichtlich schließen. So erstellen eine geschlossene Form mit einer <xref:System.Windows.Shapes.Shape.Fill%2A>, verwenden Sie eine <xref:System.Windows.Shapes.Polygon> Element.  
  
 Im folgende Beispiel zeichnet zwei <xref:System.Windows.Shapes.Polyline> Elemente innerhalb einer <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Beispiel  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], gültiger Syntax für Punkte ist eine durch Leerzeichen getrennte Liste von Paaren von durch Trennzeichen getrennten x- und y-Koordinate.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Obwohl in diesem Beispiel verwendet eine <xref:System.Windows.Controls.Canvas> die Polylinien, können Sie eine Polylinie konvertiert Elemente (und alle anderen Formelemente) mit allen <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> , die nicht-Text-Inhalt unterstützt.  
  
 Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Form-Elemente-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Shapes.Polygon>  
 <xref:System.Windows.Shapes.Shape>  
 [Beispiel für Form-Elemente](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
