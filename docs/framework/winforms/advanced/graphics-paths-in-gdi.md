---
title: Grafikpfade in GDI+
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
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e027228ea1cc047f213c28ac3a4984c2f0227c5a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="graphics-paths-in-gdi"></a><span data-ttu-id="42114-102">Grafikpfade in GDI+</span><span class="sxs-lookup"><span data-stu-id="42114-102">Graphics Paths in GDI+</span></span>
<span data-ttu-id="42114-103">Pfade werden durch Kombinieren von Linien, Rechtecke und einfachen Kurven gebildet.</span><span class="sxs-lookup"><span data-stu-id="42114-103">Paths are formed by combining lines, rectangles, and simple curves.</span></span> <span data-ttu-id="42114-104">Beachten Sie aus der [Übersicht über Vektorgrafiken](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md) , dass die folgenden grundlegenden Bausteine besonders hilfreich erwiesen haben für das Zeichnen von Bildern:</span><span class="sxs-lookup"><span data-stu-id="42114-104">Recall from the [Vector Graphics Overview](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md) that the following basic building blocks have proven to be the most useful for drawing pictures:</span></span>  
  
-   <span data-ttu-id="42114-105">Linien</span><span class="sxs-lookup"><span data-stu-id="42114-105">Lines</span></span>  
  
-   <span data-ttu-id="42114-106">Rechtecke</span><span class="sxs-lookup"><span data-stu-id="42114-106">Rectangles</span></span>  
  
-   <span data-ttu-id="42114-107">Ellipsen</span><span class="sxs-lookup"><span data-stu-id="42114-107">Ellipses</span></span>  
  
-   <span data-ttu-id="42114-108">Bögen</span><span class="sxs-lookup"><span data-stu-id="42114-108">Arcs</span></span>  
  
-   <span data-ttu-id="42114-109">Polygone</span><span class="sxs-lookup"><span data-stu-id="42114-109">Polygons</span></span>  
  
-   <span data-ttu-id="42114-110">Kardinale Splinekurven</span><span class="sxs-lookup"><span data-stu-id="42114-110">Cardinal splines</span></span>  
  
-   <span data-ttu-id="42114-111">Bézier-splines</span><span class="sxs-lookup"><span data-stu-id="42114-111">Bézier splines</span></span>  
  
 <span data-ttu-id="42114-112">In GDI + die <xref:System.Drawing.Drawing2D.GraphicsPath> Objekts können Sie eine Sequenz diese Bausteine in einem Arbeitsschritt zusammenfassen.</span><span class="sxs-lookup"><span data-stu-id="42114-112">In GDI+, the <xref:System.Drawing.Drawing2D.GraphicsPath> object allows you to collect a sequence of these building blocks into a single unit.</span></span> <span data-ttu-id="42114-113">Die gesamte Sequenz von Linien, Rechtecke, Polygone und Kurven kann dann mit einem einzigen Aufruf gezeichnet werden die <xref:System.Drawing.Graphics.DrawPath%2A> Methode der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="42114-113">The entire sequence of lines, rectangles, polygons, and curves can then be drawn with one call to the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="42114-114">Die folgende Abbildung zeigt einen Pfad erstellt, indem eine Linie, einen Bogen, eine Béziersplinekurve und eine cardinal-Splinekurve kombiniert.</span><span class="sxs-lookup"><span data-stu-id="42114-114">The following illustration shows a path created by combining a line, an arc, a Bézier spline, and a cardinal spline.</span></span>  
  
 <span data-ttu-id="42114-115">![Pfad](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span><span class="sxs-lookup"><span data-stu-id="42114-115">![Path](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span></span>  
  
## <a name="using-a-path"></a><span data-ttu-id="42114-116">Unter Verwendung eines Pfads</span><span class="sxs-lookup"><span data-stu-id="42114-116">Using a Path</span></span>  
 <span data-ttu-id="42114-117">Die <xref:System.Drawing.Drawing2D.GraphicsPath> Klasse bietet die folgenden Methoden zum Erstellen einer Sequenz von Elementen, die gezeichnet werden soll: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (bei kardinale Splines) und <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span><span class="sxs-lookup"><span data-stu-id="42114-117">The <xref:System.Drawing.Drawing2D.GraphicsPath> class provides the following methods for creating a sequence of items to be drawn: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (for cardinal splines), and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span></span> <span data-ttu-id="42114-118">Jede dieser Methoden ist überladen wird. Jede Methode unterstützt, also mehrere unterschiedliche Parameterlisten.</span><span class="sxs-lookup"><span data-stu-id="42114-118">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="42114-119">Z. B. eine Variation des der <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> Methode empfängt, vier ganzen Zahlen und eine Variante dieses die <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> -Methode lässt zwei <xref:System.Drawing.Point> Objekte.</span><span class="sxs-lookup"><span data-stu-id="42114-119">For example, one variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives four integers, and another variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="42114-120">Die Methoden zum Hinzufügen von Linien, Rechtecke und Bézier-Splines in einen Pfad haben im plural Begleitmethoden, die mehrere Elemente, auf den Pfad in einem einzigen Aufruf hinzuzufügen: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, und <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span><span class="sxs-lookup"><span data-stu-id="42114-120">The methods for adding lines, rectangles, and Bézier splines to a path have plural companion methods that add several items to the path in a single call: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span></span> <span data-ttu-id="42114-121">Darüber hinaus die <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> und <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> Methoden verfügen über Begleitmethoden <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> und <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, hinzufügen, die eine geschlossene Kurve oder ein Kreis auf den Pfad.</span><span class="sxs-lookup"><span data-stu-id="42114-121">Also, the <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> methods have companion methods, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, that add a closed curve or pie to the path.</span></span>  
  
 <span data-ttu-id="42114-122">Um einen Pfad zu zeichnen, müssen Sie eine <xref:System.Drawing.Graphics> -Objekt, eine <xref:System.Drawing.Pen> -Objekt, und ein <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt.</span><span class="sxs-lookup"><span data-stu-id="42114-122">To draw a path, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="42114-123">Die <xref:System.Drawing.Graphics> Objekt enthält die <xref:System.Drawing.Graphics.DrawPath%2A> -Methode, und die <xref:System.Drawing.Pen> Objekt speichert Attribute, z. B. Breite und Farbe der Linie verwendet, um den Pfad zu rendern.</span><span class="sxs-lookup"><span data-stu-id="42114-123">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPath%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the path.</span></span> <span data-ttu-id="42114-124">Die <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt speichert die Sequenz von Linien und Kurven, die den Pfad bilden.</span><span class="sxs-lookup"><span data-stu-id="42114-124">The <xref:System.Drawing.Drawing2D.GraphicsPath> object stores the sequence of lines and curves that make up the path.</span></span> <span data-ttu-id="42114-125">Die <xref:System.Drawing.Pen> Objekt und die <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt werden als Argumente übergeben der <xref:System.Drawing.Graphics.DrawPath%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="42114-125">The <xref:System.Drawing.Pen> object and the <xref:System.Drawing.Drawing2D.GraphicsPath> object are passed as arguments to the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="42114-126">Im folgende Beispiel zeichnet einen Pfad, der von einer Zeile und einer Ellipse, die eine Béziersplinekurve besteht aus:</span><span class="sxs-lookup"><span data-stu-id="42114-126">The following example draws a path that consists of a line, an ellipse, and a Bézier spline:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 <span data-ttu-id="42114-127">Die folgende Abbildung zeigt den Pfad an.</span><span class="sxs-lookup"><span data-stu-id="42114-127">The following illustration shows the path.</span></span>  
  
 <span data-ttu-id="42114-128">![Pfad](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span><span class="sxs-lookup"><span data-stu-id="42114-128">![Path](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span></span>  
  
 <span data-ttu-id="42114-129">Zusätzlich zum Hinzufügen von Linien, Rechtecke und Kurven auf einen Pfad ein, können Sie die Pfade zu einem Pfad hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="42114-129">In addition to adding lines, rectangles, and curves to a path, you can add paths to a path.</span></span> <span data-ttu-id="42114-130">Dadurch können Sie die existierenden Pfade zu großen, komplexen Pfade zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="42114-130">This allows you to combine existing paths to form large, complex paths.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 <span data-ttu-id="42114-131">Es gibt zwei anderen Elementen können Sie einen Pfad hinzufügen: Zeichenfolgen und Kreissegmente.</span><span class="sxs-lookup"><span data-stu-id="42114-131">There are two other items you can add to a path: strings and pies.</span></span> <span data-ttu-id="42114-132">Ein Kreis ist ein Teil das Innere einer Ellipse.</span><span class="sxs-lookup"><span data-stu-id="42114-132">A pie is a portion of the interior of an ellipse.</span></span> <span data-ttu-id="42114-133">Das folgende Beispiel erstellt einen Pfad in einen Bogen, eine cardinal-Splinekurve, eine Zeichenfolge und ein Kreis an:</span><span class="sxs-lookup"><span data-stu-id="42114-133">The following example creates a path from an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 <span data-ttu-id="42114-134">Die folgende Abbildung zeigt den Pfad an.</span><span class="sxs-lookup"><span data-stu-id="42114-134">The following illustration shows the path.</span></span> <span data-ttu-id="42114-135">Beachten Sie, dass ein Pfad keinen verbunden sein; der Bogen, cardinal-Splinekurve, Zeichenfolgen- und Kreis werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="42114-135">Note that a path does not have to be connected; the arc, cardinal spline, string, and pie are separated.</span></span>  
  
 <span data-ttu-id="42114-136">![Pfade](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span><span class="sxs-lookup"><span data-stu-id="42114-136">![Paths](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42114-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42114-137">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 <xref:System.Drawing.Point?displayProperty=nameWithType>  
 [<span data-ttu-id="42114-138">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="42114-138">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="42114-139">Gewusst wie: Erstellen von Grafikobjekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="42114-139">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="42114-140">Erstellen und Zeichnen von Pfaden</span><span class="sxs-lookup"><span data-stu-id="42114-140">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
