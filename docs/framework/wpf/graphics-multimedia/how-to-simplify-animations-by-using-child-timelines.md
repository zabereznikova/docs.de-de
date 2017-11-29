---
title: 'Gewusst wie: Vereinfachen von Animationen durch untergeordnete Timeline-Objekte'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simplifying animations by child timelines [WPF]
- animation [WPF], simplifying by child timelines
- child timelines [WPF]
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: daa4caac0046293e8b86a773bfffd46cf30e835b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-simplify-animations-by-using-child-timelines"></a><span data-ttu-id="68d9b-102">Gewusst wie: Vereinfachen von Animationen durch untergeordnete Timeline-Objekte</span><span class="sxs-lookup"><span data-stu-id="68d9b-102">How to: Simplify Animations by Using Child Timelines</span></span>
<span data-ttu-id="68d9b-103">Dieses Beispiel zeigt, wie Sie Animationen zu vereinfachen, indem Sie untergeordnete <xref:System.Windows.Media.Animation.ParallelTimeline> Objekte.</span><span class="sxs-lookup"><span data-stu-id="68d9b-103">This example shows how to simplify animations by using child <xref:System.Windows.Media.Animation.ParallelTimeline> objects.</span></span> <span data-ttu-id="68d9b-104">Ein <xref:System.Windows.Media.Animation.Storyboard> ist eine Art von <xref:System.Windows.Media.Animation.Timeline> Zielinformationen für die Zeitachsen, er enthält, bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="68d9b-104">A <xref:System.Windows.Media.Animation.Storyboard> is a type of <xref:System.Windows.Media.Animation.Timeline> that provides targeting information for the timelines it contains.</span></span> <span data-ttu-id="68d9b-105">Verwenden einer <xref:System.Windows.Media.Animation.Storyboard> Zeitachse Adressieren von Informationen, einschließlich Informationen zu Objekt und Eigenschaft bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="68d9b-105">Use a <xref:System.Windows.Media.Animation.Storyboard> to provide timeline targeting information, including object and property information.</span></span>  
  
 <span data-ttu-id="68d9b-106">Um eine Animation starten, verwenden Sie eine oder mehrere <xref:System.Windows.Media.Animation.ParallelTimeline> Objekte als geschachtelte untergeordnete Elemente von einem <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="68d9b-106">To begin an animation, use one or more <xref:System.Windows.Media.Animation.ParallelTimeline> objects as nested child elements of a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="68d9b-107">Diese <xref:System.Windows.Media.Animation.ParallelTimeline> Objekte können andere Animationen enthalten und daher die zeitliche Steuerung Sequenzen in komplexen Animationen besser kapseln.</span><span class="sxs-lookup"><span data-stu-id="68d9b-107">These <xref:System.Windows.Media.Animation.ParallelTimeline> objects can contain other animations and therefore, can better encapsulate the timing sequences in complex animations.</span></span> <span data-ttu-id="68d9b-108">Angenommen, Sie Animieren einer <xref:System.Windows.Controls.TextBlock> und mehrere Formen in der gleichen <xref:System.Windows.Media.Animation.Storyboard>, können Sie die Animationen für Trennen der <xref:System.Windows.Controls.TextBlock> und Formen, indem Sie diese jeweils in eine Separate <xref:System.Windows.Media.Animation.ParallelTimeline>.</span><span class="sxs-lookup"><span data-stu-id="68d9b-108">For example, if you are animating a <xref:System.Windows.Controls.TextBlock> and several shapes in the same <xref:System.Windows.Media.Animation.Storyboard>, you can separate the animations for the <xref:System.Windows.Controls.TextBlock> and the shapes, putting each into a separate <xref:System.Windows.Media.Animation.ParallelTimeline>.</span></span> <span data-ttu-id="68d9b-109">Da jede <xref:System.Windows.Media.Animation.ParallelTimeline> verfügt über eine eigene <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> und alle untergeordneten Elemente des der <xref:System.Windows.Media.Animation.ParallelTimeline> beginnen relativ zu dieser <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, ein Timeout besser gekapselt ist.</span><span class="sxs-lookup"><span data-stu-id="68d9b-109">Because each <xref:System.Windows.Media.Animation.ParallelTimeline> has its own <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> and all child elements of the <xref:System.Windows.Media.Animation.ParallelTimeline> begin relative to this <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, timing is better encapsulated.</span></span>  
  
 <span data-ttu-id="68d9b-110">Das folgende Beispiel erstellt eine Animation zwei Teile des Texts (<xref:System.Windows.Controls.TextBlock> Objekte) von innerhalb des gleichen <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="68d9b-110">The following example animates two pieces of text (<xref:System.Windows.Controls.TextBlock> objects) from within the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="68d9b-111">Ein <xref:System.Windows.Media.Animation.ParallelTimeline> kapselt die Animationen an eines der <xref:System.Windows.Controls.TextBlock> Objekte.</span><span class="sxs-lookup"><span data-stu-id="68d9b-111">A <xref:System.Windows.Media.Animation.ParallelTimeline> encapsulates the animations of one of the <xref:System.Windows.Controls.TextBlock> objects.</span></span>  
  
 <span data-ttu-id="68d9b-112">**Leistungshinweis:** Sie können jedoch schachteln <xref:System.Windows.Media.Animation.Storyboard> Zeitachsen innerhalb des jeweils anderen <xref:System.Windows.Media.Animation.ParallelTimeline>s sind besser geeignet, für das schachteln, da sie weniger Aufwand erfordern.</span><span class="sxs-lookup"><span data-stu-id="68d9b-112">**Performance Note:** Although you can nest <xref:System.Windows.Media.Animation.Storyboard> timelines inside each other, <xref:System.Windows.Media.Animation.ParallelTimeline>s are more suitable for nesting because they require less overhead.</span></span> <span data-ttu-id="68d9b-113">(Die <xref:System.Windows.Media.Animation.Storyboard> Klasse erbt von der <xref:System.Windows.Media.Animation.ParallelTimeline> Klasse.)</span><span class="sxs-lookup"><span data-stu-id="68d9b-113">(The <xref:System.Windows.Media.Animation.Storyboard> class inherits from the <xref:System.Windows.Media.Animation.ParallelTimeline> class.)</span></span>  
  
## <a name="example"></a><span data-ttu-id="68d9b-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="68d9b-114">Example</span></span>  
 [!code-xaml[Timelines_snip#ParallelTimelineWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="68d9b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68d9b-115">See Also</span></span>  
 [<span data-ttu-id="68d9b-116">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="68d9b-116">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="68d9b-117">Angeben des Übergabeverhaltens zwischen Storyboard-Animationen</span><span class="sxs-lookup"><span data-stu-id="68d9b-117">Specify HandoffBehavior Between Storyboard Animations</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-handoffbehavior-between-storyboard-animations.md)
