---
title: 'Gewusst wie: Erstellen von kombinierten Geometrien'
ms.date: 03/30/2017
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
ms.openlocfilehash: 107e0342b822633ccb4f51f256c121cc80c297f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561120"
---
# <a name="how-to-create-a-combined-geometry"></a><span data-ttu-id="d7a00-102">Gewusst wie: Erstellen von kombinierten Geometrien</span><span class="sxs-lookup"><span data-stu-id="d7a00-102">How to: Create a Combined Geometry</span></span>
<span data-ttu-id="d7a00-103">In diesem Beispiel wird gezeigt, wie Geometrien kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="d7a00-103">This example shows how to combine geometries.</span></span> <span data-ttu-id="d7a00-104">Zum Kombinieren zweier Geometrien verwenden eine <xref:System.Windows.Media.CombinedGeometry> Objekt.</span><span class="sxs-lookup"><span data-stu-id="d7a00-104">To combine two geometries, use a <xref:System.Windows.Media.CombinedGeometry> object.</span></span> <span data-ttu-id="d7a00-105">Legen Sie seine <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> Eigenschaften mit den zwei Geometrien zu kombinieren, und legen Sie die <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> Eigenschaft, die bestimmt, wie die Geometrien kombiniert werden sollen, auf `Union`, `Intersect`, `Exclude`, oder `Xor`.</span><span class="sxs-lookup"><span data-stu-id="d7a00-105">Set its <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> properties  with the two geometries to combine, and set the <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> property, which determines how the geometries will be combined together, to `Union`, `Intersect`, `Exclude`, or `Xor`.</span></span>  
  
 <span data-ttu-id="d7a00-106">Um eine zusammengesetzte Geometrie aus mindestens zwei Geometrien zu erstellen, verwenden Sie eine <xref:System.Windows.Media.GeometryGroup>.</span><span class="sxs-lookup"><span data-stu-id="d7a00-106">To create a composite geometry from two or more geometries, use a <xref:System.Windows.Media.GeometryGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7a00-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7a00-107">Example</span></span>  
 <span data-ttu-id="d7a00-108">Im folgenden Beispiel ein <xref:System.Windows.Media.CombinedGeometry> mit einem Kombinationsmodus definiert `Exclude`.</span><span class="sxs-lookup"><span data-stu-id="d7a00-108">In the following example, a <xref:System.Windows.Media.CombinedGeometry> is defined with a geometry combine mode of `Exclude`.</span></span>  <span data-ttu-id="d7a00-109">Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius, jedoch mit Rechenzentren Offset von 50 definiert.</span><span class="sxs-lookup"><span data-stu-id="d7a00-109">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 <span data-ttu-id="d7a00-110">![Ergebnisse des Exclude-Kombinationsmodus](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "Mil_task_combined_geometry_exclude")</span><span class="sxs-lookup"><span data-stu-id="d7a00-110">![Results of the Exclude combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span></span>  
<span data-ttu-id="d7a00-111">Kombinierte Geometrie ausschließen</span><span class="sxs-lookup"><span data-stu-id="d7a00-111">Combined Geometry Exclude</span></span>  
  
 <span data-ttu-id="d7a00-112">Im folgenden Markup eine <xref:System.Windows.Media.CombinedGeometry> wird definiert, mit der Kombinationsmodus `Intersect`.</span><span class="sxs-lookup"><span data-stu-id="d7a00-112">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Intersect`.</span></span>  <span data-ttu-id="d7a00-113">Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius, jedoch mit Rechenzentren Offset von 50 definiert.</span><span class="sxs-lookup"><span data-stu-id="d7a00-113">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 <span data-ttu-id="d7a00-114">![Ergebnisse des Intersect-Kombinationsmodus](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "Mil_task_combined_geometry_intersect")</span><span class="sxs-lookup"><span data-stu-id="d7a00-114">![Results of the Intersect combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span></span>  
<span data-ttu-id="d7a00-115">Intersect-kombinierte Geometrie</span><span class="sxs-lookup"><span data-stu-id="d7a00-115">Combined Geometry Intersect</span></span>  
  
 <span data-ttu-id="d7a00-116">Im folgenden Markup eine <xref:System.Windows.Media.CombinedGeometry> wird definiert, mit der Kombinationsmodus `Union`.</span><span class="sxs-lookup"><span data-stu-id="d7a00-116">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Union`.</span></span>  <span data-ttu-id="d7a00-117">Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius, jedoch mit Rechenzentren Offset von 50 definiert.</span><span class="sxs-lookup"><span data-stu-id="d7a00-117">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 <span data-ttu-id="d7a00-118">![Ergebnisse des Union-Kombinationsmodus](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "Mil_task_combined_geometry_union")</span><span class="sxs-lookup"><span data-stu-id="d7a00-118">![Results of the Union combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span></span>  
<span data-ttu-id="d7a00-119">Kombinierte Geomtrievereinigung</span><span class="sxs-lookup"><span data-stu-id="d7a00-119">Combined Geometry Union</span></span>  
  
 <span data-ttu-id="d7a00-120">Im folgenden Markup eine <xref:System.Windows.Media.CombinedGeometry> wird definiert, mit der Kombinationsmodus `Xor`.</span><span class="sxs-lookup"><span data-stu-id="d7a00-120">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Xor`.</span></span>  <span data-ttu-id="d7a00-121">Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius, jedoch mit Rechenzentren Offset von 50 definiert.</span><span class="sxs-lookup"><span data-stu-id="d7a00-121">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 <span data-ttu-id="d7a00-122">![Ergebnisse des Xor-Kombinationsmodus](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "Mil_task_combined_geometry_xor")</span><span class="sxs-lookup"><span data-stu-id="d7a00-122">![Results of the Xor combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span></span>  
<span data-ttu-id="d7a00-123">Kombinierte Geometrie Xor</span><span class="sxs-lookup"><span data-stu-id="d7a00-123">Combined Geometry Xor</span></span>
