---
title: 'Vorgehensweise: Erstellen eines linearen Pfadfarbverlaufs'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- path gradients [Windows Forms], creating
- gradients [Windows Forms], creating path
- graphics paths [Windows Forms], creating gradient
ms.assetid: 1948e834-e104-481c-b71d-d8aa9e4d106e
ms.openlocfilehash: 31a8c68f382f81da2acac363bba6c8822e535770
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186094"
---
# <a name="how-to-create-a-path-gradient"></a>Vorgehensweise: Erstellen eines linearen Pfadfarbverlaufs
Die <xref:System.Drawing.Drawing2D.PathGradientBrush> Klasse können Sie die Möglichkeit, die Sie ausfüllen einer Form nach und nach Ändern von Farben anpassen. Beispielsweise können Sie eine Farbe für den Mittelpunkt der einen Pfad und eine andere Farbe für die Grenze eines Pfads angeben. Sie können auch separate Farben für die einzelnen mehrere Punkte entlang der Grenzen eines Pfads angeben.  
  
> [!NOTE]
>  In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], ein Pfad ist eine Sequenz von Linien und Kurven, die von verwaltet eine <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt. Weitere Informationen zu [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Pfaden finden Sie unter [Grafikpfade in GDI +](graphics-paths-in-gdi.md) und [Constructing und zeichnen Pfade](constructing-and-drawing-paths.md).  
  
### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>Um eine Ellipse mit eines linearen Pfadfarbverlaufs zu füllen.  
  
-   Im folgenden Beispiel wird eine Ellipse mit der ein Pinsel mit Farbverlauf. Die Farbe in der Mitte auf Blau festgelegt und die Mittelpunktfarbe Hellblau festgelegt. Die folgende Abbildung zeigt die ausgefüllte Ellipse.  
  
     ![Farbverlaufspfad füllt eine Ellipse.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     Standardmäßig wird ein Pinsel mit Farbverlauf außerhalb der Grenzen des Pfads nicht erweitert. Wenn Sie Pfadfarbverlaufs verwenden, um einer Figur zu füllen, die über die Begrenzung des Pfads hinausgeht, wird der Bereich des Bildschirms außerhalb des Pfads wird nicht aufgefüllt.  
  
     Die folgende Abbildung zeigt, was geschieht, wenn Sie ändern, die <xref:System.Drawing.Graphics.FillEllipse%2A> rufen Sie in den folgenden Code zur `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`:  
  
     ![Farbverlaufspfad außerhalb der Grenzen des Pfads erweitert.](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     Das vorherige Codebeispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> e, die ein Parameter ist der <xref:System.Windows.Forms.PaintEventHandler>.  
  
### <a name="to-specify-points-on-the-boundary"></a>Punkte für die Grenze angeben.  
  
-   Im folgende Beispiel wird einen Pinsel mit Farbverlauf aus einem Pfad sternförmiger erstellt. Der Code legt die <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> -Eigenschaft, die die Farbe auf den Schwerpunkt des Sterns in Rot festlegt. Dann legt der Code die <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> Eigenschaft, um verschiedene Farben anzugeben (gespeichert der `colors` Array) an den einzelnen Positionen im der `points` Array. Das endgültige Code-Anweisung füllt den sternförmiger Pfad mit dem Pfad Farbverlaufspinsel.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
-   Das folgende Beispiel zeichnet ein linearen Pfadfarbverlaufs ohne eine <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt im Code. Bestimmte <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> Konstruktor in diesem Beispiel empfängt ein Array von Punkten benötigt jedoch keiner <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt. Beachten Sie außerdem, dass die <xref:System.Drawing.Drawing2D.PathGradientBrush> wird verwendet, um ein Rechteck, das keinen Pfad zu füllen. Das Rechteck ist größer als der geschlossenen Pfad verwendet, um den Pinsel, zu definieren, damit einige des Rechtecks nicht vom Pinsel gezeichnet wird. Die folgende Abbildung zeigt das Rechteck (gepunkteten Linie) und der Teil des Rechtecks gezeichnet, indem Pfadfarbverlaufs: 
  
     ![Farbverlauf Teil von Pfadfarbverlaufs gezeichnet.](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>Zum Anpassen eines linearen Pfadfarbverlaufs  
  
-   Eine Möglichkeit, einen Pinsel mit Farbverlauf anzupassen ist, legen Sie dessen <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> Eigenschaft. Die Skalierungen Fokus geben Sie einen internen Pfad, die sich innerhalb der Hauptausführungspfad. Die Farbe in der Mitte wird überall innerhalb des inneren Pfades und nicht nur auf den Mittelpunkt angezeigt.  
  
     Das folgende Beispiel erstellt einen Pinsel mit Farbverlauf auf der Grundlage einen elliptischen Pfads. Der Code wird die Grenze Farbe in Blau, legt die Farbe in der Mitte zu Hellblau und verwendet dann Pfadfarbverlaufs zum Ausfüllen des elliptischen Pfads.  
  
     Als Nächstes legt der Code die Skalierungen Fokus des Farbverlaufspinsels Pfad fest. Die X-Fokusskalierung 0,3 festgelegt ist, und die Skalierung des y den Fokus auf 0,8 festgelegt ist. Der Code Ruft die <xref:System.Drawing.Graphics.TranslateTransform%2A> -Methode der ein <xref:System.Drawing.Graphics> Objekt, damit der nachfolgende Aufruf von <xref:System.Drawing.Graphics.FillPath%2A> wird eine Ellipse, die sich rechts neben die erste Ellipse befindet.  
  
     Angenommen Sie, um die Auswirkungen der Fokus Skalen anzuzeigen, eine kleine Ellipse, die für die wichtigsten Ellipse freigegeben hat seinen Mittelpunkt. Kleinere (innere) Ellipse ist die wichtigsten Ellipse (über ihren Mittelpunkt) das horizontal mit einem Faktor von 0.3 und vertikal um den Faktor 0,8 skaliert. Wenn Sie von der Begrenzung der äußeren Ellipse an der Begrenzung des inneren Ellipse bewegen, ändert die Farbe allmählich von Blau zu Hellblau. Wie Sie von der Begrenzung des inneren Ellipse zum freigegebenen Center, bleibt die Farbe Aquamarin verschieben.  
  
     In der folgenden Abbildung ist das Ergebnis des angegebenen Codes dargestellt. Ellipse auf der linken Seite ist Aqua nur auf den Mittelpunkt. Ellipse auf der rechten Seite ist Aqua überall innerhalb des inneren Pfads.  
  
 ![Der Fokus Skalen Farbverlaufseffekt](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>Bei der Interpolation anpassen  
  
-   Eine weitere Möglichkeit zum Anpassen von eines Pinsels mit Farbverlauf ist ein Array von Farben und ein Array von Interpolationspositionen an.  
  
     Das folgende Beispiel erstellt einen Pinsel mit Farbverlauf auf der Grundlage eines Dreiecks. Der Code legt die <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> Eigenschaft des Pfadfarbverlaufs an ein Array von Farben (Dunkelgrün, Aqua, Blau) und ein Array von Interpolationspositionen ("0", "0.25", "1"). Während Sie von der Begrenzung des Dreiecks auf den Mittelpunkt bewegen, ändert die Farbe allmählich von Dunkelgrün Hellblau und dann von Aqua in Blau. Die Änderung von Dunkelgrün Aqua erfolgt in 25 Prozent der Entfernung von Dunkelgrün in Blau.  
  
     Die folgende Abbildung zeigt das Dreieck mit benutzerdefinierten Pfadfarbverlaufs gefüllt.  
  
     ![Dreieck wird mit benutzerdefinierter Pfad Farbverlaufspinsel gefüllt.](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>Den Mittelpunkt festlegen  
  
-   Wird standardmäßig der Mittelpunkt des Pfadfarbverlaufs an den Schwerpunkt des Pfads verwendet, um den Pinsel zu erstellen. Sie können den Speicherort des Mittelpunkts ändern, durch Festlegen der <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> Eigenschaft der <xref:System.Drawing.Drawing2D.PathGradientBrush> Klasse.  
  
     Das folgende Beispiel erstellt einen Pinsel mit Farbverlauf auf der Grundlage einer Ellipse an. Der Mittelpunkt der Ellipse ist (70, 35), aber auf der Mittelpunkt des Pfadfarbverlaufs festgelegt ist ("120", "40").  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     Die folgende Abbildung zeigt die ausgefüllte Ellipse und den Mittelpunkt des Pfadfarbverlaufs:  
  
     ![Farbverlaufspfad mit gefüllte Ellipse und Center Punkt.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
-   Sie können den Mittelpunkt des Pfadfarbverlaufs an einem Speicherort außerhalb des Pfads festlegen, die zum Erstellen des Pinsels verwendet wurde. Im folgenden Beispiel ersetzt der Aufruf zum Festlegen der <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> Eigenschaft im vorangehenden Code.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     Die folgende Abbildung zeigt die Ausgabe durch diese Änderung:  
  
     ![Farbverlaufspfad mit einem Mittelpunkt außerhalb des Pfads.](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     In der vorherigen Abbildung sind die Punkte in der rechten oberen Ecke der Ellipse nicht reines Blau (obwohl sie sehr dicht beieinander liegen). Die Farben im Farbverlauf positioniert sind, als ob die Füllung auf den Punkt (145, 35) erreicht, in dem die Farbe reines Blau (0, 0, 255) wäre. Aber die Füllung nie erreicht (145, 35), da ein Pinsel mit Farbverlauf nur innerhalb des Pfads zeichnet.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Im vorherigen Beispiel sind für die Verwendung mit Windows Forms konzipiert und erfordern <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen](using-a-gradient-brush-to-fill-shapes.md)
