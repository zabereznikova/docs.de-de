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
ms.openlocfilehash: 4e6b72dae863e89d70ec70c2cb99a5874581e9ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549100"
---
# <a name="optimizing-performance-2d-graphics-and-imaging"></a>Optimieren der Leistung: 2D-Grafiken und Bildverarbeitung
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt zahlreiche Funktionen für 2D-Grafiken und Bildverarbeitung zur Verfügung, die den Anforderungen Ihrer Anwendung entsprechend optimiert werden können. Dieses Thema enthält Informationen über die Leistungsoptimierung in diesen Bereichen.  
  
  
<a name="Drawing_and_Shapes"></a>   
## <a name="drawing-and-shapes"></a>Zeichnen und Formen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet sowohl <xref:System.Windows.Media.Drawing> und <xref:System.Windows.Shapes.Shape> -Objekten zur Darstellung der grafischen Zeichnungsinhalt. Allerdings <xref:System.Windows.Media.Drawing> Objekte sind einfacher Konstrukte als <xref:System.Windows.Shapes.Shape> Objekte und bieten eine bessere Leistungsmerkmale.  
  
 Ein <xref:System.Windows.Shapes.Shape> können Sie eine grafische Form auf dem Bildschirm gezeichnet werden soll. Da aus abgeleitet werden die <xref:System.Windows.FrameworkElement> Klasse <xref:System.Windows.Shapes.Shape> Objekte können in Bereichen und den meisten Steuerelementen verwendet werden.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet mehrere Ebenen für den Zugriff auf Grafiken und Renderingdienste. Auf der obersten Ebene <xref:System.Windows.Shapes.Shape> Objekte sind einfach zu verwenden und viele nützliche Features, z. B. Layout und Ereignisbehandlung bereitzustellen. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt eine Reihe von vorgefertigten Shape-Objekten zur Verfügung. Alle Formobjekte, die von erben die <xref:System.Windows.Shapes.Shape> Klasse. Form "verfügbar" Objekten zählen <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, und <xref:System.Windows.Shapes.Rectangle>.  
  
 <xref:System.Windows.Media.Drawing> Objekte, andererseits, leiten Sie nicht von der <xref:System.Windows.FrameworkElement> Klasse, und geben Sie eine einfache Implementierung für das Rendering von Formen, Bilder und Text.  
  
 Es gibt vier Arten von <xref:System.Windows.Media.Drawing> Objekte:  
  
-   <xref:System.Windows.Media.GeometryDrawing> Zeichnet eine Form.  
  
-   <xref:System.Windows.Media.ImageDrawing> Zeichnet ein Bild an.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing> Zeichnet Text.  
  
-   <xref:System.Windows.Media.DrawingGroup> Zeichnet andere Zeichnungen. Verwenden Sie eine Zeichnungsgruppe, um andere Zeichnungen in einer zusammengesetzten Zeichnung zu kombinieren.  
  
 Die <xref:System.Windows.Media.GeometryDrawing> Objekt wird verwendet, um den Geometrieinhalt gerendert. Die <xref:System.Windows.Media.Geometry> Klasse und der konkreten Klassen, z. B. ableiten <xref:System.Windows.Media.CombinedGeometry>, <xref:System.Windows.Media.EllipseGeometry>, und <xref:System.Windows.Media.PathGeometry>, bieten eine Möglichkeit für 2D Rendern der Grafiken sowie Treffertests und Clipping-Unterstützung bereit. Mit Geometry-Objekten können beispielsweise der Bereich eines Steuerelements oder der auf ein Bild anzuwendende Clip-Bereich definiert werden. Bei Geometry-Objekten kann es sich um einfache Bereiche wie Rechtecke und Kreise oder um aus einem oder mehreren geometrischen Objekten zusammengesetzte Regionen handeln. Komplexere geometrische Regionen können erstellt werden, durch Kombinieren von <xref:System.Windows.Media.PathSegment>-abgeleitete Objekte, z. B. <xref:System.Windows.Media.ArcSegment>, <xref:System.Windows.Media.BezierSegment>, und <xref:System.Windows.Media.QuadraticBezierSegment>.  
  
 Auf der Oberfläche der <xref:System.Windows.Media.Geometry> Klasse und die <xref:System.Windows.Shapes.Shape> -Klasse sind sehr ähnlich. Beide werden beim Rendern von Grafiken 2D verwendet, und beide verfügen über ähnliche konkrete Klassen, die daraus, z. B. ableiten <xref:System.Windows.Media.EllipseGeometry> und <xref:System.Windows.Shapes.Ellipse>. Es gibt jedoch wichtige Unterschiede zwischen diesen zwei Sätzen von Klassen. Für ein Modell das <xref:System.Windows.Media.Geometry> Klasse verfügt nicht über einige der Funktionen von der <xref:System.Windows.Shapes.Shape> Klasse, z. B. die Möglichkeit, sich selbst zu zeichnen. Zum Zeichnen eines Geometry-Objekts muss eine andere Klasse, beispielsweise DrawingContext, Drawing oder Path (dabei ist zu beachten, dass ein Path eine Shape ist), verwendet werden, um den Zeichnungsvorgang auszuführen. Renderingeigenschaften wie Füllung, Strich und Strichstärke befinden sich in der Klasse, die das Geometry-Objekt zeichnet, während ein Shape-Objekt diese Eigenschaften enthält. Eine Möglichkeit zur Annäherung an diesen Unterschied besteht darin, dass ein Geometry-Objekt einen Bereich definiert, z.B. einen Kreis, während ein Shape-Objekt definiert, wie dieser Bereich gefüllt und konturiert wird und eine Komponente des Layoutsystems ist.  
  
 Da <xref:System.Windows.Shapes.Shape> Objekte Ableiten der <xref:System.Windows.FrameworkElement> Klasse, deren Verwendung kann wesentlich mehr Arbeitsspeicher belegt in der Anwendung hinzufügen. Wenn Sie nicht wirklich benötigen die <xref:System.Windows.FrameworkElement> Funktionen für Ihre grafische Inhalte, erwägen Sie die helleren-Gewichtung <xref:System.Windows.Media.Drawing> Objekte.  
  
 Weitere Informationen zu <xref:System.Windows.Media.Drawing> anzuzeigen, [Drawing Objects Overview](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
<a name="StreamGeometry_Objects"></a>   
## <a name="streamgeometry-objects"></a>StreamGeometry-Objekte  
 Die <xref:System.Windows.Media.StreamGeometry> Objekt ist ein Lightweight-Alternative zu <xref:System.Windows.Media.PathGeometry> für das geometrische Formen erstellen. Verwenden einer <xref:System.Windows.Media.StreamGeometry> müssen Sie eine komplexe Geometrie beschreiben. <xref:System.Windows.Media.StreamGeometry> ist optimiert für die Behandlung viele <xref:System.Windows.Media.PathGeometry> Objekte und bietet eine bessere Leistung im Vergleich zur Verwendung von viele einzelne <xref:System.Windows.Media.PathGeometry> Objekte.  
  
 Im folgenden Beispiel wird die Attributsyntax eine dreieckige erstellen <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Weitere Informationen zu <xref:System.Windows.Media.StreamGeometry> anzuzeigen, [Exemplarische Vorgehensweise: Erstellen von einer Form mit einer StreamGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
<a name="DrawingVisual_Objects"></a>   
## <a name="drawingvisual-objects"></a>DrawingVisual-Objekte  
 Die <xref:System.Windows.Media.DrawingVisual> Objekt ist ein Lightweight-Zeichnung-Klasse, die zum Rendern von Formen, Bildern oder Text verwendet wird. Diese Klasse wird als einfach angesehen, weil sie weder Layout noch Ereignisbehandlung bereitstellt. Dadurch wird die Leistung gesteigert. Aus diesem Grund sind Zeichnungen für Hintergründe und ClipArt ideal. Weitere Informationen finden Sie unter [Verwenden von DrawingVisual-Objekten](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="Images"></a>   
## <a name="images"></a>Bilder  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Bildverarbeitung stellt gegenüber den Bildverarbeitungsfähigkeiten in vorherigen Versionen von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] eine deutliche Verbesserung dar. Die Bildverarbeitungsfähigkeiten wie das Anzeigen einer Bitmap oder das Verwenden eines Bilds für ein allgemeines Steuerelement wurden hauptsächlich von Microsoft Windows Graphics Device Interface (GDI) oder der Microsoft Windows GDI+-API behandelt. Diese API hat Baseline-Bildverarbeitungsfunktionen bereitgestellt, hatte aber keine Features wie die Unterstützung von Codec-Erweiterbarkeit und hochwertigen Bildern. Die WPF-Bildverarbeitungs-APIs wurden neu entworfen, um die Nachteile von GDI und GDI+ zu beheben und einen neuen Satz von APIs bereitzustellen, um Bilder in den Anwendungen anzeigen und verwenden können.  
  
 Beim Verwenden von Bildern sollten Sie die folgenden Empfehlungen in Betracht ziehen, um eine bessere Leistung zu erzielen:  
  
-   Wenn Ihre Anwendung die Anzeige von Miniaturbildern erfordert, ist das Erstellen einer Bildversion in reduzierter Größe ratsam. Standardmäßig lädt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Bild und decodiert es in seine vollständige Größe. Wenn Sie nur eine Miniaturansicht des Bilds möchten, decodiert [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Bild überflüssigerweise in seine vollständige Größe und skaliert es dann auf die Größe der Miniaturansicht. Um diesen unnötigen Aufwand zu vermeiden, können Sie entweder bei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine Decodierung des Bilds in Miniaturansichtgröße oder [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zum Laden eines Bilds in Miniaturansichtgröße auffordern.  
  
-   Decodieren Sie das Bild immer in die gewünschte Größe und nicht in die Standardgröße. Wie bereits erwähnt, fordern Sie bei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine Decodierung des Bilds in die gewünschte Größe und nicht in die vollständige Größe an. Auf diese Weise reduzieren Sie nicht nur das Workingset der Anwendung, Sie erhöhen auch die Ausführungsgeschwindigkeit.  
  
-   Kombinieren Sie die Bilder nach Möglichkeit in einem Einzelbild (z.B. ein Filmstreifen, der sich aus mehreren Bildern zusammensetzt).  
  
-   Weitere Informationen finden Sie unter [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
### <a name="bitmapscalingmode"></a>BitmapScalingMode  
 Beim Animieren der Skalierung von Bitmaps kann der Standardalgorithmus für das Resampling von Bildern hoher Qualität zuweilen einen solchen Umfang an Systemressourcen beanspruchen, dass eine Verringerung der Einzelbildrate auftritt und Animationen ruckartig wiedergegeben werden. Durch Festlegen der <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> Eigenschaft von der <xref:System.Windows.Media.RenderOptions> -Objekt <xref:System.Windows.Media.BitmapScalingMode.LowQuality> Animationen erstellen, wenn eine Bitmap zu skalieren. <xref:System.Windows.Media.BitmapScalingMode.LowQuality> Modus weist die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Renderingmodul beim Verarbeiten von Bildern von einem Algorithmus Qualität optimiert für einen Algorithmus Geschwindigkeit optimiert wechseln.  
  
 Im folgende Beispiel wird gezeigt, wie zum Festlegen der <xref:System.Windows.Media.BitmapScalingMode> für ein Image-Objekt.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### <a name="cachinghint"></a>CachingHint  
 Standardmäßig [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zwischenspeichert, den gerenderten Inhalt <xref:System.Windows.Media.TileBrush> Objekte, z. B. <xref:System.Windows.Media.DrawingBrush> und <xref:System.Windows.Media.VisualBrush>. In statischen Szenarien, in denen weder der Inhalt noch die Verwendung der <xref:System.Windows.Media.TileBrush> in der Szene ändern, ist dies sinnvoll, da Videospeicher gespart wird. Es nimmt als sinnvoll, wenn eine <xref:System.Windows.Media.TileBrush> mit statischem Inhalt in eine nicht statische Methode verwendet wird – beispielsweise, wenn eine statische <xref:System.Windows.Media.DrawingBrush> oder <xref:System.Windows.Media.VisualBrush> auf die Oberfläche eines Objekts für das Drehen von 3D zugeordnet ist. Das Standardverhalten des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] den gesamten Inhalt des erneut gerendert werden soll die <xref:System.Windows.Media.DrawingBrush> oder <xref:System.Windows.Media.VisualBrush> für jeden Frame, selbst wenn der Inhalt ist unveränderliche.  
  
 Durch Festlegen der <xref:System.Windows.Media.RenderOptions.CachingHint%2A> Eigenschaft von der <xref:System.Windows.Media.RenderOptions> -Objekt <xref:System.Windows.Media.CachingHint.Cache> können Sie die Leistung erhöhen, mithilfe von zwischengespeicherten Versionen der Kacheleffekt Objekte.  
  
 Die <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> und <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> Eigenschaftswerte sind Werte für die relative Größe, die bestimmen, wann die <xref:System.Windows.Media.TileBrush> Objekt aufgrund von Änderungen in Skalierung neu generiert werden sollte. Z. B. durch Festlegen der <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> Eigenschaft 2.0, den Cache für die <xref:System.Windows.Media.TileBrush> muss nur erneut generiert werden, wenn seine Größe zweimal der Größe des aktuellen Caches überschreitet.  
  
 Das folgende Beispiel zeigt, wie Sie die Option zum Zwischenspeichern Hinweis für ein <xref:System.Windows.Media.DrawingBrush>.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet3)]
 [!code-vb[RenderOptions#RenderOptionsSnippet3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet3)]  
  
## <a name="see-also"></a>Siehe auch  
 [Optimieren der WPF-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Planen der Anwendungsleistung](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [Vorteile der Hardware nutzen](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [Objektverhalten](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Anwendungsressourcen](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Weitere Leistungsempfehlungen](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)  
 [Tipps und Tricks zu Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)
