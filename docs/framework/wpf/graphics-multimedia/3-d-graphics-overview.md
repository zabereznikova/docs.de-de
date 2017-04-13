---
title: "&#220;bersicht &#252;ber 3D-Grafiken | Microsoft Docs"
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
  - "3D-Grafiken"
  - "Grafiken [WPF], 3D"
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# &#220;bersicht &#252;ber 3D-Grafiken
<a name="introduction"></a> Mit der [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Funktion in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] können Entwickler 3D\-Grafiken in Markup und in prozeduralem Code zeichnen, transformieren und animieren.  [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)]\- und [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Grafiken können dabei kombiniert werden, um umfangreiche Steuerelemente zu erstellen, komplexe Datenabbildungen bereitzustellen oder die Benutzerfreundlichkeit einer Anwendungsbenutzeroberfläche zu verbessern. Die [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Funktionalität in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt nicht den vollen Funktionsumfang einer Entwicklungsplattform für Spiele. Dieses Thema enthält eine Übersicht über die [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)]\-Funktionalität im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Grafiksystem.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="threed_in_2d"></a>   
## 3D in einem 2D\-Container  
 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Grafikinhalte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sind gekapselt in ein Element, <xref:System.Windows.Controls.Viewport3D>, das in die zweidimensionale Elementstruktur eingebunden werden kann.  Das Grafiksystem behandelt <xref:System.Windows.Controls.Viewport3D> in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wie viele andere Elemente als zweidimensionales visuelles Element.  <xref:System.Windows.Controls.Viewport3D> funktioniert als Fenster \(Viewport\) in eine dreidimensionale Szene.  Genauer gesagt, handelt es sich hierbei um die Oberfläche, auf der eine [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Szene projiziert wird.  
  
 In einer konventionellen [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]\-Anwendung verwenden Sie <xref:System.Windows.Controls.Viewport3D> so wie jedes andere Containerelement, z. B. wie Raster oder Canvas.  Auch wenn Sie <xref:System.Windows.Controls.Viewport3D> mit anderen [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]\-Zeichnungsobjekten in demselben Szenendiagramm verwenden können, dürfen sich [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]\-Objekte und [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Objekte in einem <xref:System.Windows.Controls.Viewport3D> nicht überschneiden.  Dieses Thema beschreibt schwerpunktmäßig, wie [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Grafiken im <xref:System.Windows.Controls.Viewport3D> gezeichnet werden.  
  
<a name="coord_space"></a>   
## 3D\-Koordinatenraum  
 Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Koordinatensystem für [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]\-Grafiken ordnet den Ursprung in der oberen linken Ecke des Renderingbereichs \(in der Regel der Bildschirm\) an.  Im [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]\-System verlaufen die positiven Werte der x\-Achse nach rechts und die positiven Werte der y\-Achse nach unten.  Im [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Koordinatensystem befindet sich der Ursprung jedoch in der Mitte des Renderingbereichs. In diesem Fall verlaufen die positiven Werte der x\-Achse nach rechts, die positiven Werte der y\-Achse aber nach oben und die positiven Werte der z\-Achse vom Ursprung nach außen in Richtung des Betrachters.  
  
 ![Koordinatensysteme](../../../../docs/framework/wpf/graphics-multimedia/media/coordsystem-1.png "CoordSystem\-1")  
Herkömmliche Darstellungen von 2D\- und 3D\-Koordinatensystemen  
  
 Der von diesen Achsen definierte Bereich ist der feststehende Verweisrahmen für [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Objekte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Wenn Sie in diesem Bereich Modelle und Lichter und Kameras zur Anzeige der Modelle erstellen, ist es hilfreich, diesen feststehenden Verweisrahmen \(auch "Weltkoordinatensystem" genannt\) vom lokalen Verweisrahmen zu unterscheiden, den Sie beim Anwenden von Transformationen für jedes Modell erstellen.  Beachten Sie außerdem, dass je nach Licht\- und Kameraeinstellung die Objekte innerhalb des Weltkoordinatensystems möglicherweise komplett unterschiedlich oder überhaupt nicht angezeigt werden. Die Position der Kamera verändert die Position der Objekte innerhalb des Weltkoordinatensystems jedoch nicht.  
  
<a name="cameras"></a>   
## Kameras und Projektionen  
 Entwickler, die in [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] arbeiten, sind mit der Positionierung von Zeichnungsprimitiven in einem zweidimensionalen Bildschirm vertraut.  Beim Erstellen einer [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Szene sollten Sie beachten, dass Sie tatsächlich eine [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]\-Darstellung von [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Objekten erstellen.  Da sich die Perspektive der [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Szene je nach der Sicht des Betrachters verändert, müssen Sie diese Perspektive angeben.  Die <xref:System.Windows.Media.Media3D.Camera>\-Klasse ermöglicht es Ihnen, diese Perspektive für eine [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Szene festzulegen.  
  
 Ein Verständnis dafür, wie eine [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Szene auf einer [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]\-Oberfläche dargestellt wird, lässt sich auch dadurch gewinnen, dass die Szene als Projektion auf der Anzeigeoberfläche beschrieben wird.  Mithilfe von <xref:System.Windows.Media.Media3D.ProjectionCamera> können Sie unterschiedliche Projektionen und deren Eigenschaften angeben, um das Erscheinungsbild von [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Modellen für Betrachter zu ändern.  Ein <xref:System.Windows.Media.Media3D.PerspectiveCamera>\-Objekt gibt eine Projektion an, die die Szene verkürzt.  In anderen Worten: <xref:System.Windows.Media.Media3D.PerspectiveCamera> enthält eine Fluchtpunktperspektive.  Sie können neben der Kameraposition im Koordinatensystem der Szene auch die Richtung und das Sichtfeld für die Kamera sowie einen Vektor, der die Richtung "nach oben" in der Szene definiert, angeben.  Das folgende Diagramm veranschaulicht die <xref:System.Windows.Media.Media3D.PerspectiveCamera>\-Projektion.  
  
 Die Eigenschaften <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> und <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> von <xref:System.Windows.Media.Media3D.ProjectionCamera> schränken den Projektionsbereich der Kamera ein.  Da Kameras in der Szene beliebig positioniert werden können, ist es möglich, dass sich die Kamera tatsächlich innerhalb eines Modells oder sehr nah an einem Modell befindet, wodurch Objekte nur schwer voneinander unterschieden werden können.  Mithilfe von <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> können Sie einen Mindestabstand zur Kamera angeben, jenseits dessen keine Objekte gezeichnet werden.  Umgekehrt können Sie mithilfe von <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> einen maximalen Abstand zur Kamera angeben, über den hinaus keine Objekte gezeichnet werden. Dadurch wird sichergestellt, dass Objekte, die aufgrund ihrer Entfernung nicht mehr erkannt werden, nicht Teil der Szene sind.  
  
 ![Kamerasetup](../../../../docs/framework/wpf/graphics-multimedia/media/coordsystem-6.png "CoordSystem\-6")  
Kameraposition  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera> gibt eine orthogonale Projektion eines [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Modells auf eine visuelle [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]\-Oberfläche an.  Wie andere Kameras gibt sie eine Position, Anzeigerichtung und Aufwärtsrichtung an.  Im Gegensatz zu <xref:System.Windows.Media.Media3D.PerspectiveCamera> beschreibt <xref:System.Windows.Media.Media3D.OrthographicCamera> jedoch eine Projektion, die keine Perspektivenverkürzung umfasst.  Anders gesagt, beschreibt <xref:System.Windows.Media.Media3D.OrthographicCamera> ein Sichtfeld mit parallelen Seiten und kein Sichtfeld, dessen Seiten sich in einem Punkt der Kamera treffen.  Das folgende Bild zeigt, wie das gleiche Modell unter Verwendung von <xref:System.Windows.Media.Media3D.PerspectiveCamera> und <xref:System.Windows.Media.Media3D.OrthographicCamera> angezeigt wird.  
  
 ![Orthografische und perspektivische Projektion](../../../../docs/framework/wpf/graphics-multimedia/media/camera-projections4.png "Camera\_projections4")  
Perspektivische und orthographische Projektionen  
  
 Im folgenden Code werden einige typische Kameraeinstellungen veranschaulicht.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>   
## Modell und Gitterprimitive  
 <xref:System.Windows.Media.Media3D.Model3D> ist die abstrakte Basisklasse, die ein generisches [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Objekt darstellt.  Zum Aufbau einer [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Szene benötigen Sie Objekte, die in der Szenengrafik angezeigt werden. Diese Objekte werden aus <xref:System.Windows.Media.Media3D.Model3D> abgeleitet.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt derzeit das Modellieren von Geometrien mit <xref:System.Windows.Media.Media3D.GeometryModel3D>.  Die <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A>\-Eigenschaft dieses Modells verwendet eine Gitterprimitive.  
  
 Um ein Modell zu erstellen, erstellen Sie zunächst eine Primitive oder ein Netz.  Eine [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Primitive ist eine Ansammlung von Eckpunkten, die eine einzelne [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Entität bilden.  Die meisten [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Systeme stellen Primitive bereit, deren Modell auf der einfachsten geschlossenen Figur beruht: einem aus drei Eckpunkten definierten Dreieck.  Da sich die drei Punkte des Dreiecks auf derselben Ebene befinden, d. h., sie sind koplanar angeordnet, können Sie zum Aufbau komplexerer Formen \(Netze genannt\) weitere Dreiecke hinzufügen.  
  
 Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-System stellt derzeit die <xref:System.Windows.Media.Media3D.MeshGeometry3D>\-Klasse zur Verfügung, anhand derer Sie jegliche Geometrie angeben können. Vordefinierte [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Primitive, z. B. Kreise und kubische Formen, werden derzeit nicht unterstützt.  Sie erstellen ein <xref:System.Windows.Media.Media3D.MeshGeometry3D>\-Objekt, indem Sie zunächst eine Liste von Dreieckseckpunkten als <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>\-Eigenschaft angeben.  Jeder Eckpunkt wird als <xref:System.Windows.Media.Media3D.Point3D> angegeben.  \(In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] definieren Sie diese Eigenschaft anhand einer Liste von Nummern, die in Dreiergruppen eingeteilt sind und die Koordinaten der einzelnen Eckpunkte darstellen.\) Das Netz kann je nach Geometrie aus mehreren Dreiecken bestehen, von denen einige dieselben Ecken \(Eckpunkte\) verwenden können.  Um das Netz ordnungsgemäß zu zeichnen, benötigt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Informationen darüber, welche Eckpunkte von welchen Dreiecken gemeinsam verwendet werden.  Sie stellen diese Informationen bereit, indem Sie mit der <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>\-Eigenschaft eine Liste mit Dreieckindizes angeben.  Diese Liste definiert die Reihenfolge, in der die in der <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>\-Liste angegebenen Punkte ein Dreieck formen.  
  
 [!code-xml[basic3d#Basic3DXAML3DN3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 Im vorherigen Beispiel werden in der <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>\-Liste acht Eckpunkte angegeben, um ein Netz in der Form eines Würfels zu definieren.  Die <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>\-Eigenschaft enthält eine Liste von zwölf Gruppen mit jeweils drei Indizes.  Jede Zahl in der Liste verweist auf einen Offset in der <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>\-Liste.  Beispiel: Die von der <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>\-Liste angegebenen ersten drei Eckpunkte sind \(1,1,0\), \(0,1,0\) und \(0,0,0\).  Die ersten drei Indizes in der <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>\-Liste lauten 0, 2 und 1. Sie entsprechen dem ersten, dritten und zweiten Punkt in der <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>\-Liste.  Aus diesem Grund wird das erste Dreieck des Cube\-Modells aus den Eckpunkten \(1,1,0\) bis \(0,1,0\) bis \(0,0,0\) gebildet. Die restlichen elf Dreiecke werden ähnlich bestimmt.  
  
 Sie können mit der Modelldefinition fortfahren, indem Sie die Werte für die Eigenschaften <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> und <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> angeben.  Um die Modelloberfläche rendern zu können, benötigt das Grafiksystem Informationen dazu, in welche Richtung die Oberfläche in jedem gegebenen Dreieck zeigt.  Das System verwendet diese Informationen, um die Beleuchtung für das Modell zu berechnen: Oberflächen, die sich direkt einer Lichtquelle zuwenden, werden heller angezeigt als die Oberflächen, die nicht auf das Licht ausgerichtet sind.  Obwohl [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Standard\-Normalenvektoren mithilfe der Positionskoordinaten bestimmen kann, können Sie zusätzlich verschiedene Normalenvektoren angeben, um die Darstellung von gekrümmten Oberflächen anzugleichen.  
  
 Die <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>\-Eigenschaft gibt eine Auflistung von <xref:System.Windows.Point>\-Elementen an, anhand derer das Grafiksystem erkennt, wie die Koordinaten zuzuordnen sind. Die Koordinaten bestimmen, wie eine Textur innerhalb der Eckpunkte im Netz gezeichnet wird.  Die <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>\-Eigenschaft wird als Wert zwischen 0 und 1 \(einschließlich\) angegeben.  Das Grafiksystem kann wie bei der <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>\-Eigenschaft Standard\-Texturkoordinaten berechnen. Sie können jedoch unterschiedliche Texturkoordinaten festlegen, um die Zuordnung einer Textur zu steuern, die z. B. einen Teil eines sich wiederholenden Musters enthält.  Weitere Informationen über Texturkoordinaten finden Sie in den nachfolgenden Themen oder im verwalteten Direct3D\-SDK.  
  
 Das folgende Beispiel zeigt, wie eine Fläche des Cube\-Modells in prozeduralem Code erstellt wird.  Beachten Sie, dass Sie das gesamte Cube\-Modell als ein einzelnes GeometryModel3D\-Modell zeichnen können. In diesem Beispiel werden die Flächen in unterschiedlichen Modellen gezeichnet, um später separate Texturen auf die einzelnen Flächen anzuwenden.  
  
 [!code-csharp[3doverview#3DOverview3DN6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>   
## Anwenden von Materialien auf ein Modell  
 Damit ein Netz als dreidimensionales Objekt angezeigt wird, muss es über eine Textur verfügen, die die von den Eckpunkten und Dreiecken definierte Oberfläche abdeckt. Auf diese Weise kann es durch die Kamera beleuchtet und projiziert werden.  In [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] verwenden Sie die <xref:System.Windows.Media.Brush>\-Klasse, um auf Bildschirmbereiche Farben, Muster, Farbverläufe oder andere visuelle Inhalte anzuwenden.  Die Darstellung von [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Objekten ist jedoch eine Funktion des Beleuchtungsmodells und hängt nicht nur von verwendeten Farben oder Mustern ab.  Reale Objekte reflektieren das Licht je nach Oberflächenqualität unterschiedlich: Das Erscheinungsbild glatter und glänzender Oberflächen unterscheidet sich vom Erscheinungsbild der rauen oder matten Oberflächen; und einige Objekte absorbieren das Licht scheinbar, während andere leuchten.  Sie können für [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Objekte alle Pinsel anwenden, die Ihnen auch für [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]\-Objekte zur Verfügung stehen. Ein direktes Anwenden ist jedoch nicht möglich.  
  
 Um die Eigenschaften einer Modelloberfläche zu definieren, verwendet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die abstrakte <xref:System.Windows.Media.Media3D.Material>\-Klasse.  Die konkreten Materialunterklassen bestimmen einige der Darstellungseigenschaften der Modelloberfläche und enthalten jeweils eine Pinseleigenschaft, an die Sie ein SolidColorBrush, TileBrush oder VisualBrush übergeben können.  
  
-   <xref:System.Windows.Media.Media3D.DiffuseMaterial> gibt an, dass der Pinsel auf das Modell so angewendet wird, als wäre das Modell diffus beleuchtet.  Die Verwendung von DiffuseMaterial ist meistens gleichzusetzen mit der direkten Verwendung von Pinseln für [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]\-Modelle; Modelloberflächen lassen reflektiertes Licht nicht glänzend erscheinen.  
  
-   <xref:System.Windows.Media.Media3D.SpecularMaterial> gibt an, dass der Pinsel auf das Modell so angewendet wird, als wäre die Modelloberfläche fest oder glänzend und in der Lage, Glanzlichter zu reflektieren.  Sie können den Umfang festlegen, in dem die Textur diese Reflexionsqualität \(den "Glanz"\) suggeriert, indem Sie einen Wert für die <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A>\-Eigenschaft angeben.  
  
-   Mithilfe von <xref:System.Windows.Media.Media3D.EmissiveMaterial> können Sie festlegen, dass die Textur so angewendet wird, als würde das Modell Licht in der Pinselfarbe abgeben.  Das Modell wird dadurch nicht zum Licht. Es wird sich jedoch im Shadowing anders verhalten als wenn es mit einer DiffuseMaterial\- oder SpecularMaterial\-Textur versehen wäre.  
  
 Zur Leistungsverbesserung werden die rückwärtigen Seiten von einem <xref:System.Windows.Media.Media3D.GeometryModel3D> \(die Flächen, die außerhalb des Sichtfensters sind, weil sie sich aus der Perspektive der Kamera auf der gegenüberliegenden Seite des Modells befinden\) aus der Szene herausgefiltert.  Wenn Sie angeben möchten, dass ein <xref:System.Windows.Media.Media3D.Material> auf die rückwärtige Seite eines Modells wie eine Ebene anzuwenden ist, müssen Sie die <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>\-Eigenschaft für das Modell festlegen.  
  
 Um gewisse Oberflächeneigenschaften zu erzielen, z. B. Leuchten oder reflektierende Effekte, könnten Sie nacheinander unterschiedliche Pinsel auf ein Modell anwenden.  Sie können mehrere Materialien anwenden und erneut verwenden, indem Sie die <xref:System.Windows.Media.Media3D.MaterialGroup>\-Klasse verwenden.  Die untergeordneten Elemente von MaterialGroup werden in mehreren Renderingdurchläufen vom ersten bis zum letzten Element angewendet.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Volltonfarbe und eine Zeichnung auf [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Modelle als Pinsel angewendet werden.  
  
 [!code-xml[basic3d#Basic3DXAML3DN5](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  
 [!code-xml[3doverview#3DOverview3DN9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
  
 [!code-csharp[3doverview#3DOverview3DN8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
 [!code-vb[3doverview#3DOverview3DN8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>   
## Beleuchten der Szene  
 Lichter in [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Grafiken machen das, was sie auch in der realen Welt machen: Sie sorgen dafür, dass Oberflächen sichtbar werden.  Genauer ausgedrückt: Lichter bestimmen, welcher Teil einer Szene in die Projektion eingeschlossen wird.  Lichtobjekte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erzeugen eine Vielzahl von Licht\- und Schatteneffekten und werden nach dem Verhalten der verschiedenen realen Lichter modelliert.  Die Modelle sind nur sichtbar, wenn Sie in der Szene mindestens ein Licht vorsehen.  
  
 Die folgenden Lichter werden aus der <xref:System.Windows.Media.Media3D.Light>\-Basisklasse abgeleitet:  
  
-   <xref:System.Windows.Media.Media3D.AmbientLight>: stellt eine Umgebungsbeleuchtung bereit, die alle Objekte, unabhängig von ihrer Position oder Ausrichtung, gleichmäßig beleuchtet.  
  
-   <xref:System.Windows.Media.Media3D.DirectionalLight>: beleuchtet wie eine entfernte Lichtquelle.  Bei gerichteten Lichtern wird eine <xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A> als Vector3D ohne Positionsangabe festgelegt.  
  
-   <xref:System.Windows.Media.Media3D.PointLight>: beleuchtet wie eine nahe gelegene Lichtquelle.  PointLights verfügen über eine Position und strahlen ihr Licht von dieser Position aus.  Die in der Szene enthaltenen Objekte werden je nach deren Position und Abstand vom Licht beleuchtet.  <xref:System.Windows.Media.Media3D.PointLightBase> stellt eine <xref:System.Windows.Media.Media3D.PointLightBase.Range%2A>\-Eigenschaft zur Verfügung, die die Entfernung bestimmt, jenseits derer die Modelle vom Licht nicht beleuchtet werden.  PointLight enthält ebenso Dämpfungseigenschaften, die bestimmen, wie sich die Intensität des Lichts mit der Entfernung verringert.  Sie können für die Dämpfung des Lichts konstante, lineare oder quadratische Interpolationen angeben.  
  
-   <xref:System.Windows.Media.Media3D.SpotLight>: erbt von <xref:System.Windows.Media.Media3D.PointLight>.  Scheinwerfer beleuchten wie PointLight \(Punktlichter\) und verfügen sowohl über eine Position als auch über eine Richtung.  Sie projizieren das Licht in einem kegelförmigen Bereich, der von den Eigenschaften <xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A> und <xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A> festgelegt und in Grad angegeben wird.  
  
 Lichter sind <xref:System.Windows.Media.Media3D.Model3D>\-Objekte. Aus diesem Grund können Sie Lichteigenschaften, einschließlich Position, Farbe, Richtung und Bereich, transformieren und animieren.  
  
 [!code-xml[hittest3d#HitTest3D3DN6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>   
## Transformieren von Modellen  
 Wenn Sie Modelle erstellen, haben sie eine bestimmte Position in der Szene.  Um diese Modelle in der Szene zu verschieben, zu drehen oder um ihre Größe zu ändern, sollten Sie nicht die Eckpunkte ändern, die das Modell selbst definieren.  Stattdessen wenden Sie wie in [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] Transformationen auf die Modelle an.  
  
 Jedes Modellobjekt verfügt über eine <xref:System.Windows.Media.Media3D.Model3D.Transform%2A>\-Eigenschaft, mit der Sie das Modell verschieben, neu ausrichten oder in der Größe verändern können.  Wenn Sie eine Transformation anwenden, versetzen Sie gewissermaßen alle Punkte im Modell um den durch die Transformation angegebenen Vektor oder Wert.  Mit anderen Worten: Sie haben den Koordinatenraum transformiert, in dem das Modell definiert ist \("Modellraum"\). Dabei haben Sie jedoch nicht die Werte geändert, aus denen sich die Geometrie des Modells im Koordinatensystem der gesamten Szene \("Weltkoordinatensystem"\) zusammensetzt.  
  
 Weitere Informationen zum Transformieren von Modellen finden Sie unter [Übersicht über 3D\-Transformationen](../../../../docs/framework/wpf/graphics-multimedia/3-d-transformations-overview.md).  
  
<a name="animations"></a>   
## Animieren von Modellen  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Implementierung gehört zum gleichen Zeitsteuerungs\- und Animationssystem wie [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]\-Grafiken.  Mit anderen Worten: Zur Animation einer 3D\-Szene animieren Sie die Eigenschaften ihrer Modelle.  Sie können die Eigenschaften von Primitiven direkt animieren. In der Regel ist es jedoch einfacher, die Transformationen zu animieren, anhand derer die Position oder die Darstellung der Modelle geändert werden.  Da sich Transformationen sowohl auf <xref:System.Windows.Media.Media3D.Model3DGroup>\-Objekte als auch auf einzelne Modelle anwenden lassen, können Sie einen Satz von Animationen auf ein untergeordnetes Model3DGroup\-Objekt und einen weiteren Satz von Animationen auf eine Gruppe von untergeordneten Objekten anwenden.  Sie können auch eine Vielzahl visueller Effekte erzielen, indem Sie die Eigenschaften der Szenenbeleuchtung animieren.  Letztendlich können Sie auch die Projektion selbst animieren, indem Sie die Kameraposition oder das Sichtfeld animieren.  Hintergrundinformationen über das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Zeitsteuerungs\- und \-Animationssystem finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md), [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md) und unter [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Um ein Objekt in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu animieren, erstellen Sie eine Zeitachse, definieren eine Animation \(tatsächlich eine Änderung einiger Eigenschaftswerte im Zeitablauf\) und geben die Eigenschaft an, auf die die Animation angewendet werden soll.  Da alle Objekte einer [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Szene untergeordnete Objekte von <xref:System.Windows.Controls.Viewport3D> sind, handelt es sich bei den Eigenschaften, auf die sich die in der Szene anzuwendenden Animationen beziehen, um Eigenschaften von Viewport3D\-Eigenschaften.  
  
 Angenommen, Sie möchten ein Modell so anzeigen, dass es an einer Position wackelt.  Dazu sollten Sie <xref:System.Windows.Media.Media3D.RotateTransform3D> auf das Modell anwenden und dessen Rotationsachse von einem Vektor auf einen anderen animieren.  Im folgenden Codebeispiel wird das Anwenden einer Vector3DAnimation auf die Achseneigenschaft von Rotation3D der Transformation veranschaulicht. Es wird angenommen, dass RotateTransform3D als eine von mehreren Transformationen mit TransformGroup auf das Modell angewendet wird.  
  
 [!code-csharp[3doverview#3DOverview3DN1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>   
## Hinzufügen von 3D\-Inhalt zum Fenster  
 Um die Szene zu rendern, fügen Sie <xref:System.Windows.Media.Media3D.Model3DGroup> Modelle und Lichter hinzu. Danach legen Sie <xref:System.Windows.Media.Media3D.Model3DGroup> als <xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A> von <xref:System.Windows.Media.Media3D.ModelVisual3D> fest.  Daraufhin fügen Sie <xref:System.Windows.Media.Media3D.ModelVisual3D> der <xref:System.Windows.Controls.Viewport3D.Children%2A>\-Auflistung von <xref:System.Windows.Controls.Viewport3D> hinzu.  Dann fügen Sie <xref:System.Windows.Controls.Viewport3D> Kameras hinzu, indem Sie dessen <xref:System.Windows.Controls.Viewport3D.Camera%2A>\-Eigenschaft festlegen.  
  
 Abschließend fügen Sie <xref:System.Windows.Controls.Viewport3D> dem Fenster hinzu.  Wenn <xref:System.Windows.Controls.Viewport3D> als Inhalt eines Layoutelements, z. B. Canvas, hinzugefügt wird, geben Sie die Viewport3D\-Größe an, indem Sie dessen Eigenschaften <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A> festlegen \(geerbt von <xref:System.Windows.FrameworkElement>\).  
  
 [!code-xml[hostingwpfusercontrolinwf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.Viewport3D>   
 <xref:System.Windows.Media.Media3D.PerspectiveCamera>   
 <xref:System.Windows.Media.Media3D.DirectionalLight>   
 <xref:System.Windows.Media.Media3D.Material>   
 [Übersicht über 3D\-Transformationen](../../../../docs/framework/wpf/graphics-multimedia/3-d-transformations-overview.md)   
 [Maximieren der 3D\-Leistung von WPF](../../../../docs/framework/wpf/graphics-multimedia/maximize-wpf-3d-performance.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-how-to-topics.md)   
 [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)