---
title: 'Gewusst wie: Erstellen einer GeometryDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: 713cecd10bfa62494c50c96cb8cbece69f7e5660
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560659"
---
# <a name="how-to-create-a-geometrydrawing"></a>Gewusst wie: Erstellen einer GeometryDrawing
In diesem Beispiel wird gezeigt, wie zum Erstellen und Anzeigen einer <xref:System.Windows.Media.GeometryDrawing>. Ein <xref:System.Windows.Media.GeometryDrawing> ermöglicht es Ihnen, die Form mit einer Füllung und Konturen zu erstellen, durch das Zuordnen einer <xref:System.Windows.Media.Pen> und ein <xref:System.Windows.Media.Brush> mit einer <xref:System.Windows.Media.Geometry>. Die <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> beschreibt die Struktur, die <xref:System.Windows.Media.GeometryDrawing.Brush%2A> beschreibt die Füllung der Form, und die <xref:System.Windows.Media.GeometryDrawing.Pen%2A> beschreibt den Rand der Form.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.GeometryDrawing> eine Form gerendert. Die Form wird beschrieben, indem eine <xref:System.Windows.Media.GeometryGroup> und zwei <xref:System.Windows.Media.EllipseGeometry> Objekte. Das Innere der Form gezeichnet wird, mit einem <xref:System.Windows.Media.LinearGradientBrush> und seine Kontur gezeichnet wird, mit einer <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>. Die <xref:System.Windows.Media.GeometryDrawing> wird angezeigt, mit einem <xref:System.Windows.Media.ImageDrawing> und ein <xref:System.Windows.Controls.Image> Element.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 Die folgende Abbildung zeigt die resultierenden <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![Eine GeometryDrawing von zwei Ellipsen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "Graphicsmm_geodraw")  
  
 Sie können mehrere Zeichnungsobjekte in einem einzigen zusammengesetzten Zeichnung mithilfe von kombinieren, um komplexere Zeichnungen zu erstellen, eine <xref:System.Windows.Media.DrawingGroup>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.DrawingGroup>  
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Übersicht über Geometrien](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Erstellen einer zusammengesetzten Zeichnung](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-drawing.md)
