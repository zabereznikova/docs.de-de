---
title: 'Gewusst wie: Drehen von Elementen ohne Positionsänderung'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: 2e72389a11e48629c2763fcbd9f7b1945ffff5dd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452791"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="6b5e1-102">Gewusst wie: Drehen von Elementen ohne Positionsänderung</span><span class="sxs-lookup"><span data-stu-id="6b5e1-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="6b5e1-103">In diesem Beispiel wird gezeigt, wie ein Element mit einem <xref:System.Windows.Media.RotateTransform> und einem <xref:System.Windows.Media.Animation.DoubleAnimation>gedreht wird.</span><span class="sxs-lookup"><span data-stu-id="6b5e1-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="6b5e1-104">Im folgenden Beispiel wird der <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A>-Eigenschaft des-Elements angewendet.</span><span class="sxs-lookup"><span data-stu-id="6b5e1-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="6b5e1-105">Das Beispiel verwendet eine <xref:System.Windows.Media.Animation.DoubleAnimation>, um die <xref:System.Windows.Media.RotateTransform.Angle%2A> der <xref:System.Windows.Media.RotateTransform>zu animieren.</span><span class="sxs-lookup"><span data-stu-id="6b5e1-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="6b5e1-106">Damit das Element gedreht wird, wird im Beispiel die <xref:System.Windows.UIElement.RenderTransformOrigin%2A>-Eigenschaft des-Elements auf den Punkt (0,5, 0,5) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6b5e1-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b5e1-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b5e1-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="6b5e1-108">Das komplette Beispiel, das weitere Transformations Beispiele enthält, finden Sie unter [Beispiel für 2D-Transformationen](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="6b5e1-108">For the complete sample, which includes more transformation examples, see [2-D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b5e1-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b5e1-109">See also</span></span>

- [<span data-ttu-id="6b5e1-110">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="6b5e1-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="6b5e1-111">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="6b5e1-111">Transforms Overview</span></span>](transforms-overview.md)
