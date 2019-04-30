---
title: 'Vorgehensweise: Zeichnen deckender und halbtransparenter Linien'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- transparency [Windows Forms], lines
- lines [Windows Forms], drawing alpha blended
- alpha blending [Windows Forms], drawing lines
ms.assetid: 8f2508af-f495-4223-b5cc-646cbbb520eb
ms.openlocfilehash: 7408722dc13e83828cfca3f0615a2730e3c53461
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004028"
---
# <a name="how-to-draw-opaque-and-semitransparent-lines"></a>Vorgehensweise: Zeichnen deckender und halbtransparenter Linien
Wenn Sie eine Linie zeichnen, müssen Sie ein <xref:System.Drawing.Pen>-Objekt an die <xref:System.Drawing.Graphics.DrawLine%2A>-Methode der <xref:System.Drawing.Graphics>-Klasse übergeben. Einer der Parameter des <xref:System.Drawing.Pen.%23ctor%2A>-Konstruktors ist ein <xref:System.Drawing.Color>-Objekt. Um eine nicht transparente Linie zu zeichnen, legen Sie den Alphaanteil der Farbe auf 255 fest. Um eine halb transparente Linie zu zeichnen, legen Sie den Alphaanteil auf einen beliebigen Wert von 1 bis 254 fest.  
  
 Wenn Sie eine halb transparente Linie vor einem Hintergrund zeichnen, wird Linienfarbe mit den Hintergrundfarben gemischt. Mit dem Alphaanteil wird das Mischungsverhältnis zwischen Linien- und Hintergrundfarben angegeben. Bei Alphawerten nahe 0 werden die Hintergrundfarben höher gewichtet, und bei Alphawerten nahe 255 wird die Linienfarbe höher gewichtet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden erst eine Bitmap und dann drei Linien gezeichnet, die die Bitmap als Hintergrund verwenden. Für die erste Linie wird ein Alphaanteil von 255 verwendet. Die Linie ist daher nicht transparent. Die zweite und die dritte Linie verwenden einen Alphaanteil von 128. Sie sind daher halb transparent. Das Hintergrundbild scheint also durch die Linien hindurch. Die Anweisung, mit der die <xref:System.Drawing.Graphics.CompositingQuality%2A>-Eigenschaft festgelegt wird, sorgt dafür, dass die Mischung für die dritte Linie unter Verwendung der Gammakorrektur erfolgt.  
  
 [!code-csharp[System.Drawing.AlphaBlending#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.AlphaBlending#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#11)]  
  
 Die folgende Abbildung zeigt die Ausgabe des folgenden Codes:  
  
 ![Abbildung der deckender und Halbtransparenter-Ausgabe](./media/how-to-draw-opaque-and-semitransparent-lines/opaque-semitransparent-lines.png)  

## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch

- [Alphablending von Linien und Füllungen](alpha-blending-lines-and-fills.md)
- [Vorgehensweise: Fügen Sie dem Steuerelement einen transparenten Hintergrund](../controls/how-to-give-your-control-a-transparent-background.md)
- [Vorgehensweise: Zeichnen Sie mit nicht transparenten und halb transparenten Pinseln](how-to-draw-with-opaque-and-semitransparent-brushes.md)
