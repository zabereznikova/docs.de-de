---
title: 'Gewusst wie: Zeichnen von umbrochenem Text in einem Rechteck'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 773216c30adf1c684ec705a909038354aab0fec9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a>Gewusst wie: Zeichnen von umbrochenem Text in einem Rechteck
Umbrochenen Text können in einem Rechteck gezeichnet werden, mithilfe der <xref:System.Drawing.Graphics.DrawString%2A> überladene Methode, der die <xref:System.Drawing.Graphics> -Klasse, akzeptiert eine <xref:System.Drawing.Rectangle> oder <xref:System.Drawing.RectangleF> Parameter. Verwenden Sie ebenfalls eine <xref:System.Drawing.Brush> und ein <xref:System.Drawing.Font>.  
  
 Sie können auch umbrochenen Text in einem Rechteck zeichnen, mithilfe der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> überladenen Methode des der <xref:System.Windows.Forms.TextRenderer> , akzeptiert eine <xref:System.Drawing.Rectangle> und eine <xref:System.Windows.Forms.TextFormatFlags> Parameter. Verwenden Sie ebenfalls eine <xref:System.Drawing.Color> und ein <xref:System.Drawing.Font>.  
  
 Die folgende Abbildung zeigt die Ausgabe von Text in das Rechteck gezeichnet werden, bei der Verwendung der <xref:System.Drawing.Graphics.DrawString%2A> Methode.  
  
 ![Schriftartentext](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>Zum Zeichnen von umbrochenem Text in einem Rechteck mit GDI +  
  
1.  Verwenden der <xref:System.Drawing.Graphics.DrawString%2A> überladene Methode, und übergeben Sie den gewünschten Text <xref:System.Drawing.Rectangle> oder <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> und <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>Zum Zeichnen von umbrochenem Text in einem Rechteck mit GDI  
  
1.  Verwenden der <xref:System.Windows.Forms.TextFormatFlags> Enumerationswert an den Text eingebunden werden soll, mit der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> überladene Methode, und übergeben Sie den gewünschten Text <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> und <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Die vorherigen Beispiele erfordern Folgendes:  
  
-   <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Zeichnen von Text mit GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Gewusst wie: Erstellen von Schriftartfamilien und Schriftarten](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [Gewusst wie: Zeichnen von Text an einer angegebenen Position](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)
