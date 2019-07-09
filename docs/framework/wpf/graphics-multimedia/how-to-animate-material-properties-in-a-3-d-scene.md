---
title: 'Vorgehensweise: Animieren von Materialeigenschaften in einer 3D-Szene'
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3-D scenes
- animation [WPF], Material properties in 3-D scenes
- 3-D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: 8dfd7f01b87e2becfbcf57544ec4f8340cf8d5cc
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662551"
---
# <a name="how-to-animate-material-properties-in-a-3-d-scene"></a><span data-ttu-id="9bced-102">Vorgehensweise: Animieren von Materialeigenschaften in einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="9bced-102">How to: Animate Material Properties in a 3-D Scene</span></span>
<span data-ttu-id="9bced-103">Dieses Beispiel zeigt, wie Sie animieren der <xref:System.Windows.Media.Brush.Opacity%2A> Eigenschaft der <xref:System.Windows.Media.Media3D.Material> auf ein 3D-Modell angewendet.</span><span class="sxs-lookup"><span data-stu-id="9bced-103">This example shows how to animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Media3D.Material> applied to a 3-D model.</span></span>  
  
 <span data-ttu-id="9bced-104">Das folgende Codebeispiel definiert die <xref:System.Windows.Media.LinearGradientBrush> verwendet als die <xref:System.Windows.Media.Media3D.Material> auf das 3D-Objekt angewendet.</span><span class="sxs-lookup"><span data-stu-id="9bced-104">The following code example defines the <xref:System.Windows.Media.LinearGradientBrush> used as the <xref:System.Windows.Media.Media3D.Material> applied to the 3D object.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 <span data-ttu-id="9bced-105">Die <xref:System.Windows.Media.Brush.Opacity%2A> -Eigenschaft dieses <xref:System.Windows.Media.LinearGradientBrush> wird im folgenden Codebeispiel wird mithilfe animiert.</span><span class="sxs-lookup"><span data-stu-id="9bced-105">The <xref:System.Windows.Media.Brush.Opacity%2A> property of this <xref:System.Windows.Media.LinearGradientBrush> is animated using the code example below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="9bced-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9bced-106">Example</span></span>  
 <span data-ttu-id="9bced-107">Der folgende Code zeigt das gesamte Beispiel.</span><span class="sxs-lookup"><span data-stu-id="9bced-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="9bced-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9bced-108">See also</span></span>

- [<span data-ttu-id="9bced-109">Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="9bced-109">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="9bced-110">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="9bced-110">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
