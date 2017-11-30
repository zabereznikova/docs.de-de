---
title: 'Gewusst wie: Angeben des Ursprungs einer Transformation mithilfe von relativen Werten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- origins of Transforms [WPF]
- Transforms [WPF], origins of
- graphics [WPF], origins of Transforms
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ec61fdedc78b785dccf2c235cd17fd20b6d5abc4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-origin-of-a-transform-by-using-relative-values"></a><span data-ttu-id="c795b-102">Gewusst wie: Angeben des Ursprungs einer Transformation mithilfe von relativen Werten</span><span class="sxs-lookup"><span data-stu-id="c795b-102">How to: Specify the Origin of a Transform by Using Relative Values</span></span>
<span data-ttu-id="c795b-103">Dieses Beispiel veranschaulicht die relativen Werte verwenden, um den Ursprung der angeben einer <xref:System.Windows.UIElement.RenderTransform%2A> angewendeten eine <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="c795b-103">This example shows how to use relative values to specify the origin of a <xref:System.Windows.UIElement.RenderTransform%2A> that is applied to a <xref:System.Windows.FrameworkElement>.</span></span>  
  
 <span data-ttu-id="c795b-104">Wenn Sie drehen, skalieren oder verzerren ein <xref:System.Windows.FrameworkElement> mithilfe der <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft, die Standardeinstellung wendet die Transformation auf der linken oberen Ecke des Elements.</span><span class="sxs-lookup"><span data-stu-id="c795b-104">When you rotate, scale, or skew a <xref:System.Windows.FrameworkElement> by using the <xref:System.Windows.UIElement.RenderTransform%2A> property, the default setting applies the transform to the upper-left corner of the element.</span></span> <span data-ttu-id="c795b-105">Wenn Sie von der Mitte des Elements aus drehen, skalieren oder neigen möchten, können Sie dies ändern, indem Sie für den Mittelpunkt der Transformation den Mittelpunkt des Elements festlegen.</span><span class="sxs-lookup"><span data-stu-id="c795b-105">If you want to rotate, scale, or skew from the center of the element, you can compensate by setting the center of the transform to the center of the element.</span></span> <span data-ttu-id="c795b-106">Für diese Lösung müssen Sie jedoch die Größe des Elements kennen.</span><span class="sxs-lookup"><span data-stu-id="c795b-106">However, that solution requires that you know the size of the element.</span></span> <span data-ttu-id="c795b-107">Eine einfachere Möglichkeit, eine Transformation anwenden, in der Mitte eines Elements festgelegt wird seine <xref:System.Windows.UIElement.RenderTransformOrigin%2A> Eigenschaft (0,5, 0,5), anstatt eine Center-Einstellung auf die Transformation selbst.</span><span class="sxs-lookup"><span data-stu-id="c795b-107">An easier way of applying a transform to the center of an element is to set its <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to (0.5, 0.5), instead of setting a center value on the transform itself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c795b-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c795b-108">Example</span></span>  
 <span data-ttu-id="c795b-109">Im folgenden Beispiel wird eine <xref:System.Windows.Media.RotateTransform> Rotieren einer <xref:System.Windows.Controls.Button> 45 Grad im Uhrzeigersinn.</span><span class="sxs-lookup"><span data-stu-id="c795b-109">The following example uses a <xref:System.Windows.Media.RotateTransform> to rotate a <xref:System.Windows.Controls.Button> 45 degrees clockwise.</span></span> <span data-ttu-id="c795b-110">Da in dem Beispiel kein Mittelpunkt angegeben ist, dreht sich die Schaltfläche um den Punkt (0, 0), die obere linke Ecke.</span><span class="sxs-lookup"><span data-stu-id="c795b-110">Because the example does not specify a center, the button rotates about the point (0, 0), which is its upper-left corner.</span></span> <span data-ttu-id="c795b-111">Die <xref:System.Windows.Media.RotateTransform> wird angewendet, um die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c795b-111">The <xref:System.Windows.Media.RotateTransform> is applied to the <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="c795b-112">In der folgenden Abbildung wird das Transformationsergebnis für das folgende Beispiel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c795b-112">The following illustration shows the transformation result for the example that follows.</span></span>  
  
 <span data-ttu-id="c795b-113">![Eine mit RenderTransform transformierte Schaltfläche](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "Graphicsmm_RenderTransformWithDefaultCenter")</span><span class="sxs-lookup"><span data-stu-id="c795b-113">![A button transformed using RenderTransform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")</span></span>  
<span data-ttu-id="c795b-114">Eine Drehung um 45 Grad im Uhrzeigersinn unter Verwendung der RenderTransform-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c795b-114">A 45 degree clockwise rotation by using the RenderTransform property</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 <span data-ttu-id="c795b-115">Auch im folgenden Beispiel wird eine <xref:System.Windows.Media.RotateTransform> drehen eine <xref:System.Windows.Controls.Button> um 45 Grad im Uhrzeigersinn gedreht; allerdings in diesem Beispiel wird die <xref:System.Windows.UIElement.RenderTransformOrigin%2A> der Schaltfläche auf (0,5, 0,5).</span><span class="sxs-lookup"><span data-stu-id="c795b-115">The following example also uses a <xref:System.Windows.Media.RotateTransform> to rotate a <xref:System.Windows.Controls.Button> 45 degrees clockwise; however, this example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> of the button to (0.5, 0.5).</span></span> <span data-ttu-id="c795b-116">Dadurch erfolgt die Drehung um den Mittelpunkt der Schaltfläche, nicht um die obere linke Ecke.</span><span class="sxs-lookup"><span data-stu-id="c795b-116">As a result, the rotation is applied to the center of the button instead of to the upper-left corner.</span></span>  
  
 <span data-ttu-id="c795b-117">In der folgenden Abbildung wird das Transformationsergebnis für das folgende Beispiel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c795b-117">The following illustration shows the transformation result for the example that follows.</span></span>  
  
 <span data-ttu-id="c795b-118">![Eine um ihren Mittelpunkt transformierte Schaltfläche](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "Graphicsmm_RenderTransformRelativeCenter")</span><span class="sxs-lookup"><span data-stu-id="c795b-118">![A button transformed about its center](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")</span></span>  
<span data-ttu-id="c795b-119">Eine Drehung um 45 Grad unter Verwendung der RenderTransform-Eigenschaft mit einem RenderTransformOrigin von (0.5, 0.5)</span><span class="sxs-lookup"><span data-stu-id="c795b-119">A 45 degree rotation by using the RenderTransform property with a RenderTransformOrigin of (0.5, 0.5)</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 <span data-ttu-id="c795b-120">Weitere Informationen zum Transformieren von <xref:System.Windows.FrameworkElement> anzuzeigen, die [Transforms Overview](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c795b-120">For more information about transforming <xref:System.Windows.FrameworkElement> objects, see the [Transforms Overview](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c795b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c795b-121">See Also</span></span>  
 <xref:System.Windows.Media.Transform>  
 [<span data-ttu-id="c795b-122">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="c795b-122">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="c795b-123">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="c795b-123">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
