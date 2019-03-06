---
title: 'Vorgehensweise: Ändern des Endes einer Zeile oder eines Segments'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: ba61b30b4ff575bb504f792f8990bbfc64a6c33e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371475"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>Vorgehensweise: Ändern des Endes einer Zeile oder eines Segments
In diesem Beispiel wird gezeigt, wie so ändern Sie die Form am Anfang oder Ende eines offenen <xref:System.Windows.Shapes.Shape> Element. So ändern Sie die Obergrenze zu Beginn eines geöffneten <xref:System.Windows.Shapes.Shape>, verwenden Sie die <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> Eigenschaft. So ändern Sie die Obergrenze am Ende eines geöffneten <xref:System.Windows.Shapes.Shape>, verwenden Sie die <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> Eigenschaft. Um die verfügbaren Zeilenenden finden Sie unter den <xref:System.Windows.Media.PenLineCap> Enumeration.  
  
> [!NOTE]
>  Diese Eigenschaft wirkt sich nur auf eine offene Form, wie z. B. eine <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline>, oder eine offene <xref:System.Windows.Shapes.Path> Element.  
  
 Das folgende Beispiel zeichnet vier <xref:System.Windows.Shapes.Polyline> Elemente und einen anderen Satz von Shapes an den Enden der einzelnen verwendet.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Formelemente](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
