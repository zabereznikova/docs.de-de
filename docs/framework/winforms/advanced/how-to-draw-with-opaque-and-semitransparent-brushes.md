---
title: 'Gewusst wie: Zeichnen mit nicht transparenten und halb transparenten Pinseln'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- semi-transparent shapes [Windows Forms], drawing
- transparency [Windows Forms], semi-transparent shapes
- alpha blending [Windows Forms], brush
- brushes [Windows Forms], using semi-transparent
ms.assetid: a4f6f6b8-3bc8-440a-84af-d62ef0f8ff40
ms.openlocfilehash: 1e48bbd563f6377380848949325962b568fa432c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142406"
---
# <a name="how-to-draw-with-opaque-and-semitransparent-brushes"></a>Gewusst wie: Zeichnen mit nicht transparenten und halb transparenten Pinseln
Wenn Sie eine Form ausfüllen, müssen Sie ein <xref:System.Drawing.Brush>-Objekt an eine der Füllmethoden der <xref:System.Drawing.Graphics>-Klasse übergeben. Der einzige Parameter des <xref:System.Drawing.SolidBrush.%23ctor%2A>-Konstruktors ist ein <xref:System.Drawing.Color>-Objekt. Um eine nicht transparente Form auszufüllen, legen Sie den Alphaanteil der Farbe auf 255 fest. Um eine halb transparente Form auszufüllen, legen Sie den Alphaanteil auf einen beliebigen Wert von 1 bis 254 fest.  
  
 Wenn Sie eine halb transparente Form ausfüllen, wird die Farbe der Form mit den Hintergrundfarben gemischt. Mit dem Alphaanteil wird das Mischungsverhältnis zwischen Form- und Hintergrundfarben angegeben. Bei Alphawerten nahe 0 werden die Hintergrundfarben höher gewichtet, und bei Alphawerten nahe 255 wird die Formfarbe höher gewichtet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird erst eine Bitmap gezeichnet, und anschließend werden drei Ellipsen ausgefüllt, die die Bitmap überlappen Für die erste Ellipse wird ein Alphaanteil von 255 verwendet. Die Ellipse ist daher nicht transparent. Die zweite und die dritte Ellipse verwenden einen Alphaanteil von 128. Sie sind daher halb transparent. Das Hintergrundbild scheint also durch die Ellipsen hindurch. Der Aufruf, mit dem die <xref:System.Drawing.Graphics.CompositingQuality%2A>-Eigenschaft festgelegt wird, sorgt dafür, dass die Mischung für die dritte Ellipse unter Verwendung der Gammakorrektur erfolgt.  

 [!code-csharp[System.Drawing.AlphaBlending#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.AlphaBlending#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#31)]  

 Die folgende Abbildung zeigt die Ausgabe des folgenden Codes:
  
 ![Abbildung, die undurchsichtige und halbtransparente Ausgabe zeigt.](./media/how-to-draw-with-opaque-and-semitransparent-brushes/compositingquality-ellipse-semitransparent.png)  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung <xref:System.Windows.Forms.PaintEventArgs> `e`mit Windows Forms <xref:System.Windows.Forms.PaintEventHandler>konzipiert und erfordert , was ein Parameter von ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Alphablending von Linien und Füllungen](alpha-blending-lines-and-fills.md)
- [Gewusst wie: Verwenden eines transparenten Hintergrunds für ein Steuerelement](../controls/how-to-give-your-control-a-transparent-background.md)
- [Gewusst wie: Zeichnen deckender und halbtransparenter Linien](how-to-draw-opaque-and-semitransparent-lines.md)
