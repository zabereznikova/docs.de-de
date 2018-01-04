---
title: "Gewusst wie: Anwenden eines Führungsliniensatzes auf eine Zeichnung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5cf689f8a7c475dbdda416297e28118d43bfdbff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a><span data-ttu-id="feb9f-102">Gewusst wie: Anwenden eines Führungsliniensatzes auf eine Zeichnung</span><span class="sxs-lookup"><span data-stu-id="feb9f-102">How to: Apply a GuidelineSet to a Drawing</span></span>
<span data-ttu-id="feb9f-103">In diesem Beispiel wird gezeigt, wie zum Anwenden einer <xref:System.Windows.Media.GuidelineSet> auf eine <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="feb9f-103">This example shows how to apply a <xref:System.Windows.Media.GuidelineSet> to a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
 <span data-ttu-id="feb9f-104">Die <xref:System.Windows.Media.DrawingGroup> Klasse ist der einzige Typ von <xref:System.Windows.Media.Drawing> , besitzt eine <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="feb9f-104">The <xref:System.Windows.Media.DrawingGroup> class is the only type of <xref:System.Windows.Media.Drawing> that has a <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> property.</span></span> <span data-ttu-id="feb9f-105">Anwenden einer <xref:System.Windows.Media.GuidelineSet> in einen anderen Typ von <xref:System.Windows.Media.Drawing>, fügen Sie diese eine <xref:System.Windows.Media.DrawingGroup> und wenden Sie dann die <xref:System.Windows.Media.GuidelineSet> zu Ihrer <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="feb9f-105">To apply a <xref:System.Windows.Media.GuidelineSet> to another type of <xref:System.Windows.Media.Drawing>, add it to a <xref:System.Windows.Media.DrawingGroup> and then apply the <xref:System.Windows.Media.GuidelineSet> to your <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="feb9f-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="feb9f-106">Example</span></span>  
 <span data-ttu-id="feb9f-107">Das folgende Beispiel erstellt zwei <xref:System.Windows.Media.DrawingGroup> Objekte, die sind nahezu identisch sind; der einzige Unterschied ist: das zweite <xref:System.Windows.Media.DrawingGroup> verfügt über eine <xref:System.Windows.Media.GuidelineSet> und das erste nicht.</span><span class="sxs-lookup"><span data-stu-id="feb9f-107">The following example creates two <xref:System.Windows.Media.DrawingGroup> objects that are almost identical; the only difference is: the second <xref:System.Windows.Media.DrawingGroup> has a <xref:System.Windows.Media.GuidelineSet> and the first does not.</span></span>  
  
 <span data-ttu-id="feb9f-108">Die folgende Abbildung zeigt die Ausgabe des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="feb9f-108">The following illustration shows the output from the example.</span></span> <span data-ttu-id="feb9f-109">Da das Rendering zu den Unterschieden zwischen den beiden <xref:System.Windows.Media.DrawingGroup> Objekte ist schwer erkennbare, Teile der Zeichnung vergrößert werden.</span><span class="sxs-lookup"><span data-stu-id="feb9f-109">Because the rendering difference between the two <xref:System.Windows.Media.DrawingGroup> objects is so subtle, portions of the drawings are enlarged.</span></span>  
  
 <span data-ttu-id="feb9f-110">![Eine DrawingGroup mit und ohne ein GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "Graphicsmm_drawinggroup_guidelineset")</span><span class="sxs-lookup"><span data-stu-id="feb9f-110">![A DrawingGroup with and without a GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="feb9f-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="feb9f-111">See Also</span></span>  
 <xref:System.Windows.Media.DrawingGroup>  
 <xref:System.Windows.Media.GuidelineSet>  
 [<span data-ttu-id="feb9f-112">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="feb9f-112">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
