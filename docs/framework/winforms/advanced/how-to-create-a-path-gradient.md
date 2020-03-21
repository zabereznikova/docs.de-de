---
title: 'Gewusst wie: Erstellen eines linearen Pfadfarbverlaufs'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- path gradients [Windows Forms], creating
- gradients [Windows Forms], creating path
- graphics paths [Windows Forms], creating gradient
ms.assetid: 1948e834-e104-481c-b71d-d8aa9e4d106e
ms.openlocfilehash: cf4dc558c008fb8adfc327a6a894a428e985df03
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182634"
---
# <a name="how-to-create-a-path-gradient"></a>Gewusst wie: Erstellen eines linearen Pfadfarbverlaufs
Mit <xref:System.Drawing.Drawing2D.PathGradientBrush> der Klasse können Sie die Art und Weise anpassen, wie Sie eine Form mit allmählich wechselnden Farben füllen. Sie können z. B. eine Farbe für die Mitte eines Pfads und eine andere Farbe für die Begrenzung eines Pfads angeben. Sie können auch separate Farben für jeden der einzelnen Punkte entlang der Grenze eines Pfads angeben.  
  
> [!NOTE]
> In GDI+ ist ein Pfad eine Folge von <xref:System.Drawing.Drawing2D.GraphicsPath> Linien und Kurven, die von einem Objekt verwaltet werden. Weitere Informationen zu GDI+-Pfaden finden Sie unter [Grafikpfade in GDI+](graphics-paths-in-gdi.md) und [Konstruktions- und Zeichnungspfade](constructing-and-drawing-paths.md).  

Die Beispiele in diesem Artikel sind Methoden, <xref:System.Windows.Forms.Control.Paint> die vom Ereignishandler eines Steuerelements aufgerufen werden.  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>So füllen Sie eine Ellipse mit einem Pfadverlauf  
  
- Im folgenden Beispiel wird eine Ellipse mit einem Pfadgradientenpinsel gefüllt. Die Mittlere Farbe ist auf Blau und die Begrenzungsfarbe auf aqua festgelegt. Die folgende Abbildung zeigt die gefüllte Ellipse.  
  
     ![Der Verlaufspfad füllt eine Ellipse.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     Standardmäßig erstreckt sich ein Pfadverlaufspinsel nicht über die Grenze des Pfads hinaus. Wenn Sie den Pfadverlaufspinsel verwenden, um eine Figur zu füllen, die über die Grenze des Pfads hinausgeht, wird der Bereich des Bildschirms außerhalb des Pfads nicht ausgefüllt.  
  
     Die folgende Abbildung zeigt, was <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> passiert, wenn `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`Sie den Aufruf im folgenden Code in folgendes ändern:  
  
     ![Der Verlaufspfad erstreckte sich über die Grenze des Pfads hinaus.](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     Das vorangehende Codebeispiel ist für die Verwendung <xref:System.Windows.Forms.PaintEventArgs> mit Windows Forms <xref:System.Windows.Forms.PaintEventHandler>konzipiert und erfordert das e, das ein Parameter von ist.  
  
### <a name="to-specify-points-on-the-boundary"></a>So geben Sie Punkte auf der Grenze an  
  
- Im folgenden Beispiel wird ein Pfadgradientenpinsel aus einem sternförmigen Pfad erstellt. Der Code <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> legt die Eigenschaft fest, die die Farbe am Schwerpunkt des Sterns auf Rot setzt. Anschließend legt der <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> Code die Eigenschaft fest, `colors` um verschiedene Farben (im Array gespeichert) an den einzelnen Punkten im `points` Array anzugeben. Die endgültige Codeanweisung füllt den sternförmigen Pfad mit dem Pfadgradientenpinsel.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
- Im folgenden Beispiel wird ein <xref:System.Drawing.Drawing2D.GraphicsPath> Pfadverlauf ohne Ein Objekt im Code gezeichnet. Der <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> jeweilige Konstruktor im Beispiel empfängt ein Array <xref:System.Drawing.Drawing2D.GraphicsPath> von Punkten, benötigt jedoch kein Objekt. Beachten Sie außerdem, dass der <xref:System.Drawing.Drawing2D.PathGradientBrush> zum Ausfüllen eines Rechtecks und nicht eines Pfads verwendet wird. Das Rechteck ist größer als der geschlossene Pfad, der zum Definieren des Pinsels verwendet wird, sodass ein Teil des Rechtecks nicht vom Pinsel gezeichnet wird. Die folgende Abbildung zeigt das Rechteck (gepunktete Linie) und den Teil des Rechtecks, der vom Pfadverlaufspinsel gezeichnet wird:
  
     ![Gradiententeil, der vom Pfadverlaufspinsel gezeichnet wird.](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>So passen Sie einen Pfadverlauf an  
  
- Eine Möglichkeit, einen Pfadverlaufspinsel <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> anzupassen, besteht darin, seine Eigenschaft festzulegen. Die Fokussierungen geben einen inneren Pfad an, der innerhalb des Hauptpfads liegt. Die Mittlere Farbe wird überall innerhalb dieses inneren Pfades angezeigt und nicht nur am Mittelpunkt.  
  
     Im folgenden Beispiel wird ein Pfadverlaufspinsel basierend auf einem elliptischen Pfad erstellt. Der Code legt die Begrenzungsfarbe auf Blau fest, legt die Mittelfarbe auf aqua fest und verwendet dann den Pfadverlaufspinsel, um den elliptischen Pfad zu füllen.  
  
     Als Nächstes legt der Code die Fokussierungen des Pfadverlaufspinsels fest. Die x-Fokusskala ist auf 0,3 und die y-Fokusskala auf 0,8 festgelegt. Der Code <xref:System.Drawing.Graphics.TranslateTransform%2A> ruft die <xref:System.Drawing.Graphics> Methode eines Objekts <xref:System.Drawing.Graphics.FillPath%2A> auf, sodass der nachfolgende Aufruf zum Ausfüllen einer Ellipse, die sich rechts neben der ersten Ellipse befindet, abruft.  
  
     Um die Auswirkungen der Fokusskalen zu sehen, stellen Sie sich eine kleine Ellipse vor, die ihr Zentrum mit der Hauptellipse teilt. Die kleine (innere) Ellipse ist die Hauptellipse, die horizontal um den Faktor 0,3 und vertikal um den Faktor 0,8 skaliert wird. Wenn Sie sich von der Grenze der äußeren Ellipse zur Grenze der inneren Ellipse bewegen, ändert sich die Farbe allmählich von blau zu aqua. Wenn Sie sich von der Grenze der inneren Ellipse zum gemeinsamen Zentrum bewegen, bleibt die Farbe aqua.  
  
     In der folgenden Abbildung ist das Ergebnis des angegebenen Codes dargestellt. Die Ellipse auf der linken Seite ist aqua nur in der Mitte. Die Ellipse auf der rechten Seite ist überall im inneren Pfad aqua.  
  
 ![Gradienteneffekt von Fokusskalen](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>So passen Sie mit der Interpolation an  
  
- Eine andere Möglichkeit zum Anpassen eines Pfadverlaufspinsels besteht darin, ein Array von Interpolationsfarben und ein Array von Interpolationspositionen anzugeben.  
  
     Im folgenden Beispiel wird ein Pfadverlaufspinsel basierend auf einem Dreieck erstellt. Der Code <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> legt die Eigenschaft des Pfadverlaufspinsels fest, um ein Array von Interpolationsfarben (dunkelgrün, aqua, blau) und ein Array von Interpolationspositionen (0, 0,25, 1) anzugeben. Wenn Sie sich von der Grenze des Dreiecks zum Mittelpunkt bewegen, ändert sich die Farbe allmählich von dunkelgrün zu aqua und dann von aqua zu blau. Der Wechsel von dunkelgrün zu aqua erfolgt in 25 Prozent des Abstands von dunkelgrün zu blau.  
  
     Die folgende Abbildung zeigt das Dreieck, das mit dem benutzerdefinierten Pfadverlaufspinsel gefüllt ist.  
  
     ![Dreieck gefüllt mit benutzerdefiniertem Pfadgradientenpinsel.](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>So legen Sie den Mittelpunkt fest  
  
- Standardmäßig befindet sich der Mittelpunkt eines Pfadverlaufspinsels am Schwerpunkt des Pfads, der zum Erstellen des Pinsels verwendet wird. Sie können die Position des Mittelpunkts <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> ändern, <xref:System.Drawing.Drawing2D.PathGradientBrush> indem Sie die Eigenschaft der Klasse festlegen.  
  
     Im folgenden Beispiel wird ein Pfadverlaufspinsel basierend auf einer Ellipse erstellt. Die Mitte der Ellipse ist bei (70, 35), aber der Mittelpunkt des Pfadgradientenpinsels ist auf (120, 40) gesetzt.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     Die folgende Abbildung zeigt die gefüllte Ellipse und den Mittelpunkt des Pfadverlaufspinsels:  
  
     ![Gradientenpfad mit gefüllter Ellipse und Mittelpunkt.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
- Sie können den Mittelpunkt eines Pfadverlaufspinsels auf eine Position außerhalb des Pfads festlegen, der zum Erstellen des Pinsels verwendet wurde. Im folgenden Beispiel wird der <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> Aufruf zum Festlegen der Eigenschaft im vorherigen Code ersetzt.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     Die folgende Abbildung zeigt die Ausgabe mit dieser Änderung:  
  
     ![Gradientenpfad mit Mittelpunkt außerhalb des Pfads.](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     In der obigen Abbildung sind die Punkte ganz rechts der Ellipse nicht rein blau (obwohl sie sehr nahe sind). Die Farben im Farbverlauf werden so positioniert, als ob die Füllung den Punkt (145, 35) erreicht hätte, an dem die Farbe reinblau (0, 0, 255) wäre. Aber die Füllung erreicht nie (145, 35), weil ein Pfadgradientenpinsel nur innerhalb seines Pfades malt.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Die vorherigen Beispiele sind für die Verwendung <xref:System.Windows.Forms.PaintEventArgs> `e`mit Windows Forms konzipiert <xref:System.Windows.Forms.Control.Paint> und erfordern , was ein Parameter des Ereignishandlers ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen](using-a-gradient-brush-to-fill-shapes.md)
