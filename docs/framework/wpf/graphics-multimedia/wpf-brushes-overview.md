---
title: Übersicht über Pinsel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], about brushes
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
ms.openlocfilehash: 18ca9b79a6ee801638a54fcb227c44e9aea21fd0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746209"
---
# <a name="wpf-brushes-overview"></a>Übersicht über WPF-Pinsel
Alle Elemente, die auf dem Bildschirm sichtbar sind, sind sichtbar, da Sie von einem Pinsel gezeichnet wurden. Beispielsweise wird ein Pinsel verwendet, um den Hintergrund einer Schaltfläche, den Vordergrund von Text und das Ausfüllen einer Form zu beschreiben. Dieses Thema enthält eine Einführung in die Konzepte der Zeichnung mit [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Pinsel und stellt Beispiele bereit. Mithilfe von Pinseln können Sie [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-Objekte, angefangen von einfachen Objekten, über Objekte in Volltonfarbe bis hin zu Objekten mit komplexen von Mustern und Bildern, zeichnen.  
  
<a name="paintingwithbrush"></a>   
## <a name="painting-with-a-brush"></a>Zeichnen mit einem Pinsel  
 Ein <xref:System.Windows.Media.Brush> "zeichnet" einen Bereich mit seiner Ausgabe. Verschiedene Pinsel verfügen über unterschiedliche Arten von Ausgaben. Einige Pinsel zeichnen einen Bereich mit einer voll Tonfarbe, andere mit einem Farbverlauf, einem Muster, einem Bild oder einer Zeichnung. Die folgende Abbildung zeigt Beispiele für jeden der verschiedenen <xref:System.Windows.Media.Brush> Typen.  
  
 ![Pinseltypen](./media/graphicsmm-brushtypes.jpg "graphicsmm_brushtypes")  
Pinsel Beispiele  
  
 Bei den meisten visuellen Objekten können Sie angeben, wie Sie gezeichnet werden. In der folgenden Tabelle sind einige allgemeine Objekte und Eigenschaften aufgeführt, mit denen Sie eine <xref:System.Windows.Media.Brush>verwenden können.  
  
|Klasse|Pinseleigenschaften|  
|-----------|----------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 In den folgenden Abschnitten werden die verschiedenen <xref:System.Windows.Media.Brush> Typen beschrieben und ein Beispiel dafür bereitgestellt.  
  
<a name="paintwithsolidcolorbrush"></a>   
## <a name="paint-with-a-solid-color"></a>Zeichnen mit einer voll Tonfarbe  
 Ein <xref:System.Windows.Media.SolidColorBrush> zeichnet einen Bereich mit einer voll soliden <xref:System.Windows.Media.Color>. Es gibt verschiedene Möglichkeiten, den <xref:System.Windows.Media.SolidColorBrush.Color%2A> eines <xref:System.Windows.Media.SolidColorBrush>anzugeben: Sie können z. b. die Alpha-, rot-, blau-und grünen Kanäle angeben oder eine der vordefinierten Farben verwenden, die von der <xref:System.Windows.Media.Colors>-Klasse bereitgestellt werden.  
  
 Im folgenden Beispiel wird ein-<xref:System.Windows.Media.SolidColorBrush> verwendet, um die <xref:System.Windows.Shapes.Shape.Fill%2A> eines <xref:System.Windows.Shapes.Rectangle>zu zeichnen. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mithilfe von SolidColorBrush gezeichnetes Rechteck](./media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm_brush_ovw_solidcolorbrush")  
Ein mithilfe von SolidColorBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 Weitere Informationen zur <xref:System.Windows.Media.SolidColorBrush>-Klasse finden Sie unter Übersicht über das Zeichnen [mit voll Tonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithlineargradientbrush"></a>   
## <a name="paint-with-a-linear-gradient"></a>Zeichnen mit einem linearen Farbverlauf  
 Ein-<xref:System.Windows.Media.LinearGradientBrush> zeichnet einen Bereich mit einem linearen Farbverlauf. Ein linearer Farbverlauf kombiniert mindestens zwei Farben in einer Linie, der Farbverlaufs Achse. Mit <xref:System.Windows.Media.GradientStop>-Objekten können Sie die Farben im Farbverlauf und deren Positionen angeben.  
  
 Im folgenden Beispiel wird ein-<xref:System.Windows.Media.LinearGradientBrush> verwendet, um die <xref:System.Windows.Shapes.Shape.Fill%2A> eines <xref:System.Windows.Shapes.Rectangle>zu zeichnen. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mit einem LinearGradientBrush gezeichnetes Rechteck](./media/graphicsmm-brush-ovw-lineargradientbrush.jpg "graphicsmm_brush_ovw_lineargradientbrush")  
Ein mit einem LinearGradientBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 Weitere Informationen zur <xref:System.Windows.Media.LinearGradientBrush>-Klasse finden Sie unter Übersicht über das Zeichnen [mit voll Tonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithradialgradientbrush"></a>   
## <a name="paint-with-a-radial-gradient"></a>Zeichnen mit einem radialen Farbverlauf  
 Ein-<xref:System.Windows.Media.RadialGradientBrush> zeichnet einen Bereich mit einem radialen Farbverlauf. Ein Radialer Farbverlauf kombiniert mindestens zwei Farben in einem Kreis. Wie bei der <xref:System.Windows.Media.LinearGradientBrush>-Klasse verwenden Sie <xref:System.Windows.Media.GradientStop>-Objekte, um die Farben im Farbverlauf und deren Positionen anzugeben.  
  
 Im folgenden Beispiel wird ein-<xref:System.Windows.Media.RadialGradientBrush> verwendet, um die <xref:System.Windows.Shapes.Shape.Fill%2A> eines <xref:System.Windows.Shapes.Rectangle>zu zeichnen. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mit einem RadialGradientBrush gezeichnetes Rechteck](./media/graphicsmm-brush-ovw-radialgradientbrush.jpg "graphicsmm_brush_ovw_radialgradientbrush")  
Ein mit einem RadialGradientBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 Weitere Informationen zur <xref:System.Windows.Media.RadialGradientBrush>-Klasse finden Sie unter Übersicht über das Zeichnen [mit voll Tonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithimage"></a>   
## <a name="paint-with-an-image"></a>Zeichnen mit einem Bild  
 Ein-<xref:System.Windows.Media.ImageBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.ImageSource>.  
  
 Im folgenden Beispiel wird ein-<xref:System.Windows.Media.ImageBrush> verwendet, um die <xref:System.Windows.Shapes.Shape.Fill%2A> eines <xref:System.Windows.Shapes.Rectangle>zu zeichnen. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein Rechteck, das von einem ImageBrush gezeichnet wird.](./media/graphicsmm-brush-ovw-imagebrush.jpg "graphicsmm_brush_ovw_imagebrush")  
Ein mithilfe eines Bilds gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 Weitere Informationen zum <xref:System.Windows.Media.ImageBrush>-Klasse finden Sie unterzeichnen [mit Bildern, Zeichnungen und visuellen](painting-with-images-drawings-and-visuals.md)Elementen.  
  
<a name="paintwithdrawing"></a>   
## <a name="paint-with-a-drawing"></a>Zeichnen mit einer Zeichnung  
 Ein <xref:System.Windows.Media.DrawingBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.Drawing>. Eine <xref:System.Windows.Media.Drawing> kann Formen, Bilder, Text und Medien enthalten.  
  
 Im folgenden Beispiel wird ein-<xref:System.Windows.Media.DrawingBrush> verwendet, um die <xref:System.Windows.Shapes.Shape.Fill%2A> eines <xref:System.Windows.Shapes.Rectangle>zu zeichnen. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mit einem DrawingBrush gezeichnetes Rechteck](./media/graphicsmm-brush-ovw-drawingbrush.jpg "graphicsmm_brush_ovw_drawingbrush")  
Ein mit einem DrawingBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 Weitere Informationen zum <xref:System.Windows.Media.DrawingBrush>-Klasse finden Sie unterzeichnen [mit Bildern, Zeichnungen und visuellen](painting-with-images-drawings-and-visuals.md)Elementen.  
  
<a name="paintwithvisual"></a>   
## <a name="paint-with-a-visual"></a>Zeichnen mit einem visuellen Element  
 Ein-<xref:System.Windows.Media.VisualBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.Visual>-Objekt. Beispiele für visuelle Objekte sind <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Page>und <xref:System.Windows.Controls.MediaElement>. Mit einem <xref:System.Windows.Media.VisualBrush> können Sie auch Inhalte aus einem Teil der Anwendung in einen anderen Bereich projizieren. Dies ist sehr nützlich für das Erstellen von reflektioneffekten und Vergrößerungs Teilen des Bildschirms.  
  
 Im folgenden Beispiel wird ein-<xref:System.Windows.Media.VisualBrush> verwendet, um die <xref:System.Windows.Shapes.Shape.Fill%2A> eines <xref:System.Windows.Shapes.Rectangle>zu zeichnen. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mithilfe eines VisualBrush gezeichnetes Rechteck](./media/graphicsmm-brush-ovw-visualbrush.jpg "graphicsmm_brush_ovw_visualbrush")  
Ein mithilfe eines VisualBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 Weitere Informationen zum <xref:System.Windows.Media.VisualBrush>-Klasse finden Sie unterzeichnen [mit Bildern, Zeichnungen und visuellen](painting-with-images-drawings-and-visuals.md)Elementen.  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>   
## <a name="paint-using-predefined-and-system-brushes"></a>Zeichnen mithilfe vordefinierter und System Pinsel  
 Der praktische Windows Presentation Foundation (WPF) stellt einen Satz vordefinierter und System Pinsel bereit, mit denen Sie Objekte zeichnen können.  
  
- Eine Liste der verfügbaren vordefinierten Pinsel finden Sie in der <xref:System.Windows.Media.Brushes>-Klasse. Ein Beispiel für die Verwendung eines vordefinierten Pinsels finden Sie unter [Zeichnen eines Bereichs mit einer voll Tonfarbe](how-to-paint-an-area-with-a-solid-color.md).  
  
- Eine Liste der verfügbaren System Pinsel finden Sie in der <xref:System.Windows.SystemColors>-Klasse. Ein Beispiel finden Sie unter [Zeichnen eines Bereichs mit einem System Pinsel](how-to-paint-an-area-with-a-system-brush.md).  
  
<a name="commonbrushfeatures"></a>   
## <a name="common-brush-features"></a>Allgemeine Pinsel Features  
 <xref:System.Windows.Media.Brush> Objekte stellen eine <xref:System.Windows.Media.Brush.Opacity%2A> Eigenschaft bereit, die verwendet werden kann, um einen Pinsel transparent oder teilweise transparent zu machen. Ein <xref:System.Windows.Media.Brush.Opacity%2A> Wert von 0 macht einen Pinsel vollständig transparent, während der <xref:System.Windows.Media.Brush.Opacity%2A> Wert 1 einen Pinsel vollständig deckend macht. Im folgenden Beispiel wird die <xref:System.Windows.Media.Brush.Opacity%2A>-Eigenschaft verwendet, um einen <xref:System.Windows.Media.SolidColorBrush> 25% nicht transparent zu machen.  
  
 [!code-xaml[BrushOverviewExamples_snip#OpacityExample1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 Wenn der Pinsel Farben enthält, die teilweise transparent sind, wird der Deckkraft Wert der Farbe durch Multiplikation mit dem Deckkraft Wert des Pinsels kombiniert. Wenn ein Pinsel z. b. einen Deckkraft Wert von 0,5 hat und eine im Pinsel verwendete Farbe auch einen Deckkraft Wert von 0,5 aufweist, hat die Ausgabe Farbe einen Deckkraft Wert von 0,25.  
  
> [!NOTE]
> Es ist effizienter, den Wert für die Deckkraft eines Pinsels zu ändern, als die Deckkraft eines gesamten Elements mithilfe der <xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType>-Eigenschaft zu ändern.  
  
 Sie können den Inhalt eines Pinsels drehen, skalieren, neigen und übersetzen, indem Sie dessen <xref:System.Windows.Media.Brush.Transform%2A> oder <xref:System.Windows.Media.Brush.RelativeTransform%2A> Eigenschaften verwenden. Weitere Informationen finden Sie unter [Übersicht über die Transformation für Pinsel](brush-transformation-overview.md).  
  
 Da es sich um <xref:System.Windows.Media.Animation.Animatable> Objekte handelt, können <xref:System.Windows.Media.Brush> Objekte animiert werden. Weitere Informationen finden Sie unter [Übersicht über Animation](animation-overview.md).  
  
<a name="freezable_features"></a>   
### <a name="freezable-features"></a>Features von Freezable  
 Da es von der <xref:System.Windows.Freezable>-Klasse erbt, bietet die <xref:System.Windows.Media.Brush>-Klasse mehrere besondere Features: <xref:System.Windows.Media.Brush> Objekte können als [Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)deklariert, von mehreren Objekten gemeinsam genutzt und geklont werden. Außerdem können alle <xref:System.Windows.Media.Brush> Typen außer <xref:System.Windows.Media.VisualBrush> schreibgeschützt werden, um die Leistung zu verbessern und Thread sicher zu machen.  
  
 Weitere Informationen zu den verschiedenen Funktionen, die von <xref:System.Windows.Freezable> Objekten bereitgestellt werden, finden Sie unter [Übersicht über](../advanced/freezable-objects-overview.md)frei wählbare Objekte.  
  
 Weitere Informationen dazu, warum <xref:System.Windows.Media.VisualBrush> Objekte nicht eingefroren werden können, finden Sie auf der Seite <xref:System.Windows.Media.VisualBrush>-Typ.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Brush>
- <xref:System.Windows.Media.Brushes>
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md)
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
- [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md)
- [Beispiel für Pinsel](https://go.microsoft.com/fwlink/?LinkID=159973)
- [ImageBrush-Beispiel](https://go.microsoft.com/fwlink/?LinkID=160005)
- [VisualBrush-Beispiel](https://go.microsoft.com/fwlink/?LinkID=160049)
- [Gewusst wie-Themen](brushes-how-to-topics.md)
- [Weitere Leistungsempfehlungen](../advanced/optimizing-performance-other-recommendations.md)
