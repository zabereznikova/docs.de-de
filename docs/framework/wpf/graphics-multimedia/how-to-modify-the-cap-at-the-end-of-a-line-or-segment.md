---
title: 'Gewusst wie: Ändern des Endes einer Zeile oder eines Segments'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: e69f461d426fc6a587263cea7a18478da53b5b09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>Gewusst wie: Ändern des Endes einer Zeile oder eines Segments
In diesem Beispiel wird gezeigt, wie so ändern Sie die Form am Anfang oder Ende eines offenen <xref:System.Windows.Shapes.Shape> Element. So ändern Sie die Abdeckung am Anfang eines geöffneten <xref:System.Windows.Shapes.Shape>, verwenden Sie die <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> Eigenschaft. So ändern Sie die Abdeckung am Ende eines geöffneten <xref:System.Windows.Shapes.Shape>, verwenden Sie die <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> Eigenschaft. Um die verfügbaren Zeilenenden finden Sie unter der <xref:System.Windows.Media.PenLineCap> Enumeration.  
  
> [!NOTE]
>  Diese Eigenschaft wirkt sich nur auf eine offene Form, wie z. B. eine <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline>, oder ein offenes <xref:System.Windows.Shapes.Path> Element.  
  
 Im folgende Beispiel zeichnet vier <xref:System.Windows.Shapes.Polyline> Elemente und einen anderen Satz von Shapes an den Enden der einzelnen verwendet.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Form-Elemente-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Media.PenLineCap>
