---
title: 'Gewusst wie: Animieren eines Doubles mithilfe von Keyframes'
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
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e87717f6e2691142efa54a7e363f1038f8b74c1b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a><span data-ttu-id="4f14a-102">Gewusst wie: Animieren eines Doubles mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="4f14a-102">How to: Animate a Double by Using Key Frames</span></span>
<span data-ttu-id="4f14a-103">In diesem Beispiel wird gezeigt, wie den Wert einer Eigenschaft animieren, akzeptiert eine <xref:System.Double> mithilfe von Keyframes.</span><span class="sxs-lookup"><span data-stu-id="4f14a-103">This example shows how to animate the value of a property that takes a <xref:System.Double> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f14a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4f14a-104">Example</span></span>  
 <span data-ttu-id="4f14a-105">Im folgenden Beispiel wird ein Rechteck über den Bildschirm bewegt.</span><span class="sxs-lookup"><span data-stu-id="4f14a-105">The following example moves a rectangle across a screen.</span></span> <span data-ttu-id="4f14a-106">Im Beispiel wird die <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> Klasse zu animierende der <xref:System.Windows.Media.TranslateTransform.X%2A> Eigenschaft eine <xref:System.Windows.Media.TranslateTransform> angewendet, um eine <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="4f14a-106">The example uses the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.TranslateTransform.X%2A> property of a <xref:System.Windows.Media.TranslateTransform> applied to a <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="4f14a-107">In dieser sich ständig wiederholenden Animation werden drei Keyframes folgendermaßen verwendet:</span><span class="sxs-lookup"><span data-stu-id="4f14a-107">This animation, which repeats indefinitely, uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="4f14a-108">Während der ersten drei Sekunden wird eine Instanz der dem <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> Klasse, um das Rechteck entlang eines Pfads mit konstanter Geschwindigkeit von der Startposition der 500 Position zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="4f14a-108">During the first three seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> class to move the rectangle along a path at a steady rate from its starting position to the 500 position.</span></span> <span data-ttu-id="4f14a-109">Lineare Keyframes wie <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> einen smooth linearen Übergang zwischen den Werten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4f14a-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="4f14a-110">Am Ende der vierten Sekunde verwendet eine Instanz der <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> Klasse, um das Rechteck plötzlich in der nächsten Position zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="4f14a-110">At the end of the fourth second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> class to suddenly move the rectangle to the next position.</span></span> <span data-ttu-id="4f14a-111">Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> plötzlichen Sprünge zwischen Werten.</span><span class="sxs-lookup"><span data-stu-id="4f14a-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> create sudden jumps between values.</span></span> <span data-ttu-id="4f14a-112">In diesem Beispiel befindet sich das Rechteck an der Startposition und wird anschließend plötzlich an der Position 500 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4f14a-112">In this example, the rectangle is at the starting position and then suddenly appears at the 500 position.</span></span>  
  
3.  <span data-ttu-id="4f14a-113">In den letzten zwei Sekunden verwendet eine Instanz der <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> Klasse, um das Rechteck zurück an seine Anfangsposition zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="4f14a-113">In the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> class to move the rectangle back to its starting position.</span></span> <span data-ttu-id="4f14a-114">Spline-Keyframes wie <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> erzeugen einen variablen Übergang zwischen Werten entsprechend dem Wert von der <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4f14a-114">Spline key frames like <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> create a variable transition between values according to the value of the <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="4f14a-115">In diesem Beispiel bewegt sich das Rechteck zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.</span><span class="sxs-lookup"><span data-stu-id="4f14a-115">In this example, the rectangle begins by moving slowly and then speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="4f14a-116">Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="4f14a-116">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
 <span data-ttu-id="4f14a-117">Aus Gründen der Konsistenz mit anderen Animation Beispiele für die Codeversionen der in diesem Beispiel verwenden eine <xref:System.Windows.Media.Animation.Storyboard> Objekt anzuwendende der <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="4f14a-117">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="4f14a-118">Alternativ beim Anwenden einer Animation im Code ist es einfacher, die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode anstelle einer <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="4f14a-118">Alternatively, when applying a single animation in code, it is simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="4f14a-119">Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="4f14a-119">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f14a-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f14a-120">See Also</span></span>  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Shapes.Rectangle>  
 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>  
 [<span data-ttu-id="4f14a-121">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="4f14a-121">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="4f14a-122">Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)</span><span class="sxs-lookup"><span data-stu-id="4f14a-122">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
