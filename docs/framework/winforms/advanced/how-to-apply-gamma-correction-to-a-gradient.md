---
title: 'Gewusst wie: Anwenden der Gammakorrektur bei einem Farbverlauf'
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
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2721a45381f2d0befe82d6d0db2630f3eae08d51
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
