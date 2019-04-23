---
title: 'Vorgehensweise: Animieren eines Point mithilfe von Keyframes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
ms.openlocfilehash: b706568a0e8221aac737780592882f728f0f9e9c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59328776"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a><span data-ttu-id="9dcac-102">Vorgehensweise: Animieren eines Point mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="9dcac-102">How to: Animate a Point by Using Key Frames</span></span>
<span data-ttu-id="9dcac-103">Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> -Klasse zum Animieren einer <xref:System.Windows.Point>.</span><span class="sxs-lookup"><span data-stu-id="9dcac-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate a <xref:System.Windows.Point>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dcac-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9dcac-104">Example</span></span>  
 <span data-ttu-id="9dcac-105">Im folgende Beispiel wird eine Ellipse entlang eines dreieckigen Pfads verschoben.</span><span class="sxs-lookup"><span data-stu-id="9dcac-105">The following example moves an ellipse along a triangular path.</span></span> <span data-ttu-id="9dcac-106">Im Beispiel wird die <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> -Klasse zum Animieren der <xref:System.Windows.Media.EllipseGeometry.Center%2A> Eigenschaft eine <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="9dcac-106">The example uses the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property of an <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="9dcac-107">In dieser Animation werden drei Keyframes folgendermaßen verwendet:</span><span class="sxs-lookup"><span data-stu-id="9dcac-107">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="9dcac-108">In der ersten halben Sekunde wird eine Instanz von der <xref:System.Windows.Media.Animation.LinearPointKeyFrame> Klasse, um die Ellipse entlang eines Pfads von der Startposition mit konstanter Geschwindigkeit zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="9dcac-108">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearPointKeyFrame> class to move the ellipse along a path at a steady rate from its starting position.</span></span> <span data-ttu-id="9dcac-109">Lineare Keyframes wie <xref:System.Windows.Media.Animation.LinearPointKeyFrame> eine glatte, lineare Interpolation zwischen Werten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9dcac-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearPointKeyFrame> create a smooth linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="9dcac-110">Am Ende der nächsten halben Sekunde wird eine Instanz von der <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> Klasse, um die Ellipse entlang des Pfads abrupt an die nächste Position zu bewegen.</span><span class="sxs-lookup"><span data-stu-id="9dcac-110">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> class to suddenly move the ellipse along the path to the next position.</span></span> <span data-ttu-id="9dcac-111">Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> ermöglichen abrupte Sprünge zwischen Werten.</span><span class="sxs-lookup"><span data-stu-id="9dcac-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> create sudden jumps between values.</span></span>  
  
3. <span data-ttu-id="9dcac-112">In den letzten zwei Sekunden wird eine Instanz von der <xref:System.Windows.Media.Animation.SplinePointKeyFrame> Klasse, um die Ellipse zurück an seine Ausgangsposition zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="9dcac-112">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame> class to move the ellipse back to its starting position.</span></span> <span data-ttu-id="9dcac-113">Spline-Keyframes wie <xref:System.Windows.Media.Animation.SplinePointKeyFrame> erzeugen einen variablen Übergang zwischen Werten, die von der <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9dcac-113">Spline key frames like <xref:System.Windows.Media.Animation.SplinePointKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="9dcac-114">In diesem Beispiel beginnt die Animation zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.</span><span class="sxs-lookup"><span data-stu-id="9dcac-114">In this example, the animation begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="9dcac-115">Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="9dcac-115">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
 <span data-ttu-id="9dcac-116">Verwenden Sie für Konsistenz mit anderen Animationsbeispielen die Codeversionen dieses Beispiels ein <xref:System.Windows.Media.Animation.Storyboard> Objekt anzuwendende der <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="9dcac-116">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="9dcac-117">Beim Anwenden einer Animation im Code ist es jedoch einfacher, die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode anstelle einer <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="9dcac-117">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="9dcac-118">Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="9dcac-118">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dcac-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9dcac-119">See also</span></span>

- <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.EllipseGeometry>
- [<span data-ttu-id="9dcac-120">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="9dcac-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="9dcac-121">Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)</span><span class="sxs-lookup"><span data-stu-id="9dcac-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
