---
title: "Optimieren der Leistung: 2D-Grafiken und Bildverarbeitung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "2D-Grafiken"
  - "Zeichnen, Optimieren der Leistung"
  - "Grafiken, Leistung"
  - "Bilder, Optimieren der Leistung"
  - "Imaging, Optimieren der Leistung"
  - "Formen, Optimieren der Leistung"
ms.assetid: e335601e-28c8-4d64-ba27-778fffd55f72
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Optimieren der Leistung: 2D-Grafiken und Bildverarbeitung
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt zahlreiche Funktionen für 2D\-Grafiken und Bildverarbeitung zur Verfügung, die den Anforderungen Ihrer Anwendung entsprechend optimiert werden können.  Dieses Thema enthält Informationen über die Leistungsoptimierung in diesen Bereichen.  
  
   
  
<a name="Drawing_and_Shapes"></a>   
## Zeichnen und Formen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt sowohl <xref:System.Windows.Media.Drawing>\-Objekte als auch <xref:System.Windows.Shapes.Shape>\-Objekte bereit, um grafischen Zeichnungsinhalt darzustellen.  <xref:System.Windows.Media.Drawing>\-Objekte sind jedoch einfachere Konstrukte als <xref:System.Windows.Shapes.Shape>\-Objekte und stellen bessere Leistungsmerkmale bereit.  
  
 Mit <xref:System.Windows.Shapes.Shape> können Sie eine grafische Form auf dem Bildschirm zeichnen.  Da sie von der <xref:System.Windows.FrameworkElement>\-Klasse abgleitet werden, können <xref:System.Windows.Shapes.Shape>\-Objekte in Bereichen und den meisten Steuerelementen verwendet werden.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet mehrere Ebenen für den Zugriff auf Grafiken und Renderingdienste.  Auf der obersten Ebene stehen die benutzerfreundlichen <xref:System.Windows.Shapes.Shape>\-Objekte mit einer Vielzahl von nützlichen Funktionen zur Verfügung, z. B. Layout und Ereignisbehandlung.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt eine Reihe von vorgefertigten Shape\-Objekten zur Verfügung.  Alle Shape\-Objekte erben von der <xref:System.Windows.Shapes.Shape>\-Klasse.  Zu den verfügbaren Shape\-Objekten gehören <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline> und <xref:System.Windows.Shapes.Rectangle>.  
  
 <xref:System.Windows.Media.Drawing>\-Objekte werden dagegen nicht von der <xref:System.Windows.FrameworkElement>\-Klasse abgeleitet und bieten eine einfache Implementierung für das Rendering von Formen, Bildern und Text.  
  
 Es gibt vier Typen von <xref:System.Windows.Media.Drawing>\-Objekten:  
  
-   <xref:System.Windows.Media.GeometryDrawing> \- Zeichnet eine Form.  
  
-   <xref:System.Windows.Media.ImageDrawing> \- Zeichnet ein Bild.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing> \- Zeichnet Text.  
  
-   <xref:System.Windows.Media.DrawingGroup> \- Zeichnet andere Zeichnungen.  Verwenden Sie eine Zeichnungsgruppe, um aus anderen Zeichnungen eine einzelne zusammengesetzte Zeichnung zu bilden.  
  
 Das <xref:System.Windows.Media.GeometryDrawing>\-Objekt wird verwendet, um Geometrieinhalt zu rendern.  Die <xref:System.Windows.Media.Geometry>\-Klasse und die von ihr abgeleiteten konkreten Klassen, wie <xref:System.Windows.Media.CombinedGeometry>, <xref:System.Windows.Media.EllipseGeometry> und <xref:System.Windows.Media.PathGeometry>, bieten eine Möglichkeit für das Rendering von 2D\-Grafiken und stellen außerdem Unterstützung für Trefferüberprüfungen und Clipping bereit.  Mit Geometry\-Objekten können beispielsweise der Bereich eines Steuerelements oder der auf ein Bild anzuwendende Clip\-Bereich definiert werden.  Bei Geometry\-Objekten kann es sich um einfache Bereiche wie Rechtecke und Kreise oder um aus einem oder mehreren geometrischen Objekten zusammengesetzte Regionen handeln.  Komplexere geometrische Regionen können erstellt werden, indem von <xref:System.Windows.Media.PathSegment> abgeleitete Objekte wie <xref:System.Windows.Media.ArcSegment>, <xref:System.Windows.Media.BezierSegment> und <xref:System.Windows.Media.QuadraticBezierSegment> kombiniert werden.  
  
 Auf den ersten Blick sind die <xref:System.Windows.Media.Geometry>\-Klasse und die <xref:System.Windows.Shapes.Shape>\-Klasse recht ähnlich.  Beide werden für das Rendering von 2D\-Grafiken verwendet und verfügen über ähnliche konkrete Klassen, die von ihnen abgeleitet werden, z. B. <xref:System.Windows.Media.EllipseGeometry> und <xref:System.Windows.Shapes.Ellipse>.  Es gibt jedoch wichtige Unterschiede zwischen diesen zwei Sätzen von Klassen.  Bei der <xref:System.Windows.Media.Geometry>\-Klasse werden einige Funktionen der <xref:System.Windows.Shapes.Shape>\-Klasse nicht unterstützt, wie die Fähigkeit, sich selbst zu zeichnen.  Zum Zeichnen eines Geometry\-Objekts muss eine andere Klasse, beispielsweise DrawingContext, Drawing oder Path \(dabei ist zu beachten, dass ein Path eine Shape ist\), verwendet werden, um den Zeichnungsvorgang auszuführen.  Renderingeigenschaften wie Füllung, Strich und Strichstärke befinden sich in der Klasse, die das Geometry\-Objekt zeichnet, während ein Shape\-Objekt diese Eigenschaften enthält.  Eine Möglichkeit zur Annäherung an diesen Unterschied besteht darin, dass ein Geometry\-Objekt einen Bereich definiert, z. B. einen Kreis, während ein Shape\-Objekt definiert, wie dieser Bereich gefüllt und konturiert wird und eine Komponente des Layoutsystems ist.  
  
 Da <xref:System.Windows.Shapes.Shape>\-Objekte von der <xref:System.Windows.FrameworkElement>\-Klasse abgeleitet werden, kann durch ihre Verwendung deutlich mehr Speicher in der Anwendung belegt werden.  Wenn Sie für den grafischen Inhalt auf die <xref:System.Windows.FrameworkElement>\-Features verzichten können, sollten Sie die Verwendung der einfachen <xref:System.Windows.Media.Drawing>\-Objekte in Betracht ziehen.  
  
 Weitere Informationen über <xref:System.Windows.Media.Drawing>\-Objekte finden Sie unter [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
<a name="StreamGeometry_Objects"></a>   
## StreamGeometry\-Objekte  
 Das <xref:System.Windows.Media.StreamGeometry>\-Objekt stellt eine einfache Alternative zu <xref:System.Windows.Media.PathGeometry> für das Erstellen geometrischer Formen dar.  Verwenden Sie eine <xref:System.Windows.Media.StreamGeometry>, wenn Sie eine komplexe Geometrie beschreiben müssen.  <xref:System.Windows.Media.StreamGeometry> ist für die Behandlung vieler <xref:System.Windows.Media.PathGeometry>\-Objekte optimiert und zeigt eine bessere Leistung als die Verwendung mehrerer einzelner <xref:System.Windows.Media.PathGeometry>\-Objekte.  
  
 Im folgenden Beispiel wird mithilfe der Attributsyntax eine dreieckige <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erstellt.  
  
 [!code-xml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Weitere Informationen über <xref:System.Windows.Media.StreamGeometry>\-Objekte finden Sie unter [Erstellen eines Shapes mit einer StreamGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
<a name="DrawingVisual_Objects"></a>   
## DrawingVisual\-Objekte  
 Das <xref:System.Windows.Media.DrawingVisual>\-Objekt ist eine einfache Zeichnungsklasse, die zum Rendern von Formen, Bildern oder Text verwendet wird.  Diese Klasse wird als einfach angesehen, weil sie weder Layout noch Ereignisbehandlung bereitstellt. Dadurch wird die Leistung gesteigert.  Aus diesem Grund sind Zeichnungen ideal für Hintergründe und ClipArt.  Weitere Informationen finden Sie unter [Verwenden von DrawingVisual\-Objekten](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="Images"></a>   
## Bilder  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Bildverarbeitung stellt gegenüber den Bildverarbeitungsfähigkeiten in vorherigen Versionen von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] eine deutliche Verbesserung dar.  Die Bildverarbeitungsfähigkeiten wie das Anzeigen einer Bitmap oder das Verwenden eines Bilds für ein allgemeines Steuerelement wurden hauptsächlich von Microsoft Windows Graphics Device Interface \(GDI\) oder der Microsoft Windows GDI\+\-API behandelt.  Diese API hat Baseline\-Bildverarbeitungsfunktionen bereitgestellt, verfügte jedoch nicht über Features wie die Unterstützung von Codec\-Erweiterbarkeit und hochwertigen Bildern.  Die WPF\-Bildverarbeitungs\-APIs wurden neu entworfen, um die Nachteile von GDI und GDI\+ zu beheben und einen neuen Satz von APIs bereitzustellen, um Bilder in den Anwendungen anzuzeigen und zu verwenden.  
  
 Beim Verwenden von Bildern sollten Sie die folgenden Empfehlungen in Betracht ziehen, um eine bessere Leistung zu erzielen:  
  
-   Wenn die Anwendung die Anzeige von Miniaturbildern erfordert, erstellen Sie eine Bildversion in reduzierter Größe.  Standardmäßig lädt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Bild und decodiert es in seine vollständige Größe.  Wenn Sie nur eine Miniaturansicht des Bilds möchten, decodiert [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Bild überflüssigerweise in seine vollständige Größe und skaliert es dann auf die Größe der Miniaturansicht.  Um diesen unnötigen Aufwand zu vermeiden, können Sie entweder bei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine Decodierung des Bilds in Miniaturansichtgröße oder das Laden eines Bilds in Miniaturansichtgröße anfordern.  
  
-   Decodieren Sie das Bild immer in die gewünschte Größe und nicht in die Standardgröße.  Wie bereits erwähnt, fordern Sie bei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine Decodierung des Bilds in die gewünschte Größe und nicht in die vollständige Größe an.  Auf diese Weise reduzieren Sie nicht nur das Workingset der Anwendung, Sie erhöhen auch die Ausführungsgeschwindigkeit.  
  
-   Kombinieren Sie die Bilder nach Möglichkeit in einem Einzelbild, wie ein Filmstreifen, der sich aus mehreren Bildern zusammensetzt.  
  
-   Weitere Informationen finden Sie unter [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
### BitmapScalingMode  
 Beim Animieren der Skalierung von Bitmaps kann der Standardalgorithmus für das Resampling von Bildern hoher Qualität zuweilen einen solchen Umfang an Systemressourcen beanspruchen, dass eine Verringerung der Einzelbildrate auftritt und Animationen ruckartig wiedergegeben werden.  Durch Festlegen der <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A>\-Eigenschaft des <xref:System.Windows.Media.RenderOptions>\-Objekts auf <xref:System.Windows.Media.BitmapScalingMode> werden Animationen gleichmäßiger wiedergegeben, wenn eine Bitmap skaliert wird.  Der <xref:System.Windows.Media.BitmapScalingMode>\-Modus weist das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Renderingmodul an, beim Verarbeiten von Bildern von einem qualitätsoptimierten Algorithmus auf einen geschwindigkeitsoptimierten Algorithmus umzuschalten.  
  
 Im folgenden Beispiel wird gezeigt, wie der <xref:System.Windows.Media.BitmapScalingMode> für ein Bildobjekt festgelegt wird.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### CachingHint  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird der gerenderte Inhalt von <xref:System.Windows.Media.TileBrush>\-Objekten, z. B. <xref:System.Windows.Media.DrawingBrush> und <xref:System.Windows.Media.VisualBrush>, standardmäßig nicht zwischengespeichert.  In statischen Szenarios, in denen sich weder der Inhalt noch die Verwendung des <xref:System.Windows.Media.TileBrush> in der Szene ändern, ist dies sinnvoll, da Videospeicher gespart wird.  Das Verfahren ist hingegen nicht sinnvoll, wenn ein <xref:System.Windows.Media.TileBrush> mit statischem Inhalt auf nicht statische Weise verwendet wird, z. B. wenn ein statischer <xref:System.Windows.Media.DrawingBrush> oder <xref:System.Windows.Media.VisualBrush> der Oberfläche eines sich drehenden 3D\-Objekts zugeordnet wird.  Das Standardverhalten von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] besteht im erneuten Rendern des gesamten <xref:System.Windows.Media.DrawingBrush>\-Inhalts oder <xref:System.Windows.Media.VisualBrush>\-Inhalts für jeden Frame, selbst wenn der Inhalt unverändert bleibt.  
  
 Sie können die Leistung erhöhen, indem Sie die <xref:System.Windows.Media.RenderOptions.CachingHint%2A>\-Eigenschaft des <xref:System.Windows.Media.RenderOptions>\-Objekts auf <xref:System.Windows.Media.CachingHint> festlegen und die zwischengespeicherten Versionen der gekachelten Pinselobjekte verwenden.  
  
 Der <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A>\-Eigenschaftswert und der <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A>\-Eigenschaftswert sind Werte von relativer Größe, die bestimmen, wann das <xref:System.Windows.Media.TileBrush>\-Objekt aufgrund einer geänderten Skalierung neu generiert werden sollte.  Wenn beispielsweise die <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A>\-Eigenschaft auf 2,0 festgelegt ist, muss der Cache für den <xref:System.Windows.Media.TileBrush> nur neu generiert werden, wenn seine Größe die Größe des aktuellen Caches um mehr als das Doppelte überschreitet.  
  
 Im folgenden Beispiel wird gezeigt, wie die Zwischenspeicherungshinweisoption für einen <xref:System.Windows.Media.DrawingBrush> verwendet wird.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet3)]
 [!code-vb[RenderOptions#RenderOptionsSnippet3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet3)]  
  
## Siehe auch  
 [Optimieren der WPF\-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Planen der Anwendungsleistung](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Nutzen der Vorteile der Hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [Projektverhalten](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Anwendungsressourcen](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Weitere Leistungsempfehlungen](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)   
 [Tipps und Tricks zu Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)