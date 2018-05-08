---
title: 'Gewusst wie: Verwenden einer Farbmatrix zum Transformieren einer Farbe'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
ms.openlocfilehash: 741259fcf853c82dfd13b43edc92e50d8767887b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a>Gewusst wie: Verwenden einer Farbmatrix zum Transformieren einer Farbe
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Stellt die <xref:System.Drawing.Image> und <xref:System.Drawing.Bitmap> Klassen zum Speichern und Bearbeiten von Bildern. <xref:System.Drawing.Image> und <xref:System.Drawing.Bitmap> Objekte speichern die Farbe jedes Pixels als 32-Bit-Zahl: jeweils 8 Bit für Rot, Grün, Blau und Alpha. Jede der vier Komponenten ist eine Zahl zwischen 0 und 255, wobei 0 für keine Intensität und 255 für volle Farbintensität. Mit dem Alphaanteil gibt die Transparenz der Farbe: 0 vollständig transparent ist, und 255 ist nicht vollständig transparent.  
  
 Ein Vektor Farbe ist ein 4-Tupel des Formulars (Rot, Grün, Blau, Alpha). Der Vektor Farbe (0, 255, 0, 255) stellt beispielsweise eine nicht transparente Farbe, die keine rote oder blaue hat, jedoch grün mit voller Intensität.  
  
 Eine andere Konvention für die Darstellung von Farben verwendet die Zahl 1 für volle Intensität an. Mithilfe dieser Konvention, würde die Farbe, die im vorherigen Abschnitt beschrieben durch den Vektor (0, 1, 0, 1) dargestellt werden. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] die Konvention von 1 verwendet als vollständige Intensität, wenn Color-Transformationen ausgeführt.  
  
 Sie können Farbe Vektoren lineare Transformationen (Drehung, Skalierung und Like) anwenden, multipliziert der Vektoren Farbe mit einer 4 x 4-Matrix. Eine 4 x 4-Matrix können Sie jedoch eine Übersetzung (nichtlinearen) ausführen. Wenn Sie jede der Farbe Vektoren eine dummy fünfte Koordinate (z. B. der Zahl 1) hinzugefügt haben, können Sie eine Matrix 5 x 5 verwenden, um eine beliebige Kombination von lineare Transformationen und Konvertierungen anzuwenden. Eine Transformation, bestehend aus einer linearen Transformations gefolgt von einer Übersetzung wird eine affine Transformation aufgerufen werden.  
  
 Nehmen wir beispielsweise an, dass Sie mit der Farbe (0,2, 0.0, 0.4, 1.0) starten und die folgenden Transformationen anwenden möchten:  
  
1.  Verdoppelung des Rotanteils  
  
2.  Hinzufügen von 0,2 Rot-, Grün- und Blau-Komponenten  
  
 Die folgenden Matrixmultiplikation führt das Paar von Transformationen in entsprechender Reihenfolge aufgelistet.  
  
 ![Neufärben von](../../../../docs/framework/winforms/advanced/media/recoloring01.gif "recoloring01")  
  
 Von Zeilen- und klicken Sie dann werden die Elemente einer Farbmatrix (nullbasiert) indiziert. Beispielsweise wird der Eintrag in der fünften Zeile und der dritten Spalte der Matrix M von M [4] [2] gekennzeichnet.  
  
 Die 5 x 5-Identitätsmatrix (in der folgenden Abbildung gezeigt) verfügt über 1 s auf die diagonale und 0 s anderen Orten wegzulassen. Wenn Sie einen Vektor Farbe durch die Identitätsmatrix multiplizieren, ändert sich der Vektor Farbe nicht. Eine einfache Möglichkeit, bilden die Matrix eine Farbe Transformation ist mit die Identitätsmatrix beginnen, und stellen eine kleine Änderung, die die gewünschte Transformation produziert.  
  
 ![Neufärben von](../../../../docs/framework/winforms/advanced/media/recoloring02.gif "recoloring02")  
  
 Eine ausführlichere Erläuterung von Matrizen und Transformationen, finden Sie unter [Koordinatensysteme und Transformationen](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Bild, das alle einfarbig (0,2, 0.0, 0.4, 1.0) und wendet die Transformation, die in den vorherigen Abschnitten beschrieben.  
  
 Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und das transformierte Bild auf der rechten Seite.  
  
 ![Farben](../../../../docs/framework/winforms/advanced/media/colortrans1.png "colortrans1")  
  
 Der Code im folgenden Beispiel verwendet die folgenden Schritte aus, um das über erneutes Einfärben auszuführen:  
  
1.  Initialisieren einer <xref:System.Drawing.Imaging.ColorMatrix> Objekt.  
  
2.  Erstellen einer <xref:System.Drawing.Imaging.ImageAttributes> Objekts und übergeben der <xref:System.Drawing.Imaging.ColorMatrix> -Objekt an die <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> Methode der <xref:System.Drawing.Imaging.ImageAttributes> Objekt.  
  
3.  Übergeben der <xref:System.Drawing.Imaging.ImageAttributes> -Objekt an die <xref:System.Drawing.Graphics.DrawImage%2A> Methode von einer <xref:System.Drawing.Graphics> Objekt.  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch  
 [Neufärben von Bildern](../../../../docs/framework/winforms/advanced/recoloring-images.md)  
 [Koordinatensysteme und Transformationen](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)
