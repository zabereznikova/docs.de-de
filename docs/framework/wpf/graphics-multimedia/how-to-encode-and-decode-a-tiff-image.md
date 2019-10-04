---
title: 'Vorgehensweise: Codieren und Decodieren eines TIFF-Bilds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TIFF encoding [WPF]
- encoding TIFF images [WPF]
- encoding image formats [WPF]
- decoding TIFF images [WPF]
- decoding image formats [WPF]
- TIFF decoding [WPF]
ms.assetid: 1dfe3209-fc73-40e6-ad1c-71c1c58b3364
ms.openlocfilehash: 173a30e785b16a3617b82b771c463083356d6e6e
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835290"
---
# <a name="how-to-encode-and-decode-a-tiff-image"></a>Vorgehensweise: Codieren und Decodieren eines TIFF-Bilds
In den folgenden Beispielen wird veranschaulicht, wie Sie ein Tagged Image File Format-Image (TIFF) mithilfe der spezifischen <xref:System.Windows.Media.Imaging.TiffBitmapDecoder>-und <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>-Objekte decodieren und codieren.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird veranschaulicht, wie ein TIFF-Bild mit einem <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> aus einem <xref:System.Uri> decodiert wird.  
  
 [!code-cpp[TiffBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#1)]
 [!code-csharp[TiffBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#1)]
 [!code-vb[TiffBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#1)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Media.Imaging.BitmapSource> in einem TIFF-Bild mit einem <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> codiert wird.  
  
 [!code-cpp[TiffBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#4)]
 [!code-csharp[TiffBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#4)]
 [!code-vb[TiffBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Bildverarbeitung](imaging-overview.md)
