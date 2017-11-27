---
title: 'Gewusst wie: Codieren und Decodieren eines GIF-Bilds'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding GIF images [WPF]
- encoding image formats [WPF]
- decoding GIF images [WPF]
- decoding image formats [WPF]
- GIF decoding [WPF]
- GIF encoding [WPF]
ms.assetid: 9cdd9ec7-71eb-444b-b9e3-991958461163
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f7832e4197ef5c3a764da265a393b654db013876
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-encode-and-decode-a-gif-image"></a>Gewusst wie: Codieren und Decodieren eines GIF-Bilds
Die folgenden Beispiele zeigen, wie Sie decodieren und Codieren einer [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] -Bild mithilfe der spezifischen <xref:System.Windows.Media.Imaging.GifBitmapDecoder> und <xref:System.Windows.Media.Imaging.GifBitmapEncoder> Objekte.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird veranschaulicht, wie die zu decodierende eine [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] image mit einer <xref:System.Windows.Media.Imaging.GifBitmapDecoder> aus einer <xref:System.IO.FileStream>.  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird veranschaulicht, wie zum Codieren einer <xref:System.Windows.Media.Imaging.BitmapSource> in eine [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] image mit einer <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
