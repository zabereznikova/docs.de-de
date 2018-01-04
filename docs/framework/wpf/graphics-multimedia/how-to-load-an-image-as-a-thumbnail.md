---
title: 'Gewusst wie: Laden eines Bilds als Miniaturansicht'
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
- loading images as thumbnails [WPF]
- images [WPF], loading as thumbnails
- thumbnails [WPF], loading images as
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e91e032162e6e652daf18268d05c2a7db291bfc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a><span data-ttu-id="60bbb-102">Gewusst wie: Laden eines Bilds als Miniaturansicht</span><span class="sxs-lookup"><span data-stu-id="60bbb-102">How to: Load an Image as a Thumbnail</span></span>
<span data-ttu-id="60bbb-103">Die folgenden Beispiele zeigen, wie beim Laden einer <xref:System.Windows.Controls.Image> als eine Miniaturansicht, um die Anwendung Speicherplatz zu sparen.</span><span class="sxs-lookup"><span data-stu-id="60bbb-103">The following examples show how to load an <xref:System.Windows.Controls.Image> as a thumbnail to conserve application memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60bbb-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60bbb-104">Example</span></span>  
 <span data-ttu-id="60bbb-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> Eigenschaft von einem <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] reduziert den erforderlichen Speicher zum Laden des Bilds.</span><span class="sxs-lookup"><span data-stu-id="60bbb-105">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to reduce the memory required to load the image.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="60bbb-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60bbb-106">Example</span></span>  
 <span data-ttu-id="60bbb-107">Im folgenden Beispiel wird die <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> Eigenschaft eine <xref:System.Windows.Media.Imaging.BitmapImage> im Code, um den erforderlichen Speicher zum Laden des Bilds zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="60bbb-107">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in code to reduce the memory required to load the image.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="60bbb-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60bbb-108">See Also</span></span>  
 [<span data-ttu-id="60bbb-109">Übersicht über die Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="60bbb-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
