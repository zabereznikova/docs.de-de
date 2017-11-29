---
title: 'Gewusst wie: Neigen eines Elements'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d5c46b8c64a26d83ba6d8f018b9a1f8ca8250a57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-skew-an-element"></a><span data-ttu-id="00f0e-102">Gewusst wie: Neigen eines Elements</span><span class="sxs-lookup"><span data-stu-id="00f0e-102">How to: Skew an Element</span></span>
<span data-ttu-id="00f0e-103">Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.SkewTransform> um ein Element zu neigen.</span><span class="sxs-lookup"><span data-stu-id="00f0e-103">This example shows how to use a <xref:System.Windows.Media.SkewTransform> to skew an element.</span></span> <span data-ttu-id="00f0e-104">Eine Neigung ist eine Transformation, die den Koordinatenraum auf ungleichmäßige Art ausdehnt.</span><span class="sxs-lookup"><span data-stu-id="00f0e-104">A skew, which is also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="00f0e-105">Eine typische Verwendung von einem <xref:System.Windows.Media.SkewTransform> ist zum Simulieren von [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] ausführlich [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] Objekte.</span><span class="sxs-lookup"><span data-stu-id="00f0e-105">One typical use of a <xref:System.Windows.Media.SkewTransform> is for simulating [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] depth in [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] objects.</span></span>  
  
 <span data-ttu-id="00f0e-106">Verwenden der <xref:System.Windows.Media.SkewTransform.CenterX%2A> und <xref:System.Windows.Media.SkewTransform.CenterY%2A> Eigenschaften zur Angabe der Mittelpunkts des zeigen die <xref:System.Windows.Media.SkewTransform>.</span><span class="sxs-lookup"><span data-stu-id="00f0e-106">Use the <xref:System.Windows.Media.SkewTransform.CenterX%2A> and <xref:System.Windows.Media.SkewTransform.CenterY%2A> properties to specify the center point of the <xref:System.Windows.Media.SkewTransform>.</span></span>  
  
 <span data-ttu-id="00f0e-107">Verwenden der <xref:System.Windows.Media.SkewTransform.AngleX%2A> und <xref:System.Windows.Media.SkewTransform.AngleY%2A> Eigenschaften den Neigungswinkel der x-Achse und y-Achse angeben, und klicken Sie auf das aktuelle Koordinatensystem entlang dieser Achsen verzerren.</span><span class="sxs-lookup"><span data-stu-id="00f0e-107">Use the <xref:System.Windows.Media.SkewTransform.AngleX%2A> and <xref:System.Windows.Media.SkewTransform.AngleY%2A> properties to specify the skew angle of the x-axis and y-axis, and to skew the current coordinate system along these axes.</span></span>  
  
 <span data-ttu-id="00f0e-108">In Betracht ziehen, um die Auswirkung der eine Neigungstransformation vorherzusagen, <xref:System.Windows.Media.SkewTransform.AngleX%2A> neigt Werte der x-Achse relativ zum ursprünglichen Koordinatensystems.</span><span class="sxs-lookup"><span data-stu-id="00f0e-108">To predict the effect of a skew transformation, consider that <xref:System.Windows.Media.SkewTransform.AngleX%2A> skews x-axis values relative to the original coordinate system.</span></span> <span data-ttu-id="00f0e-109">Aus diesem Grund für ein <xref:System.Windows.Media.SkewTransform.AngleX%2A> 30, die y-Achse dreht 30 Grad über den Ursprung und neigt die Werte in X-von 30 Grad vom Ursprung.</span><span class="sxs-lookup"><span data-stu-id="00f0e-109">Therefore, for an <xref:System.Windows.Media.SkewTransform.AngleX%2A> of 30, the y-axis rotates 30 degrees through the origin and skews the values in x- by 30 degrees from that origin.</span></span> <span data-ttu-id="00f0e-110">Ebenso ein <xref:System.Windows.Media.SkewTransform.AngleY%2A> 30 neigt Sie die y-Werte der Form von 30 Grad vom Ursprung.</span><span class="sxs-lookup"><span data-stu-id="00f0e-110">Likewise, an <xref:System.Windows.Media.SkewTransform.AngleY%2A> of 30 skews the y- values of the shape by 30 degrees from the origin.</span></span> <span data-ttu-id="00f0e-111">Beachten Sie, dass dieser Vorgang nicht dieselbe Wirkung erzielt, wie das Übersetzen (Bewegen) des Koordinatensystems um 30° in der X- oder Y-Achse.</span><span class="sxs-lookup"><span data-stu-id="00f0e-111">Note that this is not the same effect as translating (moving) the coordinate system by 30 degrees in x- or y-.</span></span>  
  
 <span data-ttu-id="00f0e-112">Im folgende Beispiel wird eine horizontale Neigung von 45 Grad ein, um eine <xref:System.Windows.Shapes.Rectangle> von einem Mittelpunkt (0,0).</span><span class="sxs-lookup"><span data-stu-id="00f0e-112">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (0,0).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00f0e-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00f0e-113">Example</span></span>  
 [!code-xaml[transformsSample#41](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 <span data-ttu-id="00f0e-114">Im folgende Beispiel wird eine horizontale Neigung von 45 Grad ein, um eine <xref:System.Windows.Shapes.Rectangle> von einem Mittelpunkt (25,25) aus.</span><span class="sxs-lookup"><span data-stu-id="00f0e-114">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#42](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 <span data-ttu-id="00f0e-115">Im folgende Beispiel wird eine vertikale Neigung von 45 Grad ein, um eine <xref:System.Windows.Shapes.Rectangle> von einem Mittelpunkt (25,25) aus.</span><span class="sxs-lookup"><span data-stu-id="00f0e-115">The following example applies a vertical skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#43](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 <span data-ttu-id="00f0e-116">Die folgenden Abbildungen zeigen die verschiedenen Neigungen, die in diesem Beispiel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00f0e-116">The following illustration shows the different skews that are used in this example.</span></span>  
  
 <span data-ttu-id="00f0e-117">![SkewTransform-Beispiele](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.gif "Img_wcpsdk_graphicsmm_skewtransformexample")</span><span class="sxs-lookup"><span data-stu-id="00f0e-117">![SkewTransform examples](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span></span>  
<span data-ttu-id="00f0e-118">Die drei SkewTransform-Beispiele veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="00f0e-118">The three SkewTransform examples illustrated</span></span>  
  
 <span data-ttu-id="00f0e-119">Das vollständige Beispiel finden Sie im [Beispiel einer 2D-Transformation](http://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="00f0e-119">For the complete sample, see [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00f0e-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00f0e-120">See Also</span></span>  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.SkewTransform>  
 [<span data-ttu-id="00f0e-121">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="00f0e-121">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="00f0e-122">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="00f0e-122">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
