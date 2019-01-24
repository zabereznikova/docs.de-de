---
title: 'Vorgehensweise: Neigen eines Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 0ba5f3645156459a711d88b7330b221a5d083e7c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611331"
---
# <a name="how-to-skew-an-element"></a><span data-ttu-id="6a039-102">Vorgehensweise: Neigen eines Elements</span><span class="sxs-lookup"><span data-stu-id="6a039-102">How to: Skew an Element</span></span>
<span data-ttu-id="6a039-103">Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.SkewTransform> auf ein Element zu neigen.</span><span class="sxs-lookup"><span data-stu-id="6a039-103">This example shows how to use a <xref:System.Windows.Media.SkewTransform> to skew an element.</span></span> <span data-ttu-id="6a039-104">Eine Neigung ist eine Transformation, die den Koordinatenraum auf ungleichmäßige Art ausdehnt.</span><span class="sxs-lookup"><span data-stu-id="6a039-104">A skew, which is also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="6a039-105">Eine typische Verwendung einer <xref:System.Windows.Media.SkewTransform> ist das simulieren [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] Tiefe [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] Objekte.</span><span class="sxs-lookup"><span data-stu-id="6a039-105">One typical use of a <xref:System.Windows.Media.SkewTransform> is for simulating [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] depth in [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] objects.</span></span>  
  
 <span data-ttu-id="6a039-106">Verwenden der <xref:System.Windows.Media.SkewTransform.CenterX%2A> und <xref:System.Windows.Media.SkewTransform.CenterY%2A> Eigenschaften an der Mitte des zeigen die <xref:System.Windows.Media.SkewTransform>.</span><span class="sxs-lookup"><span data-stu-id="6a039-106">Use the <xref:System.Windows.Media.SkewTransform.CenterX%2A> and <xref:System.Windows.Media.SkewTransform.CenterY%2A> properties to specify the center point of the <xref:System.Windows.Media.SkewTransform>.</span></span>  
  
 <span data-ttu-id="6a039-107">Verwenden der <xref:System.Windows.Media.SkewTransform.AngleX%2A> und <xref:System.Windows.Media.SkewTransform.AngleY%2A> Eigenschaften, um den Neigungswinkels der x-Achse und y-Achse anzugeben und um das aktuelle Koordinatensystem entlang dieser Achsen zu neigen.</span><span class="sxs-lookup"><span data-stu-id="6a039-107">Use the <xref:System.Windows.Media.SkewTransform.AngleX%2A> and <xref:System.Windows.Media.SkewTransform.AngleY%2A> properties to specify the skew angle of the x-axis and y-axis, and to skew the current coordinate system along these axes.</span></span>  
  
 <span data-ttu-id="6a039-108">Um die Auswirkungen einer Neigungstransformation vorherzusagen, zu berücksichtigen, die <xref:System.Windows.Media.SkewTransform.AngleX%2A> Werte der x-Achse relativ zum ursprünglichen Koordinatensystem neigt.</span><span class="sxs-lookup"><span data-stu-id="6a039-108">To predict the effect of a skew transformation, consider that <xref:System.Windows.Media.SkewTransform.AngleX%2A> skews x-axis values relative to the original coordinate system.</span></span> <span data-ttu-id="6a039-109">Aus diesem Grund für eine <xref:System.Windows.Media.SkewTransform.AngleX%2A> von 30 die y-Achse dreht 30° durch den Ursprung und neigt die Werte in X-um 30° vom Ursprung.</span><span class="sxs-lookup"><span data-stu-id="6a039-109">Therefore, for an <xref:System.Windows.Media.SkewTransform.AngleX%2A> of 30, the y-axis rotates 30 degrees through the origin and skews the values in x- by 30 degrees from that origin.</span></span> <span data-ttu-id="6a039-110">Ebenso ein <xref:System.Windows.Media.SkewTransform.AngleY%2A> neigt Sie 30 die y-Werte der Form um 30° vom Ursprung.</span><span class="sxs-lookup"><span data-stu-id="6a039-110">Likewise, an <xref:System.Windows.Media.SkewTransform.AngleY%2A> of 30 skews the y- values of the shape by 30 degrees from the origin.</span></span> <span data-ttu-id="6a039-111">Beachten Sie, dass dieser Vorgang nicht dieselbe Wirkung erzielt, wie das Übersetzen (Bewegen) des Koordinatensystems um 30° in der X- oder Y-Achse.</span><span class="sxs-lookup"><span data-stu-id="6a039-111">Note that this is not the same effect as translating (moving) the coordinate system by 30 degrees in x- or y-.</span></span>  
  
 <span data-ttu-id="6a039-112">Im folgenden Beispiel wird eine horizontale Neigung von 45° auf ein <xref:System.Windows.Shapes.Rectangle> aus einem Mittelpunkt (0,0).</span><span class="sxs-lookup"><span data-stu-id="6a039-112">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (0,0).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a039-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6a039-113">Example</span></span>  
 [!code-xaml[transformsSample#41](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 <span data-ttu-id="6a039-114">Im folgenden Beispiel wird eine horizontale Neigung von 45° auf ein <xref:System.Windows.Shapes.Rectangle> aus einem Mittelpunkt (25,25).</span><span class="sxs-lookup"><span data-stu-id="6a039-114">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#42](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 <span data-ttu-id="6a039-115">Im folgenden Beispiel wird eine vertikale Neigung von 45° auf ein <xref:System.Windows.Shapes.Rectangle> aus einem Mittelpunkt (25,25).</span><span class="sxs-lookup"><span data-stu-id="6a039-115">The following example applies a vertical skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#43](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 <span data-ttu-id="6a039-116">Die folgenden Abbildungen zeigen die verschiedenen Neigungen, die in diesem Beispiel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6a039-116">The following illustration shows the different skews that are used in this example.</span></span>  
  
 <span data-ttu-id="6a039-117">![SkewTransform-Beispiele](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.gif "Img_wcpsdk_graphicsmm_skewtransformexample")</span><span class="sxs-lookup"><span data-stu-id="6a039-117">![SkewTransform examples](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span></span>  
<span data-ttu-id="6a039-118">Die drei SkewTransform-Beispiele veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="6a039-118">The three SkewTransform examples illustrated</span></span>  
  
 <span data-ttu-id="6a039-119">Das vollständige Beispiel finden Sie im [Beispiel einer 2D-Transformation](https://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="6a039-119">For the complete sample, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a039-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a039-120">See also</span></span>
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [<span data-ttu-id="6a039-121">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="6a039-121">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
- [<span data-ttu-id="6a039-122">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="6a039-122">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
