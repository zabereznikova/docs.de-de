---
title: 'Vorgehensweise: Animieren einer Matrix mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: ff5320fa5b4441ae3e0f414b274ab9118b77ec50
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336797"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="c3775-102">Vorgehensweise: Animieren einer Matrix mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="c3775-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="c3775-103">Dieses Beispiel zeigt, wie Sie animieren der <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Eigenschaft eine <xref:System.Windows.Media.MatrixTransform> mithilfe von Keyframes.</span><span class="sxs-lookup"><span data-stu-id="c3775-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3775-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3775-104">Example</span></span>  
 <span data-ttu-id="c3775-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> -Klasse zum Animieren der <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Eigenschaft eine <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="c3775-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="c3775-106">Im Beispiel wird die <xref:System.Windows.Media.MatrixTransform> Objekt, das die Darstellung und die Position des transformiert eine <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="c3775-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="c3775-107">Diese Animation verwendet die <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> Klasse, um zwei Keyframes und wird mit ihnen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c3775-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1. <span data-ttu-id="c3775-108">Erstellt eine Animation die erste <xref:System.Windows.Media.Matrix> während der ersten 0,2 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="c3775-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="c3775-109">Die Beispiel-Änderungen der <xref:System.Windows.Media.Matrix.M11%2A> und <xref:System.Windows.Media.Matrix.M12%2A> Eigenschaften der <xref:System.Windows.Media.Matrix>.</span><span class="sxs-lookup"><span data-stu-id="c3775-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="c3775-110">Diese Änderung bewirkt, dass die Schaltfläche zum Strecken und verzerrt werden.</span><span class="sxs-lookup"><span data-stu-id="c3775-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="c3775-111">Im Beispiel ändert sich auch die <xref:System.Windows.Media.Matrix.OffsetX%2A> und <xref:System.Windows.Media.Matrix.OffsetY%2A> Eigenschaften so, dass die Position der Schaltfläche zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c3775-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2. <span data-ttu-id="c3775-112">Die zweite animiert <xref:System.Windows.Media.Matrix> bei 1,0 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="c3775-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="c3775-113">Die Schaltfläche wird in eine andere Position verschoben, während die Schaltfläche nicht mehr verzerrt oder gestreckt wird.</span><span class="sxs-lookup"><span data-stu-id="c3775-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3. <span data-ttu-id="c3775-114">Wird für die Animation endlos wiederholt.</span><span class="sxs-lookup"><span data-stu-id="c3775-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3775-115">Keyframes, die Ableiten der <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> objekterstellung abrupte Sprünge zwischen Werten, d. h. die Verschiebung der Animation ist ruckartig.</span><span class="sxs-lookup"><span data-stu-id="c3775-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="c3775-116">Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="c3775-116">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3775-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3775-117">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [<span data-ttu-id="c3775-118">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="c3775-118">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="c3775-119">Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)</span><span class="sxs-lookup"><span data-stu-id="c3775-119">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
