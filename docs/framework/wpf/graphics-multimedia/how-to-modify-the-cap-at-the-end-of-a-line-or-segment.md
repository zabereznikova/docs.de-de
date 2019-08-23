---
title: 'Vorgehensweise: Ändern des Endes einer Zeile oder eines Segments'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 53487417636dae8d855fe70b7b9255351a2dfb1e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916134"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>Vorgehensweise: Ändern des Endes einer Zeile oder eines Segments
In diesem Beispiel wird gezeigt, wie die Form am Anfang oder Ende eines geöffneten <xref:System.Windows.Shapes.Shape> Elements geändert wird. Um die Obergrenze am Anfang eines geöffneten <xref:System.Windows.Shapes.Shape>zu ändern, <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> verwenden Sie die zugehörige-Eigenschaft. Um die Obergrenze am Ende eines geöffneten <xref:System.Windows.Shapes.Shape>zu ändern, <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> verwenden Sie die zugehörige-Eigenschaft. Informationen zum Anzeigen der verfügbaren Zeilenenden finden <xref:System.Windows.Media.PenLineCap> Sie unter der-Enumeration.  
  
> [!NOTE]
> Diese Eigenschaft wirkt sich nur auf eine geöffnete Form aus, <xref:System.Windows.Shapes.Line>z. <xref:System.Windows.Shapes.Polyline>b. ein, <xref:System.Windows.Shapes.Path> ein oder ein offenes Element.  
  
 Im folgenden Beispiel werden vier <xref:System.Windows.Shapes.Polyline> Elemente gezeichnet, und es wird jeweils ein anderer Satz von Formen an den Enden der einzelnen Elemente verwendet.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 Dieses Beispiel ist Teil einer größeren Stichprobe. Das komplette Beispiel finden Sie unter [Beispiel für Shape-Elemente](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
