---
title: B&#233;Zier Splines in GDI +
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
ms.openlocfilehash: ff4e9eb18610b70c88e057d3d44020321bbb9f4f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107327"
---
# <a name="b233zier-splines-in-gdi"></a><span data-ttu-id="5e642-102">B&#233;Zier Splines in GDI +</span><span class="sxs-lookup"><span data-stu-id="5e642-102">B&#233;zier Splines in GDI+</span></span>
<span data-ttu-id="5e642-103">Eine Béziersplinekurve ist eine Kurve, die durch vier Punkte angegeben: zwei Endpunkte (p1 und p2) und zwei Punkte (c1 und c2).</span><span class="sxs-lookup"><span data-stu-id="5e642-103">A Bézier spline is a curve specified by four points: two end points (p1 and p2) and two control points (c1 and c2).</span></span> <span data-ttu-id="5e642-104">Die Kurve p1 beginnt und endet bei p2.</span><span class="sxs-lookup"><span data-stu-id="5e642-104">The curve begins at p1 and ends at p2.</span></span> <span data-ttu-id="5e642-105">Die Kurve übergibt die nicht über die Kontrollpunkte, sondern die Control-Punkte als Magnetquellen, per Pull von der Kurve in bestimmte Anweisungen und einen Einfluss auf die Möglichkeit Steuerpunkte.</span><span class="sxs-lookup"><span data-stu-id="5e642-105">The curve does not pass through the control points, but the control points act as magnets, pulling the curve in certain directions and influencing the way the curve bends.</span></span> <span data-ttu-id="5e642-106">Die folgende Abbildung zeigt eine Bézierkurve zusammen mit den End- und die Control-Punkte.</span><span class="sxs-lookup"><span data-stu-id="5e642-106">The following illustration shows a Bézier curve along with its endpoints and control points.</span></span>  
  
 <span data-ttu-id="5e642-107">![Bezier-Splines](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span><span class="sxs-lookup"><span data-stu-id="5e642-107">![Bezier Splines](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span></span>  
  
 <span data-ttu-id="5e642-108">Die Kurve beginnt bei p1 und für das Steuerelement zeigen c1 verschiebt.</span><span class="sxs-lookup"><span data-stu-id="5e642-108">The curve starts at p1 and moves toward the control point c1.</span></span> <span data-ttu-id="5e642-109">Die Tangente der Kurve in p1 ist die Zeile, die von p1 zu c1 gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="5e642-109">The tangent line to the curve at p1 is the line drawn from p1 to c1.</span></span> <span data-ttu-id="5e642-110">Die Tangente im Endpunkt P2 ist die Zeile zu p2 c2 gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="5e642-110">The tangent line at the endpoint p2 is the line drawn from c2 to p2.</span></span>  
  
## <a name="drawing-bzier-splines"></a><span data-ttu-id="5e642-111">Zeichnen Béziersplinekurven</span><span class="sxs-lookup"><span data-stu-id="5e642-111">Drawing Bézier Splines</span></span>  
 <span data-ttu-id="5e642-112">Um eine Béziersplinekurve Zeichnen zu können, benötigen Sie eine Instanz von der <xref:System.Drawing.Graphics> Klasse und ein <xref:System.Drawing.Pen>.</span><span class="sxs-lookup"><span data-stu-id="5e642-112">To draw a Bézier spline, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Pen>.</span></span> <span data-ttu-id="5e642-113">Die Instanz von der <xref:System.Drawing.Graphics> -Klasse stellt die <xref:System.Drawing.Graphics.DrawBezier%2A> -Methode, und die <xref:System.Drawing.Pen> speichert Attribute, z. B. Breite und Farbe der Linie, die zum Rendern der Kurve verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e642-113">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawBezier%2A> method, and the <xref:System.Drawing.Pen> stores attributes, such as width and color, of the line used to render the curve.</span></span> <span data-ttu-id="5e642-114">Die <xref:System.Drawing.Pen> wird als eines der Argumente zu übergeben, die <xref:System.Drawing.Graphics.DrawBezier%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="5e642-114">The <xref:System.Drawing.Pen> is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawBezier%2A> method.</span></span> <span data-ttu-id="5e642-115">Die übrigen Argumente übergeben werden, um die <xref:System.Drawing.Graphics.DrawBezier%2A> Methode sind die Endpunkte und die Kontrollpunkte.</span><span class="sxs-lookup"><span data-stu-id="5e642-115">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawBezier%2A> method are the endpoints and the control points.</span></span> <span data-ttu-id="5e642-116">Im folgende Beispiel zeichnet eine Béziersplinekurve mit dem Anfangspunkt (0, 0), Punkt ("40", "20") und (80, 150) zu steuern und dem Endpunkt (100, 10):</span><span class="sxs-lookup"><span data-stu-id="5e642-116">The following example draws a Bézier spline with starting point (0, 0), control points (40, 20) and (80, 150), and ending point (100, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#71](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 <span data-ttu-id="5e642-117">Die folgende Abbildung zeigt die Kurve, die Control-Punkte und zwei Tangenten.</span><span class="sxs-lookup"><span data-stu-id="5e642-117">The following illustration shows the curve, the control points, and two tangent lines.</span></span>  
  
 <span data-ttu-id="5e642-118">![Bezier-Splines](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span><span class="sxs-lookup"><span data-stu-id="5e642-118">![Bezier Splines](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span></span>  
  
 <span data-ttu-id="5e642-119">Béziersplinekurven wurden ursprünglich von Pierre Bézier für den Entwurf in der Automobilindustrie entwickelt.</span><span class="sxs-lookup"><span data-stu-id="5e642-119">Bézier splines were originally developed by Pierre Bézier for design in the automotive industry.</span></span> <span data-ttu-id="5e642-120">Sie haben da belegt, dass Sie in vielen Arten von CAD / CAM nützlich und werden auch verwendet, um die Umrisse von Schriftarten zu definieren.</span><span class="sxs-lookup"><span data-stu-id="5e642-120">They have since proven to be useful in many types of computer-aided design and are also used to define the outlines of fonts.</span></span> <span data-ttu-id="5e642-121">Béziersplinekurven können eine Vielzahl von Formen ergeben, von die einige in der folgenden Abbildung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5e642-121">Bézier splines can yield a wide variety of shapes, some of which are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="5e642-122">![Paths](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span><span class="sxs-lookup"><span data-stu-id="5e642-122">![Paths](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e642-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e642-123">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="5e642-124">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="5e642-124">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="5e642-125">Erstellen und Zeichnen von Kurven</span><span class="sxs-lookup"><span data-stu-id="5e642-125">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
- [<span data-ttu-id="5e642-126">Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="5e642-126">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="5e642-127">Vorgehensweise: Erstellen eines Stifts</span><span class="sxs-lookup"><span data-stu-id="5e642-127">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
