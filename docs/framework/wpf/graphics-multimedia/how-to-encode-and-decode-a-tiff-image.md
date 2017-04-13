---
title: "Gewusst wie: Codieren und Decodieren eines TIFF-Bilds | Microsoft Docs"
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
  - "Decodieren von TIFF-Bildern"
  - "Codieren von Bildformaten"
  - "Codieren von TIFF-Bildern"
  - "TIFF-Decodierung"
  - "TIFF-Codierung"
ms.assetid: 1dfe3209-fc73-40e6-ad1c-71c1c58b3364
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Codieren und Decodieren eines TIFF-Bilds
In den folgenden Beispielen wird gezeigt, wie Sie ein [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)]\-Bild mithilfe der spezifischen <xref:System.Windows.Media.Imaging.TiffBitmapDecoder>\- und <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>\-Objekte decodieren und codieren.  
  
## Beispiel  
 Dieses Beispiel zeigt, wie Sie ein [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)]\-Bild mit einem <xref:System.Windows.Media.Imaging.TiffBitmapDecoder>\-Objekt aus einem <xref:System.Uri>\-Objekt decodieren.  
  
 [!code-cpp[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#1)]
 [!code-csharp[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#1)]
 [!code-vb[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#1)]  
  
## Beispiel  
 Dieses Beispiel zeigt, wie Sie eine <xref:System.Windows.Media.Imaging.BitmapSource> mit einem <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> in ein [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)]\-Bild codieren.  
  
 [!code-cpp[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#4)]
 [!code-csharp[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#4)]
 [!code-vb[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#4)]  
  
## Siehe auch  
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)