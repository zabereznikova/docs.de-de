---
title: Übersicht über 3D-Grafiken
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D graphics [WPF]
- graphics [WPF], 3-D
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
ms.openlocfilehash: 2021a1bf706233e6361848a95f512262c1c16b6f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647106"
---
# <a name="3-d-graphics-overview"></a>Übersicht über 3D-Grafiken
<a name="introduction"></a> Mit der [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Funktionalität in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] können Entwickler 3D-Grafiken jeweils in Markup- und prozeduralem Code zeichnen, umwandeln und animieren. Entwickler können [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)]- und [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Grafiken kombinieren, um umfassende Steuerelemente zu erstellen, komplexe Illustrationen von Daten bereitstellen oder die Benutzererfahrung einer Anwendungsschnittstelle erweitern. [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Unterstützung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist nicht dazu da, um eine vollständige Plattform zur Spieleentwicklung bereitzustellen. Dieses Thema bietet eine Übersicht über [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)]-Funktionen im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Grafiksystem.  

<a name="threed_in_2d"></a>   
## <a name="3-d-in-a-2-d-container"></a>3D in einem 2D-Container  
 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Grafik, die Inhalte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in ein Element gekapselt <xref:System.Windows.Controls.Viewport3D>, kann das Teil einer zweidimensionalen Elementstruktur sein. Das Grafiksystem behandelt <xref:System.Windows.Controls.Viewport3D> als ein zweidimensionales visuelles Objekt, in wie viele andere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. <xref:System.Windows.Controls.Viewport3D> fungiert als Fenster – ein Anzeigebereich – in eine dreidimensionale Szene. Genauer gesagt handelt es sich um eine Oberfläche, auf die eine [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Szene projiziert wird.  
  
 In einer konventionellen [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] -Anwendung verwenden Sie <xref:System.Windows.Controls.Viewport3D> wie andere Containerelement wie Raster oder Canvas.  Sie können zwar <xref:System.Windows.Controls.Viewport3D> mit anderen [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] Zeichnen von Objekten im selben szenegraphen, Sie durchdringen können nicht [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] und [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Objekte innerhalb einer <xref:System.Windows.Controls.Viewport3D>.  Dieses Thema konzentriert sich auf das Zeichnen von [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] -Grafiken innerhalb der <xref:System.Windows.Controls.Viewport3D>.  
  
<a name="coord_space"></a>   
## <a name="3-d-coordinate-space"></a>3D-Koordinatenbereich  
 Im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Koordinatensystem für [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Grafiken befindet sich der Ursprung in der linken oberen Ecke des Renderingbereichs (in der Regel der Bildschirm). Im [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-System verlaufen die positiven Werte der x-Achse nach rechts und die positiven Werte der y-Achse nach unten.  Im [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Koordinatensystem befindet sich der Ursprung hingegen in der Mitte des Renderingbereichs. Die positiven Werte der x-Achse verlaufen auch nach rechts, die positiven Werte der y-Achse verlaufen aber nach oben und die positiven Werte der z-Achse laufen vom Ursprung ausgehend auf den Betrachter zu.  
  
 ![Koordinatensysteme](./media/coordsystem-1.png "CoordSystem-1")  
Darstellungen herkömmlicher 2D- und 3D-Koordinatensysteme  
  
 Der von diesen Achsen definierte Raum ist der feststehende Verweisrahmen für [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Objekte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Wenn Sie innerhalb dieses Raumes Modelle erstellen und Lichter und Kameras, um sie anzuzeigen, ist es hilfreich, diesen feststehenden Verweisrahmen oder „Weltenraum“ vom lokalen zu unterscheiden, den Sie beim Anwenden von Transformationen für jedes Modell erstellen. Beachten Sie außerdem, dass Objekte im Weltenraum je nach der Kamera und den Einstellungen völlig anders oder überhaupt nicht angezeigt werden können. Die Position der Kamera ändert aber nicht die Position von Objekten im Weltenraum.  
  
<a name="cameras"></a>   
## <a name="cameras-and-projections"></a>Kameras und Projektionen  
 Entwickler, die in [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] arbeiten, sind es gewöhnt, zeichnende primitive Typen auf einem zweidimensionalen Bildschirm zu positionieren. Beim Erstellen einer [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Szene ist es wichtig, dass Sie daran denken, dass Sie wirklich eine [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Darstellung von [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Objekten erstellen. Da eine [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Szene je nach Perspektive anders aussieht, müssen Sie diese Perspektive angeben. Die <xref:System.Windows.Media.Media3D.Camera> Klasse ermöglicht Ihnen die Angabe dieser Sicht für eine [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Szene.  
  
 Eine andere Möglichkeit, zu verstehen, wie eine [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Szene auf einer [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Oberfläche dargestellt wird, ist durch Beschreibung der Szene als eine Projektion auf die Ansichtsoberfläche. Die <xref:System.Windows.Media.Media3D.ProjectionCamera> können Sie angeben, verschiedene Projektionen und deren Eigenschaften ändern, Betrachters wie erkennt [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Modelle. Ein <xref:System.Windows.Media.Media3D.PerspectiveCamera> gibt eine Projektion an, die die Szene verkürzt.  Das heißt, die <xref:System.Windows.Media.Media3D.PerspectiveCamera> Fluchtpunktperspektive bereitstellt.  Sie können die Position der Kamera im Koordinatenbereich der Szene, die Richtung und das Sichtfeld der Kamera und ein Vektor angeben, der die Richtung „nach oben“ in der Szene definiert. Das folgende Diagramm veranschaulicht die <xref:System.Windows.Media.Media3D.PerspectiveCamera>die Projektion.  
  
 Die <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> und <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> Eigenschaften <xref:System.Windows.Media.Media3D.ProjectionCamera> schränkt den Bereich der Kameraprojektion. Da sich Kameras überall in der Szene befinden können, kann die Kamera auch innerhalb eines Modells oder sehr nah an einem Modell positioniert werden. Dies erschwert ordnungsgemäße die Unterscheidung von Objekten.  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> können Sie einen Mindestabstand zur Kamera angeben, jenseits derer keine Objekte gezeichnet werden.  Im Gegensatz dazu <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> ermöglicht die Angabe eine Entfernung von der Kamera, jenseits derer Objekte nicht gezeichnet werden werden, der sicherstellt, dass die Objekte zu weit weg, um erkannt zu werden nicht in der Szene enthalten sind.  
  
 ![Kamerasetup](./media/coordsystem-6.png "CoordSystem-6")  
Kameraposition  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera> Gibt eine orthogonale Projektion einer [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Modell eine [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] visuelle Oberfläche dar. Wie andere Kameras gibt es eine Position, Blickrichtung und die Richtung „nach oben“ an. Im Gegensatz zu <xref:System.Windows.Media.Media3D.PerspectiveCamera>jedoch <xref:System.Windows.Media.Media3D.OrthographicCamera> beschreibt eine Projektion, die keine perspektivische Verkürzung enthält. Das heißt, <xref:System.Windows.Media.Media3D.OrthographicCamera> beschreibt ein Sichtfeld, dessen Seiten parallel, anstelle eines, dessen Seiten in einem Punkt der Kamera zu erfüllen. Die folgende Abbildung zeigt das gleiche Modell mithilfe von <xref:System.Windows.Media.Media3D.PerspectiveCamera> und <xref:System.Windows.Media.Media3D.OrthographicCamera>.  
  
 ![Orthografische und perspektivische Projektion](./media/camera-projections4.png "Camera_projections4")  
Perspektivische und orthografische Projektionen  
  
 Der folgende Code zeigt einige typische Kameraeinstellungen.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>   
## <a name="model-and-mesh-primitives"></a>Modell- und primitive Gittertypen  
  
 <xref:System.Windows.Media.Media3D.Model3D> ist die abstrakte Basisklasse, die einen generischen darstellt [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Objekt. Zum Erstellen einer [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Szene, benötigen Sie einige anzuzeigende Objekte und die Objekte, aus denen die szenengraph abgeleitet <xref:System.Windows.Media.Media3D.Model3D>. Derzeit den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt das Modellieren von Geometrien mit <xref:System.Windows.Media.Media3D.GeometryModel3D>. Die <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> -Eigenschaft dieses Modell nimmt einen primitiven gittertyp.  
  
 Um ein Modell zu erstellen, erstellen Sie zuerst einen primitiven Typen oder ein Gitter. Ein primitiver [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Typ besteht aus einer Auflistung der Vertices, die eine einzelne [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Entität bilden. Die meisten [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Systeme bieten primitive Typen, die ausgehend von der einfachsten geschlossenen Figur modelliert wurden: drei durch drei Vertices definiertes Dreieck.  Da die drei Punkte eines Dreiecks auf derselben Ebene liegen, können Sie weiterhin Dreiecke hinzufügen, um komplexere Formen, die Gitter genannt werden, zu modellieren.  
  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] -System stellt derzeit die <xref:System.Windows.Media.Media3D.MeshGeometry3D> -Klasse, wodurch Sie jede beliebige Geometrie angeben; es unterstützt derzeit keine vordefinierten [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] -Grundtypen wie Kreise und kubische Formen. Erstellen einer <xref:System.Windows.Media.Media3D.MeshGeometry3D> durch Angabe einer Liste von dreieckvertices als dessen <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> Eigenschaft. Jeder Vertex wird angegeben, wie eine <xref:System.Windows.Media.Media3D.Point3D>.  (Geben Sie diese Eigenschaft in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] als eine Liste von Zahlen in Dreiergruppen an, die die Koordinaten der einzelnen Vertices darstellen.) Je nach Geometrie kann das Gitter aus mehreren Dreiecken bestehen, von denen einige dieselben Eckpunkte (Vertices) teilen. Um das Gitter ordnungsgemäß zu zeichnen, braucht [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Informationen darüber, welche Eckpunkte von welchen Dreiecken geteilt werden. Stellen Sie diese Informationen durch Angabe einer Liste der Dreiecksindizes mit der <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> Eigenschaft. Diese Liste gibt an, in dem die Punkte im angegebenen, Reihenfolge der <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> Liste ein Dreieck bestimmen.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN3](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 Im vorherigen Beispiel das <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> Liste gibt acht Vertices zum Definieren einer würfelförmigen Gitters an. Die <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> Eigenschaft gibt eine Liste von zwölf Gruppen mit drei Indizes an.  Jede Zahl in der Liste verweist auf ein Offset in die <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> Liste.  Z. B. die ersten drei Vertices, die gemäß der <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> Liste sind (1,1,0), (0,1,0) und (0,0,0).). Die ersten drei Indizes, die gemäß der <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> Liste sind 0, 2 und 1, entsprechen dem ersten, dritten und zweiten Punkt in der <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> Liste. Daher setzt sich das erste Dreieck, aus dem das Würfelmodells besteht, aus (1,1,0), (0,1,0), (0,0,0) zusammen. Die verbleibenden elf Dreiecke werden ähnlich ermittelt.  
  
 Sie können weiterhin das Definieren des Modells durch Angeben von Werten für die <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> und <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> Eigenschaften.  Um die Oberfläche des Modells zu rendern, benötigt das Grafiksystem Informationen darüber, in welche Richtung die Oberfläche bei jedem gegebenen Dreieck zeigt. Diese Informationen werden dazu verwendet, die Beleuchtung für das Modell zu berechnen: Flächen, die einer Lichtquelle direkt zugewendet sind, erscheinen heller als solche, die von Licht abgewandt sind. Obwohl [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Standardnormalvektoren mithilfe der Positionskoordinaten ermitteln kann, können Sie auch verschiedene Normalvektoren angeben, um sich der Darstellung von gekrümmten Oberflächen zu nähern.  
  
 Die <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> Eigenschaft gibt eine Auflistung von <xref:System.Windows.Point>s, die das Grafiksystem die Koordinaten zuordnet, die bestimmen, wie eine Textur auf die Vertices des Gitters gezeichnet wird. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> werden als Wert zwischen 0 (null) bis 1, angegeben werden.  Wie bei der <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> -Eigenschaft standardmäßig Texturkoordinaten, aber Sie können auch die Zuordnung einer Textur zu steuern, die Teil einer sich wiederholenden, z. B. enthält andere Texturkoordinaten festlegen, kann das Grafiksystem berechnen. Weitere Informationen zu Texturkoordinaten finden Sie in den nachfolgenden Themen oder im Managed Direct3D SDK.  
  
 Im folgenden Beispiel wird veranschaulicht, wie eine Seite des Würfelmodells in prozeduralem Code erstellt wird. Beachten Sie, dass Sie den gesamten Würfel als einzelnes GeometryModel3D zeichnen können. In diesem Beispiel wird die Würfelseite als unterschiedliches Modell gezeichnet, um später separate Texturen auf die einzelnen Seiten anzuwenden.  
  
 [!code-csharp[3doverview#3DOverview3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>   
## <a name="applying-materials-to-the-model"></a>Anwenden von Materialien auf das Modell  
  
 Damit ein Gitter wie ein dreidimensionales Objekt aussieht, muss eine Textur darauf angewendet werden, die die von den Vertices und Dreiecken definierte Fläche abdeckt, sodass es beleuchtet und von der Kamera projiziert werden kann. In [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], Sie verwenden die <xref:System.Windows.Media.Brush> Klasse, um Bildschirmbereichen Farben, Muster, Farbverläufe oder andere visuelle Inhalte zuweisen.  Die Darstellung von [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Objekten ist eine Funktion des Beleuchtungsmodells und nicht nur des der Farbe oder des Musters, die darauf angewendet werden. Reale Objekte reflektieren Licht unterschiedlich, je nach der Qualität ihrer Oberflächen: glänzende und leuchtende Oberflächen sehen anders aus als raue oder matte Oberflächen, und einige Objekte scheinen Licht zu absorbieren, während andere leuchten. Sie können dieselben Pinsel auf [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Objekte anwenden, die Sie auch auf [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Objekte anwenden können, allerdings nicht direkt.  
  
 Um die Eigenschaften einer Modelloberfläche zu definieren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet die <xref:System.Windows.Media.Media3D.Material> abstrakte Klasse. Die konkreten Unterklassen von „Material“ bestimmen einige der Darstellungseigenschaften der Modelloberfläche und stellen jeweils eine Pinseleigenschaft bereit, der Sie ein SolidColorBrush, TileBrush oder VisualBrush übergeben können.  
  
- <xref:System.Windows.Media.Media3D.DiffuseMaterial> Gibt an, dass der Pinsel auf das Modell angewendet wird, als wäre das Modell diffus beleuchtet. Die Verwendung von DiffuseMaterial ähnelt am stärksten der direkten Verwendung auf [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Modelle. Modelloberflächen reflektieren das Licht nicht, als ob sie glänzen würden.  
  
- <xref:System.Windows.Media.Media3D.SpecularMaterial> Gibt an, dass der Pinsel für das Modell angewendet wird, als wäre die Modelloberfläche oder glänzend und kann Glanzlichter zu reflektieren. Sie können den Grad, wird die Textur diese reflektierende Qualität oder "abzuheben," vorschlagen, festlegen, durch die Angabe eines Werts für die <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A> Eigenschaft.  
  
- <xref:System.Windows.Media.Media3D.EmissiveMaterial> können Sie angeben, dass die Textur angewendet wird, als ob das Modell Licht abgibt, die Farbe des Pinsels. Dies macht das Modell nicht zu Licht. Schatteneffekte werden jedoch anders dargestellt, als mit DiffuseMaterial oder SpecularMaterial.  
  
 Zur Verbesserung der Leistung die Rückseiten von einem <xref:System.Windows.Media.Media3D.GeometryModel3D> (diese Seiten, die aus der Ansicht sind, da sie auf der entgegengesetzten Seite des Modells mit der Kamera sind) aus der Szene herausgefiltert werden.  Angeben einer <xref:System.Windows.Media.Media3D.Material> legen Sie zum Anwenden von auf die Rückseite eines Modells, wie eine Ebene des Modells <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> Eigenschaft.  
  
 Um einige Oberflächenqualitäten zu erzielen, z.B. ein Leuchten oder reflektierende Effekte, können Sie nacheinander mehrere unterschiedliche Pinsel auf ein Modell anwenden. Sie können verschiedene Materialien mithilfe wieder und Anwenden der <xref:System.Windows.Media.Media3D.MaterialGroup> Klasse. Die untergeordneten Elemente von MaterialGroup werden nacheinander in mehreren Renderingdurchläufen angewendet.  
  
 In den folgenden Codebeispiele wird gezeigt, wie eine Volltonfarbe und eine Zeichnung als Pinsel auf [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Modelle angewendet wird.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN5](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  
 [!code-xaml[3doverview#3DOverview3DN9](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
  
 [!code-csharp[3doverview#3DOverview3DN8](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
 [!code-vb[3doverview#3DOverview3DN8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>   
## <a name="illuminating-the-scene"></a>Beleuchten der Szene  
 Lichter in [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Grafiken verhalten sich genauso wie Lichter in der realen Welt: Sie beleuchten Oberflächen. Genauer gesagt bestimmen Lichter, welcher Teil einer Szene auch Teil der Projektion ist. Helle Objekte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erzeugen eine Vielzahl von Licht- und Schatteneffekten und werden nach dem Verhalten verschiedener realer Lichter modelliert. Sie müssen mindestens ein Licht in Ihre Szene aufnehmen, andernfalls sind keine Modelle sichtbar.  
  
 Die folgenden Lichter leiten sich von der Basisklasse <xref:System.Windows.Media.Media3D.Light>:  
  
- <xref:System.Windows.Media.Media3D.AmbientLight>: Bietet Umgebungslicht, das alle Objekte unabhängig von ihrer Position oder Ausrichtung gleichmäßig beleuchtet.  
  
- <xref:System.Windows.Media.Media3D.DirectionalLight>: Beleuchtet wie eine entfernte Lichtquelle.  Diffuses Licht ist eine <xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A> als ein Vector3D ohne Positionsangabe angegeben.  
  
- <xref:System.Windows.Media.Media3D.PointLight>: Beleuchtet wie eine nahegelegene Lichtquelle. PointLights verfügen über eine Position und senden Licht von dieser Position aus. Objekte in der Szene werden je nach deren Position und Abstand von der Lichtquelle beleuchtet. <xref:System.Windows.Media.Media3D.PointLightBase> Stellt eine <xref:System.Windows.Media.Media3D.PointLightBase.Range%2A> -Eigenschaft, die Entfernung bestimmt, jenseits derer Modelle nicht vom Licht beleuchtet werden. PointLight macht außerdem Lichtabnahmeeigenschaften verfügbar, die bestimmen, wie die Lichtintensität mit der Entfernung abnimmt. Sie können die konstante, lineare oder quadratische Interpolationen für die Lichtabnahme angeben.  
  
- <xref:System.Windows.Media.Media3D.SpotLight>: Erbt von <xref:System.Windows.Media.Media3D.PointLight>. Scheinwerfer beleuchten wie PointLight und weisen sowohl eine Position als auch eine Richtung auf. Sie projizieren das Licht in einem kegelförmigen Bereich festlegen, indem <xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A> und <xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A> Eigenschaften, die in Grad angegeben.  
  
 Lichter sind <xref:System.Windows.Media.Media3D.Model3D> Objekte, sodass Sie transformieren und animieren einfache Eigenschaften, einschließlich der Position, Farbe, Richtung und Bereich können.  
  
 [!code-xaml[hittest3d#HitTest3D3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>   
## <a name="transforming-models"></a>Transformieren von Modellen  
 Wenn Sie Modelle erstellen, verfügen diese über eine bestimmte Position in der Szene. Um die Position dieser Modelle in der Szene zu verändern, sie zu drehen oder ihre Größe zu ändern, sollten Sie nicht die Vertices ändern, die die Modelle selbst definieren.  Wenden Sie stattdessen wie in [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Modellen Transformationen auf Modelle an.  
  
 Jedes Modellobjekt verfügt über eine <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> Eigenschaft mit dem verschieben, neu ausrichten oder Ändern der Größe des Modells.  Wenn Sie eine Transformation anwenden, versetzen Sie alle Punkte des Modells durch den in der Transformation angegebenen Vektor oder Wert. Sie haben also den Koordinatenbereich transformiert, in dem das Modell definiert ist (Modellraum), aber Sie haben noch nicht die Werte geändert, die die Geometrie des Modells im Koordinatensystem der gesamten Szene („Weltenraum“) ausmachen.  
  
 Weitere Informationen zum Transformieren von Modellen finden Sie unter [Übersicht über 3D-Transformationen](3-d-transformations-overview.md).  
  
<a name="animations"></a>   
## <a name="animating-models"></a>Animieren von Modellen  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-[!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]-Implementierung gehört dem gleichen Zeitsteuerungs- und Animationssystem an wie die [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]-Grafiken. Das heißt, dass Sie die Eigenschaften von dessen Modellen animieren müssen, um eine 3D-Szene zu animieren. Es ist möglich, die Eigenschaften von primitiven Typen direkt zu animieren. In der Regel ist es aber einfacher, Transformationen zu animieren, die die Position oder die Darstellung von Modellen ändern. Da Transformationen können, um angewendet werden <xref:System.Windows.Media.Media3D.Model3DGroup> -Objekten sowie einzelne Modelle, es ist möglich, einen Satz von Animationen auf ein untergeordnetes Element des einer Model3DGroup und einen anderen Satz von Animationen auf eine Gruppe von untergeordneten Objekten anzuwenden. Sie können eine Vielzahl von visuellen Effekten erzielen, indem Sie die Eigenschaften der Beleuchtung Ihrer Szene animieren. Schließlich können Sie ggf. die Projektion selbst animieren, indem Sie die Kameraposition oder das Sichtfeld animieren. Hintergrundinformationen zum Zeitsteuerungs- und Animationssystem von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie in den Themen [Übersicht über Animationen](animation-overview.md), [Übersicht über Storyboards](storyboards-overview.md) und [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md).  
  
 Um ein Objekt in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu animieren, erstellen Sie eine Zeitachse, definieren Sie eine Animation (die im Zeitablauf eine tatsächliche Änderung einiger Eigenschaftswerte darstellt), und geben Sie die Eigenschaft an, auf die die Animation angewendet werden soll. Da alle Objekte in einem [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Szene sind untergeordnete Elemente des <xref:System.Windows.Controls.Viewport3D>, die Eigenschaften, die alle Animationen, die Sie in die Szene anwenden möchten, sind Eigenschaften von Viewport3D.  
  
 Angenommen, ein Modell soll an seiner Position als wackelnd angezeigt werden. Sie können entscheiden, gelten eine <xref:System.Windows.Media.Media3D.RotateTransform3D> , dem Modell und dessen Rotationsachse von einem Vektor zu einem anderen animieren. Das folgende Codebeispiel veranschaulicht die Anwendung einer Vector3DAnimation auf die Achseneigenschaft der Rotation3D-Klasse der Transformation unter der Annahme, dass RotateTransform3D eine der vielen Transformationen darstellt, die auf das Modell mit TransformGroup angewendet werden.  
  
 [!code-csharp[3doverview#3DOverview3DN1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>   
## <a name="add-3-d-content-to-the-window"></a>Hinzufügen von 3D-Inhalt zum Fenster  
 Um der Szene zu rendern, hinzufügen, Modelle und Lichter zu einer <xref:System.Windows.Media.Media3D.Model3DGroup>, legen Sie dann die <xref:System.Windows.Media.Media3D.Model3DGroup> als die <xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A> von einer <xref:System.Windows.Media.Media3D.ModelVisual3D>. Hinzufügen der <xref:System.Windows.Media.Media3D.ModelVisual3D> auf die <xref:System.Windows.Controls.Viewport3D.Children%2A> Auflistung von der <xref:System.Windows.Controls.Viewport3D>. Fügen Sie Kameras, um die <xref:System.Windows.Controls.Viewport3D> durch Festlegen seiner <xref:System.Windows.Controls.Viewport3D.Camera%2A> Eigenschaft.  
  
 Fügen Sie abschließend die <xref:System.Windows.Controls.Viewport3D> an das Fenster. Wenn die <xref:System.Windows.Controls.Viewport3D> enthalten ist, wie der Inhalt eines Layoutelements wie einem Zeichenbereich, Angeben der Größe der Viewport3D durch Festlegen seiner <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaften (geerbt von <xref:System.Windows.FrameworkElement>).  
  
 [!code-xaml[hostingwpfusercontrolinwf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Viewport3D>
- <xref:System.Windows.Media.Media3D.PerspectiveCamera>
- <xref:System.Windows.Media.Media3D.DirectionalLight>
- <xref:System.Windows.Media.Media3D.Material>
- [Übersicht über 3D-Transformationen](3-d-transformations-overview.md)
- [Maximieren der 3D-Leistung von WPF](maximize-wpf-3d-performance.md)
- [Themen zu Vorgehensweisen](3-d-graphics-how-to-topics.md)
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
