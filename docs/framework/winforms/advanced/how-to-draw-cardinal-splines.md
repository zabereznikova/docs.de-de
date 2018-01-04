---
title: 'Gewusst wie: Zeichnen von kardinalen Splines'
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
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 64661bbdcb267e2f2ce33b8a8db2ab2aac9a86f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-cardinal-splines"></a><span data-ttu-id="58356-102">Gewusst wie: Zeichnen von kardinalen Splines</span><span class="sxs-lookup"><span data-stu-id="58356-102">How to: Draw Cardinal Splines</span></span>
<span data-ttu-id="58356-103">Eine cardinal-Splinekurve ist eine Kurve, die einen bestimmten Satz von Punkten gleichmäßig zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="58356-103">A cardinal spline is a curve that passes smoothly through a given set of points.</span></span> <span data-ttu-id="58356-104">Um eine cardinal-Splinekurve zu zeichnen, erstellen Sie eine <xref:System.Drawing.Graphics> Objekts und übergeben Sie die Adresse des ein Array von Punkten um die <xref:System.Drawing.Graphics.DrawCurve%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="58356-104">To draw a cardinal spline, create a <xref:System.Drawing.Graphics> object and pass the address of an array of points to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span>  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a><span data-ttu-id="58356-105">Zeichnen eines Bell geformten kardinalen Splines</span><span class="sxs-lookup"><span data-stu-id="58356-105">Drawing a Bell-Shaped Cardinal Spline</span></span>  
  
-   <span data-ttu-id="58356-106">Im folgende Beispiel zeichnet eine Bell geformten cardinal-Splinekurve, die fünf festgelegten Punkt durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="58356-106">The following example draws a bell-shaped cardinal spline that passes through five designated points.</span></span> <span data-ttu-id="58356-107">Die folgende Abbildung zeigt die Kurve und fünf Punkte.</span><span class="sxs-lookup"><span data-stu-id="58356-107">The following illustration shows the curve and five points.</span></span>  
  
     <span data-ttu-id="58356-108">![Kardinaler Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")</span><span class="sxs-lookup"><span data-stu-id="58356-108">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a><span data-ttu-id="58356-109">Zeichnen eines geschlossenen kardinalen Splines</span><span class="sxs-lookup"><span data-stu-id="58356-109">Drawing a Closed Cardinal Spline</span></span>  
  
-   <span data-ttu-id="58356-110">Verwenden der <xref:System.Drawing.Graphics.DrawClosedCurve%2A> Methode der <xref:System.Drawing.Graphics> Klasse eine geschlossene cardinal-Splinekurve gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="58356-110">Use the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method of the <xref:System.Drawing.Graphics> class to draw a closed cardinal spline.</span></span> <span data-ttu-id="58356-111">In einer geschlossenen cardinal-Splinekurve die Kurve wird fortgesetzt, bis der letzte Punkt im Array und eine Verbindung herstellt, mit dem ersten Punkt im Array.</span><span class="sxs-lookup"><span data-stu-id="58356-111">In a closed cardinal spline, the curve continues through the last point in the array and connects with the first point in the array.</span></span> <span data-ttu-id="58356-112">Im folgende Beispiel zeichnet eine geschlossene cardinal-Splinekurve, die sechs festgelegten Punkt durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="58356-112">The following example draws a closed cardinal spline that passes through six designated points.</span></span> <span data-ttu-id="58356-113">Die folgende Abbildung zeigt die geschlossene Splinekurve zusammen mit den sechs Punkten.</span><span class="sxs-lookup"><span data-stu-id="58356-113">The following illustration shows the closed spline along with the six points.</span></span>  
  
 <span data-ttu-id="58356-114">![Kardinaler Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")</span><span class="sxs-lookup"><span data-stu-id="58356-114">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a><span data-ttu-id="58356-115">Ändern der Krümmung eines kardinalen Splines</span><span class="sxs-lookup"><span data-stu-id="58356-115">Changing the Bend of a Cardinal Spline</span></span>  
  
-   <span data-ttu-id="58356-116">Ändern Sie die Möglichkeit, eine cardinal-Splinekurve durch Übergeben eines Arguments Spannung, Kurven, die <xref:System.Drawing.Graphics.DrawCurve%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="58356-116">Change the way a cardinal spline bends by passing a tension argument to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span> <span data-ttu-id="58356-117">Im folgende Beispiel werden drei kardinale Splines, die den gleichen Satz von Punkten durchlaufen gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="58356-117">The following example draws three cardinal splines that pass through the same set of points.</span></span> <span data-ttu-id="58356-118">Die folgende Abbildung zeigt die drei Splines zusammen mit ihren Spannungswerten.</span><span class="sxs-lookup"><span data-stu-id="58356-118">The following illustration shows the three splines along with their tension values.</span></span> <span data-ttu-id="58356-119">Beachten Sie, dass bei die Spannung 0 ist, die Punkte durch gerade Linien verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="58356-119">Note that when the tension is 0, the points are connected by straight lines.</span></span>  
  
 <span data-ttu-id="58356-120">![Kardinaler Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")</span><span class="sxs-lookup"><span data-stu-id="58356-120">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="58356-121">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="58356-121">Compiling the Code</span></span>  
 <span data-ttu-id="58356-122">Siehe vorstehende Beispiele sind für die Verwendung mit Windows Forms konzipiert und erfordern <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="58356-122">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58356-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58356-123">See Also</span></span>  
 [<span data-ttu-id="58356-124">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="58356-124">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="58356-125">Erstellen und Zeichnen von Kurven</span><span class="sxs-lookup"><span data-stu-id="58356-125">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
