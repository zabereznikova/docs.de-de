---
title: Typen von Koordinatensystemen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], page
- unit of measure
- world coordinate system
- page coordinate system
- page transformation
- device coordinate system
- world transformation
- coordinate systems
- transformations [Windows Forms], world
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
ms.openlocfilehash: bbb0d4908d4a281499336d262c653d7b72f3ccdc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159805"
---
# <a name="types-of-coordinate-systems"></a><span data-ttu-id="1a8eb-102">Typen von Koordinatensystemen</span><span class="sxs-lookup"><span data-stu-id="1a8eb-102">Types of Coordinate Systems</span></span>
<span data-ttu-id="1a8eb-103">GDI+ verwendet drei Koordinaten Bereiche: "World", "page" und "Device".</span><span class="sxs-lookup"><span data-stu-id="1a8eb-103">GDI+ uses three coordinate spaces: world, page, and device.</span></span> <span data-ttu-id="1a8eb-104">Globale Koordinaten sind die Koordinaten, die verwendet werden, um eine bestimmte Grafik Welt zu modellieren, und sind die Koordinaten, die Sie an Methoden in der .NET Framework übergeben.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-104">World coordinates are the coordinates used to model a particular graphic world and are the coordinates you pass to methods in the .NET Framework.</span></span> <span data-ttu-id="1a8eb-105">Seiten Koordinaten verweisen auf das Koordinatensystem, das von einer Zeichen Oberfläche verwendet wird, z. b. ein Formular oder ein Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-105">Page coordinates refer to the coordinate system used by a drawing surface, such as a form or control.</span></span> <span data-ttu-id="1a8eb-106">Geräte Koordinaten sind die Koordinaten, die von dem physischen Gerät verwendet werden, auf dem Sie gezeichnet werden, z. b. ein Bildschirm oder ein Papierblatt.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-106">Device coordinates are the coordinates used by the physical device being drawn on, such as a screen or sheet of paper.</span></span> <span data-ttu-id="1a8eb-107">Wenn Sie den-Aufruf`myGraphics.DrawLine(myPen, 0, 0, 160, 80)`durchführen, werden die Punkte, die Sie an die <xref:System.Drawing.Graphics.DrawLine%2A>-`(0, 0)` Methode – und `(160, 80)`übergeben, im weltweiten Koordinaten Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-107">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, the points that you pass to the <xref:System.Drawing.Graphics.DrawLine%2A> method—`(0, 0)` and `(160, 80)`—are in the world coordinate space.</span></span> <span data-ttu-id="1a8eb-108">Bevor GDI+ die Linie auf dem Bildschirm zeichnen kann, durchlaufen die Koordinaten eine Sequenz von Transformationen.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-108">Before GDI+ can draw the line on the screen, the coordinates pass through a sequence of transformations.</span></span> <span data-ttu-id="1a8eb-109">Eine Transformation, die als globale Transformation bezeichnet wird, konvertiert globale Koordinaten in Seiten Koordinaten, und eine andere Transformation, die als Seiten Transformation bezeichnet wird, konvertiert Seiten Koordinaten in Geräte Koordinaten.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-109">One transformation, called the world transformation, converts world coordinates to page coordinates, and another transformation, called the page transformation, converts page coordinates to device coordinates.</span></span>  
  
## <a name="transforms-and-coordinate-systems"></a><span data-ttu-id="1a8eb-110">Transformationen und Koordinatensysteme</span><span class="sxs-lookup"><span data-stu-id="1a8eb-110">Transforms and Coordinate Systems</span></span>  
 <span data-ttu-id="1a8eb-111">Angenommen, Sie möchten mit einem Koordinatensystem arbeiten, dessen Ursprung im Text des Client Bereichs liegt, und nicht in der oberen linken Ecke.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-111">Suppose you want to work with a coordinate system that has its origin in the body of the client area rather than the upper-left corner.</span></span> <span data-ttu-id="1a8eb-112">Angenommen, Sie möchten, dass der Ursprung 100 Pixel vom linken Rand des Client Bereichs und 50 Pixel vom oberen Rand des Client Bereichs sein soll.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-112">Say, for example, that you want the origin to be 100 pixels from the left edge of the client area and 50 pixels from the top of the client area.</span></span> <span data-ttu-id="1a8eb-113">Die folgende Abbildung zeigt ein solches Koordinatensystem.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-113">The following illustration shows such a coordinate system.</span></span>  
  
 <span data-ttu-id="1a8eb-114">![Koordinaten System](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span><span class="sxs-lookup"><span data-stu-id="1a8eb-114">![Coordinate System](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span></span>  
  
 <span data-ttu-id="1a8eb-115">Wenn Sie den-`myGraphics.DrawLine(myPen, 0, 0, 160, 80)`abrufen, erhalten Sie die in der folgenden Abbildung gezeigte Zeile.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-115">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, you get the line shown in the following illustration.</span></span>  
  
 <span data-ttu-id="1a8eb-116">![Koordinaten System](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span><span class="sxs-lookup"><span data-stu-id="1a8eb-116">![Coordinate System](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span></span>  
  
 <span data-ttu-id="1a8eb-117">Die Koordinaten der Endpunkte der Zeile in den drei Koordinaten Räumen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1a8eb-117">The coordinates of the endpoints of your line in the three coordinate spaces are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1a8eb-118">Welt</span><span class="sxs-lookup"><span data-stu-id="1a8eb-118">World</span></span>|<span data-ttu-id="1a8eb-119">(0,0) bis (160, 80)</span><span class="sxs-lookup"><span data-stu-id="1a8eb-119">(0, 0) to (160, 80)</span></span>|  
|<span data-ttu-id="1a8eb-120">Seite</span><span class="sxs-lookup"><span data-stu-id="1a8eb-120">Page</span></span>|<span data-ttu-id="1a8eb-121">(100, 50) bis (260, 130)</span><span class="sxs-lookup"><span data-stu-id="1a8eb-121">(100, 50) to (260, 130)</span></span>|  
|<span data-ttu-id="1a8eb-122">Gerät</span><span class="sxs-lookup"><span data-stu-id="1a8eb-122">Device</span></span>|<span data-ttu-id="1a8eb-123">(100, 50) bis (260, 130)</span><span class="sxs-lookup"><span data-stu-id="1a8eb-123">(100, 50) to (260, 130)</span></span>|  
  
 <span data-ttu-id="1a8eb-124">Beachten Sie, dass der Seiten Koordinaten Bereich seinen Ursprung in der oberen linken Ecke des Client Bereichs hat. Dies ist immer der Fall.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-124">Note that the page coordinate space has its origin at the upper-left corner of the client area; this will always be the case.</span></span> <span data-ttu-id="1a8eb-125">Beachten Sie außerdem, dass die Geräte Koordinaten den Seiten Koordinaten entsprechen, da die Maßeinheit das Pixel ist.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-125">Also note that because the unit of measure is the pixel, the device coordinates are the same as the page coordinates.</span></span> <span data-ttu-id="1a8eb-126">Wenn Sie die Maßeinheit auf einen anderen Wert als Pixel festlegen (z. b. Zoll), unterscheiden sich die Geräte Koordinaten von den Seiten Koordinaten.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-126">If you set the unit of measure to something other than pixels (for example, inches), then the device coordinates will be different from the page coordinates.</span></span>  
  
 <span data-ttu-id="1a8eb-127">Die globale Transformation, die globale Koordinaten zu Seiten Koordinaten zuordnet, wird in der <xref:System.Drawing.Graphics.Transform%2A>-Eigenschaft der <xref:System.Drawing.Graphics>-Klasse gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-127">The world transformation, which maps world coordinates to page coordinates, is held in the <xref:System.Drawing.Graphics.Transform%2A> property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="1a8eb-128">Im vorherigen Beispiel handelt es sich bei der Welt Transformation um eine Translation 100-Einheiten in der x-Richtung und 50-Einheiten in der y-Richtung.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-128">In the preceding example, the world transformation is a translation 100 units in the x direction and 50 units in the y direction.</span></span> <span data-ttu-id="1a8eb-129">Im folgenden Beispiel wird die globale Transformation eines <xref:System.Drawing.Graphics> Objekts festgelegt, und anschließend wird dieses <xref:System.Drawing.Graphics> Objekt verwendet, um die in der vorherigen Abbildung gezeigte Zeile zu zeichnen:</span><span class="sxs-lookup"><span data-stu-id="1a8eb-129">The following example sets the world transformation of a <xref:System.Drawing.Graphics> object and then uses that <xref:System.Drawing.Graphics> object to draw the line shown in the preceding figure:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 <span data-ttu-id="1a8eb-130">Die Seite Transformation ordnet den Geräte Koordinaten Seiten Koordinaten zu.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-130">The page transformation maps page coordinates to device coordinates.</span></span> <span data-ttu-id="1a8eb-131">Die <xref:System.Drawing.Graphics>-Klasse stellt die Eigenschaften <xref:System.Drawing.Graphics.PageUnit%2A> und <xref:System.Drawing.Graphics.PageScale%2A> zum Bearbeiten der Seiten Transformation bereit.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-131">The <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.PageUnit%2A> and <xref:System.Drawing.Graphics.PageScale%2A> properties for manipulating the page transformation.</span></span> <span data-ttu-id="1a8eb-132">Die <xref:System.Drawing.Graphics>-Klasse bietet auch zwei schreibgeschützte Eigenschaften, <xref:System.Drawing.Graphics.DpiX%2A> und <xref:System.Drawing.Graphics.DpiY%2A>, um die horizontalen und vertikalen Punkte pro Zoll des Anzeige Geräts zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-132">The <xref:System.Drawing.Graphics> class also provides two read-only properties, <xref:System.Drawing.Graphics.DpiX%2A> and <xref:System.Drawing.Graphics.DpiY%2A>, for examining the horizontal and vertical dots per inch of the display device.</span></span>  
  
 <span data-ttu-id="1a8eb-133">Sie können die <xref:System.Drawing.Graphics.PageUnit%2A>-Eigenschaft der <xref:System.Drawing.Graphics>-Klasse verwenden, um eine andere Maßeinheit als das Pixel anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-133">You can use the <xref:System.Drawing.Graphics.PageUnit%2A> property of the <xref:System.Drawing.Graphics> class to specify a unit of measure other than the pixel.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1a8eb-134">Die <xref:System.Drawing.Graphics.PageUnit%2A>-Eigenschaft kann nicht auf <xref:System.Drawing.GraphicsUnit.World>festgelegt werden, da es sich nicht um eine physische Einheit handelt, und es wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-134">You cannot set the <xref:System.Drawing.Graphics.PageUnit%2A> property to <xref:System.Drawing.GraphicsUnit.World>, as this is not a physical unit and will cause an exception.</span></span>  
  
 <span data-ttu-id="1a8eb-135">Im folgenden Beispiel wird eine Zeile von (0,0) zu (2, 1) gezeichnet, wobei der Punkt (2, 1) 2 Zoll nach rechts und 1 Zoll vom Punkt (0,0) ist:</span><span class="sxs-lookup"><span data-stu-id="1a8eb-135">The following example draws a line from (0, 0) to (2, 1), where the point (2, 1) is 2 inches to the right and 1 inch down from the point (0, 0):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
> <span data-ttu-id="1a8eb-136">Wenn Sie beim Erstellen des Stifts keine Stift Breite angeben, wird im vorhergehenden Beispiel eine Linie mit einer Breite von einem Zoll gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-136">If you don't specify a pen width when you construct your pen, the preceding example will draw a line that is one inch wide.</span></span> <span data-ttu-id="1a8eb-137">Sie können die Stift Breite im zweiten Argument für den <xref:System.Drawing.Pen>-Konstruktor angeben:</span><span class="sxs-lookup"><span data-stu-id="1a8eb-137">You can specify the pen width in the second argument to the <xref:System.Drawing.Pen> constructor:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 <span data-ttu-id="1a8eb-138">Wenn wir davon ausgehen, dass das Anzeigegerät 96 Punkte pro Zoll in horizontaler Richtung und 96 Punkte pro Zoll in vertikaler Richtung aufweist, haben die Endpunkte der Linie im vorherigen Beispiel die folgenden Koordinaten in den drei Koordinaten Räumen:</span><span class="sxs-lookup"><span data-stu-id="1a8eb-138">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1a8eb-139">Welt</span><span class="sxs-lookup"><span data-stu-id="1a8eb-139">World</span></span>|<span data-ttu-id="1a8eb-140">(0,0) bis (2, 1)</span><span class="sxs-lookup"><span data-stu-id="1a8eb-140">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="1a8eb-141">Seite</span><span class="sxs-lookup"><span data-stu-id="1a8eb-141">Page</span></span>|<span data-ttu-id="1a8eb-142">(0,0) bis (2, 1)</span><span class="sxs-lookup"><span data-stu-id="1a8eb-142">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="1a8eb-143">Gerät</span><span class="sxs-lookup"><span data-stu-id="1a8eb-143">Device</span></span>|<span data-ttu-id="1a8eb-144">(0,0) bis (192, 96)</span><span class="sxs-lookup"><span data-stu-id="1a8eb-144">(0, 0) to (192, 96)</span></span>|  
  
 <span data-ttu-id="1a8eb-145">Beachten Sie Folgendes: da sich der Ursprung des World-Koordinaten Bereichs in der oberen linken Ecke des Client Bereichs befindet, sind die Seiten Koordinaten identisch mit den World-Koordinaten.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-145">Note that because the origin of the world coordinate space is at the upper-left corner of the client area, the page coordinates are the same as the world coordinates.</span></span>  
  
 <span data-ttu-id="1a8eb-146">Sie können die Transformationen für Welt und Seite kombinieren, um eine Vielzahl von Effekten zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-146">You can combine the world and page transformations to achieve a variety of effects.</span></span> <span data-ttu-id="1a8eb-147">Angenommen, Sie möchten Zoll als Maßeinheit verwenden, und Sie möchten, dass der Ursprung ihres Koordinatensystems 2 Zoll vom linken Rand des Client Bereichs und 1/2 Zoll vom oberen Rand des Client Bereichs ist.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-147">For example, suppose you want to use inches as the unit of measure and you want the origin of your coordinate system to be 2 inches from the left edge of the client area and 1/2 inch from the top of the client area.</span></span> <span data-ttu-id="1a8eb-148">Im folgenden Beispiel werden die Welt-und Seiten Transformationen eines <xref:System.Drawing.Graphics> Objekts festgelegt, und anschließend wird eine Linie von (0,0) zu (2, 1) gezeichnet:</span><span class="sxs-lookup"><span data-stu-id="1a8eb-148">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object and then draws a line from (0, 0) to (2, 1):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 <span data-ttu-id="1a8eb-149">In der folgenden Abbildung ist die Linie und das Koordinatensystem dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1a8eb-149">The following illustration shows the line and coordinate system.</span></span>  
  
 <span data-ttu-id="1a8eb-150">![Koordinaten System](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span><span class="sxs-lookup"><span data-stu-id="1a8eb-150">![Coordinate System](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span></span>  
  
 <span data-ttu-id="1a8eb-151">Wenn wir davon ausgehen, dass das Anzeigegerät 96 Punkte pro Zoll in horizontaler Richtung und 96 Punkte pro Zoll in vertikaler Richtung aufweist, haben die Endpunkte der Linie im vorherigen Beispiel die folgenden Koordinaten in den drei Koordinaten Räumen:</span><span class="sxs-lookup"><span data-stu-id="1a8eb-151">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1a8eb-152">Welt</span><span class="sxs-lookup"><span data-stu-id="1a8eb-152">World</span></span>|<span data-ttu-id="1a8eb-153">(0,0) bis (2, 1)</span><span class="sxs-lookup"><span data-stu-id="1a8eb-153">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="1a8eb-154">Seite</span><span class="sxs-lookup"><span data-stu-id="1a8eb-154">Page</span></span>|<span data-ttu-id="1a8eb-155">(2, 0,5) bis (4, 1,5)</span><span class="sxs-lookup"><span data-stu-id="1a8eb-155">(2, 0.5) to (4, 1.5)</span></span>|  
|<span data-ttu-id="1a8eb-156">Gerät</span><span class="sxs-lookup"><span data-stu-id="1a8eb-156">Device</span></span>|<span data-ttu-id="1a8eb-157">(192, 48) bis (384, 144)</span><span class="sxs-lookup"><span data-stu-id="1a8eb-157">(192, 48) to (384, 144)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a8eb-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a8eb-158">See also</span></span>

- [<span data-ttu-id="1a8eb-159">Koordinatensysteme und Transformationen</span><span class="sxs-lookup"><span data-stu-id="1a8eb-159">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="1a8eb-160">Matrixdarstellung von Transformationen</span><span class="sxs-lookup"><span data-stu-id="1a8eb-160">Matrix Representation of Transformations</span></span>](matrix-representation-of-transformations.md)
