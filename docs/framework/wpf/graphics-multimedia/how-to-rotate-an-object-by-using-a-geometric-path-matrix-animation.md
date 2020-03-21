---
title: 'Gewusst wie: Drehen eines Objekts mithilfe eines geometrischen Pfads (MatrixAnimation)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
ms.openlocfilehash: 63dc873a2b840ea3f870a8c60c5691ab271c1c9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187416"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a><span data-ttu-id="28dc3-102">Gewusst wie: Drehen eines Objekts mithilfe eines geometrischen Pfads (MatrixAnimation)</span><span class="sxs-lookup"><span data-stu-id="28dc3-102">How to: Rotate an Object by Using a Geometric Path (Matrix Animation)</span></span>
<span data-ttu-id="28dc3-103">In diesem Beispiel wird <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> gezeigt, wie ein und ein <xref:System.Windows.Media.MatrixTransform> zum Drehen <xref:System.Windows.Media.PathGeometry> (Pivoten) eines Objekts entlang eines geometrischen Pfads verwendet wird, der durch ein Objekt definiert wird.</span><span class="sxs-lookup"><span data-stu-id="28dc3-103">This example shows how to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and a <xref:System.Windows.Media.MatrixTransform> to rotate (pivot) an object along a geometric path defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28dc3-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="28dc3-104">Example</span></span>  
 <span data-ttu-id="28dc3-105">Im folgenden Beispiel <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> wird das <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Objekt <xref:System.Windows.Media.MatrixTransform>verwendet, um die Eigenschaft einer zu animieren.</span><span class="sxs-lookup"><span data-stu-id="28dc3-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="28dc3-106">Der <xref:System.Windows.Media.MatrixTransform> wird auf eine Schaltfläche angewendet und bewirkt, dass er sich entlang eines gekrümmten Pfads bewegt.</span><span class="sxs-lookup"><span data-stu-id="28dc3-106">The <xref:System.Windows.Media.MatrixTransform> is applied to a button and causes it to move along a curved path.</span></span> <span data-ttu-id="28dc3-107">Da <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> die Eigenschaft `true`auf festgelegt ist, wird das Rechteck entlang der Tangente des Pfads gedreht.</span><span class="sxs-lookup"><span data-stu-id="28dc3-107">Because the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property is set to `true`, the rectangle rotates along the tangent of the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 <span data-ttu-id="28dc3-108">Das vollständige Beispiel finden Sie unter [Pfadanimationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span><span class="sxs-lookup"><span data-stu-id="28dc3-108">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="28dc3-109">Die Codeversion des vorherigen <xref:System.Windows.Media.Animation.Storyboard> Beispiels <xref:System.Windows.Media.EllipseGeometry>verwendet eine zum Animieren der , obwohl nur eine Animation angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="28dc3-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="28dc3-110">Eine einfachere Möglichkeit, eine einzelne Animation auf eine <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Eigenschaft im Code anzuwenden, ist die Verwendung der Methode.</span><span class="sxs-lookup"><span data-stu-id="28dc3-110">An easier way to apply a single animation to a property in code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="28dc3-111">Ein Beispiel finden Sie unter [Animieren einer Eigenschaft ohne Verwendung eines Storyboards](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="28dc3-111">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28dc3-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28dc3-112">See also</span></span>

- [<span data-ttu-id="28dc3-113">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="28dc3-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="28dc3-114">Gewusst-wie-Themen zur Pfadanimation</span><span class="sxs-lookup"><span data-stu-id="28dc3-114">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
- [<span data-ttu-id="28dc3-115">Beispiel einer Pfadanimation</span><span class="sxs-lookup"><span data-stu-id="28dc3-115">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
