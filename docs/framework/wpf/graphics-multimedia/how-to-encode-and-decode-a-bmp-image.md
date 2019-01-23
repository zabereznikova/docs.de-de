---
title: 'Vorgehensweise: Codieren und Decodieren eines BMP-Bilds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding BMP images [WPF]
- BMP encoding [WPF]
- decoding BMP images [WPF]
- encoding image formats [WPF]
- BMP decoding [WPF]
- decoding image formats [WPF]
ms.assetid: feb5ef27-28ac-40ab-bfc2-e0456990d32c
ms.openlocfilehash: dfdadfb7175342199099a1549008197b8d42551c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530705"
---
# <a name="how-to-encode-and-decode-a-bmp-image"></a><span data-ttu-id="92667-102">Vorgehensweise: Codieren und Decodieren eines BMP-Bilds</span><span class="sxs-lookup"><span data-stu-id="92667-102">How to: Encode and Decode a BMP Image</span></span>
<span data-ttu-id="92667-103">Die folgenden Beispiele zeigen, wie Sie decodieren und Codieren einer [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)] -Bild mithilfe der spezifischen <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> und <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> Objekte.</span><span class="sxs-lookup"><span data-stu-id="92667-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)] image using the specific <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92667-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="92667-104">Example</span></span>  
 <span data-ttu-id="92667-105">In diesem Beispiel wird veranschaulicht, wie zum Decodieren einer [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] -Bild mithilfe einer <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> aus einer <xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="92667-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] image using a <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="92667-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="92667-106">Example</span></span>  
 <span data-ttu-id="92667-107">In diesem Beispiel wird veranschaulicht, wie zum Codieren einer <xref:System.Windows.Media.Imaging.BitmapSource> in einer [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] -Bild mithilfe einer <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="92667-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] image using a <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#4)]
 [!code-csharp[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#4)]
 [!code-vb[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="92667-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92667-108">See also</span></span>
- [<span data-ttu-id="92667-109">Übersicht über die Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="92667-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
