---
title: 'Vorgehensweise: Animieren von 3D-Übersetzungen'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations
- 3-D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 6d7e0b422d6e76d5d0e25ad276550613f264e9bc
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661190"
---
# <a name="how-to-animate-3-d-translations"></a><span data-ttu-id="4b380-102">Vorgehensweise: Animieren von 3D-Übersetzungen</span><span class="sxs-lookup"><span data-stu-id="4b380-102">How to: Animate 3-D Translations</span></span>
<span data-ttu-id="4b380-103">In diesem Thema wird veranschaulicht, wie eine Übersetzungsumwandlung, legen Sie auf ein 3D-Modell animiert wird.</span><span class="sxs-lookup"><span data-stu-id="4b380-103">This topic demonstrates how to animate a translation transformation set on a 3-D model.</span></span>  
  
 <span data-ttu-id="4b380-104">Der folgende Code zeigt die Anwendung von einer <xref:System.Windows.Media.Media3D.TranslateTransform3D> -Objekt an die <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> Eigenschaft eine <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="4b380-104">The code below shows the application of a <xref:System.Windows.Media.Media3D.TranslateTransform3D> object to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 <span data-ttu-id="4b380-105">Die <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> -Eigenschaft dieses <xref:System.Windows.Media.Media3D.TranslateTransform3D> Objekt animiert wird, mit dem folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="4b380-105">The <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> property of this <xref:System.Windows.Media.Media3D.TranslateTransform3D> object is animated using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a><span data-ttu-id="4b380-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4b380-106">Example</span></span>  
 <span data-ttu-id="4b380-107">Der folgende Code zeigt das gesamte Beispiel.</span><span class="sxs-lookup"><span data-stu-id="4b380-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="4b380-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b380-108">See also</span></span>

- [<span data-ttu-id="4b380-109">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="4b380-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="4b380-110">Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="4b380-110">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="4b380-111">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="4b380-111">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="4b380-112">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="4b380-112">Transforms Overview</span></span>](transforms-overview.md)
