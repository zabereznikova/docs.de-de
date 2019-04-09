---
title: Ellipsen und Bögen in GDI+
ms.date: 03/30/2017
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
ms.openlocfilehash: 8bbc2eda6450128eac55576259880e83f07099ab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117455"
---
# <a name="ellipses-and-arcs-in-gdi"></a><span data-ttu-id="ab05d-102">Ellipsen und Bögen in GDI+</span><span class="sxs-lookup"><span data-stu-id="ab05d-102">Ellipses and Arcs in GDI+</span></span>
<span data-ttu-id="ab05d-103">Sie können problemlos zeichnen, Ellipsen und Bögen mithilfe der <xref:System.Drawing.Graphics.DrawEllipse%2A> und <xref:System.Drawing.Graphics.DrawArc%2A> Methoden der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ab05d-103">You can easily draw ellipses and arcs using the <xref:System.Drawing.Graphics.DrawEllipse%2A> and <xref:System.Drawing.Graphics.DrawArc%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="drawing-an-ellipse"></a><span data-ttu-id="ab05d-104">Zeichnen einer Ellipse</span><span class="sxs-lookup"><span data-stu-id="ab05d-104">Drawing an Ellipse</span></span>  
 <span data-ttu-id="ab05d-105">Um eine Ellipse Zeichnen zu können, benötigen Sie eine <xref:System.Drawing.Graphics> Objekt und ein <xref:System.Drawing.Pen> Objekt.</span><span class="sxs-lookup"><span data-stu-id="ab05d-105">To draw an ellipse, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="ab05d-106">Die <xref:System.Drawing.Graphics> -Objekt ermöglicht die <xref:System.Drawing.Graphics.DrawEllipse%2A> -Methode, und die <xref:System.Drawing.Pen> -Objekt speichert Attribute, z. B. Breite und Farbe der Linie verwendet, um die Ellipse zu rendern.</span><span class="sxs-lookup"><span data-stu-id="ab05d-106">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the ellipse.</span></span> <span data-ttu-id="ab05d-107">Die <xref:System.Drawing.Pen> Objekt als eines der Argumente zum Übergeben der <xref:System.Drawing.Graphics.DrawEllipse%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="ab05d-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="ab05d-108">Die übrigen Argumente übergeben werden, um die <xref:System.Drawing.Graphics.DrawEllipse%2A> Methode geben Sie das umschließende Rechteck für die Ellipse.</span><span class="sxs-lookup"><span data-stu-id="ab05d-108">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method specify the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="ab05d-109">Die folgende Abbildung zeigt eine Ellipse zusammen mit seinem umschließenden Rechteck.</span><span class="sxs-lookup"><span data-stu-id="ab05d-109">The following illustration shows an ellipse along with its bounding rectangle.</span></span>  
  
 <span data-ttu-id="ab05d-110">![Ellipsen und Bögen](./media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span><span class="sxs-lookup"><span data-stu-id="ab05d-110">![Ellipses and arcs](./media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span></span>  
  
 <span data-ttu-id="ab05d-111">Im folgende Beispiel zeichnet eine Ellipse; das umschließende Rechteck hat eine Breite von 80 und eine Höhe von 40 und einen oberen linken Ecke von (100, 50):</span><span class="sxs-lookup"><span data-stu-id="ab05d-111">The following example draws an ellipse; the bounding rectangle has a width of 80, a height of 40, and an upper-left corner of (100, 50):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#51](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <xref:System.Drawing.Graphics.DrawEllipse%2A> <span data-ttu-id="ab05d-112">ist eine überladene Methode, der die <xref:System.Drawing.Graphics> Klasse, damit es mehrere Möglichkeiten gibt, können Sie es mit Argumenten angeben.</span><span class="sxs-lookup"><span data-stu-id="ab05d-112">is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="ab05d-113">Sie können z. B. Erstellen einer <xref:System.Drawing.Rectangle> und übergeben Sie die <xref:System.Drawing.Rectangle> auf die <xref:System.Drawing.Graphics.DrawEllipse%2A> Methode als Argument:</span><span class="sxs-lookup"><span data-stu-id="ab05d-113">For example, you can construct a <xref:System.Drawing.Rectangle> and pass the <xref:System.Drawing.Rectangle> to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#52](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a><span data-ttu-id="ab05d-114">Zeichnen einen Bogen</span><span class="sxs-lookup"><span data-stu-id="ab05d-114">Drawing an Arc</span></span>  
 <span data-ttu-id="ab05d-115">Ein Bogen ist ein Teil einer Ellipse an.</span><span class="sxs-lookup"><span data-stu-id="ab05d-115">An arc is a portion of an ellipse.</span></span> <span data-ttu-id="ab05d-116">Um einen Bogen zu zeichnen, rufen Sie die <xref:System.Drawing.Graphics.DrawArc%2A> Methode der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ab05d-116">To draw an arc, you call the <xref:System.Drawing.Graphics.DrawArc%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="ab05d-117">Die Parameter der <xref:System.Drawing.Graphics.DrawArc%2A> Methode sind identisch mit den Parametern der der <xref:System.Drawing.Graphics.DrawEllipse%2A> -Methode, außer dass <xref:System.Drawing.Graphics.DrawArc%2A> erfordert einen Startwinkel und mittelpunktswinkel.</span><span class="sxs-lookup"><span data-stu-id="ab05d-117">The parameters of the <xref:System.Drawing.Graphics.DrawArc%2A> method are the same as the parameters of the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, except that <xref:System.Drawing.Graphics.DrawArc%2A> requires a starting angle and sweep angle.</span></span> <span data-ttu-id="ab05d-118">Das folgende Beispiel zeichnet einen Bogen mit einem Startwinkel von 30 Grad und bei einem mittelpunktswinkel von 180 Grad:</span><span class="sxs-lookup"><span data-stu-id="ab05d-118">The following example draws an arc with a starting angle of 30 degrees and a sweep angle of 180 degrees:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#53](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 <span data-ttu-id="ab05d-119">Die folgende Abbildung zeigt den Bogen mit Strichen, das die Ellipse und das umgebende Rechteck.</span><span class="sxs-lookup"><span data-stu-id="ab05d-119">The following illustration shows the arc, the ellipse, and the bounding rectangle.</span></span>  
  
 <span data-ttu-id="ab05d-120">![Ellipsen und Bögen](./media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span><span class="sxs-lookup"><span data-stu-id="ab05d-120">![Ellipses and arcs](./media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab05d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab05d-121">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="ab05d-122">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="ab05d-122">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="ab05d-123">Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="ab05d-123">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="ab05d-124">Vorgehensweise: Erstellen eines Stifts</span><span class="sxs-lookup"><span data-stu-id="ab05d-124">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="ab05d-125">Vorgehensweise: Zeichnen der Kontur einer Form</span><span class="sxs-lookup"><span data-stu-id="ab05d-125">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)
