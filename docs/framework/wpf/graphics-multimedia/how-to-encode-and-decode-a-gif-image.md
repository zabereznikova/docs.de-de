---
title: "Gewusst wie: Codieren und Decodieren eines GIF-Bilds | Microsoft Docs"
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
  - "Decodieren von GIF-Bildern"
  - "Decodieren von Bildformaten"
  - "Codieren von GIF-Bildern"
  - "Codieren von Bildformaten"
  - "GIF-Decodierung"
  - "GIF-Codierung"
ms.assetid: 9cdd9ec7-71eb-444b-b9e3-991958461163
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Codieren und Decodieren eines GIF-Bilds
In den folgenden Beispielen wird gezeigt, wie Sie ein [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)]\-Bild mithilfe der spezifischen <xref:System.Windows.Media.Imaging.GifBitmapDecoder>\- und <xref:System.Windows.Media.Imaging.GifBitmapEncoder>\-Objekte decodieren und codieren.  
  
## Beispiel  
 Dieses Beispiel zeigt, wie Sie ein [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)]\-Bild mit einem <xref:System.Windows.Media.Imaging.GifBitmapDecoder>\-Objekt aus einem <xref:System.IO.FileStream>\-Objekt decodieren.  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## Beispiel  
 Dieses Beispiel zeigt, wie Sie eine <xref:System.Windows.Media.Imaging.BitmapSource> in ein [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)]\-Bild codieren, indem Sie einen <xref:System.Windows.Media.Imaging.GifBitmapEncoder> verwenden.  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## Siehe auch  
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)