---
title: 'Vorgehensweise: Zeichnen eines Bereichs mit einem Video'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting with a video [WPF]
- video [WPF], painting with
- brushes [WPF], painting with a video
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
ms.openlocfilehash: be09d1310847cd7214ea795a704c25d994f07b7a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151176"
---
# <a name="how-to-paint-an-area-with-a-video"></a><span data-ttu-id="69523-102">Vorgehensweise: Zeichnen eines Bereichs mit einem Video</span><span class="sxs-lookup"><span data-stu-id="69523-102">How to: Paint an Area with a Video</span></span>
<span data-ttu-id="69523-103">Dieses Beispiel zeigt, wie Sie das Zeichnen eines Bereichs mit Media.</span><span class="sxs-lookup"><span data-stu-id="69523-103">This example shows how to paint an area with media.</span></span> <span data-ttu-id="69523-104">Eine Möglichkeit zum Zeichnen eines Bereichs mit Medien ist die Verwendung einer <xref:System.Windows.Controls.MediaElement> zusammen mit einem <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="69523-104">One way to paint an area with media is to use a <xref:System.Windows.Controls.MediaElement> together with a <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="69523-105">Verwenden der <xref:System.Windows.Controls.MediaElement> laden und Wiedergeben der Medien und verwenden dieses dann zum Festlegen der <xref:System.Windows.Media.VisualBrush.Visual%2A> Eigenschaft der <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="69523-105">Use the <xref:System.Windows.Controls.MediaElement> to load and play the media, and then use it to set the <xref:System.Windows.Media.VisualBrush.Visual%2A> property of the <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="69523-106">Anschließend können Sie die <xref:System.Windows.Media.VisualBrush> zum Zeichnen eines Bereichs mit den geladenen Medien.</span><span class="sxs-lookup"><span data-stu-id="69523-106">You can then use the <xref:System.Windows.Media.VisualBrush> to paint an area with the loaded media.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69523-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="69523-107">Example</span></span>  
 <span data-ttu-id="69523-108">Im folgenden Beispiel wird eine <xref:System.Windows.Controls.MediaElement> und ein <xref:System.Windows.Media.VisualBrush> zum Zeichnen der <xref:System.Windows.Controls.TextBlock.Foreground%2A> von einer <xref:System.Windows.Controls.TextBlock> -Steuerelement mit Video.</span><span class="sxs-lookup"><span data-stu-id="69523-108">The following example uses a <xref:System.Windows.Controls.MediaElement> and a <xref:System.Windows.Media.VisualBrush> to paint the <xref:System.Windows.Controls.TextBlock.Foreground%2A> of a <xref:System.Windows.Controls.TextBlock> control with video.</span></span> <span data-ttu-id="69523-109">In diesem Beispiel wird die <xref:System.Windows.Controls.MediaElement.IsMuted%2A> Eigenschaft der <xref:System.Windows.Controls.MediaElement> zu `true` , damit es kein Sound abgespielt wird.</span><span class="sxs-lookup"><span data-stu-id="69523-109">This example sets the <xref:System.Windows.Controls.MediaElement.IsMuted%2A> property of the <xref:System.Windows.Controls.MediaElement> to `true` so that it produces no sound.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a><span data-ttu-id="69523-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="69523-110">Example</span></span>  
 <span data-ttu-id="69523-111">Da <xref:System.Windows.Media.VisualBrush> erbt von der <xref:System.Windows.Media.TileBrush> -Klasse stellt mehrere Kachelmodi bereit.</span><span class="sxs-lookup"><span data-stu-id="69523-111">Because <xref:System.Windows.Media.VisualBrush> inherits from the <xref:System.Windows.Media.TileBrush> class, it provides several tiling modes.</span></span> <span data-ttu-id="69523-112">Durch Festlegen der <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft eine <xref:System.Windows.Media.VisualBrush> zu <xref:System.Windows.Media.TileMode.Tile> und durch Festlegen der <xref:System.Windows.Media.TileBrush.Viewport%2A> -Eigenschaft auf einen Wert kleiner als der Bereich, der zu zeichnenden, Sie können ein Kachelmuster erstellen.</span><span class="sxs-lookup"><span data-stu-id="69523-112">By setting the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.VisualBrush> to <xref:System.Windows.Media.TileMode.Tile> and by setting its <xref:System.Windows.Media.TileBrush.Viewport%2A> property to a value smaller than the area that you are painting, you can create a tiled pattern.</span></span>  
  
 <span data-ttu-id="69523-113">Im folgende Beispiel ist identisch mit dem vorherigen Beispiel, außer dass die <xref:System.Windows.Media.VisualBrush> ein Muster aus dem Video generiert.</span><span class="sxs-lookup"><span data-stu-id="69523-113">The following example is identical to the previous example, except that the <xref:System.Windows.Media.VisualBrush> generates a pattern from the video.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 <span data-ttu-id="69523-114">Informationen zur Vorgehensweise beim Hinzufügen einer Inhaltsdatei, z. B. eine Mediendatei an Ihre Anwendung finden Sie unter [WPF-Anwendungsressource, Inhalt und Datendateien](../app-development/wpf-application-resource-content-and-data-files.md).</span><span class="sxs-lookup"><span data-stu-id="69523-114">For information about how to add a content file, such as a media file, to your application, see [WPF Application Resource, Content, and Data Files](../app-development/wpf-application-resource-content-and-data-files.md).</span></span> <span data-ttu-id="69523-115">Wenn Sie eine Mediendatei hinzufügen, müssen Sie es als eine Datei mit Inhalt und nicht als eine Ressourcendatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="69523-115">When you add a media file, you must add it as a content file, not as a resource file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69523-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69523-116">See also</span></span>

- <xref:System.Windows.Media.VisualBrush>
- [<span data-ttu-id="69523-117">Zeichnen mit Bildern, Zeichnungen und visuellen Elementen</span><span class="sxs-lookup"><span data-stu-id="69523-117">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="69523-118">Übersicht über TileBrush</span><span class="sxs-lookup"><span data-stu-id="69523-118">TileBrush Overview</span></span>](tilebrush-overview.md)
- [<span data-ttu-id="69523-119">Übersicht über Multimedia</span><span class="sxs-lookup"><span data-stu-id="69523-119">Multimedia Overview</span></span>](multimedia-overview.md)
