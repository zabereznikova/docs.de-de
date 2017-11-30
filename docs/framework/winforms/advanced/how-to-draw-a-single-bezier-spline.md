---
title: 'Vorgehensweise: Zeichnen einer einzigen B &#233; Zier Spline'
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
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ebdba9e01824cc764a6ab759da049add180ba83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-single-b233zier-spline"></a>Vorgehensweise: Zeichnen einer einzigen B &#233; Zier Spline
Eine Béziersplinekurve wird durch vier Punkte definiert: einem Startpunkt, die beiden Steuerpunkte und einen Endpunkt.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel zeichnet eine Béziersplinekurve mit Startpunkt (10, 100) und Endpunkt (200, 100). Das Steuerelement zeigt sind (100, 10) und (150, 150).  
  
 Die folgende Abbildung zeigt die resultierenden Béziersplinekurve sowie dessen Startpunkt, Steuerpunkte und Endpunkt. Die Abbildung zeigt auch die Splinekurve konvexe Hülle, also ein Polygon gebildet, indem Sie die vier Punkte mit geraden verbindet.  
  
 ![Bézier-Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Graphics.DrawBezier%2A>  
 [Bézier-Splines in GDI+](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [Gewusst wie: Zeichnen einer Folge von Bézier-Splines](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
