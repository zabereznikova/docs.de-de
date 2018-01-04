---
title: 'Gewusst wie: Animieren eines Objekts entlang eines Pfads (PointAnimation)'
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
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 399d6b8028b8715f38335089a723707657df4a98
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a><span data-ttu-id="db403-102">Gewusst wie: Animieren eines Objekts entlang eines Pfads (PointAnimation)</span><span class="sxs-lookup"><span data-stu-id="db403-102">How to: Animate an Object Along a Path (Point Animation)</span></span>
<span data-ttu-id="db403-103">Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.Animation.PointAnimationUsingPath> zu animierende Objekt eine <xref:System.Windows.Point> entlang eines Kurvenpfads.</span><span class="sxs-lookup"><span data-stu-id="db403-103">This example shows how to use a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> object to animate a <xref:System.Windows.Point> along a curved path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db403-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="db403-104">Example</span></span>  
 <span data-ttu-id="db403-105">Im folgenden Beispiel wird ein <xref:System.Windows.Media.EllipseGeometry> entlang eines Pfads, definiert durch eine <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="db403-105">The following example moves an <xref:System.Windows.Media.EllipseGeometry> along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="db403-106">Der Ellipsengeometrie <xref:System.Windows.Media.EllipseGeometry.Center%2A> -Eigenschaft, die nimmt eine <xref:System.Windows.Point> Wert und gibt dessen Position; zum Verschieben der Geometrie Ellipse animieren Sie seine <xref:System.Windows.Media.EllipseGeometry.Center%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="db403-106">The ellipse geometry's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property, which takes a <xref:System.Windows.Point> value, specifies its position; to move the ellipse geometry, you animate its <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span> <span data-ttu-id="db403-107">Im Beispiel wird eine <xref:System.Windows.Media.Animation.PointAnimationUsingPath> zum Animieren der <xref:System.Windows.Media.EllipseGeometry> des Objekts <xref:System.Windows.Media.EllipseGeometry.Center%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="db403-107">The example uses a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> to animate the <xref:System.Windows.Media.EllipseGeometry> object's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 <span data-ttu-id="db403-108">Das vollständige Beispiel finden Sie unter [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="db403-108">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="db403-109">Die Codeversion des obigen Beispiels verwendet eine <xref:System.Windows.Media.Animation.Storyboard> zum Animieren der <xref:System.Windows.Media.EllipseGeometry>, obwohl nur eine einzige Animation angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="db403-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="db403-110">Ein <xref:System.Windows.Media.Animation.Storyboard> ist häufig der einfachste Weg, mehrere Animationen anzuwenden, da diese mit dem gleichen gesteuert werden können <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="db403-110">A <xref:System.Windows.Media.Animation.Storyboard> is often the easiest way to apply multiple animations because these animations can be controlled by the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="db403-111">Eine einfachere Möglichkeit zum Anwenden einer einzelnen Animation auf eine Eigenschaft, wenn Code mit allerdings ist die Verwendung der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="db403-111">However, an easier way to apply a single animation to a property when using code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="db403-112">Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="db403-112">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db403-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db403-113">See Also</span></span>  
 [<span data-ttu-id="db403-114">Beispiel zu Textanimation</span><span class="sxs-lookup"><span data-stu-id="db403-114">Path Animation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [<span data-ttu-id="db403-115">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="db403-115">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="db403-116">Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)</span><span class="sxs-lookup"><span data-stu-id="db403-116">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
