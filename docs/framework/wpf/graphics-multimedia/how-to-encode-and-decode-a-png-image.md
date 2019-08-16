---
title: 'Vorgehensweise: Codieren und Decodieren eines PNG-Bilds'
ms.date: 03/30/2017
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
ms.openlocfilehash: 0a0a2f2625901f7ee32ba9fe70e71681a1b9ccd3
ms.sourcegitcommit: 43761fcee10aeefcf851ea81cea3f3c691420856
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2019
ms.locfileid: "69545277"
---
# <a name="how-to-encode-and-decode-a-png-image"></a><span data-ttu-id="e8ad2-102">Vorgehensweise: Codieren und Decodieren eines PNG-Bilds</span><span class="sxs-lookup"><span data-stu-id="e8ad2-102">How to: Encode and Decode a PNG Image</span></span>
<span data-ttu-id="e8ad2-103">In den folgenden Beispielen wird veranschaulicht, wie Sie ein Portable Network Graphics-Image (PNG) mithilfe der spezifischen <xref:System.Windows.Media.Imaging.PngBitmapDecoder> -und- <xref:System.Windows.Media.Imaging.PngBitmapEncoder> Objekte decodieren und codieren.</span><span class="sxs-lookup"><span data-stu-id="e8ad2-103">The following examples show how to decode and encode a Portable Network Graphics (PNG) image using the specific <xref:System.Windows.Media.Imaging.PngBitmapDecoder> and <xref:System.Windows.Media.Imaging.PngBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8ad2-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e8ad2-104">Example</span></span>  
 <span data-ttu-id="e8ad2-105">In diesem Beispiel wird veranschaulicht, wie ein PNG-Bild mit <xref:System.Windows.Media.Imaging.PngBitmapDecoder> einem aus <xref:System.IO.FileStream>einem decodiert wird.</span><span class="sxs-lookup"><span data-stu-id="e8ad2-105">This example demonstrates how to decode a PNG image using a <xref:System.Windows.Media.Imaging.PngBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[PngBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#1)]
 [!code-csharp[PngBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#1)]
 [!code-vb[PngBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="e8ad2-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e8ad2-106">Example</span></span>  
 <span data-ttu-id="e8ad2-107">In diesem Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Media.Imaging.BitmapSource> mit einem <xref:System.Windows.Media.Imaging.PngBitmapEncoder>in ein PNG-Bild codiert wird.</span><span class="sxs-lookup"><span data-stu-id="e8ad2-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a PNG image using a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
 [!code-cpp[PngBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#4)]
 [!code-csharp[PngBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#4)]
 [!code-vb[PngBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="e8ad2-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8ad2-108">See also</span></span>

- [<span data-ttu-id="e8ad2-109">Übersicht über die Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="e8ad2-109">Imaging Overview</span></span>](imaging-overview.md)
