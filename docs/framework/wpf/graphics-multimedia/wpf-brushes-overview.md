---
title: "&#220;bersicht &#252;ber WPF-Pinsel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Pinsel, Informationen über Pinsel"
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# &#220;bersicht &#252;ber WPF-Pinsel
Alles, was auf dem Bildschirm sichtbar ist, ist sichtbar, weil es mit einem Pinsel gezeichnet wurde.  Mit einem Pinsel werden z. B. der Hintergrund einer Schaltfläche, der Vordergrund von Text und die Füllung einer Form beschrieben.  In diesem Thema werden die Begriffe zum Zeichnen mit [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Pinseln erklärt und Beispiele bereitgestellt.  Mithilfe von Pinseln können Sie [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]\-Objekte, angefangen von einfachen Objekten über Objekte in Volltonfarbe bis hin zu Objekten mit komplexen Mustern und Bildern, zeichnen.  
  
<a name="paintingwithbrush"></a>   
## Zeichnen mit einem Pinsel  
 Ein <xref:System.Windows.Media.Brush> "zeichnet" einen Bereich mit zugehöriger Ausgabe.  Je nach Pinsel kann die Ausgabe einen anderen Typ aufweisen.  Einige Pinsel zeichnen einen Bereich mit einer Volltonfarbe, andere mit einem Farbverlauf, Muster, Bild oder einer Zeichnung.  Die folgende Abbildung zeigt Beispiele für jeden der verschiedenen <xref:System.Windows.Media.Brush>\-Typen.  
  
 ![Pinseltypen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brushtypes.png "graphicsmm\_brushtypes")  
  
        Beispiele für Pinsel  
  
 Bei den meisten visuellen Objekten können Sie angeben, wie sie gezeichnet werden.  In der folgenden Tabelle werden einige allgemeine Objekte und Eigenschaften aufgelistet, mit denen Sie einen <xref:System.Windows.Media.Brush> verwenden können.  
  
|Klasse|Pinseleigenschaften|  
|------------|-------------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 In den folgenden Abschnitten werden die verschiedenen <xref:System.Windows.Media.Brush>\-Typen beschrieben und jeweils ein Beispiel bereitgestellt.  
  
<a name="paintwithsolidcolorbrush"></a>   
## Zeichnen mit einer Volltonfarbe  
 Ein <xref:System.Windows.Media.SolidColorBrush> zeichnet einen Bereich mit einer Vollton\-<xref:System.Windows.Media.Color>.  Es gibt viele Möglichkeiten, die <xref:System.Windows.Media.SolidColorBrush.Color%2A> für einen <xref:System.Windows.Media.SolidColorBrush> anzugeben: Sie können beispielsweise den Alpha\-, Rot\-, Blau\- und Grünkanal angeben oder eine der vordefinierten Farben verwenden, die von der <xref:System.Windows.Media.Colors>\-Klasse bereitgestellt werden.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.SolidColorBrush> verwendet, um die <xref:System.Windows.Shapes.Shape.Fill%2A> für ein <xref:System.Windows.Shapes.Rectangle> zu zeichnen.  In der folgenden Abbildung ist das gezeichnete Rechteck dargestellt.  
  
 ![Ein mit einem SolidColorBrush gezeichnetes Rechteck](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm\_brush\_ovw\_solidcolorbrush")  
  
        Mit SolidColorBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 Weitere Informationen über die <xref:System.Windows.Media.SolidColorBrush>\-Klasse finden Sie unter [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithlineargradientbrush"></a>   
## Zeichnen mit einem linearen Farbverlauf  
 Ein <xref:System.Windows.Media.LinearGradientBrush> zeichnet einen Bereich mit einem linearen Farbverlauf.  Ein linearer Farbverlauf mischt zwei oder mehr Farben entlang einer Linie, der Farbverlaufsachse.  Sie verwenden <xref:System.Windows.Media.GradientStop>\-Objekte, um die Farben und ihre Positionen im Farbverlauf anzugeben.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.LinearGradientBrush> verwendet, um die <xref:System.Windows.Shapes.Shape.Fill%2A> für ein <xref:System.Windows.Shapes.Rectangle> zu zeichnen.  In der folgenden Abbildung ist das gezeichnete Rechteck dargestellt.  
  
 ![Ein mit einem LinearGradientBrush gezeichnetes Rechteck](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-lineargradientbrush.png "graphicsmm\_brush\_ovw\_lineargradientbrush")  
  
        Mit LinearGradientBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 Weitere Informationen über die <xref:System.Windows.Media.LinearGradientBrush>\-Klasse finden Sie unter [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithradialgradientbrush"></a>   
## Zeichnen mit einem radialen Farbverlauf  
 Ein <xref:System.Windows.Media.RadialGradientBrush> zeichnet einen Bereich mit einem radialen Farbverlauf.  Ein radialer Farbverlauf mischt zwei oder mehr Farben entlang eines Kreises.  Wie bei der <xref:System.Windows.Media.LinearGradientBrush>\-Klasse verwenden Sie <xref:System.Windows.Media.GradientStop>\-Objekte, um die Farben und ihre Positionen im Farbverlauf anzugeben.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.RadialGradientBrush> verwendet, um die <xref:System.Windows.Shapes.Shape.Fill%2A> für ein <xref:System.Windows.Shapes.Rectangle> zu zeichnen.  In der folgenden Abbildung ist das gezeichnete Rechteck dargestellt.  
  
 ![Ein mit einem RadialGradientBrush gezeichnetes Rechteck](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-radialgradientbrush.png "graphicsmm\_brush\_ovw\_radialgradientbrush")  
  
        Mit RadialGradientBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 Weitere Informationen über die <xref:System.Windows.Media.RadialGradientBrush>\-Klasse finden Sie unter [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithimage"></a>   
## Zeichnen mit einem Bild  
 Ein <xref:System.Windows.Media.ImageBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.ImageSource>\-Element.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.ImageBrush> verwendet, um die <xref:System.Windows.Shapes.Shape.Fill%2A> von einem <xref:System.Windows.Shapes.Rectangle> zu zeichnen.  In der folgenden Abbildung ist das gezeichnete Rechteck dargestellt.  
  
 ![Ein mit einem ImageBrush gezeichnetes Rechteck](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-imagebrush.png "graphicsmm\_brush\_ovw\_imagebrush")  
  
        Mit einem Bild gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 Weitere Informationen über die <xref:System.Windows.Media.ImageBrush>\-Klasse finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithdrawing"></a>   
## Zeichnen mit einer Zeichnung  
 Ein <xref:System.Windows.Media.DrawingBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.Drawing>\-Element.  Eine <xref:System.Windows.Media.Drawing> kann Formen, Bilder, Text und Medien enthalten.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.DrawingBrush> verwendet, um die <xref:System.Windows.Shapes.Shape.Fill%2A> für ein <xref:System.Windows.Shapes.Rectangle> zu zeichnen.  In der folgenden Abbildung ist das gezeichnete Rechteck dargestellt.  
  
 ![Ein mit einem DrawingBrush gezeichnetes Rechteck](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-drawingbrush.png "graphicsmm\_brush\_ovw\_drawingbrush")  
  
        Mit DrawingBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 Weitere Informationen über die <xref:System.Windows.Media.DrawingBrush>\-Klasse finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithvisual"></a>   
## Zeichnen mit einem visuellen Element  
 Ein <xref:System.Windows.Media.VisualBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.Visual>\-Objekt.  Beispiele für visuelle Objekte sind: <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Page> und <xref:System.Windows.Controls.MediaElement>.  Mit einem <xref:System.Windows.Media.VisualBrush> können Sie Inhalt von einem Teil der Anwendung in einen anderen Bereich projizieren. Dies ist beim Erstellen von Reflektionseffekten und beim Vergrößern von Teilen des Bildschirms sehr nützlich.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.VisualBrush> verwendet, um die <xref:System.Windows.Shapes.Shape.Fill%2A> für ein <xref:System.Windows.Shapes.Rectangle> zu zeichnen.  In der folgenden Abbildung ist das gezeichnete Rechteck dargestellt.  
  
 ![Ein mit einem VisualBrush gezeichnetes Rechteck](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-visualbrush.png "graphicsmm\_brush\_ovw\_visualbrush")  
  
        Mit VisualBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 Weitere Informationen über die <xref:System.Windows.Media.VisualBrush>\-Klasse finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>   
## Zeichnen mit vordefinierten Pinseln und Systempinseln  
 Der Einfachheit halber stellt [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] ein Set von vordefinierten Pinseln und Systempinseln bereit, die Sie zum Zeichnen von Objekten verwenden können.  
  
-   Eine Liste der verfügbaren vordefinierten Pinsel finden Sie in der <xref:System.Windows.Media.Brushes>\-Klasse.  Ein Beispiel, das die Verwendung eines vordefinierten Pinsels veranschaulicht, finden Sie unter [Zeichnen eines Bereichs mit einer Volltonfarbe](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-solid-color.md).  
  
-   Eine Liste der verfügbaren Systempinsel finden Sie in der <xref:System.Windows.SystemColors>\-Klasse.  Ein Beispiel finden Sie unter [Zeichnen eines Bereichs mit einem Systempinsel](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md).  
  
<a name="commonbrushfeatures"></a>   
## Allgemeine Pinselfeatures  
 <xref:System.Windows.Media.Brush>\-Objekte stellen eine <xref:System.Windows.Media.Brush.Opacity%2A>\-Eigenschaft bereit, die verwendet werden kann, um einen Pinsel transparent oder teilweise transparent zu machen.  Bei einem <xref:System.Windows.Media.Brush.Opacity%2A>\-Wert von 0 \(null\) wird ein Pinsel völlig transparent, während er bei einem <xref:System.Windows.Media.Brush.Opacity%2A>\-Wert von 1 völlig deckend wird.  Im folgenden Beispiel wird die <xref:System.Windows.Media.Brush.Opacity%2A>\-Eigenschaft verwendet, um für einen <xref:System.Windows.Media.SolidColorBrush> eine Durchlässigkeit von 25 Prozent festzulegen.  
  
 [!code-xml[BrushOverviewExamples_snip#OpacityExample1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 Wenn der Pinsel Farben enthält, die teilweise transparent sind, wird der Durchlässigkeitswert der Farbe durch Multiplikation mit dem Durchlässigkeitswert des Pinsels kombiniert.  Wenn z. B. ein Pinsel einen Durchlässigkeitswert von 0,5 und eine im Pinsel verwendete Farbe ebenfalls einen Durchlässigkeitswert von 0,5 aufweist, hat die Ausgabefarbe einen Durchlässigkeitswert von 0,25.  
  
> [!NOTE]
>  Es ist effizienter, den Durchlässigkeitswert eines Pinsels als die Durchlässigkeit eines gesamten Elements mit der <xref:System.Windows.UIElement.Opacity%2A?displayProperty=fullName>\-Eigenschaft zu ändern.  
  
 Sie können den Inhalt eines Pinsels drehen, skalieren, neigen und übersetzen, indem Sie seine <xref:System.Windows.Media.Brush.Transform%2A>\-Eigenschaft oder <xref:System.Windows.Media.Brush.RelativeTransform%2A>\-Eigenschaft verwenden.  Weitere Informationen finden Sie unter [Übersicht über Pinseltransformationen](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md).  
  
 Da es sich um <xref:System.Windows.Media.Animation.Animatable>\-Objekte handelt, können <xref:System.Windows.Media.Brush>\-Objekte animiert werden.  Weitere Informationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="freezable_features"></a>   
### Features von Freezable  
 Da sie von der <xref:System.Windows.Freezable>\-Klasse erbt, stellt die <xref:System.Windows.Media.Brush>\-Klasse mehrere spezielle Features bereit: <xref:System.Windows.Media.Brush>\-Objekte können als [Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md) deklariert, von mehreren Objekten gemeinsam genutzt und geklont werden.  Außerdem können alle <xref:System.Windows.Media.Brush>\-Typen, ausgenommen <xref:System.Windows.Media.VisualBrush>, zur Leistungssteigerung als schreibgeschützt und als threadsicher festgelegt werden.  
  
 Weitere Informationen über die verschiedenen von <xref:System.Windows.Freezable>\-Objekten bereitgestellten Features finden Sie unter [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Weitere Informationen darüber, warum <xref:System.Windows.Media.VisualBrush>\-Objekte nicht fixiert werden können, finden Sie auf der Seite für den <xref:System.Windows.Media.VisualBrush>\-Typ.  
  
## Siehe auch  
 <xref:System.Windows.Media.Brush>   
 <xref:System.Windows.Media.Brushes>   
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Beispiel für Pinsel](http://go.microsoft.com/fwlink/?LinkID=159973)   
 [Beispiel zu ImageBrush](http://go.microsoft.com/fwlink/?LinkID=160005)   
 [Beispiel zu VisualBrush](http://go.microsoft.com/fwlink/?LinkID=160049)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/brushes-how-to-topics.md)   
 [Weitere Leistungsempfehlungen](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)