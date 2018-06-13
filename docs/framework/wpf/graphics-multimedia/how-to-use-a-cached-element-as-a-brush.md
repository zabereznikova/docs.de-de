---
title: 'Gewusst wie: Verwenden eines zwischengespeicherten Elements als Pinsel'
ms.date: 03/30/2017
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
ms.openlocfilehash: c43c4ecbefe99d6e38766705378d85d92ecc5729
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561523"
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a><span data-ttu-id="f2794-102">Gewusst wie: Verwenden eines zwischengespeicherten Elements als Pinsel</span><span class="sxs-lookup"><span data-stu-id="f2794-102">How to: Use a Cached Element as a Brush</span></span>
<span data-ttu-id="f2794-103">Verwenden der <xref:System.Windows.Media.BitmapCacheBrush> -Klasse zum effizienten Wiederverwenden eines zwischengespeichertes Elements.</span><span class="sxs-lookup"><span data-stu-id="f2794-103">Use the <xref:System.Windows.Media.BitmapCacheBrush> class to reuse a cached element efficiently.</span></span> <span data-ttu-id="f2794-104">Um ein Element zu zwischenzuspeichern, erstellen Sie eine neue Instanz der dem <xref:System.Windows.Media.BitmapCache> -Klasse und weisen sie auf des Elements <xref:System.Windows.UIElement.CacheMode%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f2794-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2794-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f2794-105">Example</span></span>  
 <span data-ttu-id="f2794-106">Im folgenden Codebeispiel wird veranschaulicht, wie zum Wiederverwenden eines zwischengespeicherten Elements.</span><span class="sxs-lookup"><span data-stu-id="f2794-106">The following code example shows how to reuse a cached element.</span></span> <span data-ttu-id="f2794-107">Das zwischengespeicherte Element wird ein <xref:System.Windows.Controls.Image> Steuerelement, das ein großes Bild anzeigt.</span><span class="sxs-lookup"><span data-stu-id="f2794-107">The cached element is an <xref:System.Windows.Controls.Image> control that displays a large image.</span></span> <span data-ttu-id="f2794-108">Die <xref:System.Windows.Controls.Image> Steuerelement wird als Bitmap zwischengespeichert, mit der <xref:System.Windows.Media.BitmapCache> -Klasse, und der Cache wird wiederverwendet, indem Sie die Zuweisung zu einem <xref:System.Windows.Media.BitmapCacheBrush>.</span><span class="sxs-lookup"><span data-stu-id="f2794-108">The <xref:System.Windows.Controls.Image> control is cached as a bitmap by using the <xref:System.Windows.Media.BitmapCache> class, and the cache is reused by assigning it to a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span> <span data-ttu-id="f2794-109">Der Pinsel wird dem Hintergrund eines fünfundzwanzig Schaltflächen anzuzeigende effiziente Wiederverwendung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f2794-109">The brush is assigned to the background of twenty-five buttons to show efficient reuse.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="f2794-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2794-110">See Also</span></span>  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [<span data-ttu-id="f2794-111">Gewusst wie: Verbessern der Renderingleistung durch Zwischenspeichern eines Elements</span><span class="sxs-lookup"><span data-stu-id="f2794-111">How to: Improve Rendering Performance by Caching an Element</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-improve-rendering-performance-by-caching-an-element.md)
