---
title: 'Gewusst wie: Animieren einer 3D-Rotation mithilfe von Storyboards'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 088f1a33cfc73a706ffed55ffff6494adaf8fca4
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112212"
---
# <a name="how-to-animate-a-3d-rotation-using-storyboards"></a><span data-ttu-id="f5da0-102">Gewusst wie: Animieren einer 3D-Rotation mithilfe von Storyboards</span><span class="sxs-lookup"><span data-stu-id="f5da0-102">How to: Animate a 3D Rotation Using Storyboards</span></span>
<span data-ttu-id="f5da0-103">Das folgende Beispiel zeigt, wie ein 3D-Objekt gedreht wird, während <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> es <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> durch <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> Animieren der und Eigenschaften eines Objekts "wackelt".</span><span class="sxs-lookup"><span data-stu-id="f5da0-103">The following example shows how to make a 3D object rotate while it "wobbles" by animating the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> and <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> properties of an <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object.</span></span> <span data-ttu-id="f5da0-104">Dieses <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> Objekt gibt die Rotationstransformation des 3D-Objekts an, so dass durch Animieren seiner Eigenschaften der Wunschrotationseffekt erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="f5da0-104">This <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object specifies the rotation transform of the 3D object and so animating its properties creates the desire rotation effect.</span></span> <span data-ttu-id="f5da0-105">Im Storyboard <xref:System.Windows.Media.Animation.DoubleAnimation> wird verwendet, <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> um <xref:System.Windows.Media.Animation.Vector3DAnimation> die Eigenschaft zu <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> animieren, während sie zum Animieren der Eigenschaft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f5da0-105">Within the Storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> property while <xref:System.Windows.Media.Animation.Vector3DAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5da0-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f5da0-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="f5da0-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5da0-107">See also</span></span>

- [<span data-ttu-id="f5da0-108">Animieren einer 3D-Rotation mithilfe von Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="f5da0-108">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="f5da0-109">Animieren einer 3D-Rotation mithilfe von Key Frames (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="f5da0-109">Animate a 3D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="f5da0-110">3D-Grafikübersicht</span><span class="sxs-lookup"><span data-stu-id="f5da0-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="f5da0-111">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="f5da0-111">Storyboards Overview</span></span>](storyboards-overview.md)
