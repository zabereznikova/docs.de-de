---
title: 'Vorgehensweise: Codieren und Decodieren eines GIF-Bilds'
ms.date: 03/30/2017
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
ms.openlocfilehash: 245cc2db2c3cd0187c17bc992343eb8ab30da2ea
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353412"
---
# <a name="how-to-encode-and-decode-a-gif-image"></a><span data-ttu-id="fb084-102">Vorgehensweise: Codieren und Decodieren eines GIF-Bilds</span><span class="sxs-lookup"><span data-stu-id="fb084-102">How to: Encode and Decode a GIF Image</span></span>
<span data-ttu-id="fb084-103">Die folgenden Beispiele zeigen, wie Sie decodieren und Codieren einer [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] -Bild mithilfe der spezifischen <xref:System.Windows.Media.Imaging.GifBitmapDecoder> und <xref:System.Windows.Media.Imaging.GifBitmapEncoder> Objekte.</span><span class="sxs-lookup"><span data-stu-id="fb084-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] image using the specific <xref:System.Windows.Media.Imaging.GifBitmapDecoder> and <xref:System.Windows.Media.Imaging.GifBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb084-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fb084-104">Example</span></span>  
 <span data-ttu-id="fb084-105">In diesem Beispiel wird veranschaulicht, wie zum Decodieren einer [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] -Bild mithilfe einer <xref:System.Windows.Media.Imaging.GifBitmapDecoder> aus einer <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="fb084-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] image using a <xref:System.Windows.Media.Imaging.GifBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="fb084-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fb084-106">Example</span></span>  
 <span data-ttu-id="fb084-107">In diesem Beispiel wird veranschaulicht, wie zum Codieren einer <xref:System.Windows.Media.Imaging.BitmapSource> in einer [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] -Bild mithilfe einer <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="fb084-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] image using a <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="fb084-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb084-108">See also</span></span>
- [<span data-ttu-id="fb084-109">Übersicht über die Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="fb084-109">Imaging Overview</span></span>](imaging-overview.md)
