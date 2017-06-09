---
title: "Gewusst wie: Verbessern der Renderingleistung durch Zwischenspeichern eines Elements | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "BitmapCache [WPF], Verbessern der Renderingleistung"
  - "CacheMode [WPF], Verbessern der Renderingleistung"
  - "Leistung [WPF], Zwischenspeichern eines Elements"
  - "Renderingleistung [WPF], Zwischenspeichern eines Elements"
  - "UIElement [WPF], Zwischenspeichern"
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Verbessern der Renderingleistung durch Zwischenspeichern eines Elements
Mithilfe der <xref:System.Windows.Media.BitmapCache>\-Klasse kann die Renderingleistung eines komplexen Elements vom Typ <xref:System.Windows.UIElement> verbessert werden.  Erstellen Sie zum Zwischenspeichern eines Elements eine neue Instanz der <xref:System.Windows.Media.BitmapCache>\-Klasse, und weisen Sie sie der <xref:System.Windows.UIElement.CacheMode%2A>\-Eigenschaft des Elements zu.  Ein <xref:System.Windows.Media.BitmapCache> lässt sich effizient in einem <xref:System.Windows.Media.BitmapCacheBrush> wiederverwenden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird das Erstellen eines komplexen Elements und das anschließende Speichern des Elements als Bitmap veranschaulicht. Dadurch verbessert sich die Leistung, wenn das Element animiert wird.  Bei dem Element handelt es sich um ein Canvas, das geometrische Formen mit einer Vielzahl von Eckpunkten enthält.  Dem <xref:System.Windows.UIElement.CacheMode%2A> des Canvas wird ein <xref:System.Windows.Media.BitmapCache> mit Standardwerten zugewiesen, und anhand einer Animation wird die stufenlose Skalierung des zwischengespeicherten Bitmaps veranschaulicht.  
  
 [!code-xml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## Siehe auch  
 <xref:System.Windows.Media.BitmapCache>   
 <xref:System.Windows.Media.BitmapCacheBrush>   
 <xref:System.Windows.UIElement.CacheMode%2A>   
 [Gewusst wie: Verwenden eines zwischengespeicherten Elements als Pinsel](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)