---
title: 'Gewusst wie: Anwenden der Gammakorrektur bei einem Farbverlauf'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: 9c3c9c5c63194b1dee8314a1ef96497a8b78b5ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520733"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a>Gewusst wie: Anwenden der Gammakorrektur bei einem Farbverlauf
Sie können die Gammakorrektur für einem linearen Farbverlaufspinsel aktivieren, durch Festlegen des Pinsels <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> Eigenschaft `true`. Sie können die Gammakorrektur deaktivieren, indem die <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> Eigenschaft `false`. Gammakorrektur ist standardmäßig deaktiviert.  
  
## <a name="example"></a>Beispiel  
 Im Beispiel wird einen linearen Farbverlaufspinsel erstellt und verwendet den Pinsel zwei Rechtecken ausgefüllt. Das erste Rechteck wird ohne Gammakorrektur, und das zweite Rechteck mit Gammakorrektur gefüllt ist.  
  
 Die folgende Abbildung zeigt die beiden ausgefüllten Rechtecke an. Die oberste Rechteck, das Gammakorrektur kein ist, wird in der Mitte dunkel angezeigt. Gleichmäßige Intensität der unteren Rechteck an, das Gammakorrektur verfügt, wird angezeigt.  
  
 ![Farbverlauf](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush>  
 [Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
