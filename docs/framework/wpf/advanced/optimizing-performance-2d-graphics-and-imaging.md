---
title: 'Optimieren der Leistung: 2D-Grafiken und Bildverarbeitung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], performance
- drawing [WPF], optimizing performance
- imaging [WPF], optimizing performance
- shapes [WPF], optimizing performance
- 2D graphics [WPF]
- images [WPF], optimizing performance
ms.assetid: e335601e-28c8-4d64-ba27-778fffd55f72
ms.openlocfilehash: eb3686367873276587572addda436471cd1abf27
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291801"
---
# <a name="optimizing-performance-2d-graphics-and-imaging"></a>Optimieren der Leistung: 2D-Grafiken und Bildverarbeitung
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt zahlreiche Funktionen für 2D-Grafiken und Bildverarbeitung zur Verfügung, die den Anforderungen Ihrer Anwendung entsprechend optimiert werden können. Dieses Thema enthält Informationen über die Leistungsoptimierung in diesen Bereichen.  

<a name="Drawing_and_Shapes"></a>
## <a name="drawing-and-shapes"></a>Zeichnen und Formen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]stellt <xref:System.Windows.Media.Drawing> sowohl <xref:System.Windows.Shapes.Shape> Objekte zur Darstellung von grafischen Zeichnungsinhalten bereit. <xref:System.Windows.Media.Drawing> Objekte sind jedoch einfachere <xref:System.Windows.Shapes.Shape> Konstrukte als Objekte und bieten bessere Leistungsmerkmale.  
  
 Mit <xref:System.Windows.Shapes.Shape> A können Sie eine grafische Form auf den Bildschirm zeichnen. Da sie von <xref:System.Windows.FrameworkElement> der <xref:System.Windows.Shapes.Shape> Klasse abgeleitet sind, können Objekte in Bedienfeldern und den meisten Steuerelementen verwendet werden.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet mehrere Ebenen für den Zugriff auf Grafiken und Renderingdienste. Auf der obersten <xref:System.Windows.Shapes.Shape> Ebene sind Objekte einfach zu bedienen und bieten viele nützliche Funktionen, z. B. Layout und Ereignisbehandlung. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt eine Reihe von vorgefertigten Shape-Objekten zur Verfügung. Alle Shape-Objekte erben <xref:System.Windows.Shapes.Shape> von der Klasse. Verfügbare Shape-Objekte <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path>sind <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.Shapes.Polyline>, <xref:System.Windows.Shapes.Rectangle>, , , und .  
  
 <xref:System.Windows.Media.Drawing>Objekte hingegen leiten sich nicht von der <xref:System.Windows.FrameworkElement> Klasse ab und bieten eine leichtere Implementierung zum Rendern von Formen, Bildern und Text.  
  
 Es gibt vier <xref:System.Windows.Media.Drawing> Arten von Objekten:  
  
- <xref:System.Windows.Media.GeometryDrawing>Zeichnet eine Form.  
  
- <xref:System.Windows.Media.ImageDrawing>Zeichnet ein Bild.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>Zeichnet Text.  
  
- <xref:System.Windows.Media.DrawingGroup>Zeichnet andere Zeichnungen. Verwenden Sie eine Zeichnungsgruppe, um andere Zeichnungen in einer zusammengesetzten Zeichnung zu kombinieren.  
  
 Das <xref:System.Windows.Media.GeometryDrawing> Objekt wird zum Rendern von Geometrieinhalten verwendet. Die <xref:System.Windows.Media.Geometry> Klasse und die konkreten Klassen, die <xref:System.Windows.Media.CombinedGeometry> <xref:System.Windows.Media.EllipseGeometry>daraus <xref:System.Windows.Media.PathGeometry>ableiten, z. B. , und , bieten eine Möglichkeit zum Rendern von 2D-Grafiken und zur Unterstützung von Treffertests und Clipping. Mit Geometry-Objekten können beispielsweise der Bereich eines Steuerelements oder der auf ein Bild anzuwendende Clip-Bereich definiert werden. Bei Geometry-Objekten kann es sich um einfache Bereiche wie Rechtecke und Kreise oder um aus einem oder mehreren geometrischen Objekten zusammengesetzte Regionen handeln. Komplexere geometrische Bereiche können <xref:System.Windows.Media.PathSegment>durch Kombinieren von <xref:System.Windows.Media.ArcSegment>-abgeleiteten Objekten wie , <xref:System.Windows.Media.BezierSegment>und <xref:System.Windows.Media.QuadraticBezierSegment>erstellt werden.  
  
 Oberflächlich betrachtet sind <xref:System.Windows.Media.Geometry> die <xref:System.Windows.Shapes.Shape> Klasse und die Klasse ähnlich. Beide werden beim Rendern von 2D-Grafiken verwendet, und beide haben <xref:System.Windows.Media.EllipseGeometry> ähnliche <xref:System.Windows.Shapes.Ellipse>konkrete Klassen, die sich z. B. von ihnen ableiten, und . Es gibt jedoch wichtige Unterschiede zwischen diesen zwei Sätzen von Klassen. Zum einen <xref:System.Windows.Media.Geometry> fehlt der Klasse ein Teil <xref:System.Windows.Shapes.Shape> der Funktionalität der Klasse, z. B. die Möglichkeit, sich selbst zu zeichnen. Zum Zeichnen eines Geometry-Objekts muss eine andere Klasse, beispielsweise DrawingContext, Drawing oder Path (dabei ist zu beachten, dass ein Path eine Shape ist), verwendet werden, um den Zeichnungsvorgang auszuführen. Rendering-Eigenschaften wie Füllung, Strich und Strichstärke befinden sich in der Klasse, die das Geometrieobjekt zeichnet, während ein Shape-Objekt diese Eigenschaften enthält. Eine Möglichkeit, an diesen Unterschied zu denken, besteht darin, dass ein Geometrieobjekt einen Bereich definiert, z. B. einen Kreis, während ein Shape-Objekt einen Bereich definiert, definiert, wie dieser Bereich gefüllt und umrissen wird, und am Layoutsystem teilnimmt.  
  
 Da <xref:System.Windows.Shapes.Shape> Objekte von <xref:System.Windows.FrameworkElement> der Klasse abstammen, kann ihre Verwendung zu einem deutlich mehr Speicherverbrauch in Ihrer Anwendung kommen. Wenn Sie die <xref:System.Windows.FrameworkElement> Funktionen für Ihren grafischen Inhalt wirklich <xref:System.Windows.Media.Drawing> nicht benötigen, sollten Sie die leichteren Objekte verwenden.  
  
 Weitere Informationen <xref:System.Windows.Media.Drawing> zu Objekten finden Sie unter [Übersicht über Zeichnungsobjekte](../graphics-multimedia/drawing-objects-overview.md).  
  
<a name="StreamGeometry_Objects"></a>
## <a name="streamgeometry-objects"></a>StreamGeometry-Objekte  
 Das <xref:System.Windows.Media.StreamGeometry> Objekt ist eine <xref:System.Windows.Media.PathGeometry> leichte Alternative zum Erstellen geometrischer Formen. Verwenden <xref:System.Windows.Media.StreamGeometry> Sie eine, wenn Sie eine komplexe Geometrie beschreiben müssen. <xref:System.Windows.Media.StreamGeometry>ist für die <xref:System.Windows.Media.PathGeometry> Handhabung vieler Objekte optimiert und <xref:System.Windows.Media.PathGeometry> schneidet im Vergleich zur Verwendung vieler einzelner Objekte besser ab.  
  
 Im folgenden Beispiel wird die Attributsyntax <xref:System.Windows.Media.StreamGeometry> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]verwendet, um eine Dreiecksstruktur in zu erstellen.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Weitere Informationen <xref:System.Windows.Media.StreamGeometry> zu Objekten finden Sie unter [Erstellen eines Shapes mithilfe einer StreamGeometry](../graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
<a name="DrawingVisual_Objects"></a>
## <a name="drawingvisual-objects"></a>DrawingVisual-Objekte  
 Das <xref:System.Windows.Media.DrawingVisual> Objekt ist eine einfache Zeichnungsklasse, die zum Rendern von Formen, Bildern oder Text verwendet wird. Diese Klasse wird als einfach angesehen, weil sie weder Layout noch Ereignisbehandlung bereitstellt. Dadurch wird die Leistung gesteigert. Aus diesem Grund eignen sich Zeichnungen für Hintergründe und ClipArt. Weitere Informationen finden Sie unter [Verwenden von DrawingVisual-Objekten](../graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="Images"></a>
## <a name="images"></a>Bilder  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Imaging bietet eine deutliche Verbesserung gegenüber den Bildverarbeitungsfunktionen in früheren Versionen von Windows. Imaging-Funktionen, z. B. das Anzeigen einer Bitmap oder die Verwendung eines Abbilds auf einem gemeinsamen Steuerelement, wurden in erster Linie von der Microsoft Windows Graphics Device Interface (GDI) oder der Microsoft Windows GDI+ Application Programming Interface (API) verarbeitet. Diese APIs stellten grundlegende Bildverarbeitungsfunktionen bereit, verfügten jedoch über Funktionen wie Unterstützung für Codec-Erweiterbarkeit und Unterstützung für Bildunterstützung mit hoher Genauigkeit. WPF Imaging-APIs wurden überarbeitet, um die Mängel von GDI und GDI+ zu beheben und einen neuen Satz von APIs zum Anzeigen und Verwenden von Bildern in Ihren Anwendungen bereitzustellen.  
  
 Beim Verwenden von Bildern sollten Sie die folgenden Empfehlungen in Betracht ziehen, um eine bessere Leistung zu erzielen:  
  
- Wenn Ihre Anwendung die Anzeige von Miniaturbildern erfordert, ist das Erstellen einer Bildversion in reduzierter Größe ratsam. Standardmäßig lädt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Bild und decodiert es in seine vollständige Größe. Wenn Sie nur eine Miniaturansicht des Bilds möchten, decodiert [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Bild überflüssigerweise in seine vollständige Größe und skaliert es dann auf die Größe der Miniaturansicht. Um diesen unnötigen Aufwand zu vermeiden, können Sie entweder bei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine Decodierung des Bilds in Miniaturansichtgröße oder [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zum Laden eines Bilds in Miniaturansichtgröße auffordern.  
  
- Decodieren Sie das Bild immer in die gewünschte Größe und nicht in die Standardgröße. Wie bereits erwähnt, fordern Sie bei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine Decodierung des Bilds in die gewünschte Größe und nicht in die vollständige Größe an. Auf diese Weise reduzieren Sie nicht nur das Workingset der Anwendung, Sie erhöhen auch die Ausführungsgeschwindigkeit.  
  
- Kombinieren Sie die Bilder nach Möglichkeit in einem Einzelbild (z.B. ein Filmstreifen, der sich aus mehreren Bildern zusammensetzt).  
  
- Weitere Informationen finden Sie unter [Übersicht über die Bildverarbeitung](../graphics-multimedia/imaging-overview.md).  
  
### <a name="bitmapscalingmode"></a>BitmapScalingMode  
 Wenn Sie den Maßstab einer Bitmap animieren, kann der standardmäßige hochwertige Bild-Resampling-Algorithmus manchmal genügend Systemressourcen verbrauchen, um eine Verschlechterung der Bildrate zu verursachen, wodurch Animationen effektiv stottern. Durch Festlegen <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> der <xref:System.Windows.Media.RenderOptions> Eigenschaft <xref:System.Windows.Media.BitmapScalingMode.LowQuality>des Objekts auf können Sie beim Skalieren einer Bitmap eine glattere Animation erstellen. <xref:System.Windows.Media.BitmapScalingMode.LowQuality>der Modus [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] weist die Rendering-Engine an, bei der Verarbeitung von Bildern von einem qualitätsoptimierten Algorithmus zu einem geschwindigkeitsoptimierten Algorithmus zu wechseln.  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.Media.BitmapScalingMode> wie die für ein Bildobjekt festgelegt werden.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### <a name="cachinghint"></a>CachingHint  
 Speichert standardmäßig [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nicht den gerenderten Inhalt von <xref:System.Windows.Media.TileBrush> Objekten, z. <xref:System.Windows.Media.DrawingBrush> B. und <xref:System.Windows.Media.VisualBrush>. In statischen Szenarien, in <xref:System.Windows.Media.TileBrush> denen sich der Inhalt oder die Verwendung der in der Szene nicht ändert, ist dies sinnvoll, da sie Videospeicher spart. Es macht nicht so viel <xref:System.Windows.Media.TileBrush> Sinn, wenn ein mit statischem Inhalt nicht statisch <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.VisualBrush> verwendet wird, z. B. wenn ein statisches oder der Oberfläche eines rotierenden 3D-Objekts zugeordnet ist. Das Standardverhalten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] von besteht darin, den <xref:System.Windows.Media.DrawingBrush> gesamten <xref:System.Windows.Media.VisualBrush> Inhalt des oder für jeden Frame neu zu rendern, auch wenn der Inhalt nicht geändert wird.  
  
 Durch Festlegen <xref:System.Windows.Media.RenderOptions.CachingHint%2A> der <xref:System.Windows.Media.RenderOptions> Eigenschaft <xref:System.Windows.Media.CachingHint.Cache>des Objekts auf können Sie die Leistung erhöhen, indem Sie zwischengespeicherte Versionen der gekachelten Pinselobjekte verwenden.  
  
 Die <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> und Eigenschaftswerte sind relative <xref:System.Windows.Media.TileBrush> Größenwerte, die bestimmen, wann das Objekt aufgrund von Größenänderungen neu generiert werden soll. Wenn Sie die <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> Eigenschaft beispielsweise auf 2.0 <xref:System.Windows.Media.TileBrush> festlegen, muss der Cache für den einzigen Cache neu generiert werden, wenn seine Größe doppelt so groß ist wie der aktuelle Cache.  
  
 Das folgende Beispiel zeigt, wie sie die <xref:System.Windows.Media.DrawingBrush>Option Zwischenspeicherungshinweis für eine verwenden.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet3)]
 [!code-vb[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet3)]  
  
## <a name="see-also"></a>Siehe auch

- [Optimieren der WPF-Anwendungsleistung](optimizing-wpf-application-performance.md)
- [Planen der Anwendungsleistung](planning-for-application-performance.md)
- [Vorteile der Hardware nutzen](optimizing-performance-taking-advantage-of-hardware.md)
- [Layout und Entwurf](optimizing-performance-layout-and-design.md)
- [Objektverhalten](optimizing-performance-object-behavior.md)
- [Anwendungsressourcen](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Datenbindung](optimizing-performance-data-binding.md)
- [Weitere Leistungsempfehlungen](optimizing-performance-other-recommendations.md)
- [Tipps und Tricks zu Animationen](../graphics-multimedia/animation-tips-and-tricks.md)
