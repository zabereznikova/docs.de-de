---
title: Polygone in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
ms.openlocfilehash: 2b1e3d387e4d056d9187c54dcef560544206c370
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132625"
---
# <a name="polygons-in-gdi"></a><span data-ttu-id="5ecdf-102">Polygone in GDI+</span><span class="sxs-lookup"><span data-stu-id="5ecdf-102">Polygons in GDI+</span></span>
<span data-ttu-id="5ecdf-103">Ein Polygon ist eine geschlossene Form mit drei oder mehr gerade Seiten.</span><span class="sxs-lookup"><span data-stu-id="5ecdf-103">A polygon is a closed shape with three or more straight sides.</span></span> <span data-ttu-id="5ecdf-104">Z. B. ein Dreieck ist ein Polygon mit drei Seiten, ein Rechteck ist ein Polygon mit vier Seiten und ein Fünfeck ist ein Polygon mit fünf Seiten.</span><span class="sxs-lookup"><span data-stu-id="5ecdf-104">For example, a triangle is a polygon with three sides, a rectangle is a polygon with four sides, and a pentagon is a polygon with five sides.</span></span> <span data-ttu-id="5ecdf-105">Die folgende Abbildung zeigt verschiedene Polygone.</span><span class="sxs-lookup"><span data-stu-id="5ecdf-105">The following illustration shows several polygons.</span></span>  
  
 <span data-ttu-id="5ecdf-106">![Polygons](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span><span class="sxs-lookup"><span data-stu-id="5ecdf-106">![Polygons](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span></span>  
  
## <a name="drawing-a-polygon"></a><span data-ttu-id="5ecdf-107">Zeichnen eines Polygons</span><span class="sxs-lookup"><span data-stu-id="5ecdf-107">Drawing a Polygon</span></span>  
 <span data-ttu-id="5ecdf-108">Um ein Polygon zu zeichnen, müssen Sie eine <xref:System.Drawing.Graphics> Objekt eine <xref:System.Drawing.Pen> Objekt und ein Array von <xref:System.Drawing.Point> (oder <xref:System.Drawing.PointF>) Objekte.</span><span class="sxs-lookup"><span data-stu-id="5ecdf-108">To draw a polygon, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and an array of <xref:System.Drawing.Point> (or <xref:System.Drawing.PointF>) objects.</span></span> <span data-ttu-id="5ecdf-109">Die <xref:System.Drawing.Graphics> -Objekt ermöglicht die <xref:System.Drawing.Graphics.DrawPolygon%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="5ecdf-109">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="5ecdf-110">Die <xref:System.Drawing.Pen> -Objekt speichert Attribute, z. B. Breite und Farbe der Linie verwendet, um das Polygon, und das Array von Rendern <xref:System.Drawing.Point> -Objekte speichert, die Punkte durch gerade Linien miteinander verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="5ecdf-110">The <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the polygon, and the array of <xref:System.Drawing.Point> objects stores the points to be connected by straight lines.</span></span> <span data-ttu-id="5ecdf-111">Die <xref:System.Drawing.Pen> Objekt und das Array von <xref:System.Drawing.Point> Objekte werden als Argumente übergeben die <xref:System.Drawing.Graphics.DrawPolygon%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="5ecdf-111">The <xref:System.Drawing.Pen> object and the array of <xref:System.Drawing.Point> objects are passed as arguments to the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="5ecdf-112">Im folgende Beispiel zeichnet ein Vieleck, drei Seiten.</span><span class="sxs-lookup"><span data-stu-id="5ecdf-112">The following example draws a three-sided polygon.</span></span> <span data-ttu-id="5ecdf-113">Beachten Sie, dass es nur drei Punkte im `myPointArray`: (0, 0), (50, 30), und (30, 60).</span><span class="sxs-lookup"><span data-stu-id="5ecdf-113">Note that there are only three points in `myPointArray`: (0, 0), (50, 30), and (30, 60).</span></span> <span data-ttu-id="5ecdf-114">Die <xref:System.Drawing.Graphics.DrawPolygon%2A> Methode schließt automatisch das Polygon durch Zeichnen einer Linie aus (30, 60) wieder zum Ausgangspunkt (0, 0).</span><span class="sxs-lookup"><span data-stu-id="5ecdf-114">The <xref:System.Drawing.Graphics.DrawPolygon%2A> method automatically closes the polygon by drawing a line from (30, 60) back to the starting point (0, 0).</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#111](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 <span data-ttu-id="5ecdf-115">Die folgende Abbildung zeigt das Polygon.</span><span class="sxs-lookup"><span data-stu-id="5ecdf-115">The following illustration shows the polygon.</span></span>  
  
 <span data-ttu-id="5ecdf-116">![Polygon](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span><span class="sxs-lookup"><span data-stu-id="5ecdf-116">![Polygon](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ecdf-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ecdf-117">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="5ecdf-118">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="5ecdf-118">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="5ecdf-119">Vorgehensweise: Erstellen eines Stifts</span><span class="sxs-lookup"><span data-stu-id="5ecdf-119">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
