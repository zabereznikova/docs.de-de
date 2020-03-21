---
title: 'Gewusst wie: Scheren von Farben'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: 825e5a90ebb0d9df3b894ce7bd353e917b676939
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142393"
---
# <a name="how-to-shear-colors"></a>Gewusst wie: Scheren von Farben
Das Scheren erhöht oder verringert eine Farbkomponente um einen Betrag, der proportional zu einer anderen Farbkomponente ist. Betrachten Sie beispielsweise die Transformation, bei der die rote Komponente um die Hälfte des Wertes der blauen Komponente erhöht wird. Bei einer solchen Transformation würde die Farbe (0,2, 0,5, 1) (0,7, 0,5, 1) werden. Die neue rote Komponente ist 0,2 + (1/2)(1) = 0,7.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel <xref:System.Drawing.Image> wird ein Objekt aus der Datei ColorBars4.bmp erstellt. Anschließend wendet der Code die im vorherigen Absatz beschriebene Schertransformation auf jedes Pixel im Bild an.  
  
 Die folgende Abbildung zeigt das Originalbild auf der linken Seite und das abgeserte Bild auf der rechten Seite:
  
 ![Zwei Quadrate mit farbigen Streifen nebeneinander, die das Originalbild und das geerschbte Bild veranschaulichen.](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 In der folgenden Tabelle sind die Farbvektoren für die vier Balken vor und nach der Schertransformation aufgeführt.  
  
|Original|Geschert|  
|--------------|-------------|  
|(0, 0, 1, 1)|(0.5, 0, 1, 1)|  
|(0.5, 1, 0.5, 1)|(0.75, 1, 0.5, 1)|  
|(1, 1, 0, 1)|(1, 1, 0, 1)|  
|(0.4, 0.4, 0.4, 1)|(0.6, 0.4, 0.4, 1)|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung <xref:System.Windows.Forms.PaintEventArgs> `e`mit Windows Forms <xref:System.Windows.Forms.Control.Paint> konzipiert und erfordert , was ein Parameter des Ereignishandlers ist. Ersetzen `ColorBars.bmp` Sie dies durch einen Auf- und nach dem System gültigen Bildnamen und Pfad.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Neueinfärben von Bildern](recoloring-images.md)
