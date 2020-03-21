---
title: Zeichnen mit Bildern, Zeichnungen und visuellen Elementen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- painting [WPF], with images
- painting with visuals [WPF]
- brushes [WPF], painting with images
- brushes [WPF], painting with visuals
ms.assetid: 779aac3f-8d41-49d8-8130-768244aa2240
ms.openlocfilehash: e0e5e386b32425c87502d18a24e758193c14a5b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186923"
---
# <a name="painting-with-images-drawings-and-visuals"></a>Zeichnen mit Bildern, Zeichnungen und visuellen Elementen
In diesem Thema <xref:System.Windows.Media.ImageBrush>wird <xref:System.Windows.Media.DrawingBrush>beschrieben, wie Sie , und <xref:System.Windows.Media.VisualBrush> <xref:System.Windows.Media.Drawing>Objekte verwenden, um einen Bereich mit einem Bild, einer oder einer <xref:System.Windows.Media.Visual>zu zeichnen.  

<a name="prereqs"></a>
## <a name="prerequisites"></a>Voraussetzungen  
 Als Voraussetzung für dieses Thema sollten Sie mit den von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bereitgestellten unterschiedlichen Pinseltypen und ihren grundlegenden Funktionen vertraut sein. Eine Einführung finden Sie unter [Übersicht über WPF-Pinsel](wpf-brushes-overview.md).  
  
<a name="image"></a>
## <a name="paint-an-area-with-an-image"></a>Zeichnen eines Bereichs mit einem Bild  
 Ein <xref:System.Windows.Media.ImageBrush> malt einen Bereich <xref:System.Windows.Media.ImageSource>mit einem . Der häufigste Typ <xref:System.Windows.Media.ImageSource> für die <xref:System.Windows.Media.ImageBrush> Verwendung <xref:System.Windows.Media.Imaging.BitmapImage>mit einer ist eine , die eine Bitmapgrafik beschreibt. Sie können <xref:System.Windows.Media.DrawingImage> eine verwenden, <xref:System.Windows.Media.Drawing> um mit einem Objekt <xref:System.Windows.Media.DrawingBrush> zu malen, aber es ist einfacher, stattdessen eine zu verwenden. Weitere Informationen <xref:System.Windows.Media.ImageSource> zu Objekten finden Sie in der [Imaging-Übersicht](imaging-overview.md).  
  
 Um mit <xref:System.Windows.Media.ImageBrush>einem zu <xref:System.Windows.Media.Imaging.BitmapImage> malen, erstellen Sie eine, und verwenden Sie diese, um den Bitmapinhalt zu laden. Verwenden Sie <xref:System.Windows.Media.Imaging.BitmapImage> dann die, um die <xref:System.Windows.Media.ImageBrush.ImageSource%2A> Eigenschaft der <xref:System.Windows.Media.ImageBrush>festzulegen. Wenden Sie <xref:System.Windows.Media.ImageBrush> die schließlich auf das Objekt an, das Sie malen möchten.  In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]können Sie auch <xref:System.Windows.Media.ImageBrush.ImageSource%2A> einfach die <xref:System.Windows.Media.ImageBrush> Eigenschaft des mit dem Pfad des zu ladenden Bildes festlegen.  
  
 Wie <xref:System.Windows.Media.Brush> alle Objekte <xref:System.Windows.Media.ImageBrush> kann auch ein zum Zeichnen von Objekten wie Formen, Bedienfeldern, Steuerelementen und Text verwendet werden. Die folgende Abbildung zeigt einige Effekte, <xref:System.Windows.Media.ImageBrush>die mit einem erreicht werden können.  
  
 ![ImageBrush-Ausgabebeispiele](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Von einem ImageBrush gezeichnete Objekte  
  
 Standardmäßig dehnt ein <xref:System.Windows.Media.ImageBrush> Bild sein Bild aus, um den zu malenden Bereich vollständig zu füllen, wodurch das Bild möglicherweise verzerrt wird, wenn der gezeichnete Bereich ein anderes Seitenverhältnis als das Bild aufweist. Sie können dieses Verhalten <xref:System.Windows.Media.TileBrush.Stretch%2A> ändern, indem Sie <xref:System.Windows.Media.Stretch.Fill> <xref:System.Windows.Media.Stretch.None>die <xref:System.Windows.Media.Stretch.Uniform>Eigenschaft <xref:System.Windows.Media.Stretch.UniformToFill>von ihrem Standardwert von in , oder ändern. Da <xref:System.Windows.Media.ImageBrush> es sich <xref:System.Windows.Media.TileBrush>um einen Typ von handelt, können Sie genau angeben, wie ein Bildpinsel den Ausgabebereich ausfüllt, und sogar Muster erstellen. Weitere Informationen zu <xref:System.Windows.Media.TileBrush> erweiterten Funktionen finden Sie in der [TileBrush-Übersicht](tilebrush-overview.md).  
  
<a name="fillingpanelwithimage"></a>
## <a name="example-paint-an-object-with-a-bitmap-image"></a>Beispiel: Zeichnen eines Objekts mit einem Bitmapbild  
 Im folgenden Beispiel <xref:System.Windows.Media.ImageBrush> wird <xref:System.Windows.Controls.Panel.Background%2A> ein <xref:System.Windows.Controls.Canvas>verwendet, um die von zu malen.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>
## <a name="paint-an-area-with-a-drawing"></a>Zeichnen eines Bereichs mit einer Zeichnung  
 Mit <xref:System.Windows.Media.DrawingBrush> A können Sie einen Bereich mit Formen, Text, Bildern und Videos zeichnen. Shapes innerhalb eines Zeichenpinsels können selbst mit einer Einfarbigen <xref:System.Windows.Media.DrawingBrush>Farbe, einem Farbverlauf, einem Bild oder sogar einem anderen gezeichnet werden. Die folgende Abbildung zeigt <xref:System.Windows.Media.DrawingBrush>einige Verwendungen einer .  
  
 ![DrawingBrush-Ausgabebeispiele](./media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk_mmgraphics_drawingbrushexamples")  
Von einem DrawingBrush gezeichnete Objekte  
  
 Ein <xref:System.Windows.Media.DrawingBrush> zeichnet einen Bereich <xref:System.Windows.Media.Drawing> mit einem Objekt. Ein <xref:System.Windows.Media.Drawing> Objekt beschreibt sichtbaren Inhalt, z. B. eine Form, Bitmap, ein Video oder eine Textzeile. Verschiedene Arten von Zeichnungen beschreiben verschiedene Arten von Inhalten. Im Folgenden finden Sie eine Liste der unterschiedlichen Typen von Zeichnungsobjekten.  
  
- <xref:System.Windows.Media.GeometryDrawing>– Zeichnet eine Form.  
  
- <xref:System.Windows.Media.ImageDrawing>– Zeichnet ein Bild.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>– Zeichnet Text.  
  
- <xref:System.Windows.Media.VideoDrawing>– Gibt eine Audio- oder Videodatei ab.  
  
- <xref:System.Windows.Media.DrawingGroup>– Zeichnet andere Zeichnungen. Verwenden Sie eine Zeichnungsgruppe, um andere Zeichnungen in einer zusammengesetzten Zeichnung zu kombinieren.  
  
 Weitere Informationen <xref:System.Windows.Media.Drawing> zu Objekten finden Sie in der [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md).  
  
 Wie <xref:System.Windows.Media.ImageBrush>ein <xref:System.Windows.Media.DrawingBrush> dehnt sich ein, <xref:System.Windows.Media.DrawingBrush.Drawing%2A> um seinen Ausgabebereich zu füllen. Sie können dieses Verhalten überschreiben, indem Sie die Eigenschaft aus der <xref:System.Windows.Media.TileBrush.Stretch%2A> Standardeinstellung von <xref:System.Windows.Media.Stretch.Fill>ändern. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Media.TileBrush.Stretch%2A>-Eigenschaft.  
  
<a name="fillingareawithdrawingbrushexample"></a>
## <a name="example-paint-an-object-with-a-drawing"></a>Beispiel: Zeichnen eines Objekts mit einer Zeichnung  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt mit einer Zeichnung aus drei Ellipsen gezeichnet wird. A <xref:System.Windows.Media.GeometryDrawing> wird verwendet, um die Ellipsen zu beschreiben.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>
## <a name="paint-an-area-with-a-visual"></a>Zeichnen eines Bereichs mit einem visuellen Element  
 Die vielseitigste und leistungsstärkste aller <xref:System.Windows.Media.VisualBrush> Pinsel, die malt <xref:System.Windows.Media.Visual>einen Bereich mit einem . A <xref:System.Windows.Media.Visual> ist ein grafischer Typ auf niedriger Ebene, der als Vorfahre vieler nützlicher grafischer Komponenten dient. Beispielsweise sind <xref:System.Windows.Window>die <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Controls.Control> und Die <xref:System.Windows.Media.Visual> Klassen alle Objekttypen. Mit <xref:System.Windows.Media.VisualBrush>einem können Sie Bereiche [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] mit fast jedem grafischen Objekt malen.  
  
> [!NOTE]
> Obwohl <xref:System.Windows.Media.VisualBrush> es sich <xref:System.Windows.Freezable> um einen Objekttyp handelt, kann es <xref:System.Windows.Media.VisualBrush.Visual%2A> nicht eingefroren werden (schreibgeschützt), wenn seine Eigenschaft auf einen anderen Wert als `null`festgelegt ist.  
  
 Es gibt zwei Möglichkeiten, <xref:System.Windows.Media.VisualBrush.Visual%2A> den <xref:System.Windows.Media.VisualBrush>Inhalt einer anzugeben.  
  
- Erstellen Sie <xref:System.Windows.Media.Visual> eine neue, <xref:System.Windows.Media.VisualBrush.Visual%2A> und verwenden <xref:System.Windows.Media.VisualBrush>Sie sie, um die Eigenschaft der festzulegen. Ein Beispiel finden Sie unter [Beispiel: Zeichnen eines Objekts mit einem visuellen Element](#examplevisualbrush1) im folgenden Abschnitt.  
  
- Verwenden Sie <xref:System.Windows.Media.Visual>eine vorhandene , die <xref:System.Windows.Media.Visual>ein doppeltes Abbild des Ziels erstellt. Sie können dann <xref:System.Windows.Media.VisualBrush> die verwenden, um interessante Effekte wie Reflexion und Vergrößerung zu erstellen. Ein Beispiel finden Sie unter [Beispiel: Erstellen einer Reflektion](#examplevisualbrush2).  
  
 Wenn Sie ein <xref:System.Windows.Media.VisualBrush.Visual%2A> neues <xref:System.Windows.Media.VisualBrush> für <xref:System.Windows.Media.Visual> ein <xref:System.Windows.UIElement> definieren und das ein (z. B. ein Bedienfeld oder Einsteuerelement) ist, wird das Layoutsystem auf dem <xref:System.Windows.UIElement> und seinen untergeordneten Elementen ausgeführt, wenn die <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A> Eigenschaft auf `true`festgelegt ist. Der Stamm <xref:System.Windows.UIElement> ist jedoch im Wesentlichen vom Rest des Systems isoliert: Stile und externes Layout können diese Grenze nicht durchdringen. Daher sollten Sie explizit die Größe <xref:System.Windows.UIElement>des Stamms angeben, da sein einziges übergeordnetes Element der <xref:System.Windows.Media.VisualBrush> ist und sich daher nicht automatisch auf den zu malenden Bereich spezifizieren kann. Weitere Informationen zum Layout in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] finden Sie unter [Layout](../advanced/layout.md).  
  
 Wie <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush>und <xref:System.Windows.Media.VisualBrush> , a dehnt seinen Inhalt, um seinen Ausgabebereich zu füllen. Sie können dieses Verhalten überschreiben, indem Sie die Eigenschaft aus der <xref:System.Windows.Media.TileBrush.Stretch%2A> Standardeinstellung von <xref:System.Windows.Media.Stretch.Fill>ändern. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Media.TileBrush.Stretch%2A>-Eigenschaft.  
  
<a name="examplevisualbrush1"></a>
## <a name="example-paint-an-object-with-a-visual"></a>Beispiel: Zeichnen eines Objekts mit einem visuellen Element  
 Im folgenden Beispiel werden mehrere Steuerelemente und ein Bereich verwendet, um ein Rechteck zu zeichnen.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>
## <a name="example-create-a-reflection"></a>Beispiel: Erstellen einer Reflektion  
 Das obige Beispiel zeigte, <xref:System.Windows.Media.Visual> wie Sie ein neues für die Verwendung als Hintergrund erstellen. Sie können auch <xref:System.Windows.Media.VisualBrush> eine verwenden, um ein vorhandenes visuelles Element anzuzeigen. Diese Funktion ermöglicht es Ihnen, interessante visuelle Effekte wie Reflexionen und Vergrößerung zu erzeugen. Im folgenden Beispiel <xref:System.Windows.Media.VisualBrush> wird ein verwendet, um eine Reflektion eines zu <xref:System.Windows.Controls.Border> erstellen, das mehrere Elemente enthält. In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![Ein reflektiertes Visual-Objekt](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
Ein reflektiertes Visual-Objekt  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Weitere Beispiele, die zeigen, wie Bildschirmbereiche vergrößert und Reflektionen erstellt werden, finden Sie unter [Beispiel zu VisualBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush).  
  
<a name="tilebrush"></a>
## <a name="tilebrush-features"></a>TileBrush-Funktionen  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>und <xref:System.Windows.Media.VisualBrush> sind <xref:System.Windows.Media.TileBrush> Objekttypen. <xref:System.Windows.Media.TileBrush>Objekte geben Ihnen eine große Kontrolle darüber, wie ein Bereich mit einem Bild, einer Zeichnung oder einem visuellen Element gezeichnet wird. Sie können beispielsweise zum Zeichnen eines Bereichs anstelle eines einzelnen gestreckten Bilds eine Reihe von Bildkacheln verwenden, die ein Muster ergeben.  
  
 A <xref:System.Windows.Media.TileBrush> besteht aus drei Hauptkomponenten: Inhalt, Kacheln und Ausgabebereich.  
  
 ![TileBrush-Komponenten](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Komponenten eines TileBrush mit einer einzelnen Kachel  
  
 ![Komponenten eines gekachelten TileBrush-Elements](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
Komponente eines TileBrush mit mehreren Kacheln  
  
 Weitere Informationen zu den Kachelfunktionen von <xref:System.Windows.Media.TileBrush> Objekten finden Sie in der [TileBrush-Übersicht](tilebrush-overview.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [Übersicht über TileBrush](tilebrush-overview.md)
- [Übersicht über WPF-Pinsel](wpf-brushes-overview.md)
- [Übersicht über die Bildverarbeitung](imaging-overview.md)
- [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md)
- [Übersicht über Deckkraftmasken](opacity-masks-overview.md)
- [Übersicht über das WPF-Grafikrendering](wpf-graphics-rendering-overview.md)
- [Beispiel zu ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [VisualBrush-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
