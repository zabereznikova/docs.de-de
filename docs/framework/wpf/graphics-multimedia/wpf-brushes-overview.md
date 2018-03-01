---
title: "Übersicht über WPF-Pinsel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], about brushes
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ec7e566e6f56c215bbaeafdfb5c5e97cc0add0bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="wpf-brushes-overview"></a>Übersicht über WPF-Pinsel
Alles, was auf dem Bildschirm sichtbar ist sichtbar, da er von einem Pinsel gezeichnet wurde. Z. B. wird ein Pinsel verwendet, um den Hintergrund einer Schaltfläche, die Vordergrundfarbe des Texts und der Ausfüllen einer Form zu beschreiben. In diesem Thema werden die Konzepte der Zeichnung mit [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Pinsel und stellt Beispiele bereit. Mithilfe von Pinseln können Sie [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-Objekte, angefangen von einfachen Objekten, über Objekte in Volltonfarbe bis hin zu Objekten mit komplexen von Mustern und Bildern, zeichnen.  
  
<a name="paintingwithbrush"></a>   
## <a name="painting-with-a-brush"></a>Zeichnen mit einem Pinsel  
 Ein <xref:System.Windows.Media.Brush> "zeichnet einen Bereich mit der Ausgabe". Unterschiedlicher Pinsel werden verschiedene Typen der Ausgabe aufweisen. Einige Pinsel zeichnen einen Bereich mit einer Volltonfarbe, andere Personen mit einem Farbverlauf, Muster, Bild oder Zeichnung. Die folgende Abbildung zeigt Beispiele für jeden der verschiedenen <xref:System.Windows.Media.Brush> Typen.  
  
 ![Pinseltypen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brushtypes.jpg "Graphicsmm_brushtypes")  
Pinsel-Beispiele  
  
 Die meisten visuellen Objekte können Sie angeben, wie sie gezeichnet werden. Die folgende Tabelle enthält einige allgemeine Objekte und Eigenschaften, die mit dem können Sie eine <xref:System.Windows.Media.Brush>.  
  
|Klasse|Pinseleigenschaften|  
|-----------|----------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 Die folgenden Abschnitte beschreiben die verschiedenen <xref:System.Windows.Media.Brush> Typen, und geben Sie jeweils ein Beispiel.  
  
<a name="paintwithsolidcolorbrush"></a>   
## <a name="paint-with-a-solid-color"></a>Zeichnen mit einer Volltonfarbe aus  
 Ein <xref:System.Windows.Media.SolidColorBrush> zeichnet einen Bereich mit einer einfarbigen <xref:System.Windows.Media.Color>. Gibt es eine Vielzahl von Möglichkeiten zum Angeben der <xref:System.Windows.Media.SolidColorBrush.Color%2A> von einer <xref:System.Windows.Media.SolidColorBrush>: Beispielsweise können Sie über Kanäle alpha, roten, blauen und Grün geben oder verwenden Sie eine der vordefinierten Farben gebotenen der <xref:System.Windows.Media.Colors> Klasse.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.SolidColorBrush> zum Zeichnen der <xref:System.Windows.Shapes.Shape.Fill%2A> von einem <xref:System.Windows.Shapes.Rectangle>. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mit einem SolidColorBrush gezeichnetes Rechteck](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-solidcolorbrush.png "Graphicsmm_brush_ovw_solidcolorbrush")  
Ein mit einem SolidColorBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 Weitere Informationen zu den <xref:System.Windows.Media.SolidColorBrush> Klasse, finden Sie unter [Zeichnen mit Volltonfarben und Farbverläufen (Übersicht)](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithlineargradientbrush"></a>   
## <a name="paint-with-a-linear-gradient"></a>Zeichnen mit einem linearen Farbverlauf  
 Ein <xref:System.Windows.Media.LinearGradientBrush> zeichnet einen Bereich mit einem linearen Farbverlauf. Ein linearer Farbverlauf kombiniert zwei oder mehr Farben entlang einer Linie, der Farbverlaufsachse. Verwenden Sie <xref:System.Windows.Media.GradientStop> Objekte, um die Farben in der Farbverlauf und ihre relativen Positionen anzugeben.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.LinearGradientBrush> zum Zeichnen der <xref:System.Windows.Shapes.Shape.Fill%2A> von einem <xref:System.Windows.Shapes.Rectangle>. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mit einem LinearGradientBrush gezeichnetes Rechteck](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-lineargradientbrush.jpg "Graphicsmm_brush_ovw_lineargradientbrush")  
Ein mit einem LinearGradientBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 Weitere Informationen zu den <xref:System.Windows.Media.LinearGradientBrush> Klasse, finden Sie unter [Zeichnen mit Volltonfarben und Farbverläufen (Übersicht)](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithradialgradientbrush"></a>   
## <a name="paint-with-a-radial-gradient"></a>Zeichnen mit einem radialen Farbverlauf  
 Ein <xref:System.Windows.Media.RadialGradientBrush> zeichnet einen Bereich mit einem radialen Farbverlauf. Ein Radialer Farbverlauf kombiniert zwei oder mehr Farben über ein Kreis. Wie bei der <xref:System.Windows.Media.LinearGradientBrush> -Klasse, verwenden Sie <xref:System.Windows.Media.GradientStop> Objekte, um die Farben in der Farbverlauf und ihre relativen Positionen anzugeben.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.RadialGradientBrush> zum Zeichnen der <xref:System.Windows.Shapes.Shape.Fill%2A> von einem <xref:System.Windows.Shapes.Rectangle>. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mit einem RadialGradientBrush gezeichnetes Rechteck](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-radialgradientbrush.jpg "Graphicsmm_brush_ovw_radialgradientbrush")  
Ein mit einem RadialGradientBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 Weitere Informationen zu den <xref:System.Windows.Media.RadialGradientBrush> Klasse, finden Sie unter [Zeichnen mit Volltonfarben und Farbverläufen (Übersicht)](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithimage"></a>   
## <a name="paint-with-an-image"></a>Zeichnen mit einem Bild  
 Ein <xref:System.Windows.Media.ImageBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.ImageSource>.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.ImageBrush> zum Zeichnen der <xref:System.Windows.Shapes.Shape.Fill%2A> von einem <xref:System.Windows.Shapes.Rectangle>. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein Rechteck mit einem ImageBrush gezeichnetes](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-imagebrush.jpg "Graphicsmm_brush_ovw_imagebrush")  
Ein mit einem Bild gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 Weitere Informationen zu den <xref:System.Windows.Media.ImageBrush> Klasse, finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithdrawing"></a>   
## <a name="paint-with-a-drawing"></a>Zeichnen mit einer Zeichnung  
 Ein <xref:System.Windows.Media.DrawingBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.Drawing>. Ein <xref:System.Windows.Media.Drawing> Formen, Bilder, Text und Medien enthalten können.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingBrush> zum Zeichnen der <xref:System.Windows.Shapes.Shape.Fill%2A> von einem <xref:System.Windows.Shapes.Rectangle>. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mit einem DrawingBrush gezeichnetes Rechteck](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-drawingbrush.jpg "Graphicsmm_brush_ovw_drawingbrush")  
Ein mit einem DrawingBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 Weitere Informationen zu den <xref:System.Windows.Media.DrawingBrush> Klasse, finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithvisual"></a>   
## <a name="paint-with-a-visual"></a>Paint mit einer Visualisierung  
 Ein <xref:System.Windows.Media.VisualBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.Visual> Objekt. Beispiele für visuelle Objekte <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Page>, und <xref:System.Windows.Controls.MediaElement>. Ein <xref:System.Windows.Media.VisualBrush> ermöglicht auch zum projizieren von Inhalten von einem Teil der Anwendung in einem anderen Bereich; diese Funktion ist hilfreich zum Erstellen von Reflektion Auswirkungen und Teile des Bildschirms vergrößern.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.VisualBrush> zum Zeichnen der <xref:System.Windows.Shapes.Shape.Fill%2A> von einem <xref:System.Windows.Shapes.Rectangle>. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mit einem VisualBrush gezeichnetes Rechteck](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-visualbrush.jpg "Graphicsmm_brush_ovw_visualbrush")  
Ein mit einem VisualBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 Weitere Informationen zu den <xref:System.Windows.Media.VisualBrush> Klasse, finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>   
## <a name="paint-using-predefined-and-system-brushes"></a>Zeichnen Sie mit vordefinierten und Systempinsel  
 Der Einfachheit halber [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] bietet einen Satz vordefinierter und System Pinsel, dass Sie zum Zeichnen von Objekten verwenden können.  
  
-   Eine Liste der verfügbaren vordefinierten Pinsel, finden Sie unter der <xref:System.Windows.Media.Brushes> Klasse. Ein Beispiel zum Verwenden eines vordefinierten Pinsels finden Sie unter [Zeichnen eines Bereichs mit einer Volltonfarbe](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-solid-color.md).  
  
-   Eine Liste der verfügbaren Systempinsel, finden Sie unter der <xref:System.Windows.SystemColors> Klasse. Ein Beispiel finden Sie unter [Zeichnen eines Bereichs mit einem Systempinsel](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md).  
  
<a name="commonbrushfeatures"></a>   
## <a name="common-brush-features"></a>Allgemeine Pinsel-Funktionen  
 <xref:System.Windows.Media.Brush>-Objekte stellen eine <xref:System.Windows.Media.Brush.Opacity%2A> -Eigenschaft, die verwendet werden kann, um einen Pinsel transparent oder teilweise transparent machen. Ein <xref:System.Windows.Media.Brush.Opacity%2A> der Wert 0 wird ein Pinsel völlig transparent, während ein <xref:System.Windows.Media.Brush.Opacity%2A> Wert 1 wird ein Pinsel vollständig deckend. Im folgenden Beispiel wird die <xref:System.Windows.Media.Brush.Opacity%2A> Eigenschaft, um eine <xref:System.Windows.Media.SolidColorBrush> 25 Prozent.  
  
 [!code-xaml[BrushOverviewExamples_snip#OpacityExample1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 Wenn der Pinsel Farben, die teilweise transparent sind enthält, wird der Wert für die Deckkraft der Farbe durch Multiplikation mit dem Wert für die Deckkraft des Pinsels kombiniert. Wenn ein Pinsel einen Wert für die Deckkraft von 0,5 hat und eine Farbe, die in den Pinsel verwendet verfügt auch über einen Wert für die Deckkraft von 0,5, hat die Ausgabefarbe Durchlässigkeitswert 0,25.  
  
> [!NOTE]
>  Es ist jedoch effizienter, den Wert für die Deckkraft eines Pinsels ändern, als dies so ändern Sie die Deckkraft eines gesamten Element mithilfe der <xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType> Eigenschaft.  
  
 Sie können drehen, skalieren, neigen und übersetzen Sie den Inhalt eines Pinsels mit seiner <xref:System.Windows.Media.Brush.Transform%2A> oder <xref:System.Windows.Media.Brush.RelativeTransform%2A> Eigenschaften. Weitere Informationen finden Sie unter [Pinsel Transformation Overview](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md).  
  
 Da sie sind <xref:System.Windows.Media.Animation.Animatable> Objekte <xref:System.Windows.Media.Brush> Objekte animiert werden können. Weitere Informationen finden Sie unter [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="freezable_features"></a>   
### <a name="freezable-features"></a>Funktionen von Freezable-Objekten  
 Da es erbt die <xref:System.Windows.Freezable> -Klasse, die <xref:System.Windows.Media.Brush> Klasse bietet verschiedene Sonderfunktionen: <xref:System.Windows.Media.Brush> deklarierte Objekte als [Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)für mehrere Objekte freigegeben und geklont. Darüber hinaus alle der <xref:System.Windows.Media.Brush> Typen außer <xref:System.Windows.Media.VisualBrush> zur Verbesserung der Leistung mit Schreibschutz versehen wurden und Thread-sichere vorgenommen werden können.  
  
 Weitere Informationen zu den verschiedenen Features von <xref:System.Windows.Freezable> anzuzeigen, [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Weitere Informationen dazu, warum <xref:System.Windows.Media.VisualBrush> Objekte nicht fixiert, finden Sie unter der <xref:System.Windows.Media.VisualBrush> Seite ".  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Brush>  
 <xref:System.Windows.Media.Brushes>  
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Beispiel für Pinsel](http://go.microsoft.com/fwlink/?LinkID=159973)  
 [ImageBrush-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160005)  
 [VisualBrush-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160049)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/brushes-how-to-topics.md)  
 [Weitere Leistungsempfehlungen](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
