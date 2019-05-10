---
title: Übersicht über WPF-Pinsel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], about brushes
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
ms.openlocfilehash: a0de8aee53c5db63952e4baa72827a92c47ccce0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593379"
---
# <a name="wpf-brushes-overview"></a>Übersicht über WPF-Pinsel
Alles, was auf dem Bildschirm sichtbar ist sichtbar, da es mit einem Pinsel gezeichnet wurde. Beispielsweise wird ein Pinsel verwendet, um den Hintergrund einer Schaltfläche, die Vordergrundfarbe des Texts und des Ausfüllens einer Form zu beschreiben. In diesem Thema werden die Konzepte Zeichnen mit [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Pinsel und stellt Beispiele bereit. Mithilfe von Pinseln können Sie [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-Objekte, angefangen von einfachen Objekten, über Objekte in Volltonfarbe bis hin zu Objekten mit komplexen von Mustern und Bildern, zeichnen.  
  
<a name="paintingwithbrush"></a>   
## <a name="painting-with-a-brush"></a>Zeichnen mit einem Pinsel  
 Ein <xref:System.Windows.Media.Brush> "zeichnet einen Bereich mit der Ausgabe". Andere Pinsel haben unterschiedliche Arten von Ausgaben. Einige Pinsel zeichnen ein Bereichs mit einer Volltonfarbe, andere Personen mit einem Farbverlauf, Muster, Bild oder zeichnen. Die folgende Abbildung zeigt Beispiele für jeden der verschiedenen <xref:System.Windows.Media.Brush> Typen.  
  
 ![Pinseltypen](./media/graphicsmm-brushtypes.jpg "Graphicsmm_brushtypes")  
Beispiele für Pinsel  
  
 Die meisten visuellen Objekte können Sie angeben, wie sie gezeichnet werden. Die folgende Tabelle enthält einige allgemeine Objekte und Eigenschaften, die mit dem können Sie eine <xref:System.Windows.Media.Brush>.  
  
|Klasse|Pinseleigenschaften|  
|-----------|----------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 Die folgenden Abschnitte beschreiben die verschiedenen <xref:System.Windows.Media.Brush> eingibt, und geben Sie jeweils ein Beispiel.  
  
<a name="paintwithsolidcolorbrush"></a>   
## <a name="paint-with-a-solid-color"></a>Zeichnen mit einer Volltonfarbe  
 Ein <xref:System.Windows.Media.SolidColorBrush> zeichnet einen Bereich mit einer Volltonfarbe <xref:System.Windows.Media.Color>. Stehen eine Vielzahl von Möglichkeiten zum Angeben der <xref:System.Windows.Media.SolidColorBrush.Color%2A> von einer <xref:System.Windows.Media.SolidColorBrush>: Sie können z. B. über Kanäle alpha, Rot, Blau und Grün geben oder verwenden Sie eine der vordefinierten Farben von bereitgestellten der <xref:System.Windows.Media.Colors> Klasse.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.SolidColorBrush> zum Zeichnen der <xref:System.Windows.Shapes.Shape.Fill%2A> von einem <xref:System.Windows.Shapes.Rectangle>. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mit einem SolidColorBrush gezeichnetes Rechteck](./media/graphicsmm-brush-ovw-solidcolorbrush.png "Graphicsmm_brush_ovw_solidcolorbrush")  
Ein mit einem SolidColorBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 Weitere Informationen zu den <xref:System.Windows.Media.SolidColorBrush> Klasse, finden Sie unter [Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithlineargradientbrush"></a>   
## <a name="paint-with-a-linear-gradient"></a>Zeichnen mit einem linearen Farbverlauf  
 Ein <xref:System.Windows.Media.LinearGradientBrush> zeichnet einen Bereich mit einem linearen Farbverlauf. Ein linearer Farbverlauf mischt zwei oder mehr Farben in einer Zeile der Farbverlaufsachse an. Verwenden Sie <xref:System.Windows.Media.GradientStop> Objekte, um die Farben des Farbverlaufs und ihre Positionen im anzugeben.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.LinearGradientBrush> zum Zeichnen der <xref:System.Windows.Shapes.Shape.Fill%2A> von einem <xref:System.Windows.Shapes.Rectangle>. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mit einem LinearGradientBrush gezeichnetes Rechteck](./media/graphicsmm-brush-ovw-lineargradientbrush.jpg "Graphicsmm_brush_ovw_lineargradientbrush")  
Ein mit einem LinearGradientBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 Weitere Informationen zu den <xref:System.Windows.Media.LinearGradientBrush> Klasse, finden Sie unter [Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithradialgradientbrush"></a>   
## <a name="paint-with-a-radial-gradient"></a>Zeichnen mit einem radialen Farbverlauf  
 Ein <xref:System.Windows.Media.RadialGradientBrush> zeichnet einen Bereich mit einem radialen Farbverlauf. Ein Radialer Farbverlauf mischt zwei oder mehr Farben in einem Kreis an. Wie bei der <xref:System.Windows.Media.LinearGradientBrush> -Klasse, die Sie verwenden <xref:System.Windows.Media.GradientStop> Objekte, um die Farben des Farbverlaufs und ihre Positionen im anzugeben.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.RadialGradientBrush> zum Zeichnen der <xref:System.Windows.Shapes.Shape.Fill%2A> von einem <xref:System.Windows.Shapes.Rectangle>. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mit einem RadialGradientBrush gezeichnetes Rechteck](./media/graphicsmm-brush-ovw-radialgradientbrush.jpg "Graphicsmm_brush_ovw_radialgradientbrush")  
Ein mit einem RadialGradientBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 Weitere Informationen zu den <xref:System.Windows.Media.RadialGradientBrush> Klasse, finden Sie unter [Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithimage"></a>   
## <a name="paint-with-an-image"></a>Zeichnen mit einem Bild  
 Ein <xref:System.Windows.Media.ImageBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.ImageSource>.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.ImageBrush> zum Zeichnen der <xref:System.Windows.Shapes.Shape.Fill%2A> von einem <xref:System.Windows.Shapes.Rectangle>. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein Rechteck mit einem ImageBrush gezeichnetes](./media/graphicsmm-brush-ovw-imagebrush.jpg "Graphicsmm_brush_ovw_imagebrush")  
Ein mit einem Image gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 Weitere Informationen zu den <xref:System.Windows.Media.ImageBrush> Klasse, finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithdrawing"></a>   
## <a name="paint-with-a-drawing"></a>Zeichnen mit einer Zeichnung  
 Ein <xref:System.Windows.Media.DrawingBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.Drawing>. Ein <xref:System.Windows.Media.Drawing> kann Formen, Bildern, Text und Medien enthalten.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingBrush> zum Zeichnen der <xref:System.Windows.Shapes.Shape.Fill%2A> von einem <xref:System.Windows.Shapes.Rectangle>. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein mit einem DrawingBrush gezeichnetes Rechteck](./media/graphicsmm-brush-ovw-drawingbrush.jpg "Graphicsmm_brush_ovw_drawingbrush")  
Ein mit einem DrawingBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 Weitere Informationen zu den <xref:System.Windows.Media.DrawingBrush> Klasse, finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithvisual"></a>   
## <a name="paint-with-a-visual"></a>Zeichnen mit einem visuellen Element  
 Ein <xref:System.Windows.Media.VisualBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.Visual> Objekt. Beispiele für visuelle Objekte <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Page>, und <xref:System.Windows.Controls.MediaElement>. Ein <xref:System.Windows.Media.VisualBrush> können Sie projizieren von Inhalten von einem Teil der Anwendung in einem anderen Bereich; es ist sehr nützlich für reflexionseffekte erstellen und Teile des Bildschirms zu vergrößern.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.VisualBrush> zum Zeichnen der <xref:System.Windows.Shapes.Shape.Fill%2A> von einem <xref:System.Windows.Shapes.Rectangle>. Die folgende Abbildung zeigt das gezeichnete Rechteck.  
  
 ![Ein Rechteck mit einem VisualBrush gezeichnetes](./media/graphicsmm-brush-ovw-visualbrush.jpg "Graphicsmm_brush_ovw_visualbrush")  
Ein mit einem VisualBrush gezeichnetes Rechteck  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 Weitere Informationen zu den <xref:System.Windows.Media.VisualBrush> Klasse, finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>   
## <a name="paint-using-predefined-and-system-brushes"></a>Zeichnen Sie vordefinierte mit Systempinsel  
 Der Einfachheit halber stellt Windows Presentation Foundation (WPF) bereit, einen Satz vordefinierter und System Pinsel, dass Sie zum Zeichnen von Objekten verwenden können.  
  
- Eine Liste der verfügbaren vordefinierten Pinsel, finden Sie unter den <xref:System.Windows.Media.Brushes> Klasse. Ein Beispiel ein vordefiniertes Pinsels verwenden, finden Sie unter [Zeichnen eines Bereichs mit einer Volltonfarbe](how-to-paint-an-area-with-a-solid-color.md).  
  
- Eine Liste der verfügbaren Systempinsel, finden Sie unter den <xref:System.Windows.SystemColors> Klasse. Ein Beispiel finden Sie unter [Zeichnen eines Bereichs mit einem Systempinsel](how-to-paint-an-area-with-a-system-brush.md).  
  
<a name="commonbrushfeatures"></a>   
## <a name="common-brush-features"></a>Allgemeine Funktionen für Pinsel  
 <xref:System.Windows.Media.Brush> -Objekte stellen eine <xref:System.Windows.Media.Brush.Opacity%2A> -Eigenschaft, die verwendet werden kann, um einen Pinsel transparent bzw. teilweise transparent machen. Ein <xref:System.Windows.Media.Brush.Opacity%2A> Wert 0 wird ein Pinsel, der völlig transparent, während ein <xref:System.Windows.Media.Brush.Opacity%2A> Wert 1 wird ein Pinsel transparent. Im folgenden Beispiel wird die <xref:System.Windows.Media.Brush.Opacity%2A> Eigenschaft, um eine <xref:System.Windows.Media.SolidColorBrush> 25 Prozent undurchlässig ist.  
  
 [!code-xaml[BrushOverviewExamples_snip#OpacityExample1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 Wenn der Pinsel Farben, die teilweise transparent sind enthält, wird die Farbe der Durchlässigkeitswert durch Multiplikation mit dem Deckkraftwert des Pinsels kombiniert. Beispielsweise weist die Ausgabefarbe Wenn ein Pinsel Durchlässigkeitswert 0,5 hat, und eine Farbe ab, in der Pinsel verfügt auch über eine der Deckkraftwert 0,5, Durchlässigkeitswert 0,25.  
  
> [!NOTE]
>  Es ist effizienter, den Deckkraftwert eines Pinsels ändern, als zu ändern, die Deckkraft eines gesamten Elements mithilfe der <xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType> Eigenschaft.  
  
 Sie können zu drehen, skalieren, neigen und übersetzen Sie den Inhalt eines Pinsels mit seiner <xref:System.Windows.Media.Brush.Transform%2A> oder <xref:System.Windows.Media.Brush.RelativeTransform%2A> Eigenschaften. Weitere Informationen finden Sie unter [Übersicht über Pinseltransformationen](brush-transformation-overview.md).  
  
 Da sie sind <xref:System.Windows.Media.Animation.Animatable> Objekte <xref:System.Windows.Media.Brush> Objekte können animiert werden. Weitere Informationen finden Sie unter [Übersicht über Animation](animation-overview.md).  
  
<a name="freezable_features"></a>   
### <a name="freezable-features"></a>Funktionen von Freezable-Objekten  
 Da es erbt die <xref:System.Windows.Freezable> -Klasse, die <xref:System.Windows.Media.Brush> stellt mehrere spezielle Features bereit: <xref:System.Windows.Media.Brush> als Objekte deklariert werden [Ressourcen](../advanced/xaml-resources.md)von mehreren Objekten freigegeben und geklont. Darüber hinaus alle dem <xref:System.Windows.Media.Brush> Typen außer <xref:System.Windows.Media.VisualBrush> schreibgeschützt zur Verbesserung der Leistung und threadsicher gemacht werden kann.  
  
 Weitere Informationen zu den verschiedenen Funktionen von <xref:System.Windows.Freezable> Objekten finden Sie [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md).  
  
 Weitere Informationen zu den Gründen <xref:System.Windows.Media.VisualBrush> -Objekte können nicht fixiert ist, finden Sie in der <xref:System.Windows.Media.VisualBrush> Seite.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Brush>
- <xref:System.Windows.Media.Brushes>
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md)
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
- [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md)
- [Beispiel für Pinsel](https://go.microsoft.com/fwlink/?LinkID=159973)
- [Beispiel zu ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005)
- [VisualBrush-Beispiel](https://go.microsoft.com/fwlink/?LinkID=160049)
- [Themen zu Vorgehensweisen](brushes-how-to-topics.md)
- [Weitere Leistungsempfehlungen](../advanced/optimizing-performance-other-recommendations.md)
