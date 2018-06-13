---
title: 'Gewusst wie: Verbessern der Renderingleistung durch Zwischenspeichern eines Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
ms.openlocfilehash: a92909c623db0c10e3434677b4275fa82b787fa7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559297"
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a>Gewusst wie: Verbessern der Renderingleistung durch Zwischenspeichern eines Elements
Verwenden der <xref:System.Windows.Media.BitmapCache> Klasse zur Verbesserung der Leistung beim Rendern eines komplexen <xref:System.Windows.UIElement>. Um ein Element zu zwischenzuspeichern, erstellen Sie eine neue Instanz der dem <xref:System.Windows.Media.BitmapCache> -Klasse und weisen sie auf des Elements <xref:System.Windows.UIElement.CacheMode%2A> Eigenschaft. Sie können Wiederverwenden einer <xref:System.Windows.Media.BitmapCache> effizient in ein <xref:System.Windows.Media.BitmapCacheBrush>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, erstellen ein komplexes Element, und speichert sie als eine Bitmap, die Leistung verbessert, wenn das Element animiert wird zwischen. Das Element ist ein Zeichenbereich, der Shape-Geometrien mit viele Scheitelpunkte enthält. Ein <xref:System.Windows.Media.BitmapCache> Standardwert Werte zugewiesen ist die <xref:System.Windows.UIElement.CacheMode%2A> des Zeichenbereichs, und eine Animation gezeigt, die smooth Skalierung des zwischengespeicherten Bitmaps.  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [Gewusst wie: Verwenden eines zwischengespeicherten Elements als Pinsel](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)
