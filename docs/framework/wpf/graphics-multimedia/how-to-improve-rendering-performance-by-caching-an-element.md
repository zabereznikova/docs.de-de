---
title: 'Gewusst wie: Verbessern der Renderingleistung durch Zwischenspeichern eines Elements'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9cd12b811ae4dd89c645ada1f4f70b06f73b9b13
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a><span data-ttu-id="69212-102">Gewusst wie: Verbessern der Renderingleistung durch Zwischenspeichern eines Elements</span><span class="sxs-lookup"><span data-stu-id="69212-102">How to: Improve Rendering Performance by Caching an Element</span></span>
<span data-ttu-id="69212-103">Verwenden der <xref:System.Windows.Media.BitmapCache> Klasse zur Verbesserung der Leistung beim Rendern eines komplexen <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="69212-103">Use the <xref:System.Windows.Media.BitmapCache> class to improve rendering performance of a complex <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="69212-104">Um ein Element zu zwischenzuspeichern, erstellen Sie eine neue Instanz der dem <xref:System.Windows.Media.BitmapCache> -Klasse und weisen sie auf des Elements <xref:System.Windows.UIElement.CacheMode%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="69212-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span> <span data-ttu-id="69212-105">Sie können Wiederverwenden einer <xref:System.Windows.Media.BitmapCache> effizient in ein <xref:System.Windows.Media.BitmapCacheBrush>.</span><span class="sxs-lookup"><span data-stu-id="69212-105">You can reuse a <xref:System.Windows.Media.BitmapCache> efficiently in a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69212-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="69212-106">Example</span></span>  
 <span data-ttu-id="69212-107">Im folgenden Codebeispiel wird veranschaulicht, erstellen ein komplexes Element, und speichert sie als eine Bitmap, die Leistung verbessert, wenn das Element animiert wird zwischen.</span><span class="sxs-lookup"><span data-stu-id="69212-107">The following code example shows how to create a complex element and cache it as a bitmap, which improves performance when the element is animated.</span></span> <span data-ttu-id="69212-108">Das Element ist ein Zeichenbereich, der Shape-Geometrien mit viele Scheitelpunkte enthält.</span><span class="sxs-lookup"><span data-stu-id="69212-108">The element is a canvas that holds shape geometries with many vertices.</span></span> <span data-ttu-id="69212-109">Ein <xref:System.Windows.Media.BitmapCache> Standardwert Werte zugewiesen ist die <xref:System.Windows.UIElement.CacheMode%2A> des Zeichenbereichs, und eine Animation gezeigt, die smooth Skalierung des zwischengespeicherten Bitmaps.</span><span class="sxs-lookup"><span data-stu-id="69212-109">A <xref:System.Windows.Media.BitmapCache> with default values is assigned to the <xref:System.Windows.UIElement.CacheMode%2A> of the canvas, and an animation shows the smooth scaling of the cached bitmap.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a><span data-ttu-id="69212-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69212-110">See Also</span></span>  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [<span data-ttu-id="69212-111">Gewusst wie: Verwenden eines zwischengespeicherten Elements als Pinsel</span><span class="sxs-lookup"><span data-stu-id="69212-111">How to: Use a Cached Element as a Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)
