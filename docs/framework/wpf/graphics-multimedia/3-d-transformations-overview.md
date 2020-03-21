---
title: 3D-Transformationen Übersicht
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D transformations
- transformations [WPF], 3D
ms.assetid: e45e555d-ac1e-4b36-aced-e433afe7f27f
ms.openlocfilehash: 0efd6d247f23760c878c82cc92e99f1b83c1b9d2
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112348"
---
# <a name="3d-transformations-overview"></a>3D-Transformationen Übersicht
In diesem Thema wird beschrieben, wie Transformationen auf 3D-Modelle im [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Grafiksystem angewendet werden. Mit Transformationen können Entwickler die Position und Größe von Modellen ändern und sie neu ausrichten, ohne die Basiswerte zu verändern, die sie definieren.  

## <a name="3d-coordinate-space"></a>3D-Koordinatenraum  
 3D-Grafikinhalte [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] in sind in einem <xref:System.Windows.Controls.Viewport3D>Element gekapselt, das an der zweidimensionalen Elementstruktur beteiligt werden kann. Das Grafiksystem behandelt Viewport3D als ein zweidimensionales visuelles Objekt, wie viele andere auch in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Viewport3D fungiert als Fenster – ein Anzeigebereich – in eine dreidimensionale Szene. Genauer gesagt handelt es sich um eine Oberfläche, auf die eine 3D-Szene projiziert wird.  Obwohl Sie Viewport3D mit anderen 2D-Zeichnungsobjekten im gleichen Szenendiagramm verwenden können, können Sie 2D- und 3D-Objekte nicht in ein Viewport3D einschneiden. In der folgenden Erläuterung ist der beschriebene Koordinatenraum im Viewport3D-Element enthalten.  
  
 Das [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Koordinatensystem für 2D-Grafiken lokalisiert den Ursprung in der oberen linken Seite der Renderfläche (in der Regel der Bildschirm). Im 2D-System gehen positive x-Achsenwerte nach rechts und positive y-Achsenwerte gehen nach unten. Im 3D-Koordinatensystem befindet sich der Ursprung jedoch in der Mitte des Bildschirms, wobei positive x-Achsenwerte nach rechts, aber positive y-Achsenwerte nach oben gehen und positive Z-Achsenwerte vom Ursprung nach außen in Richtung den Betrachter.  
  
 ![Koordinatensysteme](./media/coordsystem-1.png "CoordSystem-1")  
Vergleich der Koordinatensysteme  
  
 Der durch diese Achsen definierte Raum ist der stationäre Bezugsrahmen für 3D-Objekte in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Wenn Sie innerhalb dieses Raumes Modelle erstellen und Lichter und Kameras, um sie anzuzeigen, ist es hilfreich, diesen feststehenden Verweisrahmen oder „Weltenraum“ vom lokalen zu unterscheiden, den Sie beim Anwenden von Transformationen für jedes Modell erstellen. Beachten Sie außerdem, dass Objekte im Weltenraum je nach der Kamera und den Einstellungen völlig anders oder überhaupt nicht angezeigt werden können. Die Position der Kamera ändert aber nicht die Position von Objekten im Weltenraum.  
  
## <a name="transforming-models"></a>Transformieren von Modellen  
 Wenn Sie Modelle erstellen, verfügen diese über eine bestimmte Position in der Szene. Um die Position dieser Modelle in der Szene zu verändern, sie zu drehen oder ihre Größe zu ändern, sollten Sie nicht die Vertices ändern, die die Modelle selbst definieren. Stattdessen wenden Sie, genau wie in 2D, Transformationen auf Modelle an.  
  
 Jedes Modellobjekt <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> verfügt über eine Eigenschaft, mit der Sie das Modell verschieben, neu ausrichten oder die Größe ändern können. Wenn Sie eine Transformation anwenden, versetzen Sie alle Punkte des Modells um den in der Transformation angegebenen Vektor oder Wert. Sie haben also den Koordinatenbereich transformiert, in dem das Modell definiert ist (Modellraum), aber Sie haben noch nicht die Werte geändert, die die Geometrie des Modells im Koordinatensystem der gesamten Szene („Weltenraum“) ausmachen.  
  
## <a name="translation-transformations"></a>Übersetzungstransformationen  
 3D-Transformationen erben von der <xref:System.Windows.Media.Media3D.Transform3D>abstrakten Basisklasse; Dazu gehören die affinetransformationsklassen <xref:System.Windows.Media.Media3D.TranslateTransform3D>, <xref:System.Windows.Media.Media3D.ScaleTransform3D>und <xref:System.Windows.Media.Media3D.RotateTransform3D>. Das [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D-System <xref:System.Windows.Media.Media3D.MatrixTransform3D> bietet auch eine Klasse, mit der Sie dieselben Transformationen in prägnanteren Matrixoperationen angeben können.  
  
 <xref:System.Windows.Media.Media3D.TranslateTransform3D>verschiebt alle Punkte in der Model3D in die Richtung <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetY%2A>des <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetZ%2A> Offsetvektors, den Sie mit den , und den Eigenschaften angeben. Bei einem Vertex eines Würfels auf (2,2,2) würde ein Offsetvektor von (0,1.6,1) den Vertex (2,2,2) auf (2,3.6,3).) verschieben. Der Vertex des Würfels befindet sich noch immer auf (2,2,2) im Modellraum. Da sich nun aber die Beziehung des Modellraums zum Weltenraum geändert hat, entsprechen die Koordinaten (2,2,2) im Modellraum den Koordinaten (2,3.6,3) im Weltenraum.  
  
 ![Abbildung der Übersetzung](./media/transforms-translate.png "Transforms-Translate")  
Übersetzung mit Offset  
  
 In den folgenden Codebeispielen wird die Anwendung einer Übersetzung veranschaulicht.  
  
 [!code-xaml[animation3dgallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="scale-transformations"></a>Skalierungstransformationen  
 <xref:System.Windows.Media.Media3D.ScaleTransform3D>ändert die Skalierung des Modells durch einen angegebenen Maßstabsvektor mit Bezug auf einen Mittelpunkt. Geben Sie eine einheitliche Skalierung an, die das Modell um den gleichen Wert auf den x-, y- und z-Achsen skaliert, um die Größe des Modells proportional zu ändern. Wenn Sie z. B. <xref:System.Windows.Media.ScaleTransform.ScaleY%2A>die <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> <xref:System.Windows.Media.ScaleTransform.ScaleX%2A>, und Eigenschaften der Transformation auf 0,5 die Größe des Modells halbieren. Wenn Sie die gleichen Eigenschaften auf 2 festlegen, verdoppelt sich die Skalierung in allen drei Achsen.  
  
 ![Einheitliches ScaleTransform3D](./media/threecubes-uniformscale-1.png "threecubes_uniformscale_1")  
ScaleVector-Beispiel  
  
 Durch Angabe einer ungleichmäßigen Skalierungstransformation – eine Skalierungstransformation, deren x-, y- und z-Werte nicht alle identisch sind – kann ein Modell in einer oder zwei Dimensionen ohne Auswirkung auf die anderen gestreckt oder verkleinert werden. Wenn Sie <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> z. <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> B. 1, auf 2 und <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> auf 1 setzen, wird das transformierte Modell in der Höhe verdoppelt, bleibt jedoch entlang der X- und Z-Achse unverändert.  
  
 Aufgrund von ScaleTransform3D erweitern oder verkleinern sich Vertices standardmäßig um den Ursprung (0,0,0). Wenn das Modell, das Sie transformieren möchten, nicht vom Ursprung aus gezeichnet wurde, wird eine Skalierung vom Ursprung aus das Modell nicht „an Ort und Stelle“ skalieren. Stattdessen wird das Modell durch den Skalierungsvorgang sowohl übersetzt als auch skaliert, wenn die Vertices des Modells mit dem Skalierungsvektor multipliziert werden.  
  
 ![Drei mit einem angegebenen Mittelpunkt skalierte Würfel](./media/threecubes-scaledwithcenter-1.png "threecubes_scaledwithcenter_1")  
Beispiel für die Skalierung um den Mittelpunkt  
  
 Um ein Modell "an Ort und Stelle" zu skalieren, geben <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A>Sie <xref:System.Windows.Media.Media3D.ScaleTransform3D.CenterZ%2A> die Mitte des Modells an, indem Sie die ScaleTransform3D , und Eigenschaften festlegen. Dadurch wird sichergestellt, dass das Grafiksystem den Modellbereich skaliert <xref:System.Windows.Media.Media3D.Point3D>und dann in die Mitte auf die angegebene übersetzt. Wenn Sie das Modell umgekehrt um den Ursprung erstellt haben und geben einen anderen Mittelpunkt angeben, wird das Modell vom Ursprung weg übersetzt.  
  
## <a name="rotation-transformations"></a>Rotationstransformationen  
 Sie können ein Modell in 3D auf verschiedene Arten drehen. Eine normale Rotationstransformation gibt eine Achse und einen Drehwinkel um diese Achse an. Mit <xref:System.Windows.Media.Media3D.RotateTransform3D> der Klasse können <xref:System.Windows.Media.Media3D.Rotation3D> Sie <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> eine mit ihrer Eigenschaft definieren. You then specify <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> and <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> properties on the Rotation3D, in this case an <xref:System.Windows.Media.Media3D.AxisAngleRotation3D>, to define the transformation. In den folgenden Beispielen wird ein Modell um 60 Grad um die y-Achse gedreht.  
  
 [!code-xaml[animation3dgallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
 Anmerkung:[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D ist ein Rechtshändersystem, was bedeutet, dass ein positiver Winkelwert für eine Drehung zu einer Drehung gegen den Uhrzeigersinn um die Achse führt.  
  
 Achsenwinkeldrehungen nehmen die Drehung um den Ursprung an, <xref:System.Windows.Media.Media3D.RotateTransform3D.CenterY%2A>wenn <xref:System.Windows.Media.Media3D.RotateTransform3D.CenterZ%2A> kein Wert für die <xref:System.Windows.Media.Media3D.RotateTransform3D.CenterX%2A>, und die Eigenschaften in RotateTransform3D angegeben ist. Wie bei der Skalierung ist es hilfreich zu wissen, dass die Rotation den gesamten Koordinatenraum des Modells transformiert. Wenn das Modell nicht um den Ursprung erstellt wurde oder bereits übersetzt wurde, könnte die Drehung um den Ursprung und nicht an Ort und Stelle erfolgen.  
  
 ![Drehung mit neuem Mittelpunkt](./media/threecubes-rotationwithcenter-1.png "threecubes_rotationwithcenter_1")  
Drehung mit neuem, angegebenen Mittelpunkt  
  
 Geben Sie zum Drehen des Modells „an Ort und Stelle“ den tatsächlichen Mittelpunkt des Modells als Mittelpunkt der Rotation an. Da die Geometrie in der Regel um den Ursprung modelliert wird, sollten Sie zuerst die Größe des Modells anpassen (skalieren), dann die Ausrichtung festlegen (drehen) und es anschließend an die gewünschte Position verschieben (übersetzen). So erzielen Sie bei einer Reihe von Transformationen normalerweise das erwünschte Ergebnis.  
  
 ![Drehung um 60 Grad auf der x&#45; und y&#45;Achse](./media/twocubes-rotation2axes-1.png "twocubes_rotation2axes_1")  
Rotationsbeispiele  
  
 Achsen-Winkel-Rotationen eignen sich für statische Transformationen und einige Animationen. Sie sollten jedoch ein Würfelmodell um 60 Grad um die X-Achse drehen und dann 45 Grad um die Z-Achse. Sie können diese Transformation als zwei diskrete affine Transformationen oder als Matrix beschreiben. Die Animation der beschriebenen Rotation kann sich aber als problematisch herausstellen. Obwohl die Anfangs- und Endposition des Modells bei beiden Ansätzen identisch sind, sind die Zwischenpositionen des Modells rechnerisch nicht sicher. Quaternionen stellen eine alternative Möglichkeit zum Berechnen der Interpolation zwischen dem Start und dem Ende einer Rotation dar.  
  
 Ein Quaternion stellt eine Achse im 3D-Raum und eine Drehung um diese Achse dar. Eine Quaternion kann z.B. eine Achse (1,1,2) und eine Drehung um 50 Grad darstellen. Die Leistungsstärke von Quaternionen beim Definieren von Rotationen gründet in zwei Vorgängen, die Sie dafür ausführen können: die Zusammensetzung und die Interpolation. Die auf eine Geometrie angewendete Zusammensetzung von zwei Quaternionen bedeutet, dass die Geometrie um Achse2 um Rotation2 und anschließend um Achse1 um Rotation1 gedreht wird. Mithilfe der Zusammensetzung können Sie diese zwei Rotationen der Geometrie kombinieren, um eine einzelne Quaternion zu erstellen, die das Ergebnis darstellt. Da die Interpolation von Quaternionen einen eindeutigen Pfad von einer Achse und ihrer Ausrichtung zu einer anderen berechnen kann, können Sie vom Original zum zusammengesetzten Quaternion interpolieren, um einen reibungslosen Übergang von einem zum anderen zu erreichen und die Transformation dadurch zu animieren. Für Modelle, die Sie animieren <xref:System.Windows.Media.Media3D.Quaternion> möchten, können Sie <xref:System.Windows.Media.Media3D.QuaternionRotation3D> ein <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> Ziel für die Drehung angeben, indem Sie eine für die Eigenschaft verwenden.  
  
## <a name="using-transformation-collections"></a>Verwenden von Auflistungstransformationen  
 Beim Erstellen einer Szene ist es üblich, mehr als eine Transformation auf ein Modell anzuwenden. Fügen Sie der <xref:System.Windows.Media.Media3D.Transform3DGroup.Children%2A> Auflistung <xref:System.Windows.Media.Media3D.Transform3DGroup> der Klasse Transformationen hinzu, um Transformationen bequem zu gruppieren, um sie auf verschiedene Modelle in der Szene anzuwenden. Häufig ist es sinnvoll, eine Transformation in mehreren verschiedenen Gruppen wiederzuverwenden, so wie Sie auch ein Modell durch Anwenden eines anderen Satzes von Transformationen auf jede Instanz wiederverwenden können. Beachten Sie, dass die Reihenfolge, in der die Transformationen der Auflistung hinzugefügt werden, relevant ist: Die ersten Transformationen in der Auflistung werden zuerst und die letzten zuletzt angewendet.  
  
## <a name="animating-transformations"></a>Animieren von Transformationen  
 Die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D-Implementierung ist teils im gleichen Timing- und Animationssystem wie 2D-Grafiken. Mit anderen Worten, um eine 3D-Szene zu animieren, animieren Sie die Eigenschaften ihrer Modelle. Es ist möglich, die Eigenschaften von primitiven Typen direkt zu animieren. In der Regel ist es aber einfacher, Transformationen zu animieren, die die Position oder die Darstellung von Modellen ändern. Da Transformationen sowohl <xref:System.Windows.Media.Media3D.Model3DGroup> auf Objekte als auch auf einzelne Modelle angewendet werden können, ist es möglich, einen Satz von Animationen auf die untergeordneten Elemente einer Model3Dgroup und einen anderen Satz von Animationen auf eine Gruppe von Objekten anzuwenden.  Hintergrundinformationen zum Zeitsteuerungs- und Animationssystem von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] finden Sie unter [Übersicht über Animationen](animation-overview.md) und [Übersicht über Storyboards](storyboards-overview.md).  
  
 Um ein Objekt in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] zu animieren, erstellen Sie eine Zeitachse, definieren Sie eine Animation (die im Zeitablauf eine tatsächliche Änderung einiger Eigenschaftswerte darstellt), und geben Sie die Eigenschaft an, auf die die Animation angewendet werden soll. Diese Eigenschaft muss eine Eigenschaft von FrameworkElement sein. Da alle Objekte in einer 3D-Szene untergeordnete Objekte von Viewport3D sind, sind die Eigenschaften, auf die eine Animation abzielt, die Sie auf die Szene anwenden möchten, Eigenschaften von Eigenschaften von Viewport3D. Es ist wichtig, den Eigenschaftenpfad für die Animation sorgfältig anzupassen, da die Syntax sehr ausführlich sein kann.  
  
 Angenommen Sie möchten ein Objekt an Ort und Stelle drehen und außerdem eine Schwingbewegung darauf anwenden, um mehr von dem anzuzeigenden Objekt darzustellen. Sie können dazu RotateTransform3D auf das Modell anwenden und dessen Rotationsachse von einem Vektor zu einem anderen animieren. Im folgenden Codebeispiel <xref:System.Windows.Media.Animation.Vector3DAnimation> wird das Anwenden einer auf die Axis-Eigenschaft der TransformationRotation3D veranschaulicht, wobei die RotateTransform3D als eine von mehreren Transformationen gilt, die auf das Modell mit einer <xref:System.Windows.Media.TransformGroup>angewendet werden.  
  
 [!code-csharp[3doverview#3DOverview3DN1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 Verwenden Sie eine ähnliche Syntax, um auf andere zu verschiebende Transformationseigenschaften abzuzielen oder das Objekt zu skalieren.  Sie können z. <xref:System.Windows.Media.Animation.Point3DAnimation> B. eine auf die ScaleCenter-Eigenschaft in einer Maßstabstransformation anwenden, um zu bewirken, dass ein Modell seine Form problemlos verzerrt.  
  
 Obwohl die vorherigen Beispiele <xref:System.Windows.Media.Media3D.GeometryModel3D>die Eigenschaften von transformieren, ist es auch möglich, die Eigenschaften anderer Modelle in der Szene zu transformieren.  Durch die Animation von Übersetzungen, die z.B. auf Lichtobjekte angewendet werden, können Sie wechselnde Licht- und Schatteneffekte erstellen, die die Darstellung eines Modells eindrucksvoll ändern.  
  
 Da Kameras auch Modelle sind, können Kameraeigenschaften ebenfalls transformiert werden.  Sie können zwar die Darstellung der Szene durch die Transformation der Kameraposition oder der Ebenenabstände (also die Projektion der gesamten Szene) ändern, allerdings ergeben viele der so erzielten Effekte als auf die Modellposition angewendete Transformationen optisch kaum Sinn für den Zuschauer.  
  
## <a name="see-also"></a>Weitere Informationen

- [3D-Grafikübersicht](3-d-graphics-overview.md)
- [Übersicht über Transformationen](transforms-overview.md)
- [2D-Transformationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
