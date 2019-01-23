---
title: 'Vorgehensweise: Anwenden eines Führungsliniensatzes auf eine Zeichnung'
ms.date: 03/30/2017
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
ms.openlocfilehash: 4bd2ee349f2c1855a9af6b4c00f2630cd50a9108
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493377"
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a><span data-ttu-id="1f6d8-102">Vorgehensweise: Anwenden eines Führungsliniensatzes auf eine Zeichnung</span><span class="sxs-lookup"><span data-stu-id="1f6d8-102">How to: Apply a GuidelineSet to a Drawing</span></span>
<span data-ttu-id="1f6d8-103">Dieses Beispiel veranschaulicht das Anwenden einer <xref:System.Windows.Media.GuidelineSet> auf eine <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="1f6d8-103">This example shows how to apply a <xref:System.Windows.Media.GuidelineSet> to a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
 <span data-ttu-id="1f6d8-104">Die <xref:System.Windows.Media.DrawingGroup> Klasse ist die einzige Art von <xref:System.Windows.Media.Drawing> , bei dem ein <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1f6d8-104">The <xref:System.Windows.Media.DrawingGroup> class is the only type of <xref:System.Windows.Media.Drawing> that has a <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> property.</span></span> <span data-ttu-id="1f6d8-105">Anzuwendende eine <xref:System.Windows.Media.GuidelineSet> in einen anderen Typ von <xref:System.Windows.Media.Drawing>, Hinzufügen einer <xref:System.Windows.Media.DrawingGroup> und wenden Sie dann die <xref:System.Windows.Media.GuidelineSet> auf Ihre <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="1f6d8-105">To apply a <xref:System.Windows.Media.GuidelineSet> to another type of <xref:System.Windows.Media.Drawing>, add it to a <xref:System.Windows.Media.DrawingGroup> and then apply the <xref:System.Windows.Media.GuidelineSet> to your <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f6d8-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1f6d8-106">Example</span></span>  
 <span data-ttu-id="1f6d8-107">Das folgende Beispiel erstellt zwei <xref:System.Windows.Media.DrawingGroup> Objekte, die sind nahezu identisch; der einzige Unterschied besteht: zweiten <xref:System.Windows.Media.DrawingGroup> hat eine <xref:System.Windows.Media.GuidelineSet> und nicht für die erste.</span><span class="sxs-lookup"><span data-stu-id="1f6d8-107">The following example creates two <xref:System.Windows.Media.DrawingGroup> objects that are almost identical; the only difference is: the second <xref:System.Windows.Media.DrawingGroup> has a <xref:System.Windows.Media.GuidelineSet> and the first does not.</span></span>  
  
 <span data-ttu-id="1f6d8-108">Die folgende Abbildung zeigt die Ausgabe des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="1f6d8-108">The following illustration shows the output from the example.</span></span> <span data-ttu-id="1f6d8-109">Da das Rendern zu den Unterschieden zwischen den beiden <xref:System.Windows.Media.DrawingGroup> Objekte nur sehr schwer, Teile der Zeichnung vergrößert werden.</span><span class="sxs-lookup"><span data-stu-id="1f6d8-109">Because the rendering difference between the two <xref:System.Windows.Media.DrawingGroup> objects is so subtle, portions of the drawings are enlarged.</span></span>  
  
 <span data-ttu-id="1f6d8-110">![Eine DrawingGroup mit und ohne ein GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "Graphicsmm_drawinggroup_guidelineset")</span><span class="sxs-lookup"><span data-stu-id="1f6d8-110">![A DrawingGroup with and without a GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="1f6d8-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f6d8-111">See also</span></span>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.GuidelineSet>
- [<span data-ttu-id="1f6d8-112">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="1f6d8-112">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
