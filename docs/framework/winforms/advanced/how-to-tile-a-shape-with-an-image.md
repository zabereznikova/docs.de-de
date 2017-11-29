---
title: 'Gewusst wie: Kacheln einer Form mit einem Bild'
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
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f825371d3849e96ace627e660fd7c59bd290185
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-tile-a-shape-with-an-image"></a><span data-ttu-id="f99ac-102">Gewusst wie: Kacheln einer Form mit einem Bild</span><span class="sxs-lookup"><span data-stu-id="f99ac-102">How to: Tile a Shape with an Image</span></span>
<span data-ttu-id="f99ac-103">Wie Kacheln eine Etage abdecken nebeneinander platziert werden können, können rechteckige Bilder zum Füllen (Kachel) eine Form vom Typ nebeneinander platziert werden.</span><span class="sxs-lookup"><span data-stu-id="f99ac-103">Just as tiles can be placed next to each other to cover a floor, rectangular images can be placed next to each other to fill (tile) a shape.</span></span> <span data-ttu-id="f99ac-104">Um das Innere einer Form gekachelt, verwenden Sie einen Strukturpinsel.</span><span class="sxs-lookup"><span data-stu-id="f99ac-104">To tile the interior of a shape, use a texture brush.</span></span> <span data-ttu-id="f99ac-105">Bei der Erstellung einer <xref:System.Drawing.TextureBrush> Objekt eines der Argumente, die Sie an den Konstruktor übergeben, wird ein <xref:System.Drawing.Image> Objekt.</span><span class="sxs-lookup"><span data-stu-id="f99ac-105">When you construct a <xref:System.Drawing.TextureBrush> object, one of the arguments you pass to the constructor is an <xref:System.Drawing.Image> object.</span></span> <span data-ttu-id="f99ac-106">Wenn Sie die Strukturpinsel verwenden, um das Innere einer Form zu zeichnen, wird die Form mit wiederholten Kopien dieses Bild gefüllt.</span><span class="sxs-lookup"><span data-stu-id="f99ac-106">When you use the texture brush to paint the interior of a shape, the shape is filled with repeated copies of this image.</span></span>  
  
 <span data-ttu-id="f99ac-107">Der Wrap-Mode-Eigenschaft von der <xref:System.Drawing.TextureBrush> Objekt bestimmt, wie das Bild ausgerichtet ist, da es in einem rechteckigen Raster wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="f99ac-107">The wrap mode property of the <xref:System.Drawing.TextureBrush> object determines how the image is oriented as it is repeated in a rectangular grid.</span></span> <span data-ttu-id="f99ac-108">Können Sie alles, was die Kacheln im Raster sind die gleiche Ausrichtung vornehmen können, oder Sie das Image von einer Rasterseite Position zur nächsten kippen.</span><span class="sxs-lookup"><span data-stu-id="f99ac-108">You can make all the tiles in the grid have the same orientation, or you can make the image flip from one grid position to the next.</span></span> <span data-ttu-id="f99ac-109">Die kippen kann horizontal, vertikal oder beides.</span><span class="sxs-lookup"><span data-stu-id="f99ac-109">The flipping can be horizontal, vertical, or both.</span></span> <span data-ttu-id="f99ac-110">Die folgenden Beispiele zeigen die Kacheln mit verschiedenen Typen von spiegeln.</span><span class="sxs-lookup"><span data-stu-id="f99ac-110">The following examples demonstrate tiling with different types of flipping.</span></span>  
  
### <a name="to-tile-an-image"></a><span data-ttu-id="f99ac-111">Um ein Bild Kachel</span><span class="sxs-lookup"><span data-stu-id="f99ac-111">To tile an image</span></span>  
  
-   <span data-ttu-id="f99ac-112">In diesem Beispiel verwendet Abbildung 75 × 75, um ein Rechteck 200 x 200 Kachel.</span><span class="sxs-lookup"><span data-stu-id="f99ac-112">This example uses the following 75×75 image to tile a 200×200 rectangle.</span></span>  
  
 <span data-ttu-id="f99ac-113">![Kachel 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span><span class="sxs-lookup"><span data-stu-id="f99ac-113">![Tile 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span></span>  
  
-   <span data-ttu-id="f99ac-114">Die folgende Abbildung zeigt, wie das Rechteck mit dem Bild gekachelt wird.</span><span class="sxs-lookup"><span data-stu-id="f99ac-114">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="f99ac-115">Beachten Sie, dass alle Kacheln dieselbe Ausrichtung haben. Es gibt keine ein umlegen.</span><span class="sxs-lookup"><span data-stu-id="f99ac-115">Note that all tiles have the same orientation; there is no flipping.</span></span>  
  
 <span data-ttu-id="f99ac-116">![Kachel 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span><span class="sxs-lookup"><span data-stu-id="f99ac-116">![Tile 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a><span data-ttu-id="f99ac-117">Um ein Bild Kacheln horizontal gekippt.</span><span class="sxs-lookup"><span data-stu-id="f99ac-117">To flip an image horizontally while tiling</span></span>  
  
-   <span data-ttu-id="f99ac-118">Dieses Beispiel verwendet das gleiche 75 × 75 Bild zum Ausfüllen eines Rechtecks 200 x 200.</span><span class="sxs-lookup"><span data-stu-id="f99ac-118">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="f99ac-119">Der Wrap-Modus festgelegt ist, das Bild horizontal gekippt.</span><span class="sxs-lookup"><span data-stu-id="f99ac-119">The wrap mode is set to flip the image horizontally.</span></span> <span data-ttu-id="f99ac-120">Die folgende Abbildung zeigt, wie das Rechteck mit dem Bild gekachelt wird.</span><span class="sxs-lookup"><span data-stu-id="f99ac-120">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="f99ac-121">Beachten Sie, wie Sie eine Kachel zur nächsten in einer bestimmten Zeile verschieben, wird das Bild horizontal gekippt.</span><span class="sxs-lookup"><span data-stu-id="f99ac-121">Note that as you move from one tile to the next in a given row, the image is flipped horizontally.</span></span>  
  
 <span data-ttu-id="f99ac-122">![Kachel 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span><span class="sxs-lookup"><span data-stu-id="f99ac-122">![Tile 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a><span data-ttu-id="f99ac-123">Um ein Bild Kacheln vertikal kippen</span><span class="sxs-lookup"><span data-stu-id="f99ac-123">To flip an image vertically while tiling</span></span>  
  
-   <span data-ttu-id="f99ac-124">Dieses Beispiel verwendet das gleiche 75 × 75 Bild zum Ausfüllen eines Rechtecks 200 x 200.</span><span class="sxs-lookup"><span data-stu-id="f99ac-124">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="f99ac-125">Der Wrap-Modus festgelegt ist, das Bild vertikal gekippt.</span><span class="sxs-lookup"><span data-stu-id="f99ac-125">The wrap mode is set to flip the image vertically.</span></span>  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a><span data-ttu-id="f99ac-126">Um ein Bild Kacheln horizontal und vertikal kippen</span><span class="sxs-lookup"><span data-stu-id="f99ac-126">To flip an image horizontally and vertically while tiling</span></span>  
  
-   <span data-ttu-id="f99ac-127">In diesem Beispiel verwendet dasselbe 75 × 75 Bild, um ein Rechteck 200 x 200 Kachel.</span><span class="sxs-lookup"><span data-stu-id="f99ac-127">This example uses the same 75×75 image to tile a 200×200 rectangle.</span></span> <span data-ttu-id="f99ac-128">Der Umbruchmodus wird festgelegt, um das Bild horizontal und vertikal gekippt.</span><span class="sxs-lookup"><span data-stu-id="f99ac-128">The wrap mode is set to flip the image both horizontally and vertically.</span></span> <span data-ttu-id="f99ac-129">Die folgende Abbildung zeigt, wie das Rechteck mit dem Bild gekachelt wird.</span><span class="sxs-lookup"><span data-stu-id="f99ac-129">The following illustration shows how the rectangle is tiled by the image.</span></span> <span data-ttu-id="f99ac-130">Beachten Sie, wie Sie eine Kachel zur nächsten in einer bestimmten Zeile verschieben, wird das Bild horizontal gekippt, und wie Sie eine Kachel zur nächsten in einer bestimmten Spalte verschieben, wird das Bild vertikal gekippt.</span><span class="sxs-lookup"><span data-stu-id="f99ac-130">Note that as you move from one tile to the next in a given row, the image is flipped horizontally, and as you move from one tile to the next in a given column, the image is flipped vertically.</span></span>  
  
 <span data-ttu-id="f99ac-131">![Kachel 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span><span class="sxs-lookup"><span data-stu-id="f99ac-131">![Tile 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="f99ac-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f99ac-132">See Also</span></span>  
 [<span data-ttu-id="f99ac-133">Verwenden eines Pinsels zum Ausfüllen von Formen</span><span class="sxs-lookup"><span data-stu-id="f99ac-133">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
