---
title: 'Gewusst wie: Animieren von Material-Eigenschaften in einer 3D-Szene'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Material properties [WPF], animating in 3-D scenes
- animation [WPF], Material properties in 3-D scenes
- 3-D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 16d7ba089730a58106448d8a6889b362042532e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-material-properties-in-a-3-d-scene"></a><span data-ttu-id="39041-102">Gewusst wie: Animieren von Material-Eigenschaften in einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="39041-102">How to: Animate Material Properties in a 3-D Scene</span></span>
<span data-ttu-id="39041-103">In diesem Beispiel wird gezeigt, wie zum Animieren der <xref:System.Windows.Media.Brush.Opacity%2A> Eigenschaft der <xref:System.Windows.Media.Media3D.Material> angewendet, um eine [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] Modell.</span><span class="sxs-lookup"><span data-stu-id="39041-103">This example shows how to animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Media3D.Material> applied to a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="39041-104">Das folgende Codebeispiel definiert die <xref:System.Windows.Media.LinearGradientBrush> verwendet als die <xref:System.Windows.Media.Media3D.Material> auf das 3D-Objekt angewendet.</span><span class="sxs-lookup"><span data-stu-id="39041-104">The following code example defines the <xref:System.Windows.Media.LinearGradientBrush> used as the <xref:System.Windows.Media.Media3D.Material> applied to the 3D object.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 <span data-ttu-id="39041-105">Die <xref:System.Windows.Media.Brush.Opacity%2A> -Eigenschaft dieser <xref:System.Windows.Media.LinearGradientBrush> wird im folgenden Codebeispiel wird mit animiert.</span><span class="sxs-lookup"><span data-stu-id="39041-105">The <xref:System.Windows.Media.Brush.Opacity%2A> property of this <xref:System.Windows.Media.LinearGradientBrush> is animated using the code example below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="39041-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39041-106">Example</span></span>  
 <span data-ttu-id="39041-107">Der folgende Code zeigt das vollständige Beispiel.</span><span class="sxs-lookup"><span data-stu-id="39041-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="39041-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39041-108">See Also</span></span>  
 [<span data-ttu-id="39041-109">Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="39041-109">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="39041-110">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="39041-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
