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
ms.openlocfilehash: 826c5a0656a9a7e7cff0e96fc6755c5c9c717993
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204197"
---
# <a name="painting-with-images-drawings-and-visuals"></a>Zeichnen mit Bildern, Zeichnungen und visuellen Elementen
In diesem Thema wird beschrieben, wie Sie mit <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, und <xref:System.Windows.Media.VisualBrush> Objekte zum Zeichnen eines Bereichs mit einem Bild, ein <xref:System.Windows.Media.Drawing>, oder ein <xref:System.Windows.Media.Visual>.  

<a name="prereqs"></a>   
## <a name="prerequisites"></a>Vorraussetzungen  
 Als Voraussetzung für dieses Thema sollten Sie mit den von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bereitgestellten unterschiedlichen Pinseltypen und ihren grundlegenden Funktionen vertraut sein. Eine Einführung finden Sie unter [Übersicht über WPF-Pinsel](wpf-brushes-overview.md).  
  
<a name="image"></a>   
## <a name="paint-an-area-with-an-image"></a>Zeichnen eines Bereichs mit einem Bild  
 Ein <xref:System.Windows.Media.ImageBrush> zeichnet einen Bereich mit einer <xref:System.Windows.Media.ImageSource>. Die am häufigsten verwendete Typ von <xref:System.Windows.Media.ImageSource> mit einer <xref:System.Windows.Media.ImageBrush> ist eine <xref:System.Windows.Media.Imaging.BitmapImage>, das eine Bitmapgrafik beschreibt. Können Sie eine <xref:System.Windows.Media.DrawingImage> zum Zeichnen verwenden eine <xref:System.Windows.Media.Drawing> -Objekt, aber es ist einfacher, eine <xref:System.Windows.Media.DrawingBrush> stattdessen. Weitere Informationen zu <xref:System.Windows.Media.ImageSource> Objekten finden Sie die [Übersicht über die Bildverarbeitung](imaging-overview.md).  
  
 So zeichnen Sie mit einer <xref:System.Windows.Media.ImageBrush>, erstellen eine <xref:System.Windows.Media.Imaging.BitmapImage> und um den Bitmapinhalt zu laden. Verwenden Sie dann die <xref:System.Windows.Media.Imaging.BitmapImage> Festlegen der <xref:System.Windows.Media.ImageBrush.ImageSource%2A> Eigenschaft der <xref:System.Windows.Media.ImageBrush>. Wenden Sie schließlich die <xref:System.Windows.Media.ImageBrush> auf das Objekt, das Sie zeichnen möchten.  In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Sie können auch einfach festlegen, die <xref:System.Windows.Media.ImageBrush.ImageSource%2A> Eigenschaft der <xref:System.Windows.Media.ImageBrush> durch den Pfad der zu ladenden Bilds.  
  
 Wie alle <xref:System.Windows.Media.Brush> Objekte, eine <xref:System.Windows.Media.ImageBrush> können verwendet werden, um die Objekte, z. B. Formen, Bereichen, Steuerelementen und Text zu zeichnen. Die folgende Abbildung zeigt einige Effekte, die mit darstellbar ist ein <xref:System.Windows.Media.ImageBrush>.  
  
 !["ImageBrush" Ausgabe Beispiele](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "Wcpsdk_mmgraphics_imagebrushexamples")  
Von einem ImageBrush gezeichnete Objekte  
  
 Standardmäßig eine <xref:System.Windows.Media.ImageBrush> gestreckt wird dessen Abbildung Bereich vollständig auszufüllen, der gezeichnet wird, das Bild möglicherweise verzerrt, verfügt der gezeichnete Bereich ein anderes Seitenverhältnis als das Bild. Sie können dieses Verhalten ändern, indem Sie ändern die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft den Standardwert <xref:System.Windows.Media.Stretch.Fill> zu <xref:System.Windows.Media.Stretch.None>, <xref:System.Windows.Media.Stretch.Uniform>, oder <xref:System.Windows.Media.Stretch.UniformToFill>. Da <xref:System.Windows.Media.ImageBrush> ist eine Art von <xref:System.Windows.Media.TileBrush>, können Sie angeben, genau wie ein Bildpinsel den Ausgabebereich ausfüllt und sogar Muster erstellen. Weitere Informationen zu erweiterten <xref:System.Windows.Media.TileBrush> Features finden Sie die [Übersicht über TileBrush](tilebrush-overview.md).  
  
<a name="fillingpanelwithimage"></a>   
## <a name="example-paint-an-object-with-a-bitmap-image"></a>Beispiel: Zeichnen eines Objekts mit einem Bitmapbild  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.ImageBrush> zum Zeichnen der <xref:System.Windows.Controls.Panel.Background%2A> von einem <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>   
## <a name="paint-an-area-with-a-drawing"></a>Zeichnen eines Bereichs mit einer Zeichnung  
 Ein <xref:System.Windows.Media.DrawingBrush> ermöglicht es Ihnen, einen Bereich mit Formen, Text, Bilder und Videos zu zeichnen. Die Formen innerhalb des Zeichenpinsels können selbst mit einer Volltonfarbe, Farbverlauf, Bild gezeichnet werden oder auch ein anderes <xref:System.Windows.Media.DrawingBrush>. Die folgende Abbildung zeigt einige Verwendungsmöglichkeiten für einen <xref:System.Windows.Media.DrawingBrush>.  
  
 ![DrawingBrush Ausgabe Beispiele](./media/wcpsdk-mmgraphics-drawingbrushexamples.png "Wcpsdk_mmgraphics_drawingbrushexamples")  
Von einem DrawingBrush gezeichnete Objekte  
  
 Ein <xref:System.Windows.Media.DrawingBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.Drawing> Objekt. Ein <xref:System.Windows.Media.Drawing> -Objekt beschreibt sichtbaren Inhalt, z. B. eine Form, Bitmap, Video oder eine Textzeile. Verschiedene Arten von Zeichnungen beschreiben verschiedene Arten von Inhalten. Im Folgenden finden Sie eine Liste der unterschiedlichen Typen von Zeichnungsobjekten.  
  
-   <xref:System.Windows.Media.GeometryDrawing> – Zeichnet eine Form.  
  
-   <xref:System.Windows.Media.ImageDrawing> – Zeichnet ein Bild.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing> – Zeichnet Text.  
  
-   <xref:System.Windows.Media.VideoDrawing> – Gibt eine Audio- oder Videodatei.  
  
-   <xref:System.Windows.Media.DrawingGroup> – Zeichnet andere Zeichnungen. Verwenden Sie eine Zeichnungsgruppe, um andere Zeichnungen in einer zusammengesetzten Zeichnung zu kombinieren.  
  
 Weitere Informationen zu <xref:System.Windows.Media.Drawing> Objekten finden Sie die [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md).  
  
 Wie ein <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> gestreckt wird, dessen <xref:System.Windows.Media.DrawingBrush.Drawing%2A> auf den Ausgabebereich auszufüllen. Sie können dieses Verhalten überschreiben, indem Sie ändern die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft von der Standardeinstellung von <xref:System.Windows.Media.Stretch.Fill>. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Media.TileBrush.Stretch%2A>-Eigenschaft.  
  
<a name="fillingareawithdrawingbrushexample"></a>   
## <a name="example-paint-an-object-with-a-drawing"></a>Beispiel: Zeichnen eines Objekts mit einer Zeichnung  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt mit einer Zeichnung aus drei Ellipsen gezeichnet wird. Ein <xref:System.Windows.Media.GeometryDrawing> wird verwendet, um die Ellipsen zu beschreiben.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>   
## <a name="paint-an-area-with-a-visual"></a>Zeichnen eines Bereichs mit einem visuellen Element  
 Der vielseitigste und leistungsfähigste aller Pinsel, der <xref:System.Windows.Media.VisualBrush> zeichnet einen Bereich mit einem <xref:System.Windows.Media.Visual>. Ein <xref:System.Windows.Media.Visual> ist ein Grafiktyp, die als den Vorgänger des viele nützliche grafische Komponenten dient. Z. B. die <xref:System.Windows.Window>, <xref:System.Windows.FrameworkElement>, und <xref:System.Windows.Controls.Control> Klassen sind alle Arten von <xref:System.Windows.Media.Visual> Objekte. Mit einem <xref:System.Windows.Media.VisualBrush>, Sie können Bereiche mit fast allen zeichnen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] grafischen Objekten.  
  
> [!NOTE]
>  Obwohl <xref:System.Windows.Media.VisualBrush> ist eine Art von <xref:System.Windows.Freezable> Objekt kann nicht fixiert werden kann (schreibgeschützt) Wenn die <xref:System.Windows.Media.VisualBrush.Visual%2A> Eigenschaft auf einen Wert festgelegt ist als `null`.  
  
 Es gibt zwei Möglichkeiten zum Angeben der <xref:System.Windows.Media.VisualBrush.Visual%2A> Inhalt von einem <xref:System.Windows.Media.VisualBrush>.  
  
-   Erstellen Sie ein neues <xref:System.Windows.Media.Visual> und verwenden sie zum Festlegen der <xref:System.Windows.Media.VisualBrush.Visual%2A> Eigenschaft der <xref:System.Windows.Media.VisualBrush>. Ein Beispiel finden Sie unter den [Beispiel: Zeichnen eines Objekts mit einem visuellen Element](#examplevisualbrush1) im folgenden Abschnitt.  
  
-   Verwenden Sie ein vorhandenes <xref:System.Windows.Media.Visual>, wodurch ein Bildduplikat vom Ziel erstellt <xref:System.Windows.Media.Visual>. Anschließend können Sie die <xref:System.Windows.Media.VisualBrush> interessante Effekte, z.B. Reflektion und Vergrößerung zu erstellen. Ein Beispiel finden Sie unter den [Beispiel: Erstellen einer Reflektion](#examplevisualbrush2) Abschnitt.  
  
 Beim Definieren einer neuen <xref:System.Windows.Media.VisualBrush.Visual%2A> für eine <xref:System.Windows.Media.VisualBrush> und <xref:System.Windows.Media.Visual> ist eine <xref:System.Windows.UIElement> (z. B. ein Bereich oder Steuerelement), der das Layoutsystem führt auf der <xref:System.Windows.UIElement> und seine untergeordneten Elemente bei der <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A> -Eigenschaftensatz auf `true`. Jedoch den Stamm <xref:System.Windows.UIElement> ist im Grunde vom Rest des Systems isoliert: Stile und externes Layout können diese Abgrenzung nicht durchdringen. Daher sollten Sie explizit die Größe des Stamms angeben <xref:System.Windows.UIElement>, da nur das übergeordnete Element ist die <xref:System.Windows.Media.VisualBrush> und sich daher nicht automatisch auf den gezeichneten Bereich anpassen kann. Weitere Informationen zum Layout in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] finden Sie unter [Layout](../advanced/layout.md).  
  
 Wie <xref:System.Windows.Media.ImageBrush> und <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.VisualBrush> gestreckt wird, deren Inhalte in den Ausgabebereich auszufüllen. Sie können dieses Verhalten überschreiben, indem Sie ändern die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft von der Standardeinstellung von <xref:System.Windows.Media.Stretch.Fill>. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Media.TileBrush.Stretch%2A>-Eigenschaft.  
  
<a name="examplevisualbrush1"></a>   
## <a name="example-paint-an-object-with-a-visual"></a>Beispiel: Zeichnen eines Objekts mit einem visuellen Element  
 Im folgenden Beispiel werden mehrere Steuerelemente und ein Bereich verwendet, um ein Rechteck zu zeichnen.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>   
## <a name="example-create-a-reflection"></a>Beispiel: Erstellen einer Reflektion  
 Im vorherige Beispiel wurde gezeigt, wie zum Erstellen eines neuen <xref:System.Windows.Media.Visual> für die Verwendung als Hintergrund. Können Sie auch eine <xref:System.Windows.Media.VisualBrush> zum Anzeigen einer vorhandenen visuellen Element dieser Funktion können Sie interessante visuelle Effekte, z.B. Reflexionen und vergrößerungen zu erzeugen. Im folgenden Beispiel wird eine <xref:System.Windows.Media.VisualBrush> zum Erstellen einer Spiegelung einer <xref:System.Windows.Controls.Border> , das mehrere Elemente enthält. In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![Ein wiedergegeben visuellen Objekts](./media/graphicsmm-visualbrush-reflection-small.jpg "Graphicsmm_visualbrush_reflection_small")  
Ein reflektiertes Visual-Objekt  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Weitere Beispiele, die zeigen, wie Bildschirmbereiche vergrößert und Reflektionen erstellt werden, finden Sie unter [Beispiel zu VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049).  
  
<a name="tilebrush"></a>   
## <a name="tilebrush-features"></a>TileBrush-Funktionen  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, und <xref:System.Windows.Media.VisualBrush> gibt Typen von <xref:System.Windows.Media.TileBrush> Objekte. <xref:System.Windows.Media.TileBrush> -Objekte bieten Ihnen viel Kontrolle wie ein Bereich mit einem Bild, Drawing oder Visual gezeichnet wird. Sie können beispielsweise zum Zeichnen eines Bereichs anstelle eines einzelnen gestreckten Bilds eine Reihe von Bildkacheln verwenden, die ein Muster ergeben.  
  
 Ein <xref:System.Windows.Media.TileBrush> verfügt über drei primäre Komponenten: Inhalt, Kacheln und Ausgabebereich.  
  
 ![TileBrush-Komponenten](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Komponenten eines TileBrush mit einer einzelnen Kachel  
  
 ![Komponenten eines gekachelten TileBrush](./media/graphicsmm-tiledprojection.png "Graphicsmm_tiledprojection")  
Komponente eines TileBrush mit mehreren Kacheln  
  
 Weitere Informationen über das Kacheln von <xref:System.Windows.Media.TileBrush> Objekten finden Sie die [Übersicht über TileBrush](tilebrush-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [Übersicht über TileBrush](tilebrush-overview.md)
- [Übersicht über WPF-Pinsel](wpf-brushes-overview.md)
- [Übersicht über die Bildverarbeitung](imaging-overview.md)
- [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md)
- [Übersicht über Durchlässigkeitsmasken](opacity-masks-overview.md)
- [Übersicht über das WPF-Grafikrendering](wpf-graphics-rendering-overview.md)
- [Beispiel zu ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005)
- [VisualBrush-Beispiel](https://go.microsoft.com/fwlink/?LinkID=160049)
