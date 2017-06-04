---
title: "Gewusst wie: Verwenden eines zwischengespeicherten Elements als Pinsel | Microsoft Docs"
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
  - "BitmapCache [WPF], Verwenden"
  - "BitmapCacheBrush [WPF], Verwenden"
  - "Zwischengespeichertes Element [WPF], Als Pinsel verwenden"
  - "CacheMode [WPF], Verwenden"
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Verwenden eines zwischengespeicherten Elements als Pinsel
Verwenden Sie zum effizienten Wiederverwenden eines zwischengespeicherten Elements die <xref:System.Windows.Media.BitmapCacheBrush>\-Klasse.  Erstellen Sie zum Zwischenspeichern eines Elements eine neue Instanz der <xref:System.Windows.Media.BitmapCache>\-Klasse, und weisen Sie sie der <xref:System.Windows.UIElement.CacheMode%2A>\-Eigenschaft des Elements zu.  
  
## Beispiel  
 Im folgenden Codebeispiel wird die Wiederverwendung eines zwischengespeicherten Element veranschaulicht.  Bei diesem zwischengespeicherten Element handelt es sich um ein <xref:System.Windows.Controls.Image>\-Steuerelement, von dem ein großes Bild angezeigt wird.  Das <xref:System.Windows.Controls.Image>\-Steuerelement wird mithilfe der <xref:System.Windows.Media.BitmapCache>\-Klasse als Bitmap zwischengespeichert, und der Cache wird wiederverwendet, indem er einem <xref:System.Windows.Media.BitmapCacheBrush> zugewiesen wird.  Der Pinsel wird dem Hintergrund von fünfundzwanzig Schaltflächen zugewiesen, um die effiziente Wiederverwendung zu verdeutlichen.  
  
 [!code-xml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## Siehe auch  
 <xref:System.Windows.Media.BitmapCache>   
 <xref:System.Windows.Media.BitmapCacheBrush>   
 <xref:System.Windows.UIElement.CacheMode%2A>   
 [Gewusst wie: Verbessern der Renderingleistung durch Zwischenspeichern eines Elements](../../../../docs/framework/wpf/graphics-multimedia/how-to-improve-rendering-performance-by-caching-an-element.md)