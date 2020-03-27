---
title: 'Gewusst wie: Zeitliche Steuerung einer Keyframe-Animation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 8cfd2be0bbc526ed92a5fb1b558a5a41dc9c3113
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344733"
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="08a2c-102">Gewusst wie: Zeitliche Steuerung einer Keyframe-Animation</span><span class="sxs-lookup"><span data-stu-id="08a2c-102">How to: Control Key-Frame Animation Timing</span></span>

<span data-ttu-id="08a2c-103">In diesem Beispiel wird gezeigt, wie das Timing von Schlüsselbildern in einer Keyframe-Animation gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="08a2c-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="08a2c-104">Wie andere Animationen verfügen Keyframe-Animationen über eine <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="08a2c-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="08a2c-105">Zusätzlich zur Angabe der Dauer einer Animation müssen Sie angeben, welcher Teil dieser Dauer jedem seiner Schlüsselbilder zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="08a2c-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="08a2c-106">Um die Zeit zuzumachen, geben Sie für jeden Schlüsselrahmen in der Animation eine <xref:System.Windows.Media.Animation.KeyTime> an.</span><span class="sxs-lookup"><span data-stu-id="08a2c-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>

<span data-ttu-id="08a2c-107">Der <xref:System.Windows.Media.Animation.KeyTime> für jeden Schlüsselrahmen gibt an, wann ein Schlüsselrahmen endet (er gibt nicht an, wie lange ein Schlüsselrahmen abgespielt wird).</span><span class="sxs-lookup"><span data-stu-id="08a2c-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="08a2c-108">Sie können <xref:System.Windows.Media.Animation.KeyTime> einen <xref:System.TimeSpan> Wert als Wert, als <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> Prozentsatz <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> oder als oder als Sonderwert angeben.</span><span class="sxs-lookup"><span data-stu-id="08a2c-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>

## <a name="example"></a><span data-ttu-id="08a2c-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="08a2c-109">Example</span></span>

<span data-ttu-id="08a2c-110">Im folgenden Beispiel <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> wird ein verwendet, um ein Rechteck auf dem Bildschirm zu animieren.</span><span class="sxs-lookup"><span data-stu-id="08a2c-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="08a2c-111">Die Schlüsselzeiten der Keyframes <xref:System.TimeSpan> werden mit Werten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="08a2c-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

<span data-ttu-id="08a2c-112">Die folgende Abbildung zeigt, wann der Wert jedes Schlüsselrahmens erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="08a2c-112">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="08a2c-113">![Schlüsselwerte werden nach 3, 4 und 10 Sekunden erreicht](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="08a2c-113">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>

<span data-ttu-id="08a2c-114">Das nächste Beispiel zeigt eine Animation, die identisch ist, mit der Ausnahme, dass die Schlüsselzeiten der Schlüsselrahmen mit Prozentwerten festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="08a2c-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

<span data-ttu-id="08a2c-115">Die folgende Abbildung zeigt, wann der Wert jedes Schlüsselrahmens erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="08a2c-115">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="08a2c-116">![Schlüsselwerte werden nach 3, 4 und 10 Sekunden erreicht](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="08a2c-116">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>

<span data-ttu-id="08a2c-117">Im nächsten <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> Beispiel werden wichtige Zeitwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="08a2c-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

<span data-ttu-id="08a2c-118">Die folgende Abbildung zeigt, wann der Wert jedes Schlüsselrahmens erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="08a2c-118">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="08a2c-119">![Schlüsselwerte werden nach 3,3, 6,6 und 9,9 Sekunden erreicht](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="08a2c-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>

<span data-ttu-id="08a2c-120">Im letzten <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> Beispiel werden wichtige Zeitwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="08a2c-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

<span data-ttu-id="08a2c-121">Die folgende Abbildung zeigt, wann der Wert jedes Schlüsselrahmens erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="08a2c-121">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="08a2c-122">![Schlüsselwerte werden nach 0, 5 und 10 Sekunden erreicht](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="08a2c-122">![Key values are reached at 0, 5, and 10 seconds](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>

<span data-ttu-id="08a2c-123">Der Einfachheit halber verwenden die Codeversionen dieses Beispiels lokale Animationen und keine Storyboards, da nur eine einzelne Animation auf eine einzelne Eigenschaft angewendet wird, die Beispiele jedoch geändert werden können, um Storyboards stattdessen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="08a2c-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="08a2c-124">Ein Beispiel zum Deklarieren eines Storyboards im Code finden Sie unter [Animieren einer Eigenschaft mithilfe eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="08a2c-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).</span></span>

<span data-ttu-id="08a2c-125">Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="08a2c-125">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span> <span data-ttu-id="08a2c-126">Weitere Informationen zu Keyframe-Animationen finden Sie in der [Key-Frame-Animationsübersicht](key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="08a2c-126">For more information about key frame animations, see the [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="08a2c-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08a2c-127">See also</span></span>

- [<span data-ttu-id="08a2c-128">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="08a2c-128">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="08a2c-129">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="08a2c-129">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="08a2c-130">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="08a2c-130">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
