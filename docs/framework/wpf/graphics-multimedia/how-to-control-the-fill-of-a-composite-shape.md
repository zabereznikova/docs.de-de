---
title: 'Vorgehensweise: Steuern des Ausfüllens einer zusammengesetzten Form'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], composite [WPF], controlling fill
- composite shapes [WPF], controlling fill
- graphics [WPF], composite shapes
- fill [WPF], controlling
ms.assetid: c1c94575-9eca-48a5-a49a-2ec65259f229
ms.openlocfilehash: 18261b2f7a71822684707de7c8c6a37793a8a410
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574676"
---
# <a name="how-to-control-the-fill-of-a-composite-shape"></a>Vorgehensweise: Steuern des Ausfüllens einer zusammengesetzten Form
Die <xref:System.Windows.Media.GeometryGroup.FillRule%2A> Eigenschaft eine <xref:System.Windows.Media.GeometryGroup> oder <xref:System.Windows.Media.PathGeometry>, gibt eine "Regel" die zusammengesetzte Form verwendet, um zu bestimmen, ob ein bestimmter Punkt Teil der Geometrie ist. Es gibt zwei mögliche Werte für <xref:System.Windows.Media.FillRule>: <xref:System.Windows.Media.FillRule.EvenOdd> und <xref:System.Windows.Media.FillRule.Nonzero>. In den folgenden Abschnitten wird beschrieben, wie diese beiden Regeln verwendet werden.  
  
 **EvenOdd:** Diese Regel bestimmt, ob ein Punkt im Ausfüllbereich befindet ab diesem Punkt ein Strahl in beliebiger Richtung gegen Unendlich gezeichnet und die Anzahl der Pfadsegmente in der Form, die den Strahl schneidet gezählt. Bei einer ungeraden Zahl liegt der Punkt innen, und bei einer geraden Zahl liegt er außen.  
  
 Der folgende XAML erstellt z. B. eine aus einer Reihe von konzentrischen Ringen (Ziel) zusammengesetzte Form mit einem <xref:System.Windows.Media.GeometryGroup.FillRule%2A> festgelegt <xref:System.Windows.Media.FillRule.EvenOdd>.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleEvenOddValue](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillruleevenoddvalue)]  
  
 Die folgende Abbildung zeigt die im vorherigen Beispiel erstellte Form.  
  
 ![Screenshot: FillRule-Eigenschaft von EvenOdd](../../../../docs/framework/wpf/graphics-multimedia/media/fillruleevenoddfirstone.png "FillRuleEvenOddFirstOne")  
  
 Beachten Sie, dass in der Abbildung oben die Mitte und der dritte Ring nicht ausgefüllt sind. Dies ist darauf zurückzuführen, dass ein Strahl, der von einem beliebigen Punkt innerhalb eines dieser beiden Ringe gezeichnet wird, eine gerade Anzahl von Segmenten schneidet. Dies wird aus der folgenden Abbildung ersichtlich:  
  
 ![Diagramm: FillRule-Eigenschaftswert von EvenOdd](../../../../docs/framework/wpf/graphics-multimedia/media/fillruleevenodd2.png "FillRuleEvenOdd2")  
  
 **NonZero:** Diese Regel bestimmt, ob ein Punkt innerhalb des ausfüllbereichs des Pfads ist, indem ein unendlicher Strahl von diesem Punkt in beliebiger Richtung gegen Unendlich gezeichnet und anschließend die Stellen untersucht, in denen ein Segment der Form den Strahl schneidet. Beginnen Sie mit dem Wert 0 (null), und addieren Sie für jede Stelle, an der ein Segment den Strahl von links nach rechts schneidet, den Wert 1. Wenn das Ergebnis nach dem Zählen der Überschneidungen 0 (null) ist, liegt der Punkt außerhalb des Pfads. Andernfalls liegt er innerhalb des Pfads.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValueEllipseGeometry](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovalueellipsegeometry)]  
  
 Im Beispiel oben, einen Wert von <xref:System.Windows.Media.FillRule.Nonzero> für <xref:System.Windows.Media.GeometryGroup.FillRule%2A> daher ergibt die folgende Abbildung:  
  
 ![Screenshot: NonZero-FillRule-Wert](../../../../docs/framework/wpf/graphics-multimedia/media/fillrulenonzero1.png "FillRuleNonZero1")  
  
 Wie Sie sehen können, sind alle Ringe ausgefüllt. Dies kommt daher, dass alle Segmente in die gleiche Richtung verlaufen und deshalb ein Strahl, der von einem beliebigen Punkt aus gezeichnet wird, ein oder mehrere Segmente schneidet, sodass die Summe der Schnitte ungleich 0 (null) ist. So stellen zum Beispiel die roten Pfeile in der unten aufgeführten Abbildung die Richtung dar, in die die Segmente gezeichnet werden. Die weißen Pfeile stellen einen zufälligen Strahl dar, der von einem Punkt im innersten Ring aus verläuft. Ausgehend vom Wert 0 (null) wird für jedes Segment, das der Strahl schneidet, der Wert 1 addiert, da das Segment den Strahl von links nach rechts schneidet.  
  
 ![Diagramm: FillRule-Eigenschaftswert entspricht NonZero](../../../../docs/framework/wpf/graphics-multimedia/media/fillrulenonzero2.png "FillRuleNonZero2")  
  
 Um das Verhalten besser zu veranschaulichen <xref:System.Windows.Media.FillRule.Nonzero> ist Regel eine komplexere Form mit Segmenten, die in verschiedene Richtungen erforderlich ist. Der folgende XAML-Code wird eine ähnliche Form wie im vorherigen Beispiel, außer dass sie mit erstellt wird eine <xref:System.Windows.Media.PathGeometry> sondern klicken Sie dann eine <xref:System.Windows.Media.EllipseGeometry> erstellt vier konzentrische Bögen statt vollständig geschlossene konzentrische Kreise.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValuePathGeometry](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovaluepathgeometry)]  
  
 Die folgende Abbildung zeigt die im vorherigen Beispiel erstellte Form.  
  
 ![Screenshot: FillRule-Eigenschaftswert Nonzero](../../../../docs/framework/wpf/graphics-multimedia/media/fillrulenonzero3.png "FillRuleNonZero3")  
  
 Beachten Sie, dass der dritte Bogen ab der Mitte nicht ausgefüllt ist. Die folgende Abbildung zeigt, warum dies so ist. In der Abbildung stellen die roten Pfeile die Richtung dar, in der die Segmente gezeichnet werden. Die beiden weißen Pfeile stellen zwei zufällige Strahlen dar, die von einem Punkt im „nicht ausgefüllten“ Bereich ausgehen. Wie aus der Abbildung ersichtlich, ist die Summe der Werte eines bestimmten Strahls, der die Segmente in seinem Pfad schneidet, gleich 0 (null). Wie oben bereits definiert, bedeutet eine Summe von null, dass der Punkt nicht Teil der Geometrie ist (kein Teil der Füllung), während eine Summe, die *ungleich* null oder negativ ist, Teil der Geometrie ist.  
  
 ![Diagramm: FillRule-Eigenschaftswert Nonzero](../../../../docs/framework/wpf/graphics-multimedia/media/fillrulenonzero4.png "FillRuleNonZero4")  
  
 **Hinweis**: Zum Zweck der <xref:System.Windows.Media.FillRule>, alle Formen werden als geschlossen betrachtet. Wenn in einem Segment eine Lücke vorhanden ist, zeichnen Sie eine gedachte Linie, um sie zu schließen. Im oben aufgeführten Beispiel weisen die Ringe kleine Lücken auf. Daher könnte man erwarten, dass ein Strahl durch die Lücke verläuft und ein anderes Ergebnis ergibt als ein Strahl, der in eine andere Richtung verläuft. Im folgenden finden Sie eine vergrößerte Abbildung einer dieser Lücken und des "gedachten"Segments dargestellt (Segment, das der Anwendung gezeichnet wird die <xref:System.Windows.Media.FillRule>), die geschlossen wird.  
  
 ![Diagramm: Für die FillRule sind die Segmente immer geschlossen](../../../../docs/framework/wpf/graphics-multimedia/media/fillruleclosedshapes.png "FillRuleClosedShapes")  
  
## <a name="example"></a>Beispiel  
  
## <a name="see-also"></a>Siehe auch
- [Erstellen einer zusammengesetzten Form](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)
- [Übersicht über Geometrien](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
