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
ms.openlocfilehash: 2adb33e3d05e38ee71be8a12cdc2e20dc8c55c72
ms.sourcegitcommit: ceca5a1c027627abcca2767567703c3879f33325
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2018
ms.locfileid: "36338129"
---
# <a name="how-to-use-antialiasing-with-text"></a>Gewusst wie: Verwenden der Bildkantenglättung mit Text
*Antialiasing* bezieht sich auf das Glätten Flatterrändern von gezeichneten Grafiken und Text, um ihre Darstellung oder Lesbarkeit zu verbessern. Mit der verwalteten [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Klassen, können Sie qualitativ hochwertigen geglätteten Text als auch Text von geringer Qualität rendern. In der Regel akzeptiert höherer Qualität rendern zeitaufwändiger als niedrigere Qualität rendern. Legen Sie zum Festlegen der Qualitätsstufe Text der <xref:System.Drawing.Graphics.TextRenderingHint%2A> Eigenschaft eine <xref:System.Drawing.Graphics> in eines der Elemente des der <xref:System.Drawing.Text.TextRenderingHint> Enumeration  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird zeichnet Text mit zwei verschiedenen Einstellungen.  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
 
 Die folgende Abbildung zeigt die Ausgabe des Beispielcodes:  
  
 ![Schriftartentext](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Im vorangehenden Codebeispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
