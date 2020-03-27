---
title: 'Gewusst wie: Animieren von Color mithilfe von Keyframes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: 8a444706f7541b52722ab8257a88e76c3e1b0938
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344746"
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="03db1-102">Gewusst wie: Animieren von Color mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="03db1-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="03db1-103">In diesem Beispiel wird <xref:System.Windows.Media.SolidColorBrush.Color%2A> gezeigt, wie die von a <xref:System.Windows.Media.SolidColorBrush> mithilfe von Schlüsselrahmen animiert wird.</span><span class="sxs-lookup"><span data-stu-id="03db1-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03db1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03db1-104">Example</span></span>  
 <span data-ttu-id="03db1-105">Im folgenden Beispiel <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> wird die <xref:System.Windows.Media.SolidColorBrush.Color%2A> Klasse <xref:System.Windows.Media.SolidColorBrush>verwendet, um die Eigenschaft einer zu animieren.</span><span class="sxs-lookup"><span data-stu-id="03db1-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="03db1-106">In dieser Animation werden drei Keyframes folgendermaßen verwendet:</span><span class="sxs-lookup"><span data-stu-id="03db1-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="03db1-107">Verwendet in den ersten zwei Sekunden <xref:System.Windows.Media.Animation.LinearColorKeyFrame> eine Instanz der Klasse, um die Farbe schrittweise von grün in rot zu ändern.</span><span class="sxs-lookup"><span data-stu-id="03db1-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="03db1-108">Lineare Schlüsselrahmen wie <xref:System.Windows.Media.Animation.LinearColorKeyFrame> erstellen einen glatten linearen Übergang zwischen Werten.</span><span class="sxs-lookup"><span data-stu-id="03db1-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="03db1-109">Verwendet am Ende der nächsten halben Sekunde <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> eine Instanz der Klasse, um die Farbe schnell von Rot in Gelb zu ändern.</span><span class="sxs-lookup"><span data-stu-id="03db1-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="03db1-110">Diskrete Schlüsselbilder <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> wie erstellen plötzliche Änderungen zwischen Werten, d. h., die Farbänderung in diesem Teil der Animation erfolgt schnell und ist nicht subtil.</span><span class="sxs-lookup"><span data-stu-id="03db1-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="03db1-111">Verwendet in den letzten zwei Sekunden <xref:System.Windows.Media.Animation.SplineColorKeyFrame> eine Instanz der Klasse, um die Farbe erneut zu ändern – diesmal von Gelb zurück in Grün.</span><span class="sxs-lookup"><span data-stu-id="03db1-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="03db1-112">Spline-Schlüsselrahmen <xref:System.Windows.Media.Animation.SplineColorKeyFrame> wie erstellen sie einen variablen Übergang <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> zwischen Werten entsprechend den Werten der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="03db1-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="03db1-113">In diesem Beispiel beginnt die Farbveränderung zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.</span><span class="sxs-lookup"><span data-stu-id="03db1-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="03db1-114">Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="03db1-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03db1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03db1-115">See also</span></span>

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [<span data-ttu-id="03db1-116">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="03db1-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="03db1-117">Themen zur Vorgehensweise mit Keyframes</span><span class="sxs-lookup"><span data-stu-id="03db1-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
