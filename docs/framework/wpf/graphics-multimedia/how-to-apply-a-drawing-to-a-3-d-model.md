---
title: 'Vorgehensweise: Anwenden einer Zeichnung auf ein 3D-Modell'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 8ac24fdf8d7e407e10764c17fcc12121aa5f51d7
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662811"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="24051-102">Vorgehensweise: Anwenden einer Zeichnung auf ein 3D-Modell</span><span class="sxs-lookup"><span data-stu-id="24051-102">How to: Apply a Drawing to a 3-D Model</span></span>
<span data-ttu-id="24051-103">Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.DrawingBrush> als die <xref:System.Windows.Media.Media3D.Material> auf ein 3D-Modell angewendet.</span><span class="sxs-lookup"><span data-stu-id="24051-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3-D model.</span></span>  
  
 <span data-ttu-id="24051-104">Der folgende Code definiert eine <xref:System.Windows.Media.DrawingGroup> als Inhalt von einem <xref:System.Windows.Media.DrawingBrush>.</span><span class="sxs-lookup"><span data-stu-id="24051-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="24051-105">Die <xref:System.Windows.Media.DrawingBrush> festgelegt ist, als die <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> Eigenschaft der <xref:System.Windows.Media.Media3D.DiffuseMaterial> auf eine 3-d-Ebene angewendet.</span><span class="sxs-lookup"><span data-stu-id="24051-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3-D plane.</span></span>  
  
 <span data-ttu-id="24051-106">**Hinweis**: Es ist häufig wünschenswert, komplexe Objekte und Werte wie die folgende Zeichnung als Ressourcen zu definieren, die wiederverwendet werden kann und Ihren Code vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="24051-106">**Note:** It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="24051-107">Finden Sie unter [XAML-Ressourcen](../advanced/xaml-resources.md) für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="24051-107">See [XAML Resources](../advanced/xaml-resources.md) for more information.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## <a name="example"></a><span data-ttu-id="24051-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="24051-108">Example</span></span>  
 <span data-ttu-id="24051-109">Der folgende Code zeigt das gesamte Beispiel.</span><span class="sxs-lookup"><span data-stu-id="24051-109">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="24051-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24051-110">See also</span></span>

- [<span data-ttu-id="24051-111">XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="24051-111">XAML Resources</span></span>](../advanced/xaml-resources.md)
- [<span data-ttu-id="24051-112">Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="24051-112">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="24051-113">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="24051-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="24051-114">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="24051-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
