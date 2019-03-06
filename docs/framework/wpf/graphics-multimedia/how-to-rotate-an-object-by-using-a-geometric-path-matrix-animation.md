---
title: 'Vorgehensweise: Drehen eines Objekts mithilfe eines geometrischen Pfads (Matrixanimation)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
ms.openlocfilehash: 57402ba24e8dc75f3563e71329b54db9cb96aaab
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369083"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a><span data-ttu-id="eaa2e-102">Vorgehensweise: Drehen eines Objekts mithilfe eines geometrischen Pfads (Matrixanimation)</span><span class="sxs-lookup"><span data-stu-id="eaa2e-102">How to: Rotate an Object by Using a Geometric Path (Matrix Animation)</span></span>
<span data-ttu-id="eaa2e-103">Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> und ein <xref:System.Windows.Media.MatrixTransform> gedreht (PowerPivot) eines Objekts entlang eines geometrischen Pfads durch definiert eine <xref:System.Windows.Media.PathGeometry> Objekt.</span><span class="sxs-lookup"><span data-stu-id="eaa2e-103">This example shows how to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and a <xref:System.Windows.Media.MatrixTransform> to rotate (pivot) an object along a geometric path defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eaa2e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eaa2e-104">Example</span></span>  
 <span data-ttu-id="eaa2e-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> zu animierende Objekt die <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Eigenschaft eine <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="eaa2e-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="eaa2e-106">Die <xref:System.Windows.Media.MatrixTransform> ist auf eine Schaltfläche angewendet und bewirkt, dass es entlang eines gekrümmten Pfads verschoben.</span><span class="sxs-lookup"><span data-stu-id="eaa2e-106">The <xref:System.Windows.Media.MatrixTransform> is applied to a button and causes it to move along a curved path.</span></span> <span data-ttu-id="eaa2e-107">Da die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> -Eigenschaftensatz auf `true`, dreht sich das Rechteck entlang der Tangente des Pfads.</span><span class="sxs-lookup"><span data-stu-id="eaa2e-107">Because the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property is set to `true`, the rectangle rotates along the tangent of the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 <span data-ttu-id="eaa2e-108">Das vollständige Beispiel finden Sie unter [Beispiel zu Textanimation](https://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="eaa2e-108">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="eaa2e-109">Die Codeversion des vorhergehenden Beispiels verwendet eine <xref:System.Windows.Media.Animation.Storyboard> zum Animieren der <xref:System.Windows.Media.EllipseGeometry>, auch wenn nur eine einzige Animation angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="eaa2e-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="eaa2e-110">Eine einfachere Möglichkeit zum Anwenden einer einzelnen Animation auf eine Eigenschaft im Code ist die Verwendung der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="eaa2e-110">An easier way to apply a single animation to a property in code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="eaa2e-111">Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="eaa2e-111">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaa2e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eaa2e-112">See also</span></span>
- [<span data-ttu-id="eaa2e-113">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="eaa2e-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="eaa2e-114">Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)</span><span class="sxs-lookup"><span data-stu-id="eaa2e-114">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
- [<span data-ttu-id="eaa2e-115">Beispiel zu Textanimation</span><span class="sxs-lookup"><span data-stu-id="eaa2e-115">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)
