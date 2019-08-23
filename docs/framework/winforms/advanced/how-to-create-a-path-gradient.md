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
ms.openlocfilehash: 8399a56fca87704e10456a4cf8109d7c80d4db45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964405"
---
# <a name="how-to-create-a-path-gradient"></a>Vorgehensweise: Erstellen eines linearen Pfadfarbverlaufs
Mit <xref:System.Drawing.Drawing2D.PathGradientBrush> der-Klasse können Sie die Art und Weise anpassen, in der Sie eine Form ausfüllen. Sie können z. b. eine Farbe für den Mittelpunkt eines Pfades und eine andere Farbe für die Grenze eines Pfads angeben. Sie können auch separate Farben für jeden der einzelnen Punkte entlang der Grenze eines Pfads angeben.  
  
> [!NOTE]
> In GDI+ ist ein Pfad eine Sequenz von Linien und Kurven, die von einem <xref:System.Drawing.Drawing2D.GraphicsPath> -Objekt verwaltet werden. Weitere Informationen zu GDI+-Pfaden finden Sie unter [Grafik Pfade in GDI+](graphics-paths-in-gdi.md) und [Erstellen und Zeichnen von Pfaden](constructing-and-drawing-paths.md).  

Die Beispiele in diesem Artikel sind Methoden, die vom- <xref:System.Windows.Forms.Control.Paint> Ereignishandler eines Steuer Elements aufgerufen werden.  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>So füllen Sie eine Ellipse mit einem Pfad Farbverlauf aus  
  
- Im folgenden Beispiel wird eine Ellipse mit einem Pfad Farbverlaufs Pinsel gefüllt. Die Mittel Farbe ist auf Blau festgelegt, und die Begrenzungs Farbe ist auf Aqua festgelegt. Die folgende Abbildung zeigt die gefüllte Ellipse.  
  
     ![Der Farbverlaufs Pfad füllt eine Ellipse aus.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     Standardmäßig wird der Pinsel mit dem Pfad Farbverlauf nicht außerhalb der Grenze des Pfads erweitert. Wenn Sie den Pfad Farbverlaufs Pinsel zum Auffüllen einer Abbildung verwenden, die über die Grenze des Pfads hinausgeht, wird der Bereich des Bildschirms außerhalb des Pfades nicht aufgefüllt.  
  
     In der folgenden Abbildung wird gezeigt, was geschieht, <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`Wenn Sie den-Befehl im folgenden Code in ändern:  
  
     ![Der Farbverlaufs Pfad wurde über die Grenze des Pfades hinaus erweitert.](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     Das vorangehende Codebeispiel wurde für die Verwendung mit Windows Forms entwickelt und erfordert den <xref:System.Windows.Forms.PaintEventArgs> e, bei dem es sich um <xref:System.Windows.Forms.PaintEventHandler>einen Parameter von handelt.  
  
### <a name="to-specify-points-on-the-boundary"></a>So geben Sie Punkte auf der Grenze an  
  
- Im folgenden Beispiel wird ein Pfad Farbverlaufs Pinsel aus einem sternförmigen Pfad konstruiert. Der Code legt die <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> -Eigenschaft fest, die die Farbe am Schwerpunkt des Stern auf rot festlegt. Anschließend legt der Code die <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> -Eigenschaft fest, um verschiedene Farben ( `colors` im Array gespeichert) an `points` den einzelnen Punkten im Array anzugeben. Die abschließende Code Anweisung füllt den sternförmigen Pfad mit dem Pfad Farbverlaufs Pinsel.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
- Im folgenden Beispiel wird ein Pfad Farbverlauf ohne <xref:System.Drawing.Drawing2D.GraphicsPath> ein-Objekt im Code gezeichnet. Der bestimmte <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> Konstruktor im Beispiel empfängt ein Array von Punkten, <xref:System.Drawing.Drawing2D.GraphicsPath> erfordert jedoch kein-Objekt. Beachten Sie außerdem, dass <xref:System.Drawing.Drawing2D.PathGradientBrush> verwendet wird, um ein Rechteck auszufüllen, nicht um einen Pfad. Das Rechteck ist größer als der geschlossene Pfad, mit dem der Pinsel definiert wird, sodass ein Teil des Rechtecks nicht durch den Pinsel gezeichnet wird. Die folgende Abbildung zeigt das Rechteck (gepunktete Linie) und den Teil des Rechtecks, das durch den Pfad Farbverlaufs Pinsel gezeichnet wird: 
  
     ![Der vom Pfad Farbverlaufs Pinsel gezeichnete Farbverlaufs Teil.](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>So passen Sie einen Pfad Farbverlauf an  
  
- Eine Möglichkeit, einen Pfad Farbverlaufs Pinsel anzupassen, besteht <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> darin, seine-Eigenschaft festzulegen. Die Fokus Skalen geben einen inneren Pfad an, der sich innerhalb des Haupt Pfads befindet. Die Mittel Farbe wird überall innerhalb dieses inneren Pfades anstelle des Mittelpunkts angezeigt.  
  
     Im folgenden Beispiel wird ein Pfad Farbverlaufs Pinsel auf der Grundlage eines elliptischen Pfads erstellt. Der Code legt die Begrenzungs Farbe auf blau fest, legt die Mittel Farbe auf Aqua fest und verwendet dann den Pfad Farbverlaufs Pinsel, um den Ellipsen Pfad auszufüllen.  
  
     Als nächstes legt der Code die Fokus Skalen des Pinsel mit dem Pfad Farbverlauf fest. Die x-Fokus Skala ist auf 0,3 festgelegt, und die y-Fokus Skala ist auf 0,8 festgelegt. Der Code Ruft die <xref:System.Drawing.Graphics.TranslateTransform%2A> -Methode <xref:System.Drawing.Graphics> eines-Objekts auf <xref:System.Drawing.Graphics.FillPath%2A> , sodass der nachfolgende Aufruf von eine Ellipse füllt, die sich rechts von der ersten Ellipse befindet.  
  
     Um die Auswirkung der Fokus Skalen anzuzeigen, stellen Sie sich eine kleine Ellipse vor, die das Zentrum mit der Haupt Ellipse teilt. Die kleine (innere) Ellipse ist die Hauptellipse, die horizontal um den Faktor 0,3 und vertikal um den Faktor 0,8 skaliert wird. Wenn Sie von der Grenze der äußeren Ellipse zur Grenze der inneren Ellipse wechseln, ändert sich die Farbe allmählich von blau zu Aqua. Wenn Sie von der Begrenzung der inneren Ellipse zum Shared Center wechseln, bleibt die Farbe Aqua.  
  
     In der folgenden Abbildung ist das Ergebnis des angegebenen Codes dargestellt. Die Ellipse auf der linken Seite ist nur für Aqua am Mittelpunkt. Die Ellipse auf der rechten Seite ist Aqua Everywhere innerhalb des inneren Pfades.  
  
 ![Farbverlaufs Effekt von Fokus Skalen](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>So passen Sie mit Interpolations an  
  
- Eine andere Möglichkeit zum Anpassen eines Farbverlaufs Pinsels besteht darin, ein Array von Interpolations Farben und ein Array von Interpolations Positionen anzugeben.  
  
     Im folgenden Beispiel wird ein auf einem Dreieck basierender Pfad Farbverlauf erstellt. Mit dem Code wird <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> die-Eigenschaft des Farbverlaufs Pinsels festgelegt, um ein Array von Interpolations Farben (dunkelgrün, Aqua, Blue) und ein Array von Interpolations Positionen (0, 0,25, 1) anzugeben. Wenn Sie von der Grenze des Dreiecks zum Mittelpunkt wechseln, ändert sich die Farbe allmählich von Dunkelgrün zu Aqua und dann von Aqua zu blau. Die Änderung von Dunkelgrün zu Aqua erfolgt in 25 Prozent der Entfernung von Dunkelgrün zu blau.  
  
     Die folgende Abbildung zeigt das Dreieck, das mit dem benutzerdefinierten Pfad Farbverlaufs Pinsel gefüllt ist.  
  
     ![Dreieck mit benutzerdefiniertem Pfad Farbverlaufs Pinsel.](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>So legen Sie den Mittelpunkt fest  
  
- Standardmäßig befindet sich der Mittelpunkt eines Pfad Farbverlaufs Pinsels im Schwerpunkt des Pfads, der zum Erstellen des Pinsels verwendet wird. Sie können den Speicherort des Mittelpunkts ändern, indem Sie <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> die-Eigenschaft <xref:System.Drawing.Drawing2D.PathGradientBrush> der-Klasse festlegen.  
  
     Im folgenden Beispiel wird ein auf einer Ellipse basierender Pfad Farbverlauf erstellt. Der Mittelpunkt der Ellipse liegt bei (70, 35), aber der Mittelpunkt des Farbverlaufs Pinsels ist auf (120, 40) festgelegt.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     Die folgende Abbildung zeigt die gefüllte Ellipse und den Mittelpunkt des Pfads für den Pfad Farbverlauf:  
  
     ![Der Farbverlaufs Pfad mit ausgefüllter Ellipse und Mittelpunkt.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
- Sie können den Mittelpunkt eines Farbverlaufs Pinsels auf einen Speicherort außerhalb des Pfads festlegen, der zum Erstellen des Pinsels verwendet wurde. Im folgenden Beispiel wird der-Befehl ersetzt, <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> um die-Eigenschaft im vorangehenden Code festzulegen.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     Die folgende Abbildung zeigt die Ausgabe mit dieser Änderung:  
  
     ![Der Farbverlaufs Pfad mit dem Mittelpunkt außerhalb des Pfads.](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     In der obigen Abbildung sind die Punkte ganz rechts von der Ellipse nicht rein blau (obwohl Sie sehr nah sind). Die Farben im Farbverlauf werden so positioniert, als ob das Ausfüllen den Punkt erreicht hat (145, 35), bei dem die Farbe rein blau (0,0) ist (0, 0, 255). Die Füllung erreicht jedoch nie (145, 35), da ein Pfad Farbverlaufs Pinsel nur innerhalb des Pfads zeichnet.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Die vorhergehenden Beispiele sind für die Verwendung mit Windows Forms konzipiert und erfordern <xref:System.Windows.Forms.PaintEventArgs> `e`, was ein Parameter des <xref:System.Windows.Forms.Control.Paint> Ereignis Handlers ist.  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen](using-a-gradient-brush-to-fill-shapes.md)
