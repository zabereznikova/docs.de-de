---
title: 3D-Grafikübersicht
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D graphics [WPF]
- graphics [WPF], 3D
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
ms.openlocfilehash: e4918f7737bbe57a4f29c6c5cff1099f4f21674b
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291815"
---
# <a name="3d-graphics-overview"></a>3D-Grafikübersicht
<a name="introduction"></a>Die 3D-Funktionalität in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ermöglicht Entwicklern das Zeichnen, Transformieren und Animieren von 3D-Grafiken sowohl in Markup- als auch in Prozedurcode. Entwickler können 2D- und 3D-Grafiken kombinieren, um umfangreiche Steuerelemente zu erstellen, komplexe Illustrationen von Daten bereitzustellen oder die Benutzerfreundlichkeit der Benutzeroberfläche einer Anwendung zu verbessern. Die 3D-Unterstützung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist nicht so konzipiert, dass sie eine voll funktionsfähige Spielentwicklungsplattform bietet. Dieses Thema bietet einen Überblick über [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die 3D-Funktionalität im Grafiksystem.  

<a name="threed_in_2d"></a>
## <a name="3d-in-a-2d-container"></a>3D in einem 2D-Container  
 3D-Grafikinhalte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in sind in einem <xref:System.Windows.Controls.Viewport3D>Element gekapselt, das an der zweidimensionalen Elementstruktur beteiligt werden kann. Das Grafiksystem <xref:System.Windows.Controls.Viewport3D> behandelt als zweidimensionales visuelles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Element wie viele andere in . <xref:System.Windows.Controls.Viewport3D>funktioniert als Fenster – ein Ansichtsfenster – in eine dreidimensionale Szene. Genauer gesagt handelt es sich um eine Oberfläche, auf die eine 3D-Szene projiziert wird.  
  
 Verwenden Sie <xref:System.Windows.Controls.Viewport3D> in einer herkömmlichen 2D-Anwendung wie bei einem anderen Containerelement wie Grid oder Canvas.  Obwohl Sie <xref:System.Windows.Controls.Viewport3D> mit anderen 2D-Zeichnungsobjekten im gleichen Szenendiagramm verwenden können, können <xref:System.Windows.Controls.Viewport3D>Sie 2D- und 3D-Objekte nicht in eine durchdringen.  In diesem Thema wird das Zeichnen von <xref:System.Windows.Controls.Viewport3D>3D-Grafiken innerhalb der behandelt.  
  
<a name="coord_space"></a>
## <a name="3d-coordinate-space"></a>3D-Koordinatenraum  
 Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Koordinatensystem für 2D-Grafiken lokalisiert den Ursprung in der oberen linken Seite des Renderingbereichs (in der Regel der Bildschirm). Im 2D-System gehen positive x-Achsenwerte nach rechts und positive y-Achsenwerte gehen nach unten.  Im 3D-Koordinatensystem befindet sich der Ursprung jedoch in der Mitte des Rendering-Bereichs, wobei positive x-Achsenwerte nach rechts, aber positive y-Achsenwerte nach oben gehen und positive Z-Achsenwerte vom Ursprung nach außen gehen. dem Betrachter zuzuführen.  
  
 ![Koordinatensysteme](./media/coordsystem-1.png "CoordSystem-1")  
Herkömmliche 2D- und 3D-Koordinatensystemdarstellungen  
  
 Der durch diese Achsen definierte Raum ist der stationäre Bezugsrahmen für 3D-Objekte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Wenn Sie innerhalb dieses Raumes Modelle erstellen und Lichter und Kameras, um sie anzuzeigen, ist es hilfreich, diesen feststehenden Verweisrahmen oder „Weltenraum“ vom lokalen zu unterscheiden, den Sie beim Anwenden von Transformationen für jedes Modell erstellen. Beachten Sie außerdem, dass Objekte im Weltenraum je nach der Kamera und den Einstellungen völlig anders oder überhaupt nicht angezeigt werden können. Die Position der Kamera ändert aber nicht die Position von Objekten im Weltenraum.  
  
<a name="cameras"></a>
## <a name="cameras-and-projections"></a>Kameras und Projektionen  
 Entwickler, die in 2D arbeiten, sind daran gewöhnt, Zeichnungsprimitive auf einem zweidimensionalen Bildschirm zu positionieren. Wenn Sie eine 3D-Szene erstellen, sollten Sie sich daran erinnern, dass Sie wirklich eine 2D-Darstellung von 3D-Objekten erstellen. Da eine 3D-Szene je nach Sicht des Zuschauers anders aussieht, müssen Sie diesen Blickwinkel angeben. Mit <xref:System.Windows.Media.Media3D.Camera> der Klasse können Sie diesen Blickwinkel für eine 3D-Szene angeben.  
  
 Eine andere Möglichkeit, zu verstehen, wie eine 3D-Szene auf einer 2D-Oberfläche dargestellt wird, besteht darin, die Szene als Projektion auf die Anzeigefläche zu beschreiben. Mit <xref:System.Windows.Media.Media3D.ProjectionCamera> der können Sie verschiedene Projektionen und deren Eigenschaften angeben, um zu ändern, wie der Zuschauer 3D-Modelle sieht. A <xref:System.Windows.Media.Media3D.PerspectiveCamera> gibt eine Projektion an, die die Szene verkürzt.  Mit anderen Worten, die <xref:System.Windows.Media.Media3D.PerspectiveCamera> Perspektive des Fluchtpunktes.  Sie können die Position der Kamera im Koordinatenbereich der Szene, die Richtung und das Sichtfeld der Kamera und ein Vektor angeben, der die Richtung „nach oben“ in der Szene definiert. Das folgende Diagramm <xref:System.Windows.Media.Media3D.PerspectiveCamera>veranschaulicht die Projektion von '.  
  
 Der <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> und <xref:System.Windows.Media.Media3D.ProjectionCamera> die Eigenschaften des Begrenzten bereichs der Kameraprojektion. Da sich Kameras überall in der Szene befinden können, kann die Kamera auch innerhalb eines Modells oder sehr nah an einem Modell positioniert werden. Dies erschwert ordnungsgemäße die Unterscheidung von Objekten.  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A>können Sie einen Mindestabstand zur Kamera angeben, ab dem keine Objekte gezeichnet werden.  Umgekehrt können <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> Sie einen Abstand von der Kamera angeben, ab dem keine Objekte gezeichnet werden sollen, wodurch sichergestellt wird, dass Objekte, die zu weit entfernt sind, um erkennbar zu sein, nicht in die Szene einbezogen werden.  
  
 ![Kamerasetup](./media/coordsystem-6.png "CoordSystem-6")  
Kameraposition  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera>gibt eine orthogonale Projektion eines 3D-Modells auf eine visuelle 2D-Oberfläche an. Wie andere Kameras gibt es eine Position, Blickrichtung und die Richtung „nach oben“ an. Im <xref:System.Windows.Media.Media3D.PerspectiveCamera>Gegensatz <xref:System.Windows.Media.Media3D.OrthographicCamera> zu beschreibt jedoch eine Projektion, die keine perspektivische Verkürzung enthält. Mit anderen <xref:System.Windows.Media.Media3D.OrthographicCamera> Worten, beschreibt eine Anzeigebox, deren Seiten parallel sind, anstatt eine, deren Seiten sich an einem Punkt an der Kamera treffen. Die folgende Abbildung zeigt dasselbe <xref:System.Windows.Media.Media3D.PerspectiveCamera> <xref:System.Windows.Media.Media3D.OrthographicCamera>Modell wie mit und angezeigt.  
  
 ![Orthografische und perspektivische Projektion](./media/camera-projections4.png "Camera_projections4")  
Perspektivische und orthografische Projektionen  
  
 Der folgende Code zeigt einige typische Kameraeinstellungen.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>
## <a name="model-and-mesh-primitives"></a>Modell- und primitive Gittertypen  
  
 <xref:System.Windows.Media.Media3D.Model3D>ist die abstrakte Basisklasse, die ein generisches 3D-Objekt darstellt. Zum Erstellen einer 3D-Szene benötigen Sie einige Objekte zum Anzeigen, und <xref:System.Windows.Media.Media3D.Model3D>die Objekte, aus denen das Szenendiagramm besteht, stammen von . Derzeit unterstützt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Modellierung von <xref:System.Windows.Media.Media3D.GeometryModel3D>Geometrien mit . Die <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> Eigenschaft dieses Modells nimmt ein Netzprimitive.  
  
 Um ein Modell zu erstellen, erstellen Sie zuerst einen primitiven Typen oder ein Gitter. Ein 3D-Primitiv ist eine Sammlung von Scheitelpunkten, die eine einzelne 3D-Entität bilden. Die meisten 3D-Systeme bieten Primitive, die der einfachsten geschlossenen Figur nachempfunden sind: ein Dreieck, das durch drei Scheitelpunkte definiert ist.  Da die drei Punkte eines Dreiecks auf derselben Ebene liegen, können Sie weiterhin Dreiecke hinzufügen, um komplexere Formen, die Gitter genannt werden, zu modellieren.  
  
 Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 3D-System <xref:System.Windows.Media.Media3D.MeshGeometry3D> stellt derzeit die Klasse bereit, mit der Sie jede Geometrie angeben können. Es unterstützt derzeit keine vordefinierten 3D-Primitive wie Kugeln und kubische Formen. Beginnen Sie <xref:System.Windows.Media.Media3D.MeshGeometry3D> mit dem Erstellen einer, indem <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> Sie eine Liste von Dreiecksscheitelpunkten als Eigenschaft angeben. Jeder Scheitelpunkt <xref:System.Windows.Media.Media3D.Point3D>wird als angegeben.  (Geben [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]Sie diese Eigenschaft als Liste von Zahlen an, die in Dreier gruppiert sind und die Koordinaten jedes Scheitelpunkts darstellen.) Je nach Geometrie kann das Netz aus vielen Dreiecken bestehen, von denen einige dieselben Ecken (Scheitelpunkte) haben. Um das Gitter ordnungsgemäß zu zeichnen, braucht [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Informationen darüber, welche Eckpunkte von welchen Dreiecken geteilt werden. Sie stellen diese Informationen bereit, indem Sie <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> eine Liste der Dreiecksindizes mit der Eigenschaft angeben. Diese Liste gibt die Reihenfolge an, <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> in der die in der Liste angegebenen Punkte ein Dreieck bestimmen.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN3](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 Im vorherigen Beispiel <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> gibt die Liste acht Scheitelpunkte an, um ein würfelförmiges Netz zu definieren. Die <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> Eigenschaft gibt eine Liste mit zwölf Gruppen mit drei Indizes an.  Jede Zahl in der Liste bezieht <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> sich auf einen Offset in die Liste.  Die ersten drei Scheitelpunkte, <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> die in der Liste angegeben werden, sind z. B. (1,1,0), (0,1,0) und (0,0,0). Die ersten drei Indizes, die in der <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> Liste angegeben werden, sind 0, 2 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> und 1, die dem ersten, dritten und zweiten Punkt in der Liste entsprechen. Daher setzt sich das erste Dreieck, aus dem das Würfelmodells besteht, aus (1,1,0), (0,1,0), (0,0,0) zusammen. Die verbleibenden elf Dreiecke werden ähnlich ermittelt.  
  
 Sie können das Modell weiter definieren, <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> indem Sie Werte für die und Eigenschaften angeben.  Um die Oberfläche des Modells zu rendern, benötigt das Grafiksystem Informationen darüber, in welche Richtung die Oberfläche bei jedem gegebenen Dreieck zeigt. Diese Informationen werden dazu verwendet, die Beleuchtung für das Modell zu berechnen: Flächen, die einer Lichtquelle direkt zugewendet sind, erscheinen heller als solche, die von Licht abgewandt sind. Obwohl [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Standardnormalvektoren mithilfe der Positionskoordinaten ermitteln kann, können Sie auch verschiedene Normalvektoren angeben, um sich der Darstellung von gekrümmten Oberflächen zu nähern.  
  
 Die <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> Eigenschaft gibt eine <xref:System.Windows.Point>Auflistung von s an, die dem Grafiksystem mitteilen, wie die Koordinaten zugeordnet werden, die bestimmen, wie eine Textur zu den Scheitelpunkten des Netzes gezeichnet wird. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>werden als Wert zwischen Null und 1 angegeben, einschließlich.  Wie bei <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> der Eigenschaft kann das Grafiksystem standardtexturkoordinaten berechnen, sie können jedoch verschiedene Texturkoordinaten festlegen, um die Zuordnung einer Textur zu steuern, die z. B. einen Teil eines wiederholten Musters enthält. Weitere Informationen zu Texturkoordinaten finden Sie in den nachfolgenden Themen oder im Managed Direct3D SDK.  
  
 Im folgenden Beispiel wird veranschaulicht, wie eine Seite des Würfelmodells in prozeduralem Code erstellt wird. Sie können den gesamten Cube als einzelne GeometryModel3D zeichnen. In diesem Beispiel wird die Fläche des Cubes als eigenständiges Modell gezeichnet, um später separate Texturen auf jede Fläche anzuwenden.  
  
 [!code-csharp[3doverview#3DOverview3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>'
## <a name="applying-materials-to-the-model"></a>Anwenden von Materialien auf das Modell  
  
 Damit ein Gitter wie ein dreidimensionales Objekt aussieht, muss eine Textur darauf angewendet werden, die die von den Vertices und Dreiecken definierte Fläche abdeckt, sodass es beleuchtet und von der Kamera projiziert werden kann. In 2D verwenden <xref:System.Windows.Media.Brush> Sie die Klasse, um Farben, Muster, Farbverläufe oder andere visuelle Inhalte auf Bereiche des Bildschirms anzuwenden.  Das Erscheinungsbild von 3D-Objekten ist jedoch eine Funktion des Beleuchtungsmodells, nicht nur der Farbe oder des Musters, die auf sie angewendet werden. Reale Objekte reflektieren Licht unterschiedlich, je nach der Qualität ihrer Oberflächen: glänzende und leuchtende Oberflächen sehen anders aus als raue oder matte Oberflächen, und einige Objekte scheinen Licht zu absorbieren, während andere leuchten. Sie können dieselben Pinsel auf 3D-Objekte anwenden, die Sie auf 2D-Objekte anwenden können, aber Sie können sie nicht direkt anwenden.  
  
 Um die Eigenschaften der Oberfläche eines [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Modells <xref:System.Windows.Media.Media3D.Material> zu definieren, wird die abstrakte Klasse verwendet. Die konkreten Unterklassen von „Material“ bestimmen einige der Darstellungseigenschaften der Modelloberfläche und stellen jeweils eine Pinseleigenschaft bereit, der Sie ein SolidColorBrush, TileBrush oder VisualBrush übergeben können.  
  
- <xref:System.Windows.Media.Media3D.DiffuseMaterial>gibt an, dass der Pinsel auf das Modell angewendet wird, als ob dieses Modell diffus beleuchtet würde. Die Verwendung von DiffuseMaterial ähnelt am ehesten der Verwendung von Pinseln direkt auf 2D-Modellen; Modellflächen reflektieren das Licht nicht wie glänzend.  
  
- <xref:System.Windows.Media.Media3D.SpecularMaterial>gibt an, dass der Pinsel auf das Modell angewendet wird, als ob die Oberfläche des Modells hart oder glänzend wäre und in der Lage wäre, Hervorhebungen widerzuspiegeln. Sie können den Grad festlegen, in dem die Textur diese reflektierende Qualität oder <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A> "Glanz" suggeriert, indem Sie einen Wert für die Eigenschaft angeben.  
  
- <xref:System.Windows.Media.Media3D.EmissiveMaterial>Können Sie angeben, dass die Textur so angewendet wird, als würde das Modell Licht aussenden, das der Farbe des Pinsels entspricht. Dies macht das Modell nicht zu Licht. Schatteneffekte werden jedoch anders dargestellt, als mit DiffuseMaterial oder SpecularMaterial.  
  
 Für eine bessere Leistung werden <xref:System.Windows.Media.Media3D.GeometryModel3D> die Rückseiten eines (jene Gesichter, die nicht sichtbar sind, weil sie sich auf der gegenüberliegenden Seite des Modells von der Kamera befinden) von der Szene gekeult.  Um eine <xref:System.Windows.Media.Media3D.Material> anzugeben, die auf die Rückseite eines Modells wie <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> eine Ebene angewendet werden soll, legen Sie die Eigenschaft des Modells fest.  
  
 Um einige Oberflächenqualitäten zu erzielen, z.B. ein Leuchten oder reflektierende Effekte, können Sie nacheinander mehrere unterschiedliche Pinsel auf ein Modell anwenden. Sie können mehrere Materialien anwenden und <xref:System.Windows.Media.Media3D.MaterialGroup> wiederverwenden, indem Sie die Klasse verwenden. Die untergeordneten Elemente von MaterialGroup werden nacheinander in mehreren Renderingdurchläufen angewendet.  
  
 Die folgenden Codebeispiele zeigen, wie Sie eine Volltonfarbe und eine Zeichnung als Pinsel auf 3D-Modelle anwenden.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN5](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  ' [!code-xaml[3doverview#3DOverview3DN9](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
 ' [!code-csharp[3doverview#3DOverview3DN8](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
  [!code-vb[3doverview#3DOverview3DN8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>
## <a name="illuminating-the-scene"></a>Beleuchten der Szene  
 Lichter in 3D-Grafiken tun, was Lichter in der realen Welt tun: Sie machen Oberflächen sichtbar. Genauer gesagt bestimmen Lichter, welcher Teil einer Szene auch Teil der Projektion ist. Helle Objekte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erzeugen eine Vielzahl von Licht- und Schatteneffekten und werden nach dem Verhalten verschiedener realer Lichter modelliert. Fügen Sie mindestens ein Licht in Ihre Szene ein, oder es sind keine Modelle sichtbar.  
  
 Die folgenden Leuchten stammen aus <xref:System.Windows.Media.Media3D.Light>der Basisklasse:  
  
- <xref:System.Windows.Media.Media3D.AmbientLight>: Bietet Umgebungsbeleuchtung, die alle Objekte unabhängig von ihrer Position oder Ausrichtung gleichmäßig beleuchtet.  
  
- <xref:System.Windows.Media.Media3D.DirectionalLight>: Leuchtet wie eine entfernte Lichtquelle.  Richtungslichter haben <xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A> eine angegebene Vector3D, aber keine angegebene Position.  
  
- <xref:System.Windows.Media.Media3D.PointLight>: Leuchtet wie eine nahegelegene Lichtquelle. PointLights verfügen über eine Position und senden Licht von dieser Position aus. Objekte in der Szene werden je nach deren Position und Abstand von der Lichtquelle beleuchtet. <xref:System.Windows.Media.Media3D.PointLightBase>macht eine <xref:System.Windows.Media.Media3D.PointLightBase.Range%2A> Eigenschaft frei, die einen Abstand bestimmt, ab dem Modelle nicht durch das Licht beleuchtet werden. PointLight setzt auch Dämpfungseigenschaften aus, die bestimmen, wie die Intensität des Lichts über die Entfernung abnimmt. Sie können die konstante, lineare oder quadratische Interpolationen für die Lichtabnahme angeben.  
  
- <xref:System.Windows.Media.Media3D.SpotLight>: Erbt <xref:System.Windows.Media.Media3D.PointLight>von . Scheinwerfer beleuchten wie PointLight und weisen sowohl eine Position als auch eine Richtung auf. Sie projizieren Licht in einer <xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A> kegelförmigen Fläche, die durch und <xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A> Eigenschaften festgelegt wird, in Grad angegeben.  
  
 Lichtquellen <xref:System.Windows.Media.Media3D.Model3D> sind Objekte, sodass Sie Lichteigenschaften transformieren und animieren können, einschließlich Position, Farbe, Richtung und Reichweite.  
  
 [!code-xaml[hittest3d#HitTest3D3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>
## <a name="transforming-models"></a>Transformieren von Modellen  
 Wenn Sie Modelle erstellen, verfügen diese über eine bestimmte Position in der Szene. Um die Position dieser Modelle in der Szene zu verändern, sie zu drehen oder ihre Größe zu ändern, sollten Sie nicht die Vertices ändern, die die Modelle selbst definieren.  Stattdessen wenden Sie, genau wie in 2D, Transformationen auf Modelle an.  
  
 Jedes Modellobjekt <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> verfügt über eine Eigenschaft, mit der Sie das Modell verschieben, neu ausrichten oder die Größe ändern können.  Wenn Sie eine Transformation anwenden, versetzen Sie alle Punkte des Modells durch den in der Transformation angegebenen Vektor oder Wert. Sie haben also den Koordinatenbereich transformiert, in dem das Modell definiert ist (Modellraum), aber Sie haben noch nicht die Werte geändert, die die Geometrie des Modells im Koordinatensystem der gesamten Szene („Weltenraum“) ausmachen.  
  
 Weitere Informationen zum Transformieren von Modellen finden Sie unter [3D-Transformationsübersicht](3-d-transformations-overview.md).  
  
<a name="animations"></a>
## <a name="animating-models"></a>Animieren von Modellen  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 3D-Implementierung ist teils im gleichen Timing- und Animationssystem wie 2D-Grafiken. Mit anderen Worten, um eine 3D-Szene zu animieren, animieren Sie die Eigenschaften ihrer Modelle. Es ist möglich, die Eigenschaften von primitiven Typen direkt zu animieren. In der Regel ist es aber einfacher, Transformationen zu animieren, die die Position oder die Darstellung von Modellen ändern. Da Transformationen sowohl <xref:System.Windows.Media.Media3D.Model3DGroup> auf Objekte als auch auf einzelne Modelle angewendet werden können, ist es möglich, einen Satz von Animationen auf ein untergeordnetes Element einer Model3DGroup und einen anderen Satz von Animationen auf eine Gruppe von untergeordneten Objekten anzuwenden. Sie können eine Vielzahl von visuellen Effekten erzielen, indem Sie die Eigenschaften der Beleuchtung Ihrer Szene animieren. Schließlich können Sie ggf. die Projektion selbst animieren, indem Sie die Kameraposition oder das Sichtfeld animieren. Hintergrundinformationen zum Zeitsteuerungs- und Animationssystem von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie in den Themen [Übersicht über Animationen](animation-overview.md), [Übersicht über Storyboards](storyboards-overview.md) und [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md).  
  
 Um ein Objekt in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu animieren, erstellen Sie eine Zeitachse, definieren Sie eine Animation (die im Zeitablauf eine tatsächliche Änderung einiger Eigenschaftswerte darstellt), und geben Sie die Eigenschaft an, auf die die Animation angewendet werden soll. Da alle Objekte in einer 3D-Szene untergeordnete Objekte <xref:System.Windows.Controls.Viewport3D>sind, sind die Eigenschaften, auf die eine Animation abzielt, die Sie auf die Szene anwenden möchten, Eigenschaften von Viewport3D.  
  
 Angenommen, ein Modell soll an seiner Position als wackelnd angezeigt werden. Sie können eine <xref:System.Windows.Media.Media3D.RotateTransform3D> auf das Modell anwenden und die Achse seiner Drehung von einem Vektor zu einem anderen animieren. Das folgende Codebeispiel veranschaulicht die Anwendung einer Vector3DAnimation auf die Achseneigenschaft der Rotation3D-Klasse der Transformation unter der Annahme, dass RotateTransform3D eine der vielen Transformationen darstellt, die auf das Modell mit TransformGroup angewendet werden.  
  
 [!code-csharp[3doverview#3DOverview3DN1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>
## <a name="add-3d-content-to-the-window"></a>Hinzufügen von 3D-Inhalten zum Fenster  
 Um die Szene zu rendern, <xref:System.Windows.Media.Media3D.Model3DGroup>fügen Sie <xref:System.Windows.Media.Media3D.Model3DGroup> Modelle <xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A> und <xref:System.Windows.Media.Media3D.ModelVisual3D>Lichtquellen zu einem hinzu, und legen Sie dann die als von an fest. Fügen <xref:System.Windows.Media.Media3D.ModelVisual3D> Sie <xref:System.Windows.Controls.Viewport3D.Children%2A> die zur <xref:System.Windows.Controls.Viewport3D>Auflistung der hinzu. Fügen Sie <xref:System.Windows.Controls.Viewport3D> Kameras hinzu, indem Sie die Eigenschaft festlegen. <xref:System.Windows.Controls.Viewport3D.Camera%2A>  
  
 Fügen Sie <xref:System.Windows.Controls.Viewport3D> die schließlich zum Fenster hinzu. Wenn <xref:System.Windows.Controls.Viewport3D> der als Inhalt eines Layoutelements wie Canvas enthalten ist, geben Sie <xref:System.Windows.FrameworkElement.Height%2A> die <xref:System.Windows.FrameworkElement.Width%2A> Größe des <xref:System.Windows.FrameworkElement>Viewport3D an, indem Sie seine und Eigenschaften festlegen (von geerbt).  
  
 [!code-xaml[hostingwpfusercontrolinwf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Viewport3D>
- <xref:System.Windows.Media.Media3D.PerspectiveCamera>
- <xref:System.Windows.Media.Media3D.DirectionalLight>
- <xref:System.Windows.Media.Media3D.Material>
- [3D-Transformationen Übersicht](3-d-transformations-overview.md)
- [Maximieren der 3D-Leistung von WPF](maximize-wpf-3d-performance.md)
- [Gewusst wie-Themen](3-d-graphics-how-to-topics.md)
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
