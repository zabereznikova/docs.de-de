---
title: 'Vorgehensweise: Angeben des Ursprungs einer Transformation mithilfe von relativen Werten'
ms.date: 03/30/2017
helpviewer_keywords:
- origins of Transforms [WPF]
- Transforms [WPF], origins of
- graphics [WPF], origins of Transforms
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
ms.openlocfilehash: bdcc17e2d9bf68170c10dd8e35670f3e072a527c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352567"
---
# <a name="how-to-specify-the-origin-of-a-transform-by-using-relative-values"></a><span data-ttu-id="cc5a3-102">Vorgehensweise: Angeben des Ursprungs einer Transformation mithilfe von relativen Werten</span><span class="sxs-lookup"><span data-stu-id="cc5a3-102">How to: Specify the Origin of a Transform by Using Relative Values</span></span>
<span data-ttu-id="cc5a3-103">Dieses Beispiel zeigt, wie Sie relative Werte verwenden, um den Ursprung der angeben einer <xref:System.Windows.UIElement.RenderTransform%2A> angewendeten eine <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="cc5a3-103">This example shows how to use relative values to specify the origin of a <xref:System.Windows.UIElement.RenderTransform%2A> that is applied to a <xref:System.Windows.FrameworkElement>.</span></span>  
  
 <span data-ttu-id="cc5a3-104">Wenn Sie drehen, skalieren oder neigen eine <xref:System.Windows.FrameworkElement> mithilfe der <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft, die Standardeinstellung wendet die Transformation auf der linken oberen Ecke des Elements.</span><span class="sxs-lookup"><span data-stu-id="cc5a3-104">When you rotate, scale, or skew a <xref:System.Windows.FrameworkElement> by using the <xref:System.Windows.UIElement.RenderTransform%2A> property, the default setting applies the transform to the upper-left corner of the element.</span></span> <span data-ttu-id="cc5a3-105">Wenn Sie von der Mitte des Elements aus drehen, skalieren oder neigen möchten, können Sie dies ändern, indem Sie für den Mittelpunkt der Transformation den Mittelpunkt des Elements festlegen.</span><span class="sxs-lookup"><span data-stu-id="cc5a3-105">If you want to rotate, scale, or skew from the center of the element, you can compensate by setting the center of the transform to the center of the element.</span></span> <span data-ttu-id="cc5a3-106">Für diese Lösung müssen Sie jedoch die Größe des Elements kennen.</span><span class="sxs-lookup"><span data-stu-id="cc5a3-106">However, that solution requires that you know the size of the element.</span></span> <span data-ttu-id="cc5a3-107">Eine einfachere Anwendung einer Transformation in der Mitte des Elements festgelegt wird seine <xref:System.Windows.UIElement.RenderTransformOrigin%2A> Eigenschaft auf (0.5, 0.5) Wert für den Mittelpunkt der Transformation selbst festlegen, statt.</span><span class="sxs-lookup"><span data-stu-id="cc5a3-107">An easier way of applying a transform to the center of an element is to set its <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to (0.5, 0.5), instead of setting a center value on the transform itself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc5a3-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cc5a3-108">Example</span></span>  
 <span data-ttu-id="cc5a3-109">Im folgenden Beispiel wird eine <xref:System.Windows.Media.RotateTransform> Rotieren einer <xref:System.Windows.Controls.Button> um 45 Grad im Uhrzeigersinn.</span><span class="sxs-lookup"><span data-stu-id="cc5a3-109">The following example uses a <xref:System.Windows.Media.RotateTransform> to rotate a <xref:System.Windows.Controls.Button> 45 degrees clockwise.</span></span> <span data-ttu-id="cc5a3-110">Da in dem Beispiel kein Mittelpunkt angegeben ist, dreht sich die Schaltfläche um den Punkt (0, 0), die obere linke Ecke.</span><span class="sxs-lookup"><span data-stu-id="cc5a3-110">Because the example does not specify a center, the button rotates about the point (0, 0), which is its upper-left corner.</span></span> <span data-ttu-id="cc5a3-111">Die <xref:System.Windows.Media.RotateTransform> gilt, an die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="cc5a3-111">The <xref:System.Windows.Media.RotateTransform> is applied to the <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="cc5a3-112">In der folgenden Abbildung wird das Transformationsergebnis für das folgende Beispiel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc5a3-112">The following illustration shows the transformation result for the example that follows.</span></span>  
  
 <span data-ttu-id="cc5a3-113">![Eine mit RenderTransform transformierte Schaltfläche](./media/graphicsmm-rendertransformwithdefaultcenter.png "Graphicsmm_RenderTransformWithDefaultCenter")</span><span class="sxs-lookup"><span data-stu-id="cc5a3-113">![A button transformed using RenderTransform](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")</span></span>  
<span data-ttu-id="cc5a3-114">Eine Drehung um 45 Grad im Uhrzeigersinn unter Verwendung der RenderTransform-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="cc5a3-114">A 45 degree clockwise rotation by using the RenderTransform property</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 <span data-ttu-id="cc5a3-115">Das folgende Beispiel verwendet auch eine <xref:System.Windows.Media.RotateTransform> Rotieren einer <xref:System.Windows.Controls.Button> um 45 Grad im Uhrzeigersinn gedreht; allerdings in diesem Beispiel wird der <xref:System.Windows.UIElement.RenderTransformOrigin%2A> der Schaltfläche auf (0.5, 0.5).</span><span class="sxs-lookup"><span data-stu-id="cc5a3-115">The following example also uses a <xref:System.Windows.Media.RotateTransform> to rotate a <xref:System.Windows.Controls.Button> 45 degrees clockwise; however, this example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> of the button to (0.5, 0.5).</span></span> <span data-ttu-id="cc5a3-116">Dadurch erfolgt die Drehung um den Mittelpunkt der Schaltfläche, nicht um die obere linke Ecke.</span><span class="sxs-lookup"><span data-stu-id="cc5a3-116">As a result, the rotation is applied to the center of the button instead of to the upper-left corner.</span></span>  
  
 <span data-ttu-id="cc5a3-117">In der folgenden Abbildung wird das Transformationsergebnis für das folgende Beispiel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc5a3-117">The following illustration shows the transformation result for the example that follows.</span></span>  
  
 <span data-ttu-id="cc5a3-118">![Eine um ihren Mittelpunkt transformierte Schaltfläche](./media/graphicsmm-rendertransformrelativecenter.png "Graphicsmm_RenderTransformRelativeCenter")</span><span class="sxs-lookup"><span data-stu-id="cc5a3-118">![A button transformed about its center](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")</span></span>  
<span data-ttu-id="cc5a3-119">Eine Drehung um 45 Grad unter Verwendung der RenderTransform-Eigenschaft mit einem RenderTransformOrigin von (0.5, 0.5)</span><span class="sxs-lookup"><span data-stu-id="cc5a3-119">A 45 degree rotation by using the RenderTransform property with a RenderTransformOrigin of (0.5, 0.5)</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 <span data-ttu-id="cc5a3-120">Weitere Informationen zum Transformieren von <xref:System.Windows.FrameworkElement> Objekten finden Sie die [Übersicht über Transformationen](transforms-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cc5a3-120">For more information about transforming <xref:System.Windows.FrameworkElement> objects, see the [Transforms Overview](transforms-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc5a3-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc5a3-121">See also</span></span>
- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="cc5a3-122">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="cc5a3-122">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="cc5a3-123">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="cc5a3-123">How-to Topics</span></span>](transformations-how-to-topics.md)
