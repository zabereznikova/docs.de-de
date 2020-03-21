---
title: 'Gewusst wie: Drehen von Elementen ohne Positionsänderung'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a1b515822391de08ec8ed8ff0ff1f0086874dc02
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112075"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="ed81b-102">Gewusst wie: Drehen von Elementen ohne Positionsänderung</span><span class="sxs-lookup"><span data-stu-id="ed81b-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="ed81b-103">Dieses Beispiel zeigt, wie ein Element <xref:System.Windows.Media.RotateTransform> mithilfe <xref:System.Windows.Media.Animation.DoubleAnimation>von a und a gespinnt wird.</span><span class="sxs-lookup"><span data-stu-id="ed81b-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="ed81b-104">Im folgenden Beispiel <xref:System.Windows.Media.RotateTransform> wird <xref:System.Windows.UIElement.RenderTransform%2A> die Eigenschaft des Elements angewendet.</span><span class="sxs-lookup"><span data-stu-id="ed81b-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="ed81b-105">Im Beispiel <xref:System.Windows.Media.Animation.DoubleAnimation> wird a <xref:System.Windows.Media.RotateTransform.Angle%2A> verwendet, um die der <xref:System.Windows.Media.RotateTransform>zu animieren.</span><span class="sxs-lookup"><span data-stu-id="ed81b-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="ed81b-106">Um das Element an Ort und <xref:System.Windows.UIElement.RenderTransformOrigin%2A> Stelle zu drehen, legt das Beispiel die Eigenschaft des Elements auf den Punkt (0,5, 0,5) fest.</span><span class="sxs-lookup"><span data-stu-id="ed81b-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed81b-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ed81b-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="ed81b-108">Das vollständige Beispiel, das weitere Transformationsbeispiele enthält, finden Sie unter [2D-Transformationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="ed81b-108">For the complete sample, which includes more transformation examples, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed81b-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed81b-109">See also</span></span>

- [<span data-ttu-id="ed81b-110">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="ed81b-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="ed81b-111">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="ed81b-111">Transforms Overview</span></span>](transforms-overview.md)
