---
title: 'Vorgehensweise: Animieren eines Objekts mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: b0a0f7c00125a43228a2658415b72f4d541f37be
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59315841"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="974d1-102">Vorgehensweise: Animieren eines Objekts mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="974d1-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="974d1-103">In diesem Beispiel wird gezeigt, wie zum Animieren eines Objekts, die in diesem Beispiel wird die <xref:System.Windows.Controls.Page.Background%2A> Eigenschaft eine <xref:System.Windows.Controls.Page> -Steuerelement, mithilfe von Keyframes.</span><span class="sxs-lookup"><span data-stu-id="974d1-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="974d1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="974d1-104">Example</span></span>  
 <span data-ttu-id="974d1-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> -Klasse zum Animieren der Farbe ändert, für die <xref:System.Windows.Controls.Page.Background%2A> Eigenschaft eine <xref:System.Windows.Controls.Page> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="974d1-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="974d1-106">Beispiel ändert sich die Animation in einen anderen Hintergrundpinsel in regelmäßigen Abständen.</span><span class="sxs-lookup"><span data-stu-id="974d1-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="974d1-107">Diese Animation verwendet die <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> Klasse, um drei verschiedene Keyframes zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="974d1-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="974d1-108">Die Animation werden Keyframes folgendermaßen verwendet:</span><span class="sxs-lookup"><span data-stu-id="974d1-108">The animation uses key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="974d1-109">Am Ende der ersten Sekunde, eine Animation auf eine Instanz von der <xref:System.Windows.Media.LinearGradientBrush> Klasse.</span><span class="sxs-lookup"><span data-stu-id="974d1-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="974d1-110">In diesem Abschnitt des Beispiels gilt die Farbe des Hintergrunds ein lineares Farbverlaufs, damit die Farbe von Gelb zu Orange zu rot ändert.</span><span class="sxs-lookup"><span data-stu-id="974d1-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2. <span data-ttu-id="974d1-111">Am Ende der nächsten Sekunde, eine Animation auf eine Instanz von der <xref:System.Windows.Media.RadialGradientBrush> Klasse.</span><span class="sxs-lookup"><span data-stu-id="974d1-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="974d1-112">In diesem Abschnitt des Beispiels gilt die Farbe des Hintergrunds ein radiales Farbverlaufs, damit die Farbe von weiß zu Schwarz Blau wechselt.</span><span class="sxs-lookup"><span data-stu-id="974d1-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3. <span data-ttu-id="974d1-113">Am Ende des dritten zweiten, eine Animation auf eine Instanz von der <xref:System.Windows.Media.DrawingBrush> Klasse.</span><span class="sxs-lookup"><span data-stu-id="974d1-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="974d1-114">In diesem Abschnitt des Beispiels wird ein Schachbrettmuster in den Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="974d1-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4. <span data-ttu-id="974d1-115">Die Animation erneut gestartet, und es wird auf unbestimmte Zeit wiederholt.</span><span class="sxs-lookup"><span data-stu-id="974d1-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="974d1-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> ist die einzige Art des Keyframes, mit denen Sie mit der <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> Klasse.</span><span class="sxs-lookup"><span data-stu-id="974d1-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="974d1-117">Schlüssel wie frames <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> können abrupte Veränderungen in den Werten, d. h., ändert sich die Farbe, in diesem Beispiel treten plötzlich.</span><span class="sxs-lookup"><span data-stu-id="974d1-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="974d1-118">Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="974d1-118">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="974d1-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="974d1-119">See also</span></span>

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [<span data-ttu-id="974d1-120">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="974d1-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="974d1-121">Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)</span><span class="sxs-lookup"><span data-stu-id="974d1-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
