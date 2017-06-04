---
title: "Matrixdarstellung von Transformationen | Microsoft Docs"
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
  - "Affine Transformationen"
  - "Zusammengesetzte Transformationen"
  - "Lineare Transformationen"
  - "Matrizen"
  - "Transformationen, Zusammengesetzt"
  - "Transformationen, Linear"
  - "Transformationen, Matrixdarstellung von"
  - "Transformationen, Verschiebung"
  - "Verschiebungen in Matrixdarstellung"
  - "Vektoren"
ms.assetid: 0659fe00-9e0c-41c4-9118-016f2404c905
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Matrixdarstellung von Transformationen
Eine m×n\-Matrix ist eine Gruppe von Zahlen, die in m\-Zeilen und n\-Spalten angeordnet wird.  Die folgende Abbildung zeigt mehrere Matrizen.  
  
 ![Transformationen](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art04.png "AboutGdip05\_art04")  
  
 Sie können zwei gleich große Matrizen addieren, indem Sie einzelne Elemente addieren.  Die folgende Abbildung zeigt zwei Beispiele für die Matrixaddition.  
  
 ![Transformationen](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art05.png "AboutGdip05\_art05")  
  
 Eine m×n\-Matrix kann mit einer n×p\-Matrix multipliziert werden. Das Produkt ist eine m×p\-Matrix.  Die Anzahl der Spalten in der ersten Matrix muss mit der Anzahl der Zeilen in der zweiten Matrix übereinstimmen.  Eine 4×2\-Matrix kann beispielsweise mit einer 2×3\-Matrix multipliziert werden. Das Produkt ist eine 4×3\-Matrix.  
  
 Punkte in der Ebene sowie Zeilen und Spalten in einer Matrix können als Vektoren betrachtet werden.  Beispielsweise ist \(2, 5\) ein Vektor mit zwei Komponenten, und \(3, 7, 1\) ist ein Vektor mit drei Komponenten.  Das Skalarprodukt aus den beiden Vektoren ist wie folgt definiert:  
  
 \(a, b\) • \(c, d\) \= ac \+ bd  
  
 \(a, b, c\) • \(d, e, f\) \= ad \+ be \+ cf  
  
 Beispiele: Das Skalarprodukt aus \(2, 3\) und \(5, 4\) ist \(2\)\(5\) \+ \(3\)\(4\) \= 22.  Das Skalarprodukt aus \(2, 5, 1\) und \(4, 3, 1\) ist \(2\)\(4\) \+ \(5\)\(3\) \+ \(1\)\(1\) \= 24.  Beachten Sie, dass das Skalarprodukt aus zwei Vektoren eine Zahl ist, kein Vektor.  Beachten Sie auch, dass Sie das Skalarprodukt nur dann berechnen können, wenn die beiden Vektoren die gleiche Anzahl an Komponenten enthalten.  
  
 Angenommen, A\(i, j\) ist der Eintrag in Matrix A in Zeile i und Spalte j.  Beispielsweise ist A\(3, 2\) der Eintrag in Matrix A in der 3. Zeile und der 2. Spalte.  Angenommen, A, B und C sind Matrizen, und AB \= C.  Dann werden die Einträge von C wie folgt berechnet:  
  
 C\(i, j\) \= \(Zeile i von A\) • \(Spalte j von B\)  
  
 Die folgende Abbildung zeigt mehrere Beispiele für die Matrixmultiplikation.  
  
 ![Transformationen](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art06.png "AboutGdip05\_art06")  
  
 Wenn Sie sich einen Punkt in einer Ebene als eine 1×2\-Matrix vorstellen, können Sie diesen Punkt transformieren, indem Sie ihn mit einer 2×2\-Matrix multiplizieren.  Die folgende Abbildung zeigt mehrere Transformationen für den Punkt \(2, 1\).  
  
 ![Transformationen](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art07.gif "AboutGdip05\_art07")  
  
 Alle Transformationen in der obigen Abbildung sind lineare Transformationen.  Bestimmte andere Transformationen, z. B. die Verschiebung, sind nicht linear und können nicht als Multiplikation mit einer 2×2\-Matrix ausgedrückt werden.  Angenommen, Sie möchten mit dem Punkt \(2, 1\) beginnen, ihn um 90 Grad drehen, um 3 Einheiten in der x‑Richtung verschieben und dann um 4 Einheiten in der y‑Richtung verschieben.  Verwenden Sie hierzu eine Matrixmultiplikation, gefolgt von einer Matrixaddition.  
  
 ![Transformationen](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art08.gif "AboutGdip05\_art08")  
  
 Eine lineare Transformation \(Multiplikation mit einer 2×2\-Matrix\), gefolgt von einer Verschiebung \(Addition einer 1×2\-Matrix\) wird als affine Transformation bezeichnet.  Eine Alternative zum Speichern einer affinen Transformation in einem Matrixpaar \(eine Matrix für den linearen Teil, eine für die Verschiebung\) besteht darin, die gesamte Transformation in einer 3×3\-Matrix zu speichern.  Damit dies funktioniert, muss ein Punkt in der Ebene in einer 1×3\-Matrix mit einem Dummywert für die dritte Koordinate gespeichert werden.  Die übliche Vorgehensweise besteht darin, alle dritten Koordinaten gleich 1 zu setzen.  Beispiel: Der Punkt \(2, 1\) wird durch die Matrix \[2 1 1\] dargestellt.  Die folgende Abbildung zeigt eine affine Transformation \(um 90 Grad drehen, um 3 Einheiten in der x\-Richtung verschieben, um 4 Einheiten in der y\-Richtung verschieben\), die als Multiplikation mit einer einzigen 3×3\-Matrix ausgedrückt wird.  
  
 ![Transformationen](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art09.png "AboutGdip05\_art09")  
  
 Im obigen Beispiel wird der Punkt \(2, 1\) dem Punkt \(2, 6\) zugeordnet.  Beachten Sie, dass die dritte Spalte der 3×3\-Matrix die Zahlen 0, 0, 1 enthält.  Dies ist für die 3×3\-Matrix einer affinen Transformation immer der Fall.  Die wichtigen Zahlen sind die sechs Zahlen in den Spalten 1 und 2.  Der linke obere 2×2\-Teil der Matrix stellt den linearen Teil der Transformation dar, die ersten beiden Einträge in der dritten Zeile stellen die Verschiebung dar.  
  
 ![Transformationen](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art10.gif "AboutGdip05\_art10")  
  
 In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] können Sie eine affine Transformation in einem <xref:System.Drawing.Drawing2D.Matrix>\-Objekt speichern.  Da die dritte Spalte einer Matrix, die eine affine Transformation darstellt, immer \(0, 0, 1\) ist, geben Sie beim Erstellen eines <xref:System.Drawing.Drawing2D.Matrix>\-Objekts nur die sechs Zahlen in den ersten beiden Spalten an.  Mit der Anweisung `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` wird die in der vorangehenden Abbildung dargestellte Matrix erstellt.  
  
## Zusammengesetzte Transformationen  
 Eine zusammengesetzte Transformation ist eine Folge von Transformationen.  Betrachten Sie die Matrizen und Transformationen in der folgenden Liste:  
  
|||  
|-|-|  
|Matrix A|Um 90 Grad drehen|  
|Matrix B|Um den Faktor 2 in der x‑Richtung skalieren|  
|Matrix C|Um 3 Einheiten in der y‑Richtung verschieben|  
  
 Wenn Sie mit dem Punkt \(2, 1\) beginnen – dargestellt durch die Matrix \[2 1 1\] – und erst mit A, dann mit B und dann mit C multiplizieren, durchläuft der Punkt \(2, 1\) die drei Transformationen in der angegebenen Reihenfolge.  
  
 \[2 1 1\]ABC \= \[\-2 5 1\]  
  
 Anstatt die drei Teile der zusammengesetzten Transformation in drei getrennten Matrizen zu speichern, können Sie A, B und C gemeinsam multiplizieren, um eine einzige 3×3\-Matrix zu erhalten, in der die gesamte zusammengesetzte Transformation gespeichert wird.  Angenommen ABC \= D.  Dann generiert ein mit D multiplizierter Punkt das gleiche Ergebnis wie ein mit A, dann mit B und dann mit C multiplizierter Punkt.  
  
 \[2 1 1\]D \= \[\-2 5 1\]  
  
 Die folgende Abbildung zeigt die Matrizen A, B, C und D.  
  
 ![Transformationen](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art12.png "AboutGdip05\_art12")  
  
 Aufgrund der Tatsache, dass die Matrix einer zusammengesetzten Transformation durch Multiplikation der einzelnen Transformationsmatrizen gebildet werden kann, lässt sich jede beliebige Folge von affinen Transformationen in einem einzigen <xref:System.Drawing.Drawing2D.Matrix>\-Objekt speichern.  
  
> [!CAUTION]
>  Die Reihenfolge innerhalb einer zusammengesetzten Transformation spielt eine wichtige Rolle.  Grundsätzlich ist Drehen, dann Skalieren, dann Verschieben nicht identisch mit Skalieren, dann Drehen, dann Verschieben.  Entsprechend ist die Reihenfolge der Matrixmultiplikation wichtig.  Hierbei gilt: ABC ist nicht identisch mit BAC.  
  
 Die <xref:System.Drawing.Drawing2D.Matrix>\-Klasse bietet mehrere Methoden zum Erstellen einer zusammengesetzten Transformation: <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>, <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>, <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>, <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>, <xref:System.Drawing.Drawing2D.Matrix.Shear%2A> und <xref:System.Drawing.Drawing2D.Matrix.Translate%2A>.  Im folgenden Beispiel wird die Matrix einer zusammengesetzten Transformation erstellt, die zuerst eine Drehung um 30 Grad, dann eine Skalierung um den Faktor 2 in y‑Richtung und anschließend eine Verschiebung um 5 Einheiten in x‑Richtung ausführt:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.CoordinateSystems#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#11)]  
  
 Die folgende Abbildung zeigt diese Matrix.  
  
 ![Transformationen](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art13.png "AboutGdip05\_art13")  
  
## Siehe auch  
 [Koordinatensysteme und Transformationen](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)   
 [Verwenden von Transformationen in Managed GDI\+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)