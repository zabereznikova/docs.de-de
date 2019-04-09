---
title: 'Vorgehensweise: Verbessern der Renderingleistung durch Zwischenspeichern eines Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
ms.openlocfilehash: 118e8b0cca52c44788c9d5b291d710f765e7af2a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153373"
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a><span data-ttu-id="3ae65-102">Vorgehensweise: Verbessern der Renderingleistung durch Zwischenspeichern eines Elements</span><span class="sxs-lookup"><span data-stu-id="3ae65-102">How to: Improve Rendering Performance by Caching an Element</span></span>
<span data-ttu-id="3ae65-103">Verwenden der <xref:System.Windows.Media.BitmapCache> Klasse zur Verbesserung der Leistung beim Rendern eines komplexen <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="3ae65-103">Use the <xref:System.Windows.Media.BitmapCache> class to improve rendering performance of a complex <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="3ae65-104">Erstellen Sie eine neue Instanz der zum Zwischenspeichern eines Elements, das <xref:System.Windows.Media.BitmapCache> -Klasse und weisen sie auf des Elements des <xref:System.Windows.UIElement.CacheMode%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3ae65-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span> <span data-ttu-id="3ae65-105">Sie können Wiederverwenden einer <xref:System.Windows.Media.BitmapCache> effizient in eine <xref:System.Windows.Media.BitmapCacheBrush>.</span><span class="sxs-lookup"><span data-stu-id="3ae65-105">You can reuse a <xref:System.Windows.Media.BitmapCache> efficiently in a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ae65-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ae65-106">Example</span></span>  
 <span data-ttu-id="3ae65-107">Im folgenden Codebeispiel wird veranschaulicht, wie die Erstellen eines komplexen Elements als eine Bitmap, die Leistung wird verbessert, wenn das Element animiert wird zwischengespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="3ae65-107">The following code example shows how to create a complex element and cache it as a bitmap, which improves performance when the element is animated.</span></span> <span data-ttu-id="3ae65-108">Das Element ist eine Leinwand, die Shape-Geometrien mit viele Scheitelpunkte enthält.</span><span class="sxs-lookup"><span data-stu-id="3ae65-108">The element is a canvas that holds shape geometries with many vertices.</span></span> <span data-ttu-id="3ae65-109">Ein <xref:System.Windows.Media.BitmapCache> mit standardmäßigen Werte zugewiesen ist, um die <xref:System.Windows.UIElement.CacheMode%2A> neben dem experimentbereich und einer Animation wird veranschaulicht, die smooth Skalierung der zwischengespeicherten Bitmap.</span><span class="sxs-lookup"><span data-stu-id="3ae65-109">A <xref:System.Windows.Media.BitmapCache> with default values is assigned to the <xref:System.Windows.UIElement.CacheMode%2A> of the canvas, and an animation shows the smooth scaling of the cached bitmap.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a><span data-ttu-id="3ae65-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ae65-110">See also</span></span>

- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [<span data-ttu-id="3ae65-111">Vorgehensweise: Verwenden eines zwischengespeicherten Elements als Pinsel</span><span class="sxs-lookup"><span data-stu-id="3ae65-111">How to: Use a Cached Element as a Brush</span></span>](how-to-use-a-cached-element-as-a-brush.md)
