---
title: "Übersicht über 3D-Grafiken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D graphics [WPF]
- graphics [WPF], 3-D
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 979cc7580471f616d39056f541b8374b372e8e88
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="3-d-graphics-overview"></a>Übersicht über 3D-Grafiken
<a name="introduction"></a> Mit der [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Funktionalität in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] können Entwickler 3D-Grafiken jeweils in Markup- und prozeduralem Code zeichnen, umwandeln und animieren. Entwickler können [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)]- und [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Grafiken kombinieren, um umfassende Steuerelemente zu erstellen, komplexe Illustrationen von Daten bereitstellen oder die Benutzererfahrung einer Anwendungsschnittstelle erweitern. [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Unterstützung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist nicht dazu da, um eine vollständige Plattform zur Spieleentwicklung bereitzustellen. Dieses Thema bietet eine Übersicht über [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)]-Funktionen im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Grafiksystem.  
 
  
<a name="threed_in_2d"></a>   
## <a name="3-d-in-a-2-d-container"></a>3D in einem 2D-Container  
 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]Grafiken, die Inhalte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird in einem Element gekapselt <xref:System.Windows.Controls.Viewport3D>, die zweidimensionalen Elementstruktur teilnehmen kann. Das Grafiksystem behandelt <xref:System.Windows.Controls.Viewport3D> als ein zweidimensionales visuelles Element, in wie viele andere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. <xref:System.Windows.Controls.Viewport3D>fungiert als ein Fenster – einen Viewport, in eine dreidimensionale Szene. Genauer gesagt handelt es sich um eine Oberfläche, auf die eine [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Szene projiziert wird.  
  
 In einer konventionellen [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] -Anwendung verwenden <xref:System.Windows.Controls.Viewport3D> wie andere Containerelement wie Raster oder Canvas.  Sie können zwar <xref:System.Windows.Controls.Viewport3D> mit anderen [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] Zeichnen von Objekten im gleichen Szenendiagramm, Sie durchdringen können nicht [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] und [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] -Objekte innerhalb einer <xref:System.Windows.Controls.Viewport3D>.  Dieses Thema konzentriert sich auf das Zeichnen von [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Grafiken innerhalb der <xref:System.Windows.Controls.Viewport3D>.  
  
<a name="coord_space"></a>   
## <a name="3-d-coordinate-space"></a>3D-Koordinatenbereich  
 Im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Koordinatensystem für [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Grafiken befindet sich der Ursprung in der linken oberen Ecke des Renderingbereichs (in der Regel der Bildschirm). Im [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-System verlaufen die positiven Werte der x-Achse nach rechts und die positiven Werte der y-Achse nach unten.  Im [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Koordinatensystem befindet sich der Ursprung hingegen in der Mitte des Renderingbereichs. Die positiven Werte der x-Achse verlaufen auch nach rechts, die positiven Werte der y-Achse verlaufen aber nach oben und die positiven Werte der z-Achse laufen vom Ursprung ausgehend auf den Betrachter zu.  
  
 ![Koordinatensysteme](../../../../docs/framework/wpf/graphics-multimedia/media/coordsystem-1.png "CoordSystem 1")  
Darstellungen herkömmlicher 2D- und 3D-Koordinatensysteme  
  
 Der von diesen Achsen definierte Raum ist der feststehende Verweisrahmen für [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Objekte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Wenn Sie innerhalb dieses Raumes Modelle erstellen und Lichter und Kameras, um sie anzuzeigen, ist es hilfreich, diesen feststehenden Verweisrahmen oder „Weltenraum“ vom lokalen zu unterscheiden, den Sie beim Anwenden von Transformationen für jedes Modell erstellen. Beachten Sie außerdem, dass Objekte im Weltenraum je nach der Kamera und den Einstellungen völlig anders oder überhaupt nicht angezeigt werden können. Die Position der Kamera ändert aber nicht die Position von Objekten im Weltenraum.  
  
<a name="cameras"></a>   
## <a name="cameras-and-projections"></a>Kameras und Projektionen  
 Entwickler, die in [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] arbeiten, sind es gewöhnt, zeichnende primitive Typen auf einem zweidimensionalen Bildschirm zu positionieren. Beim Erstellen einer [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Szene ist es wichtig, dass Sie daran denken, dass Sie wirklich eine [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Darstellung von [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Objekten erstellen. Da eine [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Szene je nach Perspektive anders aussieht, müssen Sie diese Perspektive angeben. Die <xref:System.Windows.Media.Media3D.Camera> -Klasse ermöglicht Ihnen das Festlegen dieser Sicht für eine [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Szene.  
  
 Eine andere Möglichkeit, zu verstehen, wie eine [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Szene auf einer [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Oberfläche dargestellt wird, ist durch Beschreibung der Szene als eine Projektion auf die Ansichtsoberfläche. Die <xref:System.Windows.Media.Media3D.ProjectionCamera> können Sie angeben, unterschiedliche Vorhersagen und ihre Eigenschaften ändern, wie die Betrachters verändert sieht [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Modelle. Ein <xref:System.Windows.Media.Media3D.PerspectiveCamera> gibt eine Projektion aus, die die Szene verkürzt.  Das heißt, die <xref:System.Windows.Media.Media3D.PerspectiveCamera> vermittelt-Punkt-Perspektive enthält.  Sie können die Position der Kamera im Koordinatenbereich der Szene, die Richtung und das Sichtfeld der Kamera und ein Vektor angeben, der die Richtung „nach oben“ in der Szene definiert. Das folgende Diagramm veranschaulicht die <xref:System.Windows.Media.Media3D.PerspectiveCamera>des Projektion.  
  
 Die <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> und <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> Eigenschaften <xref:System.Windows.Media.Media3D.ProjectionCamera> schränkt den Bereich der Projektion von der Kamera. Da sich Kameras überall in der Szene befinden können, kann die Kamera auch innerhalb eines Modells oder sehr nah an einem Modell positioniert werden. Dies erschwert ordnungsgemäße die Unterscheidung von Objekten.  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A>können Sie einen Mindestabstand zwischen der Kamera und Ihrer angeben, jenseits derer Objekte nicht gezeichnet werden.  Im Gegensatz dazu <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> ermöglicht die Angabe eine Entfernung von der Kamera, jenseits derer Objekte nicht gezeichnet werden, was sicherstellt, dass die Objekte zu weit erkannt werden nicht in der Szene enthalten sind.  
  
 ![Kamerasetup](../../../../docs/framework/wpf/graphics-multimedia/media/coordsystem-6.png "CoordSystem 6")  
Kameraposition  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera>Gibt eine orthogonale Projektion eine [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Modell eine [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] visuelle Oberfläche. Wie andere Kameras gibt es eine Position, Blickrichtung und die Richtung „nach oben“ an. Im Gegensatz zu <xref:System.Windows.Media.Media3D.PerspectiveCamera>, allerdings <xref:System.Windows.Media.Media3D.OrthographicCamera> beschreibt eine Projektion aus, die Verkürzung der Perspektive nicht enthalten ist. Das heißt, <xref:System.Windows.Media.Media3D.OrthographicCamera> beschreibt ein Sichtfeld, dessen Seiten parallel statt in einem werden, dessen Seiten in ein Punkt, an die Kamera zu erfüllen. Die folgende Abbildung zeigt das gleiche Modell, während der Anzeige mit <xref:System.Windows.Media.Media3D.PerspectiveCamera> und <xref:System.Windows.Media.Media3D.OrthographicCamera>.  
  
 ![Orthografische und perspektivische Projektion](../../../../docs/framework/wpf/graphics-multimedia/media/camera-projections4.png "Camera_projections4")  
Perspektivische und orthografische Projektionen  
  
 Der folgende Code zeigt einige typische Kameraeinstellungen.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>   
## <a name="model-and-mesh-primitives"></a>Modell- und primitive Gittertypen  
  
 <xref:System.Windows.Media.Media3D.Model3D>ist die abstrakte Basisklasse, die eine generische darstellt [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Objekt. Zum Erstellen einer [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Szene, benötigen Sie einige Objekte anzeigen, und die Objekte, die das Szenendiagramm bilden abgeleitet <xref:System.Windows.Media.Media3D.Model3D>. Derzeit ist die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt Modellieren von Geometrien mit <xref:System.Windows.Media.Media3D.GeometryModel3D>. Die <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> Eigenschaft dieses Modells akzeptiert ein Netzes primitive.  
  
 Um ein Modell zu erstellen, erstellen Sie zuerst einen primitiven Typen oder ein Gitter. Ein primitiver [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Typ besteht aus einer Auflistung der Vertices, die eine einzelne [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Entität bilden. Die meisten [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Systeme bieten primitive Typen, die ausgehend von der einfachsten geschlossenen Figur modelliert wurden: drei durch drei Vertices definiertes Dreieck.  Da die drei Punkte eines Dreiecks auf derselben Ebene liegen, können Sie weiterhin Dreiecke hinzufügen, um komplexere Formen, die Gitter genannt werden, zu modellieren.  
  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] stellt derzeit die <xref:System.Windows.Media.Media3D.MeshGeometry3D> -Klasse, womit Sie eine Geometrie angeben; es derzeit nicht unterstützt vordefinierten [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] primitive Typen wie z. B. Kreise und kubische Formen. Erstellen einer <xref:System.Windows.Media.Media3D.MeshGeometry3D> durch Angeben einer Liste Dreieck Scheitelpunkte als seine <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> Eigenschaft. Jede Vertex wird angegeben, wie eine <xref:System.Windows.Media.Media3D.Point3D>.  (Geben Sie diese Eigenschaft in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] als eine Liste von Zahlen in Dreiergruppen an, die die Koordinaten der einzelnen Vertices darstellen.) Je nach Geometrie kann das Gitter aus mehreren Dreiecken bestehen, von denen einige dieselben Eckpunkte (Vertices) teilen. Um das Gitter ordnungsgemäß zu zeichnen, braucht [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Informationen darüber, welche Eckpunkte von welchen Dreiecken geteilt werden. Diese Informationen bereitzustellen, indem eine Liste der Dreiecksindizes mit der <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> Eigenschaft. Diese Liste gibt an, in dem die Punkte im angegebenen, Reihenfolge der <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> Liste wird ein Dreieck bestimmt.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 Im vorherigen Beispiel der <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> Liste gibt acht Scheitelpunkte, um einen Cube geformten Mesh zu definieren. Die <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> Eigenschaft gibt eine Liste der zwölf Gruppen drei Indizes.  Jede Nummer in der Liste bezieht sich auf ein Offset in die <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> Liste.  Beispielsweise die ersten drei Scheitelpunkte gemäß der <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> Liste sind (1,1,0), (0,1,0) und (0,0,0).). Die ersten drei Indizes, die gemäß der <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> Liste sind 0, 2 und 1, entsprechen die erste Seite im dritten und zweiten Punkt in der <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> Liste. Daher setzt sich das erste Dreieck, aus dem das Würfelmodells besteht, aus (1,1,0), (0,1,0), (0,0,0) zusammen. Die verbleibenden elf Dreiecke werden ähnlich ermittelt.  
  
 Sie können weiterhin die Modelldefinition durch Angeben von Werten für die <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> und <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> Eigenschaften.  Um die Oberfläche des Modells zu rendern, benötigt das Grafiksystem Informationen darüber, in welche Richtung die Oberfläche bei jedem gegebenen Dreieck zeigt. Diese Informationen werden dazu verwendet, die Beleuchtung für das Modell zu berechnen: Flächen, die einer Lichtquelle direkt zugewendet sind, erscheinen heller als solche, die von Licht abgewandt sind. Obwohl [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Standardnormalvektoren mithilfe der Positionskoordinaten ermitteln kann, können Sie auch verschiedene Normalvektoren angeben, um sich der Darstellung von gekrümmten Oberflächen zu nähern.  
  
 Die <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> Eigenschaft gibt eine Auflistung von <xref:System.Windows.Point>e, die die Grafiksystem wird gezeigt, wie die Koordinaten zuzuordnen, die bestimmen, wie eine Struktur, die die Eckpunkte des Netzes gezeichnet wird. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>als Wert zwischen 0 (null) bis 1, angegeben sind.  Wie bei der <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> -Eigenschaft berechnet das Grafiksystem kann als Standardwert Texturkoordinaten, aber Sie können entscheiden, legen Sie die Zuordnung einer Textur zu steuern, die Teil einer sich wiederholenden, z. B. enthält verschiedene Texturkoordinaten. Weitere Informationen zu Texturkoordinaten finden Sie in den nachfolgenden Themen oder im Managed Direct3D SDK.  
  
 Im folgenden Beispiel wird veranschaulicht, wie eine Seite des Würfelmodells in prozeduralem Code erstellt wird. Beachten Sie, dass Sie den gesamten Würfel als einzelnes GeometryModel3D zeichnen können. In diesem Beispiel wird die Würfelseite als unterschiedliches Modell gezeichnet, um später separate Texturen auf die einzelnen Seiten anzuwenden.  
  
 [!code-csharp[3doverview#3DOverview3DN6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>   
## <a name="applying-materials-to-the-model"></a>Anwenden von Materialien auf das Modell  
  
 Damit ein Gitter wie ein dreidimensionales Objekt aussieht, muss eine Textur darauf angewendet werden, die die von den Vertices und Dreiecken definierte Fläche abdeckt, sodass es beleuchtet und von der Kamera projiziert werden kann. In [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], verwenden Sie die <xref:System.Windows.Media.Brush> Klasse, um Farben, Muster, Verläufe oder anderen visuellen Inhalt auf Bereiche des Bildschirms angewendet werden sollen.  Die Darstellung von [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Objekten ist eine Funktion des Beleuchtungsmodells und nicht nur des der Farbe oder des Musters, die darauf angewendet werden. Reale Objekte reflektieren Licht unterschiedlich, je nach der Qualität ihrer Oberflächen: glänzende und leuchtende Oberflächen sehen anders aus als raue oder matte Oberflächen, und einige Objekte scheinen Licht zu absorbieren, während andere leuchten. Sie können dieselben Pinsel auf [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Objekte anwenden, die Sie auch auf [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Objekte anwenden können, allerdings nicht direkt.  
  
 Zum Definieren der Merkmale der Oberfläche für ein Modell, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet die <xref:System.Windows.Media.Media3D.Material> abstrakte Klasse. Die konkreten Unterklassen von „Material“ bestimmen einige der Darstellungseigenschaften der Modelloberfläche und stellen jeweils eine Pinseleigenschaft bereit, der Sie ein SolidColorBrush, TileBrush oder VisualBrush übergeben können.  
  
-   <xref:System.Windows.Media.Media3D.DiffuseMaterial>Gibt an, dass es sich bei der Pinsel für das Modell angewendet werden soll, als wäre das Modell diffus beleuchtet. Die Verwendung von DiffuseMaterial ähnelt am stärksten der direkten Verwendung auf [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Modelle. Modelloberflächen reflektieren das Licht nicht, als ob sie glänzen würden.  
  
-   <xref:System.Windows.Media.Media3D.SpecularMaterial>Gibt an, dass es sich bei der Pinsel für das Modell angewendet werden soll, als wäre das Modell schwer oder glänzend und der Darstellung des Highlights kann. Sie können den Grad, zu dem die Textur schlägt diese Reflektierend Qualität oder "ergänzen," festgelegt, indem Sie einen Wert für die <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A> Eigenschaft.  
  
-   <xref:System.Windows.Media.Media3D.EmissiveMaterial>können Sie angeben, dass die Struktur angewendet wird, als wäre das Modell wurden Licht abgibt, die Farbe des Pinsels ausgeben. Dies macht das Modell nicht zu Licht. Schatteneffekte werden jedoch anders dargestellt, als mit DiffuseMaterial oder SpecularMaterial.  
  
 Für eine bessere Leistung, die Flächen von einer <xref:System.Windows.Media.Media3D.GeometryModel3D> (diese Flächen, die aus der Ansicht sind, da auf der entgegengesetzten Seite des Modells von der Kamera) aus der Szene entfernt werden.  Angeben einer <xref:System.Windows.Media.Media3D.Material> um auf die rückwärtige eines Modells wie eine Ebene anzuwenden, legen Sie des Modells <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> Eigenschaft.  
  
 Um einige Oberflächenqualitäten zu erzielen, z.B. ein Leuchten oder reflektierende Effekte, können Sie nacheinander mehrere unterschiedliche Pinsel auf ein Modell anwenden. Sie können anwenden und mehrere Materialien wiederverwenden, indem die <xref:System.Windows.Media.Media3D.MaterialGroup> Klasse. Die untergeordneten Elemente von MaterialGroup werden nacheinander in mehreren Renderingdurchläufen angewendet.  
  
 In den folgenden Codebeispiele wird gezeigt, wie eine Volltonfarbe und eine Zeichnung als Pinsel auf [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Modelle angewendet wird.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN5](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  
 [!code-xaml[3doverview#3DOverview3DN9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
  
 [!code-csharp[3doverview#3DOverview3DN8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
 [!code-vb[3doverview#3DOverview3DN8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>   
## <a name="illuminating-the-scene"></a>Beleuchten der Szene  
 Lichter in [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Grafiken verhalten sich genauso wie Lichter in der realen Welt: Sie beleuchten Oberflächen. Genauer gesagt bestimmen Lichter, welcher Teil einer Szene auch Teil der Projektion ist. Helle Objekte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erzeugen eine Vielzahl von Licht- und Schatteneffekten und werden nach dem Verhalten verschiedener realer Lichter modelliert. Sie müssen mindestens ein Licht in Ihre Szene aufnehmen, andernfalls sind keine Modelle sichtbar.  
  
 Die folgenden LEDs leiten Sie von der Basisklasse <xref:System.Windows.Media.Media3D.Light>:  
  
-   <xref:System.Windows.Media.Media3D.AmbientLight>: Bietet ambient Beleuchtung, die alle Objekte unabhängig von deren Speicherort oder die Ausrichtung gleichmäßig beleuchtet.  
  
-   <xref:System.Windows.Media.Media3D.DirectionalLight>: Beleuchtet wie eine entfernte Lichtquelle.  Direktionale Lichtquellen haben eine <xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A> angegeben, wie ein Vector3D, jedoch keine angegebenen Speicherort.  
  
-   <xref:System.Windows.Media.Media3D.PointLight>: Beleuchtet wie eine nahe gelegene Lichtquelle. PointLights verfügen über eine Position und senden Licht von dieser Position aus. Objekte in der Szene werden je nach deren Position und Abstand von der Lichtquelle beleuchtet. <xref:System.Windows.Media.Media3D.PointLightBase>macht eine <xref:System.Windows.Media.Media3D.PointLightBase.Range%2A> -Eigenschaft, die Entfernung bestimmt, jenseits derer Modelle nicht durch das Licht beleuchtet werden. PointLight macht außerdem Lichtabnahmeeigenschaften verfügbar, die bestimmen, wie die Lichtintensität mit der Entfernung abnimmt. Sie können die konstante, lineare oder quadratische Interpolationen für die Lichtabnahme angeben.  
  
-   <xref:System.Windows.Media.Media3D.SpotLight>: Erbt von <xref:System.Windows.Media.Media3D.PointLight>. Scheinwerfer beleuchten wie PointLight und weisen sowohl eine Position als auch eine Richtung auf. Projizieren sie das Licht in einem Kegel geformten Bereich festlegen, indem <xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A> und <xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A> Eigenschaften, die in Grad angegeben.  
  
 Leuchten <xref:System.Windows.Media.Media3D.Model3D> Objekte, sodass Sie transformieren und helle Eigenschaften animieren, einschließlich der Position, Farbe, Richtung und Bereich können.  
  
 [!code-xaml[hittest3d#HitTest3D3DN6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>   
## <a name="transforming-models"></a>Transformieren von Modellen  
 Wenn Sie Modelle erstellen, verfügen diese über eine bestimmte Position in der Szene. Um die Position dieser Modelle in der Szene zu verändern, sie zu drehen oder ihre Größe zu ändern, sollten Sie nicht die Vertices ändern, die die Modelle selbst definieren.  Wenden Sie stattdessen wie in [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Modellen Transformationen auf Modelle an.  
  
 Jedes Modellobjekt verfügt über eine <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> Eigenschaft mit dem verschieben, neu ausrichten oder Ändern der Größe des Modells.  Wenn Sie eine Transformation anwenden, versetzen Sie alle Punkte des Modells durch den in der Transformation angegebenen Vektor oder Wert. Sie haben also den Koordinatenbereich transformiert, in dem das Modell definiert ist (Modellraum), aber Sie haben noch nicht die Werte geändert, die die Geometrie des Modells im Koordinatensystem der gesamten Szene („Weltenraum“) ausmachen.  
  
 Weitere Informationen zum Transformieren von Modellen finden Sie unter [Übersicht über 3D-Transformationen](../../../../docs/framework/wpf/graphics-multimedia/3-d-transformations-overview.md).  
  
<a name="animations"></a>   
## <a name="animating-models"></a>Animieren von Modellen  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-[!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Implementierung gehört dem gleichen Zeitsteuerungs- und Animationssystem an wie die [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Grafiken. Das heißt, dass Sie die Eigenschaften von dessen Modellen animieren müssen, um eine 3D-Szene zu animieren. Es ist möglich, die Eigenschaften von primitiven Typen direkt zu animieren. In der Regel ist es aber einfacher, Transformationen zu animieren, die die Position oder die Darstellung von Modellen ändern. Da Transformationen können, um angewendet werden <xref:System.Windows.Media.Media3D.Model3DGroup> -Objekte sowie einzelne Modelle ist es möglich, einen Satz von Animationen auf ein untergeordnetes Element von einem Model3DGroup und einen anderen Satz von Animationen auf eine Gruppe von untergeordneten Objekten anwenden. Sie können eine Vielzahl von visuellen Effekten erzielen, indem Sie die Eigenschaften der Beleuchtung Ihrer Szene animieren. Schließlich können Sie ggf. die Projektion selbst animieren, indem Sie die Kameraposition oder das Sichtfeld animieren. Hintergrundinformationen zum Zeitsteuerungs- und Animationssystem von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie in den Themen [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md), [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md) und [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Um ein Objekt in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu animieren, erstellen Sie eine Zeitachse, definieren Sie eine Animation (die im Zeitablauf eine tatsächliche Änderung einiger Eigenschaftswerte darstellt), und geben Sie die Eigenschaft an, auf die die Animation angewendet werden soll. Da alle Objekte in einer [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Szene sind untergeordnete Elemente des <xref:System.Windows.Controls.Viewport3D>, die Eigenschaften, die Animationen in der Szene anwenden möchten, sind Eigenschaften von Viewport3D Eigenschaften.  
  
 Angenommen, ein Modell soll an seiner Position als wackelnd angezeigt werden. Sie können entscheiden, gelten eine <xref:System.Windows.Media.Media3D.RotateTransform3D> für das Modell und seine Rotationsachse aus einem Vektor in einen anderen animieren. Das folgende Codebeispiel veranschaulicht die Anwendung einer Vector3DAnimation auf die Achseneigenschaft der Rotation3D-Klasse der Transformation unter der Annahme, dass RotateTransform3D eine der vielen Transformationen darstellt, die auf das Modell mit TransformGroup angewendet werden.  
  
 [!code-csharp[3doverview#3DOverview3DN1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>   
## <a name="add-3-d-content-to-the-window"></a>Hinzufügen von 3D-Inhalt zum Fenster  
 Zum Rendern der Szene hinzufügen, Modelle und leuchten auf eine <xref:System.Windows.Media.Media3D.Model3DGroup>, legen Sie dann die <xref:System.Windows.Media.Media3D.Model3DGroup> als die <xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A> von einer <xref:System.Windows.Media.Media3D.ModelVisual3D>. Hinzufügen der <xref:System.Windows.Media.Media3D.ModelVisual3D> auf die <xref:System.Windows.Controls.Viewport3D.Children%2A> Auflistung von der <xref:System.Windows.Controls.Viewport3D>. Fügen Sie Kameras, um die <xref:System.Windows.Controls.Viewport3D> durch Festlegen seiner <xref:System.Windows.Controls.Viewport3D.Camera%2A> Eigenschaft.  
  
 Fügen Sie schließlich die <xref:System.Windows.Controls.Viewport3D> an das Fenster. Wenn die <xref:System.Windows.Controls.Viewport3D> enthalten ist, wie der Inhalt eines Layoutelements wie Zeichenbereich, Angeben der Größe der Viewport3D durch Festlegen seiner <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaften (geerbt von <xref:System.Windows.FrameworkElement>).  
  
 [!code-xaml[hostingwpfusercontrolinwf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Viewport3D>  
 <xref:System.Windows.Media.Media3D.PerspectiveCamera>  
 <xref:System.Windows.Media.Media3D.DirectionalLight>  
 <xref:System.Windows.Media.Media3D.Material>  
 [Übersicht über 3D-Transformationen](../../../../docs/framework/wpf/graphics-multimedia/3-d-transformations-overview.md)  
 [Maximieren der 3D-Leistung von WPF](../../../../docs/framework/wpf/graphics-multimedia/maximize-wpf-3d-performance.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-how-to-topics.md)  
 [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
