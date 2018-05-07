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
ms.openlocfilehash: a3a23d382e199b7ec70a8605041f7e464d1bffe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-path-gradient"></a>Gewusst wie: Erstellen eines linearen Pfadfarbverlaufs
Die <xref:System.Drawing.Drawing2D.PathGradientBrush> -Klasse ermöglicht es Ihnen die Möglichkeit, die Sie ausfüllen einer Form mit allmählich Ändern der Farben anpassen. Beispielsweise können Sie eine Farbe für den Mittelpunkt eines Pfads und eine andere Farbe für die Grenze eines Pfads angeben. Sie können auch separate Farben für jede mehrere Punkte entlang der Grenze eines Pfads angeben.  
  
> [!NOTE]
>  In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], ein Pfads ist eine Sequenz von Linien und Kurven von verwaltet eine <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt. Weitere Informationen zu [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Aktualisierungspfaden finden Sie unter [Grafikpfade in GDI +](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md) und [Constructing und Zeichnen von Pfaden](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md).  
  
### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>Zum Auffüllen einer Ellipse, die mit eines linearen Pfadfarbverlaufs  
  
-   Das folgende Beispiel füllt eine Ellipse mit einem Pinsel mit Farbverlauf. Die Farbe in der Mitte Blau und Farbe der Begrenzung Hellblau festgelegt ist. Die folgende Abbildung zeigt das ausgefüllte Ellipse.  
  
     ![Farbverlaufspfad](../../../../docs/framework/winforms/advanced/media/pathgradient1.png "pathgradient1")  
  
     Standardmäßig erweitert ein Pinsel mit Farbverlauf nicht außerhalb der Grenzen des Pfads. Wenn Sie Pfadfarbverlaufs verwenden, um eine Abbildung zu füllen, die die Grenze des Pfads überschreitet, wird der Bereich des Bildschirms außerhalb des Pfads nicht aufgefüllt.  
  
     Die folgende Abbildung zeigt, was geschieht, wenn Sie ändern, die <xref:System.Drawing.Graphics.FillEllipse%2A> rufen Sie in den folgenden Code hinzu `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`.  
  
     ![Farbverlaufspfad](../../../../docs/framework/winforms/advanced/media/pathgradient2.png "pathgradient2")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     Im vorangehenden Codebeispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> e, die ein Parameter ist der <xref:System.Windows.Forms.PaintEventHandler>.  
  
### <a name="to-specify-points-on-the-boundary"></a>Punkte für die Grenze angeben.  
  
-   Das folgende Beispiel erstellt eine Pfadfarbverlaufs aus einem Pfad sternförmiger. Der Code legt die <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> -Eigenschaft, die die Farbe auf den Schwerpunkt des Sterns Rot festlegt. Anschließend legt der Code die <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> Eigenschaft verschiedener Farben angeben (gespeichert der `colors` Array) an den einzelnen Positionen im die `points` Array. Das endgültige Code-Anweisung füllt den sternförmiger Pfad mit dem Pinsel mit Farbverlauf.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
-   Im folgende Beispiel zeichnet ein linearen Pfadfarbverlaufs ohne eine <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt im Code. Die jeweilige <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> Konstruktor in diesem Beispiel empfängt ein Array von Punkten, erfordert aber kein <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt. Beachten Sie außerdem, dass die <xref:System.Drawing.Drawing2D.PathGradientBrush> wird verwendet, um ein Rechteck, keinen Pfad zu füllen. Das Rechteck ist größer als der geschlossenen Pfad verwendet, um den Pinsel definieren, damit einige des Rechtecks nicht durch den Pinsel gezeichnet wird. Die folgende Abbildung zeigt das Rechteck (gepunktete Linie) und der Teil der mit Pfadfarbverlaufs gezeichnetes Rechteck.  
  
     ![Farbverlauf](../../../../docs/framework/winforms/advanced/media/gradient4.png "gradient4")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>Anpassen ein linearen Pfadfarbverlaufs  
  
-   Eine Möglichkeit, einen Pinsel mit Farbverlauf anzupassen ist, legen Sie dessen <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> Eigenschaft. Die Skalierungen Fokus geben Sie einen inneren Pfad, der innerhalb der Hauptausführungspfad liegt. Die Farbe in der Mitte wird überall innerhalb des inneren Pfades statt nur im Mittelpunkt angezeigt.  
  
     Im folgende Beispiel wird basierend auf einem Pfad elliptischen Pfadfarbverlaufs erstellt. Der Code legt die Farbe der Begrenzung Blau, legt die Farbe in der Mitte Hellblau und klicken Sie dann Pfadfarbverlaufs zum Ausfüllen des elliptischen Pfads verwendet.  
  
     Als Nächstes wird durch den Code der Fokus Größenordnungen Pfadfarbverlaufs. X Fokus Skala 0,3 festgelegt ist, und die y-Skala den Fokus auf 0,8 festgelegt ist. Der Code Ruft die <xref:System.Drawing.Graphics.TranslateTransform%2A> Methode eine <xref:System.Drawing.Graphics> Objekt, damit nachfolgenden Aufruf an <xref:System.Drawing.Graphics.FillPath%2A> füllt eine Ellipse, die rechts neben die erste Ellipse befindet.  
  
     Angenommen Sie, um die Auswirkung der Fokus Skalen angezeigt wird, eine kleine Ellipse, die ihren Mittelpunkt und die wichtigsten Ellipse gemeinsam verwendet wird. Kleinere (innere) Ellipse ist die wichtigsten Ellipse skaliert (über ihren Mittelpunkt) horizontal mit dem Faktor 0,3 und vertikal um einen Faktor 0,8. Wenn Sie die Grenze der äußeren Ellipse auf die Begrenzung der inneren Ellipse verschieben, ändert sich die Farbe allmählich von Blau Hellblau. Wie Sie die Grenze der inneren Ellipse des freigegebenen Center, bleibt die Farbe Aqua verschieben.  
  
     In der folgenden Abbildung ist das Ergebnis des angegebenen Codes dargestellt. Ellipse auf der linken Seite ist nur im Mittelpunkt hellblau. Ellipse auf der rechten Seite ist Hellblau überall innerhalb des inneren Pfades.  
  
 ![Farbverlauf](../../../../docs/framework/winforms/advanced/media/focusscales1nogamma.png "focusscales1NoGamma")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>Mit Interpolation anpassen  
  
-   Eine weitere Möglichkeit zum Anpassen einer Pfadfarbverlaufs ist ein Array von Farben und ein Array von Interpolationspositionen an.  
  
     Das folgende Beispiel erstellt einen Pinsel mit Farbverlauf auf der Grundlage eines Dreiecks. Der Code legt die <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> Eigenschaft Pfadfarbverlaufs an ein Array von Farben (Dunkelgrün, Aqua, Blau) und ein Array von Interpolationspositionen (0, 0.25, 1). Sie von der Begrenzung des Dreiecks für den Mittelpunkt verschieben, ändert sich die Farbe graduell von Dunkelgrün Hellblau und dann von Hellblau Blau. Die Änderung von Dunkelgrün Aqua erfolgt in 25 Prozent der Entfernung von Dunkelgrün Blau.  
  
     Die folgende Abbildung zeigt das Dreieck mit benutzerdefinierten Pfadfarbverlaufs gefüllt.  
  
     ![Farbverlaufspfad](../../../../docs/framework/winforms/advanced/media/pathgradient4.png "pathgradient4")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>Den Mittelpunkt festlegen  
  
-   Standardmäßig ist der Mittelpunkt des Pfadfarbverlaufs an der Schwerpunkt des Pfads verwendet, um den Pinsel erstellen. Sie können den Speicherort des Mittelpunkts ändern, durch Festlegen der <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> Eigenschaft von der <xref:System.Drawing.Drawing2D.PathGradientBrush> Klasse.  
  
     Das folgende Beispiel erstellt einen Pinsel mit Farbverlauf auf der Grundlage einer Ellipse, die an. Befindet sich auf die Mitte der Ellipse (70, 35), aber der Mittelpunkt des Pfadfarbverlaufs auf festgelegt ist (120, 40).  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     Die folgende Abbildung zeigt das ausgefüllte Ellipse und der Mittelpunkt des Pfadfarbverlaufs.  
  
     ![Farbverlaufspfad](../../../../docs/framework/winforms/advanced/media/pathgradient5.png "pathgradient5")  
  
-   Sie können den Mittelpunkt des Pfadfarbverlaufs an einen Speicherort außerhalb des Pfads festlegen, die zum Erstellen des Pinsels verwendet wurde. Im folgende Beispiel ersetzt der Aufruf zum Festlegen der <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> Eigenschaft im vorangehenden Code.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     Die folgende Abbildung zeigt die Ausgabe dieser Änderung.  
  
     ![Farbverlaufspfad](../../../../docs/framework/winforms/advanced/media/pathgradient6.png "pathgradient6")  
  
     In der vorherigen Abbildung sind die Punkte ganz rechts in der Ellipse nicht reine Blau (obwohl sie sehr nahe sind). Die Farben im Farbverlauf werden positioniert, als wäre die Füllung für den Punkt (145, 35) erreicht, in dem die Farbe reines Blau (0, 0, 255) wäre. Aber die Füllung nie erreicht (145, 35), da nur innerhalb des Pfads ein Pinsel mit Farbverlauf zeichnet.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Siehe vorstehende Beispiele sind für die Verwendung mit Windows Forms konzipiert und erfordern <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
