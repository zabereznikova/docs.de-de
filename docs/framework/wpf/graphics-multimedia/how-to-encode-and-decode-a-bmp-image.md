---
title: "Gewusst wie: Codieren und Decodieren eines BMP-Bilds | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "BMP-Decodierung"
  - "BMP-Codierung"
  - "Decodieren von BMP-Bildern"
  - "Decodieren von Bildformaten"
  - "Codieren von BMP-Bildern"
  - "Codieren von Bildformaten"
ms.assetid: feb5ef27-28ac-40ab-bfc2-e0456990d32c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Codieren und Decodieren eines BMP-Bilds
In den folgenden Beispielen wird gezeigt, wie Sie ein [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)]\-Bild mithilfe der spezifischen <xref:System.Windows.Media.Imaging.BmpBitmapDecoder>\- und <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>\-Objekte decodieren und codieren.  
  
## Beispiel  
 Dieses Beispiel zeigt, wie Sie ein [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)]\-Bild mit einem <xref:System.Windows.Media.Imaging.BmpBitmapDecoder>\-Objekt aus einem <xref:System.Uri>\-Objekt decodieren.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
## Beispiel  
 Dieses Beispiel zeigt, wie Sie ein <xref:System.Windows.Media.Imaging.BitmapSource> in ein [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)]\-Bild codieren, indem Sie einen <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> verwenden.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#4)]
 [!code-csharp[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#4)]
 [!code-vb[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#4)]  
  
## Siehe auch  
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)