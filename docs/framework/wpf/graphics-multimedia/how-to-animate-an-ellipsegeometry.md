---
title: 'Gewusst wie: Animieren eines "EllipseGeometry"-Elements'
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
- animation [WPF], EllipseGeometry objects [WPF]
- EllipseGeometry objects [WPF], animating
- graphics [WPF], animation
ms.assetid: 767b9b6e-9cb7-482e-b6c2-fee7750c3995
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 948aa340436b51b6e8cbb09f4b0791535ca5ecd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-an-ellipsegeometry"></a><span data-ttu-id="fa026-102">Gewusst wie: Animieren eines "EllipseGeometry"-Elements</span><span class="sxs-lookup"><span data-stu-id="fa026-102">How to: Animate an EllipseGeometry</span></span>
<span data-ttu-id="fa026-103">In diesem Beispiel wird gezeigt, wie zum Animieren einer <xref:System.Windows.Media.Geometry> innerhalb einer <xref:System.Windows.Shapes.Path> Element.</span><span class="sxs-lookup"><span data-stu-id="fa026-103">This example shows how to animate a <xref:System.Windows.Media.Geometry> within a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="fa026-104">Im folgenden Beispiel ein <xref:System.Windows.Media.Animation.PointAnimation> dient zum Animieren der <xref:System.Windows.Media.EllipseGeometry.Center%2A> von einer <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="fa026-104">In the following example, a <xref:System.Windows.Media.Animation.PointAnimation> is used to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> of an <xref:System.Windows.Media.EllipseGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa026-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa026-105">Example</span></span>  
 [!code-xaml[animatepath_snip_XAML#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip_XAML/CS/EllipseGeometryExample.xaml#1)]  
  
 [!code-csharp[animatepath_snip#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip/CSharp/EllipseGeometryExample.cs#101)]  
  
 [!code-vb[animatepath_snip#201](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animatepath_snip/VisualBasic/EllipseGeometryExample.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="fa026-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa026-106">See Also</span></span>  
 [<span data-ttu-id="fa026-107">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="fa026-107">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="fa026-108">Übersicht über Geometrien</span><span class="sxs-lookup"><span data-stu-id="fa026-108">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
