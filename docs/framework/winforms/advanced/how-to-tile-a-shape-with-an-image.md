---
title: 'Vorgehensweise: Kacheln einer Form mit einem Bild'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
ms.openlocfilehash: d873ba717fa94852692ce395ef7da30c512aba59
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719688"
---
# <a name="how-to-tile-a-shape-with-an-image"></a><span data-ttu-id="514df-102">Vorgehensweise: Kacheln einer Form mit einem Bild</span><span class="sxs-lookup"><span data-stu-id="514df-102">How to: Tile a Shape with an Image</span></span>
<span data-ttu-id="514df-103">Genau wie Kacheln ein Fußboden nebeneinander platziert werden können, können rechteckige Images Fill (Kachel) eine Form nebeneinander platziert werden.</span><span class="sxs-lookup"><span data-stu-id="514df-103">Just as tiles can be placed next to each other to cover a floor, rectangular images can be placed next to each other to fill (tile) a shape.</span></span> <span data-ttu-id="514df-104">Verwenden Sie, um das Innere einer Form Kachel, eines Pinsels Textur.</span><span class="sxs-lookup"><span data-stu-id="514df-104">To tile the interior of a shape, use a texture brush.</span></span> <span data-ttu-id="514df-105">Beim Erstellen einer <xref:System.Drawing.TextureBrush> Objekt ist, wird eines der Argumente, die Sie an den Konstruktor übergeben, wird ein <xref:System.Drawing.Image> Objekt.</span><span class="sxs-lookup"><span data-stu-id="514df-105">When you construct a <xref:System.Drawing.TextureBrush> object, one of the arguments you pass to the constructor is an <xref:System.Drawing.Image> object.</span></span> <span data-ttu-id="514df-106">Wenn Sie den Texturpinsel verwenden, um das Innere einer Form zu zeichnen, wird die Form durch wiederholte Kopien dieses Bilds gefüllt.</span><span class="sxs-lookup"><span data-stu-id="514df-106">When you use the texture brush to paint the interior of a shape, the shape is filled with repeated copies of this image.</span></span>  
  
 <span data-ttu-id="514df-107">Der Wrap-Mode-Eigenschaft von der <xref:System.Drawing.TextureBrush> Objekt bestimmt, wie das Bild ausgerichtet ist, wie es in einem rechteckigen Raster wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="514df-107">The wrap mode property of the <xref:System.Drawing.TextureBrush> object determines how the image is oriented as it is repeated in a rectangular grid.</span></span> <span data-ttu-id="514df-108">Können Sie alles, was die Kacheln im Raster die gleiche Ausrichtung vornehmen können, oder Sie das Image von einer Rasterseite Position zum nächsten zu kippen.</span><span class="sxs-lookup"><span data-stu-id="514df-108">You can make all the tiles in the grid have the same orientation, or you can make the image flip from one grid position to the next.</span></span> <span data-ttu-id="514df-109">Die kippen möglich horizontal, vertikal oder beides.</span><span class="sxs-lookup"><span data-stu-id="514df-109">The flipping can be horizontal, vertical, or both.</span></span> <span data-ttu-id="514df-110">Die folgenden Beispiele veranschaulichen die Kacheln mit unterschiedlichen Arten von kippen.</span><span class="sxs-lookup"><span data-stu-id="514df-110">The following examples demonstrate tiling with different types of flipping.</span></span>  
  
### <a name="to-tile-an-image"></a><span data-ttu-id="514df-111">Ein Bild gekachelt</span><span class="sxs-lookup"><span data-stu-id="514df-111">To tile an image</span></span>  
  
-   <span data-ttu-id="514df-112">Dieses Beispiel verwendet die folgende Abbildung 75 × 75 zu einem Rechteck 200 x 200-Kachel.</span><span class="sxs-lookup"><span data-stu-id="514df-112">This example uses the following 75×75 image to tile a 200×200 rectangle.</span></span>  
  
 <span data-ttu-id="514df-113">![Kachel "1](./media/tile1.gif "tile1")</span><span class="sxs-lookup"><span data-stu-id="514df-113">![Tile 1](./media/tile1.gif "tile1")</span></span>  
  
-   <span data-ttu-id="514df-114">Die folgende Abbildung zeigt, wie das Rechteck mit dem Image gekachelt wird.</span><span class="sxs-lookup"><span data-stu-id="514df-114">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="514df-115">Beachten Sie, dass alle Kacheln die gleiche Ausrichtung; Es gibt kein Kippen verwendet.</span><span class="sxs-lookup"><span data-stu-id="514df-115">Note that all tiles have the same orientation; there is no flipping.</span></span>  
  
 <span data-ttu-id="514df-116">![Kachel 2](./media/tile2.gif "tile2")</span><span class="sxs-lookup"><span data-stu-id="514df-116">![Tile 2](./media/tile2.gif "tile2")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a><span data-ttu-id="514df-117">Um ein Bild in Kacheln horizontal kippen</span><span class="sxs-lookup"><span data-stu-id="514df-117">To flip an image horizontally while tiling</span></span>  
  
-   <span data-ttu-id="514df-118">Dieses Beispiel verwendet das gleiche Bild für die 75 × 75 ein 200 x 200 Rechteck ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="514df-118">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="514df-119">Der Umbruchmodus wird festgelegt, um das Bild horizontal gekippt.</span><span class="sxs-lookup"><span data-stu-id="514df-119">The wrap mode is set to flip the image horizontally.</span></span> <span data-ttu-id="514df-120">Die folgende Abbildung zeigt, wie das Rechteck mit dem Image gekachelt wird.</span><span class="sxs-lookup"><span data-stu-id="514df-120">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="514df-121">Beachten Sie, wie Sie von einer Kachel in den nächsten in einer angegebenen Zeile verschieben, wird das Bild horizontal gekippt.</span><span class="sxs-lookup"><span data-stu-id="514df-121">Note that as you move from one tile to the next in a given row, the image is flipped horizontally.</span></span>  
  
 <span data-ttu-id="514df-122">![Kachel "3](./media/tile3.gif "tile3")</span><span class="sxs-lookup"><span data-stu-id="514df-122">![Tile 3](./media/tile3.gif "tile3")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a><span data-ttu-id="514df-123">Um ein Bild in Kacheln vertikal kippen</span><span class="sxs-lookup"><span data-stu-id="514df-123">To flip an image vertically while tiling</span></span>  
  
-   <span data-ttu-id="514df-124">Dieses Beispiel verwendet das gleiche Bild für die 75 × 75 ein 200 x 200 Rechteck ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="514df-124">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="514df-125">Der Umbruchmodus wird festgelegt, um das Bild vertikal gekippt.</span><span class="sxs-lookup"><span data-stu-id="514df-125">The wrap mode is set to flip the image vertically.</span></span>  
  
     [!code-csharp[System.Drawing.UsingABrush#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a><span data-ttu-id="514df-126">Um ein Bild Kacheln horizontal und vertikal kippen</span><span class="sxs-lookup"><span data-stu-id="514df-126">To flip an image horizontally and vertically while tiling</span></span>  
  
-   <span data-ttu-id="514df-127">Dieses Beispiel verwendet die gleichen 75 × 75-Image zu einem Rechteck 200 x 200-Kachel.</span><span class="sxs-lookup"><span data-stu-id="514df-127">This example uses the same 75×75 image to tile a 200×200 rectangle.</span></span> <span data-ttu-id="514df-128">Der Umbruchmodus wird festgelegt, das Bild horizontal und vertikal gekippt.</span><span class="sxs-lookup"><span data-stu-id="514df-128">The wrap mode is set to flip the image both horizontally and vertically.</span></span> <span data-ttu-id="514df-129">Die folgende Abbildung zeigt, wie das Rechteck das Image gekachelt wird.</span><span class="sxs-lookup"><span data-stu-id="514df-129">The following illustration shows how the rectangle is tiled by the image.</span></span> <span data-ttu-id="514df-130">Beachten Sie, wie Sie von einer Kachel in den nächsten in einer angegebenen Zeile verschieben, die das Bild horizontal gekippt wird, und wie Sie von einer Kachel in den nächsten in einer bestimmten Spalte verschieben, wird das Bild vertikal gekippt.</span><span class="sxs-lookup"><span data-stu-id="514df-130">Note that as you move from one tile to the next in a given row, the image is flipped horizontally, and as you move from one tile to the next in a given column, the image is flipped vertically.</span></span>  
  
 <span data-ttu-id="514df-131">![Kachel 5](./media/tile5.gif "tile5")</span><span class="sxs-lookup"><span data-stu-id="514df-131">![Tile 5](./media/tile5.gif "tile5")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="514df-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="514df-132">See also</span></span>
- [<span data-ttu-id="514df-133">Verwenden eines Pinsels zum Ausfüllen von Formen</span><span class="sxs-lookup"><span data-stu-id="514df-133">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
