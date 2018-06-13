---
title: 'Gewusst wie: Animieren einer 3D-Drehung mit Storyboards'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3-D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3-D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: a6cc8774c14d4b393b0d04822216c894e486ba66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556704"
---
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a><span data-ttu-id="da45a-102">Gewusst wie: Animieren einer 3D-Drehung mit Storyboards</span><span class="sxs-lookup"><span data-stu-id="da45a-102">How to: Animate a 3-D Rotation Using Storyboards</span></span>
<span data-ttu-id="da45a-103">Im folgende Beispiel wird gezeigt, wie ein 3D-Objekt gedreht wird, während es "durch animieren wackelt" die <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> und <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> Eigenschaften einer <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> Objekt.</span><span class="sxs-lookup"><span data-stu-id="da45a-103">The following example shows how to make a 3D object rotate while it "wobbles" by animating the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> and <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> properties of an <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object.</span></span> <span data-ttu-id="da45a-104">Dies <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> Objekt gibt an, die Drehungstransformation des 3D Objekts und die Desire Drehung Auswirkungen also die Animation seiner Eigenschaften erstellt.</span><span class="sxs-lookup"><span data-stu-id="da45a-104">This <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object specifies the rotation transform of the 3D object and so animating its properties creates the desire rotation effect.</span></span> <span data-ttu-id="da45a-105">Innerhalb des Storyboards <xref:System.Windows.Media.Animation.DoubleAnimation> dient zum Animieren der <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> Eigenschaft beim <xref:System.Windows.Media.Animation.Vector3DAnimation> wird verwendet, um dem animiert werden soll die <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="da45a-105">Within the Storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> property while <xref:System.Windows.Media.Animation.Vector3DAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da45a-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da45a-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="da45a-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da45a-107">See Also</span></span>  
 [<span data-ttu-id="da45a-108">Animieren einer 3D-Drehung mit Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="da45a-108">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [<span data-ttu-id="da45a-109">Animieren einer 3D-Drehung mithilfe von Keyframes (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="da45a-109">Animate a 3-D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)  
 [<span data-ttu-id="da45a-110">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="da45a-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="da45a-111">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="da45a-111">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
