---
title: 'Vorgehensweise: Verwenden eines zwischengespeicherten Elements als Pinsel'
ms.date: 03/30/2017
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
ms.openlocfilehash: 78df242c7f00b69e36ea4ab6751f51509d9e2220
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769251"
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a><span data-ttu-id="01f5f-102">Vorgehensweise: Verwenden eines zwischengespeicherten Elements als Pinsel</span><span class="sxs-lookup"><span data-stu-id="01f5f-102">How to: Use a Cached Element as a Brush</span></span>
<span data-ttu-id="01f5f-103">Verwenden der <xref:System.Windows.Media.BitmapCacheBrush> Klasse, um ein zwischengespeichertes Element so effizient wie möglich erneut zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="01f5f-103">Use the <xref:System.Windows.Media.BitmapCacheBrush> class to reuse a cached element efficiently.</span></span> <span data-ttu-id="01f5f-104">Erstellen Sie eine neue Instanz der zum Zwischenspeichern eines Elements, das <xref:System.Windows.Media.BitmapCache> -Klasse und weisen sie auf des Elements des <xref:System.Windows.UIElement.CacheMode%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="01f5f-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01f5f-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="01f5f-105">Example</span></span>  
 <span data-ttu-id="01f5f-106">Im folgenden Codebeispiel wird veranschaulicht, wie zum Wiederverwenden eines zwischengespeicherten Elements wird.</span><span class="sxs-lookup"><span data-stu-id="01f5f-106">The following code example shows how to reuse a cached element.</span></span> <span data-ttu-id="01f5f-107">Das zwischengespeicherte Element wird ein <xref:System.Windows.Controls.Image> Steuerelement, das ein großes Bild anzeigt.</span><span class="sxs-lookup"><span data-stu-id="01f5f-107">The cached element is an <xref:System.Windows.Controls.Image> control that displays a large image.</span></span> <span data-ttu-id="01f5f-108">Die <xref:System.Windows.Controls.Image> Steuerelement wird als Bitmap zwischengespeichert, mit der <xref:System.Windows.Media.BitmapCache> -Klasse, und der Cache wird wiederverwendet, indem Sie die Zuweisung zu einem <xref:System.Windows.Media.BitmapCacheBrush>.</span><span class="sxs-lookup"><span data-stu-id="01f5f-108">The <xref:System.Windows.Controls.Image> control is cached as a bitmap by using the <xref:System.Windows.Media.BitmapCache> class, and the cache is reused by assigning it to a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span> <span data-ttu-id="01f5f-109">Der Pinsel wird in den Hintergrund der Uhr fünfundzwanzig Schaltflächen zugewiesen, um effiziente Wiederverwendung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="01f5f-109">The brush is assigned to the background of twenty-five buttons to show efficient reuse.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="01f5f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01f5f-110">See also</span></span>

- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [<span data-ttu-id="01f5f-111">Vorgehensweise: Verbessern der Renderingleistung durch Zwischenspeichern eines Elements</span><span class="sxs-lookup"><span data-stu-id="01f5f-111">How to: Improve Rendering Performance by Caching an Element</span></span>](how-to-improve-rendering-performance-by-caching-an-element.md)
