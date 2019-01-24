---
title: 'Vorgehensweise: Codieren und Decodieren eines WDP-Bilds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- WDP encoding [WPF]
- WDP decoding [WPF]
- encoding image formats [WPF]
- decoding WDP images [WPF]
- decoding image formats [WPF]
- encoding WDP images [WPF]
ms.assetid: 911777d1-516b-49db-a87b-b54e31b18532
ms.openlocfilehash: ed30adc668a2ba58544a33b88a89d779bd112921
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723523"
---
# <a name="how-to-encode-and-decode-a-wdp-image"></a>Vorgehensweise: Codieren und Decodieren eines WDP-Bilds
Die folgenden Beispiele zeigen, wie Sie decodieren und Codieren einer [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)] -Bild mithilfe der spezifischen <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> und <xref:System.Windows.Media.Imaging.WmpBitmapEncoder> Objekte.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird veranschaulicht, wie zum Decodieren einer [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] -Bild mithilfe einer <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> aus einer <xref:System.Uri>.  
  
 [!code-cpp[WdpBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#1)]
 [!code-csharp[WdpBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#1)]
 [!code-vb[WdpBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#1)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird veranschaulicht, wie zum Codieren einer <xref:System.Windows.Media.Imaging.BitmapSource> in einer [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] -Bild mithilfe einer <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>.  
  
 [!code-cpp[WdpBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#4)]
 [!code-csharp[WdpBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#4)]
 [!code-vb[WdpBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
