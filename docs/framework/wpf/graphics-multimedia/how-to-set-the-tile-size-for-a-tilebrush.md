---
title: 'Vorgehensweise: Festlegen der Kachelgröße für einen TileBrush'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: 80b5dfc668464df829db593668bea8a9a4ec09e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61804195"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a><span data-ttu-id="37b81-102">Vorgehensweise: Festlegen der Kachelgröße für einen TileBrush</span><span class="sxs-lookup"><span data-stu-id="37b81-102">How to: Set the Tile Size for a TileBrush</span></span>

<span data-ttu-id="37b81-103">Dieses Beispiel veranschaulicht das Festlegen die Flächengröße für ein <xref:System.Windows.Media.TileBrush>.</span><span class="sxs-lookup"><span data-stu-id="37b81-103">This example shows how to set the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="37b81-104">Standardmäßig eine <xref:System.Windows.Media.TileBrush> erzeugt eine einzelne Kachel, die den Bereich vollständig ausfüllt, die Sie zeichnen werden.</span><span class="sxs-lookup"><span data-stu-id="37b81-104">By default, a <xref:System.Windows.Media.TileBrush> produces a single tile that completely fills the area that you are painting.</span></span> <span data-ttu-id="37b81-105">Sie können dieses Verhalten überschreiben, indem Sie die Einstellung der <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="37b81-105">You can override this behavior by setting the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties.</span></span>

<span data-ttu-id="37b81-106">Die <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft gibt die Flächengröße für ein <xref:System.Windows.Media.TileBrush>.</span><span class="sxs-lookup"><span data-stu-id="37b81-106">The <xref:System.Windows.Media.TileBrush.Viewport%2A> property specifies the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="37b81-107">Standardmäßig wird der Wert des der <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft ist relativ zur Größe des gezeichneten Bereichs.</span><span class="sxs-lookup"><span data-stu-id="37b81-107">By default, the value of the <xref:System.Windows.Media.TileBrush.Viewport%2A> property is relative to the size of the area being painted.</span></span> <span data-ttu-id="37b81-108">Vornehmen der <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft geben Sie eine absolute Flächengröße, legen Sie die <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Eigenschaft <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="37b81-108">To make the <xref:System.Windows.Media.TileBrush.Viewport%2A> property specify an absolute tile size, set the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property to <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span>

## <a name="example"></a><span data-ttu-id="37b81-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="37b81-109">Example</span></span>

<span data-ttu-id="37b81-110">Im folgenden Beispiel wird ein <xref:System.Windows.Media.ImageBrush>, einen Typ von <xref:System.Windows.Media.TileBrush>, um ein Rechteck mit Flächen gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="37b81-110">The following example uses an <xref:System.Windows.Media.ImageBrush>, a type of <xref:System.Windows.Media.TileBrush>, to paint a rectangle with tiles.</span></span> <span data-ttu-id="37b81-111">Im Beispiel wird jede Kachel auf 50 x 50 Prozent des Ausgabebereichs (das Rechteck).</span><span class="sxs-lookup"><span data-stu-id="37b81-111">The example sets each tile to 50 percent by 50 percent of the output area (the rectangle).</span></span> <span data-ttu-id="37b81-112">Als Ergebnis wird das Rechteck mit vier Projektionen des Bilds gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="37b81-112">As a result, the rectangle is painted with four projections of the image.</span></span>

<span data-ttu-id="37b81-113">Die folgende Abbildung zeigt die Ausgabe, die das Beispiel erzeugt:</span><span class="sxs-lookup"><span data-stu-id="37b81-113">The following illustration shows the output that the example produces:</span></span>

![Ein Rechteck mit vier Kirschen Anordnung mit einem Bildpinsel veranschaulicht.](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

<span data-ttu-id="37b81-115">Im nächsten Beispiel wird erstellt eine <xref:System.Windows.Media.ImageBrush>, legt diese fest seine <xref:System.Windows.Media.TileBrush.Viewport%2A> zu `0,0,25,25` und die zugehörige <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> zu <xref:System.Windows.Media.BrushMappingMode.Absolute>, und verwendet, um ein weiteres Rechteck gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="37b81-115">The next example creates an <xref:System.Windows.Media.ImageBrush>, sets its <xref:System.Windows.Media.TileBrush.Viewport%2A> to `0,0,25,25` and its <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> to <xref:System.Windows.Media.BrushMappingMode.Absolute>, and uses it to paint another rectangle.</span></span> <span data-ttu-id="37b81-116">Als Ergebnis erzeugt der Pinsel Flächen mit einer Breite und Höhe von 25 Pixeln.</span><span class="sxs-lookup"><span data-stu-id="37b81-116">As a result, the brush produces tiles that have a width of 25  pixels and a height of 25 pixels .</span></span>

<span data-ttu-id="37b81-117">Die folgende Abbildung zeigt die Ausgabe, die das Beispiel erzeugt:</span><span class="sxs-lookup"><span data-stu-id="37b81-117">The following illustration shows the output that the example produces:</span></span>

![Ein Rechteck mit zugeht Kirschen einen gekachelten TileBrush mit einem Viewport veranschaulicht.](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

<span data-ttu-id="37b81-119">Die vorangehenden Beispiele sind Teil eines umfangreicheren Beispiels.</span><span class="sxs-lookup"><span data-stu-id="37b81-119">The preceding examples are part of a larger sample.</span></span> <span data-ttu-id="37b81-120">Das vollständige Beispiel finden Sie unter [Beispiel zu ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005).</span><span class="sxs-lookup"><span data-stu-id="37b81-120">For the complete sample, see [ImageBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160005).</span></span>

<span data-ttu-id="37b81-121">Obwohl dieses Beispiel verwendet die <xref:System.Windows.Media.ImageBrush> -Klasse, die <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Eigenschaften verhalten sich identisch, für die anderen <xref:System.Windows.Media.TileBrush> Objekte, d. h. für <xref:System.Windows.Media.DrawingBrush> und <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="37b81-121">Although this example uses the <xref:System.Windows.Media.ImageBrush> class, the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties behave identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="37b81-122">Weitere Informationen zu <xref:System.Windows.Media.ImageBrush> und die andere <xref:System.Windows.Media.TileBrush> Objekten finden Sie [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="37b81-122">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="37b81-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37b81-123">See also</span></span>

- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="37b81-124">Zeichnen mit Bildern, Zeichnungen und visuellen Elementen</span><span class="sxs-lookup"><span data-stu-id="37b81-124">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="37b81-125">Erstellen von unterschiedlichen Kachelmustern mit einem TileBrush</span><span class="sxs-lookup"><span data-stu-id="37b81-125">Create Different Tile Patterns with a TileBrush</span></span>](how-to-create-different-tile-patterns-with-a-tilebrush.md)
