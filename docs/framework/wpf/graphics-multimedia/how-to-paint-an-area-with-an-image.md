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
ms.openlocfilehash: 5899531291c22ada76213905d0f2ca6944fcbba7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408019"
---
# <a name="how-to-paint-an-area-with-an-image"></a><span data-ttu-id="a672a-102">Gewusst wie: Zeichnen eines Bereichs mit einem Bild</span><span class="sxs-lookup"><span data-stu-id="a672a-102">How to: Paint an Area with an Image</span></span>
<span data-ttu-id="a672a-103">Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.ImageBrush> -Klasse zum Zeichnen eines Bereichs mit einem Bild.</span><span class="sxs-lookup"><span data-stu-id="a672a-103">This example shows how to use the <xref:System.Windows.Media.ImageBrush> class to paint an area with an image.</span></span> <span data-ttu-id="a672a-104">Ein <xref:System.Windows.Media.ImageBrush> zeigt ein einzelnes Bild, das angegebenen seine <xref:System.Windows.Media.ImageBrush.ImageSource%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a672a-104">An <xref:System.Windows.Media.ImageBrush> displays a single image, which is specified by its <xref:System.Windows.Media.ImageBrush.ImageSource%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a672a-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a672a-105">Example</span></span>  
 <span data-ttu-id="a672a-106">Das folgende Beispiel zeichnet die <xref:System.Windows.Controls.Control.Background%2A> einer Schaltfläche mithilfe einer <xref:System.Windows.Media.ImageBrush>.</span><span class="sxs-lookup"><span data-stu-id="a672a-106">The following example paints the <xref:System.Windows.Controls.Control.Background%2A> of a button by using an <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 <span data-ttu-id="a672a-107">Standardmäßig eine <xref:System.Windows.Media.ImageBrush> gestreckt wird, das Image aus, um vollständig auf die Fläche auszufüllen, die Sie zeichnen werden.</span><span class="sxs-lookup"><span data-stu-id="a672a-107">By default, an <xref:System.Windows.Media.ImageBrush> stretches its image to completely fill the area that you are painting.</span></span> <span data-ttu-id="a672a-108">Im vorhergehenden Beispiel wird das Bild zum Ausfüllen der Schaltfläche gestreckt, wobei das Bild möglicherweise verzerrt wird.</span><span class="sxs-lookup"><span data-stu-id="a672a-108">In the preceding example, the image is stretched to fill the button, possibly distorting the image.</span></span> <span data-ttu-id="a672a-109">Sie können dieses Verhalten steuern, durch Festlegen der <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft <xref:System.Windows.Media.TileBrush> zu <xref:System.Windows.Media.Stretch.Uniform> oder <xref:System.Windows.Media.Stretch.UniformToFill>, der bewirkt, dass des Pinsels das Seitenverhältnis des Bilds beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a672a-109">You can control this behavior by setting the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of <xref:System.Windows.Media.TileBrush> to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>, which causes the brush to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="a672a-110">Setzen Sie die <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaften eine <xref:System.Windows.Media.ImageBrush>, Sie können ein sich wiederholendes Muster erstellen.</span><span class="sxs-lookup"><span data-stu-id="a672a-110">If you set the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties of an <xref:System.Windows.Media.ImageBrush>, you can create a repeating pattern.</span></span> <span data-ttu-id="a672a-111">Im folgenden Beispiel wird eine Schaltfläche mithilfe eines Musters gezeichnet, das auf Basis eines Bilds erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="a672a-111">The following example paints a button by using a pattern that is created from an image.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 <span data-ttu-id="a672a-112">Weitere Informationen zu den <xref:System.Windows.Media.ImageBrush> Klasse, finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="a672a-112">For more information about the <xref:System.Windows.Media.ImageBrush> class, see [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="a672a-113">Dieses Codebeispiel ist Teil eines größeren Beispiels, die aus Gründen der <xref:System.Windows.Media.ImageBrush> Klasse.</span><span class="sxs-lookup"><span data-stu-id="a672a-113">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="a672a-114">Das vollständige Beispiel finden Sie unter [Beispiel zu ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005).</span><span class="sxs-lookup"><span data-stu-id="a672a-114">For the complete sample, see [ImageBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a672a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a672a-115">See Also</span></span>  
 [<span data-ttu-id="a672a-116">Zeichnen mit Bildern, Zeichnungen und visuellen Elementen</span><span class="sxs-lookup"><span data-stu-id="a672a-116">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
