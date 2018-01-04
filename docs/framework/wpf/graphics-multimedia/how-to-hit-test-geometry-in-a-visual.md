---
title: "Gewusst wie: Treffertest für eine Geometrie in einem visuellen Objekt"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a990a43853e375c1c97f88dc6792932ad64c8d37
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a><span data-ttu-id="bed96-102">Gewusst wie: Treffertest für eine Geometrie in einem visuellen Objekt</span><span class="sxs-lookup"><span data-stu-id="bed96-102">How to: Hit Test Geometry in a Visual</span></span>
<span data-ttu-id="bed96-103">In diesem Beispiel wird gezeigt, wie einen Treffertest für ein visuelles Objekt ausführen, der einem oder mehreren besteht <xref:System.Windows.Media.Geometry> Objekte.</span><span class="sxs-lookup"><span data-stu-id="bed96-103">This example shows how to perform a hit test on a visual object that is composed of one or more <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bed96-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bed96-104">Example</span></span>  
 <span data-ttu-id="bed96-105">Im folgende Beispiel wird gezeigt, wie zum Abrufen der <xref:System.Windows.Media.DrawingGroup> aus ein visuelles Objekt, das verwendet die <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="bed96-105">The following example shows how to retrieve the <xref:System.Windows.Media.DrawingGroup> from a visual object that uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method.</span></span> <span data-ttu-id="bed96-106">Ein Treffertest erfolgt klicken Sie dann auf den gerenderten Inhalt der einzelnen Zeichnen in die <xref:System.Windows.Media.DrawingGroup> um zu bestimmen, welche Geometrie geklickt wurde.</span><span class="sxs-lookup"><span data-stu-id="bed96-106">A hit test is then performed on the rendered content of each drawing in the <xref:System.Windows.Media.DrawingGroup> to determine which geometry was hit.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bed96-107">In den meisten Fällen verwenden Sie die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methode, um zu bestimmen, ob ein Punkt mit den gerenderten Inhalt eines visuellen überschneidet.</span><span class="sxs-lookup"><span data-stu-id="bed96-107">In most cases, you would use the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method to determine whether a point intersects any of the rendered content of a visual.</span></span>  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 <span data-ttu-id="bed96-108">Die <xref:System.Windows.Media.Geometry.FillContains%2A> Methode ist eine überladene Methode, die Ihnen ermöglicht, den ein Treffertest mithilfe eines angegebenen <xref:System.Windows.Point> oder <xref:System.Windows.Media.Geometry>.</span><span class="sxs-lookup"><span data-stu-id="bed96-108">The <xref:System.Windows.Media.Geometry.FillContains%2A> method is an overloaded method that allows you to hit test by using a specified <xref:System.Windows.Point> or <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="bed96-109">Wenn eine Geometrie gestrichelt ist, kann die Strichelung ggf. über die Füllbereichsgrenzen hinaus reichen.</span><span class="sxs-lookup"><span data-stu-id="bed96-109">If a geometry is stroked, the stroke can extend outside the fill bounds.</span></span> <span data-ttu-id="bed96-110">Sie möchten in diesem Fall rufen <xref:System.Windows.Media.Geometry.StrokeContains%2A> zusätzlich zu <xref:System.Windows.Media.Geometry.FillContains%2A>.</span><span class="sxs-lookup"><span data-stu-id="bed96-110">In which case, you may want to call <xref:System.Windows.Media.Geometry.StrokeContains%2A> in addition to <xref:System.Windows.Media.Geometry.FillContains%2A>.</span></span>  
  
 <span data-ttu-id="bed96-111">Sie können auch angeben einer <xref:System.Windows.Media.ToleranceType> , die im Rahmen der Bézier-reduzieren verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bed96-111">You can also provide a <xref:System.Windows.Media.ToleranceType> that is used for the purposes of Bezier flattening.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bed96-112">Bei diesem Beispiel werden keine Clippings oder Transformationen berücksichtigt, die ggf. auf die Geometrie angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="bed96-112">This sample does not take into account any transforms or clipping that may be applied to the geometry.</span></span> <span data-ttu-id="bed96-113">Außerdem funktioniert dieses Beispiel nicht mit einem formatierten Steuerelement, da diesem keine Zeichnungen direkt zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="bed96-113">In addition, this sample will not work with a styled control, since it does not have any drawings directly associated with it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bed96-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bed96-114">See Also</span></span>  
 [<span data-ttu-id="bed96-115">Treffertests in der visuellen Ebene</span><span class="sxs-lookup"><span data-stu-id="bed96-115">Hit Testing in the Visual Layer</span></span>](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [<span data-ttu-id="bed96-116">Treffertest mit Geometrie als Parameter</span><span class="sxs-lookup"><span data-stu-id="bed96-116">Hit Test Using Geometry as a Parameter</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-using-geometry-as-a-parameter.md)
