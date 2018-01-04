---
title: 'Gewusst wie: Animieren der Position eines Objekts mit PointAnimation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: baa412a889ee82c9bf20ff1d6420d8a86f339ca6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a><span data-ttu-id="db429-102">Gewusst wie: Animieren der Position eines Objekts mit PointAnimation</span><span class="sxs-lookup"><span data-stu-id="db429-102">How to: Animate the Position of an Object by Using PointAnimation</span></span>
<span data-ttu-id="db429-103">Dieses Beispiel zeigt, wie die <xref:System.Windows.Media.Animation.PointAnimation> Klasse, um ein Objekt entlang Animieren einer <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="db429-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimation> class to animate an object along a <xref:System.Windows.Shapes.Path>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db429-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="db429-104">Example</span></span>  
 <span data-ttu-id="db429-105">Im folgenden Beispiel wird eine Ellipse, die zusammen eine <xref:System.Windows.Shapes.Path> von einem Punkt auf dem Bildschirm zu einem anderen.</span><span class="sxs-lookup"><span data-stu-id="db429-105">The following example moves an ellipse along a <xref:System.Windows.Shapes.Path> from one point on the screen to another.</span></span> <span data-ttu-id="db429-106">Das Beispiel erstellt eine Animation, die Position des ein <xref:System.Windows.Media.EllipseGeometry> mit <xref:System.Windows.Media.Animation.PointAnimation> zum Animieren der <xref:System.Windows.Media.EllipseGeometry.Center%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="db429-106">The example animates the position of an <xref:System.Windows.Media.EllipseGeometry> by using <xref:System.Windows.Media.Animation.PointAnimation> to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="db429-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db429-107">See Also</span></span>  
 <xref:System.Windows.Media.Animation.PointAnimation>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.EllipseGeometry>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A>  
 [<span data-ttu-id="db429-108">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="db429-108">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="db429-109">Grafiken und Multimedia</span><span class="sxs-lookup"><span data-stu-id="db429-109">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
 [<span data-ttu-id="db429-110">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="db429-110">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)  
 [<span data-ttu-id="db429-111">Animation und zeitlichen Steuerung</span><span class="sxs-lookup"><span data-stu-id="db429-111">Animation and Timing</span></span>](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="db429-112">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="db429-112">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
