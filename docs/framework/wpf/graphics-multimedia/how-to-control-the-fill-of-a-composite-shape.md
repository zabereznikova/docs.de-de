---
title: 'Vorgehensweise: Steuern des Ausfüllens einer zusammengesetzten Form'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], composite [WPF], controlling fill
- composite shapes [WPF], controlling fill
- graphics [WPF], composite shapes
- fill [WPF], controlling
ms.assetid: c1c94575-9eca-48a5-a49a-2ec65259f229
ms.openlocfilehash: 0ba07d8979a2910ce4ec775493e38c714240f642
ms.sourcegitcommit: d21bee9dbd32b9540ad30f9d0e2e874227040be3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59427473"
---
# <a name="how-to-control-the-fill-of-a-composite-shape"></a>Vorgehensweise: Steuern des Ausfüllens einer zusammengesetzten Form
Die <xref:System.Windows.Media.GeometryGroup.FillRule%2A> Eigenschaft eine <xref:System.Windows.Media.GeometryGroup> oder <xref:System.Windows.Media.PathGeometry>, gibt eine "Regel" die zusammengesetzte Form verwendet, um zu bestimmen, ob ein bestimmter Punkt Teil der Geometrie ist. Es gibt zwei mögliche Werte für <xref:System.Windows.Media.FillRule>: <xref:System.Windows.Media.FillRule.EvenOdd> und <xref:System.Windows.Media.FillRule.Nonzero>. In den folgenden Abschnitten wird beschrieben, wie diese beiden Regeln verwendet werden.  
  
 **EvenOdd:** Diese Regel bestimmt, ob ein Punkt im Ausfüllbereich befindet ab diesem Punkt ein Strahl in beliebiger Richtung gegen Unendlich gezeichnet und die Anzahl der Pfadsegmente in der Form, die den Strahl schneidet gezählt. Bei einer ungeraden Zahl liegt der Punkt innen, und bei einer geraden Zahl liegt er außen.  
  
 Der folgende XAML erstellt z. B. eine aus einer Reihe von konzentrischen Ringen (Ziel) zusammengesetzte Form mit einem <xref:System.Windows.Media.GeometryGroup.FillRule%2A> festgelegt <xref:System.Windows.Media.FillRule.EvenOdd>.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleEvenOddValue](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillruleevenoddvalue)]  
  
 Die folgende Abbildung zeigt die im vorherigen Beispiel erstellte Form.  
  
 ![Ein Kreis, setzt sich aus einer Reihe konzentrischen Ringen mit unterschiedlichen Farben.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-property.png)  
  
 Beachten Sie, dass es sich bei dem Mittelpunkt und der dritte Ring nicht ausgefüllt sind, in der vorherigen Abbildung. Dies ist darauf zurückzuführen, dass ein Strahl, der von einem beliebigen Punkt innerhalb eines dieser beiden Ringe gezeichnet wird, eine gerade Anzahl von Segmenten schneidet. Finden Sie in der folgende Abbildung aus:  
  
 ![Diagramm mit der EvenOdd Strahlung in der Kreis gezeichnet.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-rays.png)  
  
 **NonZero:** Diese Regel bestimmt, ob ein Punkt innerhalb des ausfüllbereichs des Pfads ist, indem ein unendlicher Strahl von diesem Punkt in beliebiger Richtung gegen Unendlich gezeichnet und anschließend die Stellen untersucht, in denen ein Segment der Form den Strahl schneidet. Beginnen Sie mit dem Wert 0 (null), und addieren Sie für jede Stelle, an der ein Segment den Strahl von links nach rechts schneidet, den Wert 1. Wenn das Ergebnis nach dem Zählen der Überschneidungen 0 (null) ist, liegt der Punkt außerhalb des Pfads. Andernfalls liegt er innerhalb des Pfads.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValueEllipseGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovalueellipsegeometry)]  
  
 Im vorherigen Beispiel, einen Wert von <xref:System.Windows.Media.FillRule.Nonzero> für <xref:System.Windows.Media.GeometryGroup.FillRule%2A> daher ergibt die folgende Abbildung:  
  
 ![Ein Kreis, setzt sich aus einer Reihe konzentrischen Ringen alle mit der gleichen Farbe gefüllt.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-nonzero.png)  
  
 Wie Sie sehen können, sind alle Ringe ausgefüllt. Dies kommt daher, dass alle Segmente in die gleiche Richtung verlaufen und deshalb ein Strahl, der von einem beliebigen Punkt aus gezeichnet wird, ein oder mehrere Segmente schneidet, sodass die Summe der Schnitte ungleich 0 (null) ist. In der folgenden Abbildung wird z. B. die roten Pfeile stellen die kommunikationsrichtung, die die Segmente gezeichnet werden und der weiße Pfeil stellt einen zufälligen Strahl, der von einem Punkt im innersten Ring aus. Ausgehend vom Wert 0 (null) wird für jedes Segment, das der Strahl schneidet, der Wert 1 addiert, da das Segment den Strahl von links nach rechts schneidet.  
  
 ![Das Diagramm zeigt die FillRule-Eigenschaftswert entspricht Nonzero.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-equal-nonzero.png)  
  
 Um das Verhalten besser zu veranschaulichen <xref:System.Windows.Media.FillRule.Nonzero> ist Regel eine komplexere Form mit Segmenten, die in verschiedene Richtungen erforderlich ist. Der folgende XAML-Code wird eine ähnliche Form wie im vorherigen Beispiel, außer dass sie mit erstellt wird eine <xref:System.Windows.Media.PathGeometry> sondern klicken Sie dann eine <xref:System.Windows.Media.EllipseGeometry> erstellt vier konzentrische Bögen statt vollständig geschlossene konzentrische Kreise.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValuePathGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovaluepathgeometry)]  
  
 Die folgende Abbildung zeigt die im vorherigen Beispiel erstellte Form.  
  
 ![Ein Kreis, setzt sich aus einer Reihe konzentrischen Ringen mit unterschiedlichen Farben mit der dritte Bogen nicht ausgefüllt.](./media/how-to-control-the-fill-of-a-composite-shape/pathgeometry-concentric-arcs.png)  
  
 Beachten Sie, dass der dritte Bogen ab der Mitte nicht ausgefüllt ist. Die folgende Abbildung zeigt, warum dies ist. In der Abbildung stellen die roten Pfeile die Richtung dar, in der die Segmente gezeichnet werden. Die beiden weißen Pfeile stellen zwei zufällige Strahlen dar, die von einem Punkt im „nicht ausgefüllten“ Bereich ausgehen. Wie aus der Abbildung ersichtlich, ist die Summe der Werte eines bestimmten Strahls, der die Segmente in seinem Pfad schneidet, gleich 0 (null). Wie oben bereits definiert, bedeutet eine Summe von null, dass der Punkt nicht Teil der Geometrie ist (kein Teil der Füllung), während eine Summe, die *ungleich* null oder negativ ist, Teil der Geometrie ist.  
  
 ![Das Diagramm zeigt Zufällige Strahlen überschreiten Segmente.](./media/how-to-control-the-fill-of-a-composite-shape/arbitrary-ray-cross-segment.png)  
  
 **Hinweis**: Zum Zweck der <xref:System.Windows.Media.FillRule>, alle Formen werden als geschlossen betrachtet. Wenn in einem Segment eine Lücke vorhanden ist, zeichnen Sie eine gedachte Linie, um sie zu schließen. Im oben aufgeführten Beispiel weisen die Ringe kleine Lücken auf. Daher könnte man erwarten, dass ein Strahl durch die Lücke verläuft und ein anderes Ergebnis ergibt als ein Strahl, der in eine andere Richtung verläuft. Im folgenden finden Sie eine vergrößerte Abbildung einer dieser Lücken und des "gedachten"Segments dargestellt (Segment, das der Anwendung gezeichnet wird die <xref:System.Windows.Media.FillRule>), die geschlossen wird.  
  
 ![Das Diagramm zeigt die FillRule-Segmente, die immer geschlossen sind.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-closed-segments.png)  
  
## <a name="example"></a>Beispiel  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen einer zusammengesetzten Form](how-to-create-a-composite-shape.md)
- [Übersicht über die Geometrie](geometry-overview.md)
