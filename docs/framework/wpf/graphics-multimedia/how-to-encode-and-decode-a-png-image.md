---
title: "Gewusst wie: Codieren und Decodieren eines PNG-Bilds | Microsoft Docs"
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
  - "Decodieren von Bildformaten"
  - "Decodieren von PNG-Bildern"
  - "Codieren von Bildformaten"
  - "Codieren von PNG-Bildern"
  - "PNG-Decodierung"
  - "PNG-Codierung"
ms.assetid: 3d31d186-af73-47f0-b5a7-c26ae46409a6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Codieren und Decodieren eines PNG-Bilds
In den folgenden Beispielen wird gezeigt, wie Sie ein [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)]\-Bild mithilfe der spezifischen <xref:System.Windows.Media.Imaging.PngBitmapDecoder>\- und <xref:System.Windows.Media.Imaging.PngBitmapEncoder>\-Objekte decodieren und codieren.  
  
## Beispiel  
 Dieses Beispiel zeigt, wie Sie ein [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)]\-Bild mit einem <xref:System.Windows.Media.Imaging.PngBitmapDecoder>\-Objekt aus einem <xref:System.IO.FileStream>\-Objekt decodieren.  
  
 [!code-cpp[PngBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#1)]
 [!code-csharp[PngBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#1)]
 [!code-vb[PngBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#1)]  
  
## Beispiel  
 Dieses Beispiel zeigt, wie Sie ein <xref:System.Windows.Media.Imaging.BitmapSource> in ein [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)]\-Bild codieren, indem Sie einen <xref:System.Windows.Media.Imaging.PngBitmapEncoder> verwenden.  
  
 [!code-cpp[PngBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#4)]
 [!code-csharp[PngBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#4)]
 [!code-vb[PngBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#4)]  
  
## Siehe auch  
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)