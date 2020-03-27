---
title: 'Gewusst wie: Animieren eines Objekts mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 0bc33b189fd856dbe8106c1db35bc18e27ea131e
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344707"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="0e77f-102">Gewusst wie: Animieren eines Objekts mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="0e77f-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="0e77f-103">In diesem Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.Page.Background%2A> Objekt, <xref:System.Windows.Controls.Page> das in diesem Beispiel die Eigenschaft eines Steuerelements ist, mithilfe von Schlüsselrahmen animiert wird.</span><span class="sxs-lookup"><span data-stu-id="0e77f-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e77f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e77f-104">Example</span></span>  
 <span data-ttu-id="0e77f-105">Im folgenden Beispiel <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> wird die Klasse <xref:System.Windows.Controls.Page.Background%2A> verwendet, <xref:System.Windows.Controls.Page> um Farbänderungen für die Eigenschaft eines Steuerelements zu animieren.</span><span class="sxs-lookup"><span data-stu-id="0e77f-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="0e77f-106">Die Beispielanimation ändert sich in regelmäßigen Abständen in einen anderen Hintergrundpinsel.</span><span class="sxs-lookup"><span data-stu-id="0e77f-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="0e77f-107">Diese Animation <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> verwendet die Klasse, um drei verschiedene Schlüsselbilder zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0e77f-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="0e77f-108">Die Animation verwendet Schlüsselbilder auf folgende Weise:</span><span class="sxs-lookup"><span data-stu-id="0e77f-108">The animation uses key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="0e77f-109">Animiert am Ende der ersten Sekunde <xref:System.Windows.Media.LinearGradientBrush> eine Instanz der Klasse.</span><span class="sxs-lookup"><span data-stu-id="0e77f-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="0e77f-110">In diesem Beispielabschnitt wird ein linearer Farbverlauf auf die Hintergrundfarbe angewendet, sodass die Farbe von gelb zu orange zu rot übergeht.</span><span class="sxs-lookup"><span data-stu-id="0e77f-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2. <span data-ttu-id="0e77f-111">Animiert am Ende der nächsten Sekunde <xref:System.Windows.Media.RadialGradientBrush> eine Instanz der Klasse.</span><span class="sxs-lookup"><span data-stu-id="0e77f-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="0e77f-112">In diesem Beispielabschnitt wird ein radialer Farbverlauf auf die Hintergrundfarbe angewendet, sodass die Farbe von Weiß zu Blau zu Schwarz übergeht.</span><span class="sxs-lookup"><span data-stu-id="0e77f-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3. <span data-ttu-id="0e77f-113">Am Ende der dritten Sekunde wird eine <xref:System.Windows.Media.DrawingBrush> Instanz der Klasse animiert.</span><span class="sxs-lookup"><span data-stu-id="0e77f-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="0e77f-114">In diesem Beispielabschnitt wird ein Schachbrettmuster auf den Hintergrund angewendet.</span><span class="sxs-lookup"><span data-stu-id="0e77f-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4. <span data-ttu-id="0e77f-115">Die Animation wird erneut und auf unbestimmte Zeit wiederholt.</span><span class="sxs-lookup"><span data-stu-id="0e77f-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0e77f-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>ist der einzige Schlüsselrahmentyp, den <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> Sie mit der Klasse verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0e77f-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="0e77f-117">Schlüsselrahmen <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> wie erstellen plötzliche Änderungen in Werten, das heißt, die Farbänderungen in diesem Beispiel treten plötzlich auf.</span><span class="sxs-lookup"><span data-stu-id="0e77f-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="0e77f-118">Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="0e77f-118">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e77f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e77f-119">See also</span></span>

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [<span data-ttu-id="0e77f-120">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="0e77f-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="0e77f-121">Themen zur Vorgehensweise mit Keyframes</span><span class="sxs-lookup"><span data-stu-id="0e77f-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
