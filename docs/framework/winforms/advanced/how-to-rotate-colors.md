---
title: 'Gewusst wie: Drehen von Farben'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 8d2717dd7b819e963126072279b361fda02188bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111334"
---
# <a name="how-to-rotate-colors"></a>Gewusst wie: Drehen von Farben
Die Rotation in einem vierdimensionalen Farbraum ist schwer zu visualisieren. Wir können es einfacher machen, die Rotation zu visualisieren, indem wir uns darauf einigen, eine der Farbkomponenten festzuhalten. Angenommen, wir stimmen zu, die Alphakomponente auf 1 festzuhalten (vollständig undurchsichtig). Dann können wir einen dreidimensionalen Farbraum mit roten, grünen und blauen Achsen visualisieren, wie in der folgenden Abbildung dargestellt.  
  
 ![Abbildung, die die Drehung mit roten, grünen und blauen Achsen anzeigt.](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 Eine Farbe kann als ein Punkt im 3D-Raum betrachtet werden. Beispielsweise stellt der Punkt (1, 0, 0) im Raum die Farbe Rot und der Punkt (0, 1, 0) im Raum die Farbe Grün dar.  
  
 Die folgende Abbildung zeigt, was es bedeutet, die Farbe (1, 0, 0) in der rot-grünen Ebene um einen Winkel von 60 Grad zu drehen. Die Rotation in einer Ebene parallel zur rot-grünen Ebene kann als Rotation um die blaue Achse betrachtet werden.  
  
 ![Abbildung, die die Drehung um die blaue Achse zeigt.](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 Die folgende Abbildung zeigt, wie Sie eine Farbmatrix initialisieren, um Rotationen um jede der drei Koordinatenachsen (rot, grün, blau) durchzuführen:  
  
 ![Initialisieren Sie eine Farbmatrix, um Drehungen um drei Achsen durchzuführen.](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Bild mit einer Farbe (1, 0, 0,6) verwendet und eine 60-Grad-Drehung um die blaue Achse angewendet. Der Drehwinkel wird in einer Ebene, die parallel zur rot-grünen Ebene verläuft, ausgefegt.  
  
 Die folgende Abbildung zeigt das Originalbild auf der linken Seite und das farblich gedrehte Bild auf der rechten Seite:  
  
 ![Abbildung, die Originalbild und farblich gedrehtes Bild zeigt.](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 Die folgende Abbildung zeigt eine Visualisierung der Farbrotation, die im folgenden Code durchgeführt wird:
  
 ![Abbildung, die die Visualisierung der Farbrotation zeigt.](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung <xref:System.Windows.Forms.PaintEventArgs> `e`mit Windows Forms <xref:System.Windows.Forms.Control.Paint> konzipiert und erfordert , was ein Parameter des Ereignishandlers ist. Ersetzen `RotationInput.bmp` Sie dies durch einen Bilddateinamen und einen Pfad, der auf Ihrem System gültig ist.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Neueinfärben von Bildern](recoloring-images.md)
