---
title: Maximieren der 3D-Leistung von WPF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 3-D graphics [WPF]
ms.assetid: 4bcf949d-d92f-4d8d-8a9b-1e4c61b25bf6
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 45053762a4782544531a09c92531b26f99663016
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="maximize-wpf-3d-performance"></a>Maximieren der 3D-Leistung von WPF
Wie Sie mit der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] um 3D Steuerelemente zu erstellen und 3D-Szenen in Ihren Anwendungen enthalten, es ist wichtig, die zur Optimierung der Leistung berücksichtigen. Dieses Thema enthält eine Liste von 3D Klassen und Eigenschaften, die Auswirkungen auf die Leistung für Ihre Anwendung, sowie Empfehlungen zur Optimierung der Leistung bei ihrer Verwendung verfügen.  
  
 In diesem Thema wird angenommen, ein Kenntnissen der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D-Funktionen. Die Vorschläge in diesem Dokument gelten, für ", Renderingebene 2" – Hardware, die Pixel-Shader-Version 2.0 und Vertex-Shader-Version 2.0 unterstützt ungefähr definiert. Weitere Informationen finden Sie unter [Graphics Rendering Tiers](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
## <a name="performance-impact-high"></a>Auswirkungen auf die Leistung: hoch  
  
|Eigenschaft|Empfehlung|  
|-|-|  
|<xref:System.Windows.Media.Brush>|Pinsel-Geschwindigkeit (am schnellsten langsamsten):<br /><br /> <xref:System.Windows.Media.SolidColorBrush><br /><br /> <xref:System.Windows.Media.LinearGradientBrush><br /><br /> <xref:System.Windows.Media.ImageBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush>(zwischengespeichert)<br /><br /> <xref:System.Windows.Media.VisualBrush>(zwischengespeichert)<br /><br /> <xref:System.Windows.Media.RadialGradientBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush>(nicht zwischengespeichert)<br /><br /> <xref:System.Windows.Media.VisualBrush>(nicht zwischengespeichert)|  
|<xref:System.Windows.UIElement.ClipToBoundsProperty>|Legen Sie `Viewport3D.ClipToBounds` auf "false", wenn Sie nicht benötigen, damit [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] explizit schneiden Sie den Inhalt des eine <xref:System.Windows.Controls.Viewport3D> der Viewport3D Rechteck. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Clipping mit Antialiasing kann sehr langsam sein und `ClipToBounds` ist (langsam) standardmäßig aktiviert, auf <xref:System.Windows.Controls.Viewport3D>.|  
|<xref:System.Windows.UIElement.IsHitTestVisible%2A>|Legen Sie `Viewport3D.IsHitTestVisible` auf "false", wenn Sie nicht benötigen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] , berücksichtigen den Inhalt des eine <xref:System.Windows.Controls.Viewport3D> hochleistungsfähiger Maus bei Treffertests.  Treffer testen 3D-Inhalt erfolgt in der Software und kann bei großen Netzen langsam sein. <xref:System.Windows.UIElement.IsHitTestVisible%2A>(langsam) standardmäßig aktiviert auf <xref:System.Windows.Controls.Viewport3D>.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D>|Erstellen Sie verschiedene Modelle, nur, wenn sie andere Materialien oder Transformationen erfordern.  Andernfalls versuchen, die viele coalesce <xref:System.Windows.Media.Media3D.GeometryModel3D> Instanzen mit dem gleichen Materialien und Transformationen zu einigen größeren <xref:System.Windows.Media.Media3D.GeometryModel3D> und <xref:System.Windows.Media.Media3D.MeshGeometry3D> Instanzen.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Animation Mesh – ändern die einzelnen Scheitelpunkte eines Netzes auf einer pro-Frame-Basis – ist nicht immer effizient [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Zum Minimieren Auswirkungen auf die Leistung von änderungsbenachrichtigungen aus, wenn jede Vertex geändert wird, trennen Sie das Netz aus der visuellen Struktur vor dem Ausführen von pro-Vertex-Änderung.  Sobald das Netz geändert wurde, erneut mit der visuellen Struktur an.  Versuchen Sie außerdem, die Größe der Netze zu minimieren, die auf diese Weise animiert werden soll.|  
|3D Antialiasing (Antialiasing)|Deaktivieren Sie das Multisampling zum Rendering zu beschleunigen, auf eine <xref:System.Windows.Controls.Viewport3D> durch Festlegen der angefügten Eigenschaft <xref:System.Windows.Media.RenderOptions.EdgeMode%2A> auf `Aliased`.  3D Antialiasing ist standardmäßig auf deaktiviert [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] und für aktiviert [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)] mit 4 Samplings pro Pixel.|  
|Text|Live-Text in einer 3D-Szene (live befindet sich im ein <xref:System.Windows.Media.DrawingBrush> oder <xref:System.Windows.Media.VisualBrush>) können langsam sein. Versuchen Sie, stattdessen verwenden Sie Bilder des Texts (über <xref:System.Windows.Media.Imaging.RenderTargetBitmap>), wenn der Text ändert.|  
|<xref:System.Windows.Media.TileBrush>|Bei Verwendung von muss eine <xref:System.Windows.Media.VisualBrush> oder ein <xref:System.Windows.Media.DrawingBrush> in einer 3D-Szene, da der Inhalt des Pinsels nicht statisch ist, wiederholen Sie den Pinsel zwischenzuspeichern (Festlegen der angefügten Eigenschaft <xref:System.Windows.Media.RenderOptions.CachingHint%2A> auf `Cache`).  Legen Sie die minimale und maximale Skala invalidierung Schwellenwerte (mit den angefügten Eigenschaften <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> und <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A>), damit die zwischengespeicherten Pinsel zu häufig neu generiert werden und gleichzeitig Ihre gewünschte Maß an Qualität.  Standardmäßig <xref:System.Windows.Media.DrawingBrush> und <xref:System.Windows.Media.VisualBrush> werden nicht zwischengespeichert, was bedeutet, dass jedes Mal, wenn ein Element mit dem Pinsel gezeichnet wurde erneut gerendert werden, der gesamte Inhalt des Pinsels zunächst in einen intermediate Oberfläche erneut gerendert werden muss.|  
|<xref:System.Windows.Media.Effects.BitmapEffect>|<xref:System.Windows.Media.Effects.BitmapEffect>Erzwingt, dass alle betroffenen Inhalt ohne die Hardwarebeschleunigung gerendert werden.  Verwenden Sie für optimale Leistung kein <xref:System.Windows.Media.Effects.BitmapEffect>.|  
  
## <a name="performance-impact-medium"></a>Auswirkungen auf die Leistung: Mittel  
  
|Eigenschaft|Empfehlung|  
|-|-|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Bei einem Netz als Kachelmethode verwendet Dreiecke mit freigegebenen Scheitelpunkte definiert ist, und diese Scheitelpunkte die gleiche Position, Normal und Texturkoordinaten haben, jede freigegebene Vertex nur einmal dann definieren und die Dreiecke über einen Index mit <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>.|  
|<xref:System.Windows.Media.ImageBrush>|Wiederholen Sie den Textur Größen zu minimieren, wenn Sie explizite Kontrolle über die Größe haben (bei Verwendung einer <xref:System.Windows.Media.Imaging.RenderTargetBitmap> und/oder ein <xref:System.Windows.Media.ImageBrush>).  Beachten Sie, dass niedrigere Auflösung Texturen können visuelle Qualität verringern, daher versuchen, das richtige Gleichgewicht zwischen Qualität und Leistung gefunden.|  
|Deckkraft|Beim Rendern durchsichtigen 3D-Inhalten (z. B. Reflektionen) verwenden Sie die Deckkraft-Eigenschaften auf den Pinsel oder Materialien (über <xref:System.Windows.Media.Brush.Opacity%2A> oder <xref:System.Windows.Media.Media3D.DiffuseMaterial.Color%2A>) statt ein separates durchsichtigen <xref:System.Windows.Controls.Viewport3D> durch Festlegen von `Viewport3D.Opacity` auf einen Wert kleiner als 1.|  
|<xref:System.Windows.Controls.Viewport3D>|Minimieren Sie die Anzahl der <xref:System.Windows.Controls.Viewport3D> Objekte Sie verwenden in einer Szene.  Fügen Sie viele 3D-Modelle in demselben Viewport3D, anstatt separate Viewport3D-Instanzen für jedes Modell zu erstellen.|  
|<xref:System.Windows.Freezable>|In der Regel ist es auch hilfreich, wiederverwenden <xref:System.Windows.Media.Media3D.MeshGeometry3D>, <xref:System.Windows.Media.Media3D.GeometryModel3D>, Pinsel und Materialien.  Alle sind mehrere übergeordnete Objekte haben, da sie abgeleitet sind `Freezable`.|  
|<xref:System.Windows.Freezable>|Rufen Sie die <xref:System.Windows.Freezable.Freeze%2A> Methode für Freezable-Objekte, wenn deren Eigenschaften bleibt unverändert in der Anwendung.  Einfrieren kann Workingset verkleinern und Leistung zu steigern.|  
|<xref:System.Windows.Media.Brush>|Verwendung <xref:System.Windows.Media.ImageBrush> anstelle von <xref:System.Windows.Media.VisualBrush> oder <xref:System.Windows.Media.DrawingBrush> Wenn der Inhalt des Pinsels nicht ändern.  2D Inhalt konvertiert werden kann, um eine <xref:System.Windows.Controls.Image> über <xref:System.Windows.Media.Imaging.RenderTargetBitmap> und klicken Sie dann in verwendet ein <xref:System.Windows.Media.ImageBrush>.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>|Verwenden Sie keine <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> , wenn tatsächlich, lesen die Back Gesichter müssen Ihrer <xref:System.Windows.Media.Media3D.GeometryModel3D>.|  
|<xref:System.Windows.Media.Media3D.Light>|Hell Geschwindigkeit (am schnellsten langsamsten):<br /><br /> <xref:System.Windows.Media.Media3D.AmbientLight><br /><br /> <xref:System.Windows.Media.Media3D.DirectionalLight><br /><br /> <xref:System.Windows.Media.Media3D.PointLight><br /><br /> <xref:System.Windows.Media.Media3D.SpotLight>|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Versuchen Sie, Netz Größen unter diese Grenzen zu halten:<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>: 20.001 <xref:System.Windows.Media.Media3D.Point3D> Instanzen<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>: 60.003 <xref:System.Int32> Instanzen|  
|<xref:System.Windows.Media.Media3D.Material>|Material Geschwindigkeit (am schnellsten langsamsten):<br /><br /> <xref:System.Windows.Media.Media3D.EmissiveMaterial><br /><br /> <xref:System.Windows.Media.Media3D.DiffuseMaterial><br /><br /> <xref:System.Windows.Media.Media3D.SpecularMaterial>|  
|<xref:System.Windows.Media.Brush>|[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]3D nicht sichtbare Pinsel (schwarze Ambiente-Pinsel, klare Pinsel usw.) auf konsistente Weise zu beenden.  Erwägen Sie, aus der Szene entfernen.|  
|<xref:System.Windows.Media.Media3D.MaterialGroup>|Jede <xref:System.Windows.Media.Media3D.Material> in einem <xref:System.Windows.Media.Media3D.MaterialGroup> bewirkt, dass eine andere Renderingdurchlauf, so viele Materialien einschließlich auch einfache Materialien, die Füllung-Anforderungen für Ihre GPU drastisch erhöhen können.  Minimieren Sie die Anzahl der Materialien in Ihrem <xref:System.Windows.Media.Media3D.MaterialGroup>.|  
  
## <a name="performance-impact-low"></a>Auswirkungen auf die Leistung: Niedrig  
  
|Eigenschaft|Empfehlung|  
|-|-|  
|<xref:System.Windows.Media.Media3D.Transform3DGroup>|Wenn Animation ist nicht erforderlich, oder die Datenbindung, anstatt einer Transform-Gruppenstatus enthält mehrere Transformationen verwenden Sie einen einzelnen <xref:System.Windows.Media.Media3D.MatrixTransform3D>, das Festlegen auf das Produkt aller Transformationen werden, die andernfalls unabhängig voneinander in der Gruppe "Transformieren" vorhanden wäre.|  
|<xref:System.Windows.Media.Media3D.Light>|Minimieren Sie die Anzahl der in der Szene leuchten. Zu viele Leuchten in eine Szene erzwingt [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] auf Elemente des Softwarerendering zurückgreifen.  Die Grenzwerte sind ungefähr 110 <xref:System.Windows.Media.Media3D.DirectionalLight> Objekte 70 <xref:System.Windows.Media.Media3D.PointLight> Objekte oder 40 <xref:System.Windows.Media.Media3D.SpotLight> Objekte.|  
|<xref:System.Windows.Media.Media3D.ModelVisual3D>|Trennen Sie bewegliche Objekte von statischen Objekten verlegen, in separaten <xref:System.Windows.Media.Media3D.ModelVisual3D> Instanzen.  ModelVisual3D ist "schwerer" als <xref:System.Windows.Media.Media3D.GeometryModel3D> daran, dass es transformierte Grenzen zwischenspeichert.  GeometryModel3D wurde optimiert, um ein Modell sein. ModelVisual3D wird optimiert, um eine Szene Knoten sein.  Verwenden Sie ModelVisual3D freigegebene Instanzen von GeometryModel3D in der Szene zu versetzen.|  
|<xref:System.Windows.Media.Media3D.Light>|Minimieren Sie die Anzahl der Male, die die Anzahl von Leuchten, die in der Szene zu ändern.  Jeder Änderung der erzwingt ein Shader Regenerierung noch neu kompiliert, es sei denn, diese Konfiguration wurde zuvor vorhanden war (und somit des Shaders zwischengespeichert wurde).|  
|Hell|Schwarz Leuchten wird nicht angezeigt werden, aber sie werden hinzugefügt, um Zeit zu rendern; sollten Sie darauf verzichten.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Minimieren Sie die Erstellungszeit der großen Auflistungen im [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], z. B. eine MeshGeometry3D <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>, und <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>, vorab die Auflistungen vor der Auffüllung des Feldwerts Größe. Wenn möglich, übergeben Sie die Sammlungen Konstruktoren aufgefüllten Datenstrukturen wie Arrays oder Listen aus.|  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über 3D-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
