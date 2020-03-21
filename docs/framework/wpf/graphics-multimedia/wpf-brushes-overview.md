---
title: Pinsel übersicht
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], about brushes
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
ms.openlocfilehash: 7a9474b392052900952f5b677ad94b16025de8dd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186576"
---
# <a name="wpf-brushes-overview"></a>Übersicht über WPF-Pinsel
Alles, was auf dem Bildschirm sichtbar ist, ist sichtbar, weil es mit einem Pinsel gemalt wurde. Ein Pinsel wird beispielsweise verwendet, um den Hintergrund einer Schaltfläche, den Vordergrund des Textes und die Füllung einer Form zu beschreiben. In diesem Thema werden [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] die Konzepte der Malerei mit Pinsel vorgestellt und Beispiele vorgestellt. Mithilfe von Pinseln können Sie [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-Objekte, angefangen von einfachen Objekten, über Objekte in Volltonfarbe bis hin zu Objekten mit komplexen von Mustern und Bildern, zeichnen.  
  
<a name="paintingwithbrush"></a>
## <a name="painting-with-a-brush"></a>Malen mit einem Pinsel  
 Ein <xref:System.Windows.Media.Brush> "malt" einen Bereich mit seiner Ausgabe. Verschiedene Pinsel haben unterschiedliche Ausgabetypen. Einige Pinsel zeichnen einen Bereich mit einer Volltonfarbe, andere mit einem Farbverlauf, Muster, Bild oder Zeichnung. Die folgende Abbildung zeigt Beispiele <xref:System.Windows.Media.Brush> für die einzelnen Typen.  
  
 ![Pinseltypen](./media/graphicsmm-brushtypes.jpg "graphicsmm_brushtypes")  
Pinselbeispiele  
  
 Mit den meisten visuellen Objekten können Sie angeben, wie sie gezeichnet werden. In der folgenden Tabelle sind einige allgemeine Objekte <xref:System.Windows.Media.Brush>und Eigenschaften aufgeführt, mit denen Sie eine verwenden können.  
  
|Klasse|Pinseleigenschaften|  
|-----------|----------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 In den folgenden Abschnitten werden die verschiedenen <xref:System.Windows.Media.Brush> Typen beschrieben und ein Beispiel für jeden Typ gegeben.  
  
<a name="paintwithsolidcolorbrush"></a>
## <a name="paint-with-a-solid-color"></a>Malen mit einer Volltonfarbe  
 Ein <xref:System.Windows.Media.SolidColorBrush> zeichnet einen Bereich <xref:System.Windows.Media.Color>mit einem festen . Es gibt eine Vielzahl von <xref:System.Windows.Media.SolidColorBrush.Color%2A> Möglichkeiten, die von a <xref:System.Windows.Media.SolidColorBrush>anzugeben: Zum Beispiel können Sie seine Alpha-, Rot-, <xref:System.Windows.Media.Colors> Blau- und Grünen-Kanäle angeben oder einen der vordefinierten Farben verwenden, die von der Klasse bereitgestellt werden.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.SolidColorBrush> wird <xref:System.Windows.Shapes.Shape.Fill%2A> ein <xref:System.Windows.Shapes.Rectangle>verwendet, um die von zu malen. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mit einem SolidColorBrush gezeichnetes Rechteck](./media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm_brush_ovw_solidcolorbrush")  
Ein Rechteck, das mit einem SolidColorBrush gezeichnet wurde  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 Weitere Informationen zur <xref:System.Windows.Media.SolidColorBrush> Klasse finden Sie unter [Malerei mit Volltonfarben und Farbverläufen Übersicht](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithlineargradientbrush"></a>
## <a name="paint-with-a-linear-gradient"></a>Malen mit einem linearen Farbverlauf  
 Ein <xref:System.Windows.Media.LinearGradientBrush> zeichnet einen Bereich mit einem linearen Farbverlauf. Ein linearer Farbverlauf überblendt zwei oder mehr Farben über eine Linie, die Farbverlaufsachse. Sie <xref:System.Windows.Media.GradientStop> verwenden Objekte, um die Farben im Farbverlauf und deren Positionen anzugeben.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.LinearGradientBrush> wird <xref:System.Windows.Shapes.Shape.Fill%2A> ein <xref:System.Windows.Shapes.Rectangle>verwendet, um die von zu malen. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mit einem LinearGradientBrush gezeichnetes Rechteck](./media/graphicsmm-brush-ovw-lineargradientbrush.jpg "graphicsmm_brush_ovw_lineargradientbrush")  
Ein Rechteck, das mit einem LinearGradientBrush gezeichnet wird  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 Weitere Informationen zur <xref:System.Windows.Media.LinearGradientBrush> Klasse finden Sie unter [Malerei mit Volltonfarben und Farbverläufen Übersicht](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithradialgradientbrush"></a>
## <a name="paint-with-a-radial-gradient"></a>Malen mit radialem Farbverlauf  
 A <xref:System.Windows.Media.RadialGradientBrush> zeichnet einen Bereich mit einem radialen Farbverlauf. Ein radialer Farbverlauf überblendt zwei oder mehr Farben über einen Kreis. Wie bei <xref:System.Windows.Media.LinearGradientBrush> der Klasse <xref:System.Windows.Media.GradientStop> verwenden Sie Objekte, um die Farben im Farbverlauf und ihre Positionen anzugeben.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.RadialGradientBrush> wird <xref:System.Windows.Shapes.Shape.Fill%2A> ein <xref:System.Windows.Shapes.Rectangle>verwendet, um die von zu malen. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mit einem RadialGradientBrush gezeichnetes Rechteck](./media/graphicsmm-brush-ovw-radialgradientbrush.jpg "graphicsmm_brush_ovw_radialgradientbrush")  
Ein Rechteck, das mit einem RadialGradientBrush gezeichnet wurde  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 Weitere Informationen zur <xref:System.Windows.Media.RadialGradientBrush> Klasse finden Sie unter [Malerei mit Volltonfarben und Farbverläufen Übersicht](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithimage"></a>
## <a name="paint-with-an-image"></a>Malen mit einem Bild  
 Ein <xref:System.Windows.Media.ImageBrush> zeichnet einen Bereich <xref:System.Windows.Media.ImageSource>mit einem .  
  
 Im folgenden Beispiel <xref:System.Windows.Media.ImageBrush> wird <xref:System.Windows.Shapes.Shape.Fill%2A> ein <xref:System.Windows.Shapes.Rectangle>verwendet, um die von zu malen. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mit einem ImageBrush gezeichnetes Rechteck](./media/graphicsmm-brush-ovw-imagebrush.jpg "graphicsmm_brush_ovw_imagebrush")  
Ein Rechteck, das mit einem Bild gezeichnet wird  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 Weitere Informationen zur <xref:System.Windows.Media.ImageBrush> Klasse finden Sie unter [Malen mit Bildern, Zeichnungen und Visuals](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithdrawing"></a>
## <a name="paint-with-a-drawing"></a>Malen mit einer Zeichnung  
 Ein <xref:System.Windows.Media.DrawingBrush> zeichnet einen Bereich <xref:System.Windows.Media.Drawing>mit einem . A <xref:System.Windows.Media.Drawing> kann Formen, Bilder, Text und Medien enthalten.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.DrawingBrush> wird <xref:System.Windows.Shapes.Shape.Fill%2A> ein <xref:System.Windows.Shapes.Rectangle>verwendet, um die von zu malen. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mit einem DrawingBrush gezeichnetes Rechteck](./media/graphicsmm-brush-ovw-drawingbrush.jpg "graphicsmm_brush_ovw_drawingbrush")  
Ein Rechteck, das mit einem DrawingBrush gezeichnet wurde  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 Weitere Informationen zur <xref:System.Windows.Media.DrawingBrush> Klasse finden Sie unter [Malen mit Bildern, Zeichnungen und Visuals](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithvisual"></a>
## <a name="paint-with-a-visual"></a>Malen mit einem visuellen  
 Ein <xref:System.Windows.Media.VisualBrush> zeichnet einen Bereich <xref:System.Windows.Media.Visual> mit einem Objekt. Beispiele für Visual-Objekte sind <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Page>und <xref:System.Windows.Controls.MediaElement>. A <xref:System.Windows.Media.VisualBrush> ermöglicht es Ihnen auch, Inhalte aus einem Teil Ihrer Anwendung in einen anderen Bereich zu projizieren. Es ist sehr nützlich, um Reflexionseffekte zu erstellen und Teile des Bildschirms zu vergrößern.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.VisualBrush> wird <xref:System.Windows.Shapes.Shape.Fill%2A> ein <xref:System.Windows.Shapes.Rectangle>verwendet, um die von zu malen. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mit einem VisualBrush gezeichnetes Rechteck](./media/graphicsmm-brush-ovw-visualbrush.jpg "graphicsmm_brush_ovw_visualbrush")  
Ein Rechteck, das mit einem VisualBrush gezeichnet wurde  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 Weitere Informationen zur <xref:System.Windows.Media.VisualBrush> Klasse finden Sie unter [Malen mit Bildern, Zeichnungen und Visuals](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>
## <a name="paint-using-predefined-and-system-brushes"></a>Malen mit vordefinierten und Systempinsel  
 Der Einfachheit halber bietet Windows Presentation Foundation (WPF) eine Reihe vordefinierter und Systempinsel, mit denen Sie Objekte malen können.  
  
- Eine Liste der verfügbaren vordefinierten Pinsel <xref:System.Windows.Media.Brushes> finden Sie in der Klasse. Ein Beispiel, das zeigt, wie sie einen vordefinierten Pinsel verwenden, finden Sie unter [Zeichnen eines Bereichs mit einer Volltonfarbe](how-to-paint-an-area-with-a-solid-color.md).  
  
- Eine Liste der verfügbaren Systempinsel <xref:System.Windows.SystemColors> finden Sie in der Klasse. Ein Beispiel finden Sie unter [Zeichnen eines Bereichs mit einem Systempinsel](how-to-paint-an-area-with-a-system-brush.md).  
  
<a name="commonbrushfeatures"></a>
## <a name="common-brush-features"></a>Häufige Pinsel-Funktionen  
 <xref:System.Windows.Media.Brush>Objekte stellen <xref:System.Windows.Media.Brush.Opacity%2A> eine Eigenschaft bereit, die verwendet werden kann, um einen Pinsel transparent oder teilweise transparent zu machen. Ein <xref:System.Windows.Media.Brush.Opacity%2A> Wert von 0 macht einen <xref:System.Windows.Media.Brush.Opacity%2A> Pinsel vollständig transparent, während ein Wert von 1 einen Pinsel vollständig undurchsichtig macht. Im folgenden Beispiel <xref:System.Windows.Media.Brush.Opacity%2A> wird die <xref:System.Windows.Media.SolidColorBrush> Eigenschaft verwendet, um eine 25-prozentige Undurchsichtigkeit zu erstellen.  
  
 [!code-xaml[BrushOverviewExamples_snip#OpacityExample1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 Wenn der Pinsel Farben enthält, die teilweise transparent sind, wird der Deckkraftwert der Farbe durch Multiplikation mit dem Deckkraftwert des Pinsels kombiniert. Wenn ein Pinsel beispielsweise einen Deckkraftwert von 0,5 und eine Farbe, die im Pinsel verwendet wird, auch einen Deckkraftwert von 0,5 hat, hat die Ausgabefarbe einen Deckkraftwert von 0,25.  
  
> [!NOTE]
> Es ist effizienter, den Deckkraftwert eines Pinsels zu ändern, als die Deckkraft eines gesamten Elements mithilfe seiner <xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType> Eigenschaft zu ändern.  
  
 Sie können den Inhalt eines Pinsels drehen, skalieren, verzerren und übersetzen, indem Sie dessen <xref:System.Windows.Media.Brush.Transform%2A> oder <xref:System.Windows.Media.Brush.RelativeTransform%2A> Eigenschaften verwenden. Weitere Informationen finden Sie unter [Pinseltransformationsübersicht](brush-transformation-overview.md).  
  
 Da es <xref:System.Windows.Media.Animation.Animatable> sich <xref:System.Windows.Media.Brush> um Objekte handelt, können Objekte animiert werden. Weitere Informationen finden Sie unter [Übersicht über Animation](animation-overview.md).  
  
<a name="freezable_features"></a>
### <a name="freezable-features"></a>Features von Freezable  
 Da sie von der <xref:System.Windows.Freezable> Klasse <xref:System.Windows.Media.Brush> erbt, bietet <xref:System.Windows.Media.Brush> die Klasse mehrere spezielle Features: Objekte können als [Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)deklariert, von mehreren Objekten gemeinsam genutzt und geklont werden. Darüber hinaus können <xref:System.Windows.Media.Brush> alle <xref:System.Windows.Media.VisualBrush> Typen außer schreibgeschützt gemacht werden, um die Leistung zu verbessern und threadsicher zu machen.  
  
 Weitere Informationen zu den verschiedenen <xref:System.Windows.Freezable> Features, die von Objekten bereitgestellt werden, finden Sie unter Übersicht über [freisetzbare Objekte](../advanced/freezable-objects-overview.md).  
  
 Weitere Informationen dazu, warum <xref:System.Windows.Media.VisualBrush> Objekte nicht <xref:System.Windows.Media.VisualBrush> eingefroren werden können, finden Sie auf der Typseite.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.Brush>
- <xref:System.Windows.Media.Brushes>
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md)
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
- [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md)
- [Beispiel für Pinsel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)
- [Beispiel zu ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [VisualBrush-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
- [How-to-Themen](brushes-how-to-topics.md)
- [Weitere Leistungsempfehlungen](../advanced/optimizing-performance-other-recommendations.md)
