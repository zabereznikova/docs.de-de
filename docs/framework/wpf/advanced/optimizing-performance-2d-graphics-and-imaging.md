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
- 2-D graphics [WPF]
- images [WPF], optimizing performance
ms.assetid: e335601e-28c8-4d64-ba27-778fffd55f72
ms.openlocfilehash: 4fca9231872a268470c9bcfa73e7a0c0a26d300c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074988"
---
# <a name="optimizing-performance-2d-graphics-and-imaging"></a>Optimieren der Leistung: 2D-Grafiken und Bildverarbeitung
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Stellt eine Vielzahl von 2D-Grafiken und bildverarbeitung Funktionen, die optimiert werden kann für den Anforderungen Ihrer Anwendung bereit. Dieses Thema enthält Informationen über die Leistungsoptimierung in diesen Bereichen.  

<a name="Drawing_and_Shapes"></a>   
## <a name="drawing-and-shapes"></a>Zeichnen und Formen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sowohl <xref:System.Windows.Media.Drawing> und <xref:System.Windows.Shapes.Shape> Objekten um grafischen Zeichnungsinhalt darzustellen. Allerdings <xref:System.Windows.Media.Drawing> Objekte sind jedoch einfachere Konstrukte als <xref:System.Windows.Shapes.Shape> Objekte aus, und stellen bessere Leistungsmerkmale bereit.  
  
 Ein <xref:System.Windows.Shapes.Shape> können Sie grafische Formen auf dem Bildschirm zu zeichnen. Da sie von abgeleitet werden die <xref:System.Windows.FrameworkElement> -Klasse, <xref:System.Windows.Shapes.Shape> können Objekte in Bereichen und den meisten Steuerelementen verwendet werden.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet mehrere Ebenen des Zugriffs auf Grafiken und Renderingdienste. Auf der obersten Ebene <xref:System.Windows.Shapes.Shape> Objekte sind einfach zu verwenden und bieten viele nützliche Features, z.B. Layout und Ereignisbehandlung. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet eine Reihe von sofort zu verwendende Shape-Objekte. Alle Shape-Objekte erben von der <xref:System.Windows.Shapes.Shape> Klasse. Verfügbare Shape-Objekte sind <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, und <xref:System.Windows.Shapes.Rectangle>.  
  
 <xref:System.Windows.Media.Drawing> Objekte, auf der anderen Seite leiten Sie nicht von der <xref:System.Windows.FrameworkElement> Klasse und bieten eine schlankere Implementierung für Rendering von Formen, Bildern und Text.  
  
 Es gibt vier Arten von <xref:System.Windows.Media.Drawing> Objekte:  
  
-   <xref:System.Windows.Media.GeometryDrawing> Zeichnet eine Form.  
  
-   <xref:System.Windows.Media.ImageDrawing> Zeichnet ein Bild.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing> Zeichnet Text.  
  
-   <xref:System.Windows.Media.DrawingGroup> Zeichnet andere Zeichnungen. Verwenden Sie eine Zeichnungsgruppe, um andere Zeichnungen in einer zusammengesetzten Zeichnung zu kombinieren.  
  
 Die <xref:System.Windows.Media.GeometryDrawing> Objekt wird verwendet, um Geometrieinhalt zu rendern. Die <xref:System.Windows.Media.Geometry> -Klasse und der konkreten Klassen wie z. B. ableiten, <xref:System.Windows.Media.CombinedGeometry>, <xref:System.Windows.Media.EllipseGeometry>, und <xref:System.Windows.Media.PathGeometry>, bieten eine Möglichkeit für das Rendering von 2D-Grafiken, als auch Treffertests und Clipping-Unterstützung bereitstellen. Mit Geometry-Objekten können beispielsweise der Bereich eines Steuerelements oder der auf ein Bild anzuwendende Clip-Bereich definiert werden. Bei Geometry-Objekten kann es sich um einfache Bereiche wie Rechtecke und Kreise oder um aus einem oder mehreren geometrischen Objekten zusammengesetzte Regionen handeln. Komplexere geometrische Regionen können erstellt werden, durch Kombinieren von <xref:System.Windows.Media.PathSegment>--abgeleitete Objekte wie z. B. <xref:System.Windows.Media.ArcSegment>, <xref:System.Windows.Media.BezierSegment>, und <xref:System.Windows.Media.QuadraticBezierSegment>.  
  
 Auf der Oberfläche der <xref:System.Windows.Media.Geometry> Klasse und die <xref:System.Windows.Shapes.Shape> Klasse sind sehr ähnlich. Beide werden für das Rendering von 2D-Grafiken verwendet, und verfügen über ähnliche konkrete Klassen, die von ihnen abgeleitet z. B. werden <xref:System.Windows.Media.EllipseGeometry> und <xref:System.Windows.Shapes.Ellipse>. Es gibt jedoch wichtige Unterschiede zwischen diesen zwei Sätzen von Klassen. Zum einen die <xref:System.Windows.Media.Geometry> -Klasse fehlen einige Funktionen des die <xref:System.Windows.Shapes.Shape> Klasse, z. B. die Möglichkeit, sich selbst zu zeichnen. Zum Zeichnen eines Geometry-Objekts muss eine andere Klasse, beispielsweise DrawingContext, Drawing oder Path (dabei ist zu beachten, dass ein Path eine Shape ist), verwendet werden, um den Zeichnungsvorgang auszuführen. Renderingeigenschaften wie Füllung, Strich und Strichstärke befinden sich in der Klasse, die das Geometry-Objekt zeichnet, während ein Shape-Objekt diese Eigenschaften enthält. Eine Möglichkeit zur Annäherung an diesen Unterschied besteht darin, dass ein Geometry-Objekt einen Bereich definiert, z.B. einen Kreis, während ein Shape-Objekt definiert, wie dieser Bereich gefüllt und konturiert wird und eine Komponente des Layoutsystems ist.  
  
 Da <xref:System.Windows.Shapes.Shape> Objekte Ableiten der <xref:System.Windows.FrameworkElement> -Klasse, deren Verwendung kann deutlich mehr Speicherverbrauch in Ihrer Anwendung hinzufügen. Wenn Sie nicht wirklich benötigen die <xref:System.Windows.FrameworkElement> Features für den grafischen Inhalt, erwägen Sie die Verwendung der schlankere <xref:System.Windows.Media.Drawing> Objekte.  
  
 Weitere Informationen zu <xref:System.Windows.Media.Drawing> Objekten finden Sie [Übersicht über Zeichnungsobjekte](../graphics-multimedia/drawing-objects-overview.md).  
  
<a name="StreamGeometry_Objects"></a>   
## <a name="streamgeometry-objects"></a>StreamGeometry-Objekte  
 Die <xref:System.Windows.Media.StreamGeometry> Objekt ist eine einfache Alternative zu <xref:System.Windows.Media.PathGeometry> zum Erstellen geometrischer Formen. Verwenden einer <xref:System.Windows.Media.StreamGeometry> Wenn Sie eine komplexe Geometrie beschreiben müssen. <xref:System.Windows.Media.StreamGeometry> ist optimiert für die Behandlung vieler <xref:System.Windows.Media.PathGeometry> Objekten und bietet eine bessere Leistung im Vergleich zur Verwendung mehrerer einzelner <xref:System.Windows.Media.PathGeometry> Objekte.  
  
 Im folgenden Beispiel wird eine Attributsyntax eine dreieckige erstellen <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Weitere Informationen zu <xref:System.Windows.Media.StreamGeometry> Objekten finden Sie [Erstellen einer Form mithilfe von StreamGeometry](../graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
<a name="DrawingVisual_Objects"></a>   
## <a name="drawingvisual-objects"></a>DrawingVisual-Objekte  
 Die <xref:System.Windows.Media.DrawingVisual> Objekt ist eine einfache Zeichnungsklasse, die zum Rendern von Formen, Bildern oder Text verwendet wird. Diese Klasse wird als einfach angesehen, weil sie weder Layout noch Ereignisbehandlung bereitstellt. Dadurch wird die Leistung gesteigert. Aus diesem Grund sind Zeichnungen für Hintergründe und ClipArt ideal. Weitere Informationen finden Sie unter [Verwenden von DrawingVisual-Objekten](../graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="Images"></a>   
## <a name="images"></a>Bilder  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -bildverarbeitung stellt eine bedeutende Verbesserung gegenüber den bildverarbeitungsfähigkeiten in vorherigen Versionen von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]. Die Bildverarbeitungsfähigkeiten wie das Anzeigen einer Bitmap oder das Verwenden eines Bilds für ein allgemeines Steuerelement wurden hauptsächlich von Microsoft Windows Graphics Device Interface (GDI) oder der Microsoft Windows GDI+-API behandelt. Diese API hat Baseline-Bildverarbeitungsfunktionen bereitgestellt, hatte aber keine Features wie die Unterstützung von Codec-Erweiterbarkeit und hochwertigen Bildern. Die WPF-Bildverarbeitungs-APIs wurden neu entworfen, um die Nachteile von GDI und GDI+ zu beheben und einen neuen Satz von APIs bereitzustellen, um Bilder in den Anwendungen anzeigen und verwenden können.  
  
 Beim Verwenden von Bildern sollten Sie die folgenden Empfehlungen in Betracht ziehen, um eine bessere Leistung zu erzielen:  
  
-   Wenn Ihre Anwendung die Anzeige von Miniaturbildern erfordert, ist das Erstellen einer Bildversion in reduzierter Größe ratsam. Standardmäßig lädt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Bild und decodiert es in seine vollständige Größe. Wenn Sie nur eine Miniaturansicht des Bilds möchten, decodiert [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Bild überflüssigerweise in seine vollständige Größe und skaliert es dann auf die Größe der Miniaturansicht. Um diesen unnötigen Aufwand zu vermeiden, können Sie entweder bei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine Decodierung des Bilds in Miniaturansichtgröße oder [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zum Laden eines Bilds in Miniaturansichtgröße auffordern.  
  
-   Decodieren Sie das Bild immer in die gewünschte Größe und nicht in die Standardgröße. Wie bereits erwähnt, fordern Sie bei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine Decodierung des Bilds in die gewünschte Größe und nicht in die vollständige Größe an. Auf diese Weise reduzieren Sie nicht nur das Workingset der Anwendung, Sie erhöhen auch die Ausführungsgeschwindigkeit.  
  
-   Kombinieren Sie die Bilder nach Möglichkeit in einem Einzelbild (z.B. ein Filmstreifen, der sich aus mehreren Bildern zusammensetzt).  
  
-   Weitere Informationen finden Sie unter [Übersicht über die Bildverarbeitung](../graphics-multimedia/imaging-overview.md).  
  
### <a name="bitmapscalingmode"></a>BitmapScalingMode  
 Beim Animieren der Skalierung von Bitmaps kann der Standardalgorithmus für das Resampling von Bildern hoher Qualität zuweilen einen solchen Umfang an Systemressourcen beanspruchen, dass eine Verringerung der Einzelbildrate auftritt und Animationen ruckartig wiedergegeben werden. Durch Festlegen der <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> Eigenschaft der <xref:System.Windows.Media.RenderOptions> -Objekt <xref:System.Windows.Media.BitmapScalingMode.LowQuality> Animationen erstellen, wenn eine Bitmap skaliert. <xref:System.Windows.Media.BitmapScalingMode.LowQuality> Modus weist die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Rendering-Engine beim Verarbeiten von Images von einem qualitätsoptimierten Algorithmus auf einen geschwindigkeitsoptimierten Algorithmus umzuschalten.  
  
 Im folgende Beispiel veranschaulicht die legen Sie die <xref:System.Windows.Media.BitmapScalingMode> für ein Image-Objekt.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### <a name="cachinghint"></a>CachingHint  
 In der Standardeinstellung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zwischenspeichert, wenn der gerenderte Inhalt von <xref:System.Windows.Media.TileBrush> Objekte, z. B. <xref:System.Windows.Media.DrawingBrush> und <xref:System.Windows.Media.VisualBrush>. In statischen Szenarios, in denen weder der Inhalt noch die Verwendung der <xref:System.Windows.Media.TileBrush> in der Szene ändern, ist sinnvoll, da Videospeicher gespart wird. Macht es nicht als sinnvoll, wenn eine <xref:System.Windows.Media.TileBrush> mit statischem Inhalt in eine nicht statische Weise verwendet wird – z. B., wenn eine statische <xref:System.Windows.Media.DrawingBrush> oder <xref:System.Windows.Media.VisualBrush> der Oberfläche eines sich drehenden 3D-Objekts zugeordnet ist. Das Standardverhalten des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] besteht darin, den gesamten Inhalt der erneut Rendern der <xref:System.Windows.Media.DrawingBrush> oder <xref:System.Windows.Media.VisualBrush> für jeden Frame, selbst wenn der Inhalt ist unveränderlich.  
  
 Durch Festlegen der <xref:System.Windows.Media.RenderOptions.CachingHint%2A> Eigenschaft der <xref:System.Windows.Media.RenderOptions> -Objekt <xref:System.Windows.Media.CachingHint.Cache> können Sie die Leistung mithilfe von zwischengespeicherten Versionen der gekachelten Pinselobjekte erhöhen.  
  
 Die <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> und <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> Werte sind Werte von relativer Größe, die bestimmen, wann das <xref:System.Windows.Media.TileBrush> -Objekt aufgrund einer geänderten Skalierung neu generiert werden sollte. Z. B. durch Festlegen der <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> Eigenschaft auf 2.0, den Cache für die <xref:System.Windows.Media.TileBrush> nur neu generiert werden, überschreitet die Größe zweimal die Größe des aktuellen Caches.  
  
 Das folgende Beispiel zeigt, wie Sie mit die Zwischenspeicherungshinweisoption für eine <xref:System.Windows.Media.DrawingBrush>.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet3)]
 [!code-vb[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet3)]  
  
## <a name="see-also"></a>Siehe auch

- [Optimieren der WPF-Anwendungsleistung](optimizing-wpf-application-performance.md)
- [Planen der Anwendungsleistung](planning-for-application-performance.md)
- [Nutzen der Vorteile der Hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Layout und Entwurf](optimizing-performance-layout-and-design.md)
- [Objektverhalten](optimizing-performance-object-behavior.md)
- [Anwendungsressourcen](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Datenbindung](optimizing-performance-data-binding.md)
- [Weitere Leistungsempfehlungen](optimizing-performance-other-recommendations.md)
- [Tipps und Tricks zu Animationen](../graphics-multimedia/animation-tips-and-tricks.md)
