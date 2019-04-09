---
title: Übersicht über 3D-Transformationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D transformations
- transformations [WPF], 3-D
ms.assetid: e45e555d-ac1e-4b36-aced-e433afe7f27f
ms.openlocfilehash: bbb3c413148bd2e2ab8de8a1a725f2d9a8acf2f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190629"
---
# <a name="3-d-transformations-overview"></a>Übersicht über 3D-Transformationen
In diesem Thema wird beschrieben, wie Transformationen im [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Grafiksystem auf 3D-Modelle angewendet werden. Mit Transformationen können Entwickler die Position und Größe von Modellen ändern und sie neu ausrichten, ohne die Basiswerte zu verändern, die sie definieren.  

## <a name="3-d-coordinate-space"></a>3D-Koordinatenbereich  
 In Inhalte von 3D-Grafiken [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] in ein Element gekapselt <xref:System.Windows.Controls.Viewport3D>, kann das Teil einer zweidimensionalen Elementstruktur sein. Das Grafiksystem behandelt Viewport3D als ein zweidimensionales visuelles Objekt, wie viele andere auch in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Viewport3D fungiert als Fenster – ein Anzeigebereich – in eine dreidimensionale Szene. Genauer gesagt handelt es sich um eine Oberfläche, auf die eine 3D-Szene projiziert wird.  Obwohl Sie Viewport3D mit anderen 2D-Zeichenobjekten im selben Szenegraphen verwenden können, können Sie keine 2D- und 3D-Objekte in Viewport3D durchdringen. In der folgenden Erläuterung ist der beschriebene Koordinatenraum im Viewport3D-Element enthalten.  
  
 Im [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Koordinatensystem für 2D-Grafiken befindet sich der Ursprung in der linken oberen Ecke der Renderingoberfläche (in der Regel der Bildschirm). Im 2D-System verlaufen die positiven Werte der x-Achse nach rechts und die positiven Werte der y-Achse nach unten. Im 3D-Koordinatensystem befindet sich der Ursprung hingegen in der Mitte des Bildschirms. Die positiven Werte der x-Achse verlaufen auch nach rechts, die positiven Werte der y-Achse verlaufen aber nach oben und die positiven Werte der z-Achse laufen vom Ursprung ausgehend auf den Betrachter zu.  
  
 ![Koordinatensysteme](./media/coordsystem-1.png "CoordSystem-1")  
Vergleich der Koordinatensysteme  
  
 Der von diesen Achsen definierte Raum ist der feststehende Verweisrahmen für 3D-Objekte in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Wenn Sie innerhalb dieses Raumes Modelle erstellen und Lichter und Kameras, um sie anzuzeigen, ist es hilfreich, diesen feststehenden Verweisrahmen oder „Weltenraum“ vom lokalen zu unterscheiden, den Sie beim Anwenden von Transformationen für jedes Modell erstellen. Beachten Sie außerdem, dass Objekte im Weltenraum je nach der Kamera und den Einstellungen völlig anders oder überhaupt nicht angezeigt werden können. Die Position der Kamera ändert aber nicht die Position von Objekten im Weltenraum.  
  
## <a name="transforming-models"></a>Transformieren von Modellen  
 Wenn Sie Modelle erstellen, verfügen diese über eine bestimmte Position in der Szene. Um die Position dieser Modelle in der Szene zu verändern, sie zu drehen oder ihre Größe zu ändern, sollten Sie nicht die Vertices ändern, die die Modelle selbst definieren. Wenden Sie stattdessen wie in 2D-Modellen Transformationen auf Modelle an.  
  
 Jedes Modellobjekt verfügt über eine <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> Eigenschaft mit dem verschieben, neu ausrichten oder Ändern der Größe des Modells. Wenn Sie eine Transformation anwenden, versetzen Sie alle Punkte des Modells um den in der Transformation angegebenen Vektor oder Wert. Mit anderen Worten: Sie haben den Koordinatenbereich transformiert, in dem das Modell definiert ist (Modellraum), aber Sie haben noch nicht die Werte geändert, die die Geometrie des Modells im Koordinatensystem der gesamten Szene („Weltenraum“) ausmachen.  
  
## <a name="translation-transformations"></a>Übersetzungstransformationen  
 3D-Transformationen erben von der abstrakten Basisklasse <xref:System.Windows.Media.Media3D.Transform3D>; dazu gehören die affinen Transformationsklassen <xref:System.Windows.Media.Media3D.TranslateTransform3D>, <xref:System.Windows.Media.Media3D.ScaleTransform3D>, und <xref:System.Windows.Media.Media3D.RotateTransform3D>. Die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D-System bietet auch eine <xref:System.Windows.Media.Media3D.MatrixTransform3D> -Klasse, die Ihnen ermöglicht geben die gleichen Transformationen in kürzeren matrixoperationen.  
  
 <xref:System.Windows.Media.Media3D.TranslateTransform3D> Verschiebt alle Punkte in der Model3D in Richtung des Offsetvektors, die Sie angeben, mit der <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A>, <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetY%2A>, und <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetZ%2A> Eigenschaften. Bei einem Vertex eines Würfels auf (2,2,2) würde ein Offsetvektor von (0,1.6,1) den Vertex (2,2,2) auf (2,3.6,3).) verschieben. Der Vertex des Würfels befindet sich noch immer auf (2,2,2) im Modellraum. Da sich nun aber die Beziehung des Modellraums zum Weltenraum geändert hat, entsprechen die Koordinaten (2,2,2) im Modellraum den Koordinaten (2,3.6,3) im Weltenraum.  
  
 ![Abbildung der Übersetzung](./media/transforms-translate.png "Transformationen übersetzen")  
Übersetzung mit Offset  
  
 In den folgenden Codebeispielen wird die Anwendung einer Übersetzung veranschaulicht.  
  
 [!code-xaml[animation3dgallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="scale-transformations"></a>Skalierungstransformationen  
 <xref:System.Windows.Media.Media3D.ScaleTransform3D> Ändert die Skalierung des Modells durch einen angegebenen Skalierungsvektor auf einen Mittelpunkt. Geben Sie eine einheitliche Skalierung an, die das Modell um den gleichen Wert auf den x-, y- und z-Achsen skaliert, um die Größe des Modells proportional zu ändern. Beispiel: Wenn der Transformation <xref:System.Windows.Media.ScaleTransform.ScaleX%2A>, <xref:System.Windows.Media.ScaleTransform.ScaleY%2A>, und <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> auf 0,5 wird die Größe des Modells halbiert; die gleichen Eigenschaften auf 2 festlegen, wird die Skalierung auf allen drei Achsen verdoppelt.  
  
 ![Symbole mit einheitlicher ScaleTransform3D](./media/threecubes-uniformscale-1.png "threecubes_uniformscale_1")  
ScaleVector-Beispiel  
  
 Durch Angabe einer ungleichmäßigen Skalierungstransformation – eine Skalierungstransformation, deren x-, y- und z-Werte nicht alle identisch sind – kann ein Modell in einer oder zwei Dimensionen ohne Auswirkung auf die anderen gestreckt oder verkleinert werden. Z. B. <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 1 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> auf 2 und <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> 1 würde des transformierten Modells verdoppelt sich die Höhe aber entlang der X- und Z-Achse unverändert bleiben.  
  
 Aufgrund von ScaleTransform3D erweitern oder verkleinern sich Vertices standardmäßig um den Ursprung (0,0,0). Wenn das Modell, das Sie transformieren möchten, nicht vom Ursprung aus gezeichnet wurde, wird eine Skalierung vom Ursprung aus das Modell nicht „an Ort und Stelle“ skalieren. Stattdessen wird das Modell durch den Skalierungsvorgang sowohl übersetzt als auch skaliert, wenn die Vertices des Modells mit dem Skalierungsvektor multipliziert werden.  
  
 ![Drei Cubes, die mit einem angegebenen Mittelpunkt skalierte](./media/threecubes-scaledwithcenter-1.png "threecubes_scaledwithcenter_1")  
Beispiel für die Skalierung um den Mittelpunkt  
  
 Um das Modell "an Ort und Stelle" Skalieren zu können, geben Sie den Mittelpunkt des Modells, durch Festlegen der ScaleTransform3D <xref:System.Windows.Media.ScaleTransform.CenterX%2A>, <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, und <xref:System.Windows.Media.Media3D.ScaleTransform3D.CenterZ%2A> Eigenschaften. Dadurch wird sichergestellt, dass das Grafiksystem den Modellraum skaliert, und klicken Sie dann auf dem angegebenen zentrieren übersetzt <xref:System.Windows.Media.Media3D.Point3D>. Wenn Sie das Modell umgekehrt um den Ursprung erstellt haben und geben einen anderen Mittelpunkt angeben, wird das Modell vom Ursprung weg übersetzt.  
  
## <a name="rotation-transformations"></a>Rotationstransformationen  
 Sie können ein Modell in 3D auf verschiedene Weise drehen. Eine normale Rotationstransformation gibt eine Achse und einen Drehwinkel um diese Achse an. Die <xref:System.Windows.Media.Media3D.RotateTransform3D> Klasse können Sie definieren eine <xref:System.Windows.Media.Media3D.Rotation3D> mit seiner <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> Eigenschaft. Geben Sie dann <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> und <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> Eigenschaften auf der Rotation3D, in diesem Fall eine <xref:System.Windows.Media.Media3D.AxisAngleRotation3D>, um die Transformation zu definieren. In den folgenden Beispielen wird ein Modell um 60 Grad um die y-Achse gedreht.  
  
 [!code-xaml[animation3dgallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
 Hinweis:[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D ist ein rechtshändiges System, was bedeutet, dass ein positiver Winkelwert für eine Rotation gegen den Uhrzeigersinn eine Drehung um die Achse ergibt.  
  
 Achsen-Winkel-Rotationen davon den Ursprung aus, wenn ein Wert nicht, für angegeben wird die <xref:System.Windows.Media.Media3D.RotateTransform3D.CenterX%2A>, <xref:System.Windows.Media.Media3D.RotateTransform3D.CenterY%2A>, und <xref:System.Windows.Media.Media3D.RotateTransform3D.CenterZ%2A> RotateTransform3D Eigenschaften. Wie bei der Skalierung ist es hilfreich zu wissen, dass die Rotation den gesamten Koordinatenraum des Modells transformiert. Wenn das Modell nicht um den Ursprung erstellt wurde oder bereits übersetzt wurde, könnte die Drehung um den Ursprung und nicht an Ort und Stelle erfolgen.  
  
 ![Drehung mit neuem Mittelpunkt](./media/threecubes-rotationwithcenter-1.png "threecubes_rotationwithcenter_1")  
Drehung mit neuem, angegebenen Mittelpunkt  
  
 Geben Sie zum Drehen des Modells „an Ort und Stelle“ den tatsächlichen Mittelpunkt des Modells als Mittelpunkt der Rotation an. Da die Geometrie in der Regel um den Ursprung modelliert wird, sollten Sie zuerst die Größe des Modells anpassen (skalieren), dann die Ausrichtung festlegen (drehen) und es anschließend an die gewünschte Position verschieben (übersetzen). So erzielen Sie bei einer Reihe von Transformationen normalerweise das erwünschte Ergebnis.  
  
 ![Drehung um 60 Grad in x&#45; und y&#45;Achsen](./media/twocubes-rotation2axes-1.png "twocubes_rotation2axes_1")  
Rotationsbeispiele  
  
 Achsen-Winkel-Rotationen eignen sich für statische Transformationen und einige Animationen. Jedoch sollten Sie die Rotation eines würfelmodells um 60 Grad um die x-Achse und anschließend um 45 Grad um die Z-Achse. Sie können diese Transformation als zwei affine Transformationen oder als Matrix beschreiben. Die Animation der beschriebenen Rotation kann sich aber als problematisch herausstellen. Obwohl die Anfangs- und Endposition des Modells bei beiden Ansätzen identisch sind, sind die Zwischenpositionen des Modells rechnerisch nicht sicher. Quaternionen stellen eine alternative Möglichkeit zum Berechnen der Interpolation zwischen dem Start und dem Ende einer Rotation dar.  
  
 Eine Quaternion stellt eine Achse in einem 3D-Raum und eine Rotation um diese Achse dar. Eine Quaternion kann z.B. eine Achse (1,1,2) und eine Drehung um 50 Grad darstellen. Die Leistungsstärke von Quaternionen beim Definieren von Rotationen gründet in zwei Vorgängen, die Sie dafür ausführen können: die Zusammensetzung und die Interpolation. Die auf eine Geometrie angewendete Zusammensetzung von zwei Quaternionen bedeutet, dass die Geometrie um Achse2 um Rotation2 und anschließend um Achse1 um Rotation1 gedreht wird. Mithilfe der Zusammensetzung können Sie diese zwei Rotationen der Geometrie kombinieren, um eine einzelne Quaternion zu erstellen, die das Ergebnis darstellt. Da die Interpolation von Quaternionen einen eindeutigen Pfad von einer Achse und ihrer Ausrichtung zu einer anderen berechnen kann, können Sie vom Original zum zusammengesetzten Quaternion interpolieren, um einen reibungslosen Übergang von einem zum anderen zu erreichen und die Transformation dadurch zu animieren. Für Modelle, die Sie animieren möchten, können Sie angeben, ein Ziel <xref:System.Windows.Media.Media3D.Quaternion> für die Rotation mithilfe einer <xref:System.Windows.Media.Media3D.QuaternionRotation3D> für die <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> Eigenschaft.  
  
## <a name="using-transformation-collections"></a>Verwenden von Auflistungstransformationen  
 Beim Erstellen einer Szene ist es üblich, mehr als eine Transformation auf ein Modell anzuwenden. Hinzufügen von Transformationen der <xref:System.Windows.Media.Media3D.Transform3DGroup.Children%2A> Auflistung von der <xref:System.Windows.Media.Media3D.Transform3DGroup> Klasse, um der Gruppe um Transformationen bequem für verschiedene Modelle in der Szene zuweisen. Häufig ist es sinnvoll, eine Transformation in mehreren verschiedenen Gruppen wiederzuverwenden, so wie Sie auch ein Modell durch Anwenden eines anderen Satzes von Transformationen auf jede Instanz wiederverwenden können. Beachten Sie, dass die Reihenfolge, in der die Transformationen der Auflistung hinzugefügt werden, relevant ist: Die ersten Transformationen in der Auflistung werden zuerst und die letzten zuletzt angewendet.  
  
## <a name="animating-transformations"></a>Animieren von Transformationen  
 Die 3D-Implementierung von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] gehört dem gleichen Zeitsteuerungs- und Animationssystem an wie die 2D-Grafiken. Das heißt, dass Sie die Eigenschaften von dessen Modellen animieren müssen, um eine 3D-Szene zu animieren. Es ist möglich, die Eigenschaften von primitiven Typen direkt zu animieren. In der Regel ist es aber einfacher, Transformationen zu animieren, die die Position oder die Darstellung von Modellen ändern. Da Transformationen können, um angewendet werden <xref:System.Windows.Media.Media3D.Model3DGroup> -Objekten sowie einzelne Modelle, es ist möglich, einen Satz von Animationen auf die untergeordneten Elemente einer Model3Dgroup und einen anderen Satz von Animationen auf eine Gruppe von Objekten anzuwenden.  Hintergrundinformationen zum Zeitsteuerungs- und Animationssystem von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] finden Sie unter [Übersicht über Animationen](animation-overview.md) und [Übersicht über Storyboards](storyboards-overview.md).  
  
 Um ein Objekt in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] zu animieren, erstellen Sie eine Zeitachse, definieren Sie eine Animation (die im Zeitablauf eine tatsächliche Änderung einiger Eigenschaftswerte darstellt), und geben Sie die Eigenschaft an, auf die die Animation angewendet werden soll. Diese Eigenschaft muss eine Eigenschaft von FrameworkElement sein. Da alle Objekte in einer 3D-Szene untergeordnete Elemente von Viewport3D sind, handelt es sich bei den Eigenschaften, an die sich alle Animationen richten, die Sie auf die Szene anwenden möchten, um Eigenschaften von Viewport3D-Eigenschaften. Es ist wichtig, den Eigenschaftenpfad für die Animation sorgfältig anzupassen, da die Syntax sehr ausführlich sein kann.  
  
 Angenommen Sie möchten ein Objekt an Ort und Stelle drehen und außerdem eine Schwingbewegung darauf anwenden, um mehr von dem anzuzeigenden Objekt darzustellen. Sie können dazu RotateTransform3D auf das Modell anwenden und dessen Rotationsachse von einem Vektor zu einem anderen animieren. Das folgende Codebeispiel veranschaulicht die Anwendung eine <xref:System.Windows.Media.Animation.Vector3DAnimation> auf die Achseneigenschaft von Rotation3D der Transformation, sofern die RotateTransform3D eine der vielen Transformationen angewendet werden, auf das Modell mit einem <xref:System.Windows.Media.TransformGroup>.  
  
 [!code-csharp[3doverview#3DOverview3DN1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 Verwenden Sie eine ähnliche Syntax, um auf andere zu verschiebende Transformationseigenschaften abzuzielen oder das Objekt zu skalieren.  Sie können z. B. Anwenden einer <xref:System.Windows.Media.Animation.Point3DAnimation> auf die ScaleCenter-Eigenschaft bei einer Skalierungstransformation, dazu führen, dass ein Modell für reibungslos zu verzerren.  
  
 Obwohl es sich bei die vorherigen Beispielen die Eigenschaften der Transformation <xref:System.Windows.Media.Media3D.GeometryModel3D>, es ist auch möglich, die die Eigenschaften anderer Modelle in der Szene zu transformieren.  Durch die Animation von Übersetzungen, die z.B. auf Lichtobjekte angewendet werden, können Sie wechselnde Licht- und Schatteneffekte erstellen, die die Darstellung eines Modells eindrucksvoll ändern.  
  
 Da Kameras auch Modelle sind, können Kameraeigenschaften ebenfalls transformiert werden.  Sie können zwar die Darstellung der Szene durch die Transformation der Kameraposition oder der Ebenenabstände (also die Projektion der gesamten Szene) ändern, allerdings ergeben viele der so erzielten Effekte als auf die Modellposition angewendete Transformationen optisch kaum Sinn für den Zuschauer.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über 3D-Grafiken](3-d-graphics-overview.md)
- [Übersicht über Transformationen](transforms-overview.md)
- [Beispiel für 2D-Transformationen](https://go.microsoft.com/fwlink/?LinkID=158252)
