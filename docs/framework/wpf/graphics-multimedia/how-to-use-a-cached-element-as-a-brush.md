---
title: 'Gewusst wie: Verwenden eines zwischengespeicherten Elements als Pinsel'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4d0f0c60e9df6a1ec816b1f9cf5769c93b382ae5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
