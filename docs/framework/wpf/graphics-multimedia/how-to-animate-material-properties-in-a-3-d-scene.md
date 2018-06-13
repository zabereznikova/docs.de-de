---
title: 'Gewusst wie: Animieren von Material-Eigenschaften in einer 3D-Szene'
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3-D scenes
- animation [WPF], Material properties in 3-D scenes
- 3-D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: ed4bbb3b22b09c24ed40b72a483db38b35038759
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559051"
---
# <a name="how-to-animate-material-properties-in-a-3-d-scene"></a><span data-ttu-id="10545-102">Gewusst wie: Animieren von Material-Eigenschaften in einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="10545-102">How to: Animate Material Properties in a 3-D Scene</span></span>
<span data-ttu-id="10545-103">In diesem Beispiel wird gezeigt, wie zum Animieren der <xref:System.Windows.Media.Brush.Opacity%2A> Eigenschaft der <xref:System.Windows.Media.Media3D.Material> angewendet, um eine [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] Modell.</span><span class="sxs-lookup"><span data-stu-id="10545-103">This example shows how to animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Media3D.Material> applied to a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="10545-104">Das folgende Codebeispiel definiert die <xref:System.Windows.Media.LinearGradientBrush> verwendet als die <xref:System.Windows.Media.Media3D.Material> auf das 3D-Objekt angewendet.</span><span class="sxs-lookup"><span data-stu-id="10545-104">The following code example defines the <xref:System.Windows.Media.LinearGradientBrush> used as the <xref:System.Windows.Media.Media3D.Material> applied to the 3D object.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 <span data-ttu-id="10545-105">Die <xref:System.Windows.Media.Brush.Opacity%2A> -Eigenschaft dieser <xref:System.Windows.Media.LinearGradientBrush> wird im folgenden Codebeispiel wird mit animiert.</span><span class="sxs-lookup"><span data-stu-id="10545-105">The <xref:System.Windows.Media.Brush.Opacity%2A> property of this <xref:System.Windows.Media.LinearGradientBrush> is animated using the code example below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="10545-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10545-106">Example</span></span>  
 <span data-ttu-id="10545-107">Der folgende Code zeigt das vollständige Beispiel.</span><span class="sxs-lookup"><span data-stu-id="10545-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="10545-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10545-108">See Also</span></span>  
 [<span data-ttu-id="10545-109">Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="10545-109">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="10545-110">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="10545-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
