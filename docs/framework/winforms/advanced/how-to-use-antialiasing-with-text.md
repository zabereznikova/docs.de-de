---
title: "Gewusst wie: Verwenden der Bildkantenglättung mit Text"
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
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bb5a57f8bcbdc1edad78dcd48ad495a187bbb44a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-antialiasing-with-text"></a>Gewusst wie: Verwenden der Bildkantenglättung mit Text
*Antialiasing* bezieht sich auf das Glätten Flatterrändern von gezeichneten Grafiken und Text, um ihre Darstellung oder Lesbarkeit zu verbessern. Mit der verwalteten [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Klassen, können Sie qualitativ hochwertigen geglätteten Text als auch Text von geringer Qualität rendern. In der Regel akzeptiert höherer Qualität rendern zeitaufwändiger als niedrigere Qualität rendern. Legen Sie zum Festlegen der Qualitätsstufe Text der <xref:System.Drawing.Graphics.TextRenderingHint%2A> Eigenschaft eine <xref:System.Drawing.Graphics> in eines der Elemente des der <xref:System.Drawing.Text.TextRenderingHint> Enumeration  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird zeichnet Text mit zwei verschiedenen Einstellungen.  
  
 Die folgende Abbildung zeigt die Ausgabe des Beispielcodes Beispielcode.  
  
 ![Schriftartentext](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Im vorangehenden Codebeispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
