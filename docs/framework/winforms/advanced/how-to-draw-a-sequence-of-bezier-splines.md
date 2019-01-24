---
title: 'Vorgehensweise: Zeichnen Sie eine Sequenz von B&#233;Zier Splines'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 45e56113334be4c384ef6f615d3062ed7f098ad1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572889"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a><span data-ttu-id="4b46e-102">Vorgehensweise: Zeichnen Sie eine Sequenz von B&#233;Zier Splines</span><span class="sxs-lookup"><span data-stu-id="4b46e-102">How to: Draw a Sequence of B&#233;zier Splines</span></span>
<span data-ttu-id="4b46e-103">Können Sie die <xref:System.Drawing.Graphics.DrawBeziers%2A> Methode der <xref:System.Drawing.Graphics> Béziersplinekurven zum Zeichnen einer Sequenz von verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="4b46e-103">You can use the <xref:System.Drawing.Graphics.DrawBeziers%2A> method of the <xref:System.Drawing.Graphics> class to draw a sequence of connected Bézier splines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b46e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4b46e-104">Example</span></span>  
 <span data-ttu-id="4b46e-105">Im folgende Beispiel zeichnet eine Kurve, die aus zwei verbundenen Béziersplinekurven besteht.</span><span class="sxs-lookup"><span data-stu-id="4b46e-105">The following example draws a curve that consists of two connected Bézier splines.</span></span> <span data-ttu-id="4b46e-106">Der Endpunkt die erste Béziersplinekurve ist der Ausgangspunkt der zweiten Béziersplinekurve.</span><span class="sxs-lookup"><span data-stu-id="4b46e-106">The endpoint of the first Bézier spline is the start point of the second Bézier spline.</span></span>  
  
 <span data-ttu-id="4b46e-107">Die folgende Abbildung zeigt die verbundenen Splines sowie die sieben Punkte.</span><span class="sxs-lookup"><span data-stu-id="4b46e-107">The following illustration shows the connected splines along with the seven points.</span></span>  
  
 <span data-ttu-id="4b46e-108">![Bezier-Spline](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")</span><span class="sxs-lookup"><span data-stu-id="4b46e-108">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4b46e-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4b46e-109">Compiling the Code</span></span>  
 <span data-ttu-id="4b46e-110">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="4b46e-110">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b46e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b46e-111">See also</span></span>
- [<span data-ttu-id="4b46e-112">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4b46e-112">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="4b46e-113">Béziersplinekurven in GDI +</span><span class="sxs-lookup"><span data-stu-id="4b46e-113">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)
- [<span data-ttu-id="4b46e-114">Erstellen und Zeichnen von Kurven</span><span class="sxs-lookup"><span data-stu-id="4b46e-114">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
