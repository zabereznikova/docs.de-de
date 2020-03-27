---
title: 'Gewusst wie: Animieren einer Rechteckgeometrie mithilfe von Keyframes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: bcc9e7f198b8a20ffe13daf6508fb8a735937652
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344675"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="4ae54-102">Gewusst wie: Animieren einer Rechteckgeometrie mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="4ae54-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="4ae54-103">In diesem Beispiel wird <xref:System.Windows.Media.RectangleGeometry.Rect%2A> gezeigt, <xref:System.Windows.Media.RectangleGeometry> wie die Eigenschaft eines mithilfe von Schlüsselbildern animiert wird.</span><span class="sxs-lookup"><span data-stu-id="4ae54-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ae54-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4ae54-104">Example</span></span>  
 <span data-ttu-id="4ae54-105">Im folgenden Beispiel <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> wird die <xref:System.Windows.Media.RectangleGeometry.Rect%2A> Klasse <xref:System.Windows.Media.RectangleGeometry>verwendet, um die Eigenschaft einer zu animieren.</span><span class="sxs-lookup"><span data-stu-id="4ae54-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="4ae54-106">In dieser Animation werden drei Keyframes folgendermaßen verwendet:</span><span class="sxs-lookup"><span data-stu-id="4ae54-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="4ae54-107">Verwendet in den ersten zwei Sekunden <xref:System.Windows.Media.Animation.LinearRectKeyFrame> eine Instanz der Klasse, um eine allmähliche Änderung der Position, Breite und Höhe eines Rechtecks zu animieren.</span><span class="sxs-lookup"><span data-stu-id="4ae54-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="4ae54-108">Lineare Schlüsselrahmen wie <xref:System.Windows.Media.Animation.LinearRectKeyFrame> erstellen einen glatten linearen Übergang zwischen Werten.</span><span class="sxs-lookup"><span data-stu-id="4ae54-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="4ae54-109">Verwendet am Ende der nächsten halben Sekunde <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> eine Instanz der Klasse, um die Höhe des Rechtecks plötzlich zu verringern.</span><span class="sxs-lookup"><span data-stu-id="4ae54-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="4ae54-110">Diskrete Schlüsselrahmen <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> wie erstellen plötzliche Änderungen zwischen Werten, das heißt, die Abnahme der Höhe erfolgt schnell und ist nicht subtil.</span><span class="sxs-lookup"><span data-stu-id="4ae54-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="4ae54-111">Verwendet in den letzten zwei Sekunden <xref:System.Windows.Media.Animation.SplineRectKeyFrame> eine Instanz der Klasse, um das Rechteck wieder auf seine ursprüngliche Größe und Position zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4ae54-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="4ae54-112">Spline-Schlüsselrahmen <xref:System.Windows.Media.Animation.SplineRectKeyFrame> wie erstellen sie einen variablen Übergang <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> zwischen Werten entsprechend den Werten der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4ae54-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="4ae54-113">In diesem Beispiel beginnt die Veränderung zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.</span><span class="sxs-lookup"><span data-stu-id="4ae54-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="4ae54-114">Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="4ae54-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ae54-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ae54-115">See also</span></span>

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [<span data-ttu-id="4ae54-116">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="4ae54-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="4ae54-117">Themen zur Vorgehensweise mit Keyframes</span><span class="sxs-lookup"><span data-stu-id="4ae54-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
