---
title: 'Gewusst wie: Laden eines Bilds als Miniaturansicht'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loading images as thumbnails [WPF]
- images [WPF], loading as thumbnails
- thumbnails [WPF], loading images as
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
ms.openlocfilehash: 349a602a10b89931701e24334bf5ac5536f26400
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562322"
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a><span data-ttu-id="fc8ca-102">Gewusst wie: Laden eines Bilds als Miniaturansicht</span><span class="sxs-lookup"><span data-stu-id="fc8ca-102">How to: Load an Image as a Thumbnail</span></span>
<span data-ttu-id="fc8ca-103">Die folgenden Beispiele zeigen, wie beim Laden einer <xref:System.Windows.Controls.Image> als eine Miniaturansicht, um die Anwendung Speicherplatz zu sparen.</span><span class="sxs-lookup"><span data-stu-id="fc8ca-103">The following examples show how to load an <xref:System.Windows.Controls.Image> as a thumbnail to conserve application memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc8ca-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc8ca-104">Example</span></span>  
 <span data-ttu-id="fc8ca-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> Eigenschaft von einem <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] reduziert den erforderlichen Speicher zum Laden des Bilds.</span><span class="sxs-lookup"><span data-stu-id="fc8ca-105">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to reduce the memory required to load the image.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="fc8ca-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc8ca-106">Example</span></span>  
 <span data-ttu-id="fc8ca-107">Im folgenden Beispiel wird die <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> Eigenschaft eine <xref:System.Windows.Media.Imaging.BitmapImage> im Code, um den erforderlichen Speicher zum Laden des Bilds zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="fc8ca-107">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in code to reduce the memory required to load the image.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="fc8ca-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc8ca-108">See Also</span></span>  
 [<span data-ttu-id="fc8ca-109">Übersicht über die Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="fc8ca-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
