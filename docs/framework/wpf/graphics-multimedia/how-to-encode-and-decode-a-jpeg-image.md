---
title: 'Vorgehensweise: Codieren und Decodieren ein JPEG-Bilds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding image formats [WPF]
- decoding JPEG images [WPF]
- encoding JPEG images [WPF]
- decoding image formats [WPF]
- JPEG decoding [WPF]
- JPEG encoding [WPF]
ms.assetid: b8cfde37-9f68-4911-a05e-51d8d7bdec7b
ms.openlocfilehash: 916eab63938100daf91e6c1a5af31648a99108d0
ms.sourcegitcommit: f9e38d31288fe5962e6be5b0cc286da633482873
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37027966"
---
# <a name="how-to-encode-and-decode-a-jpeg-image"></a><span data-ttu-id="6b39a-102">Vorgehensweise: Codieren und Decodieren ein JPEG-Bilds</span><span class="sxs-lookup"><span data-stu-id="6b39a-102">How to: Encode and decode a JPEG image</span></span>

<span data-ttu-id="6b39a-103">Die folgenden Beispiele zeigen, wie Sie decodieren und Codieren eines JPEG-Bilds, indem der spezifische <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> und <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> Objekte.</span><span class="sxs-lookup"><span data-stu-id="6b39a-103">The following examples show how to decode and encode a JPEG image using the specific <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> and <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> objects.</span></span>  
  
## <a name="example---decode-a-jpeg-image"></a><span data-ttu-id="6b39a-104">Beispiel: Decodieren eines JPEG-Bilds</span><span class="sxs-lookup"><span data-stu-id="6b39a-104">Example - Decode a JPEG image</span></span>

<span data-ttu-id="6b39a-105">In diesem Beispiel wird veranschaulicht, wie eine JPEG-Bild mit decodieren eine <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> aus einem <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="6b39a-105">This example demonstrates how to decode a JPEG image using a <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
[!code-cpp[JpegBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#1)]
[!code-csharp[JpegBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#1)]
[!code-vb[JpegBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#1)]  
  
## <a name="example---encode-a-jpeg-image"></a><span data-ttu-id="6b39a-106">Beispiel: Codieren ein JPEG-Bilds</span><span class="sxs-lookup"><span data-stu-id="6b39a-106">Example - Encode a JPEG image</span></span>

<span data-ttu-id="6b39a-107">In diesem Beispiel wird veranschaulicht, wie zum Codieren einer <xref:System.Windows.Media.Imaging.BitmapSource> in das JPEG-Format image mit einer <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="6b39a-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a JPEG image using a <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>.</span></span>  
  
[!code-cpp[JpegBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#4)]
[!code-csharp[JpegBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#4)]
[!code-vb[JpegBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="6b39a-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b39a-108">See also</span></span>

[<span data-ttu-id="6b39a-109">Übersicht über die Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="6b39a-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)