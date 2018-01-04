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
ms.workload: dotnet
ms.openlocfilehash: 6d2eaf570190f85ca084e5a5ab5d1bee1be56871
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="79638-102">Vorgehensweise: Zeichnen einer einzigen B &#233; Zier Spline</span><span class="sxs-lookup"><span data-stu-id="79638-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="79638-103">Eine Béziersplinekurve wird durch vier Punkte definiert: einem Startpunkt, die beiden Steuerpunkte und einen Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="79638-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79638-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79638-104">Example</span></span>  
 <span data-ttu-id="79638-105">Im folgende Beispiel zeichnet eine Béziersplinekurve mit Startpunkt (10, 100) und Endpunkt (200, 100).</span><span class="sxs-lookup"><span data-stu-id="79638-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="79638-106">Das Steuerelement zeigt sind (100, 10) und (150, 150).</span><span class="sxs-lookup"><span data-stu-id="79638-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="79638-107">Die folgende Abbildung zeigt die resultierenden Béziersplinekurve sowie dessen Startpunkt, Steuerpunkte und Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="79638-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="79638-108">Die Abbildung zeigt auch die Splinekurve konvexe Hülle, also ein Polygon gebildet, indem Sie die vier Punkte mit geraden verbindet.</span><span class="sxs-lookup"><span data-stu-id="79638-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 <span data-ttu-id="79638-109">![Bézier-Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span><span class="sxs-lookup"><span data-stu-id="79638-109">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="79638-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="79638-110">Compiling the Code</span></span>  
 <span data-ttu-id="79638-111">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="79638-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79638-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79638-112">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawBezier%2A>  
 [<span data-ttu-id="79638-113">Bézier-Splines in GDI +</span><span class="sxs-lookup"><span data-stu-id="79638-113">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [<span data-ttu-id="79638-114">Gewusst wie: Zeichnen einer Folge von Bézier-Splines</span><span class="sxs-lookup"><span data-stu-id="79638-114">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
