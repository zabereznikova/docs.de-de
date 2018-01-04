---
title: 'Gewusst wie: Zeichnen eines Bereichs mit einem Video'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting with a video [WPF]
- video [WPF], painting with
- brushes [WPF], painting with a video
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a72843547d934aeaeec062eec1241e402baf56bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-paint-an-area-with-a-video"></a><span data-ttu-id="eaf09-102">Gewusst wie: Zeichnen eines Bereichs mit einem Video</span><span class="sxs-lookup"><span data-stu-id="eaf09-102">How to: Paint an Area with a Video</span></span>
<span data-ttu-id="eaf09-103">In diesem Beispiel wird gezeigt, wie einen Bereich mit Medien gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="eaf09-103">This example shows how to paint an area with media.</span></span> <span data-ttu-id="eaf09-104">Eine Möglichkeit zum Zeichnen eines Bereichs mit Medien ist die Verwendung einer <xref:System.Windows.Controls.MediaElement> zusammen mit einem <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="eaf09-104">One way to paint an area with media is to use a <xref:System.Windows.Controls.MediaElement> together with a <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="eaf09-105">Verwenden der <xref:System.Windows.Controls.MediaElement> zum Laden und Wiedergeben der Medien und Verwendung zur Festlegung der <xref:System.Windows.Media.VisualBrush.Visual%2A> Eigenschaft von der <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="eaf09-105">Use the <xref:System.Windows.Controls.MediaElement> to load and play the media, and then use it to set the <xref:System.Windows.Media.VisualBrush.Visual%2A> property of the <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="eaf09-106">Anschließend können Sie die <xref:System.Windows.Media.VisualBrush> um einen Bereich mit den geladenen Medien zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="eaf09-106">You can then use the <xref:System.Windows.Media.VisualBrush> to paint an area with the loaded media.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eaf09-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eaf09-107">Example</span></span>  
 <span data-ttu-id="eaf09-108">Im folgenden Beispiel wird eine <xref:System.Windows.Controls.MediaElement> und ein <xref:System.Windows.Media.VisualBrush> zum Zeichnen der <xref:System.Windows.Controls.TextBlock.Foreground%2A> des ein <xref:System.Windows.Controls.TextBlock> -Steuerelement mit Video.</span><span class="sxs-lookup"><span data-stu-id="eaf09-108">The following example uses a <xref:System.Windows.Controls.MediaElement> and a <xref:System.Windows.Media.VisualBrush> to paint the <xref:System.Windows.Controls.TextBlock.Foreground%2A> of a <xref:System.Windows.Controls.TextBlock> control with video.</span></span> <span data-ttu-id="eaf09-109">In diesem Beispiel wird die <xref:System.Windows.Controls.MediaElement.IsMuted%2A> Eigenschaft von der <xref:System.Windows.Controls.MediaElement> auf `true` , damit es kein Sound erzeugt.</span><span class="sxs-lookup"><span data-stu-id="eaf09-109">This example sets the <xref:System.Windows.Controls.MediaElement.IsMuted%2A> property of the <xref:System.Windows.Controls.MediaElement> to `true` so that it produces no sound.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a><span data-ttu-id="eaf09-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eaf09-110">Example</span></span>  
 <span data-ttu-id="eaf09-111">Da <xref:System.Windows.Media.VisualBrush> erbt von der <xref:System.Windows.Media.TileBrush> -Klasse stellt verschiedene Modi für Tiling bereit.</span><span class="sxs-lookup"><span data-stu-id="eaf09-111">Because <xref:System.Windows.Media.VisualBrush> inherits from the <xref:System.Windows.Media.TileBrush> class, it provides several tiling modes.</span></span> <span data-ttu-id="eaf09-112">Durch Festlegen der <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaft eine <xref:System.Windows.Media.VisualBrush> auf <xref:System.Windows.Media.TileMode.Tile> festlegen und die <xref:System.Windows.Media.TileBrush.Viewport%2A> -Eigenschaft auf einen Wert kleiner als der Bereich, der zu zeichnenden sind, können Sie ein gekacheltes Muster erstellen.</span><span class="sxs-lookup"><span data-stu-id="eaf09-112">By setting the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.VisualBrush> to <xref:System.Windows.Media.TileMode.Tile> and by setting its <xref:System.Windows.Media.TileBrush.Viewport%2A> property to a value smaller than the area that you are painting, you can create a tiled pattern.</span></span>  
  
 <span data-ttu-id="eaf09-113">Im folgende Beispiel ist identisch mit dem vorherigen Beispiel, außer dass die <xref:System.Windows.Media.VisualBrush> ein Muster aus dem Video generiert.</span><span class="sxs-lookup"><span data-stu-id="eaf09-113">The following example is identical to the previous example, except that the <xref:System.Windows.Media.VisualBrush> generates a pattern from the video.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 <span data-ttu-id="eaf09-114">Informationen zur Vorgehensweise beim Hinzufügen einer Inhaltsdatei ein, z. B. eine Mediendatei an Ihre Anwendung finden Sie unter [Anwendungsressource WPF-Inhalt und Datendateien](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).</span><span class="sxs-lookup"><span data-stu-id="eaf09-114">For information about how to add a content file, such as a media file, to your application, see [WPF Application Resource, Content, and Data Files](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).</span></span> <span data-ttu-id="eaf09-115">Wenn Sie eine Mediendatei hinzufügen, müssen Sie es als eine Datei mit Inhalt und nicht als eine Ressourcendatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="eaf09-115">When you add a media file, you must add it as a content file, not as a resource file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaf09-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eaf09-116">See Also</span></span>  
 <xref:System.Windows.Media.VisualBrush>  
 [<span data-ttu-id="eaf09-117">Zeichnen mit Bildern, Zeichnungen und visuellen Elementen</span><span class="sxs-lookup"><span data-stu-id="eaf09-117">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [<span data-ttu-id="eaf09-118">Übersicht über TileBrush</span><span class="sxs-lookup"><span data-stu-id="eaf09-118">TileBrush Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)  
 [<span data-ttu-id="eaf09-119">Übersicht über Multimedia</span><span class="sxs-lookup"><span data-stu-id="eaf09-119">Multimedia Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md)
