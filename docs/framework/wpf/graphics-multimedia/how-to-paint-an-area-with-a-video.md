---
title: "Gewusst wie: Zeichnen eines Bereichs mit einem Video | Microsoft Docs"
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
  - "Pinsel, Zeichnen mit einem Video"
  - "Zeichnen mit einem Video"
  - "Video, Zeichnen mit"
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Zeichnen eines Bereichs mit einem Video
Dieses Beispiel veranschaulicht, wie ein Bereich mit Medien gezeichnet wird.  Eine Möglichkeit zum Zeichnen eines Bereichs mit Medien besteht darin, <xref:System.Windows.Controls.MediaElement> zusammen mit <xref:System.Windows.Media.VisualBrush> zu verwenden.  Verwenden Sie <xref:System.Windows.Controls.MediaElement> zum Laden und Wiedergeben der Medien, und legen Sie damit anschließend die <xref:System.Windows.Media.VisualBrush.Visual%2A>\-Eigenschaft von <xref:System.Windows.Media.VisualBrush> fest.  Sie können dann <xref:System.Windows.Media.VisualBrush> verwenden, um einen Bereich mit den geladenen Medien zu zeichnen.  
  
## Beispiel  
 Im folgenden Beispiel werden <xref:System.Windows.Controls.MediaElement> und <xref:System.Windows.Media.VisualBrush> verwendet, um den <xref:System.Windows.Controls.TextBlock.Foreground%2A> eines <xref:System.Windows.Controls.TextBlock>\-Steuerelements mit einem Video zu zeichnen.  In diesem Beispiel wird die <xref:System.Windows.Controls.MediaElement.IsMuted%2A>\-Eigenschaft von <xref:System.Windows.Controls.MediaElement> auf `true` festgelegt, damit kein Sound abgespielt wird.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## Beispiel  
 Da <xref:System.Windows.Media.VisualBrush> von der <xref:System.Windows.Media.TileBrush>\-Klasse erbt, sind verschiedene Unterteilungsmodi verfügbar.  Wenn die <xref:System.Windows.Media.TileBrush.TileMode%2A>\-Eigenschaft von <xref:System.Windows.Media.VisualBrush> auf <xref:System.Windows.Media.TileMode> und die <xref:System.Windows.Media.TileBrush.Viewport%2A>\-Eigenschaft auf einen Wert festgelegt wird, der kleiner ist als der zu zeichnende Bereich, können Sie ein gekacheltes Muster erstellen.  
  
 Das folgende Beispiel ist mit dem vorherigen Beispiel identisch, allerdings wird hier von <xref:System.Windows.Media.VisualBrush> ein Muster aus dem Video erstellt.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 Informationen zum Hinzufügen einer Inhaltsdatei zur Anwendung, z. B. einer Mediendatei, finden Sie unter [WPF\-Anwendungsressource, Inhalts\- und Datendateien](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).  Wenn Sie eine Mediendatei hinzufügen, müssen Sie diese als Inhaltsdatei und nicht als Ressourcendatei hinzufügen.  
  
## Siehe auch  
 <xref:System.Windows.Media.VisualBrush>   
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Übersicht über TileBrush](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)   
 [Übersicht über Multimedia](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md)