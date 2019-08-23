---
title: 'Vorgehensweise: Animieren einer Matrix mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: 6aa3e27cdfda7597c9b6acbf2980a2774f2b667b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963024"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="b8d85-102">Vorgehensweise: Animieren einer Matrix mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="b8d85-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="b8d85-103">In diesem Beispiel <xref:System.Windows.Media.MatrixTransform> wird gezeigt, wie <xref:System.Windows.Media.MatrixTransform.Matrix%2A> die-Eigenschaft eines mithilfe von Keyframes animiert wird.</span><span class="sxs-lookup"><span data-stu-id="b8d85-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8d85-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8d85-104">Example</span></span>  
 <span data-ttu-id="b8d85-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> -Klasse verwendet, <xref:System.Windows.Media.MatrixTransform.Matrix%2A> um die- <xref:System.Windows.Media.MatrixTransform>Eigenschaft eines zu animieren.</span><span class="sxs-lookup"><span data-stu-id="b8d85-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="b8d85-106">Im Beispiel wird das <xref:System.Windows.Media.MatrixTransform> -Objekt verwendet, um die Darstellung und Position <xref:System.Windows.Controls.Button>eines zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="b8d85-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="b8d85-107">Diese Animation verwendet die <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> -Klasse, um zwei Keyframes zu erstellen und mit Ihnen die folgenden Aktionen durchführen zu können:</span><span class="sxs-lookup"><span data-stu-id="b8d85-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1. <span data-ttu-id="b8d85-108">Animiert den ersten <xref:System.Windows.Media.Matrix> während der ersten 0,2 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="b8d85-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="b8d85-109">Im Beispiel werden die <xref:System.Windows.Media.Matrix.M11%2A> - <xref:System.Windows.Media.Matrix.M12%2A> Eigenschaft und die <xref:System.Windows.Media.Matrix>-Eigenschaft der geändert.</span><span class="sxs-lookup"><span data-stu-id="b8d85-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="b8d85-110">Diese Änderung bewirkt, dass die Schaltfläche gestreckt wird und verzerrt wird.</span><span class="sxs-lookup"><span data-stu-id="b8d85-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="b8d85-111">Das Beispiel ändert auch die <xref:System.Windows.Media.Matrix.OffsetX%2A> - <xref:System.Windows.Media.Matrix.OffsetY%2A> Eigenschaft und die-Eigenschaft, sodass die Schaltfläche die Position ändert.</span><span class="sxs-lookup"><span data-stu-id="b8d85-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2. <span data-ttu-id="b8d85-112">Animiert den zweiten <xref:System.Windows.Media.Matrix> um 1,0 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="b8d85-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="b8d85-113">Die Schaltfläche wird an eine andere Position verschoben, während die Schaltfläche nicht mehr verzerrt oder gestreckt wird.</span><span class="sxs-lookup"><span data-stu-id="b8d85-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3. <span data-ttu-id="b8d85-114">Wiederholt die Animation unbegrenzt.</span><span class="sxs-lookup"><span data-stu-id="b8d85-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8d85-115">Keyframes, die vom <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> -Objekt abgeleitet werden, erzeugen plötzliche Sprünge zwischen Werten, d. h., dass die Bewegung der Animation ruckartig ist.</span><span class="sxs-lookup"><span data-stu-id="b8d85-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="b8d85-116">Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="b8d85-116">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8d85-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8d85-117">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [<span data-ttu-id="b8d85-118">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="b8d85-118">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="b8d85-119">Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)</span><span class="sxs-lookup"><span data-stu-id="b8d85-119">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
