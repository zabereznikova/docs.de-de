---
title: 'Gewusst wie: Animieren einer Matrix mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: eb596cf728f8a7cc1964963b8509f42bdd7a392a
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344921"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="13acf-102">Gewusst wie: Animieren einer Matrix mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="13acf-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="13acf-103">In diesem Beispiel wird <xref:System.Windows.Media.MatrixTransform.Matrix%2A> gezeigt, <xref:System.Windows.Media.MatrixTransform> wie die Eigenschaft eines mithilfe von Schlüsselbildern animiert wird.</span><span class="sxs-lookup"><span data-stu-id="13acf-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13acf-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13acf-104">Example</span></span>  
 <span data-ttu-id="13acf-105">Im folgenden Beispiel <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> wird die <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Klasse <xref:System.Windows.Media.MatrixTransform>verwendet, um die Eigenschaft einer zu animieren.</span><span class="sxs-lookup"><span data-stu-id="13acf-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="13acf-106">Im Beispiel <xref:System.Windows.Media.MatrixTransform> wird das Objekt verwendet, <xref:System.Windows.Controls.Button>um die Darstellung und Position einer zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="13acf-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="13acf-107">Diese Animation <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> verwendet die Klasse, um zwei Schlüsselbilder zu erstellen, und führt die folgenden Schritte mit:</span><span class="sxs-lookup"><span data-stu-id="13acf-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1. <span data-ttu-id="13acf-108">Animiert <xref:System.Windows.Media.Matrix> die erste in den ersten 0,2 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="13acf-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="13acf-109">Das Beispiel <xref:System.Windows.Media.Matrix.M11%2A> ändert <xref:System.Windows.Media.Matrix.M12%2A> die <xref:System.Windows.Media.Matrix>und Eigenschaften der .</span><span class="sxs-lookup"><span data-stu-id="13acf-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="13acf-110">Diese Änderung bewirkt, dass sich die Schaltfläche dehnt und verzerrt wird.</span><span class="sxs-lookup"><span data-stu-id="13acf-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="13acf-111">Im Beispiel werden <xref:System.Windows.Media.Matrix.OffsetX%2A> <xref:System.Windows.Media.Matrix.OffsetY%2A> auch die und-Eigenschaften so geändert, dass die Schaltfläche die Position ändert.</span><span class="sxs-lookup"><span data-stu-id="13acf-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2. <span data-ttu-id="13acf-112">Animiert <xref:System.Windows.Media.Matrix> die Sekunde mit 1,0 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="13acf-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="13acf-113">Die Schaltfläche wird an eine andere Position verschoben, während die Schaltfläche nicht mehr verzerrt oder gestreckt ist.</span><span class="sxs-lookup"><span data-stu-id="13acf-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3. <span data-ttu-id="13acf-114">Wiederholt die Animation auf unbestimmte Zeit.</span><span class="sxs-lookup"><span data-stu-id="13acf-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13acf-115">Schlüsselbilder, die <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> vom Objekt ableiten, erzeugen plötzliche Sprünge zwischen Werten, d. h., die Bewegung der Animation ist ruckartig.</span><span class="sxs-lookup"><span data-stu-id="13acf-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="13acf-116">Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="13acf-116">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13acf-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13acf-117">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [<span data-ttu-id="13acf-118">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="13acf-118">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="13acf-119">Themen zur Vorgehensweise mit Keyframes</span><span class="sxs-lookup"><span data-stu-id="13acf-119">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
