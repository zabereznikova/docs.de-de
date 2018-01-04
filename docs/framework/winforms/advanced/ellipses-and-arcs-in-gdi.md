---
title: "Ellipsen und Bögen in GDI+"
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
- arcs
- GDI+, arcs
- drawing [Windows Forms], ellipses
- GDI+, ellipses
- ellipses
- drawing [Windows Forms], arcs
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 71126942f4cde37cc5d26bfba029c5f50f1065a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ellipses-and-arcs-in-gdi"></a><span data-ttu-id="4c336-102">Ellipsen und Bögen in GDI+</span><span class="sxs-lookup"><span data-stu-id="4c336-102">Ellipses and Arcs in GDI+</span></span>
<span data-ttu-id="4c336-103">Sie können problemlos zeichnen Ellipsen und Bögen mit der <xref:System.Drawing.Graphics.DrawEllipse%2A> und <xref:System.Drawing.Graphics.DrawArc%2A> Methoden die <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="4c336-103">You can easily draw ellipses and arcs using the <xref:System.Drawing.Graphics.DrawEllipse%2A> and <xref:System.Drawing.Graphics.DrawArc%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="drawing-an-ellipse"></a><span data-ttu-id="4c336-104">Zeichnen einer Ellipse</span><span class="sxs-lookup"><span data-stu-id="4c336-104">Drawing an Ellipse</span></span>  
 <span data-ttu-id="4c336-105">Um eine Ellipse zu zeichnen, müssen Sie eine <xref:System.Drawing.Graphics> Objekt und ein <xref:System.Drawing.Pen> Objekt.</span><span class="sxs-lookup"><span data-stu-id="4c336-105">To draw an ellipse, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="4c336-106">Die <xref:System.Drawing.Graphics> Objekt enthält die <xref:System.Drawing.Graphics.DrawEllipse%2A> -Methode, und die <xref:System.Drawing.Pen> Objekt speichert Attribute, z. B. Breite und Farbe der Linie, die zum Rendern der Ellipse verwendet.</span><span class="sxs-lookup"><span data-stu-id="4c336-106">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the ellipse.</span></span> <span data-ttu-id="4c336-107">Die <xref:System.Drawing.Pen> Objekt als eines der Argumente zu übergeben der <xref:System.Drawing.Graphics.DrawEllipse%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="4c336-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="4c336-108">Die übrigen Argumente zu übergeben, um die <xref:System.Drawing.Graphics.DrawEllipse%2A> Methode geben Sie das umschließende Rechteck für die Ellipse.</span><span class="sxs-lookup"><span data-stu-id="4c336-108">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method specify the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="4c336-109">Die folgende Abbildung zeigt eine Ellipse, die zusammen mit das umschließende Rechteck.</span><span class="sxs-lookup"><span data-stu-id="4c336-109">The following illustration shows an ellipse along with its bounding rectangle.</span></span>  
  
 <span data-ttu-id="4c336-110">![Ellipsen und Bögen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span><span class="sxs-lookup"><span data-stu-id="4c336-110">![Ellipses and arcs](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span></span>  
  
 <span data-ttu-id="4c336-111">Im folgende Beispiel zeichnet eine Ellipse; das umschließende Rechteck hat eine Breite von 80, eine Höhe von 40 und einen oberen linken Ecke des (100, 50):</span><span class="sxs-lookup"><span data-stu-id="4c336-111">The following example draws an ellipse; the bounding rectangle has a width of 80, a height of 40, and an upper-left corner of (100, 50):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <span data-ttu-id="4c336-112"><xref:System.Drawing.Graphics.DrawEllipse%2A>eine überladene Methode wird die <xref:System.Drawing.Graphics> Klasse, damit es gibt mehrere Möglichkeiten, die Sie Argumente angeben können.</span><span class="sxs-lookup"><span data-stu-id="4c336-112"><xref:System.Drawing.Graphics.DrawEllipse%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="4c336-113">Sie können z. B. Erstellen einer <xref:System.Drawing.Rectangle> und übergeben Sie der <xref:System.Drawing.Rectangle> zu der <xref:System.Drawing.Graphics.DrawEllipse%2A> Methode als Argument:</span><span class="sxs-lookup"><span data-stu-id="4c336-113">For example, you can construct a <xref:System.Drawing.Rectangle> and pass the <xref:System.Drawing.Rectangle> to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#52](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a><span data-ttu-id="4c336-114">Zeichnen eines Bogens</span><span class="sxs-lookup"><span data-stu-id="4c336-114">Drawing an Arc</span></span>  
 <span data-ttu-id="4c336-115">Ein Bogen ist ein Teil einer Ellipse.</span><span class="sxs-lookup"><span data-stu-id="4c336-115">An arc is a portion of an ellipse.</span></span> <span data-ttu-id="4c336-116">Um einen Bogen zu zeichnen, rufen Sie die <xref:System.Drawing.Graphics.DrawArc%2A> Methode der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="4c336-116">To draw an arc, you call the <xref:System.Drawing.Graphics.DrawArc%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="4c336-117">Die Parameter von der <xref:System.Drawing.Graphics.DrawArc%2A> Methode sind identisch mit den Parametern des der <xref:System.Drawing.Graphics.DrawEllipse%2A> -Methode, außer dass <xref:System.Drawing.Graphics.DrawArc%2A> erfordert eine Startwinkel und mittelpunktswinkel.</span><span class="sxs-lookup"><span data-stu-id="4c336-117">The parameters of the <xref:System.Drawing.Graphics.DrawArc%2A> method are the same as the parameters of the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, except that <xref:System.Drawing.Graphics.DrawArc%2A> requires a starting angle and sweep angle.</span></span> <span data-ttu-id="4c336-118">Im folgende Beispiel zeichnet einen Bogen mit einem Startwinkel von 30 Grad und bei einem mittelpunktswinkel von 180 Grad:</span><span class="sxs-lookup"><span data-stu-id="4c336-118">The following example draws an arc with a starting angle of 30 degrees and a sweep angle of 180 degrees:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#53](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 <span data-ttu-id="4c336-119">Die folgende Abbildung zeigt den Bogen, das die Ellipse und das umschließende Rechteck.</span><span class="sxs-lookup"><span data-stu-id="4c336-119">The following illustration shows the arc, the ellipse, and the bounding rectangle.</span></span>  
  
 <span data-ttu-id="4c336-120">![Ellipsen und Bögen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span><span class="sxs-lookup"><span data-stu-id="4c336-120">![Ellipses and arcs](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c336-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c336-121">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="4c336-122">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="4c336-122">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="4c336-123">Gewusst wie: Erstellen von Grafikobjekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="4c336-123">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="4c336-124">Gewusst wie: Erstellen eines Stifts</span><span class="sxs-lookup"><span data-stu-id="4c336-124">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [<span data-ttu-id="4c336-125">Gewusst wie: Zeichnen der Kontur einer Form</span><span class="sxs-lookup"><span data-stu-id="4c336-125">How to: Draw an Outlined Shape</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
