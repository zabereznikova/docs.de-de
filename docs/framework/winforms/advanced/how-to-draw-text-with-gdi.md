---
title: 'Vorgehensweise: Zeichnen von Text mit GDI'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
ms.openlocfilehash: d4bf72998c798040451b814a7f0287bca65f5300
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073324"
---
# <a name="how-to-draw-text-with-gdi"></a>Vorgehensweise: Zeichnen von Text mit GDI
Mit der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> -Methode in der die <xref:System.Windows.Forms.TextRenderer> -Klasse, die Sie zugreifen können [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Funktionen zum Zeichnen von Text in einem Formular oder Steuerelement. [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Rendern von Text in der Regel bietet, eine bessere Leistung und genauere Messung als Text [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Methoden der <xref:System.Windows.Forms.TextRenderer> Klasse werden zum Drucken nicht unterstützt. Beim Drucken, verwenden Sie immer die <xref:System.Drawing.Graphics.DrawString%2A> Methoden der <xref:System.Drawing.Graphics> Klasse.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Zeichnen von Text auf mehrere Zeilen in einem Rechteck mithilfe der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Methode.  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 Zum Rendern von Text mit der <xref:System.Windows.Forms.TextRenderer> -Klasse, die Sie benötigen ein <xref:System.Drawing.IDeviceContext>, z. B. eine <xref:System.Drawing.Graphics> und ein <xref:System.Drawing.Font>, einen Speicherort zum Zeichnen von Text und die Farbe, in denen es gezeichnet werden soll. Optional können Sie angeben, die textformatierung, die mithilfe der <xref:System.Windows.Forms.TextFormatFlags> Enumeration.  
  
 Weitere Informationen zum Abrufen einer <xref:System.Drawing.Graphics>, finden Sie unter [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](how-to-create-graphics-objects-for-drawing.md). Weitere Informationen zum Erstellen einer <xref:System.Drawing.Font>, finden Sie unter [Vorgehensweise: Erstellen von Schriftartfamilien und Schriftarten](how-to-construct-font-families-and-fonts.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das vorherige Codebeispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs>`e`, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- <xref:System.Drawing.Color>
- [Verwenden von Schriftarten und Text](using-fonts-and-text.md)
