---
title: 'Gewusst wie: Verwenden der Bildkantenglättung mit Text'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
ms.openlocfilehash: 632ed329173d134495a424b34ca7c71e402607bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182483"
---
# <a name="how-to-use-antialiasing-with-text"></a>Gewusst wie: Verwenden der Bildkantenglättung mit Text
*Antialiasing* bezieht sich auf die Glättung von gezackten Kanten von gezeichneten Grafiken und Text, um ihr Aussehen oder ihre Lesbarkeit zu verbessern. Mit den verwalteten GDI+-Klassen können Sie qualitativ hochwertigen Antialiased-Text sowie Text mit geringerer Qualität rendern. In der Regel benötigt das Rendern höherer Qualität mehr Verarbeitungszeit als Rendering mit geringerer Qualität. Um die Textqualitätsstufe festzulegen, legen Sie die <xref:System.Drawing.Graphics.TextRenderingHint%2A> Eigenschaft von a <xref:System.Drawing.Graphics> auf eines der Elemente der <xref:System.Drawing.Text.TextRenderingHint> Enumeration fest.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird Text mit zwei verschiedenen Qualitätseinstellungen gezeichnet.  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  

 Die folgende Abbildung zeigt die Ausgabe des Beispielcodes:  
  
 ![Screenshot, der Text mit zwei verschiedenen Qualitätseinstellungen anzeigt.](./media/how-to-use-antialiasing-with-text/antialiasing-text-quality-settings.png)  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das vorangehende Codebeispiel ist für die <xref:System.Windows.Forms.PaintEventArgs> `e`Verwendung mit Windows <xref:System.Windows.Forms.PaintEventHandler>Forms konzipiert und erfordert , was ein Parameter von ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Schriftarten und Text](using-fonts-and-text.md)
