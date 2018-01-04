---
title: 'Gewusst wie: Codieren und Decodieren eines PNG-Bilds'
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
- PNG encoding [WPF]
- decoding PNG images [WPF]
- PNG decoding [WPF]
- encoding image formats [WPF]
- decoding image formats [WPF]
- encoding PNG images [WPF]
ms.assetid: 3d31d186-af73-47f0-b5a7-c26ae46409a6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0fa304515e508fab246a6946c5a8026369cda250
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-encode-and-decode-a-png-image"></a><span data-ttu-id="f35ec-102">Gewusst wie: Codieren und Decodieren eines PNG-Bilds</span><span class="sxs-lookup"><span data-stu-id="f35ec-102">How to: Encode and Decode a PNG Image</span></span>
<span data-ttu-id="f35ec-103">Die folgenden Beispiele zeigen, wie Sie decodieren und Codieren einer [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] -Bild mithilfe der spezifischen <xref:System.Windows.Media.Imaging.PngBitmapDecoder> und <xref:System.Windows.Media.Imaging.PngBitmapEncoder> Objekte.</span><span class="sxs-lookup"><span data-stu-id="f35ec-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] image using the specific <xref:System.Windows.Media.Imaging.PngBitmapDecoder> and <xref:System.Windows.Media.Imaging.PngBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f35ec-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35ec-104">Example</span></span>  
 <span data-ttu-id="f35ec-105">In diesem Beispiel wird veranschaulicht, wie die zu decodierende eine [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] image mit einer <xref:System.Windows.Media.Imaging.PngBitmapDecoder> aus einer <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="f35ec-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] image using a <xref:System.Windows.Media.Imaging.PngBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[PngBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#1)]
 [!code-csharp[PngBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#1)]
 [!code-vb[PngBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="f35ec-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35ec-106">Example</span></span>  
 <span data-ttu-id="f35ec-107">In diesem Beispiel wird veranschaulicht, wie zum Codieren einer <xref:System.Windows.Media.Imaging.BitmapSource> in eine [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] image mit einer <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="f35ec-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] image using a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
 [!code-cpp[PngBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#4)]
 [!code-csharp[PngBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#4)]
 [!code-vb[PngBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="f35ec-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f35ec-108">See Also</span></span>  
 [<span data-ttu-id="f35ec-109">Übersicht über die Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="f35ec-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
