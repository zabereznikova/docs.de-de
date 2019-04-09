---
title: 'Vorgehensweise: Zeichnen von Text in einem Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], drawing text
- text [Windows Forms], drawing
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
ms.openlocfilehash: ae7749deedba03f0a63bb74099d071d5da4fe27e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172977"
---
# <a name="how-to-draw-text-on-a-windows-form"></a>Vorgehensweise: Zeichnen von Text in einem Windows Form
Im folgenden Codebeispiel wird veranschaulicht, wie Sie mit der <xref:System.Drawing.Graphics.DrawString%2A> Methode der <xref:System.Drawing.Graphics> zum Zeichnen von Text in einem Formular. Alternativ können Sie <xref:System.Windows.Forms.TextRenderer> zum Zeichnen von Text in einem Formular. Weitere Informationen finden Sie unter [Vorgehensweise: Zeichnen von Text mit GDI](how-to-draw-text-with-gdi.md).  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Sie können nicht aufgerufen werden die <xref:System.Drawing.Graphics.DrawString%2A> -Methode in der die <xref:System.Windows.Forms.Form.Load> -Ereignishandler. Der gezeichnete Inhalt wird nicht neu gezeichnet werden, wenn das Formular vergrößert bzw. verkleinert oder durch eine andere Form verdeckt. Sie sollten damit wird den Inhalt automatisch neu gezeichnet, überschreiben die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Die Schriftart Arial ist nicht installiert.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Windows.Forms.TextRenderer.DrawText%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.TextFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Erste Schritte mit der Grafikprogrammierung](getting-started-with-graphics-programming.md)
- [Vorgehensweise: Zeichnen von Text mit GDI](how-to-draw-text-with-gdi.md)
