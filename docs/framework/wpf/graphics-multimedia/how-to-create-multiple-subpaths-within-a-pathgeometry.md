---
title: 'Vorgehensweise: Erstellen von mehreren untergeordneten Pfaden innerhalb einer PathGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: d7b3d24f8d947d342a2af5484a6620c8379ac664
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638352"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a><span data-ttu-id="5a5a5-102">Vorgehensweise: Erstellen von mehreren untergeordneten Pfaden innerhalb einer PathGeometry</span><span class="sxs-lookup"><span data-stu-id="5a5a5-102">How to: Create Multiple Subpaths Within a PathGeometry</span></span>
<span data-ttu-id="5a5a5-103">Dieses Beispiel zeigt, wie Sie mehrere Pfade im Erstellen einer <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="5a5a5-103">This example shows how to create multiple subpaths in a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="5a5a5-104">Um mehrere Pfade zu erstellen, erstellen Sie eine <xref:System.Windows.Media.PathFigure> für jeden untergeordneten Pfad.</span><span class="sxs-lookup"><span data-stu-id="5a5a5-104">To create multiple subpaths, you create a <xref:System.Windows.Media.PathFigure> for each subpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a5a5-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5a5a5-105">Example</span></span>  
 <span data-ttu-id="5a5a5-106">Das folgende Beispiel erstellt zwei Pfade, die jeweils ein Dreieck.</span><span class="sxs-lookup"><span data-stu-id="5a5a5-106">The following example creates two subpaths, each one a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 <span data-ttu-id="5a5a5-107">Das folgende Beispiel zeigt, wie zum Erstellen von mehreren untergeordneten Pfaden mithilfe einer <xref:System.Windows.Shapes.Path> und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Attributsyntax.</span><span class="sxs-lookup"><span data-stu-id="5a5a5-107">The following example shows how to create multiple subpaths by using a <xref:System.Windows.Shapes.Path> and [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax.</span></span> <span data-ttu-id="5a5a5-108">Jede `M` erstellt einen neuen untergeordneten, so, dass im Beispiel werden zwei Pfade erstellt, jeweils ein Dreieck gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="5a5a5-108">Each `M` creates a new subpath so that the example creates two subpaths that each draw a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 <span data-ttu-id="5a5a5-109">(Beachten Sie, die dieser Attributsyntax eigentlich erstellt eine <xref:System.Windows.Media.StreamGeometry>, eine schlankere-Version von einem <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="5a5a5-109">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="5a5a5-110">Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).)</span><span class="sxs-lookup"><span data-stu-id="5a5a5-110">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a5a5-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a5a5-111">See also</span></span>
- [<span data-ttu-id="5a5a5-112">Übersicht über Geometrien</span><span class="sxs-lookup"><span data-stu-id="5a5a5-112">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
