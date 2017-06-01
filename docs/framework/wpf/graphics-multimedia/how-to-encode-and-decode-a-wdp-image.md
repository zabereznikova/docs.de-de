---
title: "Gewusst wie: Codieren und Decodieren eines WDP-Bilds | Microsoft Docs"
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
  - "Decodieren von WDP-Bildern"
  - "Codieren von Bildformaten"
  - "Codieren von WDP-Bildern"
  - "WDP-Decodierung"
  - "WDP-Codierung"
ms.assetid: 911777d1-516b-49db-a87b-b54e31b18532
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Codieren und Decodieren eines WDP-Bilds
In den folgenden Beispielen wird gezeigt, wie Sie ein [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)]\-Bild mithilfe der spezifischen <xref:System.Windows.Media.Imaging.WmpBitmapDecoder>\- und <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>\-Objekte decodieren und codieren.  
  
## Beispiel  
 Dieses Beispiel zeigt, wie Sie ein [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)]\-Bild mit einem <xref:System.Windows.Media.Imaging.WmpBitmapDecoder>\-Objekt aus einem <xref:System.Uri>\-Objekt decodieren.  
  
 [!code-cpp[WdpBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#1)]
 [!code-csharp[WdpBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#1)]
 [!code-vb[WdpBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#1)]  
  
## Beispiel  
 Dieses Beispiel zeigt, wie Sie eine <xref:System.Windows.Media.Imaging.BitmapSource> in ein [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)]\-Bild codieren, indem Sie einen <xref:System.Windows.Media.Imaging.WmpBitmapEncoder> verwenden.  
  
 [!code-cpp[WdpBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#4)]
 [!code-csharp[WdpBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#4)]
 [!code-vb[WdpBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#4)]  
  
## Siehe auch  
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)