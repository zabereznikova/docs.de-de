---
title: 'Vorgehensweise: Zuschneiden eines Bilds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
ms.openlocfilehash: f4c1a735ac102b3f6d81b5253bc15a5d1893075c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366802"
---
# <a name="how-to-crop-an-image"></a><span data-ttu-id="bf410-102">Vorgehensweise: Zuschneiden eines Bilds</span><span class="sxs-lookup"><span data-stu-id="bf410-102">How to: Crop an Image</span></span>
<span data-ttu-id="bf410-103">Dieses Beispiel zeigt, wie Sie ein Bild mit Zuschneiden <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span><span class="sxs-lookup"><span data-stu-id="bf410-103">This example shows how to crop an image using <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span></span>  
  
 <span data-ttu-id="bf410-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> Bei der Codierung einer zugeschnittenen Version eines Bilds wird in erster Linie, die sich in einer Datei speichern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bf410-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> is primarily used when encoding a cropped version of an image to save out to a file.</span></span> <span data-ttu-id="bf410-105">Zum Zuschneiden eines Bilds zu Anzeigezwecken finden Sie die [Vorgehensweise: Erstellen Sie einen Clip-Bereich](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90)) Thema.</span><span class="sxs-lookup"><span data-stu-id="bf410-105">To crop an image for display purposes see the [How to: Create a Clip Region](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90)) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf410-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf410-106">Example</span></span>  
 <span data-ttu-id="bf410-107">Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] definiert Ressourcen, die in den folgenden Beispielen verwendet.</span><span class="sxs-lookup"><span data-stu-id="bf410-107">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] defines resources used within the samples below.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 <span data-ttu-id="bf410-108">Das folgende Beispiel erstellt ein Image mit einem <xref:System.Windows.Media.Imaging.CroppedBitmap> als Quelle.</span><span class="sxs-lookup"><span data-stu-id="bf410-108">The following example creates an image using a <xref:System.Windows.Media.Imaging.CroppedBitmap> as its source.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 <span data-ttu-id="bf410-109">Die <xref:System.Windows.Media.Imaging.CroppedBitmap> kann auch verwendet werden, als Quelle eines anderen <xref:System.Windows.Media.Imaging.CroppedBitmap>, das Zuschneiden zu verketten.</span><span class="sxs-lookup"><span data-stu-id="bf410-109">The <xref:System.Windows.Media.Imaging.CroppedBitmap> can also be used as the source of another <xref:System.Windows.Media.Imaging.CroppedBitmap>, chaining the cropping.</span></span> <span data-ttu-id="bf410-110">Beachten Sie, dass die <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> verwendet Werte, die relativ zum zugeschnittenen Bitmap und nicht das erste Bild sind.</span><span class="sxs-lookup"><span data-stu-id="bf410-110">Note that the <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> uses values that are relative to the source cropped bitmap and not the initial image.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a><span data-ttu-id="bf410-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf410-111">See also</span></span>
- <span data-ttu-id="bf410-112">[Vorgehensweise: Erstellen Sie einen Clip-Bereich](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="bf410-112">[How to: Create a Clip Region](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90))</span></span>
