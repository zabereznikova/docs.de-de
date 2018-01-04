---
title: 'Gewusst wie: Zeitliche Steuerung einer Keyframe-Animation'
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
- key frames [WPF], timing
- timing key-fram animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 252da422ffb34e5865a29112e349e18d0f40327f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="04f14-102">Gewusst wie: Zeitliche Steuerung einer Keyframe-Animation</span><span class="sxs-lookup"><span data-stu-id="04f14-102">How to: Control Key-Frame Animation Timing</span></span>
<span data-ttu-id="04f14-103">Dieses Beispiel zeigt, wie die zeitliche Abfolge von Keyframes innerhalb einer Keyframe Animation steuern.</span><span class="sxs-lookup"><span data-stu-id="04f14-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="04f14-104">Wie andere Animationen Keyframe-Animationen haben eine <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="04f14-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="04f14-105">Zusätzlich zur Angabe der Dauer der Animation, müssen Sie angeben, welcher Teil dieser Dauer auf die einzelnen Keyframes zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="04f14-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="04f14-106">Um die Zeit zuzuweisen, geben Sie einen <xref:System.Windows.Media.Animation.KeyTime> für jeden Keyframe in der Animation.</span><span class="sxs-lookup"><span data-stu-id="04f14-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>  
  
 <span data-ttu-id="04f14-107">Die <xref:System.Windows.Media.Animation.KeyTime> für jede Keyframes gibt an, wenn eine Keyframes endet (es gibt keinen die Zeitdauer, die ein Keyframe spielt).</span><span class="sxs-lookup"><span data-stu-id="04f14-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="04f14-108">Können Sie angeben, eine <xref:System.Windows.Media.Animation.KeyTime> als eine <xref:System.TimeSpan> als Prozentsatz oder als Wert der <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> oder <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> Spezialwert.</span><span class="sxs-lookup"><span data-stu-id="04f14-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04f14-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04f14-109">Example</span></span>  
 <span data-ttu-id="04f14-110">Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> um ein Rechteck über den Bildschirm bewegen.</span><span class="sxs-lookup"><span data-stu-id="04f14-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="04f14-111">Wie oft der Keyframes-Schlüssel festgelegt <xref:System.TimeSpan> Werte.</span><span class="sxs-lookup"><span data-stu-id="04f14-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
 [!code-vb[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
 [!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]  
  
 <span data-ttu-id="04f14-112">Die folgende Abbildung zeigt, wenn der Wert der einzelnen Keyframes erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="04f14-112">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="04f14-113">![Schlüsselwerte werden nach 3, 4 und 10 Sekunden erreicht](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="04f14-113">![Key values are reached at 3, 4, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>  
  
 <span data-ttu-id="04f14-114">Das nächste Beispiel zeigt eine Animation, die nahezu identisch, außer, dass der Keyframes Key Zeiten mit Prozentwerten festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="04f14-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
 [!code-vb[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
 [!code-xaml[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]  
  
 <span data-ttu-id="04f14-115">Die folgende Abbildung zeigt, wenn der Wert der einzelnen Keyframes erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="04f14-115">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="04f14-116">![Schlüsselwerte werden nach 3, 4 und 10 Sekunden erreicht](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="04f14-116">![Key values are reached at 3, 4, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>  
  
 <span data-ttu-id="04f14-117">Im nächste Beispiel wird <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key Time-Werten.</span><span class="sxs-lookup"><span data-stu-id="04f14-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
 [!code-vb[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
 [!code-xaml[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]  
  
 <span data-ttu-id="04f14-118">Die folgende Abbildung zeigt, wenn der Wert der einzelnen Keyframes erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="04f14-118">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="04f14-119">![Schlüsselwerte werden am 3.3,6.6 und 9,9 Sekunden erreicht](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="04f14-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>  
  
 <span data-ttu-id="04f14-120">Im abschließenden Beispiel verwendet <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key Time-Werten.</span><span class="sxs-lookup"><span data-stu-id="04f14-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
 [!code-vb[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
 [!code-xaml[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]  
  
 <span data-ttu-id="04f14-121">Die folgende Abbildung zeigt, wenn der Wert der einzelnen Keyframes erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="04f14-121">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="04f14-122">![Schlüsselwerte werden nach 0, 5 und 10 Sekunden erreicht](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="04f14-122">![Key values are reached at 0, 5, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>  
  
 <span data-ttu-id="04f14-123">Der Einfachheit halber die Codeversionen dieses Beispiels lokale Animationen, storyboards, da nur eine Animation auf eine einzelne Eigenschaft angewendet wird, aber in den Beispielen möglicherweise geändert werden, um Storyboards stattdessen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="04f14-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="04f14-124">Ein Beispiel zeigt, wie ein Storyboard im Code deklariert ist, finden Sie unter [Animieren einer Eigenschaft eines Drehbuchs mit](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="04f14-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span></span>  
  
 <span data-ttu-id="04f14-125">Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="04f14-125">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span> <span data-ttu-id="04f14-126">Weitere Informationen zu Keyframe-Animationen, finden Sie unter der [Keyframe-Animationen Übersicht](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="04f14-126">For more information about key frame animations, see the [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f14-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04f14-127">See Also</span></span>  
 [<span data-ttu-id="04f14-128">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="04f14-128">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="04f14-129">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="04f14-129">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="04f14-130">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="04f14-130">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
