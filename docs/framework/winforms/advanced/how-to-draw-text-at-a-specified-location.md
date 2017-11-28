---
title: 'Gewusst wie: Zeichnen von Text an einer angegebenen Position'
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
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text a a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aab9570b98caec5b3975a5b3ff6f1e62d4ad303b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-text-at-a-specified-location"></a>Gewusst wie: Zeichnen von Text an einer angegebenen Position
Wenn Sie benutzerdefinierte Zeichnung zu erstellen, können Sie Text in einer einzelnen horizontalen Linie ab, zu einem bestimmten Zeitpunkt zeichnen. Sie können auf diese Weise Text zeichnen, mithilfe der <xref:System.Drawing.Graphics.DrawString%2A> überladene Methode, der die <xref:System.Drawing.Graphics> -Klasse, akzeptiert eine <xref:System.Drawing.Point> oder <xref:System.Drawing.PointF> Parameter. Die <xref:System.Drawing.Graphics.DrawString%2A> Methode erfordert außerdem eine <xref:System.Drawing.Brush> und<xref:System.Drawing.Font>  
  
 Können Sie auch die <xref:System.Windows.Forms.TextRenderer.DrawText%2A> überladene Methode, der die <xref:System.Windows.Forms.TextRenderer> , akzeptiert eine <xref:System.Drawing.Point>. <xref:System.Windows.Forms.TextRenderer.DrawText%2A>Außerdem erfordert eine <xref:System.Drawing.Color> und ein <xref:System.Drawing.Font>.  
  
 Die folgende Abbildung zeigt die Ausgabe von Text zu einem bestimmten Zeitpunkt gezeichnet werden, bei der Verwendung der <xref:System.Drawing.Graphics.DrawString%2A> überladene Methode.  
  
 ![Schriftartentext](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>Zum Zeichnen einer Linie von Text mit GDI +  
  
1.  Verwenden der <xref:System.Drawing.Graphics.DrawString%2A> -Methode, und übergeben Sie den gewünschten Text, <xref:System.Drawing.Point> oder <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, und <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>Zum Zeichnen einer Linie von Text mit GDI  
  
1.  Verwenden der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> -Methode, und übergeben Sie den gewünschten Text, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, und <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Die vorherigen Beispiele erfordern Folgendes:  
  
-   <xref:System.Windows.Forms.PaintEventArgs>  `e`, ein Parameter des <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Zeichnen von Text mit GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Gewusst wie: Erstellen von Schriftartfamilien und Schriftarten](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [Gewusst wie: Zeichnen von umbrochenem Text in einem Rechteck](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)
