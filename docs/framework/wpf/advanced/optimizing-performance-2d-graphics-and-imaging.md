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
ms.openlocfilehash: 59ac7a5aa8b0591c51cdb6ee0d6435649e22fade
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111217"
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
  
 Das <xref:System.Windows.Media.GeometryDrawing> Objekt wird zum Rendern von Geometrieinhalten verwendet. Die <xref:System.Windows.Media.Geometry> Klasse und die daraus resultierenden Betonklassen, z. <xref:System.Windows.Media.CombinedGeometry>B. , <xref:System.Windows.Media.EllipseGeometry>und <xref:System.Windows.Media.PathGeometry>, bieten ein Mittel zum Rendern von 2D-Grafiken sowie für Treffertests und Clipping-Unterstützung. Mit Geometry-Objekten können beispielsweise der Bereich eines Steuerelements oder der auf ein Bild anzuwendende Clip-Bereich definiert werden. Bei Geometry-Objekten kann es sich um einfache Bereiche wie Rechtecke und Kreise oder um aus einem oder mehreren geometrischen Objekten zusammengesetzte Regionen handeln. Komplexere geometrische Bereiche können <xref:System.Windows.Media.PathSegment>durch Kombinieren von <xref:System.Windows.Media.ArcSegment>-abgeleiteten Objekten wie , <xref:System.Windows.Media.BezierSegment>und <xref:System.Windows.Media.QuadraticBezierSegment>erstellt werden.  
  
 Oberflächlich betrachtet sind <xref:System.Windows.Media.Geometry> sich <xref:System.Windows.Shapes.Shape> die Klasse und die Klasse ziemlich ähnlich. Beide werden beim Rendern von 2D-Grafiken verwendet und beide haben ähnliche <xref:System.Windows.Media.EllipseGeometry> <xref:System.Windows.Shapes.Ellipse>konkrete Klassen, die sich z. B. von ihnen ableiten, und . Es gibt jedoch wichtige Unterschiede zwischen diesen zwei Sätzen von Klassen. Zum einen <xref:System.Windows.Media.Geometry> fehlt der Klasse ein Teil <xref:System.Windows.Shapes.Shape> der Funktionalität der Klasse, z. B. die Möglichkeit, sich selbst zu zeichnen. Zum Zeichnen eines Geometry-Objekts muss eine andere Klasse, beispielsweise DrawingContext, Drawing oder Path (dabei ist zu beachten, dass ein Path eine Shape ist), verwendet werden, um den Zeichnungsvorgang auszuführen. Renderingeigenschaften wie Füllung, Strich und Strichstärke befinden sich in der Klasse, die das Geometry-Objekt zeichnet, während ein Shape-Objekt diese Eigenschaften enthält. Eine Möglichkeit zur Annäherung an diesen Unterschied besteht darin, dass ein Geometry-Objekt einen Bereich definiert, z.B. einen Kreis, während ein Shape-Objekt definiert, wie dieser Bereich gefüllt und konturiert wird und eine Komponente des Layoutsystems ist.  
  
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
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Imaging bietet eine deutliche Verbesserung gegenüber den Bildverarbeitungsfunktionen in früheren Versionen von Windows. Die Bildverarbeitungsfähigkeiten wie das Anzeigen einer Bitmap oder das Verwenden eines Bilds für ein allgemeines Steuerelement wurden hauptsächlich von Microsoft Windows Graphics Device Interface (GDI) oder der Microsoft Windows GDI+-API behandelt. Diese API hat Baseline-Bildverarbeitungsfunktionen bereitgestellt, hatte aber keine Features wie die Unterstützung von Codec-Erweiterbarkeit und hochwertigen Bildern. Die WPF-Bildverarbeitungs-APIs wurden neu entworfen, um die Nachteile von GDI und GDI+ zu beheben und einen neuen Satz von APIs bereitzustellen, um Bilder in den Anwendungen anzeigen und verwenden können.  
  
 Beim Verwenden von Bildern sollten Sie die folgenden Empfehlungen in Betracht ziehen, um eine bessere Leistung zu erzielen:  
  
- Wenn Ihre Anwendung die Anzeige von Miniaturbildern erfordert, ist das Erstellen einer Bildversion in reduzierter Größe ratsam. Standardmäßig lädt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Bild und decodiert es in seine vollständige Größe. Wenn Sie nur eine Miniaturansicht des Bilds möchten, decodiert [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Bild überflüssigerweise in seine vollständige Größe und skaliert es dann auf die Größe der Miniaturansicht. Um diesen unnötigen Aufwand zu vermeiden, können Sie entweder bei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine Decodierung des Bilds in Miniaturansichtgröße oder [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zum Laden eines Bilds in Miniaturansichtgröße auffordern.  
  
- Decodieren Sie das Bild immer in die gewünschte Größe und nicht in die Standardgröße. Wie bereits erwähnt, fordern Sie bei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine Decodierung des Bilds in die gewünschte Größe und nicht in die vollständige Größe an. Auf diese Weise reduzieren Sie nicht nur das Workingset der Anwendung, Sie erhöhen auch die Ausführungsgeschwindigkeit.  
  
- Kombinieren Sie die Bilder nach Möglichkeit in einem Einzelbild (z.B. ein Filmstreifen, der sich aus mehreren Bildern zusammensetzt).  
  
- Weitere Informationen finden Sie unter [Übersicht über die Bildverarbeitung](../graphics-multimedia/imaging-overview.md).  
  
### <a name="bitmapscalingmode"></a>BitmapScalingMode  
 Beim Animieren der Skalierung von Bitmaps kann der Standardalgorithmus für das Resampling von Bildern hoher Qualität zuweilen einen solchen Umfang an Systemressourcen beanspruchen, dass eine Verringerung der Einzelbildrate auftritt und Animationen ruckartig wiedergegeben werden. Durch Festlegen <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> der <xref:System.Windows.Media.RenderOptions> Eigenschaft <xref:System.Windows.Media.BitmapScalingMode.LowQuality> des Objekts können Sie beim Skalieren einer Bitmap eine glattere Animation erstellen. <xref:System.Windows.Media.BitmapScalingMode.LowQuality>der Modus [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] weist die Rendering-Engine an, bei der Verarbeitung von Bildern von einem qualitätsoptimierten Algorithmus zu einem geschwindigkeitsoptimierten Algorithmus zu wechseln.  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.Media.BitmapScalingMode> wie die für ein Bildobjekt festgelegt werden.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### <a name="cachinghint"></a>CachingHint  
 Speichert standardmäßig [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nicht den gerenderten Inhalt von <xref:System.Windows.Media.TileBrush> Objekten, z. <xref:System.Windows.Media.DrawingBrush> B. und <xref:System.Windows.Media.VisualBrush>. In statischen Szenarien, in denen <xref:System.Windows.Media.TileBrush> sich weder der Inhalt noch die Verwendung des in der Szene ändert, ist dies sinnvoll, da es Videospeicher schont. Es macht nicht so viel <xref:System.Windows.Media.TileBrush> Sinn, wenn ein mit statischem Inhalt nicht statisch <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.VisualBrush> verwendet wird, z. B. wenn ein statisches oder der Oberfläche eines rotierenden 3D-Objekts zugeordnet ist. Das Standardverhalten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] von besteht darin, den <xref:System.Windows.Media.DrawingBrush> gesamten <xref:System.Windows.Media.VisualBrush> Inhalt des oder für jeden Frame neu zu rendern, auch wenn der Inhalt nicht geändert wird.  
  
 Durch Festlegen <xref:System.Windows.Media.RenderOptions.CachingHint%2A> der <xref:System.Windows.Media.RenderOptions> Eigenschaft <xref:System.Windows.Media.CachingHint.Cache> des Objekts können Sie die Leistung erhöhen, indem Sie zwischengespeicherte Versionen der gekachelten Pinselobjekte verwenden.  
  
 Die <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> und Eigenschaftswerte sind relative <xref:System.Windows.Media.TileBrush> Größenwerte, die bestimmen, wann das Objekt aufgrund von Größenänderungen neu generiert werden soll. Wenn Sie die <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> Eigenschaft beispielsweise auf 2.0 <xref:System.Windows.Media.TileBrush> festlegen, muss der Cache für den einzigen Cache neu generiert werden, wenn seine Größe doppelt so groß ist wie der aktuelle Cache.  
  
 Das folgende Beispiel zeigt, wie sie die <xref:System.Windows.Media.DrawingBrush>Option Zwischenspeicherungshinweis für eine verwenden.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet3)]
 [!code-vb[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet3)]  
  
## <a name="see-also"></a>Weitere Informationen

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
