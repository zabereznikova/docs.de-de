---
title: "Übersicht über Vektorgrafiken"
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
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 603b76c999933f177a9e48ddb819562b8e4dd8f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="vector-graphics-overview"></a><span data-ttu-id="bcfc9-102">Übersicht über Vektorgrafiken</span><span class="sxs-lookup"><span data-stu-id="bcfc9-102">Vector Graphics Overview</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="bcfc9-103">Zeichnet Linien, Rechtecke und andere Formen auf einem Koordinatensystem.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-103"> draws lines, rectangles, and other shapes on a coordinate system.</span></span> <span data-ttu-id="bcfc9-104">Sie können aus einer Vielzahl von Koordinatensysteme auswählen, aber das Standard-Koordinatensystem verfügt über den Ursprung in der oberen linken Ecke mit der x-Achse nach rechts und die y-Achse nach unten zeigendes verweist.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-104">You can choose from a variety of coordinate systems, but the default coordinate system has the origin in the upper-left corner with the x-axis pointing to the right and the y-axis pointing down.</span></span> <span data-ttu-id="bcfc9-105">Die Maßeinheit in der Standard-Koordinatensystem wird das Pixel.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-105">The unit of measure in the default coordinate system is the pixel.</span></span>  
  
## <a name="the-building-blocks-of-gdi"></a><span data-ttu-id="bcfc9-106">Die Bausteine von GDI +</span><span class="sxs-lookup"><span data-stu-id="bcfc9-106">The Building Blocks of GDI+</span></span>  
 <span data-ttu-id="bcfc9-107">![Vektorgrafik](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.gif "AboutGdip02_Art01")</span><span class="sxs-lookup"><span data-stu-id="bcfc9-107">![Vector graphic](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.gif "AboutGdip02_Art01")</span></span>  
  
 <span data-ttu-id="bcfc9-108">Computermonitor erstellt seine Anzeige auf ein rechteckiges Array von Punkten Bildelemente oder Pixel bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-108">A computer monitor creates its display on a rectangular array of dots called picture elements or pixels.</span></span> <span data-ttu-id="bcfc9-109">Die Anzahl der Pixel, die auf dem Bildschirm angezeigt werden, die von einem Monitor zum nächsten variiert, und die Anzahl der Pixel, die auf einem einzelnen Monitor angezeigt werden kann in der Regel zu einem gewissen Grad vom Benutzer konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-109">The number of pixels that appear on the screen varies from one monitor to the next, and the number of pixels that appear on an individual monitor can usually be configured to some extent by the user.</span></span>  
  
 <span data-ttu-id="bcfc9-110">![Vektorgrafik](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.gif "AboutGdip02_Art02")</span><span class="sxs-lookup"><span data-stu-id="bcfc9-110">![Vector graphic](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.gif "AboutGdip02_Art02")</span></span>  
  
 <span data-ttu-id="bcfc9-111">Bei Verwendung von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] um eine Linie, Rechteck oder in Kurve zu zeichnen, geben Sie bestimmte wichtige Informationen über das Element, gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-111">When you use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to draw a line, rectangle, or curve, you provide certain key information about the item to be drawn.</span></span> <span data-ttu-id="bcfc9-112">Beispielsweise können Sie eine Linie durch die Bereitstellung von zwei Punkten angeben, und können Sie durch die Bereitstellung von einem Punkt, eine Höhen- und eine Breite ein Rechtecks angeben.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-112">For example, you can specify a line by providing two points, and you can specify a rectangle by providing a point, a height, and a width.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="bcfc9-113">funktioniert in Verbindung mit dem Bildschirmtreiber um zu bestimmen, welche Pixel eingeschaltet bleiben müssen auf die Linie, Rechteck oder in Kurve anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-113"> works in conjunction with the display driver software to determine which pixels must be turned on to show the line, rectangle, or curve.</span></span> <span data-ttu-id="bcfc9-114">Die folgende Abbildung zeigt die Pixel, die eingeschaltet sind, um eine Linie an dem Punkt (4, 2) auf den Punkt ("12", "8") anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-114">The following illustration shows the pixels that are turned on to display a line from the point (4, 2) to the point (12, 8).</span></span>  
  
 <span data-ttu-id="bcfc9-115">![Vektorgrafik](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.gif "AboutGdip02_Art03")</span><span class="sxs-lookup"><span data-stu-id="bcfc9-115">![Vector graphic](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.gif "AboutGdip02_Art03")</span></span>  
  
 <span data-ttu-id="bcfc9-116">Im Laufe der Zeit haben bestimmte grundlegenden Bausteine erwiesen besonders hilfreich für zweidimensionale Grafiken erstellen.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-116">Over time, certain basic building blocks have proven to be the most useful for creating two-dimensional pictures.</span></span> <span data-ttu-id="bcfc9-117">Diese Bausteine, die alle von unterstützt werden [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], sind in der folgenden Liste angegeben:</span><span class="sxs-lookup"><span data-stu-id="bcfc9-117">These building blocks, which are all supported by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], are given in the following list:</span></span>  
  
-   <span data-ttu-id="bcfc9-118">Linien</span><span class="sxs-lookup"><span data-stu-id="bcfc9-118">Lines</span></span>  
  
-   <span data-ttu-id="bcfc9-119">Rechtecke</span><span class="sxs-lookup"><span data-stu-id="bcfc9-119">Rectangles</span></span>  
  
-   <span data-ttu-id="bcfc9-120">Ellipsen</span><span class="sxs-lookup"><span data-stu-id="bcfc9-120">Ellipses</span></span>  
  
-   <span data-ttu-id="bcfc9-121">Bögen</span><span class="sxs-lookup"><span data-stu-id="bcfc9-121">Arcs</span></span>  
  
-   <span data-ttu-id="bcfc9-122">Polygone</span><span class="sxs-lookup"><span data-stu-id="bcfc9-122">Polygons</span></span>  
  
-   <span data-ttu-id="bcfc9-123">Kardinale Splinekurven</span><span class="sxs-lookup"><span data-stu-id="bcfc9-123">Cardinal splines</span></span>  
  
-   <span data-ttu-id="bcfc9-124">Béziersplinekurven</span><span class="sxs-lookup"><span data-stu-id="bcfc9-124">Bezier splines</span></span>  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a><span data-ttu-id="bcfc9-125">Methoden zum Zeichnen mit einem Graphics-Objekts</span><span class="sxs-lookup"><span data-stu-id="bcfc9-125">Methods For Drawing with a Graphics Object</span></span>  
 <span data-ttu-id="bcfc9-126">Die <xref:System.Drawing.Graphics> -Klasse im [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet die folgenden Methoden zum Zeichnen der Elemente in der vorherigen Liste: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (bei kardinale Splines) und <xref:System.Drawing.Graphics.DrawBezier%2A>.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-126">The <xref:System.Drawing.Graphics> class in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] provides the following methods for drawing the items in the previous list: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (for cardinal splines), and <xref:System.Drawing.Graphics.DrawBezier%2A>.</span></span> <span data-ttu-id="bcfc9-127">Jede dieser Methoden ist überladen wird. Jede Methode unterstützt, also mehrere unterschiedliche Parameterlisten.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-127">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="bcfc9-128">Z. B. eine Variation des der <xref:System.Drawing.Graphics.DrawLine%2A> Methode empfängt einen <xref:System.Drawing.Pen> Objekt und vier ganzen Zahlen, während eine andere Variante der der <xref:System.Drawing.Graphics.DrawLine%2A> Methode empfängt eine <xref:System.Drawing.Pen> Objekt und zwei <xref:System.Drawing.Point> Objekte.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-128">For example, one variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and four integers, while another variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="bcfc9-129">Die Methoden zum Zeichnen von Linien, Rechtecke und Bézier-Splines verfügen im plural Begleitmethoden, die mehrere Elemente in einem einzigen Aufruf abgerufen: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, und <xref:System.Drawing.Graphics.DrawBeziers%2A>.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-129">The methods for drawing lines, rectangles, and Bézier splines have plural companion methods that draw several items in a single call: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, and <xref:System.Drawing.Graphics.DrawBeziers%2A>.</span></span> <span data-ttu-id="bcfc9-130">Darüber hinaus die <xref:System.Drawing.Graphics.DrawCurve%2A> Methode verfügt über eine Methode Companion <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, zeigen Sie geschlossen wird, wird eine Kurve durch Herstellen einer Verbindung den Endpunkt der Kurve ab.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-130">Also, the <xref:System.Drawing.Graphics.DrawCurve%2A> method has a companion method, <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, that closes a curve by connecting the ending point of the curve to the starting point.</span></span>  
  
 <span data-ttu-id="bcfc9-131">Alle Methoden von zeichnen die <xref:System.Drawing.Graphics> -Klasse funktionieren in Verbindung mit einer <xref:System.Drawing.Pen> Objekt.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-131">All of the drawing methods of the <xref:System.Drawing.Graphics> class work in conjunction with a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="bcfc9-132">Zum Zeichnen, müssen Sie mindestens zwei Objekte erstellen: eine <xref:System.Drawing.Graphics> Objekt und ein <xref:System.Drawing.Pen> Objekt.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-132">To draw anything, you must create at least two objects: a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="bcfc9-133">Die <xref:System.Drawing.Pen> Objekt speichert Attribute, z. B. Breite und Farbe des Elements, gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-133">The <xref:System.Drawing.Pen> object stores attributes, such as line width and color, of the item to be drawn.</span></span> <span data-ttu-id="bcfc9-134">Die <xref:System.Drawing.Pen> Objekt als eines der Argumente an die Zeichnen-Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="bcfc9-134">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the drawing method.</span></span> <span data-ttu-id="bcfc9-135">Z. B. eine Variation des der <xref:System.Drawing.Graphics.DrawLine%2A> Methode empfängt einen <xref:System.Drawing.Pen> Objekt und vier ganzen Zahlen wie im folgenden Beispiel gezeigt wird, die mit einer Breite von 100, eine Höhe von 50 und einen oberen linken Ecke des Rechtecks zeichnet (20, 10):</span><span class="sxs-lookup"><span data-stu-id="bcfc9-135">For example, one variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and four integers as shown in the following example, which draws a rectangle with a width of 100, a height of 50 and an upper-left corner of (20, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="bcfc9-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bcfc9-136">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="bcfc9-137">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="bcfc9-137">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="bcfc9-138">Gewusst wie: Erstellen von Grafikobjekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="bcfc9-138">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
