---
title: 'Vorgehensweise: Zeichnen einer Sequenz von B&#233;Zier Splines'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 8439e08109630b9a59c8e0359aa4d18e5241412c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521406"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a><span data-ttu-id="03b50-102">Vorgehensweise: Zeichnen einer Sequenz von B&#233;Zier Splines</span><span class="sxs-lookup"><span data-stu-id="03b50-102">How to: Draw a Sequence of B&#233;zier Splines</span></span>
<span data-ttu-id="03b50-103">Können Sie die <xref:System.Drawing.Graphics.DrawBeziers%2A> Methode der <xref:System.Drawing.Graphics> Bézier-Splines zum Zeichnen einer Folge von verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="03b50-103">You can use the <xref:System.Drawing.Graphics.DrawBeziers%2A> method of the <xref:System.Drawing.Graphics> class to draw a sequence of connected Bézier splines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03b50-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03b50-104">Example</span></span>  
 <span data-ttu-id="03b50-105">Im folgende Beispiel zeichnet eine Kurve, die aus zwei verbundenen Bézier-Splines besteht.</span><span class="sxs-lookup"><span data-stu-id="03b50-105">The following example draws a curve that consists of two connected Bézier splines.</span></span> <span data-ttu-id="03b50-106">Der Endpunkt des ersten Bézier-Splines ist der Startpunkt des zweiten Bézier-Splines.</span><span class="sxs-lookup"><span data-stu-id="03b50-106">The endpoint of the first Bézier spline is the start point of the second Bézier spline.</span></span>  
  
 <span data-ttu-id="03b50-107">Die folgende Abbildung zeigt die verbundenen Splines zusammen mit sieben Punkte.</span><span class="sxs-lookup"><span data-stu-id="03b50-107">The following illustration shows the connected splines along with the seven points.</span></span>  
  
 <span data-ttu-id="03b50-108">![Bézier-Spline](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")</span><span class="sxs-lookup"><span data-stu-id="03b50-108">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="03b50-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="03b50-109">Compiling the Code</span></span>  
 <span data-ttu-id="03b50-110">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="03b50-110">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03b50-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03b50-111">See Also</span></span>  
 [<span data-ttu-id="03b50-112">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="03b50-112">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="03b50-113">Bézier-Splines in GDI +</span><span class="sxs-lookup"><span data-stu-id="03b50-113">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [<span data-ttu-id="03b50-114">Erstellen und Zeichnen von Kurven</span><span class="sxs-lookup"><span data-stu-id="03b50-114">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
