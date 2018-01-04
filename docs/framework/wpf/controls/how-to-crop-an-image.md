---
title: 'Gewusst wie: Zuschneiden eines Bilds'
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
helpviewer_keywords:
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 084e3dc7fad2bcb3b7ab787302f55c824ff3739d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-crop-an-image"></a><span data-ttu-id="17576-102">Gewusst wie: Zuschneiden eines Bilds</span><span class="sxs-lookup"><span data-stu-id="17576-102">How to: Crop an Image</span></span>
<span data-ttu-id="17576-103">In diesem Beispiel wird gezeigt, wie ein Bild mit einzubeziehende <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span><span class="sxs-lookup"><span data-stu-id="17576-103">This example shows how to crop an image using <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span></span>  
  
 <span data-ttu-id="17576-104"><xref:System.Windows.Media.Imaging.CroppedBitmap>wird in erster Linie verwendet, wenn eine zugeschnittene Version eines Bilds Codierung out in eine Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="17576-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> is primarily used when encoding a cropped version of an image to save out to a file.</span></span> <span data-ttu-id="17576-105">Zum Zuschneiden eines Bilds zu Anzeigezwecken finden Sie die [Erstellen eines Clippingbereichs](http://msdn.microsoft.com/en-us/56e4bed6-78d7-4292-b917-d72d0b3e4376) Thema.</span><span class="sxs-lookup"><span data-stu-id="17576-105">To crop an image for display purposes see the [Create a Clip Region](http://msdn.microsoft.com/en-us/56e4bed6-78d7-4292-b917-d72d0b3e4376) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17576-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="17576-106">Example</span></span>  
 <span data-ttu-id="17576-107">Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Ressourcen in den Beispielen unten definiert.</span><span class="sxs-lookup"><span data-stu-id="17576-107">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] defines resources used within the samples below.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 <span data-ttu-id="17576-108">Das folgende Beispiel erstellt ein Abbild mithilfe einer <xref:System.Windows.Media.Imaging.CroppedBitmap> als Quelle.</span><span class="sxs-lookup"><span data-stu-id="17576-108">The following example creates an image using a <xref:System.Windows.Media.Imaging.CroppedBitmap> as its source.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 <span data-ttu-id="17576-109">Die <xref:System.Windows.Media.Imaging.CroppedBitmap> kann auch verwendet werden, als Quelle eines anderen <xref:System.Windows.Media.Imaging.CroppedBitmap>, das Zuschneiden zu verketten.</span><span class="sxs-lookup"><span data-stu-id="17576-109">The <xref:System.Windows.Media.Imaging.CroppedBitmap> can also be used as the source of another <xref:System.Windows.Media.Imaging.CroppedBitmap>, chaining the cropping.</span></span> <span data-ttu-id="17576-110">Beachten Sie, dass die <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> werden verwendet, die relativ zu der Quelle, die mithilfe einer Bitmap und nicht das erste Bild zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="17576-110">Note that the <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> uses values that are relative to the source cropped bitmap and not the initial image.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a><span data-ttu-id="17576-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17576-111">See Also</span></span>  
 [<span data-ttu-id="17576-112">Erstellen eines Clippingbereichs</span><span class="sxs-lookup"><span data-stu-id="17576-112">Create a Clip Region</span></span>](http://msdn.microsoft.com/en-us/56e4bed6-78d7-4292-b917-d72d0b3e4376)
