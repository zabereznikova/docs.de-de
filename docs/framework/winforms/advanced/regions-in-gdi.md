---
title: Bereiche in GDI+
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
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0525e7b58353909d41e5367aa52a17aa56bcd77c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="regions-in-gdi"></a><span data-ttu-id="bf999-102">Bereiche in GDI+</span><span class="sxs-lookup"><span data-stu-id="bf999-102">Regions in GDI+</span></span>
<span data-ttu-id="bf999-103">Ein Bereich ist ein Teil der Anzeigebereich des ein Ausgabegerät an.</span><span class="sxs-lookup"><span data-stu-id="bf999-103">A region is a portion of the display area of an output device.</span></span> <span data-ttu-id="bf999-104">Regionen können es sich um einfachen (ein einzelnes Rechteck) oder komplexe (eine Kombination aus Polygone und geschlossene Kurven) handeln.</span><span class="sxs-lookup"><span data-stu-id="bf999-104">Regions can be simple (a single rectangle) or complex (a combination of polygons and closed curves).</span></span> <span data-ttu-id="bf999-105">Die folgende Abbildung zeigt zwei Bereiche: einen erstellt aus einem Rechteck und die andere erstellt aus einem Pfad.</span><span class="sxs-lookup"><span data-stu-id="bf999-105">The following illustration shows two regions: one constructed from a rectangle, and the other constructed from a path.</span></span>  
  
 <span data-ttu-id="bf999-106">![Regionen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span><span class="sxs-lookup"><span data-stu-id="bf999-106">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span></span>  
  
## <a name="using-regions"></a><span data-ttu-id="bf999-107">Verwenden von Bereichen</span><span class="sxs-lookup"><span data-stu-id="bf999-107">Using Regions</span></span>  
 <span data-ttu-id="bf999-108">Bereiche werden häufig zum Ausschneiden und Treffertests.</span><span class="sxs-lookup"><span data-stu-id="bf999-108">Regions are often used for clipping and hit testing.</span></span> <span data-ttu-id="bf999-109">Clipping wird das Zeichnen auf einen bestimmten Bereich neben dem Anzeigebereich, in der Regel der Teil, der zu aktualisierenden beschränkt.</span><span class="sxs-lookup"><span data-stu-id="bf999-109">Clipping involves restricting drawing to a certain region of the display area, usually the portion that needs to be updated.</span></span> <span data-ttu-id="bf999-110">Treffertests beinhaltet die Überprüfung, um festzustellen, ob der Cursor befindet sich in einem bestimmten Bereich des Bildschirms, wenn eine Maustaste gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="bf999-110">Hit testing involves checking to determine whether the cursor is in a certain region of the screen when a mouse button is pressed.</span></span>  
  
 <span data-ttu-id="bf999-111">Sie können einen Bereich aus einem Rechteck oder einen Pfad erstellen.</span><span class="sxs-lookup"><span data-stu-id="bf999-111">You can construct a region from a rectangle or a path.</span></span> <span data-ttu-id="bf999-112">Sie können auch komplexe Regionen erstellen, durch die Kombination der vorhandener Regions.</span><span class="sxs-lookup"><span data-stu-id="bf999-112">You can also create complex regions by combining existing regions.</span></span> <span data-ttu-id="bf999-113">Die <xref:System.Drawing.Region> Klasse bietet die folgenden Methoden zum Kombinieren von Bereichen: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, und <xref:System.Drawing.Region.Complement%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf999-113">The <xref:System.Drawing.Region> class provides the following methods for combining regions: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, and <xref:System.Drawing.Region.Complement%2A>.</span></span>  
  
 <span data-ttu-id="bf999-114">Die Schnittmenge der beiden Regionen ist der Satz aller Punkte, die zu beiden Bereichen gehören.</span><span class="sxs-lookup"><span data-stu-id="bf999-114">The intersection of two regions is the set of all points belonging to both regions.</span></span> <span data-ttu-id="bf999-115">Die Union ist der Satz aller Punkte, die zu den anderen oder beide Regionen gehören.</span><span class="sxs-lookup"><span data-stu-id="bf999-115">The union is the set of all points belonging to one or the other or both regions.</span></span> <span data-ttu-id="bf999-116">Das Komplement eines Datenbereichs ist der Satz aller Punkte, die nicht in der Region sind.</span><span class="sxs-lookup"><span data-stu-id="bf999-116">The complement of a region is the set of all points that are not in the region.</span></span> <span data-ttu-id="bf999-117">Die folgende Abbildung zeigt die Schnittmenge und die Union der beiden Regionen in der vorherigen Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="bf999-117">The following illustration shows the intersection and union of the two regions shown in the preceding illustration.</span></span>  
  
 <span data-ttu-id="bf999-118">![Regionen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span><span class="sxs-lookup"><span data-stu-id="bf999-118">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span></span>  
  
 <span data-ttu-id="bf999-119">Die <xref:System.Drawing.Region.Xor%2A> -Methode angewendet wird, um ein Paar von Regionen, erzeugt einen Bereich, der alle Punkte enthält, die zu einer Region oder zur anderen jedoch nicht zu beiden gehören.</span><span class="sxs-lookup"><span data-stu-id="bf999-119">The <xref:System.Drawing.Region.Xor%2A> method, applied to a pair of regions, produces a region that contains all points that belong to one region or the other, but not both.</span></span> <span data-ttu-id="bf999-120">Die <xref:System.Drawing.Region.Exclude%2A> -Methode angewendet wird, um ein Paar von Regionen, erzeugt eine Region, die alle Punkte in der ersten Region enthält, die nicht im zweiten Bereich enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="bf999-120">The <xref:System.Drawing.Region.Exclude%2A> method, applied to a pair of regions, produces a region that contains all points in the first region that are not in the second region.</span></span> <span data-ttu-id="bf999-121">Die folgende Abbildung zeigt die Bereiche, die aus dem Anwenden der <xref:System.Drawing.Region.Xor%2A> und <xref:System.Drawing.Region.Exclude%2A> Methoden, um die beiden Bereiche am Anfang dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="bf999-121">The following illustration shows the regions that result from applying the <xref:System.Drawing.Region.Xor%2A> and <xref:System.Drawing.Region.Exclude%2A> methods to the two regions shown at the beginning of this topic.</span></span>  
  
 <span data-ttu-id="bf999-122">![Regionen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span><span class="sxs-lookup"><span data-stu-id="bf999-122">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span></span>  
  
 <span data-ttu-id="bf999-123">Um einen Bereich zu füllen, müssen Sie eine <xref:System.Drawing.Graphics> -Objekt, eine <xref:System.Drawing.Brush> -Objekt, und ein <xref:System.Drawing.Region> Objekt.</span><span class="sxs-lookup"><span data-stu-id="bf999-123">To fill a region, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Brush> object, and a <xref:System.Drawing.Region> object.</span></span> <span data-ttu-id="bf999-124">Die <xref:System.Drawing.Graphics> Objekt enthält die <xref:System.Drawing.Graphics.FillRegion%2A> -Methode, und die <xref:System.Drawing.Brush> Objekt speichert Attribute für die Füllung, z. B. Farbe oder ein Muster.</span><span class="sxs-lookup"><span data-stu-id="bf999-124">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.FillRegion%2A> method, and the <xref:System.Drawing.Brush> object stores attributes of the fill, such as color or pattern.</span></span> <span data-ttu-id="bf999-125">Das folgende Beispiel füllt einen Bereich mit einer Volltonfarbe aus.</span><span class="sxs-lookup"><span data-stu-id="bf999-125">The following example fills a region with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="bf999-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf999-126">See Also</span></span>  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [<span data-ttu-id="bf999-127">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="bf999-127">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="bf999-128">Verwenden von Bereichen</span><span class="sxs-lookup"><span data-stu-id="bf999-128">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)
