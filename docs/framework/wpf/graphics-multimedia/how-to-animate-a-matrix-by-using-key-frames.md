---
title: 'Gewusst wie: Animieren einer Matrix mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: 8f58b43a870f2c85ae4349965f586a33e2f75a2a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485849"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="10582-102">Gewusst wie: Animieren einer Matrix mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="10582-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="10582-103">Dieses Beispiel zeigt, wie Sie animieren der <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Eigenschaft eine <xref:System.Windows.Media.MatrixTransform> mithilfe von Keyframes.</span><span class="sxs-lookup"><span data-stu-id="10582-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10582-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10582-104">Example</span></span>  
 <span data-ttu-id="10582-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> -Klasse zum Animieren der <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Eigenschaft eine <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="10582-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="10582-106">Im Beispiel wird die <xref:System.Windows.Media.MatrixTransform> Objekt, das die Darstellung und die Position des transformiert eine <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="10582-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="10582-107">Diese Animation verwendet die <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> Klasse, um zwei Keyframes und wird mit ihnen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="10582-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1.  <span data-ttu-id="10582-108">Erstellt eine Animation die erste <xref:System.Windows.Media.Matrix> während der ersten 0,2 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="10582-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="10582-109">Die Beispiel-Änderungen der <xref:System.Windows.Media.Matrix.M11%2A> und <xref:System.Windows.Media.Matrix.M12%2A> Eigenschaften der <xref:System.Windows.Media.Matrix>.</span><span class="sxs-lookup"><span data-stu-id="10582-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="10582-110">Diese Änderung bewirkt, dass die Schaltfläche zum Strecken und verzerrt werden.</span><span class="sxs-lookup"><span data-stu-id="10582-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="10582-111">Im Beispiel ändert sich auch die <xref:System.Windows.Media.Matrix.OffsetX%2A> und <xref:System.Windows.Media.Matrix.OffsetY%2A> Eigenschaften so, dass die Position der Schaltfläche zu ändern.</span><span class="sxs-lookup"><span data-stu-id="10582-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2.  <span data-ttu-id="10582-112">Die zweite animiert <xref:System.Windows.Media.Matrix> bei 1,0 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="10582-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="10582-113">Die Schaltfläche wird in eine andere Position verschoben, während die Schaltfläche nicht mehr verzerrt oder gestreckt wird.</span><span class="sxs-lookup"><span data-stu-id="10582-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3.  <span data-ttu-id="10582-114">Wird für die Animation endlos wiederholt.</span><span class="sxs-lookup"><span data-stu-id="10582-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10582-115">Keyframes, die Ableiten der <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> objekterstellung abrupte Sprünge zwischen Werten, d. h. die Verschiebung der Animation ist ruckartig.</span><span class="sxs-lookup"><span data-stu-id="10582-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="10582-116">Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="10582-116">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10582-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10582-117">See Also</span></span>  
 <xref:System.Windows.Media.MatrixTransform.Matrix%2A>  
 <xref:System.Windows.Media.MatrixTransform>  
 [<span data-ttu-id="10582-118">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="10582-118">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="10582-119">Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)</span><span class="sxs-lookup"><span data-stu-id="10582-119">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
