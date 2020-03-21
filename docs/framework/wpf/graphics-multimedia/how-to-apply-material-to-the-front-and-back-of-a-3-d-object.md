---
title: 'Gewusst wie: Material auf die Vorder- und Rückseite eines 3D-Objekts anwenden'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 5c24879d97e7857fb07fcef4a9ba8efa901e4a39
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112140"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3d-object"></a><span data-ttu-id="77b5f-102">Gewusst wie: Material auf die Vorder- und Rückseite eines 3D-Objekts anwenden</span><span class="sxs-lookup"><span data-stu-id="77b5f-102">How to: Apply Material to the Front and Back of a 3D Object</span></span>
<span data-ttu-id="77b5f-103">Das folgende Beispiel zeigt, <xref:System.Windows.Media.Media3D.Material> wie Sie eine auf die Vorder- und Rückseite eines 3D-Objekts anwenden und das Objekt animieren, um beide Seiten des Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="77b5f-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="77b5f-104">Die <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> Eigenschaft <xref:System.Windows.Media.Media3D.GeometryModel3D> von a wird <xref:System.Windows.Media.Brush> verwendet, um ein Rot <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> auf die <xref:System.Windows.Media.Media3D.GeometryModel3D> Vorderseite des Objekts anzuwenden, und die Eigenschaft des wird verwendet, um ein Blau <xref:System.Windows.Media.Brush> auf die Rückseite des Objekts anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="77b5f-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="77b5f-105">Der folgende Code zeigt die Anwendung der Materialien auf das Objekt:</span><span class="sxs-lookup"><span data-stu-id="77b5f-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="77b5f-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77b5f-106">Example</span></span>  
 <span data-ttu-id="77b5f-107">Der folgende Code zeigt das gesamte Beispiel.</span><span class="sxs-lookup"><span data-stu-id="77b5f-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="77b5f-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="77b5f-108">See also</span></span>

- [<span data-ttu-id="77b5f-109">Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="77b5f-109">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="77b5f-110">3D-Grafikübersicht</span><span class="sxs-lookup"><span data-stu-id="77b5f-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="77b5f-111">Animieren von Materialeigenschaften in einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="77b5f-111">Animate Material Properties in a 3D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="77b5f-112">Anwenden von Emissivmaterial auf ein 3D-Objekt</span><span class="sxs-lookup"><span data-stu-id="77b5f-112">Apply Emissive Material to a 3D Object</span></span>](how-to-apply-emissive-material-to-a-3-d-object.md)
