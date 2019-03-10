---
title: 'Vorgehensweise: Zeichnen von umbrochenem Text in einem Rechteck'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: 5c4e76cda37527d0167b21c0d206749ba6dab4a9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708859"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a>Vorgehensweise: Zeichnen von umbrochenem Text in einem Rechteck
Sie können die umbrochenen Text in ein Rechteck zeichnen, mit der <xref:System.Drawing.Graphics.DrawString%2A> überladene Methode, die von der <xref:System.Drawing.Graphics> Klasse, die akzeptiert eine <xref:System.Drawing.Rectangle> oder <xref:System.Drawing.RectangleF> Parameter. Sie können auch eine <xref:System.Drawing.Brush> und <xref:System.Drawing.Font>.  
  
 Sie können auch umbrochenen Text in ein Rechteck zeichnen, mit der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> überladene Methode, die von der <xref:System.Windows.Forms.TextRenderer> , akzeptiert eine <xref:System.Drawing.Rectangle> und ein <xref:System.Windows.Forms.TextFormatFlags> Parameter. Sie können auch eine <xref:System.Drawing.Color> und <xref:System.Drawing.Font>.  
  
 Die folgende Abbildung zeigt die Ausgabe von Text in das Rechteck gezeichnet werden, bei der Verwendung der <xref:System.Drawing.Graphics.DrawString%2A> Methode.  
  
 ![Schriftartentext](./media/csfontstext2.png "csfontstext2")  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>Zum Zeichnen von umbrochenem Text in einem Rechteck mit GDI +  
  
1.  Verwenden der <xref:System.Drawing.Graphics.DrawString%2A> überladene Methode, und übergeben Sie den Text an, Sie möchten, <xref:System.Drawing.Rectangle> oder <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> und <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>Zum Zeichnen von umbrochenem Text in einem Rechteck mit GDI  
  
1.  Verwenden der <xref:System.Windows.Forms.TextFormatFlags> Enumerationswert zum Angeben des Texts eingebunden werden soll, mit der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> überladene Methode, und übergeben Sie den Text an, Sie möchten, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> und <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Die vorherigen Beispiele erfordern Folgendes:  
  
-   <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Zeichnen von Text mit GDI](how-to-draw-text-with-gdi.md)
- [Verwenden von Schriftarten und Text](using-fonts-and-text.md)
- [Vorgehensweise: Erstellen von Schriftartfamilien und Schriftarten](how-to-construct-font-families-and-fonts.md)
- [Vorgehensweise: Zeichnen von Text an einer angegebenen Position](how-to-draw-text-at-a-specified-location.md)
