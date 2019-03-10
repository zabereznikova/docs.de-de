---
title: Offene und geschlossene Kurven in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
ms.openlocfilehash: bc78077be45f22826eaa23a746dcf272601d51b4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711459"
---
# <a name="open-and-closed-curves-in-gdi"></a><span data-ttu-id="c445f-102">Offene und geschlossene Kurven in GDI+</span><span class="sxs-lookup"><span data-stu-id="c445f-102">Open and Closed Curves in GDI+</span></span>
<span data-ttu-id="c445f-103">Die folgende Abbildung zeigt zwei Kurven geteilt: eine offene und eine geschlossen.</span><span class="sxs-lookup"><span data-stu-id="c445f-103">The following illustration shows two curves: one open and one closed.</span></span>  
  
 <span data-ttu-id="c445f-104">![Offene und geschlossene Kurven](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span><span class="sxs-lookup"><span data-stu-id="c445f-104">![Open & Closed curves](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span></span>  
  
## <a name="managed-interface-for-curves"></a><span data-ttu-id="c445f-105">Verwaltete Schnittstelle für die Kurven</span><span class="sxs-lookup"><span data-stu-id="c445f-105">Managed Interface for Curves</span></span>  
 <span data-ttu-id="c445f-106">Geschlossene Kurven ein inneres haben und können daher mit einem Pinsel gefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="c445f-106">Closed curves have an interior and therefore can be filled with a brush.</span></span> <span data-ttu-id="c445f-107">Die <xref:System.Drawing.Graphics> -Klasse im [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet die folgenden Methoden zum Füllen geschlossene Formen und Kurven: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, und <xref:System.Drawing.Graphics.FillRegion%2A>.</span><span class="sxs-lookup"><span data-stu-id="c445f-107">The <xref:System.Drawing.Graphics> class in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] provides the following methods for filling closed shapes and curves: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, and <xref:System.Drawing.Graphics.FillRegion%2A>.</span></span> <span data-ttu-id="c445f-108">Wenn Sie eine der folgenden Methoden aufrufen, müssen Sie eine der bestimmten Pinseltyp übergeben (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, oder <xref:System.Drawing.Drawing2D.PathGradientBrush>) als Argument.</span><span class="sxs-lookup"><span data-stu-id="c445f-108">Whenever you call one of these methods, you must pass one of the specific brush types (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, or <xref:System.Drawing.Drawing2D.PathGradientBrush>) as an argument.</span></span>  
  
 <span data-ttu-id="c445f-109">Die <xref:System.Drawing.Graphics.FillPie%2A> Methode ist eine Ergänzung für die <xref:System.Drawing.Graphics.DrawArc%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="c445f-109">The <xref:System.Drawing.Graphics.FillPie%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawArc%2A> method.</span></span> <span data-ttu-id="c445f-110">Ebenso wie die <xref:System.Drawing.Graphics.DrawArc%2A> Methode zeichnet einen Teil der Kontur einer Ellipse, die <xref:System.Drawing.Graphics.FillPie%2A> Methode füllt einen Teil der das Innere einer Ellipse.</span><span class="sxs-lookup"><span data-stu-id="c445f-110">Just as the <xref:System.Drawing.Graphics.DrawArc%2A> method draws a portion of the outline of an ellipse, the <xref:System.Drawing.Graphics.FillPie%2A> method fills a portion of the interior of an ellipse.</span></span> <span data-ttu-id="c445f-111">Im folgenden Beispiel zeichnet einen Bogen und den entsprechenden Teil das Innere der Ellipse füllt:</span><span class="sxs-lookup"><span data-stu-id="c445f-111">The following example draws an arc and fills the corresponding portion of the interior of the ellipse:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#21](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 <span data-ttu-id="c445f-112">Die folgende Abbildung zeigt den Bogen mit Strichen und der gefüllten Kreis.</span><span class="sxs-lookup"><span data-stu-id="c445f-112">The following illustration shows the arc and the filled pie.</span></span>  
  
 <span data-ttu-id="c445f-113">![Offene und geschlossene Kurven](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span><span class="sxs-lookup"><span data-stu-id="c445f-113">![Open & Closed curves](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span></span>  
  
 <span data-ttu-id="c445f-114">Die <xref:System.Drawing.Graphics.FillClosedCurve%2A> Methode ist eine Ergänzung für die <xref:System.Drawing.Graphics.DrawClosedCurve%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="c445f-114">The <xref:System.Drawing.Graphics.FillClosedCurve%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method.</span></span> <span data-ttu-id="c445f-115">Beide Methoden schließen die Kurve automatisch durch das Verbinden des Endpunkts mit den Anfangspunkt, an.</span><span class="sxs-lookup"><span data-stu-id="c445f-115">Both methods automatically close the curve by connecting the ending point to the starting point.</span></span> <span data-ttu-id="c445f-116">Das folgende Beispiel zeichnet eine Kurve, die durchlaufen (0, 0), (60, 20) und (40, 50).</span><span class="sxs-lookup"><span data-stu-id="c445f-116">The following example draws a curve that passes through (0, 0), (60, 20), and (40, 50).</span></span> <span data-ttu-id="c445f-117">Die Kurve wird dann automatisch geschlossen, durch das Verbinden (40, 50) zum Ausgangspunkt (0, 0), und das innere mit einer Volltonfarbe gefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="c445f-117">Then, the curve is automatically closed by connecting (40, 50) to the starting point (0, 0), and the interior is filled with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#22](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 <span data-ttu-id="c445f-118">Die <xref:System.Drawing.Graphics.FillPath%2A> Methode füllt das Innere der separate Teile eines Pfads.</span><span class="sxs-lookup"><span data-stu-id="c445f-118">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the interiors of the separate pieces of a path.</span></span> <span data-ttu-id="c445f-119">Wenn ein Teil eines Pfads eine geschlossene Kurve oder Form bilden nicht die <xref:System.Drawing.Graphics.FillPath%2A> Methode dieser Teil des Pfads wird vor dem Ausfüllen es automatisch geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="c445f-119">If a piece of a path doesn't form a closed curve or shape, the <xref:System.Drawing.Graphics.FillPath%2A> method automatically closes that piece of the path before filling it.</span></span> <span data-ttu-id="c445f-120">Im folgenden Beispiel wird gezeichnet, und füllt einen Pfad, der einen Bogen, eine cardinal-Splinekurve, eine Zeichenfolge und einem Kreis besteht:</span><span class="sxs-lookup"><span data-stu-id="c445f-120">The following example draws and fills a path that consists of an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#23](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 <span data-ttu-id="c445f-121">Die folgende Abbildung zeigt den Pfad mit und ohne die einfarbige Füllung.</span><span class="sxs-lookup"><span data-stu-id="c445f-121">The following illustration shows the path with and without the solid fill.</span></span> <span data-ttu-id="c445f-122">Beachten Sie, dass der Text in der Zeichenfolge wird beschrieben, aber nicht, durch ausgefüllt die <xref:System.Drawing.Graphics.DrawPath%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="c445f-122">Note that the text in the string is outlined, but not filled, by the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="c445f-123">Es ist die <xref:System.Drawing.Graphics.FillPath%2A> -Methode, die die Innenflächen der Zeichen in der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c445f-123">It is the <xref:System.Drawing.Graphics.FillPath%2A> method that paints the interiors of the characters in the string.</span></span>  
  
 <span data-ttu-id="c445f-124">![Zeichenfolge in einem Pfad](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span><span class="sxs-lookup"><span data-stu-id="c445f-124">![String in a path](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c445f-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c445f-125">See also</span></span>
- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="c445f-126">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="c445f-126">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="c445f-127">Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="c445f-127">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="c445f-128">Erstellen und Zeichnen von Pfaden</span><span class="sxs-lookup"><span data-stu-id="c445f-128">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
