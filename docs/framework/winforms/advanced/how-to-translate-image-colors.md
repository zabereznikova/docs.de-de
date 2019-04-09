---
title: 'Vorgehensweise: Verschieben von Bildfarben'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: 04e61383ef79b17ea6e1523588cd9593ec9b082c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132638"
---
# <a name="how-to-translate-image-colors"></a>Vorgehensweise: Verschieben von Bildfarben
Eine Übersetzung Fügt einen Wert an eine oder mehrere der vier Farbkomponenten. Die Farbe Matrix Einträge von Übersetzungen werden in der folgenden Tabelle angegeben.  
  
|Komponente, die zu übersetzende|Matrixeintrag|  
|--------------------------------|------------------|  
|Rot|[4][0]|  
|Grün|[4][1]|  
|Blau|[4][2]|  
|Alpha|[4][3]|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datei ColorBars.bmp. Klicken Sie dann den Code hinzugefügt 0,75 Rotanteils der einzelnen Pixel in der Abbildung. Das ursprüngliche Bild wird zusammen mit den transformierten Bild gezeichnet.  
  
 Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und die transformierten auf der rechten Seite an:  
  
 ![Screenshot des ursprünglichen und die transformierten Bilds.](./media/how-to-translate-image-colors/original-image-translate-colors.png)  
  
 Die folgende Tabelle enthält die Farbe Vektoren für die vier Balken, vor und nach die roten Übersetzung. Beachten Sie, dass der Rotanteil in der zweiten Zeile, da der maximale Wert für eine Komponente Farbe 1 ist, nicht geändert wird. (Auf ähnliche Weise ist der minimale Wert für eine Komponente Farbe 0.)  
  
|Ursprünglich|Übersetzt|  
|--------------|----------------|  
|Schwarz (0, 0, 0, 1)|(0.75, 0, 0, 1)|  
|Rot (1, 0, 0, 1)|(1, 0, 0, 1)|  
|Grün (0, 1, 0, 1)|(0.75, 1, 0, 1)|  
|Blau (0, 0, 1, 1)|(0.75, 0, 1, 1)|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler. Ersetzen Sie dies `ColorBars.bmp` mit einer Bilddateinamen und den Pfad, die auf Ihrem System gültig sind.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Neueinfärben von Bildern](recoloring-images.md)
