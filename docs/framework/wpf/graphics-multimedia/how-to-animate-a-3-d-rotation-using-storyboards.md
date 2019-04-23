---
title: 'Vorgehensweise: Animieren einer 3D-Drehung mit Storyboards'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3-D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3-D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 03b01205f1a31426a01b09533b350682c384df4b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59146197"
---
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a><span data-ttu-id="904e1-102">Vorgehensweise: Animieren einer 3D-Drehung mit Storyboards</span><span class="sxs-lookup"><span data-stu-id="904e1-102">How to: Animate a 3-D Rotation Using Storyboards</span></span>
<span data-ttu-id="904e1-103">Das folgende Beispiel zeigt, wie Sie ein 3D-Objekt gedreht, während es "durch die Animation wackelt" die <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> und <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> Eigenschaften eine <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> Objekt.</span><span class="sxs-lookup"><span data-stu-id="904e1-103">The following example shows how to make a 3D object rotate while it "wobbles" by animating the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> and <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> properties of an <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object.</span></span> <span data-ttu-id="904e1-104">Dies <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> Objekt gibt an, die Drehungstransformation des 3D-Objekts, und so animieren dessen Eigenschaften die Auswirkungen der gewünschten Rotation erstellt.</span><span class="sxs-lookup"><span data-stu-id="904e1-104">This <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object specifies the rotation transform of the 3D object and so animating its properties creates the desire rotation effect.</span></span> <span data-ttu-id="904e1-105">In diesem Storyboard <xref:System.Windows.Media.Animation.DoubleAnimation> wird verwendet, um das Animieren der <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> Eigenschaft beim <xref:System.Windows.Media.Animation.Vector3DAnimation> wird verwendet, um das Animieren der <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="904e1-105">Within the Storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> property while <xref:System.Windows.Media.Animation.Vector3DAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="904e1-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="904e1-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="904e1-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="904e1-107">See also</span></span>

- [<span data-ttu-id="904e1-108">Animieren einer 3D-Drehung mit Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="904e1-108">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="904e1-109">Animieren einer 3D-Drehung mithilfe von Keyframes (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="904e1-109">Animate a 3-D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="904e1-110">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="904e1-110">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="904e1-111">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="904e1-111">Storyboards Overview</span></span>](storyboards-overview.md)
