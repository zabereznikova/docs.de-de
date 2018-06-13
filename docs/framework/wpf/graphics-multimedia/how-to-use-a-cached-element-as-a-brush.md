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
# <a name="how-to-use-a-cached-element-as-a-brush"></a>Gewusst wie: Verwenden eines zwischengespeicherten Elements als Pinsel
Verwenden der <xref:System.Windows.Media.BitmapCacheBrush> -Klasse zum effizienten Wiederverwenden eines zwischengespeichertes Elements. Um ein Element zu zwischenzuspeichern, erstellen Sie eine neue Instanz der dem <xref:System.Windows.Media.BitmapCache> -Klasse und weisen sie auf des Elements <xref:System.Windows.UIElement.CacheMode%2A> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Wiederverwenden eines zwischengespeicherten Elements. Das zwischengespeicherte Element wird ein <xref:System.Windows.Controls.Image> Steuerelement, das ein großes Bild anzeigt. Die <xref:System.Windows.Controls.Image> Steuerelement wird als Bitmap zwischengespeichert, mit der <xref:System.Windows.Media.BitmapCache> -Klasse, und der Cache wird wiederverwendet, indem Sie die Zuweisung zu einem <xref:System.Windows.Media.BitmapCacheBrush>. Der Pinsel wird dem Hintergrund eines fünfundzwanzig Schaltflächen anzuzeigende effiziente Wiederverwendung zugewiesen.  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [Gewusst wie: Verbessern der Renderingleistung durch Zwischenspeichern eines Elements](../../../../docs/framework/wpf/graphics-multimedia/how-to-improve-rendering-performance-by-caching-an-element.md)
