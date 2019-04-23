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
ms.openlocfilehash: 765df4bcd3cef83e624ad8b11676696b95f7d035
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089301"
---
# <a name="types-of-coordinate-systems"></a><span data-ttu-id="6d3f3-102">Typen von Koordinatensystemen</span><span class="sxs-lookup"><span data-stu-id="6d3f3-102">Types of Coordinate Systems</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="6d3f3-103">verwendet drei Koordinatensysteme: Welt, Seiten- und Gerät.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-103">uses three coordinate spaces: world, page, and device.</span></span> <span data-ttu-id="6d3f3-104">Globale Koordinaten sind die Koordinaten, die zum Modellieren einer bestimmten grafikumgebung verwendet und die Koordinaten, die Sie Methoden in .NET Framework übergeben.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-104">World coordinates are the coordinates used to model a particular graphic world and are the coordinates you pass to methods in the .NET Framework.</span></span> <span data-ttu-id="6d3f3-105">Seitenkoordinaten beziehen sich auf das Koordinatensystem, die von einer Zeichenoberfläche, z. B. eines Formulars oder Steuerelements verwendet.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-105">Page coordinates refer to the coordinate system used by a drawing surface, such as a form or control.</span></span> <span data-ttu-id="6d3f3-106">Gerätekoordinaten beziehen, die von der physischen Zeichengerät, z. B. einen Bildschirm oder Blatt Papier verwendet.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-106">Device coordinates are the coordinates used by the physical device being drawn on, such as a screen or sheet of paper.</span></span> <span data-ttu-id="6d3f3-107">Wenn Sie den Aufruf vornehmen `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, die Punkte, die Sie übergeben die <xref:System.Drawing.Graphics.DrawLine%2A> Methode –`(0, 0)` und `(160, 80)`– werden in der Welt Koordinatenraum.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-107">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, the points that you pass to the <xref:System.Drawing.Graphics.DrawLine%2A> method—`(0, 0)` and `(160, 80)`—are in the world coordinate space.</span></span> <span data-ttu-id="6d3f3-108">Vor dem [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] die Zeile auf dem Bildschirm zeichnen können, die eine Sequenz von Transformationen durchlaufen die Koordinaten.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-108">Before [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can draw the line on the screen, the coordinates pass through a sequence of transformations.</span></span> <span data-ttu-id="6d3f3-109">Eine Transformation, wird aufgerufen, die globale Transformation, globale Koordinaten in Seitenkoordinaten konvertiert und eine andere Transformation, die genannte Seitentransformation, Seitenkoordinaten in Gerätekoordinaten.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-109">One transformation, called the world transformation, converts world coordinates to page coordinates, and another transformation, called the page transformation, converts page coordinates to device coordinates.</span></span>  
  
## <a name="transforms-and-coordinate-systems"></a><span data-ttu-id="6d3f3-110">Transformationen und Koordinatensysteme</span><span class="sxs-lookup"><span data-stu-id="6d3f3-110">Transforms and Coordinate Systems</span></span>  
 <span data-ttu-id="6d3f3-111">Nehmen wir an, dass Sie mit einem Koordinatensystem arbeiten möchten, die dessen Ursprung im Text der Clientbereich statt in der oberen linken Ecke.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-111">Suppose you want to work with a coordinate system that has its origin in the body of the client area rather than the upper-left corner.</span></span> <span data-ttu-id="6d3f3-112">Angenommen Sie, z. B., dass den Ursprung 100 Pixel vom linken Rand des Clientbereichs und 50 Pixel vom oberen Rand des Clientbereichs sein soll.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-112">Say, for example, that you want the origin to be 100 pixels from the left edge of the client area and 50 pixels from the top of the client area.</span></span> <span data-ttu-id="6d3f3-113">Die folgende Abbildung zeigt eine solche einem Koordinatensystem.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-113">The following illustration shows such a coordinate system.</span></span>  
  
 <span data-ttu-id="6d3f3-114">![Koordinatensystem](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span><span class="sxs-lookup"><span data-stu-id="6d3f3-114">![Coordinate System](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span></span>  
  
 <span data-ttu-id="6d3f3-115">Wenn Sie den Aufruf vornehmen `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, erhalten Sie die Zeile, die in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-115">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, you get the line shown in the following illustration.</span></span>  
  
 <span data-ttu-id="6d3f3-116">![Koordinatensystem](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span><span class="sxs-lookup"><span data-stu-id="6d3f3-116">![Coordinate System](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span></span>  
  
 <span data-ttu-id="6d3f3-117">Die Koordinaten der Endpunkte der Linie in den drei Koordinatensysteme lauten wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="6d3f3-117">The coordinates of the endpoints of your line in the three coordinate spaces are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6d3f3-118">World</span><span class="sxs-lookup"><span data-stu-id="6d3f3-118">World</span></span>|<span data-ttu-id="6d3f3-119">(0, 0), ("160", "80")</span><span class="sxs-lookup"><span data-stu-id="6d3f3-119">(0, 0) to (160, 80)</span></span>|  
|<span data-ttu-id="6d3f3-120">Seite</span><span class="sxs-lookup"><span data-stu-id="6d3f3-120">Page</span></span>|<span data-ttu-id="6d3f3-121">(100, 50), ("260", "130")</span><span class="sxs-lookup"><span data-stu-id="6d3f3-121">(100, 50) to (260, 130)</span></span>|  
|<span data-ttu-id="6d3f3-122">Gerät</span><span class="sxs-lookup"><span data-stu-id="6d3f3-122">Device</span></span>|<span data-ttu-id="6d3f3-123">(100, 50), ("260", "130")</span><span class="sxs-lookup"><span data-stu-id="6d3f3-123">(100, 50) to (260, 130)</span></span>|  
  
 <span data-ttu-id="6d3f3-124">Beachten Sie, dass die Seite einen Koordinatenbereich hat seinen Ursprung auf der linken oberen Ecke des Clientbereichs. Dies wird immer der Fall sein.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-124">Note that the page coordinate space has its origin at the upper-left corner of the client area; this will always be the case.</span></span> <span data-ttu-id="6d3f3-125">Beachten Sie außerdem, da die Maßeinheit Pixel ist, die Gerätekoordinaten die Seitenkoordinaten identisch sind.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-125">Also note that because the unit of measure is the pixel, the device coordinates are the same as the page coordinates.</span></span> <span data-ttu-id="6d3f3-126">Wenn Sie die Maßeinheit mit etwas anderem als Pixel (z. B. Zoll) festlegen, werden die Gerätekoordinaten von den Seitenkoordinaten unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-126">If you set the unit of measure to something other than pixels (for example, inches), then the device coordinates will be different from the page coordinates.</span></span>  
  
 <span data-ttu-id="6d3f3-127">Die globale Transformation, die globale Koordinaten in Seitenkoordinaten zugeordnet wird, wird, verbleibt in der <xref:System.Drawing.Graphics.Transform%2A> Eigenschaft der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-127">The world transformation, which maps world coordinates to page coordinates, is held in the <xref:System.Drawing.Graphics.Transform%2A> property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="6d3f3-128">Im vorherigen Beispiel ist die globale Transformation ein Übersetzungseinheiten 100 in X-Richtung und 50 Einheiten in der y-Richtung.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-128">In the preceding example, the world transformation is a translation 100 units in the x direction and 50 units in the y direction.</span></span> <span data-ttu-id="6d3f3-129">Im folgenden Beispiel wird die globale Transformation für einen <xref:System.Drawing.Graphics> Objekt aus, und klicken Sie dann verwendet, die <xref:System.Drawing.Graphics> Objekt zum Zeichnen der Linie, die in der obigen Abbildung gezeigt:</span><span class="sxs-lookup"><span data-stu-id="6d3f3-129">The following example sets the world transformation of a <xref:System.Drawing.Graphics> object and then uses that <xref:System.Drawing.Graphics> object to draw the line shown in the preceding figure:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 <span data-ttu-id="6d3f3-130">Die Seitentransformation wird Seitenkoordinaten Gerätekoordinaten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-130">The page transformation maps page coordinates to device coordinates.</span></span> <span data-ttu-id="6d3f3-131">Die <xref:System.Drawing.Graphics> -Klasse stellt die <xref:System.Drawing.Graphics.PageUnit%2A> und <xref:System.Drawing.Graphics.PageScale%2A> Eigenschaften für das Bearbeiten der Seitentransformation.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-131">The <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.PageUnit%2A> and <xref:System.Drawing.Graphics.PageScale%2A> properties for manipulating the page transformation.</span></span> <span data-ttu-id="6d3f3-132">Die <xref:System.Drawing.Graphics> Klasse bietet auch zwei schreibgeschützte Eigenschaften, <xref:System.Drawing.Graphics.DpiX%2A> und <xref:System.Drawing.Graphics.DpiY%2A>, überprüfen Sie die horizontale und vertikale DPI-Wert des Anzeigegeräts.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-132">The <xref:System.Drawing.Graphics> class also provides two read-only properties, <xref:System.Drawing.Graphics.DpiX%2A> and <xref:System.Drawing.Graphics.DpiY%2A>, for examining the horizontal and vertical dots per inch of the display device.</span></span>  
  
 <span data-ttu-id="6d3f3-133">Können Sie die <xref:System.Drawing.Graphics.PageUnit%2A> Eigenschaft der <xref:System.Drawing.Graphics> Klasse, einer Maßeinheit als das Pixel an.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-133">You can use the <xref:System.Drawing.Graphics.PageUnit%2A> property of the <xref:System.Drawing.Graphics> class to specify a unit of measure other than the pixel.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d3f3-134">Kann nicht festgelegt werden die <xref:System.Drawing.Graphics.PageUnit%2A> Eigenschaft <xref:System.Drawing.GraphicsUnit.World>, wie dies keine physische Einheit ist, und wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-134">You cannot set the <xref:System.Drawing.Graphics.PageUnit%2A> property to <xref:System.Drawing.GraphicsUnit.World>, as this is not a physical unit and will cause an exception.</span></span>  
  
 <span data-ttu-id="6d3f3-135">Das folgende Beispiel zeichnet eine Linie von (0, 0), (2, 1), in dem der Punkt ("2", "1") ist 2 Zoll rechts und 1 Zoll nach unten, an dem Punkt (0, 0):</span><span class="sxs-lookup"><span data-stu-id="6d3f3-135">The following example draws a line from (0, 0) to (2, 1), where the point (2, 1) is 2 inches to the right and 1 inch down from the point (0, 0):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  <span data-ttu-id="6d3f3-136">Wenn Sie beim Erstellen des Stifts eine Breite nicht angeben, wird im vorherige Beispiel eine Linie gezeichnet, die einen Zoll breit ist.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-136">If you don't specify a pen width when you construct your pen, the preceding example will draw a line that is one inch wide.</span></span> <span data-ttu-id="6d3f3-137">Sie können die Stiftbreite angeben, in das zweite Argument für die <xref:System.Drawing.Pen> Konstruktor:</span><span class="sxs-lookup"><span data-stu-id="6d3f3-137">You can specify the pen width in the second argument to the <xref:System.Drawing.Pen> constructor:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 <span data-ttu-id="6d3f3-138">Wenn Sie davon ausgehen, dass das Anzeigegerät, 96 DPI-Wert in horizontaler Richtung und 96 DPI-Wert in vertikaler Richtung hat, haben die Endpunkte der Linie im vorherigen Beispiel die folgenden Koordinaten in der drei Koordinatensysteme:</span><span class="sxs-lookup"><span data-stu-id="6d3f3-138">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6d3f3-139">World</span><span class="sxs-lookup"><span data-stu-id="6d3f3-139">World</span></span>|<span data-ttu-id="6d3f3-140">(0, 0), (2, 1)</span><span class="sxs-lookup"><span data-stu-id="6d3f3-140">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="6d3f3-141">Seite</span><span class="sxs-lookup"><span data-stu-id="6d3f3-141">Page</span></span>|<span data-ttu-id="6d3f3-142">(0, 0), (2, 1)</span><span class="sxs-lookup"><span data-stu-id="6d3f3-142">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="6d3f3-143">Gerät</span><span class="sxs-lookup"><span data-stu-id="6d3f3-143">Device</span></span>|<span data-ttu-id="6d3f3-144">(0, 0 (null), (192, 96)</span><span class="sxs-lookup"><span data-stu-id="6d3f3-144">(0, 0, to (192, 96)</span></span>|  
  
 <span data-ttu-id="6d3f3-145">Beachten Sie, da der Ursprung der globalen Koordinatensystem auf der linken oberen Ecke des Clientbereichs ist, die Seitenkoordinaten identisch mit der globalen Koordinaten.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-145">Note that because the origin of the world coordinate space is at the upper-left corner of the client area, the page coordinates are the same as the world coordinates.</span></span>  
  
 <span data-ttu-id="6d3f3-146">Sie können die Welt und Seite-Transformationen, um eine Reihe von Effekten erzielen kombinieren.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-146">You can combine the world and page transformations to achieve a variety of effects.</span></span> <span data-ttu-id="6d3f3-147">Nehmen wir beispielsweise an Zoll als Maßeinheit verwendet werden sollen, und den Ursprung des Koordinatensystems 2 Zoll vom linken Rand des Clientbereichs und 1/2 Zoll zwischen dem oberen Rand des Clientbereichs sein sollen.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-147">For example, suppose you want to use inches as the unit of measure and you want the origin of your coordinate system to be 2 inches from the left edge of the client area and 1/2 inch from the top of the client area.</span></span> <span data-ttu-id="6d3f3-148">Im folgenden Beispiel wird die Seite "und" World Transformationen von einem <xref:System.Drawing.Graphics> Objekt aus, und klicken Sie dann zeichnet eine Linie von (0, 0), (2, 1):</span><span class="sxs-lookup"><span data-stu-id="6d3f3-148">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object and then draws a line from (0, 0) to (2, 1):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 <span data-ttu-id="6d3f3-149">Die folgende Abbildung zeigt die Zeile und der Koordinatensystem.</span><span class="sxs-lookup"><span data-stu-id="6d3f3-149">The following illustration shows the line and coordinate system.</span></span>  
  
 <span data-ttu-id="6d3f3-150">![Koordinatensystem](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span><span class="sxs-lookup"><span data-stu-id="6d3f3-150">![Coordinate System](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span></span>  
  
 <span data-ttu-id="6d3f3-151">Wenn Sie davon ausgehen, dass das Anzeigegerät, 96 DPI-Wert in horizontaler Richtung und 96 DPI-Wert in vertikaler Richtung hat, haben die Endpunkte der Linie im vorherigen Beispiel die folgenden Koordinaten in der drei Koordinatensysteme:</span><span class="sxs-lookup"><span data-stu-id="6d3f3-151">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6d3f3-152">World</span><span class="sxs-lookup"><span data-stu-id="6d3f3-152">World</span></span>|<span data-ttu-id="6d3f3-153">(0, 0), (2, 1)</span><span class="sxs-lookup"><span data-stu-id="6d3f3-153">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="6d3f3-154">Seite</span><span class="sxs-lookup"><span data-stu-id="6d3f3-154">Page</span></span>|<span data-ttu-id="6d3f3-155">(2, 0,5), (4, 1.5)</span><span class="sxs-lookup"><span data-stu-id="6d3f3-155">(2, 0.5) to (4, 1.5)</span></span>|  
|<span data-ttu-id="6d3f3-156">Gerät</span><span class="sxs-lookup"><span data-stu-id="6d3f3-156">Device</span></span>|<span data-ttu-id="6d3f3-157">(192, 48), (384, 144)</span><span class="sxs-lookup"><span data-stu-id="6d3f3-157">(192, 48) to (384, 144)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6d3f3-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d3f3-158">See also</span></span>

- [<span data-ttu-id="6d3f3-159">Koordinatensysteme und Transformationen</span><span class="sxs-lookup"><span data-stu-id="6d3f3-159">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="6d3f3-160">Matrixdarstellung von Transformationen</span><span class="sxs-lookup"><span data-stu-id="6d3f3-160">Matrix Representation of Transformations</span></span>](matrix-representation-of-transformations.md)
