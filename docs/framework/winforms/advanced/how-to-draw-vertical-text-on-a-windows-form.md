---
title: "Gewusst wie: Zeichnen von vertikalem Text in einem Windows Form"
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
- cpp
f1_keywords:
- StringFormat.FormatFlags
- Graphics.DrawString
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- strings [Windows Forms], drawing vertical
- text [Windows Forms], drawing
- text [Windows Forms], vertical text
ms.assetid: 717a6131-00f6-4373-b574-9894e8317799
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 76da7be50f9e12454e16e08ec4db494585fae613
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-vertical-text-on-a-windows-form"></a>Gewusst wie: Zeichnen von vertikalem Text in einem Windows Form
Im folgenden Codebeispiel wird veranschaulicht, wie Zeichnen von vertikalem Text in einem Formular mithilfe der <xref:System.Drawing.Graphics.DrawString%2A> Methode <xref:System.Drawing.Graphics>.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#8)]
 [!code-csharp[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#8)]
 [!code-vb[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#8)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Sie können diese Methode nicht aufrufen, der <xref:System.Windows.Forms.Form.Load> -Ereignishandler. Der gezeichnete Inhalt wird nicht neu gezeichnet wird, wenn das Formular vergrößert bzw. verkleinert oder durch eine andere Form verdeckt. Damit der Inhalt automatisch neu gezeichnet werden soll, sollten Sie überschreiben die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Die Schriftart Arial ist nicht installiert.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Graphics.DrawString%2A>  
 <xref:System.Drawing.StringFormat.FormatFlags%2A>  
 <xref:System.Drawing.StringFormatFlags>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [Erste Schritte mit Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
