---
title: 'Vorgehensweise: Transformieren der Skalierung eines 3D-Modells'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3-D objects
- 3-D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: 6d668de08201d819ce9f8752bedf6c388a6bc718
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165081"
---
# <a name="how-to-transform-the-scale-of-a-3-d-model"></a><span data-ttu-id="ab536-102">Vorgehensweise: Transformieren der Skalierung eines 3D-Modells</span><span class="sxs-lookup"><span data-stu-id="ab536-102">How to: Transform the Scale of a 3-D Model</span></span>
<span data-ttu-id="ab536-103">Dieses Beispiel zeigt, wie Sie ein 3D-Objekt zu skalieren.</span><span class="sxs-lookup"><span data-stu-id="ab536-103">This example shows how to scale a 3-D object.</span></span> <span data-ttu-id="ab536-104">Um ein 3D-Objekt skalieren zu können, verwendet eine <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span><span class="sxs-lookup"><span data-stu-id="ab536-104">To scale a 3-D object, use a <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span></span> <span data-ttu-id="ab536-105">Die <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, und <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> Eigenschaften Größe des Elements geändert, um den Faktor, die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="ab536-105">The <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, and <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> properties resize the element by the factor you specify.</span></span> <span data-ttu-id="ab536-106">Z. B. eine <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> Wert von 1,5 wird ein Objekt auf 150 Prozent der ursprünglichen Breite gestreckt.</span><span class="sxs-lookup"><span data-stu-id="ab536-106">For example, a <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> value of 1.5 stretches an object to 150 percent of its original width.</span></span> <span data-ttu-id="ab536-107">Ein <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> Wert von 0,5 verringert sich die Höhe eines Objekts, aufgerufen werden, um 50 Prozent.</span><span class="sxs-lookup"><span data-stu-id="ab536-107">A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> value of 0.5 shrinks the height of an object by 50 percent.</span></span> <span data-ttu-id="ab536-108">Der folgende Code zeigt die Verwendung einer <xref:System.Windows.Media.Media3D.ScaleTransform3D> als Transformation für einen <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="ab536-108">The code below shows using a <xref:System.Windows.Media.Media3D.ScaleTransform3D> as the transform for a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="ab536-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ab536-109">Example</span></span>  
 <span data-ttu-id="ab536-110">Der folgende Code zeigt das gesamte Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ab536-110">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="ab536-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab536-111">See also</span></span>

- [<span data-ttu-id="ab536-112">Animieren von 3D-Übersetzungen</span><span class="sxs-lookup"><span data-stu-id="ab536-112">Animate 3-D Translations</span></span>](how-to-animate-3-d-translations.md)
- [<span data-ttu-id="ab536-113">Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="ab536-113">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="ab536-114">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="ab536-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
