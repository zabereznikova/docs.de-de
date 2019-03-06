---
title: 'Vorgehensweise: Erstellen einer GeometryDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: 6eb604a8446000ef308c2b5a99480fb6a476c949
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373815"
---
# <a name="how-to-create-a-geometrydrawing"></a>Vorgehensweise: Erstellen einer GeometryDrawing
In diesem Beispiel wird gezeigt, wie zum Erstellen und Anzeigen einer <xref:System.Windows.Media.GeometryDrawing>. Ein <xref:System.Windows.Media.GeometryDrawing> können Sie zum Erstellen einer Form mit einer Füllung und eine Übersicht über durch Zuordnen einer <xref:System.Windows.Media.Pen> und ein <xref:System.Windows.Media.Brush> mit einem <xref:System.Windows.Media.Geometry>. Die <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> beschreibt die Struktur, die <xref:System.Windows.Media.GeometryDrawing.Brush%2A> wird beschrieben, die Füllung der Form, und die <xref:System.Windows.Media.GeometryDrawing.Pen%2A> der Form beschreibt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.GeometryDrawing> eine Form gerendert. Die Form wird beschrieben, indem eine <xref:System.Windows.Media.GeometryGroup> und zwei <xref:System.Windows.Media.EllipseGeometry> Objekte. Das Innere der Form gezeichnet wird eine <xref:System.Windows.Media.LinearGradientBrush> und seine Kontur gezeichnet wird, mit einem <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>. Die <xref:System.Windows.Media.GeometryDrawing> nutzt eine <xref:System.Windows.Media.ImageDrawing> und <xref:System.Windows.Controls.Image> Element.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 Die folgende Abbildung zeigt die resultierende <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![Eine GeometryDrawing von zwei Ellipsen](./media/graphicsmm-geodraw.jpg "Graphicsmm_geodraw")  
  
 Sie können mehrere Zeichnungsobjekte in einem einzigen zusammengesetzten Zeichnung mithilfe von kombinieren, um komplexere Zeichnungen erstellen zu können, eine <xref:System.Windows.Media.DrawingGroup>.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.DrawingGroup>
- [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md)
- [Übersicht über Geometrien](geometry-overview.md)
- [Erstellen einer zusammengesetzten Zeichnung](how-to-create-a-composite-drawing.md)
