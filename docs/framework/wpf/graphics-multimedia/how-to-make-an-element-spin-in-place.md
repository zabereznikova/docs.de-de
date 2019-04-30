---
title: 'Vorgehensweise: Drehen von Elementen ohne Positionierung'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: aca9bd577f2882e31e8d49abe5eeb5ade86f95f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947251"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="2ceb0-102">Vorgehensweise: Drehen von Elementen ohne Positionierung</span><span class="sxs-lookup"><span data-stu-id="2ceb0-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="2ceb0-103">Dieses Beispiel zeigt, wie Sie ein Element, das Starten mit einem <xref:System.Windows.Media.RotateTransform> und <xref:System.Windows.Media.Animation.DoubleAnimation>.</span><span class="sxs-lookup"><span data-stu-id="2ceb0-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="2ceb0-104">Im folgenden Beispiel wird die <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft des Elements.</span><span class="sxs-lookup"><span data-stu-id="2ceb0-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="2ceb0-105">Im Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> zum Animieren der <xref:System.Windows.Media.RotateTransform.Angle%2A> von der <xref:System.Windows.Media.RotateTransform>.</span><span class="sxs-lookup"><span data-stu-id="2ceb0-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="2ceb0-106">Damit wird das Element an der Stelle, im Beispiel wird die <xref:System.Windows.UIElement.RenderTransformOrigin%2A> Eigenschaft des Elements, das den Punkt (0,5, 0,5).</span><span class="sxs-lookup"><span data-stu-id="2ceb0-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ceb0-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2ceb0-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="2ceb0-108">Enthält weitere Beispiele für die Transformation für das vollständige Beispiel finden Sie unter [2D-Transformationen Beispiel](https://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="2ceb0-108">For the complete sample, which includes more transformation examples, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ceb0-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ceb0-109">See also</span></span>

- [<span data-ttu-id="2ceb0-110">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="2ceb0-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="2ceb0-111">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="2ceb0-111">Transforms Overview</span></span>](transforms-overview.md)
