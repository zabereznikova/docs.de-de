---
title: Matrixdarstellung von Transformationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- composite transformations
- transformations [Windows Forms], linear
- matrices
- translations in matrix representation
- transformations [Windows Forms], composite
- vectors
- linear transformations
- transformations [Windows Forms], matrix representation of
- transformations [Windows Forms], translation
- affine transformations
ms.assetid: 0659fe00-9e0c-41c4-9118-016f2404c905
ms.openlocfilehash: ec1feda5547a96a0deac6f9d2e6ba1139e3fa73f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732088"
---
# <a name="matrix-representation-of-transformations"></a>Matrixdarstellung von Transformationen
Eine m-x-n-Matrix ist eine Menge von Zahlen, die in m Zeilen und n Spalten angeordnet sind. Die folgende Abbildung zeigt mehrere Matrizen.  
  
 ![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art04.gif "AboutGdip05_art04")  
  
 Sie können zwei Matrizen der gleichen Größe Hinzufügen einzelner Elemente hinzufügen. Die folgende Abbildung zeigt zwei Beispiele für die Matrix hinzufügen.  
  
 ![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art05.gif "AboutGdip05_art05")  
  
 Eine m-x-n-Matrix kann in einer n x p-Matrix multipliziert werden, und das Ergebnis ist eine m x p-Matrix. Die Anzahl der Spalten in der ersten Matrix muss die Anzahl der Zeilen in der zweiten Matrix identisch sein. Eine 4 x 2-Matrix kann z. B. eine 2 x 3-Matrix zum Erzeugen einer 4 x 3-Matrix multipliziert werden.  
  
 Punkte in der Datenebene und die Zeilen und Spalten einer Matrix können als Vektoren betrachtet werden. Beispielsweise (2, 5) ist ein Vektor mit zwei Komponenten, und (3, 7, 1) ist ein Vektor mit drei Komponenten. Das Skalarprodukt zweier Vektoren wird wie folgt definiert:  
  
 (a, b) • (C, d) = Ac + bd  
  
 (a, b, c) • (d, e, f) = Ad + + Cf  
  
 Z. B. das Skalarprodukt von (2, 3) und (5, 4) ist ((2)(5) + ((3)(4) = 22. Das Skalarprodukt von (2, 5, 1) und (4, 3, 1) ist (2)(4) + (5)(3) + (1)(1) = 24. Beachten Sie, dass das Skalarprodukt von zwei Vektoren eine Zahl, die nicht von einem anderen Vektor. Beachten Sie außerdem, dass Sie das Skalarprodukt berechnen können, nur dann, wenn die beiden Vektoren, die gleiche Anzahl von Komponenten haben.  
  
 Lassen Sie A(i, j) werden den Eintrag in der Matrix ein, in der IT-Zeile und Spalte j. Zum Beispiel ein (3, 2) ist der Eintrag in der Matrix ein, in dem 3. Zeile und der 2. Spalte. Angenommen, A, B und C Matrizen, und AB = C. Die Einträge von C werden wie folgt berechnet:  
  
 C (i, j) = (Zeile i von A) • (Spalte B j)  
  
 Die folgende Abbildung zeigt einige Beispiele für Matrixmultiplikation.  
  
 ![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art06.gif "AboutGdip05_art06")  
  
 Wenn Sie einen Punkt in einer Ebene als eine 1 × 2-Matrix vorstellen, können Sie diesen Punkt transformieren, indem er mit einer 2 × 2-Matrix multipliziert. Die folgende Abbildung zeigt mehrere Transformationen für den Punkt ("2", "1").  
  
 ![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art07.gif "AboutGdip05_art07")  
  
 Alle Transformationen in der obigen Abbildung sind die lineare Transformationen. Bestimmte andere Transformationen, wie die Verschiebung, nicht linear sind, und nicht als Multiplikation mit einer 2 × 2-Matrix ausgedrückt werden. Angenommen, Sie möchten für den Einstieg der Punkt (2, 1), um 90 Grad drehen, 3 Einheiten in X-Richtung und 4 Einheiten in der y-Richtung. Sie erreichen das mithilfe einer Matrixmultiplikation, gefolgt von einer Matrix hinzufügen.  
  
 ![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art08.gif "AboutGdip05_art08")  
  
 Eine lineare Transformation (Multiplikation mit einer 2 × 2-Matrix), gefolgt von einer Übersetzung (Hinzufügen einer 1 × 2-Matrix), wird eine affine Transformation aufgerufen. Eine Alternative zum Speichern von eine affine Transformation in einem Paar von Matrizen (eine für den linearen Teil) und eine für die Übersetzung ist die gesamte Transformation in einer 3 × 3-Matrix zu speichern. Damit dies funktioniert, muss ein Punkt in der Ebene in einer 1 × 3-Matrix mit einer dummy 3. Koordinate gespeichert werden. Die übliche Vorgehensweise ist, alle 3. Koordinaten gleich 1. Beispielsweise wird der Punkt ("2", "1") mit der Matrix [2-1-1] dargestellt. Die folgende Abbildung zeigt eine affine Transformation (um 90 Grad drehen, übersetzen, 3 Einheiten in der X-Richtung, 4 Einheiten in der y-Richtung) als Multiplikation mit einer einzelnen 3 x 3-Matrix.  
  
 ![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art09.gif "AboutGdip05_art09")  
  
 Im vorherigen Beispiel ist der Punkt ("2", "1") auf den Zeitpunkt (2, 6) zugeordnet. Beachten Sie, dass die dritte Spalte von der 3 x 3-Matrix die Ziffern 0, 0, 1 enthält. Dies wird immer der Fall für die 3 x 3-Matrix eine affine Transformation sein. Die wichtigen Zahlen sind die sechs Zahlen in den Spalten 1 und 2. Der linken oberen 2 × 2-Teil der Matrix darstellt, des linearen Teils der Transformation, und die ersten beiden Einträge in der 3. Zeile darstellen, die Übersetzung.  
  
 ![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art10.gif "AboutGdip05_art10")  
  
 In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] können Sie eine affine Transformation in speichern eine <xref:System.Drawing.Drawing2D.Matrix> Objekt. Da immer ist der dritte Spalte der eine Matrix, die eine affine Transformation darstellt (0, 0, 1), Sie nur die sechs Zahlen in den ersten beiden Spalten angeben, wenn Sie erstellen eine <xref:System.Drawing.Drawing2D.Matrix> Objekt. Die Anweisung `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` erstellt die Matrix, die in der obigen Abbildung dargestellt.  
  
## <a name="composite-transformations"></a>Zusammengesetzte Transformationen  
 Eine zusammengesetzte Transformation ist eine Sequenz von Transformationen gefolgt von den anderen. Beachten Sie die Matrizen und Transformationen in der folgenden Liste:  
  
|||  
|-|-|  
|Matrix A|90 Grad drehen|  
|Matrix B|Um den Faktor 2 in der X-Richtung skaliert|  
|Matrix C|3 Einheiten in der y-Richtung verschieben|  
  
 Wenn beginnen wir mit den Punkt ("2", "1"), dargestellt durch die Matrix [2-1-1] – A, B dann multiplizieren, und klicken Sie dann C, die der Punkt (2, 1) die drei Transformationen in der aufgeführten Reihenfolge ausgeführt wird.  
  
 [2 1 1]ABC = [-2 5 1]  
  
 Stattdessen als die drei Teile der zusammengesetzten Transformation in drei separaten Matrizen zu speichern, Multiplizieren Sie A, B und C miteinander um eine einzelne 3 x 3-Matrix abzurufen, die die gesamte zusammengesetzte Transformation gespeichert. Nehmen wir an ABC = D. Ein Punkt, multipliziert mit D gibt dann das gleiche Ergebnis wie einen Punkt, multipliziert mit ein, klicken Sie dann B dann C.  
  
 [2 1 1]D = [-2 5 1]  
  
 Die folgende Abbildung zeigt die Matrizen, A, B, C und D.  
  
 ![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art12.gif "AboutGdip05_art12")  
  
 Die Tatsache, dass die Matrix eine zusammengesetzte Transformation gebildet werden kann, durch die einzelnen Transformationsmatrizen multipliziert bedeutet, dass es sich bei einer beliebigen Folge von affine Transformationen in einer einzelnen gespeichert werden kann <xref:System.Drawing.Drawing2D.Matrix> Objekt.  
  
> [!CAUTION]
>  Die Reihenfolge der eine zusammengesetzte Transformation ist wichtig. Im Allgemeinen zu drehen, skalieren und dann zu übersetzen ist nicht dasselbe wie skalieren, drehen und anschließend zu übersetzen. Die Reihenfolge der Matrixmultiplikation ist ebenso wichtig. ABC ist im Allgemeinen nicht identisch mit PK.  
  
 Die <xref:System.Drawing.Drawing2D.Matrix> Klasse bietet mehrere Methoden zum Erstellen einer zusammengesetzten Transformations: <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>, <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>, <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>, <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>, <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>, und <xref:System.Drawing.Drawing2D.Matrix.Translate%2A>. Im folgende Beispiel wird die Matrix eine zusammengesetzte Transformation, die zuerst eine Drehung um 30 Grad festlegen, und klicken Sie dann mit einem Faktor von 2 in y-Richtung skaliert, und übersetzt dann 5 Einheiten in X-Richtung erstellt:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.CoordinateSystems#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#11)]  
  
 Die folgende Abbildung zeigt die Matrix.  
  
 ![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art13.gif "AboutGdip05_art13")  
  
## <a name="see-also"></a>Siehe auch
- [Koordinatensysteme und Transformationen](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)
- [Verwenden von Transformationen in Managed GDI+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
