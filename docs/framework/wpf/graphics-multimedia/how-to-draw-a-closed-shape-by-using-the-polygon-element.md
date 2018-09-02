---
title: 'Gewusst wie: Zeichnen einer geschlossener Form mithilfe des Polygon-Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 89c78877e196e803f6b4139ffcfa2b4def1a07d7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43468091"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a>Gewusst wie: Zeichnen einer geschlossener Form mithilfe des Polygon-Elements
Dieses Beispiel zeigt, wie Sie das Zeichnen einer geschlossenen Form mithilfe der <xref:System.Windows.Shapes.Polygon> Element. Um eine geschlossene Form zu zeichnen, erstellen eine <xref:System.Windows.Shapes.Polygon> -Element, und verwenden dessen <xref:System.Windows.Shapes.Polygon.Points%2A> -Eigenschaft an den Scheitelpunkten einer Form. Automatisch wird eine Linie gezeichnet, die die ersten und letzten Punkte verbindet. Geben Sie abschließend eine <xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>, oder beides.  
  
## <a name="example"></a>Beispiel  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], gültiger Syntax für Punkte ist eine durch Leerzeichen getrennte Liste von durch Trennzeichen getrennte x und y-Koordinate-Paaren.  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 Obwohl das Beispiel verwendet eine <xref:System.Windows.Controls.Canvas> die Polygone enthalten, können Sie Polygon-Elemente (und alle anderen Formelemente) mit einem <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> , die nicht-Text-Inhalt unterstützt.  
  
 Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Formelemente](https://go.microsoft.com/fwlink/?LinkID=160037).
