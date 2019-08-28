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
ms.openlocfilehash: 24da407de24a924a68466e4301cc3f4a74cb2e94
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044249"
---
# <a name="matrix-representation-of-transformations"></a>Matrixdarstellung von Transformationen
Eine m × n-Matrix ist ein Satz von Zahlen, der in m Zeilen und n Spalten angeordnet ist. Die folgende Abbildung zeigt mehrere Matrizen.  
  
 ![Transformationen](./media/aboutgdip05-art04.gif "AboutGdip05_art04")  
  
 Sie können zwei Matrizen derselben Größe hinzufügen, indem Sie einzelne Elemente hinzufügen. Die folgende Abbildung zeigt zwei Beispiele für das Hinzufügen von Matrizen.  
  
 ![Transformationen](./media/aboutgdip05-art05.gif "AboutGdip05_art05")  
  
 Eine m × n-Matrix kann mit einer n × p-Matrix multipliziert werden, und das Ergebnis ist eine m × p-Matrix. Die Anzahl der Spalten in der ersten Matrix muss mit der Anzahl der Zeilen in der zweiten Matrix identisch sein. Beispielsweise kann eine 4 × 2-Matrix mit einer 2 × 3-Matrix multipliziert werden, um eine 4 × 3-Matrix zu schaffen.  
  
 Punkte in der Ebene und die Zeilen und Spalten einer Matrix können als Vektoren betrachtet werden. (2, 5) ist z. b. ein Vektor mit zwei Komponenten, und (3, 7, 1) ist ein Vektor mit drei Komponenten. Das Punktprodukt von zwei Vektoren wird wie folgt definiert:  
  
 (a, b) • (c, d) = AC + BD  
  
 (a, b, c) • (d, e, f) = AD + be + CF  
  
 Beispielsweise ist das Punktprodukt von (2, 3) und (5, 4) (2) (5) + (3) (4) = 22. Das Punktprodukt von (2, 5, 1) und (4, 3, 1) ist (2) (4) + (5) (3) + (1) (1) = 24. Beachten Sie, dass es sich bei dem Punktprodukt zweier Vektoren um eine Zahl, nicht um einen anderen Vektor handelt. Beachten Sie außerdem, dass Sie das Punktprodukt nur berechnen können, wenn die beiden Vektoren über die gleiche Anzahl von Komponenten verfügen.  
  
 Let a (i, j) ist der Eintrag in Matrix A in der Zeile ITH und in der Jth-Spalte. Beispielsweise ist a (3, 2) der Eintrag in Matrix A in der dritten Zeile und in der zweiten Spalte. Angenommen, a, B und C sind Matrizen, und ab = c. Die Einträge von C werden wie folgt berechnet:  
  
 C (i, j) = (Zeile i von a) • (Spalte j von B)  
  
 Die folgende Abbildung zeigt mehrere Beispiele für die Matrix Multiplikation.  
  
 ![Transformationen](./media/aboutgdip05-art06.gif "AboutGdip05_art06")  
  
 Wenn Sie sich einen Punkt in einer Ebene als 1 × 2-Matrix vorstellen, können Sie diesen Punkt transformieren, indem Sie ihn mit einer 2 × 2-Matrix multiplizieren. Die folgende Abbildung zeigt mehrere Transformationen, die auf den Punkt (2, 1) angewendet werden.  
  
 ![Transformationen](./media/aboutgdip05-art07.gif "AboutGdip05_art07")  
  
 Alle in der vorangehenden Abbildung gezeigten Transformationen sind lineare Transformationen. Bestimmte andere Transformationen, z. b. die Übersetzung, sind nicht linear und können nicht durch eine 2 × 2-Matrix als Multiplikation ausgedrückt werden. Angenommen, Sie möchten mit dem Punkt (2, 1) beginnen, ihn um 90 Grad drehen, 3 Einheiten in die x-Richtung übersetzen und vier Einheiten in y-Richtung übersetzen. Dies erreichen Sie mithilfe einer Matrix Multiplikation, gefolgt von einer Matrix Addition.  
  
 ![Transformationen](./media/aboutgdip05-art08.gif "AboutGdip05_art08")  
  
 Eine lineare Transformation (Multiplikation durch eine 2 × 2-Matrix), gefolgt von einer Übersetzung (Addition einer 1 × 2-Matrix), wird als affine Transformation bezeichnet. Eine Alternative zum Speichern einer affinen Transformation in einem Matrizen-Paar (eines für den linearen Teil und eines für die Übersetzung) ist das Speichern der gesamten Transformation in einer 3 × 3-Matrix. Um dies zu ermöglichen, muss ein Punkt in der Ebene in einer 1 × 3-Matrix mit einer Dummy-Dritt-Koordinate gespeichert werden. Die übliche Vorgehensweise besteht darin, alle Dritt-Koordinaten gleich 1 zu erstellen. Der Punkt (2, 1) wird z. b. durch die Matrix [2 1 1] dargestellt. Die folgende Abbildung zeigt eine affine Transformation (Drehen von 90 Grad) und übersetzt 3 Einheiten in der x-Richtung, 4 Einheiten in der y-Richtung), die durch eine einzelne 3 × 3-Matrix als Multiplikation ausgedrückt werden.  
  
 ![Transformationen](./media/aboutgdip05-art09.gif "AboutGdip05_art09")  
  
 Im vorherigen Beispiel wird der Punkt (2, 1) dem Punkt (2, 6) zugeordnet. Beachten Sie, dass die dritte Spalte der 3 × 3-Matrix die Zahlen 0, 0, 1 enthält. Dies ist immer die Groß-/Kleinschreibung für die 3 × 3-Matrix einer affinen Transformation. Die wichtigsten Zahlen sind die sechs Zahlen in den Spalten 1 und 2. Der obere linke 2 × 2-Teil der Matrix stellt den linearen Teil der Transformation dar, und die ersten beiden Einträge in der dritten Zeile stellen die Übersetzung dar.  
  
 ![Transformationen](./media/aboutgdip05-art10.gif "AboutGdip05_art10")  
  
 In GDI+ können Sie eine affine Transformation in einem <xref:System.Drawing.Drawing2D.Matrix> -Objekt speichern. Da die dritte Spalte einer Matrix, die eine affine-Transformation darstellt, immer (0, 0, 1) ist, geben Sie nur die sechs Zahlen in den ersten beiden Spalten an, <xref:System.Drawing.Drawing2D.Matrix> Wenn Sie ein-Objekt erstellen. Die- `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` Anweisung erstellt die in der vorangehenden Abbildung gezeigte Matrix.  
  
## <a name="composite-transformations"></a>Zusammengesetzte Transformationen  
 Eine zusammengesetzte Transformation ist eine Sequenz von Transformationen, von denen eine nacheinander folgt. Beachten Sie die Matrizen und Transformationen in der folgenden Liste:  
  
|||  
|-|-|  
|Matrix A|Drehen von 90 Grad|  
|Matrix B|Skalieren Sie mit dem Faktor 2 in der x-Richtung.|  
|Matrix C|Übersetzt 3 Einheiten in y-Richtung|  
  
 Wenn wir mit dem Punkt (2, 1) –, der durch die Matrix [2 1 1] – dargestellt wird, und Multiplizieren von a, dann C, wird der Punkt (2, 1) den drei Transformationen in der aufgelisteten Reihenfolge unterzogen.  
  
 [2 1 1]ABC = [-2 5 1]  
  
 Anstatt die drei Teile der zusammengesetzten Transformation in drei separaten Matrizen zu speichern, können Sie a, B und C zusammen multiplizieren, um eine einzelne 3 × 3-Matrix zu erhalten, in der die gesamte zusammengesetzte Transformation gespeichert wird. Angenommen, ABC = D. Ein Punkt, der mit D multipliziert ist, gibt das gleiche Ergebnis wie ein Punkt multipliziert mit a, dann B und dann C.  
  
 [2 1 1]D = [-2 5 1]  
  
 Die folgende Abbildung zeigt die Matrizen A, B, C und D.  
  
 ![Transformationen](./media/aboutgdip05-art12.gif "AboutGdip05_art12")  
  
 Die Tatsache, dass die Matrix einer zusammengesetzten Transformation durch Multiplizieren der einzelnen Transformations Matrizen gebildet werden kann, bedeutet, dass jede Sequenz von affinen Transformationen in einem <xref:System.Drawing.Drawing2D.Matrix> einzelnen Objekt gespeichert werden kann.  
  
> [!CAUTION]
> Die Reihenfolge einer zusammengesetzten Transformation ist wichtig. Im Allgemeinen ist die Drehung, Skalierung und Übersetzung nicht dasselbe wie die Skalierung, dann drehen und übersetzen. Ebenso ist die Reihenfolge der Matrix Multiplikation wichtig. Im Allgemeinen ist ABC nicht mit der Bac identisch.  
  
 Die <xref:System.Drawing.Drawing2D.Matrix> -Klasse stellt mehrere Methoden zum Aufbauen einer zusammengesetzten Transformation <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>bereit <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>: <xref:System.Drawing.Drawing2D.Matrix.Scale%2A> <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>, <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>,, <xref:System.Drawing.Drawing2D.Matrix.Translate%2A>, und. Im folgenden Beispiel wird die Matrix einer zusammengesetzten Transformation erstellt, die zuerst 30 Grad rotiert, dann mit einem Faktor von 2 in der y-Richtung skaliert und dann 5 Einheiten in der x-Richtung übersetzt:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.CoordinateSystems#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#11)]  
  
 Die folgende Abbildung zeigt die Matrix.  
  
 ![Transformationen](./media/aboutgdip05-art13.gif "AboutGdip05_art13")  
  
## <a name="see-also"></a>Siehe auch

- [Koordinatensysteme und Transformationen](coordinate-systems-and-transformations.md)
- [Verwenden von Transformationen in Managed GDI+](using-transformations-in-managed-gdi.md)
