---
title: 'Gewusst wie: Anwenden von EmissiveMaterial auf ein 3D-Objekt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3-D objects
- 3-D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: da2c8c5d488afd02b50cfeee70048e6fa619248c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559420"
---
# <a name="how-to-apply-emissive-material-to-a-3-d-object"></a><span data-ttu-id="b8a03-102">Gewusst wie: Anwenden von EmissiveMaterial auf ein 3D-Objekt</span><span class="sxs-lookup"><span data-stu-id="b8a03-102">How to: Apply Emissive Material to a 3-D Object</span></span>
<span data-ttu-id="b8a03-103">Das folgende Beispiel zeigt, wie Sie <xref:System.Windows.Media.Media3D.EmissiveMaterial> auf ein vorhandenes Material, das die Farbe des Pinsels EmissiveMaterial gleich Farbe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b8a03-103">The following example shows how to use <xref:System.Windows.Media.Media3D.EmissiveMaterial> to add color to an existing Material equal to the color of the EmissiveMaterial's brush.</span></span> <span data-ttu-id="b8a03-104">Der folgende Code zeigt <xref:System.Windows.Media.Media3D.DiffuseMaterial> und <xref:System.Windows.Media.Media3D.EmissiveMaterial> in Kombination der DiffuseMaterial Darstellung Blau hinzuzufügende angewendet.</span><span class="sxs-lookup"><span data-stu-id="b8a03-104">The code below shows <xref:System.Windows.Media.Media3D.DiffuseMaterial> and <xref:System.Windows.Media.Media3D.EmissiveMaterial> applied in combination to add blue to the DiffuseMaterial's appearance.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 <span data-ttu-id="b8a03-105">In prozeduralem Code:</span><span class="sxs-lookup"><span data-stu-id="b8a03-105">In procedural code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="b8a03-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8a03-106">Example</span></span>  
 <span data-ttu-id="b8a03-107">Der folgende Code zeigt das gesamte Beispiel in XAML.</span><span class="sxs-lookup"><span data-stu-id="b8a03-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="b8a03-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8a03-108">Example</span></span>  
 <span data-ttu-id="b8a03-109">Im folgenden wird das gesamte Beispiel in prozeduralem Code ein.</span><span class="sxs-lookup"><span data-stu-id="b8a03-109">Below is the entire sample in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b8a03-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8a03-110">See Also</span></span>  
 [<span data-ttu-id="b8a03-111">Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="b8a03-111">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="b8a03-112">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="b8a03-112">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="b8a03-113">Animieren von Material-Eigenschaften in einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="b8a03-113">Animate Material Properties in a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)  
 [<span data-ttu-id="b8a03-114">Anwenden von Material auf die Vorder- und Rückseite eines 3D-Objekts</span><span class="sxs-lookup"><span data-stu-id="b8a03-114">Apply Material to the Front and Back of a 3-D Object</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
