---
title: 'Gewusst wie: Animieren eines Objekts mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 7dc49bc6b3f9156507cb821bfc32b269365b206c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558539"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="e8f72-102">Gewusst wie: Animieren eines Objekts mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="e8f72-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="e8f72-103">In diesem Beispiel wird gezeigt, wie ein Objekt animiert wird in diesem Beispiel wird die <xref:System.Windows.Controls.Page.Background%2A> Eigenschaft von einem <xref:System.Windows.Controls.Page> mithilfe von Keyframes.</span><span class="sxs-lookup"><span data-stu-id="e8f72-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8f72-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e8f72-104">Example</span></span>  
 <span data-ttu-id="e8f72-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> Klasse zu animierende Farbe ändert, für die <xref:System.Windows.Controls.Page.Background%2A> Eigenschaft ein <xref:System.Windows.Controls.Page> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e8f72-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="e8f72-106">Die Animation Beispiel ändert sich zu einem anderen Hintergrundpinsel in regelmäßigen Abständen.</span><span class="sxs-lookup"><span data-stu-id="e8f72-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="e8f72-107">Diese Animation verwendet die <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> Klasse, um drei verschiedene Keyframes zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e8f72-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="e8f72-108">Die Animation verwendet Keyframes auf folgende Weise:</span><span class="sxs-lookup"><span data-stu-id="e8f72-108">The animation uses key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="e8f72-109">Eine Animation am Ende der ersten Sekunde eine Instanz von der <xref:System.Windows.Media.LinearGradientBrush> Klasse.</span><span class="sxs-lookup"><span data-stu-id="e8f72-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="e8f72-110">In diesem Abschnitt des Beispiels gilt die Farbe des Hintergrunds ein lineares Farbverlaufs, damit die Farbe in Orange ändert sich in Rot über gelb wechselt.</span><span class="sxs-lookup"><span data-stu-id="e8f72-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2.  <span data-ttu-id="e8f72-111">Eine Animation am Ende der nächsten Sekunde eine Instanz von der <xref:System.Windows.Media.RadialGradientBrush> Klasse.</span><span class="sxs-lookup"><span data-stu-id="e8f72-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="e8f72-112">In diesem Abschnitt des Beispiels wird die Farbe des Hintergrunds radialen Farbverlaufs betrifft, so, dass die Farbe von Weiß in Schwarz Blau übergeht.</span><span class="sxs-lookup"><span data-stu-id="e8f72-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3.  <span data-ttu-id="e8f72-113">Eine Animation am Ende der dritten Sekunde eine Instanz von der <xref:System.Windows.Media.DrawingBrush> Klasse.</span><span class="sxs-lookup"><span data-stu-id="e8f72-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="e8f72-114">In diesem Abschnitt des Beispiels wird ein Schachbrettmuster im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="e8f72-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4.  <span data-ttu-id="e8f72-115">Die Animation wird erneut gestartet und auf unbestimmte Zeit wiederholt.</span><span class="sxs-lookup"><span data-stu-id="e8f72-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8f72-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> ist die einzige Art des Keyframes, die mit der <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> Klasse.</span><span class="sxs-lookup"><span data-stu-id="e8f72-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="e8f72-117">Keyframes wie <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> erstellen dabei plötzliche Änderungen in Werten, d. h., ändert sich die Farbe in diesem Beispiel plötzlich auftreten.</span><span class="sxs-lookup"><span data-stu-id="e8f72-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="e8f72-118">Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="e8f72-118">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8f72-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8f72-119">See Also</span></span>  
 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.Page.Background%2A>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>  
 <xref:System.Windows.Media.LinearGradientBrush>  
 <xref:System.Windows.Media.RadialGradientBrush>  
 <xref:System.Windows.Media.DrawingBrush>  
 [<span data-ttu-id="e8f72-120">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="e8f72-120">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="e8f72-121">Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)</span><span class="sxs-lookup"><span data-stu-id="e8f72-121">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
