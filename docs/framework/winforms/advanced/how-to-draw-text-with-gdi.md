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
ms.openlocfilehash: 3ed2b5c94e4a38a5873a34e61287c4038cab5cbb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956544"
---
# <a name="how-to-draw-text-with-gdi"></a>Vorgehensweise: Zeichnen von Text mit GDI
Mit der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> -Methode in <xref:System.Windows.Forms.TextRenderer> der-Klasse können Sie auf die GDI-Funktionalität zum Zeichnen von Text in einem Formular oder Steuerelement zugreifen. Das GDI-Text Rendering bietet in der Regel eine bessere Leistung und eine präzisere Text Messung als GDI+.  
  
> [!NOTE]
> Die <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Methoden<xref:System.Windows.Forms.TextRenderer> der-Klasse werden zum Drucken nicht unterstützt. Wenn Sie drucken, verwenden Sie <xref:System.Drawing.Graphics.DrawString%2A> immer die Methoden <xref:System.Drawing.Graphics> der-Klasse.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie mithilfe der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> -Methode Text in mehreren Zeilen innerhalb eines Rechtecks zeichnen.  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 Zum Rendering von Text mit <xref:System.Windows.Forms.TextRenderer> der-Klasse <xref:System.Drawing.IDeviceContext>benötigen Sie, <xref:System.Drawing.Font>wie z <xref:System.Drawing.Graphics> . b. und, einen Speicherort zum Zeichnen des Texts und die Farbe, in der der Text gezeichnet werden soll. Optional können Sie die Textformatierung mithilfe der <xref:System.Windows.Forms.TextFormatFlags> -Enumeration angeben.  
  
 Weitere Informationen zum Abrufen eines <xref:System.Drawing.Graphics>finden [Sie unter Gewusst wie: Erstellen Sie Grafik Objekte zum](how-to-create-graphics-objects-for-drawing.md)zeichnen. Weitere Informationen zum Erstellen eines <xref:System.Drawing.Font>finden [Sie unter Gewusst wie: Erstellen von Schriftfamilien und](how-to-construct-font-families-and-fonts.md)Schriftarten  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das vorangehende Codebeispiel wurde für die Verwendung mit Windows Forms entwickelt und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, was ein Parameter von <xref:System.Windows.Forms.PaintEventHandler>ist.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- [Verwenden von Schriftarten und Text](using-fonts-and-text.md)
