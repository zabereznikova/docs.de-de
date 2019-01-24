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
ms.openlocfilehash: 79f427198be370d9cb48cab429906202a62bb72d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647574"
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a>Vorgehensweise: Verbessern der Renderingleistung durch Zwischenspeichern eines Elements
Verwenden der <xref:System.Windows.Media.BitmapCache> Klasse zur Verbesserung der Leistung beim Rendern eines komplexen <xref:System.Windows.UIElement>. Erstellen Sie eine neue Instanz der zum Zwischenspeichern eines Elements, das <xref:System.Windows.Media.BitmapCache> -Klasse und weisen sie auf des Elements des <xref:System.Windows.UIElement.CacheMode%2A> Eigenschaft. Sie können Wiederverwenden einer <xref:System.Windows.Media.BitmapCache> effizient in eine <xref:System.Windows.Media.BitmapCacheBrush>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie die Erstellen eines komplexen Elements als eine Bitmap, die Leistung wird verbessert, wenn das Element animiert wird zwischengespeichert wird. Das Element ist eine Leinwand, die Shape-Geometrien mit viele Scheitelpunkte enthält. Ein <xref:System.Windows.Media.BitmapCache> mit standardmäßigen Werte zugewiesen ist, um die <xref:System.Windows.UIElement.CacheMode%2A> neben dem experimentbereich und einer Animation wird veranschaulicht, die smooth Skalierung der zwischengespeicherten Bitmap.  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [Vorgehensweise: Verwenden eines zwischengespeicherten Elements als Pinsel](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)
