---
title: 'Gewusst wie: Neigen eines Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 10b00044c1c518641281e2e72cdb5a68474b5170
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112023"
---
# <a name="how-to-skew-an-element"></a><span data-ttu-id="7eb93-102">Gewusst wie: Neigen eines Elements</span><span class="sxs-lookup"><span data-stu-id="7eb93-102">How to: Skew an Element</span></span>
<span data-ttu-id="7eb93-103">In diesem Beispiel wird <xref:System.Windows.Media.SkewTransform> gezeigt, wie ein verwendet wird, um ein Element zu verzerren.</span><span class="sxs-lookup"><span data-stu-id="7eb93-103">This example shows how to use a <xref:System.Windows.Media.SkewTransform> to skew an element.</span></span> <span data-ttu-id="7eb93-104">Eine Neigung ist eine Transformation, die den Koordinatenraum auf ungleichmäßige Art ausdehnt.</span><span class="sxs-lookup"><span data-stu-id="7eb93-104">A skew, which is also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="7eb93-105">Eine typische Verwendung <xref:System.Windows.Media.SkewTransform> von a ist die Simulation von 3D-Tiefe in 2D-Objekten.</span><span class="sxs-lookup"><span data-stu-id="7eb93-105">One typical use of a <xref:System.Windows.Media.SkewTransform> is for simulating 3D depth in 2D objects.</span></span>  
  
 <span data-ttu-id="7eb93-106">Verwenden <xref:System.Windows.Media.SkewTransform.CenterX%2A> Sie <xref:System.Windows.Media.SkewTransform.CenterY%2A> die und Eigenschaften, <xref:System.Windows.Media.SkewTransform>um den Mittelpunkt der anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7eb93-106">Use the <xref:System.Windows.Media.SkewTransform.CenterX%2A> and <xref:System.Windows.Media.SkewTransform.CenterY%2A> properties to specify the center point of the <xref:System.Windows.Media.SkewTransform>.</span></span>  
  
 <span data-ttu-id="7eb93-107">Verwenden <xref:System.Windows.Media.SkewTransform.AngleX%2A> Sie <xref:System.Windows.Media.SkewTransform.AngleY%2A> die und Eigenschaften, um den Neigungswinkel der x-Achse und der y-Achse anzugeben und das aktuelle Koordinatensystem entlang dieser Achsen zu verzerren.</span><span class="sxs-lookup"><span data-stu-id="7eb93-107">Use the <xref:System.Windows.Media.SkewTransform.AngleX%2A> and <xref:System.Windows.Media.SkewTransform.AngleY%2A> properties to specify the skew angle of the x-axis and y-axis, and to skew the current coordinate system along these axes.</span></span>  
  
 <span data-ttu-id="7eb93-108">Um den Effekt einer Schiefentransformation <xref:System.Windows.Media.SkewTransform.AngleX%2A> vorherzusagen, sollten Sie berücksichtigen, dass x-Achsenwerte relativ zum ursprünglichen Koordinatensystem verzerrt werden.</span><span class="sxs-lookup"><span data-stu-id="7eb93-108">To predict the effect of a skew transformation, consider that <xref:System.Windows.Media.SkewTransform.AngleX%2A> skews x-axis values relative to the original coordinate system.</span></span> <span data-ttu-id="7eb93-109">Daher dreht <xref:System.Windows.Media.SkewTransform.AngleX%2A> sich bei einer von 30 die y-Achse um 30 Grad durch den Ursprung und verzerrt die Werte in x- um 30 Grad von diesem Ursprung.</span><span class="sxs-lookup"><span data-stu-id="7eb93-109">Therefore, for an <xref:System.Windows.Media.SkewTransform.AngleX%2A> of 30, the y-axis rotates 30 degrees through the origin and skews the values in x- by 30 degrees from that origin.</span></span> <span data-ttu-id="7eb93-110">Ebenso verzerrt <xref:System.Windows.Media.SkewTransform.AngleY%2A> ein von 30 die y-Werte der Form um 30 Grad vom Ursprung.</span><span class="sxs-lookup"><span data-stu-id="7eb93-110">Likewise, an <xref:System.Windows.Media.SkewTransform.AngleY%2A> of 30 skews the y- values of the shape by 30 degrees from the origin.</span></span> <span data-ttu-id="7eb93-111">Beachten Sie, dass dieser Vorgang nicht dieselbe Wirkung erzielt, wie das Übersetzen (Bewegen) des Koordinatensystems um 30° in der X- oder Y-Achse.</span><span class="sxs-lookup"><span data-stu-id="7eb93-111">Note that this is not the same effect as translating (moving) the coordinate system by 30 degrees in x- or y-.</span></span>  
  
 <span data-ttu-id="7eb93-112">Im folgenden Beispiel wird eine horizontale Neigung <xref:System.Windows.Shapes.Rectangle> von 45 Grad auf eine von einem Mittelpunkt von (0,0) angewendet.</span><span class="sxs-lookup"><span data-stu-id="7eb93-112">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (0,0).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7eb93-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7eb93-113">Example</span></span>  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 <span data-ttu-id="7eb93-114">Im folgenden Beispiel wird eine horizontale Neigung <xref:System.Windows.Shapes.Rectangle> von 45 Grad auf eine von einem Mittelpunkt (25,25) angewendet.</span><span class="sxs-lookup"><span data-stu-id="7eb93-114">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 <span data-ttu-id="7eb93-115">Im folgenden Beispiel wird eine vertikale Neigung <xref:System.Windows.Shapes.Rectangle> von 45 Grad auf eine von einem Mittelpunkt (25,25) angewendet.</span><span class="sxs-lookup"><span data-stu-id="7eb93-115">The following example applies a vertical skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 <span data-ttu-id="7eb93-116">Die folgenden Abbildungen zeigen die verschiedenen Neigungen, die in diesem Beispiel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7eb93-116">The following illustration shows the different skews that are used in this example.</span></span>  
  
 <span data-ttu-id="7eb93-117">![SkewTransform-Beispiele](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span><span class="sxs-lookup"><span data-stu-id="7eb93-117">![SkewTransform examples](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span></span>  
<span data-ttu-id="7eb93-118">Die drei SkewTransform-Beispiele veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="7eb93-118">The three SkewTransform examples illustrated</span></span>  
  
 <span data-ttu-id="7eb93-119">Das vollständige Beispiel finden Sie unter [2D-Transformationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="7eb93-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eb93-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7eb93-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [<span data-ttu-id="7eb93-121">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="7eb93-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="7eb93-122">How-to-Themen</span><span class="sxs-lookup"><span data-stu-id="7eb93-122">How-to Topics</span></span>](transformations-how-to-topics.md)
