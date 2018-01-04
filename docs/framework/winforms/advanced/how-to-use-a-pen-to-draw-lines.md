---
title: 'Gewusst wie: Verwenden eines Stiftes zum Zeichnen von Linien'
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
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 156d7acbbf3f863e89ae2a5c303b2cf4140b3592
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-pen-to-draw-lines"></a>Gewusst wie: Verwenden eines Stiftes zum Zeichnen von Linien
Um Linien zu zeichnen, müssen Sie eine <xref:System.Drawing.Graphics> Objekt und ein <xref:System.Drawing.Pen> Objekt. Die <xref:System.Drawing.Graphics> Objekt enthält die <xref:System.Drawing.Graphics.DrawLine%2A> -Methode, und die <xref:System.Drawing.Pen> Objekt speichert die Funktionen der Zeile, z. B. Farbe und Breite.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel zeichnet eine verbindende Linie aus (20, 10), (300, 100). Die erste Anweisung verwendet die <xref:System.Drawing.Pen.%23ctor%2A> -Klassenkonstruktor einen schwarzen Stift zu erstellen. Ein Argument zu übergeben, um die <xref:System.Drawing.Pen.%23ctor%2A> Konstruktor ist ein <xref:System.Drawing.Color> Objekt erstellt, mit der <xref:System.Drawing.Color.FromArgb%2A> Methode. Die Werte, die zum Erstellen der <xref:System.Drawing.Color> Objekt – (255, 0, 0, 0) – entsprechen, die alpha, Rot-, Grün- und blauen-Komponenten der Farbe. Diese Werte definieren, einen nicht transparenten schwarzen Stift.  
  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Pen>  
 [Verwenden eines Stifts zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Stifte, Linien und Rechtecke in GDI+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
