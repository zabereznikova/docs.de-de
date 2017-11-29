---
title: 'Gewusst wie: Zeichnen von Text mit GDI'
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
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48644ce8449c8d8eea7306eff1e43539659370c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-text-with-gdi"></a>Gewusst wie: Zeichnen von Text mit GDI
Mit der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Methode in der <xref:System.Windows.Forms.TextRenderer> -Klasse, die Sie zugreifen können [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Funktionen zum Zeichnen von Text in einem Formular oder Steuerelement. [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]Textrendering bietet in der Regel eine bessere Leistung und genauere Text als messen [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Methoden die <xref:System.Windows.Forms.TextRenderer> -Klasse sind zum Drucken nicht unterstützt. Beim Drucken, verwenden Sie immer die <xref:System.Drawing.Graphics.DrawString%2A> Methoden die <xref:System.Drawing.Graphics> Klasse.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Zeichnen von Text in mehreren Zeilen in einem Rechteck mit dem <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Methode.  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 Zum Rendern von Text mit der <xref:System.Windows.Forms.TextRenderer> -Klasse, Sie müssen eine <xref:System.Drawing.IDeviceContext>, z. B. eine <xref:System.Drawing.Graphics> und ein <xref:System.Drawing.Font>, einen Speicherort zum Zeichnen von Text und die Farbe, in dem er gezeichnet werden soll. Optional können Sie angeben, die textformatierung mithilfe der <xref:System.Windows.Forms.TextFormatFlags> Enumeration.  
  
 Weitere Informationen zum Abrufen einer <xref:System.Drawing.Graphics>, finden Sie unter [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md). Weitere Informationen zum Erstellen einer <xref:System.Drawing.Font>, finden Sie unter [Vorgehensweise: Erstellen von Schriftartfamilien und Schriftarten](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Im vorangehenden Codebeispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.TextRenderer>  
 <xref:System.Drawing.Font>  
 <xref:System.Drawing.Color>  
 <xref:System.Drawing.Color>  
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
