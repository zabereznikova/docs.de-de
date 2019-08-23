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
ms.openlocfilehash: 764e7e802ccaff50b76229b9441380bfe77fefb5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933353"
---
# <a name="optimizing-performance-2d-graphics-and-imaging"></a>Optimieren der Leistung: 2D-Grafiken und Bildverarbeitung
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt zahlreiche Funktionen für 2D-Grafiken und Bildverarbeitung zur Verfügung, die den Anforderungen Ihrer Anwendung entsprechend optimiert werden können. Dieses Thema enthält Informationen über die Leistungsoptimierung in diesen Bereichen.  

<a name="Drawing_and_Shapes"></a>   
## <a name="drawing-and-shapes"></a>Zeichnen und Formen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]stellt sowohl <xref:System.Windows.Media.Drawing> - <xref:System.Windows.Shapes.Shape> als auch-Objekte zur Darstellung von grafischer Zeichnungs Inhalt bereit. Objekte sind jedoch einfachere Konstrukte als <xref:System.Windows.Shapes.Shape> Objekte und bieten bessere Leistungsmerkmale. <xref:System.Windows.Media.Drawing>  
  
 Mit <xref:System.Windows.Shapes.Shape> einem können Sie eine grafische Form auf dem Bildschirm zeichnen. Da Sie von der <xref:System.Windows.FrameworkElement> -Klasse abgeleitet sind, <xref:System.Windows.Shapes.Shape> können-Objekte in Bereichen und den meisten Steuerelementen verwendet werden.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet mehrere Ebenen für den Zugriff auf Grafiken und Renderingdienste. Auf der obersten Ebene <xref:System.Windows.Shapes.Shape> sind-Objekte einfach zu verwenden und bieten zahlreiche nützliche Features wie Layout und Ereignis Behandlung. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt eine Reihe von vorgefertigten Shape-Objekten zur Verfügung. Alle Shape-Objekte erben von <xref:System.Windows.Shapes.Shape> der-Klasse. Zu den verfügbaren <xref:System.Windows.Shapes.Ellipse>Shape-Objekten zählen <xref:System.Windows.Shapes.Polyline> <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Rectangle>, <xref:System.Windows.Shapes.Polygon>, und.  
  
 <xref:System.Windows.Media.Drawing>Objekte hingegen werden nicht von der <xref:System.Windows.FrameworkElement> -Klasse abgeleitet und bieten eine einfachere Implementierung zum Rendern von Formen, Bildern und Text.  
  
 Es gibt vier Arten von <xref:System.Windows.Media.Drawing> Objekten:  
  
- <xref:System.Windows.Media.GeometryDrawing>Zeichnet eine Form.  
  
- <xref:System.Windows.Media.ImageDrawing>Zeichnet ein Bild.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>Zeichnet Text.  
  
- <xref:System.Windows.Media.DrawingGroup>Zeichnet andere Zeichnungen. Verwenden Sie eine Zeichnungsgruppe, um andere Zeichnungen in einer zusammengesetzten Zeichnung zu kombinieren.  
  
 Das <xref:System.Windows.Media.GeometryDrawing> -Objekt wird zum Rendering von Geometrie Inhalten verwendet. Die <xref:System.Windows.Media.Geometry> -Klasse und die konkreten Klassen, die von ihr abgeleitet werden <xref:System.Windows.Media.CombinedGeometry>, <xref:System.Windows.Media.EllipseGeometry>z. <xref:System.Windows.Media.PathGeometry>b., und, bieten eine Möglichkeit zum Rendern von 2D-Grafiken sowie zum Bereitstellen von Treffer Tests und Clipping-Unterstützung. Mit Geometry-Objekten können beispielsweise der Bereich eines Steuerelements oder der auf ein Bild anzuwendende Clip-Bereich definiert werden. Bei Geometry-Objekten kann es sich um einfache Bereiche wie Rechtecke und Kreise oder um aus einem oder mehreren geometrischen Objekten zusammengesetzte Regionen handeln. Komplexere geometrische Bereiche können erstellt werden, indem von <xref:System.Windows.Media.PathSegment>abgeleitete Objekte kombiniert werden, <xref:System.Windows.Media.ArcSegment>wie <xref:System.Windows.Media.BezierSegment>z. <xref:System.Windows.Media.QuadraticBezierSegment>b., und.  
  
 Auf der-Oberfläche <xref:System.Windows.Media.Geometry> sind die- <xref:System.Windows.Shapes.Shape> Klasse und die-Klasse sehr ähnlich. Beide werden beim Rendern von 2D-Grafiken verwendet, und beide verfügen über ähnliche konkrete Klassen, die von Ihnen abgeleitet <xref:System.Windows.Media.EllipseGeometry> werden <xref:System.Windows.Shapes.Ellipse>, z. b. und. Es gibt jedoch wichtige Unterschiede zwischen diesen zwei Sätzen von Klassen. Für eine der Klassen <xref:System.Windows.Media.Geometry> fehlt die Funktion <xref:System.Windows.Shapes.Shape> der-Klasse, z. b. die Fähigkeit, sich selbst zu zeichnen. Zum Zeichnen eines Geometry-Objekts muss eine andere Klasse, beispielsweise DrawingContext, Drawing oder Path (dabei ist zu beachten, dass ein Path eine Shape ist), verwendet werden, um den Zeichnungsvorgang auszuführen. Renderingeigenschaften wie Füllung, Strich und Strichstärke befinden sich in der Klasse, die das Geometry-Objekt zeichnet, während ein Shape-Objekt diese Eigenschaften enthält. Eine Möglichkeit zur Annäherung an diesen Unterschied besteht darin, dass ein Geometry-Objekt einen Bereich definiert, z.B. einen Kreis, während ein Shape-Objekt definiert, wie dieser Bereich gefüllt und konturiert wird und eine Komponente des Layoutsystems ist.  
  
 Da <xref:System.Windows.Shapes.Shape> Objekte von der <xref:System.Windows.FrameworkElement> -Klasse abgeleitet werden, kann die Verwendung der Objekte deutlich mehr Arbeitsspeicher Auslastung in Ihrer Anwendung zur Verfügung stehen. Wenn Sie die <xref:System.Windows.FrameworkElement> Funktionen für Ihre grafischen Inhalte wirklich nicht benötigen, sollten Sie die Verwendung der Objekte mit <xref:System.Windows.Media.Drawing> heller Gewichtung in Erwägung gezogen.  
  
 Weitere Informationen zu <xref:System.Windows.Media.Drawing> Objekten finden Sie unter [Übersicht über Zeichnungsobjekte](../graphics-multimedia/drawing-objects-overview.md).  
  
<a name="StreamGeometry_Objects"></a>   
## <a name="streamgeometry-objects"></a>StreamGeometry-Objekte  
 Das <xref:System.Windows.Media.StreamGeometry> -Objekt ist eine vereinfachte Alternative <xref:System.Windows.Media.PathGeometry> zu zum Erstellen geometrischer Formen. Verwenden Sie, wenn Sie eine komplexe Geometrie beschreiben müssen. <xref:System.Windows.Media.StreamGeometry> <xref:System.Windows.Media.StreamGeometry>ist für die Verarbeitung vieler <xref:System.Windows.Media.PathGeometry> -Objekte optimiert und verbessert sich im Vergleich zur Verwendung <xref:System.Windows.Media.PathGeometry> vieler einzelner Objekte.  
  
 Im folgenden Beispiel wird die-Attribut Syntax verwendet, <xref:System.Windows.Media.StreamGeometry> um [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]eine dreieckige in zu erstellen.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Weitere Informationen zu <xref:System.Windows.Media.StreamGeometry> Objekten finden Sie unter [Erstellen einer Form mithilfe von StreamGeometry](../graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
<a name="DrawingVisual_Objects"></a>   
## <a name="drawingvisual-objects"></a>DrawingVisual-Objekte  
 Das <xref:System.Windows.Media.DrawingVisual> -Objekt ist eine vereinfachte Zeichnungs Klasse, die zum Rendering von Formen, Bildern oder Text verwendet wird. Diese Klasse wird als einfach angesehen, weil sie weder Layout noch Ereignisbehandlung bereitstellt. Dadurch wird die Leistung gesteigert. Aus diesem Grund sind Zeichnungen für Hintergründe und ClipArt ideal. Weitere Informationen finden Sie unter [Verwenden von DrawingVisual-Objekten](../graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="Images"></a>   
## <a name="images"></a>Bilder  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]die Abbild Erstellung bietet eine bedeutende Verbesserung gegenüber den Abbild Erstellungs Funktionen in früheren Versionen von Windows. Die Bildverarbeitungsfähigkeiten wie das Anzeigen einer Bitmap oder das Verwenden eines Bilds für ein allgemeines Steuerelement wurden hauptsächlich von Microsoft Windows Graphics Device Interface (GDI) oder der Microsoft Windows GDI+-API behandelt. Diese API hat Baseline-Bildverarbeitungsfunktionen bereitgestellt, hatte aber keine Features wie die Unterstützung von Codec-Erweiterbarkeit und hochwertigen Bildern. Die WPF-Bildverarbeitungs-APIs wurden neu entworfen, um die Nachteile von GDI und GDI+ zu beheben und einen neuen Satz von APIs bereitzustellen, um Bilder in den Anwendungen anzeigen und verwenden können.  
  
 Beim Verwenden von Bildern sollten Sie die folgenden Empfehlungen in Betracht ziehen, um eine bessere Leistung zu erzielen:  
  
- Wenn Ihre Anwendung die Anzeige von Miniaturbildern erfordert, ist das Erstellen einer Bildversion in reduzierter Größe ratsam. Standardmäßig lädt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Bild und decodiert es in seine vollständige Größe. Wenn Sie nur eine Miniaturansicht des Bilds möchten, decodiert [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Bild überflüssigerweise in seine vollständige Größe und skaliert es dann auf die Größe der Miniaturansicht. Um diesen unnötigen Aufwand zu vermeiden, können Sie entweder bei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine Decodierung des Bilds in Miniaturansichtgröße oder [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zum Laden eines Bilds in Miniaturansichtgröße auffordern.  
  
- Decodieren Sie das Bild immer in die gewünschte Größe und nicht in die Standardgröße. Wie bereits erwähnt, fordern Sie bei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine Decodierung des Bilds in die gewünschte Größe und nicht in die vollständige Größe an. Auf diese Weise reduzieren Sie nicht nur das Workingset der Anwendung, Sie erhöhen auch die Ausführungsgeschwindigkeit.  
  
- Kombinieren Sie die Bilder nach Möglichkeit in einem Einzelbild (z.B. ein Filmstreifen, der sich aus mehreren Bildern zusammensetzt).  
  
- Weitere Informationen finden Sie unter [Übersicht über die Bildverarbeitung](../graphics-multimedia/imaging-overview.md).  
  
### <a name="bitmapscalingmode"></a>BitmapScalingMode  
 Beim Animieren der Skalierung von Bitmaps kann der Standardalgorithmus für das Resampling von Bildern hoher Qualität zuweilen einen solchen Umfang an Systemressourcen beanspruchen, dass eine Verringerung der Einzelbildrate auftritt und Animationen ruckartig wiedergegeben werden. Durch Festlegen der <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> -Eigenschaft <xref:System.Windows.Media.RenderOptions> des-Objekts <xref:System.Windows.Media.BitmapScalingMode.LowQuality> auf können Sie eine reibungslosere Animation erstellen, wenn Sie eine Bitmap skalieren. <xref:System.Windows.Media.BitmapScalingMode.LowQuality>der Modus weist [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Rendering-Engine an, bei der Verarbeitung von Bildern von einem qualitätsoptimierten Algorithmus zu einem Geschwindigkeits optimierten Algorithmus zu wechseln.  
  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Media.BitmapScalingMode> für ein Bild Objekt festgelegt wird.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### <a name="cachinghint"></a>CachingHint  
 Standardmäßig [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] speichert den gerenderten Inhalt von <xref:System.Windows.Media.TileBrush> <xref:System.Windows.Media.DrawingBrush> -Objekten, z. b <xref:System.Windows.Media.VisualBrush>. und, nicht zwischen. In statischen Szenarios, in denen weder der Inhalt noch <xref:System.Windows.Media.TileBrush> die Verwendung von in der Szene geändert wird, ist dies sinnvoll, da es den Videospeicher bewahrt. Es ist nicht sinnvoll, wenn ein <xref:System.Windows.Media.TileBrush> mit statischem Inhalt auf nicht statische Weise verwendet wird, z. –. Wenn ein statisches <xref:System.Windows.Media.DrawingBrush> oder <xref:System.Windows.Media.VisualBrush> der Oberfläche eines rotierenden 3D-Objekts zugeordnet wird. Das Standardverhalten von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] besteht darin, den gesamten Inhalt <xref:System.Windows.Media.DrawingBrush> des oder <xref:System.Windows.Media.VisualBrush> für jeden Frame erneut zu renderieren, auch wenn sich der Inhalt ändert.  
  
 Durch Festlegen der <xref:System.Windows.Media.RenderOptions.CachingHint%2A> -Eigenschaft <xref:System.Windows.Media.RenderOptions> des-Objekts <xref:System.Windows.Media.CachingHint.Cache> auf können Sie die Leistung steigern, indem Sie zwischengespeicherte Versionen der gekachelten Pinsel Objekte verwenden.  
  
 Der <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> - <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> Eigenschafts Wert und der-Eigenschafts Wert sind <xref:System.Windows.Media.TileBrush> relative Größen Werte, die bestimmen, wann das Objekt aufgrund von Skalierungs Änderungen neu generiert werden soll. Wenn Sie z. b. <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> die-Eigenschaft auf 2,0 festlegen, muss <xref:System.Windows.Media.TileBrush> der Cache für nur neu generiert werden, wenn seine Größe die doppelte Größe des aktuellen Caches überschreitet.  
  
 Im folgenden Beispiel wird gezeigt, wie die Option Caching Hint für einen <xref:System.Windows.Media.DrawingBrush>verwendet wird.  
  
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
