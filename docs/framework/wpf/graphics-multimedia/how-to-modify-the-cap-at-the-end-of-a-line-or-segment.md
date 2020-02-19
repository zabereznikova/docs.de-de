---
title: 'Gewusst wie: Ändern des Endes einer Zeile oder eines Segments'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 5f755d7b4d1682755ea461121f91c0666d450ad1
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452778"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>Gewusst wie: Ändern des Endes einer Zeile oder eines Segments
In diesem Beispiel wird gezeigt, wie die Form am Anfang oder Ende eines geöffneten <xref:System.Windows.Shapes.Shape> Elements geändert wird. Um die Obergrenze am Anfang eines geöffneten <xref:System.Windows.Shapes.Shape>zu ändern, verwenden Sie die <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A>-Eigenschaft. Um die Obergrenze am Ende eines geöffneten <xref:System.Windows.Shapes.Shape>zu ändern, verwenden Sie die <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A>-Eigenschaft. Informationen zum Anzeigen der verfügbaren Zeilenenden finden Sie in der <xref:System.Windows.Media.PenLineCap>-Enumeration.  
  
> [!NOTE]
> Diese Eigenschaft wirkt sich nur auf eine geöffnete Form aus, z. b. eine <xref:System.Windows.Shapes.Line>, eine <xref:System.Windows.Shapes.Polyline>oder ein offenes <xref:System.Windows.Shapes.Path> Element.  
  
 Im folgenden Beispiel werden vier <xref:System.Windows.Shapes.Polyline> Elemente gezeichnet, und es wird ein anderer Satz von Formen an den Enden der einzelnen Elemente verwendet.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 Dieses Beispiel ist Teil einer größeren Stichprobe. Das komplette Beispiel finden Sie unter [Beispiel für Shape-Elemente](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
