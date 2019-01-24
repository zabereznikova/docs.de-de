---
title: 'Vorgehensweise: Anwenden einer Zeichnung auf ein 3D-Modell'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 07811f8c0326827ed90484ce12632589b2f6fc82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611240"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="715fe-102">Vorgehensweise: Anwenden einer Zeichnung auf ein 3D-Modell</span><span class="sxs-lookup"><span data-stu-id="715fe-102">How to: Apply a Drawing to a 3-D Model</span></span>
<span data-ttu-id="715fe-103">Dieses Beispiel zeigt, wie Sie mit einer <xref:System.Windows.Media.DrawingBrush> als die <xref:System.Windows.Media.Media3D.Material> angewendet werden, um eine [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] Modell.</span><span class="sxs-lookup"><span data-stu-id="715fe-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="715fe-104">Der folgende Code definiert eine <xref:System.Windows.Media.DrawingGroup> als Inhalt von einem <xref:System.Windows.Media.DrawingBrush>.</span><span class="sxs-lookup"><span data-stu-id="715fe-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="715fe-105">Die <xref:System.Windows.Media.DrawingBrush> festgelegt ist, als die <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> Eigenschaft der <xref:System.Windows.Media.Media3D.DiffuseMaterial> angewendet werden, um eine [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Ebene.</span><span class="sxs-lookup"><span data-stu-id="715fe-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] plane.</span></span>  
  
 <span data-ttu-id="715fe-106">**Hinweis**: Es ist häufig wünschenswert, komplexe Objekte und Werte wie die folgende Zeichnung als Ressourcen zu definieren, die wiederverwendet werden kann und Ihren Code vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="715fe-106">**Note:** It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="715fe-107">Finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md) für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="715fe-107">See [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md) for more information.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## <a name="example"></a><span data-ttu-id="715fe-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="715fe-108">Example</span></span>  
 <span data-ttu-id="715fe-109">Der folgende Code zeigt das gesamte Beispiel.</span><span class="sxs-lookup"><span data-stu-id="715fe-109">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="715fe-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="715fe-110">See also</span></span>
- [<span data-ttu-id="715fe-111">XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="715fe-111">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)
- [<span data-ttu-id="715fe-112">Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="715fe-112">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="715fe-113">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="715fe-113">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="715fe-114">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="715fe-114">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
