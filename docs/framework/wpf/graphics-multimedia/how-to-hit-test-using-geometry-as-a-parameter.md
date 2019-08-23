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
ms.openlocfilehash: 8bed7784b00f49178c9a87def74b62f7ce620ec7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923407"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a><span data-ttu-id="bf0c6-102">Vorgehensweise: Treffertest mit Geometrie als Parameter</span><span class="sxs-lookup"><span data-stu-id="bf0c6-102">How to: Hit Test Using Geometry as a Parameter</span></span>
<span data-ttu-id="bf0c6-103">Dieses Beispiel zeigt, wie Sie einen Treffer Test für ein visuelles Objekt ausführen, <xref:System.Windows.Media.Geometry> indem Sie als Treffer Testparameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="bf0c6-103">This example shows how to perform a hit test on a visual object using a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf0c6-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf0c6-104">Example</span></span>  
 <span data-ttu-id="bf0c6-105">Im folgenden Beispiel wird gezeigt, wie Sie einen Treffer Test mithilfe <xref:System.Windows.Media.GeometryHitTestParameters> von für <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> die-Methode einrichten.</span><span class="sxs-lookup"><span data-stu-id="bf0c6-105">The following example shows how to set up a hit test using <xref:System.Windows.Media.GeometryHitTestParameters> for the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="bf0c6-106">Der <xref:System.Windows.Point> Wert, der an die `OnMouseDown` -Methode weitergegeben wird, wird <xref:System.Windows.Media.Geometry> verwendet, um ein-Objekt zu erstellen, um den Bereich des Treffer Tests zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="bf0c6-106">The <xref:System.Windows.Point> value that is passed to the `OnMouseDown` method is used to create a <xref:System.Windows.Media.Geometry> object in order to expand the range of the hit test.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 <span data-ttu-id="bf0c6-107">Die <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> -Eigenschaft <xref:System.Windows.Media.GeometryHitTestResult> von enthält Informationen zu den Ergebnissen eines Treffer Tests, der einen <xref:System.Windows.Media.Geometry> als Treffer Testparameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="bf0c6-107">The <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property of <xref:System.Windows.Media.GeometryHitTestResult> provides information about the results of a hit test that uses a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span> <span data-ttu-id="bf0c6-108">In der folgenden Abbildung wird die Beziehung zwischen der Treffertestgeometrie (blauer Kreis) und dem gerenderten Inhalt des Zielobjekts (rotes Quadrat) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="bf0c6-108">The following illustration shows the relationship between the hit test geometry (the blue circle) and the rendered content of the target visual object (the red square).</span></span>  
  
 ![Diagramm, das IntersectionDetail anzeigt, das bei Treffer Tests verwendet wird.](./media/how-to-hit-test-using-geometry-as-a-parameter/intersectiondetail-hit-test.png)  
  
 <span data-ttu-id="bf0c6-110">Im folgenden Beispiel wird gezeigt, wie Sie einen Treffer Test Rückruf implementieren <xref:System.Windows.Media.Geometry> , wenn ein als Treffer Testparameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bf0c6-110">The following example shows how to implement a hit test callback when a <xref:System.Windows.Media.Geometry> is used as a hit test parameter.</span></span> <span data-ttu-id="bf0c6-111">Der `result` -Parameter wird in einen <xref:System.Windows.Media.GeometryHitTestResult> umgewandelt, um den Wert der- <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> Eigenschaft abzurufen.</span><span class="sxs-lookup"><span data-stu-id="bf0c6-111">The `result` parameter is cast to a <xref:System.Windows.Media.GeometryHitTestResult> in order to retrieve the value of the <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property.</span></span> <span data-ttu-id="bf0c6-112">Mit dem Eigenschafts Wert können Sie feststellen <xref:System.Windows.Media.Geometry> , ob der Treffer Testparameter vollständig oder teilweise im gerenderten Inhalt des Treffer Test Ziels enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="bf0c6-112">The property value allows you to determine if the <xref:System.Windows.Media.Geometry> hit test parameter is fully or partially contained within the rendered content of the hit test target.</span></span> <span data-ttu-id="bf0c6-113">In diesem Fall fügt der Beispielcode der Liste visueller Objekte nur Treffertestergebnisse hinzu, die vollständig im Zielbereich enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="bf0c6-113">In this case, the sample code is only adding hit test results to the list for visuals that are fully contained within the target boundary.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
> <span data-ttu-id="bf0c6-114">Der <xref:System.Windows.Media.HitTestResult> Rückruf sollte nicht aufgerufen werden, wenn die Überschneidungs <xref:System.Windows.Media.IntersectionDetail.Empty>Details ist.</span><span class="sxs-lookup"><span data-stu-id="bf0c6-114">The <xref:System.Windows.Media.HitTestResult> callback should not be called when the intersection detail is <xref:System.Windows.Media.IntersectionDetail.Empty>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf0c6-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf0c6-115">See also</span></span>

- [<span data-ttu-id="bf0c6-116">Treffertests in der visuellen Ebene</span><span class="sxs-lookup"><span data-stu-id="bf0c6-116">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="bf0c6-117">Vorgehensweise: Treffertest für eine Geometrie in einem visuellen Objekt</span><span class="sxs-lookup"><span data-stu-id="bf0c6-117">Hit Test Geometry in a Visual</span></span>](how-to-hit-test-geometry-in-a-visual.md)
