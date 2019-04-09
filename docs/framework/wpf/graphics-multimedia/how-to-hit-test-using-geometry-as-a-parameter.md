---
title: 'Vorgehensweise: Treffertest mit Geometrie als Parameter'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: 73420d6ae1386676ed900e91b3951df9e0934db8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100963"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a><span data-ttu-id="d4261-102">Vorgehensweise: Treffertest mit Geometrie als Parameter</span><span class="sxs-lookup"><span data-stu-id="d4261-102">How to: Hit Test Using Geometry as a Parameter</span></span>
<span data-ttu-id="d4261-103">Dieses Beispiel zeigt, wie Sie einen Treffertest durchführen, auf einem visuellen Objekt mit einem <xref:System.Windows.Media.Geometry> Parameter als Treffer zu testen.</span><span class="sxs-lookup"><span data-stu-id="d4261-103">This example shows how to perform a hit test on a visual object using a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4261-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d4261-104">Example</span></span>  
 <span data-ttu-id="d4261-105">Im folgenden Beispiel wird veranschaulicht, wie ein Treffertest eingerichtet <xref:System.Windows.Media.GeometryHitTestParameters> für die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="d4261-105">The following example shows how to set up a hit test using <xref:System.Windows.Media.GeometryHitTestParameters> for the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="d4261-106">Die <xref:System.Windows.Point> Wert an der `OnMouseDown` -Methode zum Erstellen einer <xref:System.Windows.Media.Geometry> Objekt um den Bereich des Treffertests zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="d4261-106">The <xref:System.Windows.Point> value that is passed to the `OnMouseDown` method is used to create a <xref:System.Windows.Media.Geometry> object in order to expand the range of the hit test.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 <span data-ttu-id="d4261-107">Die <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> -Eigenschaft des <xref:System.Windows.Media.GeometryHitTestResult> enthält Informationen über die Ergebnisse eines Treffertests verwendet eine <xref:System.Windows.Media.Geometry> als Hit test Parameter.</span><span class="sxs-lookup"><span data-stu-id="d4261-107">The <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property of <xref:System.Windows.Media.GeometryHitTestResult> provides information about the results of a hit test that uses a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span> <span data-ttu-id="d4261-108">In der folgenden Abbildung wird die Beziehung zwischen der Treffertestgeometrie (blauer Kreis) und dem gerenderten Inhalt des Zielobjekts (rotes Quadrat) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d4261-108">The following illustration shows the relationship between the hit test geometry (the blue circle) and the rendered content of the target visual object (the red square).</span></span>  
  
 ![Diagramm, das zeigt, dass IntersectionDetail verwendet den Treffertest durchführen.](./media/how-to-hit-test-using-geometry-as-a-parameter/intersectiondetail-hit-test.png)  
  
 <span data-ttu-id="d4261-110">Das folgende Beispiel zeigt, wie Sie einen Treffertestrückruf implementieren bei einem <xref:System.Windows.Media.Geometry> als Treffertestparameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d4261-110">The following example shows how to implement a hit test callback when a <xref:System.Windows.Media.Geometry> is used as a hit test parameter.</span></span> <span data-ttu-id="d4261-111">Die `result` Parameter der Umwandlung in einen <xref:System.Windows.Media.GeometryHitTestResult> zum Abrufen des Werts der <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d4261-111">The `result` parameter is cast to a <xref:System.Windows.Media.GeometryHitTestResult> in order to retrieve the value of the <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property.</span></span> <span data-ttu-id="d4261-112">Den Wert der Eigenschaft können Sie bestimmen, ob die <xref:System.Windows.Media.Geometry> -Treffertestparameter ganz oder teilweise enthalten ist in den gerenderten Inhalt des Treffertestziels.</span><span class="sxs-lookup"><span data-stu-id="d4261-112">The property value allows you to determine if the <xref:System.Windows.Media.Geometry> hit test parameter is fully or partially contained within the rendered content of the hit test target.</span></span> <span data-ttu-id="d4261-113">In diesem Fall fügt der Beispielcode der Liste visueller Objekte nur Treffertestergebnisse hinzu, die vollständig im Zielbereich enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d4261-113">In this case, the sample code is only adding hit test results to the list for visuals that are fully contained within the target boundary.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  <span data-ttu-id="d4261-114">Die <xref:System.Windows.Media.HitTestResult> Rückruf nicht aufgerufen werden soll, wenn die Schnittmenge aufweist <xref:System.Windows.Media.IntersectionDetail.Empty>.</span><span class="sxs-lookup"><span data-stu-id="d4261-114">The <xref:System.Windows.Media.HitTestResult> callback should not be called when the intersection detail is <xref:System.Windows.Media.IntersectionDetail.Empty>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4261-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4261-115">See also</span></span>

- [<span data-ttu-id="d4261-116">Treffertests in der visuellen Ebene</span><span class="sxs-lookup"><span data-stu-id="d4261-116">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="d4261-117">Treffertest für eine Geometrie in einem visuellen Objekt</span><span class="sxs-lookup"><span data-stu-id="d4261-117">Hit Test Geometry in a Visual</span></span>](how-to-hit-test-geometry-in-a-visual.md)
