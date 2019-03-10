---
title: 'Vorgehensweise: Drehen von Farben'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: cb3824d8a5a5674b83124301dbfbd5a3ba60effa
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720617"
---
# <a name="how-to-rotate-colors"></a>Vorgehensweise: Drehen von Farben
Drehung in einer vierdimensionalen Farbraum ist schwierig, zu visualisieren. Wir können es vorstellbar, stimmen zu einer der festen Farbkomponenten vereinfachen. Nehmen wir an, dass in jedem die alpha-Komponente auf 1 festgesetzt (vollständig deckend) beibehalten. Dann können wir einen dreidimensionalen Farbraum mit roten, grünen und blauen Achsen visualisieren, wie in der folgenden Abbildung dargestellt.  
  
 ![Recoloring](./media/recoloring03.gif "recoloring03")  
  
 Eine Farbe kann als ein Punkt im 3D-Raum betrachtet werden. Beispielsweise wird der Punkt im Raum (1, 0, 0) darstellt, die Farbe Rot, und der Punkt im Raum (0, 1, 0) darstellt, die Farbe Grün.  
  
 Die folgende Abbildung zeigt was es bedeutet, die die Farbe (1, 0, 0) gedreht, über einen Winkel von 60 Grad in der Rot-Grün-Ebene. Drehung in einer Ebene Parallel zur Rot-Grün-Ebene kann als Drehung um die blauen Achse betrachtet werden.  
  
 ![Recoloring](./media/recoloring04.gif "recoloring04")  
  
 In der folgende Abbildung wird veranschaulicht, wie eine Farbmatrix zum Ausführen der Rotation zu jeder der drei Koordinatenachsen (Rot, Grün, Blau) initialisiert wird.  
  
 ![Recoloring](./media/recoloring05.gif "recoloring05")  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Bild, das alle eine Farbe ("1", "0", "0,6") und wendet eine Drehung um 60 Grad die blaue Achse an. Der Winkel der Drehung wird sich in einer Ebene überflüssig, die parallel zu der Rot-Grün-Ebene ist.  
  
 Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und das Bild Farben gedreht, auf der rechten Seite.  
  
 ![Drehen von Farben](./media/colortrans5.png "colortrans5")  
  
 Die folgende Abbildung zeigt eine Visualisierung der Color-Drehung, die in den folgenden Code ausgeführt wird.  
  
 ![Recoloring](./media/recoloring06.gif "recoloring06")  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers. Ersetzen Sie dies `RotationInput.bmp` mit einer Bilddateinamen gültigen und Pfad auf Ihrem System.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Neufärben von Bildern](recoloring-images.md)
