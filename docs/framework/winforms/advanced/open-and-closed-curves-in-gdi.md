---
title: Offene und geschlossene Kurven in GDI+
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
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cde1aae6196ef8b773b8c072a42c700924f9c8cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="open-and-closed-curves-in-gdi"></a><span data-ttu-id="b201e-102">Offene und geschlossene Kurven in GDI+</span><span class="sxs-lookup"><span data-stu-id="b201e-102">Open and Closed Curves in GDI+</span></span>
<span data-ttu-id="b201e-103">Die folgende Abbildung zeigt zwei Kurven: eine offene und eine geschlossen.</span><span class="sxs-lookup"><span data-stu-id="b201e-103">The following illustration shows two curves: one open and one closed.</span></span>  
  
 <span data-ttu-id="b201e-104">![Offene und geschlossene Kurven](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span><span class="sxs-lookup"><span data-stu-id="b201e-104">![Open & Closed curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span></span>  
  
## <a name="managed-interface-for-curves"></a><span data-ttu-id="b201e-105">Verwaltete Schnittstelle für Kurven</span><span class="sxs-lookup"><span data-stu-id="b201e-105">Managed Interface for Curves</span></span>  
 <span data-ttu-id="b201e-106">Geschlossene Kurven dem inneren haben und daher mit einem Pinsel ausgefüllt werden können.</span><span class="sxs-lookup"><span data-stu-id="b201e-106">Closed curves have an interior and therefore can be filled with a brush.</span></span> <span data-ttu-id="b201e-107">Die <xref:System.Drawing.Graphics> -Klasse im [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet die folgenden Methoden zum Füllen geschlossener Formen und Kurven: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, und <xref:System.Drawing.Graphics.FillRegion%2A>.</span><span class="sxs-lookup"><span data-stu-id="b201e-107">The <xref:System.Drawing.Graphics> class in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] provides the following methods for filling closed shapes and curves: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, and <xref:System.Drawing.Graphics.FillRegion%2A>.</span></span> <span data-ttu-id="b201e-108">Wenn Sie eine der folgenden Methoden aufrufen, müssen Sie einen der Pinseltypen bestimmten übergeben (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, oder <xref:System.Drawing.Drawing2D.PathGradientBrush>) als Argument.</span><span class="sxs-lookup"><span data-stu-id="b201e-108">Whenever you call one of these methods, you must pass one of the specific brush types (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, or <xref:System.Drawing.Drawing2D.PathGradientBrush>) as an argument.</span></span>  
  
 <span data-ttu-id="b201e-109">Die <xref:System.Drawing.Graphics.FillPie%2A> Methode ist eine Ergänzung zu den <xref:System.Drawing.Graphics.DrawArc%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="b201e-109">The <xref:System.Drawing.Graphics.FillPie%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawArc%2A> method.</span></span> <span data-ttu-id="b201e-110">Ebenso wie die <xref:System.Drawing.Graphics.DrawArc%2A> Methode zeichnet einen Teil der Kontur einer Ellipse, die <xref:System.Drawing.Graphics.FillPie%2A> Methode füllt einen Teil der das Innere einer Ellipse.</span><span class="sxs-lookup"><span data-stu-id="b201e-110">Just as the <xref:System.Drawing.Graphics.DrawArc%2A> method draws a portion of the outline of an ellipse, the <xref:System.Drawing.Graphics.FillPie%2A> method fills a portion of the interior of an ellipse.</span></span> <span data-ttu-id="b201e-111">Im folgenden Beispiel zeichnet einen Bogen und füllt den betreffenden Teil das Innere der Ellipse:</span><span class="sxs-lookup"><span data-stu-id="b201e-111">The following example draws an arc and fills the corresponding portion of the interior of the ellipse:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 <span data-ttu-id="b201e-112">Die folgende Abbildung zeigt den Bogen und der ausgefüllte Kreis.</span><span class="sxs-lookup"><span data-stu-id="b201e-112">The following illustration shows the arc and the filled pie.</span></span>  
  
 <span data-ttu-id="b201e-113">![Offene und geschlossene Kurven](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span><span class="sxs-lookup"><span data-stu-id="b201e-113">![Open & Closed curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span></span>  
  
 <span data-ttu-id="b201e-114">Die <xref:System.Drawing.Graphics.FillClosedCurve%2A> Methode ist eine Ergänzung zu den <xref:System.Drawing.Graphics.DrawClosedCurve%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="b201e-114">The <xref:System.Drawing.Graphics.FillClosedCurve%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method.</span></span> <span data-ttu-id="b201e-115">Beide Methoden schließen die Kurve automatisch durch Herstellen einer Verbindung den Endpunkt auf den Startpunkt.</span><span class="sxs-lookup"><span data-stu-id="b201e-115">Both methods automatically close the curve by connecting the ending point to the starting point.</span></span> <span data-ttu-id="b201e-116">Im folgende Beispiel zeichnet eine Kurve, die durchlaufen (0, 0), (60, 20) und (40, 50).</span><span class="sxs-lookup"><span data-stu-id="b201e-116">The following example draws a curve that passes through (0, 0), (60, 20), and (40, 50).</span></span> <span data-ttu-id="b201e-117">Die Kurve wird dann automatisch geschlossen, durch Herstellen einer Verbindung (40, 50) zum Anfangspunkt (0, 0), und das innere mit einer Volltonfarbe gefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="b201e-117">Then, the curve is automatically closed by connecting (40, 50) to the starting point (0, 0), and the interior is filled with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 <span data-ttu-id="b201e-118">Die <xref:System.Drawing.Graphics.FillPath%2A> Methode füllt das Innere der separate Teile eines Pfads.</span><span class="sxs-lookup"><span data-stu-id="b201e-118">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the interiors of the separate pieces of a path.</span></span> <span data-ttu-id="b201e-119">Wenn ein Teil eines Pfads einen geschlossenen Kurve oder eine Form, bilden keine der <xref:System.Drawing.Graphics.FillPath%2A> Methode dieser Teil des Pfads wird vor dem Ausfüllen es automatisch geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="b201e-119">If a piece of a path doesn't form a closed curve or shape, the <xref:System.Drawing.Graphics.FillPath%2A> method automatically closes that piece of the path before filling it.</span></span> <span data-ttu-id="b201e-120">Im folgenden Beispiel zeichnet und füllt einen Pfad, der einen Bogen, eine cardinal-Splinekurve, eine Zeichenfolge und einem Kreis besteht:</span><span class="sxs-lookup"><span data-stu-id="b201e-120">The following example draws and fills a path that consists of an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 <span data-ttu-id="b201e-121">Die folgende Abbildung zeigt den Pfad mit und ohne die einfarbige Füllung.</span><span class="sxs-lookup"><span data-stu-id="b201e-121">The following illustration shows the path with and without the solid fill.</span></span> <span data-ttu-id="b201e-122">Beachten Sie, dass der Text in der Zeichenfolge beschrieben wird, aber nicht, indem ausgefüllt die <xref:System.Drawing.Graphics.DrawPath%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="b201e-122">Note that the text in the string is outlined, but not filled, by the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="b201e-123">Es ist die <xref:System.Drawing.Graphics.FillPath%2A> -Methode, die die Innenflächen der Zeichen in der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b201e-123">It is the <xref:System.Drawing.Graphics.FillPath%2A> method that paints the interiors of the characters in the string.</span></span>  
  
 <span data-ttu-id="b201e-124">![Zeichenfolge in einem Pfad](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span><span class="sxs-lookup"><span data-stu-id="b201e-124">![String in a path](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b201e-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b201e-125">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Point?displayProperty=nameWithType>  
 [<span data-ttu-id="b201e-126">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="b201e-126">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="b201e-127">Gewusst wie: Erstellen von Grafikobjekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="b201e-127">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="b201e-128">Erstellen und Zeichnen von Pfaden</span><span class="sxs-lookup"><span data-stu-id="b201e-128">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
