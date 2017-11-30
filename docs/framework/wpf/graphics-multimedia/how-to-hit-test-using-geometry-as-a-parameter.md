---
title: 'Gewusst wie: Treffertest mit Geometrie als Parameter'
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
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 32feb70a3b7a44a5a48f57fc2ecee912de4d39ef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a><span data-ttu-id="b4736-102">Gewusst wie: Treffertest mit Geometrie als Parameter</span><span class="sxs-lookup"><span data-stu-id="b4736-102">How to: Hit Test Using Geometry as a Parameter</span></span>
<span data-ttu-id="b4736-103">In diesem Beispiel wird gezeigt, wie zum Ausführen von Treffertests auf ein visuelles Objekt mithilfe einer <xref:System.Windows.Media.Geometry> Parameter als Treffer zu testen.</span><span class="sxs-lookup"><span data-stu-id="b4736-103">This example shows how to perform a hit test on a visual object using a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4736-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4736-104">Example</span></span>  
 <span data-ttu-id="b4736-105">Das folgende Beispiel zeigt, wie ein Treffertest mit eingerichtet <xref:System.Windows.Media.GeometryHitTestParameters> für die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="b4736-105">The following example shows how to set up a hit test using <xref:System.Windows.Media.GeometryHitTestParameters> for the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="b4736-106">Die <xref:System.Windows.Point> -Wert, der übergeben wird die `OnMouseDown` Methode dient zum Erstellen einer <xref:System.Windows.Media.Geometry> Objekt, um den Bereich des Treffertests zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="b4736-106">The <xref:System.Windows.Point> value that is passed to the `OnMouseDown` method is used to create a <xref:System.Windows.Media.Geometry> object in order to expand the range of the hit test.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 <span data-ttu-id="b4736-107">Die <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> Eigenschaft <xref:System.Windows.Media.GeometryHitTestResult> enthält Informationen über die Ergebnisse eines Treffertests verwendet eine <xref:System.Windows.Media.Geometry> Parameter als Treffer zu testen.</span><span class="sxs-lookup"><span data-stu-id="b4736-107">The <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property of <xref:System.Windows.Media.GeometryHitTestResult> provides information about the results of a hit test that uses a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span> <span data-ttu-id="b4736-108">In der folgenden Abbildung wird die Beziehung zwischen der Treffertestgeometrie (blauer Kreis) und dem gerenderten Inhalt des Zielobjekts (rotes Quadrat) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4736-108">The following illustration shows the relationship between the hit test geometry (the blue circle) and the rendered content of the target visual object (the red square).</span></span>  
  
 <span data-ttu-id="b4736-109">![Diagramm von IntersectionDetail bei Treffertests](../../../../docs/framework/wpf/graphics-multimedia/media/intersectiondetail01.png "IntersectionDetail01")</span><span class="sxs-lookup"><span data-stu-id="b4736-109">![Diagram of IntersectionDetail used in hit testing](../../../../docs/framework/wpf/graphics-multimedia/media/intersectiondetail01.png "IntersectionDetail01")</span></span>  
<span data-ttu-id="b4736-110">Schnittmenge einer Treffertestgeometrie und eines Zielobjekts</span><span class="sxs-lookup"><span data-stu-id="b4736-110">Intersection between hit test geometry and target visual object</span></span>  
  
 <span data-ttu-id="b4736-111">Im folgende Beispiel wird gezeigt, wie einen Treffertest-Rückruf implementieren bei einem <xref:System.Windows.Media.Geometry> als Treffertestparameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b4736-111">The following example shows how to implement a hit test callback when a <xref:System.Windows.Media.Geometry> is used as a hit test parameter.</span></span> <span data-ttu-id="b4736-112">Die `result` Parameter umgewandelt wird eine <xref:System.Windows.Media.GeometryHitTestResult> zum Abrufen des Werts der <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b4736-112">The `result` parameter is cast to a <xref:System.Windows.Media.GeometryHitTestResult> in order to retrieve the value of the <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property.</span></span> <span data-ttu-id="b4736-113">Den Wert der Eigenschaft können Sie bestimmen, ob die <xref:System.Windows.Media.Geometry> Treffertest-Parameter ist vollständig oder teilweise enthaltenen den gerenderten Inhalt des Ziels Treffertest.</span><span class="sxs-lookup"><span data-stu-id="b4736-113">The property value allows you to determine if the <xref:System.Windows.Media.Geometry> hit test parameter is fully or partially contained within the rendered content of the hit test target.</span></span> <span data-ttu-id="b4736-114">In diesem Fall fügt der Beispielcode der Liste visueller Objekte nur Treffertestergebnisse hinzu, die vollständig im Zielbereich enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b4736-114">In this case, the sample code is only adding hit test results to the list for visuals that are fully contained within the target boundary.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  <span data-ttu-id="b4736-115">Die <xref:System.Windows.Media.HitTestResult> Rückruf darf nicht aufgerufen werden, wenn die Schnittmenge ist <xref:System.Windows.Media.IntersectionDetail.Empty>.</span><span class="sxs-lookup"><span data-stu-id="b4736-115">The <xref:System.Windows.Media.HitTestResult> callback should not be called when the intersection detail is <xref:System.Windows.Media.IntersectionDetail.Empty>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4736-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4736-116">See Also</span></span>  
 [<span data-ttu-id="b4736-117">Treffertests in der visuellen Ebene</span><span class="sxs-lookup"><span data-stu-id="b4736-117">Hit Testing in the Visual Layer</span></span>](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [<span data-ttu-id="b4736-118">Vorgehensweise: Treffertest für eine Geometrie in einem visuellen Objekt</span><span class="sxs-lookup"><span data-stu-id="b4736-118">Hit Test Geometry in a Visual</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-geometry-in-a-visual.md)
