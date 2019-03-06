---
title: 'Vorgehensweise: Erstellen von kombinierten Geometrien'
ms.date: 03/30/2017
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
ms.openlocfilehash: c5ebe87abd4c2cf70f8fa17f1fcc773293f3ad27
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364787"
---
# <a name="how-to-create-a-combined-geometry"></a><span data-ttu-id="f5bfc-102">Vorgehensweise: Erstellen von kombinierten Geometrien</span><span class="sxs-lookup"><span data-stu-id="f5bfc-102">How to: Create a Combined Geometry</span></span>
<span data-ttu-id="f5bfc-103">Dieses Beispiel zeigt, wie Geometrien kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="f5bfc-103">This example shows how to combine geometries.</span></span> <span data-ttu-id="f5bfc-104">Zum Kombinieren zweier Geometrien verwenden eine <xref:System.Windows.Media.CombinedGeometry> Objekt.</span><span class="sxs-lookup"><span data-stu-id="f5bfc-104">To combine two geometries, use a <xref:System.Windows.Media.CombinedGeometry> object.</span></span> <span data-ttu-id="f5bfc-105">Legen Sie seine <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> Eigenschaften mit die beiden Geometrien zu kombinieren, und legen Sie die <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> Eigenschaft, die bestimmt, wie die Geometrien kombiniert werden sollen, zu `Union`, `Intersect`, `Exclude`, oder `Xor`.</span><span class="sxs-lookup"><span data-stu-id="f5bfc-105">Set its <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> properties  with the two geometries to combine, and set the <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> property, which determines how the geometries will be combined together, to `Union`, `Intersect`, `Exclude`, or `Xor`.</span></span>  
  
 <span data-ttu-id="f5bfc-106">Um eine zusammengesetzte Geometrie aus mindestens zwei Geometrien erstellen, verwenden Sie eine <xref:System.Windows.Media.GeometryGroup>.</span><span class="sxs-lookup"><span data-stu-id="f5bfc-106">To create a composite geometry from two or more geometries, use a <xref:System.Windows.Media.GeometryGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5bfc-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f5bfc-107">Example</span></span>  
 <span data-ttu-id="f5bfc-108">Im folgenden Beispiel eine <xref:System.Windows.Media.CombinedGeometry> wird definiert, mit einem Kombinationsmodus `Exclude`.</span><span class="sxs-lookup"><span data-stu-id="f5bfc-108">In the following example, a <xref:System.Windows.Media.CombinedGeometry> is defined with a geometry combine mode of `Exclude`.</span></span>  <span data-ttu-id="f5bfc-109">Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius, aber deren Mittelpunkte von 50 definiert.</span><span class="sxs-lookup"><span data-stu-id="f5bfc-109">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 <span data-ttu-id="f5bfc-110">![Ergebnisse des Exclude-Kombinationsmodus](./media/mil-task-combined-geometry-exclude.PNG "Mil_task_combined_geometry_exclude")</span><span class="sxs-lookup"><span data-stu-id="f5bfc-110">![Results of the Exclude combine mode](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span></span>  
<span data-ttu-id="f5bfc-111">Ausschließen von kombinierten Geometrien</span><span class="sxs-lookup"><span data-stu-id="f5bfc-111">Combined Geometry Exclude</span></span>  
  
 <span data-ttu-id="f5bfc-112">Im folgenden Markup ein <xref:System.Windows.Media.CombinedGeometry> wird definiert, wobei der Kombinationsmodus von `Intersect`.</span><span class="sxs-lookup"><span data-stu-id="f5bfc-112">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Intersect`.</span></span>  <span data-ttu-id="f5bfc-113">Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius, aber deren Mittelpunkte von 50 definiert.</span><span class="sxs-lookup"><span data-stu-id="f5bfc-113">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 <span data-ttu-id="f5bfc-114">![Ergebnisse des Intersect-Kombinationsmodus](./media/mil-task-combined-geometry-intersect.PNG "Mil_task_combined_geometry_intersect")</span><span class="sxs-lookup"><span data-stu-id="f5bfc-114">![Results of the Intersect combine mode](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span></span>  
<span data-ttu-id="f5bfc-115">Schneiden von kombinierten Geometrien</span><span class="sxs-lookup"><span data-stu-id="f5bfc-115">Combined Geometry Intersect</span></span>  
  
 <span data-ttu-id="f5bfc-116">Im folgenden Markup ein <xref:System.Windows.Media.CombinedGeometry> wird definiert, wobei der Kombinationsmodus von `Union`.</span><span class="sxs-lookup"><span data-stu-id="f5bfc-116">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Union`.</span></span>  <span data-ttu-id="f5bfc-117">Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius, aber deren Mittelpunkte von 50 definiert.</span><span class="sxs-lookup"><span data-stu-id="f5bfc-117">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 <span data-ttu-id="f5bfc-118">![Ergebnisse des Union-Kombinationsmodus](./media/mil-task-combined-geometry-union.PNG "Mil_task_combined_geometry_union")</span><span class="sxs-lookup"><span data-stu-id="f5bfc-118">![Results of the Union combine mode](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span></span>  
<span data-ttu-id="f5bfc-119">Union von kombinierten Geometrien</span><span class="sxs-lookup"><span data-stu-id="f5bfc-119">Combined Geometry Union</span></span>  
  
 <span data-ttu-id="f5bfc-120">Im folgenden Markup ein <xref:System.Windows.Media.CombinedGeometry> wird definiert, wobei der Kombinationsmodus von `Xor`.</span><span class="sxs-lookup"><span data-stu-id="f5bfc-120">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Xor`.</span></span>  <span data-ttu-id="f5bfc-121">Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius, aber deren Mittelpunkte von 50 definiert.</span><span class="sxs-lookup"><span data-stu-id="f5bfc-121">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 <span data-ttu-id="f5bfc-122">![Ergebnisse des Xor-Kombinationsmodus](./media/mil-task-combined-geometry-xor.PNG "Mil_task_combined_geometry_xor")</span><span class="sxs-lookup"><span data-stu-id="f5bfc-122">![Results of the Xor combine mode](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span></span>  
<span data-ttu-id="f5bfc-123">Xor von kombinierten Geometrien</span><span class="sxs-lookup"><span data-stu-id="f5bfc-123">Combined Geometry Xor</span></span>
