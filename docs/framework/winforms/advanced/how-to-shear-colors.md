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
ms.openlocfilehash: 204f15ce44d5ad688be0ea9ac0fa4a90781b25dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-shear-colors"></a>Gewusst wie: Scheren von Farben
Scheren erhöht oder verringert eine Farbe Komponente durch einen Betrag proportional zu einer anderen Farbe-Komponente. Betrachten Sie beispielsweise die Transformation, in dem die Hälfte der Wert des Blauanteils Rotanteils gestiegen ist. Unter solchen eine Transformation werden die Farbe (0,2, 0,5, 1), (0,7, 0,5, 1). Neuen Rotanteils ist 0,2 + ((1/2)(1) = 0,7.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datei ColorBars4.bmp. Der Code wendet dann die Scheren Transformation, die im vorherigen Abschnitt Pixel in der Abbildung beschrieben.  
  
 Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und das Schertransformation Bild auf der rechten Seite.  
  
 ![Scheren von Farben](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")  
  
 Die folgende Tabelle enthält die Vektoren Farbe für die vier Balken vor und nach der Scheren Transformation.  
  
|Ursprünglich|Verbogen|  
|--------------|-------------|  
|(0, 0, 1, 1)|(0.5, 0, 1, 1)|  
|(0.5, 1, 0.5, 1)|(0.75, 1, 0.5, 1)|  
|(1, 1, 0, 1)|(1, 1, 0, 1)|  
|(0.4, 0.4, 0.4, 1)|(0.6, 0.4, 0.4, 1)|  
  
 [!code-csharp[System.Drawing.Misc3#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler. Ersetzen Sie `ColorBars.bmp` mit einem Image-Name und Pfad auf Ihrem System ungültig.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Neufärben von Bildern](../../../../docs/framework/winforms/advanced/recoloring-images.md)
