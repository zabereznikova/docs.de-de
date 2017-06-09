---
title: "Gewusst wie: Erstellen eines linearen Pfadfarbverlaufs | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Farbverläufe, Erstellen eines Pfads"
  - "Grafikpfade, Erstellen eines Farbverlaufs"
  - "Pfadfarbverläufe, Erstellen"
ms.assetid: 1948e834-e104-481c-b71d-d8aa9e4d106e
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Gewusst wie: Erstellen eines linearen Pfadfarbverlaufs
Mit der <xref:System.Drawing.Drawing2D.PathGradientBrush>\-Klasse können Sie die Art und Weise anpassen, in der eine Form mit einem graduellen Farbwechsel ausgefüllt wird.  Sie können beispielsweise eine Farbe für die Mitte eines Pfades und eine andere Farbe für die Begrenzung eines Pfades festlegen.  Außerdem können Sie für verschiedene Punkte entlang der Pfadbegrenzung jeweils eine andere Farbe angeben.  
  
> [!NOTE]
>  In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ist ein Pfad eine Abfolge von Linien und Kurven, die von einem <xref:System.Drawing.Drawing2D.GraphicsPath>\-Objekt verwaltet werden.  Weitere Informationen zu Pfaden in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] finden Sie unter [Grafikpfade in GDI\+](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md) und unter [Erstellen und Zeichnen von Pfaden](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md).  
  
### So füllen Sie eine Ellipse mit einem Pfadfarbverlauf aus  
  
-   Im folgenden Beispiel wird eine Ellipse mit einem Pinsel mit Pfadfarbverlauf ausgefüllt.  Als Innenfarbe wird Blau und als Farbe der Begrenzung Hellblau festgelegt.  In der folgenden Abbildung ist die ausgefüllte Ellipse dargestellt.  
  
     ![Farbverlaufspfad](../../../../docs/framework/winforms/advanced/media/pathgradient1.png "pathgradient1")  
  
     In der Standardeinstellung kann ein Pinsel mit Pfadfarbverlauf nicht außerhalb der Pfadbegrenzung eingesetzt werden.  Wenn Sie mithilfe eines Pinsels mit Pfadfarbverlauf eine Form ausfüllen möchten, die die Pfadbegrenzung überschreitet, wird der Bildschirmbereich außerhalb des Pfads nicht ausgefüllt.  
  
     Die folgende Abbildung zeigt das Ergebnis, wenn Sie den <xref:System.Drawing.Graphics.FillEllipse%2A>\-Aufruf im folgenden Code in `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)` ändern.  
  
     ![Farbverlaufspfad](../../../../docs/framework/winforms/advanced/media/pathgradient2.png "pathgradient2")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     Das vorangehende Codebeispiel ist für die Verwendung mit Windows Forms vorgesehen und erfordert <xref:System.Windows.Forms.PaintEventArgs>, einen Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
### So legen Sie Punkte auf der Begrenzung fest  
  
-   Im folgenden Beispiel wird ein Pinsel mit Pfadfarbverlauf auf der Grundlage eines sternförmigen Pfades erstellt.  Durch den Code wird die <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A>\-Eigenschaft festgelegt, mit der Rot als Farbe des Sternschwerpunkts festgelegt wird.  Anschließend wird durch den Code die <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A>\-Eigenschaft festgelegt, um für die einzelnen Punkte im `colors`\-Array verschiedene \(im `points`\-Array gespeicherte\) Farben anzugeben.  Durch die letzte Codeanweisung wird der sternförmige Pfad mithilfe des Pinsels mit Pfadfarbverlauf ausgefüllt.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
-   Im folgenden Beispiel wird ein Pfadfarbverlauf ohne ein <xref:System.Drawing.Drawing2D.GraphicsPath>\-Objekt im Code gezeichnet.  Der spezielle <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A>\-Konstruktor in diesem Beispiel empfängt ein Array aus Punkten, benötigt jedoch kein <xref:System.Drawing.Drawing2D.GraphicsPath>\-Objekt.  Beachten Sie außerdem, dass mit dem <xref:System.Drawing.Drawing2D.PathGradientBrush>\-Pinsel ein Rechteck ausgefüllt wird und kein Pfad.  Das Rechteck ist größer als der geschlossene Pfad, der zum Definieren des Pinsels verwendet wird, daher wird ein Teil des Rechtecks nicht mit dem Pinsel ausgefüllt.  In der folgenden Abbildung sind das Rechteck \(punktierte Linie\) und der Bereich des Rechtecks dargestellt, der mit dem Pinsel mit Pfadfarbverlauf ausgefüllt wird.  
  
     ![Farbverlauf](../../../../docs/framework/winforms/advanced/media/gradient4.png "gradient4")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### So passen Sie einen Pfadfarbverlauf an  
  
-   Eine Möglichkeit zum Anpassen eines Pinsels mit Pfadfarbverlauf besteht darin, die <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A>\-Eigenschaft festzulegen.  Die Fokusskalierung gibt einen inneren Pfad an, der innerhalb des Hauptpfades liegt.  Die Innenfarbe wird im ganzen Bereich innerhalb des inneren Pfades angezeigt, nicht nur im Mittelpunkt.  
  
     Im folgenden Beispiel wird ein Pinsel mit Pfadfarbverlauf auf der Grundlage eines elliptischen Pfades erstellt.  Durch den Code wird als Farbe der Begrenzung Blau und als Innenfarbe Hellblau festgelegt. Anschließend wird der elliptische Pfad mit dem Pinsel mit Pfadfarbverlauf ausgefüllt.  
  
     Als nächstes wird durch den Code die Fokusskalierung des Pinsels mit Pfadfarbverlauf festgelegt.  Als x\-Fokusskalierung wird 0,3 und als y\-Fokusskalierung wird 0,8 festgelegt.  Der Code ruft die <xref:System.Drawing.Graphics.TranslateTransform%2A>\-Methode eines <xref:System.Drawing.Graphics>\-Objekts auf, sodass der nachfolgende Aufruf von <xref:System.Drawing.Graphics.FillPath%2A> eine Ellipse ausfüllt, die sich rechts von der ersten Ellipse befindet.  
  
     Um sich die Auswirkung der Fokusskalierung zu vergegenwärtigen, stellen Sie sich eine kleine Ellipse vor, die den gleichen Mittelpunkt hat wie die Hauptellipse.  Die kleine \(innere\) Ellipse entspricht der Hauptellipse, die \(um den eigenen Mittelpunkt\) in horizontaler Richtung um den Faktor 0.3 und in vertikaler Richtung um den Faktor 0.8 skaliert wurde.  Auf dem Weg von der Begrenzung der äußeren Ellipse zur Begrenzung der inneren Ellipse ändert sich die Farbe graduell von Blau zu Hellblau.  Von der Begrenzung der inneren Ellipse zum Mittelpunkt der beiden Ellipsen bleibt die Farbe unverändert Hellblau.  
  
     In der nachstehenden Abbildung ist das Ergebnis des folgenden Codes dargestellt.  Die linke Ellipse ist nur im Mittelpunkt hellblau.  Die rechte Ellipse ist im ganzen Bereich innerhalb des inneren Pfades hellblau.  
  
 ![Farbverlauf](../../../../docs/framework/winforms/advanced/media/focusscales1nogamma.png "focusscales1NoGamma")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### So passen Sie mithilfe von Interpolation an  
  
-   Eine weitere Möglichkeit, einen Pinsel mit Pfadfarbverlauf anzupassen, besteht darin, ein Array von Interpolationsfarben und ein Array von Interpolationspositionen festzulegen.  
  
     Im folgenden Beispiel wird ein Pinsel mit Pfadfarbverlauf auf der Grundlage eines Dreiecks erstellt.  Der Code legt für einen Pinsel mit Pfadfarbverlauf die <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A>\-Eigenschaft fest, um ein Array von Interpolationsfarben \(Dunkelgrün, Hellblau, Blau\) und ein Array von Interpolationspositionen \(0, 0.25, 1\) anzugeben.  Von der Begrenzung des Dreiecks zu seinem Mittelpunkt ändert sich die Farbe graduell von Dunkelgrün zu Hellblau und dann von Hellblau zu Blau.  Der Wechsel von Dunkelgrün zu Hellblau vollzieht sich auf einer Strecke, die 25 Prozent der Entfernung von Dunkelgrün nach Blau ausmacht.  
  
     In der folgenden Abbildung ist das Dreieck dargestellt, das mit dem benutzerdefinierten Pinsel mit Pfadfarbverlauf ausgefüllt wurde.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### So legen Sie den Mittelpunkt fest  
  
-   Der Mittelpunkt des Pfadfarbverlaufs liegt standardmäßig auf dem Schwerpunkt des Pfades, der zum Erstellen des Pinsels verwendet wird.  Sie können die Position des Mittelpunkts ändern, indem Sie die <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A>\-Eigenschaft der <xref:System.Drawing.Drawing2D.PathGradientBrush>\-Klasse festlegen.  
  
     Im folgenden Beispiel wird ein Pinsel mit Pfadfarbverlauf auf der Grundlage einer Ellipse erstellt.  Der Mittelpunkt der Ellipse liegt bei \(70, 35\), der Mittelpunkt des Pfadfarbverlaufs wird jedoch auf \(120, 40\) festgelegt.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     In der folgenden Abbildung sind die ausgefüllte Ellipse und der Mittelpunkt des Pfadfarbverlaufs dargestellt.  
  
     ![Farbverlaufspfad](../../../../docs/framework/winforms/advanced/media/pathgradient5.png "pathgradient5")  
  
-   Als Mittelpunkt des Pfadfarbverlaufs kann auch eine Position außerhalb des Pfades, der zum Erstellen des Pinsels verwendet wird, festgelegt werden.  Im folgenden Beispiel wird der im vorherigen Beispiel verwendete Aufruf zum Festlegen der <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A>\-Eigenschaft ersetzt.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     In der folgenden Abbildung ist das Ergebnis nach der Änderung dargestellt.  
  
     ![Farbverlaufspfad](../../../../docs/framework/winforms/advanced/media/pathgradient6.png "pathgradient6")  
  
     Die Farbe der Punkte, die sich in der obigen Abbildung ganz rechts in der Ellipse befinden, entspricht keinem reinen Blau \(obwohl sie nicht weit davon entfernt ist\).  Die Farben im Farbverlauf werden so positioniert, als würde die Füllung den Punkt \(145, 35\) erreichen, der ein reines Blau \(0, 0, 255\) darstellt.  Die Füllung erreicht jedoch niemals \(145, 35\), da ein Pinsel mit Pfadfarbverlauf nur innerhalb seiner Pfadgrenzen zeichnen kann.  
  
## Kompilieren des Codes  
 Die vorangehenden Beispiele sind für die Verwendung mit Windows Forms konzipiert und erfordern <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  
  
## Siehe auch  
 [Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)