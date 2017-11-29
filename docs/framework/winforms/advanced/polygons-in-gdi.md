---
title: Polygone in GDI+
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
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 740a454873976e407843c417a7b09e5a5218398d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="polygons-in-gdi"></a><span data-ttu-id="b6e32-102">Polygone in GDI+</span><span class="sxs-lookup"><span data-stu-id="b6e32-102">Polygons in GDI+</span></span>
<span data-ttu-id="b6e32-103">Ein Polygon ist eine geschlossene Form mit drei oder mehr geraden Seiten.</span><span class="sxs-lookup"><span data-stu-id="b6e32-103">A polygon is a closed shape with three or more straight sides.</span></span> <span data-ttu-id="b6e32-104">Z. B. einem Dreieck ist ein Polygon mit drei Seiten ein Rechteck ist ein Polygon mit vier Seiten und ein Fünfeck ist ein Polygon mit fünf Seiten.</span><span class="sxs-lookup"><span data-stu-id="b6e32-104">For example, a triangle is a polygon with three sides, a rectangle is a polygon with four sides, and a pentagon is a polygon with five sides.</span></span> <span data-ttu-id="b6e32-105">Die folgende Abbildung zeigt verschiedene Polygone.</span><span class="sxs-lookup"><span data-stu-id="b6e32-105">The following illustration shows several polygons.</span></span>  
  
 <span data-ttu-id="b6e32-106">![Polygone](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span><span class="sxs-lookup"><span data-stu-id="b6e32-106">![Polygons](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span></span>  
  
## <a name="drawing-a-polygon"></a><span data-ttu-id="b6e32-107">Zeichnen eines Polygons</span><span class="sxs-lookup"><span data-stu-id="b6e32-107">Drawing a Polygon</span></span>  
 <span data-ttu-id="b6e32-108">Um ein Polygon zu zeichnen, müssen Sie eine <xref:System.Drawing.Graphics> -Objekt, eine <xref:System.Drawing.Pen> Objekt und ein Array von <xref:System.Drawing.Point> (oder <xref:System.Drawing.PointF>) Objekte.</span><span class="sxs-lookup"><span data-stu-id="b6e32-108">To draw a polygon, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and an array of <xref:System.Drawing.Point> (or <xref:System.Drawing.PointF>) objects.</span></span> <span data-ttu-id="b6e32-109">Die <xref:System.Drawing.Graphics> Objekt enthält die <xref:System.Drawing.Graphics.DrawPolygon%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="b6e32-109">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="b6e32-110">Die <xref:System.Drawing.Pen> Objekt speichert Attribute, z. B. Breite und Farbe der Linie verwendet, um das Polygon, und das Array von Rendern <xref:System.Drawing.Point> -Objekte speichert die Punkte durch gerade Linien verbunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="b6e32-110">The <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the polygon, and the array of <xref:System.Drawing.Point> objects stores the points to be connected by straight lines.</span></span> <span data-ttu-id="b6e32-111">Die <xref:System.Drawing.Pen> Objekt und das Array von <xref:System.Drawing.Point> Objekte werden als Argumente übergeben der <xref:System.Drawing.Graphics.DrawPolygon%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="b6e32-111">The <xref:System.Drawing.Pen> object and the array of <xref:System.Drawing.Point> objects are passed as arguments to the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="b6e32-112">Im folgende Beispiel zeichnet ein Vieleck, drei Seiten.</span><span class="sxs-lookup"><span data-stu-id="b6e32-112">The following example draws a three-sided polygon.</span></span> <span data-ttu-id="b6e32-113">Beachten Sie, dass nur drei Punkten in `myPointArray`: (0, 0), (50, 30) und (30, 60).</span><span class="sxs-lookup"><span data-stu-id="b6e32-113">Note that there are only three points in `myPointArray`: (0, 0), (50, 30), and (30, 60).</span></span> <span data-ttu-id="b6e32-114">Die <xref:System.Drawing.Graphics.DrawPolygon%2A> Methode schließt automatisch das Polygon durch eine Linie von (30, 60) zurück zum Anfangspunkt (0, 0).</span><span class="sxs-lookup"><span data-stu-id="b6e32-114">The <xref:System.Drawing.Graphics.DrawPolygon%2A> method automatically closes the polygon by drawing a line from (30, 60) back to the starting point (0, 0).</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 <span data-ttu-id="b6e32-115">Die folgende Abbildung zeigt das Polygon.</span><span class="sxs-lookup"><span data-stu-id="b6e32-115">The following illustration shows the polygon.</span></span>  
  
 <span data-ttu-id="b6e32-116">![Polygon](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span><span class="sxs-lookup"><span data-stu-id="b6e32-116">![Polygon](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6e32-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6e32-117">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="b6e32-118">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="b6e32-118">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="b6e32-119">Gewusst wie: Erstellen eines Stifts</span><span class="sxs-lookup"><span data-stu-id="b6e32-119">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
