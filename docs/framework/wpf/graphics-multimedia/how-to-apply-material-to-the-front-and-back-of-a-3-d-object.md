---
title: 'Vorgehensweise: Anwenden von Material auf die Vorder- und Rückseite eines 3D-Objekts'
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3-D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 16f30e3a880d7dcc943a9583ba0f04c4bd682827
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652032"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3-d-object"></a><span data-ttu-id="6250f-102">Vorgehensweise: Anwenden von Material auf die Vorder- und Rückseite eines 3D-Objekts</span><span class="sxs-lookup"><span data-stu-id="6250f-102">How to: Apply Material to the Front and Back of a 3-D Object</span></span>
<span data-ttu-id="6250f-103">Das folgende Beispiel zeigt, wie Sie Anwenden einer <xref:System.Windows.Media.Media3D.Material> auf die Vorder- und Rückseite eines 3D-Objekts Objekt aus, und das Objekt zum Anzeigen von beiden Seiten des Objekts animieren.</span><span class="sxs-lookup"><span data-stu-id="6250f-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3-D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="6250f-104">Die <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> Eigenschaft eine <xref:System.Windows.Media.Media3D.GeometryModel3D> dient zum Anwenden von eines rotes <xref:System.Windows.Media.Brush> , die auf der Vorderseite des Objekts und die <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> Eigenschaft der <xref:System.Windows.Media.Media3D.GeometryModel3D> wird verwendet, um ein blaues anwenden <xref:System.Windows.Media.Brush> auf die Rückseite des Objekts.</span><span class="sxs-lookup"><span data-stu-id="6250f-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="6250f-105">Der folgende Code zeigt die Anwendung der Materialien auf das Objekt:</span><span class="sxs-lookup"><span data-stu-id="6250f-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="6250f-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6250f-106">Example</span></span>  
 <span data-ttu-id="6250f-107">Der folgende Code zeigt das gesamte Beispiel.</span><span class="sxs-lookup"><span data-stu-id="6250f-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="6250f-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6250f-108">See also</span></span>
- [<span data-ttu-id="6250f-109">Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="6250f-109">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="6250f-110">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="6250f-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [<span data-ttu-id="6250f-111">Animieren von Material-Eigenschaften in einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="6250f-111">Animate Material Properties in a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="6250f-112">Anwenden von Emissive Material auf ein 3D-Objekt</span><span class="sxs-lookup"><span data-stu-id="6250f-112">Apply Emissive Material to a 3-D Object</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)
