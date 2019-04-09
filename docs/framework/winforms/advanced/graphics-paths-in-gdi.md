---
title: Grafikpfade in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
ms.openlocfilehash: c9a43065210f5ef0fffcae01cc7eb88349696b6b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140503"
---
# <a name="graphics-paths-in-gdi"></a><span data-ttu-id="0d8d1-102">Grafikpfade in GDI+</span><span class="sxs-lookup"><span data-stu-id="0d8d1-102">Graphics Paths in GDI+</span></span>
<span data-ttu-id="0d8d1-103">Pfade werden durch die Kombination von Linien, Rechtecke und einfache Kurven gebildet.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-103">Paths are formed by combining lines, rectangles, and simple curves.</span></span> <span data-ttu-id="0d8d1-104">Erinnern Sie sich an den [Übersicht über Vektorgrafiken](vector-graphics-overview.md) , dass die folgenden grundlegenden Bausteine der am häufigsten für das Zeichnen von Bildern nützlich erwiesen haben:</span><span class="sxs-lookup"><span data-stu-id="0d8d1-104">Recall from the [Vector Graphics Overview](vector-graphics-overview.md) that the following basic building blocks have proven to be the most useful for drawing pictures:</span></span>  
  
-   <span data-ttu-id="0d8d1-105">Linien</span><span class="sxs-lookup"><span data-stu-id="0d8d1-105">Lines</span></span>  
  
-   <span data-ttu-id="0d8d1-106">Rechtecke</span><span class="sxs-lookup"><span data-stu-id="0d8d1-106">Rectangles</span></span>  
  
-   <span data-ttu-id="0d8d1-107">Ellipsen</span><span class="sxs-lookup"><span data-stu-id="0d8d1-107">Ellipses</span></span>  
  
-   <span data-ttu-id="0d8d1-108">Bögen</span><span class="sxs-lookup"><span data-stu-id="0d8d1-108">Arcs</span></span>  
  
-   <span data-ttu-id="0d8d1-109">Polygone</span><span class="sxs-lookup"><span data-stu-id="0d8d1-109">Polygons</span></span>  
  
-   <span data-ttu-id="0d8d1-110">Kardinale splines</span><span class="sxs-lookup"><span data-stu-id="0d8d1-110">Cardinal splines</span></span>  
  
-   <span data-ttu-id="0d8d1-111">Béziersplinekurven</span><span class="sxs-lookup"><span data-stu-id="0d8d1-111">Bézier splines</span></span>  
  
 <span data-ttu-id="0d8d1-112">In GDI + die <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt können Sie eine Sequenz von diese Bausteine in einer einzigen Einheit zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-112">In GDI+, the <xref:System.Drawing.Drawing2D.GraphicsPath> object allows you to collect a sequence of these building blocks into a single unit.</span></span> <span data-ttu-id="0d8d1-113">Die gesamte Sequenz aus Linien, Rechtecke, Polygone und Kurven kann dann mit einem einzigen Aufruf gezeichnet werden die <xref:System.Drawing.Graphics.DrawPath%2A> Methode der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-113">The entire sequence of lines, rectangles, polygons, and curves can then be drawn with one call to the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="0d8d1-114">Die folgende Abbildung zeigt einen Pfad durch Kombination einer Zeile, einen Bogen, eine Béziersplinekurve und eine cardinal-Splinekurve erstellt.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-114">The following illustration shows a path created by combining a line, an arc, a Bézier spline, and a cardinal spline.</span></span>  
  
 <span data-ttu-id="0d8d1-115">![Path](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span><span class="sxs-lookup"><span data-stu-id="0d8d1-115">![Path](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span></span>  
  
## <a name="using-a-path"></a><span data-ttu-id="0d8d1-116">Mithilfe eines Pfads</span><span class="sxs-lookup"><span data-stu-id="0d8d1-116">Using a Path</span></span>  
 <span data-ttu-id="0d8d1-117">Die <xref:System.Drawing.Drawing2D.GraphicsPath> Klasse stellt die folgenden Methoden zum Erstellen einer Sequenz von Elementen, die gezeichnet werden soll: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (für kardinale Splines), und <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-117">The <xref:System.Drawing.Drawing2D.GraphicsPath> class provides the following methods for creating a sequence of items to be drawn: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (for cardinal splines), and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span></span> <span data-ttu-id="0d8d1-118">Jede dieser Methoden überladen wird. Jede Methode unterstützt, d. h. mehrere unterschiedliche Parameterlisten.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-118">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="0d8d1-119">Z. B. eine Variante der der <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> Methode empfängt, vier ganzen Zahlen, und eine andere Variante des der <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> -Methode empfängt zwei <xref:System.Drawing.Point> Objekte.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-119">For example, one variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives four integers, and another variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="0d8d1-120">Die Methoden zum Hinzufügen von Linien, Rechtecke und Béziersplinekurven zu einem Pfad haben im plural Begleitmethoden, die den Pfad in einem einzigen Aufruf mehrere Elemente hinzugefügt: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, und <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-120">The methods for adding lines, rectangles, and Bézier splines to a path have plural companion methods that add several items to the path in a single call: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span></span> <span data-ttu-id="0d8d1-121">Darüber hinaus die <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> und <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> Methoden verfügen über zugehörige Methoden, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> und <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, hinzufügen, die eine geschlossene Kurve oder ein Kreis auf den Pfad.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-121">Also, the <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> methods have companion methods, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, that add a closed curve or pie to the path.</span></span>  
  
 <span data-ttu-id="0d8d1-122">Um einen Pfad zu zeichnen, müssen Sie eine <xref:System.Drawing.Graphics> Objekt eine <xref:System.Drawing.Pen> Objekt und ein <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-122">To draw a path, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="0d8d1-123">Die <xref:System.Drawing.Graphics> -Objekt ermöglicht die <xref:System.Drawing.Graphics.DrawPath%2A> -Methode, und die <xref:System.Drawing.Pen> -Objekt speichert Attribute, z. B. Breite und Farbe der Linie verwendet, um den Pfad zu rendern.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-123">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPath%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the path.</span></span> <span data-ttu-id="0d8d1-124">Die <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt speichert die Sequenz von Linien und Kurven, die den Pfad zu bilden.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-124">The <xref:System.Drawing.Drawing2D.GraphicsPath> object stores the sequence of lines and curves that make up the path.</span></span> <span data-ttu-id="0d8d1-125">Die <xref:System.Drawing.Pen> Objekt und die <xref:System.Drawing.Drawing2D.GraphicsPath> -Objekt übergeben werden, als Argumente für die <xref:System.Drawing.Graphics.DrawPath%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-125">The <xref:System.Drawing.Pen> object and the <xref:System.Drawing.Drawing2D.GraphicsPath> object are passed as arguments to the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="0d8d1-126">Das folgende Beispiel zeichnet einen Pfad, der eine Zeile und eine Ellipse eine Béziersplinekurve besteht:</span><span class="sxs-lookup"><span data-stu-id="0d8d1-126">The following example draws a path that consists of a line, an ellipse, and a Bézier spline:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#101](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 <span data-ttu-id="0d8d1-127">Die folgende Abbildung zeigt den Pfad an.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-127">The following illustration shows the path.</span></span>  
  
 <span data-ttu-id="0d8d1-128">![Path](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span><span class="sxs-lookup"><span data-stu-id="0d8d1-128">![Path](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span></span>  
  
 <span data-ttu-id="0d8d1-129">Zusätzlich zum Hinzufügen von Linien, Rechtecke und Kurven in einen Pfad, können Sie Pfade zu einem Pfad hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-129">In addition to adding lines, rectangles, and curves to a path, you can add paths to a path.</span></span> <span data-ttu-id="0d8d1-130">Dadurch können Sie vorhandene Pfade zu großen, komplexen Pfaden zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-130">This allows you to combine existing paths to form large, complex paths.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#102](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 <span data-ttu-id="0d8d1-131">Es gibt zwei weitere Elemente können Sie einen Pfad hinzufügen: Zeichenfolgen und Kreisen.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-131">There are two other items you can add to a path: strings and pies.</span></span> <span data-ttu-id="0d8d1-132">Ein Kreis ist ein Teil das Innere einer Ellipse an.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-132">A pie is a portion of the interior of an ellipse.</span></span> <span data-ttu-id="0d8d1-133">Das folgende Beispiel erstellt einen Pfad in einen Bogen, eine cardinal-Splinekurve, eine Zeichenfolge und einem Kreis dargestellt:</span><span class="sxs-lookup"><span data-stu-id="0d8d1-133">The following example creates a path from an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#103](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 <span data-ttu-id="0d8d1-134">Die folgende Abbildung zeigt den Pfad an.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-134">The following illustration shows the path.</span></span> <span data-ttu-id="0d8d1-135">Beachten Sie, dass ein Pfad nicht verbunden sein. der Bogen, cardinal-Splinekurve, Zeichenfolgen- und Kreis werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="0d8d1-135">Note that a path does not have to be connected; the arc, cardinal spline, string, and pie are separated.</span></span>  
  
 <span data-ttu-id="0d8d1-136">![Paths](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span><span class="sxs-lookup"><span data-stu-id="0d8d1-136">![Paths](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d8d1-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d8d1-137">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="0d8d1-138">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="0d8d1-138">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="0d8d1-139">Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="0d8d1-139">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="0d8d1-140">Erstellen und Zeichnen von Pfaden</span><span class="sxs-lookup"><span data-stu-id="0d8d1-140">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
