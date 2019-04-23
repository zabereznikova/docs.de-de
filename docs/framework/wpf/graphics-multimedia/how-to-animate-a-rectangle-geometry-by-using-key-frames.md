---
title: 'Vorgehensweise: Animieren einer Rechteckgeometrie mithilfe von Keyframes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: 03953b79127ffceeb49e4ece2070d09f382448a5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59311343"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="400fa-102">Vorgehensweise: Animieren einer Rechteckgeometrie mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="400fa-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="400fa-103">Dieses Beispiel zeigt, wie Sie animieren der <xref:System.Windows.Media.RectangleGeometry.Rect%2A> Eigenschaft eine <xref:System.Windows.Media.RectangleGeometry> mithilfe von Keyframes.</span><span class="sxs-lookup"><span data-stu-id="400fa-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="400fa-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="400fa-104">Example</span></span>  
 <span data-ttu-id="400fa-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> -Klasse zum Animieren der <xref:System.Windows.Media.RectangleGeometry.Rect%2A> Eigenschaft eine <xref:System.Windows.Media.RectangleGeometry>.</span><span class="sxs-lookup"><span data-stu-id="400fa-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="400fa-106">In dieser Animation werden drei Keyframes folgendermaßen verwendet:</span><span class="sxs-lookup"><span data-stu-id="400fa-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="400fa-107">In den ersten zwei Sekunden wird eine Instanz von der <xref:System.Windows.Media.Animation.LinearRectKeyFrame> Klasse, um eine schrittweise Änderung der Position, Breite und Höhe eines Rechtecks zu animieren.</span><span class="sxs-lookup"><span data-stu-id="400fa-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="400fa-108">Lineare Keyframes wie <xref:System.Windows.Media.Animation.LinearRectKeyFrame> einen glatten, linearen Übergang zwischen Werten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="400fa-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="400fa-109">Am Ende der nächsten halben Sekunde wird eine Instanz von der <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> Klasse, um die Höhe des Rechtecks abrupt zu verringern.</span><span class="sxs-lookup"><span data-stu-id="400fa-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="400fa-110">Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> abrupte Veränderungen zwischen Werten, d. h. erstellen, die Verringerung der Höhe tritt schnell auf und ist.</span><span class="sxs-lookup"><span data-stu-id="400fa-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="400fa-111">In den letzten zwei Sekunden wird eine Instanz von der <xref:System.Windows.Media.Animation.SplineRectKeyFrame> Klasse so ändern Sie das Rechteck zurück in seiner ursprünglichen Größe und Position.</span><span class="sxs-lookup"><span data-stu-id="400fa-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="400fa-112">Spline-Keyframes wie <xref:System.Windows.Media.Animation.SplineRectKeyFrame> erzeugen einen variablen Übergang zwischen Werten, die von der <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="400fa-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="400fa-113">In diesem Beispiel beginnt die Veränderung zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.</span><span class="sxs-lookup"><span data-stu-id="400fa-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="400fa-114">Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="400fa-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="400fa-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="400fa-115">See also</span></span>

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [<span data-ttu-id="400fa-116">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="400fa-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="400fa-117">Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)</span><span class="sxs-lookup"><span data-stu-id="400fa-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
