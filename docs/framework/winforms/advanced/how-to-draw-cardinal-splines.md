---
title: 'Vorgehensweise: Zeichnen von kardinalen Splines'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 12e938567d529b33ead93e081d380a650a803f23
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626218"
---
# <a name="how-to-draw-cardinal-splines"></a><span data-ttu-id="9f35b-102">Vorgehensweise: Zeichnen von kardinalen Splines</span><span class="sxs-lookup"><span data-stu-id="9f35b-102">How to: Draw Cardinal Splines</span></span>
<span data-ttu-id="9f35b-103">Eine cardinal-Splinekurve ist eine Kurve, die einen bestimmten Satz von Punkten reibungslos zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="9f35b-103">A cardinal spline is a curve that passes smoothly through a given set of points.</span></span> <span data-ttu-id="9f35b-104">Um eine cardinal-Splinekurve zu zeichnen, erstellen eine <xref:System.Drawing.Graphics> Objekt, und übergeben Sie die Adresse eines Arrays von Punkten um die <xref:System.Drawing.Graphics.DrawCurve%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="9f35b-104">To draw a cardinal spline, create a <xref:System.Drawing.Graphics> object and pass the address of an array of points to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span>  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a><span data-ttu-id="9f35b-105">Zeichnen eines glockenförmigen kardinalen Splines</span><span class="sxs-lookup"><span data-stu-id="9f35b-105">Drawing a Bell-Shaped Cardinal Spline</span></span>  
  
- <span data-ttu-id="9f35b-106">Im folgende Beispiel zeichnet eine glockenförmigen cardinal-Splinekurve, die fünf angegebenen Punkte durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="9f35b-106">The following example draws a bell-shaped cardinal spline that passes through five designated points.</span></span> <span data-ttu-id="9f35b-107">Die folgende Abbildung zeigt die Kurve und fünf Punkte.</span><span class="sxs-lookup"><span data-stu-id="9f35b-107">The following illustration shows the curve and five points.</span></span>  
  
     ![Das Diagramm, das eine glockenförmigen cardinal-Splinekurve anzeigt.](./media/how-to-draw-cardinal-splines/bell-shaped-cardinal-spline.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a><span data-ttu-id="9f35b-109">Zeichnen einer geschlossenen kardinalen Splines</span><span class="sxs-lookup"><span data-stu-id="9f35b-109">Drawing a Closed Cardinal Spline</span></span>  
  
- <span data-ttu-id="9f35b-110">Verwenden der <xref:System.Drawing.Graphics.DrawClosedCurve%2A> Methode der <xref:System.Drawing.Graphics> Klasse, um eine geschlossene cardinal-Splinekurve zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="9f35b-110">Use the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method of the <xref:System.Drawing.Graphics> class to draw a closed cardinal spline.</span></span> <span data-ttu-id="9f35b-111">In einer geschlossenen cardinal-Splinekurve die Kurve wird fortgesetzt, bis der letzte Punkt im Array und eine Verbindung mit den ersten Punkt im Array.</span><span class="sxs-lookup"><span data-stu-id="9f35b-111">In a closed cardinal spline, the curve continues through the last point in the array and connects with the first point in the array.</span></span> <span data-ttu-id="9f35b-112">Im folgende Beispiel zeichnet eine geschlossene cardinal-Splinekurve, die sechs angegebenen Punkte durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="9f35b-112">The following example draws a closed cardinal spline that passes through six designated points.</span></span> <span data-ttu-id="9f35b-113">Die folgende Abbildung zeigt die geschlossene Splinekurve, die zusammen mit den sechs Punkten:</span><span class="sxs-lookup"><span data-stu-id="9f35b-113">The following illustration shows the closed spline along with the six points:</span></span>  
  
 ![Das Diagramm, die eine geschlossene cardinal-Splinekurve anzeigt.](./media/how-to-draw-cardinal-splines/closed-cardinal-spine.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a><span data-ttu-id="9f35b-115">Ändern der Krümmung eines kardinalen Splines</span><span class="sxs-lookup"><span data-stu-id="9f35b-115">Changing the Bend of a Cardinal Spline</span></span>  
  
- <span data-ttu-id="9f35b-116">Ändern Sie die Möglichkeit, eine cardinal-Splinekurve durch Übergeben eines Arguments Spannung zu sanftesten, der <xref:System.Drawing.Graphics.DrawCurve%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="9f35b-116">Change the way a cardinal spline bends by passing a tension argument to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span> <span data-ttu-id="9f35b-117">Im folgende Beispiel zeichnet drei kardinale Splinekurven, die über den gleichen Satz von Punkten übergeben.</span><span class="sxs-lookup"><span data-stu-id="9f35b-117">The following example draws three cardinal splines that pass through the same set of points.</span></span> <span data-ttu-id="9f35b-118">Die folgende Abbildung zeigt die drei Splines zusammen mit ihren Spannungswerten.</span><span class="sxs-lookup"><span data-stu-id="9f35b-118">The following illustration shows the three splines along with their tension values.</span></span> <span data-ttu-id="9f35b-119">Beachten Sie, wenn die Spannung 0 ist, die Punkte durch gerade Linien verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="9f35b-119">Note that when the tension is 0, the points are connected by straight lines.</span></span>  
  
 ![Das Diagramm, das drei kardinale Splinekurven anzeigt.](./media/how-to-draw-cardinal-splines/three-cardinal-splines.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9f35b-121">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="9f35b-121">Compiling the Code</span></span>  
 <span data-ttu-id="9f35b-122">Im vorherigen Beispiel sind für die Verwendung mit Windows Forms konzipiert und erfordern <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="9f35b-122">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f35b-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f35b-123">See also</span></span>

- [<span data-ttu-id="9f35b-124">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="9f35b-124">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="9f35b-125">Erstellen und Zeichnen von Kurven</span><span class="sxs-lookup"><span data-stu-id="9f35b-125">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
