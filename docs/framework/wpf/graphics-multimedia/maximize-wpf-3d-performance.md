---
title: "Maximieren der 3D-Leistung von WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "3D-Grafiken [WPF]"
ms.assetid: 4bcf949d-d92f-4d8d-8a9b-1e4c61b25bf6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Maximieren der 3D-Leistung von WPF
Bei der Erstellung von 3D\-Steuerelementen und der Einbindung von 3D\-Szenen in Anwendungen mithilfe von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] muss auch die Leistungsoptimierung berücksichtigt werden. In diesem Thema werden die 3D\-Klassen und 3D\-Eigenschaften aufgelistet, die die Leistung von Anwendungen beeinflussen. Darüber hinaus werden Empfehlungen zur Leistungsoptimierung bei der Verwendung der jeweiligen Klassen und Eigenschaften gegeben.  
  
 In diesem Thema werden fortgeschrittene Kenntnisse der 3D\-Features von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] vorausgesetzt.  Die Vorschläge in diesem Dokument gelten für die "Renderingebene 2", d. h. allgemein für Hardware, die Pixel\-Shader der Version 2.0 und Vertex\-Shader der Version 2.0 unterstützt.  Weitere Informationen finden Sie unter [Renderingebenen für Grafiken](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
## Auswirkung auf die Leistung: Hoch  
  
|||  
|-|-|  
|Property|Empfehlung|  
|<xref:System.Windows.Media.Brush>|Pinselgeschwindigkeit \(absteigend\):<br /><br /> <xref:System.Windows.Media.SolidColorBrush><br /><br /> <xref:System.Windows.Media.LinearGradientBrush><br /><br /> <xref:System.Windows.Media.ImageBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush> \(zwischengespeichert\)<br /><br /> <xref:System.Windows.Media.VisualBrush> \(zwischengespeichert\)<br /><br /> <xref:System.Windows.Media.RadialGradientBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush> \(nicht zwischengespeichert\)<br /><br /> <xref:System.Windows.Media.VisualBrush> \(nicht zwischengespeichert\)|  
|<xref:System.Windows.UIElement.ClipToBoundsProperty>|Legen Sie `Viewport3D.ClipToBounds` immer auf false fest, wenn [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] den Inhalt eines <xref:System.Windows.Controls.Viewport3D>\-Elements nicht unbedingt auf das Viewport3D\-Rechteck zuschneiden muss. Das [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Clipping mit Antialiasing kann sehr langsam sein, und `ClipToBounds` wird standardmäßig für <xref:System.Windows.Controls.Viewport3D> aktiviert \(langsam\).|  
|<xref:System.Windows.UIElement.IsHitTestVisible%2A>|Legen Sie `Viewport3D.IsHitTestVisible` immer auf "false" fest, wenn [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] den Inhalt eines <xref:System.Windows.Controls.Viewport3D> bei Maustreffertests nicht unbedingt berücksichtigen muss. Treffertests für 3D\-Inhalte werden in der Software ausgeführt und können bei großen Netzen sehr langsam sein. <xref:System.Windows.UIElement.IsHitTestVisible%2A> wird standardmäßig für <xref:System.Windows.Controls.Viewport3D> aktiviert \(langsam\).|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D>|Erstellen Sie andere Modelle nur, wenn sie andere Materialien oder Transformationen benötigen.  Andernfalls versuchen Sie, viele <xref:System.Windows.Media.Media3D.GeometryModel3D>\-Instanzen mit denselben Materialien und Transformationen zu einigen größeren <xref:System.Windows.Media.Media3D.GeometryModel3D>\-Instanzen und <xref:System.Windows.Media.Media3D.MeshGeometry3D>\-Instanzen zusammenzufügen.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Die Animation des Netzes, d. h. die Änderung der einzelnen Eckpunkte eines Netzes auf Framebasis, ist in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] nicht immer effizient. Um die Auswirkungen von Änderungsbenachrichtigungen auf die Leistung nach jeder Änderung eines Eckpunkts zu minimieren, trennen Sie das Netz von der visuellen Struktur, bevor Sie die Eckpunkte einzeln ändern. Nach der Änderung fügen Sie das Netz wieder der visuellen Struktur hinzu. Versuchen Sie außerdem, die Größe der Netze zu minimieren, die auf diese Art animiert werden.|  
|3D\-Antialiasing|Um das Rendering zu beschleunigen, deaktivieren Sie das Multisampling für ein <xref:System.Windows.Controls.Viewport3D>, indem Sie die angefügten <xref:System.Windows.Media.RenderOptions.EdgeMode%2A>\-Eigenschaft auf `Aliased` festlegen.  3D\-Antialiasing ist unter [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] standardmäßig deaktiviert und unter [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)] mit vier Abtastungen pro Pixel aktiviert.|  
|Text|Livetext in einer 3D\-Szene \(live, weil er sich in <xref:System.Windows.Media.DrawingBrush> oder <xref:System.Windows.Media.VisualBrush> befindet\) kann langsam sein.  Versuchen Sie stattdessen, Bilder des Texts \(über <xref:System.Windows.Media.Imaging.RenderTargetBitmap>\) zu verwenden, außer wenn sich der Text ändert.|  
|<xref:System.Windows.Media.TileBrush>|Wenn Sie <xref:System.Windows.Media.VisualBrush> oder <xref:System.Windows.Media.DrawingBrush> in einer 3D\-Szene verwenden müssen, weil der Inhalt des Pinsels nicht statisch ist, versuchen Sie, den Pinsel zwischenzuspeichern \(durch Festlegen der angefügten <xref:System.Windows.Media.RenderOptions.CachingHint%2A>\-Eigenschaft auf `Cache`\).  Legen Sie den unteren und oberen Schwellenwert für die Ungültigkeit \(mit den angefügten Eigenschaften <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> und <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A>\) so fest, dass die zwischengespeicherten Pinsel nur so oft neu generiert werden, dass das gewünschte Qualitätsniveau erhalten bleibt.  <xref:System.Windows.Media.DrawingBrush> und <xref:System.Windows.Media.VisualBrush> werden standardmäßig nicht zwischengespeichert. Dies bedeutet: Immer wenn Elemente, die mit dem Pinsel gezeichnet wurden, neu gerendert werden sollen, muss zuerst der gesamte Inhalt des Pinsels in einer Zwischenoberfläche neu gerendert werden.|  
|<xref:System.Windows.Media.Effects.BitmapEffect>|<xref:System.Windows.Media.Effects.BitmapEffect> erzwingt, dass alle betroffenen Inhalte ohne Hardwarebeschleunigung gerendert werden.  Um eine optimale Leistung zu erzielen, verwenden Sie nicht <xref:System.Windows.Media.Effects.BitmapEffect>.|  
  
## Auswirkung auf die Leistung: Mittel  
  
|||  
|-|-|  
|Property|Empfehlung|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Wenn ein Netz als aneinander grenzende Dreiecke mit gemeinsamen Eckpunkten definiert ist und diese Eckpunkte dieselbe Position, dieselbe Normale und dieselben Texturkoordinaten haben, definieren Sie jeden gemeinsamen Eckpunkt nur einmal und anschließend die Dreiecke mit <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> nach Index.|  
|<xref:System.Windows.Media.ImageBrush>|Versuchen Sie, die Texturgrößen zu minimieren, wenn Sie die explizite Kontrolle über die Größe haben \(d. h., wenn Sie <xref:System.Windows.Media.Imaging.RenderTargetBitmap> und\/oder <xref:System.Windows.Media.ImageBrush> verwenden\).  Texturen mit geringerer Auflösung können die visuelle Qualität verringern. Versuchen Sie daher, die richtige Balance zwischen Qualität und Leistung zu finden.|  
|Durchlässigkeit|Beim Rendering lichtdurchlässiger 3D\-Inhalte \(wie Reflektionen\) verwenden Sie die Durchlässigkeitseigenschaften für Pinsel oder Materialien \(über <xref:System.Windows.Media.Brush.Opacity%2A> oder <xref:System.Windows.Media.Media3D.DiffuseMaterial.Color%2A>\), anstatt ein separates lichtdurchlässiges <xref:System.Windows.Controls.Viewport3D> zu erstellen. Legen Sie `Viewport3D.Opacity` dazu auf einen Wert kleiner als 1 fest.|  
|<xref:System.Windows.Controls.Viewport3D>|Minimieren Sie die Anzahl der <xref:System.Windows.Controls.Viewport3D>\-Objekte, die Sie in einer Szene verwenden.  Platzieren Sie viele 3D\-Modelle in demselben Viewport3D, anstatt separate Viewport3D\-Instanzen für jedes Modell zu erstellen.|  
|<xref:System.Windows.Freezable>|In der Regel ist es von Vorteil, <xref:System.Windows.Media.Media3D.MeshGeometry3D>, <xref:System.Windows.Media.Media3D.GeometryModel3D>, Pinsel und Materialien mehrfach zu verwenden.  Alle können mehrere übergeordnete Objekte haben, da sie von `Freezable` abgeleitet werden.|  
|<xref:System.Windows.Freezable>|Rufen Sie die <xref:System.Windows.Freezable.Freeze%2A>\-Methode für Freezable\-Objekte auf, wenn ihre Eigenschaften in der Anwendung unverändert bleiben.  Das Fixieren kann das Workingset verkleinern und die Geschwindigkeit erhöhen.|  
|<xref:System.Windows.Media.Brush>|Verwenden Sie <xref:System.Windows.Media.ImageBrush> statt <xref:System.Windows.Media.VisualBrush> oder <xref:System.Windows.Media.DrawingBrush>, wenn sich der Inhalt des Pinsels nicht ändert.  2D\-Inhalt kann über <xref:System.Windows.Media.Imaging.RenderTargetBitmap> in <xref:System.Windows.Controls.Image> konvertiert und dann in <xref:System.Windows.Media.ImageBrush> verwendet werden.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>|Verwenden Sie <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> nur, wenn Sie die Backfaces von <xref:System.Windows.Media.Media3D.GeometryModel3D> wirklich sehen müssen.|  
|<xref:System.Windows.Media.Media3D.Light>|Lichtgeschwindigkeit \(absteigend\):<br /><br /> <xref:System.Windows.Media.Media3D.AmbientLight><br /><br /> <xref:System.Windows.Media.Media3D.DirectionalLight><br /><br /> <xref:System.Windows.Media.Media3D.PointLight><br /><br /> <xref:System.Windows.Media.Media3D.SpotLight>|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Versuchen Sie, unterhalb der folgenden Netzgrößen zu bleiben:<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>: 20.001 <xref:System.Windows.Media.Media3D.Point3D>\-Instanzen<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>: 60.003 <xref:System.Int32>\-Instanzen|  
|<xref:System.Windows.Media.Media3D.Material>|Materialgeschwindigkeit \(absteigend\):<br /><br /> <xref:System.Windows.Media.Media3D.EmissiveMaterial><br /><br /> <xref:System.Windows.Media.Media3D.DiffuseMaterial><br /><br /> <xref:System.Windows.Media.Media3D.SpecularMaterial>|  
|<xref:System.Windows.Media.Brush>|[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] verzichtet nicht immer auf nicht sichtbare Pinsel \(schwarze Umgebungspinsel, klare Pinsel usw.\). Überlegen Sie, ob Sie sie ggf. aus der Szene entfernen können.|  
|<xref:System.Windows.Media.Media3D.MaterialGroup>|Jedes <xref:System.Windows.Media.Media3D.Material>\-Element in <xref:System.Windows.Media.Media3D.MaterialGroup> führt zu einem weiteren Renderingdurchlauf, sodass die Aufnahme vieler Materialen, auch einfacher Materialien, die Füllanforderungen der GPU drastisch erhöhen kann.  Minimieren Sie also die Anzahl von Materialien in <xref:System.Windows.Media.Media3D.MaterialGroup>.|  
  
## Auswirkung auf die Leistung: Niedrig  
  
|||  
|-|-|  
|Property|Empfehlung|  
|<xref:System.Windows.Media.Media3D.Transform3DGroup>|Wenn keine Animation oder Datenbindung erforderlich ist, verwenden Sie anstelle einer Transformationsgruppe mit mehreren Transformationen ein einzelnes <xref:System.Windows.Media.Media3D.MatrixTransform3D>, und legen Sie es als Produkt aller Transformationen fest, die ansonsten unabhängig voneinander in der Transformationsgruppe existieren würden.|  
|<xref:System.Windows.Media.Media3D.Light>|Minimieren Sie die Anzahl von Lichtern in der Szene.  Zu viele Lichter in einer Szene zwingen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], auf das Softwarerendering zurückzugreifen. Die Obergrenzen liegen ungefähr bei 110 <xref:System.Windows.Media.Media3D.DirectionalLight>\-Objekten, 70 <xref:System.Windows.Media.Media3D.PointLight>\-Objekten oder 40 <xref:System.Windows.Media.Media3D.SpotLight>\-Objekten.|  
|<xref:System.Windows.Media.Media3D.ModelVisual3D>|Trennen Sie bewegliche Objekte von statischen Objekten, indem Sie sie in separaten <xref:System.Windows.Media.Media3D.ModelVisual3D>\-Instanzen platzieren.  ModelVisual3D ist "schwerer" als <xref:System.Windows.Media.Media3D.GeometryModel3D>, da es transformierte Begrenzungen zwischenspeichert.  GeometryModel3D wurde als Modell und ModelVisual3D als Szenenknoten optimiert.  Verwenden Sie ModelVisual3D, um freigegebene Instanzen von GeometryModel3D in der Szene zu platzieren.|  
|<xref:System.Windows.Media.Media3D.Light>|Ändern Sie die Anzahl der Lichter in der Szene möglichst selten.  Nach jeder Änderung der Lichteranzahl muss der Shader neu generiert und kompiliert werden, es sei denn, die jeweilige Konfiguration lag schon einmal vor \(und der zugehörige Shader ist noch zwischengespeichert\).|  
|Licht|Schwarze Lichter sind zwar nicht sichtbar, verlängern aber das Rendering. Überlegen Sie daher, ob Sie darauf verzichten können.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Um die Erstellung großer Auflistungen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] wie <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> und <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> für MeshGeometry3D zu beschleunigen, legen Sie die Größe der Auflistungen fest, bevor diese mit Werten aufgefüllt werden.  Übergeben Sie nach Möglichkeit vorab gefüllte Datenstrukturen wie Arrays oder Listen an die Konstruktoren der Auflistungen.|  
  
## Siehe auch  
 [Übersicht über 3D\-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)