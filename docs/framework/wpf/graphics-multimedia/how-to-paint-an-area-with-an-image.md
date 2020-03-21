---
title: 'Gewusst wie: Zeichnen eines Bereichs mit einem Bild'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 92969778c04c6ac634a2964c402d6c3439b96b49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186054"
---
# <a name="how-to-paint-an-area-with-an-image"></a><span data-ttu-id="ca8d0-102">Gewusst wie: Zeichnen eines Bereichs mit einem Bild</span><span class="sxs-lookup"><span data-stu-id="ca8d0-102">How to: Paint an Area with an Image</span></span>
<span data-ttu-id="ca8d0-103">In diesem Beispiel wird <xref:System.Windows.Media.ImageBrush> gezeigt, wie sie die Klasse zum Zeichnen eines Bereichs mit einem Bild verwendet.</span><span class="sxs-lookup"><span data-stu-id="ca8d0-103">This example shows how to use the <xref:System.Windows.Media.ImageBrush> class to paint an area with an image.</span></span> <span data-ttu-id="ca8d0-104">Ein <xref:System.Windows.Media.ImageBrush> zeigt ein einzelnes Bild <xref:System.Windows.Media.ImageBrush.ImageSource%2A> an, das durch seine Eigenschaft angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ca8d0-104">An <xref:System.Windows.Media.ImageBrush> displays a single image, which is specified by its <xref:System.Windows.Media.ImageBrush.ImageSource%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca8d0-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ca8d0-105">Example</span></span>  
 <span data-ttu-id="ca8d0-106">Im folgenden Beispiel <xref:System.Windows.Controls.Control.Background%2A> wird die Schaltfläche <xref:System.Windows.Media.ImageBrush>mithilfe einer gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ca8d0-106">The following example paints the <xref:System.Windows.Controls.Control.Background%2A> of a button by using an <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 <span data-ttu-id="ca8d0-107">Standardmäßig dehnt ein <xref:System.Windows.Media.ImageBrush> Bild sein Bild aus, um den Bereich, den Sie malen, vollständig zu füllen.</span><span class="sxs-lookup"><span data-stu-id="ca8d0-107">By default, an <xref:System.Windows.Media.ImageBrush> stretches its image to completely fill the area that you are painting.</span></span> <span data-ttu-id="ca8d0-108">Im vorhergehenden Beispiel wird das Bild zum Ausfüllen der Schaltfläche gestreckt, wobei das Bild möglicherweise verzerrt wird.</span><span class="sxs-lookup"><span data-stu-id="ca8d0-108">In the preceding example, the image is stretched to fill the button, possibly distorting the image.</span></span> <span data-ttu-id="ca8d0-109">Sie können dieses Verhalten <xref:System.Windows.Media.TileBrush.Stretch%2A> steuern, <xref:System.Windows.Media.TileBrush> <xref:System.Windows.Media.Stretch.Uniform> indem <xref:System.Windows.Media.Stretch.UniformToFill>Sie die Eigenschaft von oder festlegen, wodurch der Pinsel das Seitenverhältnis des Bildes beibehält.</span><span class="sxs-lookup"><span data-stu-id="ca8d0-109">You can control this behavior by setting the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of <xref:System.Windows.Media.TileBrush> to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>, which causes the brush to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="ca8d0-110">Wenn Sie <xref:System.Windows.Media.TileBrush.Viewport%2A> die <xref:System.Windows.Media.TileBrush.TileMode%2A> und <xref:System.Windows.Media.ImageBrush>die Eigenschaften eines festlegen, können Sie ein wiederholtes Muster erstellen.</span><span class="sxs-lookup"><span data-stu-id="ca8d0-110">If you set the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties of an <xref:System.Windows.Media.ImageBrush>, you can create a repeating pattern.</span></span> <span data-ttu-id="ca8d0-111">Im folgenden Beispiel wird eine Schaltfläche mithilfe eines Musters gezeichnet, das auf Basis eines Bilds erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ca8d0-111">The following example paints a button by using a pattern that is created from an image.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 <span data-ttu-id="ca8d0-112">Weitere Informationen zur <xref:System.Windows.Media.ImageBrush> Klasse finden Sie unter [Malen mit Bildern, Zeichnungen und Visuals](painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="ca8d0-112">For more information about the <xref:System.Windows.Media.ImageBrush> class, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="ca8d0-113">Dieses Codebeispiel ist Teil eines größeren Beispiels, das für die <xref:System.Windows.Media.ImageBrush> Klasse bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ca8d0-113">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="ca8d0-114">Das vollständige Beispiel finden Sie unter [ImageBrush-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span><span class="sxs-lookup"><span data-stu-id="ca8d0-114">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca8d0-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ca8d0-115">See also</span></span>

- [<span data-ttu-id="ca8d0-116">Zeichnen mit Bildern, Zeichnungen und visuellen Elementen</span><span class="sxs-lookup"><span data-stu-id="ca8d0-116">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
