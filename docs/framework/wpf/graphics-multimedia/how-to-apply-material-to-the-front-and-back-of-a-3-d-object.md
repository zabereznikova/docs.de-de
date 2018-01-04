---
title: "Gewusst wie: Anwenden von Material auf die Vorder- und Rückseite eines 3D-Objekts"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 3-D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3-D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c5ead8805c3d16bc16e259bdf90a19f05500563c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3-d-object"></a><span data-ttu-id="5b874-102">Gewusst wie: Anwenden von Material auf die Vorder- und Rückseite eines 3D-Objekts</span><span class="sxs-lookup"><span data-stu-id="5b874-102">How to: Apply Material to the Front and Back of a 3-D Object</span></span>
<span data-ttu-id="5b874-103">Im folgende Beispiel wird gezeigt, wie zum Anwenden einer <xref:System.Windows.Media.Media3D.Material> in den Vordergrund und Rückseite eine 3D-Objekt und das Objekt zum Anzeigen von beiden Seiten des Objekts animiert.</span><span class="sxs-lookup"><span data-stu-id="5b874-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3-D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="5b874-104">Die <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> Eigenschaft eine <xref:System.Windows.Media.Media3D.GeometryModel3D> wird verwendet, um einen roten gelten <xref:System.Windows.Media.Brush> auf der Vorderseite des Objekts und die <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> Eigenschaft der <xref:System.Windows.Media.Media3D.GeometryModel3D> wird verwendet, um ein blaues anwenden <xref:System.Windows.Media.Brush> auf der Rückseite des Objekts.</span><span class="sxs-lookup"><span data-stu-id="5b874-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="5b874-105">Der folgende Code zeigt die Anwendung der Materialien auf das Objekt:</span><span class="sxs-lookup"><span data-stu-id="5b874-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="5b874-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5b874-106">Example</span></span>  
 <span data-ttu-id="5b874-107">Der folgende Code zeigt das vollständige Beispiel.</span><span class="sxs-lookup"><span data-stu-id="5b874-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="5b874-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b874-108">See Also</span></span>  
 [<span data-ttu-id="5b874-109">Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="5b874-109">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="5b874-110">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="5b874-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="5b874-111">Animieren von Material-Eigenschaften in einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="5b874-111">Animate Material Properties in a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)  
 [<span data-ttu-id="5b874-112">Anwenden von Emissive Material auf ein 3D-Objekt</span><span class="sxs-lookup"><span data-stu-id="5b874-112">Apply Emissive Material to a 3-D Object</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)
