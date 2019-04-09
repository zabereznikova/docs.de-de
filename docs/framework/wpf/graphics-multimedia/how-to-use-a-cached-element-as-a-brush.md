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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229367"
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a>Vorgehensweise: Verwenden eines zwischengespeicherten Elements als Pinsel
Verwenden der <xref:System.Windows.Media.BitmapCacheBrush> Klasse, um ein zwischengespeichertes Element so effizient wie möglich erneut zu verwenden. Erstellen Sie eine neue Instanz der zum Zwischenspeichern eines Elements, das <xref:System.Windows.Media.BitmapCache> -Klasse und weisen sie auf des Elements des <xref:System.Windows.UIElement.CacheMode%2A> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Wiederverwenden eines zwischengespeicherten Elements wird. Das zwischengespeicherte Element wird ein <xref:System.Windows.Controls.Image> Steuerelement, das ein großes Bild anzeigt. Die <xref:System.Windows.Controls.Image> Steuerelement wird als Bitmap zwischengespeichert, mit der <xref:System.Windows.Media.BitmapCache> -Klasse, und der Cache wird wiederverwendet, indem Sie die Zuweisung zu einem <xref:System.Windows.Media.BitmapCacheBrush>. Der Pinsel wird in den Hintergrund der Uhr fünfundzwanzig Schaltflächen zugewiesen, um effiziente Wiederverwendung anzuzeigen.  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [Vorgehensweise: Verbessern der Renderingleistung durch Zwischenspeichern eines Elements](how-to-improve-rendering-performance-by-caching-an-element.md)
