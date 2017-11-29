---
title: 'Gewusst wie: Erstellen von mehreren untergeordneten Pfaden innerhalb einer PathGeometry'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3a9a233df95f69a68c5410c5836dacd5ab2c239a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a><span data-ttu-id="f01d2-102">Gewusst wie: Erstellen von mehreren untergeordneten Pfaden innerhalb einer PathGeometry</span><span class="sxs-lookup"><span data-stu-id="f01d2-102">How to: Create Multiple Subpaths Within a PathGeometry</span></span>
<span data-ttu-id="f01d2-103">In diesem Beispiel wird gezeigt, wie mehrere Pfade im Erstellen einer <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="f01d2-103">This example shows how to create multiple subpaths in a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="f01d2-104">Um mehrere Pfade zu erstellen, erstellen Sie eine <xref:System.Windows.Media.PathFigure> für jeden untergeordneten Pfad.</span><span class="sxs-lookup"><span data-stu-id="f01d2-104">To create multiple subpaths, you create a <xref:System.Windows.Media.PathFigure> for each subpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f01d2-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f01d2-105">Example</span></span>  
 <span data-ttu-id="f01d2-106">Das folgende Beispiel erstellt zwei Pfade, die jeweils einem Dreieck gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="f01d2-106">The following example creates two subpaths, each one a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 <span data-ttu-id="f01d2-107">Im folgende Beispiel wird gezeigt, wie erstellen Sie mehrere Pfade mithilfe einer <xref:System.Windows.Shapes.Path> und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Attributsyntax.</span><span class="sxs-lookup"><span data-stu-id="f01d2-107">The following example shows how to create multiple subpaths by using a <xref:System.Windows.Shapes.Path> and [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax.</span></span> <span data-ttu-id="f01d2-108">Jede `M` erstellt einen neuen untergeordneten so, dass im Beispiel werden zwei Pfade erstellt, jeweils ein Dreieck gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="f01d2-108">Each `M` creates a new subpath so that the example creates two subpaths that each draw a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 <span data-ttu-id="f01d2-109">(Beachten Sie, die diese Attributsyntax tatsächlich erstellt eine <xref:System.Windows.Media.StreamGeometry>, einer helleren Gewichtung-Version von einer <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="f01d2-109">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="f01d2-110">Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).)</span><span class="sxs-lookup"><span data-stu-id="f01d2-110">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f01d2-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f01d2-111">See Also</span></span>  
 [<span data-ttu-id="f01d2-112">Übersicht über Geometrien</span><span class="sxs-lookup"><span data-stu-id="f01d2-112">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
