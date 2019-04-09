---
title: 'Vorgehensweise: Anwenden einer Zeichnung auf ein 3D-Modell'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: a20b89a7359fc85d9790ac02dd2b173452df8c22
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125033"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="13e1f-102">Vorgehensweise: Anwenden einer Zeichnung auf ein 3D-Modell</span><span class="sxs-lookup"><span data-stu-id="13e1f-102">How to: Apply a Drawing to a 3-D Model</span></span>
<span data-ttu-id="13e1f-103">Dieses Beispiel zeigt, wie Sie mit einer <xref:System.Windows.Media.DrawingBrush> als die <xref:System.Windows.Media.Media3D.Material> angewendet werden, um eine [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] Modell.</span><span class="sxs-lookup"><span data-stu-id="13e1f-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="13e1f-104">Der folgende Code definiert eine <xref:System.Windows.Media.DrawingGroup> als Inhalt von einem <xref:System.Windows.Media.DrawingBrush>.</span><span class="sxs-lookup"><span data-stu-id="13e1f-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="13e1f-105">Die <xref:System.Windows.Media.DrawingBrush> festgelegt ist, als die <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> Eigenschaft der <xref:System.Windows.Media.Media3D.DiffuseMaterial> angewendet werden, um eine [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Ebene.</span><span class="sxs-lookup"><span data-stu-id="13e1f-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] plane.</span></span>  
  
 <span data-ttu-id="13e1f-106">**Hinweis**: Es ist häufig wünschenswert, komplexe Objekte und Werte wie die folgende Zeichnung als Ressourcen zu definieren, die wiederverwendet werden kann und Ihren Code vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="13e1f-106">**Note:** It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="13e1f-107">Finden Sie unter [XAML-Ressourcen](../advanced/xaml-resources.md) für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="13e1f-107">See [XAML Resources](../advanced/xaml-resources.md) for more information.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## <a name="example"></a><span data-ttu-id="13e1f-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13e1f-108">Example</span></span>  
 <span data-ttu-id="13e1f-109">Der folgende Code zeigt das gesamte Beispiel.</span><span class="sxs-lookup"><span data-stu-id="13e1f-109">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="13e1f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13e1f-110">See also</span></span>

- [<span data-ttu-id="13e1f-111">XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="13e1f-111">XAML Resources</span></span>](../advanced/xaml-resources.md)
- [<span data-ttu-id="13e1f-112">Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="13e1f-112">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="13e1f-113">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="13e1f-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="13e1f-114">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="13e1f-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
