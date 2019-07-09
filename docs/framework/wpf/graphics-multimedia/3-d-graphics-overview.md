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
ms.openlocfilehash: 48f14ff145ad35dae3ba960191d34360cbec6173
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67664103"
---
# <a name="3-d-graphics-overview"></a>Übersicht über 3D-Grafiken
<a name="introduction"></a> Die 3-d-Funktion in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ermöglicht es Entwicklern, zeichnen, umwandeln und Animieren von 3D-Grafiken in sowohl Markup- und prozeduralem Code. Entwickler können 2D- und 3D-Grafik Grafiken, um umfassende Steuerelemente zu erstellen, komplexe Illustrationen von Daten bereitstellen oder verbessern die benutzerfreundlichkeit der Schnittstelle einer Anwendung kombinieren. 3-d-Unterstützung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dient nicht um eine voll funktionsfähige Spieleentwicklung Plattform bereitzustellen. Dieses Thema enthält eine Übersicht über 3D-Grafiken Funktionen in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Grafiksystem.  

<a name="threed_in_2d"></a>   
## <a name="3-d-in-a-2-d-container"></a>3D in einem 2D-Container  
 In Inhalte von 3D-Grafiken [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in ein Element gekapselt <xref:System.Windows.Controls.Viewport3D>, kann das Teil einer zweidimensionalen Elementstruktur sein. Das Grafiksystem behandelt <xref:System.Windows.Controls.Viewport3D> als ein zweidimensionales visuelles Objekt, in wie viele andere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. <xref:System.Windows.Controls.Viewport3D> fungiert als Fenster – ein Anzeigebereich – in eine dreidimensionale Szene. Genauer gesagt handelt es sich um eine Oberfläche, auf die eine 3D-Szene projiziert wird.  
  
 Verwenden Sie in einer herkömmlichen 2-D-Anwendung <xref:System.Windows.Controls.Viewport3D> wie andere Containerelement wie Raster oder Canvas.  Sie können zwar <xref:System.Windows.Controls.Viewport3D> mit andere 2-D-Objekte im selben szenegraphen, Sie 2D- und 3D-Grafik Objekte innerhalb durchdringen können keinem <xref:System.Windows.Controls.Viewport3D>.  In diesem Thema liegt der Schwerpunkt auf zum Zeichnen von 3D-Grafiken innerhalb der <xref:System.Windows.Controls.Viewport3D>.  
  
<a name="coord_space"></a>   
## <a name="3-d-coordinate-space"></a>3D-Koordinatenbereich  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Koordinatensystem für 2D-Grafiken befindet sich der Ursprung in der oberen linken Ecke des Renderingbereichs (in der Regel der Bildschirm). Im 2D-System verlaufen die positiven Werte der x-Achse nach rechts und die positiven Werte der y-Achse nach unten.  Im 3D-Koordinatensystem jedoch der Ursprung in der Mitte des Renderingbereichs positiven Werte der x-Achse nach rechts aber die positiven Werte der y-Achse nach oben und die z positive Achsenwerte nach außen vom Ursprung befindet , auf den Betrachter.  
  
 ![Koordinatensysteme](./media/coordsystem-1.png "CoordSystem-1")  
Darstellungen herkömmlicher 2D- und 3D-Koordinatensysteme  
  
 Der von diesen Achsen definierte Raum ist der feststehende Verweisrahmen für 3D-Objekte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Wenn Sie innerhalb dieses Raumes Modelle erstellen und Lichter und Kameras, um sie anzuzeigen, ist es hilfreich, diesen feststehenden Verweisrahmen oder „Weltenraum“ vom lokalen zu unterscheiden, den Sie beim Anwenden von Transformationen für jedes Modell erstellen. Beachten Sie außerdem, dass Objekte im Weltenraum je nach der Kamera und den Einstellungen völlig anders oder überhaupt nicht angezeigt werden können. Die Position der Kamera ändert aber nicht die Position von Objekten im Weltenraum.  
  
<a name="cameras"></a>   
## <a name="cameras-and-projections"></a>Kameras und Projektionen  
 Entwickler, die in 2-D arbeiten sind daran gewöhnt, zeichnende primitive Typen in einem zweidimensionalen Bildschirm positionieren. Bei der Erstellung einer 3D-Szene ist es wichtig zu beachten, dass Sie wirklich eine 2-D-Darstellung der 3D-Objekte erstellen. Da es sich bei eine 3D-Szene hängt von der Sicht des Betrachters aussieht, müssen Sie diese Perspektive angeben. Die <xref:System.Windows.Media.Media3D.Camera> Klasse können Sie diese Perspektive für eine 3D-Szene zu angeben.  
  
 Eine weitere Möglichkeit, zu verstehen, wie eine 3D-Szene dargestellt wird, auf einer 2-D-Oberfläche wird, die die Szene als eine Projektion auf die Ansichtsoberfläche beschrieben. Die <xref:System.Windows.Media.Media3D.ProjectionCamera> können Sie verschiedene Projektionen und deren Eigenschaften so ändern Sie die 3-d-Modellen angeben. Ein <xref:System.Windows.Media.Media3D.PerspectiveCamera> gibt eine Projektion an, die die Szene verkürzt.  Das heißt, die <xref:System.Windows.Media.Media3D.PerspectiveCamera> Fluchtpunktperspektive bereitstellt.  Sie können die Position der Kamera im Koordinatenbereich der Szene, die Richtung und das Sichtfeld der Kamera und ein Vektor angeben, der die Richtung „nach oben“ in der Szene definiert. Das folgende Diagramm veranschaulicht die <xref:System.Windows.Media.Media3D.PerspectiveCamera>die Projektion.  
  
 Die <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> und <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> Eigenschaften <xref:System.Windows.Media.Media3D.ProjectionCamera> schränkt den Bereich der Kameraprojektion. Da sich Kameras überall in der Szene befinden können, kann die Kamera auch innerhalb eines Modells oder sehr nah an einem Modell positioniert werden. Dies erschwert ordnungsgemäße die Unterscheidung von Objekten.  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> können Sie einen Mindestabstand zur Kamera angeben, jenseits derer keine Objekte gezeichnet werden.  Im Gegensatz dazu <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> ermöglicht die Angabe eine Entfernung von der Kamera, jenseits derer Objekte nicht gezeichnet werden werden, der sicherstellt, dass die Objekte zu weit weg, um erkannt zu werden nicht in der Szene enthalten sind.  
  
 ![Kamerasetup](./media/coordsystem-6.png "CoordSystem-6")  
Kameraposition  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera> Gibt eine orthogonale Projektion eines 3D-Modells verwendet, eine 2-D visuelle Oberfläche an. Wie andere Kameras gibt es eine Position, Blickrichtung und die Richtung „nach oben“ an. Im Gegensatz zu <xref:System.Windows.Media.Media3D.PerspectiveCamera>jedoch <xref:System.Windows.Media.Media3D.OrthographicCamera> beschreibt eine Projektion, die keine perspektivische Verkürzung enthält. Das heißt, <xref:System.Windows.Media.Media3D.OrthographicCamera> beschreibt ein Sichtfeld, dessen Seiten parallel, anstelle eines, dessen Seiten in einem Punkt der Kamera zu erfüllen. Die folgende Abbildung zeigt das gleiche Modell mithilfe von <xref:System.Windows.Media.Media3D.PerspectiveCamera> und <xref:System.Windows.Media.Media3D.OrthographicCamera>.  
  
 ![Orthografische und perspektivische Projektion](./media/camera-projections4.png "Camera_projections4")  
Perspektivische und orthografische Projektionen  
  
 Der folgende Code zeigt einige typische Kameraeinstellungen.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>   
## <a name="model-and-mesh-primitives"></a>Modell- und primitive Gittertypen  
  
 <xref:System.Windows.Media.Media3D.Model3D> ist die abstrakte Basisklasse, die ein generisches 3D-Objekt darstellt. Um eine 3D-Szene zu erstellen, benötigen Sie einige anzuzeigende Objekte und die Objekte, aus denen die szenengraph abgeleitet <xref:System.Windows.Media.Media3D.Model3D>. Derzeit den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt das Modellieren von Geometrien mit <xref:System.Windows.Media.Media3D.GeometryModel3D>. Die <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> -Eigenschaft dieses Modell nimmt einen primitiven gittertyp.  
  
 Um ein Modell zu erstellen, erstellen Sie zuerst einen primitiven Typen oder ein Gitter. Ein 3-d primitiver Typ ist eine Auflistung der Vertices, die eine 3-d-Einheit zu bilden. Die meisten 3D--Systeme bieten primitive Typen, die auf der einfachsten geschlossenen Figur modelliert: durch drei Vertices definiertes Dreieck.  Da die drei Punkte eines Dreiecks auf derselben Ebene liegen, können Sie weiterhin Dreiecke hinzufügen, um komplexere Formen, die Gitter genannt werden, zu modellieren.  
  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 3D-System bietet derzeit die <xref:System.Windows.Media.Media3D.MeshGeometry3D> -Klasse, sodass Sie jede beliebige Geometrie angeben; dies der Fall ist derzeit nicht unterstützt, die vordefinierte 3D-primitive Typen wie Kreise und kubische Formen. Erstellen einer <xref:System.Windows.Media.Media3D.MeshGeometry3D> durch Angabe einer Liste von dreieckvertices als dessen <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> Eigenschaft. Jeder Vertex wird angegeben, wie eine <xref:System.Windows.Media.Media3D.Point3D>.  (Geben Sie diese Eigenschaft in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] als eine Liste von Zahlen in Dreiergruppen an, die die Koordinaten der einzelnen Vertices darstellen.) Je nach Geometrie kann das Gitter aus mehreren Dreiecken bestehen, von denen einige dieselben Eckpunkte (Vertices) teilen. Um das Gitter ordnungsgemäß zu zeichnen, braucht [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Informationen darüber, welche Eckpunkte von welchen Dreiecken geteilt werden. Stellen Sie diese Informationen durch Angabe einer Liste der Dreiecksindizes mit der <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> Eigenschaft. Diese Liste gibt an, in dem die Punkte im angegebenen, Reihenfolge der <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> Liste ein Dreieck bestimmen.  
  
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
  
 Damit ein Gitter wie ein dreidimensionales Objekt aussieht, muss eine Textur darauf angewendet werden, die die von den Vertices und Dreiecken definierte Fläche abdeckt, sodass es beleuchtet und von der Kamera projiziert werden kann. In 2-D, verwenden Sie die <xref:System.Windows.Media.Brush> Klasse, um Bildschirmbereichen Farben, Muster, Farbverläufe oder andere visuelle Inhalte zuweisen.  Die Darstellung von 3D-Objekten ist jedoch eine Funktion des Beleuchtungsmodells und nicht nur des der Farbe oder ein Muster, die angewendet werden. Reale Objekte reflektieren Licht unterschiedlich, je nach der Qualität ihrer Oberflächen: glänzende und leuchtende Oberflächen sehen anders aus als raue oder matte Oberflächen, und einige Objekte scheinen Licht zu absorbieren, während andere leuchten. Sie können dieselben Pinsel anwenden auf 3D-Objekte, die Sie auf 2-D-Objekte anwenden können, aber sie kann nicht direkt angewendet.  
  
 Um die Eigenschaften einer Modelloberfläche zu definieren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet die <xref:System.Windows.Media.Media3D.Material> abstrakte Klasse. Die konkreten Unterklassen von „Material“ bestimmen einige der Darstellungseigenschaften der Modelloberfläche und stellen jeweils eine Pinseleigenschaft bereit, der Sie ein SolidColorBrush, TileBrush oder VisualBrush übergeben können.  
  
- <xref:System.Windows.Media.Media3D.DiffuseMaterial> Gibt an, dass der Pinsel auf das Modell angewendet wird, als wäre das Modell diffus beleuchtet. Die Verwendung von DiffuseMaterial ähnelt der Pinsel direkt auf 2-D-Modelle; Modell-Oberflächen Licht Modelloberflächen nicht wieder.  
  
- <xref:System.Windows.Media.Media3D.SpecularMaterial> Gibt an, dass der Pinsel für das Modell angewendet wird, als wäre die Modelloberfläche oder glänzend und kann Glanzlichter zu reflektieren. Sie können den Grad, wird die Textur diese reflektierende Qualität oder "abzuheben," vorschlagen, festlegen, durch die Angabe eines Werts für die <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A> Eigenschaft.  
  
- <xref:System.Windows.Media.Media3D.EmissiveMaterial> können Sie angeben, dass die Textur angewendet wird, als ob das Modell Licht abgibt, die Farbe des Pinsels. Dies macht das Modell nicht zu Licht. Schatteneffekte werden jedoch anders dargestellt, als mit DiffuseMaterial oder SpecularMaterial.  
  
 Zur Verbesserung der Leistung die Rückseiten von einem <xref:System.Windows.Media.Media3D.GeometryModel3D> (diese Seiten, die aus der Ansicht sind, da sie auf der entgegengesetzten Seite des Modells mit der Kamera sind) aus der Szene herausgefiltert werden.  Angeben einer <xref:System.Windows.Media.Media3D.Material> legen Sie zum Anwenden von auf die Rückseite eines Modells, wie eine Ebene des Modells <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> Eigenschaft.  
  
 Um einige Oberflächenqualitäten zu erzielen, z.B. ein Leuchten oder reflektierende Effekte, können Sie nacheinander mehrere unterschiedliche Pinsel auf ein Modell anwenden. Sie können verschiedene Materialien mithilfe wieder und Anwenden der <xref:System.Windows.Media.Media3D.MaterialGroup> Klasse. Die untergeordneten Elemente von MaterialGroup werden nacheinander in mehreren Renderingdurchläufen angewendet.  
  
 Der folgende Code veranschaulicht, wie eine Volltonfarbe und eine Zeichnung als Pinsel auf 3D-Modelle angewendet.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN5](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  
 [!code-xaml[3doverview#3DOverview3DN9](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
  
 [!code-csharp[3doverview#3DOverview3DN8](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
 [!code-vb[3doverview#3DOverview3DN8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>   
## <a name="illuminating-the-scene"></a>Beleuchten der Szene  
 Lichter in 3D-Grafiken zu machen, was Sie auch in der realen Welt machen: sie beleuchten Oberflächen. Genauer gesagt bestimmen Lichter, welcher Teil einer Szene auch Teil der Projektion ist. Helle Objekte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erzeugen eine Vielzahl von Licht- und Schatteneffekten und werden nach dem Verhalten verschiedener realer Lichter modelliert. Sie müssen mindestens ein Licht in Ihre Szene aufnehmen, andernfalls sind keine Modelle sichtbar.  
  
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
 Wenn Sie Modelle erstellen, verfügen diese über eine bestimmte Position in der Szene. Um die Position dieser Modelle in der Szene zu verändern, sie zu drehen oder ihre Größe zu ändern, sollten Sie nicht die Vertices ändern, die die Modelle selbst definieren.  Wenden Sie stattdessen wie in 2D-Modellen Transformationen auf Modelle an.  
  
 Jedes Modellobjekt verfügt über eine <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> Eigenschaft mit dem verschieben, neu ausrichten oder Ändern der Größe des Modells.  Wenn Sie eine Transformation anwenden, versetzen Sie alle Punkte des Modells durch den in der Transformation angegebenen Vektor oder Wert. Sie haben also den Koordinatenbereich transformiert, in dem das Modell definiert ist (Modellraum), aber Sie haben noch nicht die Werte geändert, die die Geometrie des Modells im Koordinatensystem der gesamten Szene („Weltenraum“) ausmachen.  
  
 Weitere Informationen zum Transformieren von Modellen finden Sie unter [Übersicht über 3D-Transformationen](3-d-transformations-overview.md).  
  
<a name="animations"></a>   
## <a name="animating-models"></a>Animieren von Modellen  
 Die 3D-Implementierung von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gehört dem gleichen Zeitsteuerungs- und Animationssystem an wie die 2D-Grafiken. Das heißt, dass Sie die Eigenschaften von dessen Modellen animieren müssen, um eine 3D-Szene zu animieren. Es ist möglich, die Eigenschaften von primitiven Typen direkt zu animieren. In der Regel ist es aber einfacher, Transformationen zu animieren, die die Position oder die Darstellung von Modellen ändern. Da Transformationen können, um angewendet werden <xref:System.Windows.Media.Media3D.Model3DGroup> -Objekten sowie einzelne Modelle, es ist möglich, einen Satz von Animationen auf ein untergeordnetes Element des einer Model3DGroup und einen anderen Satz von Animationen auf eine Gruppe von untergeordneten Objekten anzuwenden. Sie können eine Vielzahl von visuellen Effekten erzielen, indem Sie die Eigenschaften der Beleuchtung Ihrer Szene animieren. Schließlich können Sie ggf. die Projektion selbst animieren, indem Sie die Kameraposition oder das Sichtfeld animieren. Hintergrundinformationen zum Zeitsteuerungs- und Animationssystem von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie in den Themen [Übersicht über Animationen](animation-overview.md), [Übersicht über Storyboards](storyboards-overview.md) und [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md).  
  
 Um ein Objekt in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu animieren, erstellen Sie eine Zeitachse, definieren Sie eine Animation (die im Zeitablauf eine tatsächliche Änderung einiger Eigenschaftswerte darstellt), und geben Sie die Eigenschaft an, auf die die Animation angewendet werden soll. Da alle Objekte in einer 3D-Szene untergeordnete Elemente sind <xref:System.Windows.Controls.Viewport3D>, die Eigenschaften, die alle Animationen, die Sie in die Szene anwenden möchten, sind Eigenschaften von Viewport3D.  
  
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
