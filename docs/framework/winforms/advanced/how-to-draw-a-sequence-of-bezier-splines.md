---
title: 'Vorgehensweise: Zeichnen einer Folge von B &#233; Zier Splines'
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
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 76a0ab96f40c1b8d9db6f61d19ece82066b63eb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a>Vorgehensweise: Zeichnen einer Folge von B &#233; Zier Splines
Können Sie die <xref:System.Drawing.Graphics.DrawBeziers%2A> Methode der <xref:System.Drawing.Graphics> Bézier-Splines zum Zeichnen einer Folge von verbunden ist.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel zeichnet eine Kurve, die aus zwei verbundenen Bézier-Splines besteht. Der Endpunkt des ersten Bézier-Splines ist der Startpunkt des zweiten Bézier-Splines.  
  
 Die folgende Abbildung zeigt die verbundenen Splines zusammen mit sieben Punkte.  
  
 ![Bézier-Spline](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Bézier-Splines in GDI+](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [Erstellen und Zeichnen von Kurven](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
