---
title: 'Vorgehensweise: Treffertest für eine Geometrie in einem visuellen Objekt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
ms.openlocfilehash: 87b626e575d889447ef061d1ed62ef28efe5dfeb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227339"
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a><span data-ttu-id="16b7a-102">Vorgehensweise: Treffertest für eine Geometrie in einem visuellen Objekt</span><span class="sxs-lookup"><span data-stu-id="16b7a-102">How to: Hit Test Geometry in a Visual</span></span>
<span data-ttu-id="16b7a-103">Dieses Beispiel zeigt, wie Sie einen Treffertest für ein visuelles Objekt durchführen, das von einem oder mehreren besteht <xref:System.Windows.Media.Geometry> Objekte.</span><span class="sxs-lookup"><span data-stu-id="16b7a-103">This example shows how to perform a hit test on a visual object that is composed of one or more <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16b7a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="16b7a-104">Example</span></span>  
 <span data-ttu-id="16b7a-105">Das folgende Beispiel zeigt das Abrufen der <xref:System.Windows.Media.DrawingGroup> aus einem visuellen Objekt, das verwendet die <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="16b7a-105">The following example shows how to retrieve the <xref:System.Windows.Media.DrawingGroup> from a visual object that uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method.</span></span> <span data-ttu-id="16b7a-106">Ein Treffertest erfolgt klicken Sie dann auf den gerenderten Inhalt der einzelnen Zeichnungen in der <xref:System.Windows.Media.DrawingGroup> um zu bestimmen, welche Geometrie getroffen wurde.</span><span class="sxs-lookup"><span data-stu-id="16b7a-106">A hit test is then performed on the rendered content of each drawing in the <xref:System.Windows.Media.DrawingGroup> to determine which geometry was hit.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16b7a-107">In den meisten Fällen verwenden Sie die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methode, um zu bestimmen, ob ein Punkt innerhalb des gerenderten Inhalts eines visuellen Objekts liegt.</span><span class="sxs-lookup"><span data-stu-id="16b7a-107">In most cases, you would use the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method to determine whether a point intersects any of the rendered content of a visual.</span></span>  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 <span data-ttu-id="16b7a-108">Die <xref:System.Windows.Media.Geometry.FillContains%2A> Methode ist eine überladene Methode, die Ihnen ermöglicht, den ein Treffertest mithilfe eines angegebenen <xref:System.Windows.Point> oder <xref:System.Windows.Media.Geometry>.</span><span class="sxs-lookup"><span data-stu-id="16b7a-108">The <xref:System.Windows.Media.Geometry.FillContains%2A> method is an overloaded method that allows you to hit test by using a specified <xref:System.Windows.Point> or <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="16b7a-109">Wenn eine Geometrie gestrichelt ist, kann die Strichelung ggf. über die Füllbereichsgrenzen hinaus reichen.</span><span class="sxs-lookup"><span data-stu-id="16b7a-109">If a geometry is stroked, the stroke can extend outside the fill bounds.</span></span> <span data-ttu-id="16b7a-110">Sie möchten in diesem Fall rufen <xref:System.Windows.Media.Geometry.StrokeContains%2A> zusätzlich zu <xref:System.Windows.Media.Geometry.FillContains%2A>.</span><span class="sxs-lookup"><span data-stu-id="16b7a-110">In which case, you may want to call <xref:System.Windows.Media.Geometry.StrokeContains%2A> in addition to <xref:System.Windows.Media.Geometry.FillContains%2A>.</span></span>  
  
 <span data-ttu-id="16b7a-111">Sie bieten auch eine <xref:System.Windows.Media.ToleranceType> , die im Rahmen der Bezier vereinfachen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="16b7a-111">You can also provide a <xref:System.Windows.Media.ToleranceType> that is used for the purposes of Bezier flattening.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16b7a-112">Bei diesem Beispiel werden keine Clippings oder Transformationen berücksichtigt, die ggf. auf die Geometrie angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="16b7a-112">This sample does not take into account any transforms or clipping that may be applied to the geometry.</span></span> <span data-ttu-id="16b7a-113">Außerdem funktioniert dieses Beispiel nicht mit einem formatierten Steuerelement, da diesem keine Zeichnungen direkt zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="16b7a-113">In addition, this sample will not work with a styled control, since it does not have any drawings directly associated with it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b7a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16b7a-114">See also</span></span>

- [<span data-ttu-id="16b7a-115">Treffertests in der visuellen Ebene</span><span class="sxs-lookup"><span data-stu-id="16b7a-115">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="16b7a-116">Treffertest mit Geometrie als Parameter</span><span class="sxs-lookup"><span data-stu-id="16b7a-116">Hit Test Using Geometry as a Parameter</span></span>](how-to-hit-test-using-geometry-as-a-parameter.md)
