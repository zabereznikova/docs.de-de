---
title: 'Gewusst wie: Zeichnen einer Linie mit Linienenden'
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
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e2d5a5aba4a7634e0ea8480aa9744a5a7b9721d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-line-with-line-caps"></a>Gewusst wie: Zeichnen einer Linie mit Linienenden
Sie können den Anfang oder Ende einer Zeile in einer von mehreren Formen aufgerufen Linienenden zeichnen. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]unterstützt mehrere Linienenden wie Round, Quadrat, Raute und Pfeilspitze an.  
  
## <a name="example"></a>Beispiel  
 Sie können Linienenden für den Anfang einer Zeile (startinitiale), das Ende einer Zeile (Linienende) oder die Striche eine gestrichelte Linie (Bindestrich Cap) angeben.  
  
 Im folgende Beispiel zeichnet eine Linie mit Pfeilspitze an einem Ende und ein runder Abschluss am anderen Ende. Die Abbildung zeigt die resultierenden Zeile:  
  
 ![Stifte](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Erstellen eines Windows Form, und behandeln Sie des Formulars <xref:System.Windows.Forms.Control.Paint> Ereignis. Fügen Sie den Beispielcode in die <xref:System.Windows.Forms.Control.Paint> -Ereignishandler übergeben `e` als <xref:System.Windows.Forms.PaintEventArgs>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Verwenden eines Stifts zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
