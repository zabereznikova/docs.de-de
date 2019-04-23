---
title: 'Vorgehensweise: Festlegen von horizontaler und vertikaler Ausrichtung bei einem TileBrush'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], alignment of
- vertical alignment of TileBrushes [WPF]
- aligning [WPF], TileBrushes
- horizontal alignment of Tilebrushes [WPF]
ms.assetid: 65ae89bd-9246-4c9e-bde4-2fb991d4060d
ms.openlocfilehash: ddef63bba7fce1bfb8d50b4f2dbaaddfa76709ce
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149178"
---
# <a name="how-to-set-the-horizontal-and-vertical-alignment-of-a-tilebrush"></a>Vorgehensweise: Festlegen von horizontaler und vertikaler Ausrichtung bei einem TileBrush
In diesem Beispiel wird gezeigt, wie die horizontale und die vertikale Ausrichtung des Inhalts in einer Fläche gesteuert werden. Die horizontale und vertikale Ausrichtung des steuern eine <xref:System.Windows.Media.TileBrush>, verwenden die <xref:System.Windows.Media.TileBrush.AlignmentX%2A> und <xref:System.Windows.Media.TileBrush.AlignmentY%2A> Eigenschaften.  
  
 Die <xref:System.Windows.Media.TileBrush.AlignmentX%2A> und <xref:System.Windows.Media.TileBrush.AlignmentY%2A> Eigenschaften eine <xref:System.Windows.Media.TileBrush> werden verwendet, wenn eine der folgenden Bedingungen zutrifft:  
  
-   Die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft <xref:System.Windows.Media.Stretch.Uniform> oder <xref:System.Windows.Media.Stretch.UniformToFill> und <xref:System.Windows.Media.TileBrush.Viewbox%2A> und <xref:System.Windows.Media.TileBrush.Viewport%2A> weisen unterschiedliche Seitenverhältnisse.  
  
-   Die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft <xref:System.Windows.Media.Stretch.None> und <xref:System.Windows.Media.TileBrush.Viewbox%2A> und <xref:System.Windows.Media.TileBrush.Viewport%2A> sind von unterschiedlicher Größe.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Inhalt ausgerichtet eine <xref:System.Windows.Media.DrawingBrush>, d.h. eine Art von <xref:System.Windows.Media.TileBrush>, auf der linken oberen Ecke der zugehörigen Fläche. Zum Ausrichten des Inhalts, der im Beispiel wird die <xref:System.Windows.Media.TileBrush.AlignmentX%2A> Eigenschaft der <xref:System.Windows.Media.DrawingBrush> zu <xref:System.Windows.Media.AlignmentX.Left> und <xref:System.Windows.Media.TileBrush.AlignmentY%2A> Eigenschaft <xref:System.Windows.Media.AlignmentY.Top>. Folgende Ergebnisse werden zurückgegeben:  
  
 ![Ein TileBrush mit oben&#45;Ausrichtung links](./media/graphicsmm-tilebrushalignmentexampletopleft.png "Graphicsmm_TileBrushAlignmentExampleTopLeft")  
TileBrush mit an der linken oberen Ecke ausgerichtetem Inhalt  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmentinline)]  
  
## <a name="example"></a>Beispiel  
 Im nächsten Beispiel wird der Inhalt ausgerichtet eine <xref:System.Windows.Media.DrawingBrush> auf der unteren rechten Ecke der zugehörigen Fläche durch Festlegen der <xref:System.Windows.Media.TileBrush.AlignmentX%2A> Eigenschaft <xref:System.Windows.Media.AlignmentX.Right> und <xref:System.Windows.Media.TileBrush.AlignmentY%2A> Eigenschaft <xref:System.Windows.Media.AlignmentY.Bottom>. Das Beispiel erzeugt folgende Ausgabe.  
  
 ![Ein TileBrush mit unten&#45;Ausrichtung rechts](./media/graphicsmm-tilebrushalignmentexamplebottomright.png "Graphicsmm_TileBrushAlignmentExampleBottomRight")  
TileBrush mit an der rechten unteren Ecke ausgerichtetem Inhalt  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
## <a name="example"></a>Beispiel  
 Im nächsten Beispiel wird der Inhalt ausgerichtet eine <xref:System.Windows.Media.DrawingBrush> auf der linken oberen Ecke der zugehörigen Fläche durch Festlegen der <xref:System.Windows.Media.TileBrush.AlignmentX%2A> Eigenschaft <xref:System.Windows.Media.AlignmentX.Left> und <xref:System.Windows.Media.TileBrush.AlignmentY%2A> Eigenschaft <xref:System.Windows.Media.AlignmentY.Top>. Außerdem wird die <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.TileMode%2A> von der <xref:System.Windows.Media.DrawingBrush> um ein Flächenmuster zu erzeugen. Das Beispiel erzeugt folgende Ausgabe.  
  
 ![Ein TileBrush von tiled mit oben&#45;Ausrichtung links](./media/graphicsmm-tilebrushalignmentexampletoplefttiled.png "Graphicsmm_TileBrushAlignmentExampleTopLeftTiled")  
Flächenmuster mit in der Basisfläche oben links ausgerichtetem Inhalt  
  
 In der Abbildung ist eine Basisfläche hervorgehoben, damit Sie sehen können, wie der Inhalt ausgerichtet ist. Beachten Sie, dass die <xref:System.Windows.Media.TileBrush.AlignmentX%2A> Einstellung hat keine Auswirkungen, da der Inhalt des der <xref:System.Windows.Media.DrawingBrush> vollständig die Basisfläche horizontal ausfüllt.  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmenttiledinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmenttiledinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmenttiledinline)]  
  
## <a name="example"></a>Beispiel  
 Im letzte Beispiel wird der Inhalt eines in Flächen unterteilten ausgerichtet <xref:System.Windows.Media.DrawingBrush> auf der rechten unteren Ecke der zugehörigen Basisfläche durch Festlegen der <xref:System.Windows.Media.TileBrush.AlignmentX%2A> Eigenschaft <xref:System.Windows.Media.AlignmentX.Right> und <xref:System.Windows.Media.TileBrush.AlignmentY%2A> Eigenschaft <xref:System.Windows.Media.AlignmentY.Bottom>. Das Beispiel erzeugt folgende Ausgabe.  
  
 ![Ein TileBrush von tiled mit unten&#45;Ausrichtung rechts](./media/graphicsmm-tilebrushalignmentexamplebottomrighttiled.png "Graphicsmm_TileBrushAlignmentExampleBottomRightTiled")  
Flächenmuster mit in der Basisfläche oben rechts ausgerichtetem Inhalt  
  
 In diesem Fall die <xref:System.Windows.Media.TileBrush.AlignmentX%2A> Einstellung hat keine Auswirkungen, da der Inhalt des der <xref:System.Windows.Media.DrawingBrush> vollständig die Basisfläche horizontal ausfüllt.  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
 In den Beispielen <xref:System.Windows.Media.DrawingBrush> -Objekten gezeigt wie das <xref:System.Windows.Media.TileBrush.AlignmentX%2A> und <xref:System.Windows.Media.TileBrush.AlignmentY%2A> Eigenschaften verwendet werden. Diese Eigenschaften verhalten sich identisch, bei allen TileBrush-Objekten: <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.ImageBrush>, und <xref:System.Windows.Media.VisualBrush>. Weitere Informationen zu TileBrush-Objekten finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.VisualBrush>
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
