---
title: 'Gewusst wie: Transformieren der Skalierung eines 3D-Modells'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scaling [WPF], 3-D objects
- 3-D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d94086f38169ee31cbee29e034359d573462ffca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-transform-the-scale-of-a-3-d-model"></a><span data-ttu-id="64c3c-102">Gewusst wie: Transformieren der Skalierung eines 3D-Modells</span><span class="sxs-lookup"><span data-stu-id="64c3c-102">How to: Transform the Scale of a 3-D Model</span></span>
<span data-ttu-id="64c3c-103">In diesem Beispiel wird gezeigt, wie ein 3D-Objekt skaliert wird.</span><span class="sxs-lookup"><span data-stu-id="64c3c-103">This example shows how to scale a 3-D object.</span></span> <span data-ttu-id="64c3c-104">Wenn ein 3D-Objekt skaliert werden sollen, verwenden Sie eine <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span><span class="sxs-lookup"><span data-stu-id="64c3c-104">To scale a 3-D object, use a <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span></span> <span data-ttu-id="64c3c-105">Die <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, und <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> Eigenschaften Größe des Elements geändert, durch den Faktor, die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="64c3c-105">The <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, and <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> properties resize the element by the factor you specify.</span></span> <span data-ttu-id="64c3c-106">Angenommen, ein <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> Wert von 1,5 gestreckt wird, ein Objekt auf 150 Prozent der ursprünglichen Breite.</span><span class="sxs-lookup"><span data-stu-id="64c3c-106">For example, a <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> value of 1.5 stretches an object to 150 percent of its original width.</span></span> <span data-ttu-id="64c3c-107">Ein <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> Wert von 0,5 verkleinert die Höhe eines Objekts um 50 Prozent.</span><span class="sxs-lookup"><span data-stu-id="64c3c-107">A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> value of 0.5 shrinks the height of an object by 50 percent.</span></span> <span data-ttu-id="64c3c-108">Der folgende Code zeigt die Verwendung einer <xref:System.Windows.Media.Media3D.ScaleTransform3D> als Transformation für ein <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="64c3c-108">The code below shows using a <xref:System.Windows.Media.Media3D.ScaleTransform3D> as the transform for a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="64c3c-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="64c3c-109">Example</span></span>  
 <span data-ttu-id="64c3c-110">Der folgende Code zeigt das vollständige Beispiel.</span><span class="sxs-lookup"><span data-stu-id="64c3c-110">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="64c3c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64c3c-111">See Also</span></span>  
 [<span data-ttu-id="64c3c-112">Animieren von 3D-Übersetzungen</span><span class="sxs-lookup"><span data-stu-id="64c3c-112">Animate 3-D Translations</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-3-d-translations.md)  
 [<span data-ttu-id="64c3c-113">Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="64c3c-113">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="64c3c-114">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="64c3c-114">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
