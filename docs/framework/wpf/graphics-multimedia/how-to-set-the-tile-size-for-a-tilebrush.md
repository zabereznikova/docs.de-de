---
title: 'Gewusst wie: Festlegen der Flächengröße für ein TileBrush-Objekt'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: af7bab59a292549b29dad9b6a7417f22b1b84e48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186833"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a><span data-ttu-id="c6363-102">Gewusst wie: Festlegen der Flächengröße für ein TileBrush-Objekt</span><span class="sxs-lookup"><span data-stu-id="c6363-102">How to: Set the Tile Size for a TileBrush</span></span>

<span data-ttu-id="c6363-103">In diesem Beispiel wird gezeigt, <xref:System.Windows.Media.TileBrush>wie die Kachelgröße für eine festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="c6363-103">This example shows how to set the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="c6363-104">Standardmäßig erzeugt <xref:System.Windows.Media.TileBrush> a eine einzelne Kachel, die den Bereich, den Sie malen, vollständig ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="c6363-104">By default, a <xref:System.Windows.Media.TileBrush> produces a single tile that completely fills the area that you are painting.</span></span> <span data-ttu-id="c6363-105">Sie können dieses Verhalten überschreiben, indem Sie die <xref:System.Windows.Media.TileBrush.Viewport%2A> und-Eigenschaften <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> festlegen.</span><span class="sxs-lookup"><span data-stu-id="c6363-105">You can override this behavior by setting the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties.</span></span>

<span data-ttu-id="c6363-106">Die <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft gibt die Kachelgröße für eine <xref:System.Windows.Media.TileBrush>an.</span><span class="sxs-lookup"><span data-stu-id="c6363-106">The <xref:System.Windows.Media.TileBrush.Viewport%2A> property specifies the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="c6363-107">Standardmäßig ist der Wert <xref:System.Windows.Media.TileBrush.Viewport%2A> der Eigenschaft relativ zur Größe des zu malenden Bereichs.</span><span class="sxs-lookup"><span data-stu-id="c6363-107">By default, the value of the <xref:System.Windows.Media.TileBrush.Viewport%2A> property is relative to the size of the area being painted.</span></span> <span data-ttu-id="c6363-108">Damit die <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft eine absolute Kachelgröße <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> angibt, legen Sie die Eigenschaft auf fest. <xref:System.Windows.Media.BrushMappingMode.Absolute></span><span class="sxs-lookup"><span data-stu-id="c6363-108">To make the <xref:System.Windows.Media.TileBrush.Viewport%2A> property specify an absolute tile size, set the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property to <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span>

## <a name="example"></a><span data-ttu-id="c6363-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c6363-109">Example</span></span>

<span data-ttu-id="c6363-110">Im folgenden Beispiel <xref:System.Windows.Media.ImageBrush>wird ein <xref:System.Windows.Media.TileBrush>, ein Typ von verwendet, um ein Rechteck mit Kacheln zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="c6363-110">The following example uses an <xref:System.Windows.Media.ImageBrush>, a type of <xref:System.Windows.Media.TileBrush>, to paint a rectangle with tiles.</span></span> <span data-ttu-id="c6363-111">Im Beispiel wird jede Kachel auf 50 Prozent um 50 Prozent der Ausgabefläche (rechteckig) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c6363-111">The example sets each tile to 50 percent by 50 percent of the output area (the rectangle).</span></span> <span data-ttu-id="c6363-112">Als Ergebnis wird das Rechteck mit vier Projektionen des Bilds gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c6363-112">As a result, the rectangle is painted with four projections of the image.</span></span>

<span data-ttu-id="c6363-113">Die folgende Abbildung zeigt die Ausgabe, die das Beispiel erzeugt:</span><span class="sxs-lookup"><span data-stu-id="c6363-113">The following illustration shows the output that the example produces:</span></span>

![Ein Rechteck mit vier Kirschen, die Fliesen mit einem Bildpinsel demonstrieren.](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

<span data-ttu-id="c6363-115">Im nächsten Beispiel <xref:System.Windows.Media.ImageBrush>wird <xref:System.Windows.Media.TileBrush.Viewport%2A> eine `0,0,25,25` , <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> <xref:System.Windows.Media.BrushMappingMode.Absolute>auf und auf festgelegt und verwendet, um ein weiteres Rechteck zu malen.</span><span class="sxs-lookup"><span data-stu-id="c6363-115">The next example creates an <xref:System.Windows.Media.ImageBrush>, sets its <xref:System.Windows.Media.TileBrush.Viewport%2A> to `0,0,25,25` and its <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> to <xref:System.Windows.Media.BrushMappingMode.Absolute>, and uses it to paint another rectangle.</span></span> <span data-ttu-id="c6363-116">Als Ergebnis erzeugt der Pinsel Flächen mit einer Breite und Höhe von 25 Pixeln.</span><span class="sxs-lookup"><span data-stu-id="c6363-116">As a result, the brush produces tiles that have a width of 25  pixels and a height of 25 pixels .</span></span>

<span data-ttu-id="c6363-117">Die folgende Abbildung zeigt die Ausgabe, die das Beispiel erzeugt:</span><span class="sxs-lookup"><span data-stu-id="c6363-117">The following illustration shows the output that the example produces:</span></span>

![Ein Rechteck mit 48 Kirschen, die einen gefliesten TileBrush mit einem Viewport demonstrieren.](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

<span data-ttu-id="c6363-119">Die vorangehenden Beispiele sind Teil eines umfangreicheren Beispiels.</span><span class="sxs-lookup"><span data-stu-id="c6363-119">The preceding examples are part of a larger sample.</span></span> <span data-ttu-id="c6363-120">Das vollständige Beispiel finden Sie unter [ImageBrush-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span><span class="sxs-lookup"><span data-stu-id="c6363-120">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>

<span data-ttu-id="c6363-121">Obwohl in diesem <xref:System.Windows.Media.ImageBrush> Beispiel <xref:System.Windows.Media.TileBrush.Viewport%2A> die <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Klasse verwendet wird, <xref:System.Windows.Media.TileBrush> verhalten sich die <xref:System.Windows.Media.DrawingBrush> und-Eigenschaften für die anderen Objekte, d. h. für und, <xref:System.Windows.Media.VisualBrush>identisch.</span><span class="sxs-lookup"><span data-stu-id="c6363-121">Although this example uses the <xref:System.Windows.Media.ImageBrush> class, the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties behave identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="c6363-122">Weitere Informationen <xref:System.Windows.Media.ImageBrush> zu und <xref:System.Windows.Media.TileBrush> zu den anderen Objekten finden Sie unter [Malen mit Bildern, Zeichnungen und Visuals](painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="c6363-122">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c6363-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6363-123">See also</span></span>

- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="c6363-124">Zeichnen mit Bildern, Zeichnungen und visuellen Elementen</span><span class="sxs-lookup"><span data-stu-id="c6363-124">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="c6363-125">Erstellen von unterschiedlichen Kachelmustern mit einem TileBrush</span><span class="sxs-lookup"><span data-stu-id="c6363-125">Create Different Tile Patterns with a TileBrush</span></span>](how-to-create-different-tile-patterns-with-a-tilebrush.md)
