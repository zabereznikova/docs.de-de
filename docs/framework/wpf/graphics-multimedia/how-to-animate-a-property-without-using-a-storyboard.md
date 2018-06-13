---
title: 'Gewusst wie: Animieren einer Eigenschaft ohne Storyboard'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- non-Storyboard animation
- local animation [WPF]
- animation [WPF], non-Storyboard (local)
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
ms.openlocfilehash: 18f8fb4edf5f71904335180e43dd65bd9910bdef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561013"
---
# <a name="how-to-animate-a-property-without-using-a-storyboard"></a><span data-ttu-id="fd23b-102">Gewusst wie: Animieren einer Eigenschaft ohne Storyboard</span><span class="sxs-lookup"><span data-stu-id="fd23b-102">How to: Animate a Property Without Using a Storyboard</span></span>
<span data-ttu-id="fd23b-103">Dieses Beispiel zeigt eine Möglichkeit, eine Animation auf eine Eigenschaft anwenden, ohne eine <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="fd23b-103">This example shows one way to apply an animation to a property without using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd23b-104">Diese Funktionalität ist in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fd23b-104">This functionality is not available in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="fd23b-105">Informationen über das Animieren einer Eigenschaft in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="fd23b-105">For information about animating a property in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span></span>  
  
 <span data-ttu-id="fd23b-106">Um eine lokale Animation auf eine Eigenschaft anwenden möchten, verwenden Sie die <xref:System.Windows.UIElement.BeginAnimation%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="fd23b-106">To apply a local animation to a property, use the <xref:System.Windows.UIElement.BeginAnimation%2A> method.</span></span> <span data-ttu-id="fd23b-107">Diese Methode akzeptiert zwei Parameter: eine <xref:System.Windows.DependencyProperty> , der angibt, die zu animierende Eigenschaft und die Animation auf die Eigenschaft angewendet.</span><span class="sxs-lookup"><span data-stu-id="fd23b-107">This method takes two parameters: a <xref:System.Windows.DependencyProperty> that specifies the property to animate, and the animation to apply to that property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd23b-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fd23b-108">Example</span></span>  
 <span data-ttu-id="fd23b-109">Das folgende Beispiel zeigt, wie Sie die Breite und Hintergrund Farbe Animieren einer <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="fd23b-109">The following example shows how to animate the width and background color of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 <span data-ttu-id="fd23b-110">Eine Vielzahl von Animationsklassen in der <xref:System.Windows.Media.Animation> Namespace zum Animieren von verschiedenen Eigenschaften vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="fd23b-110">A variety of animation classes in the <xref:System.Windows.Media.Animation> namespace exist for animating different types of properties.</span></span> <span data-ttu-id="fd23b-111">Weitere Informationen über das Animieren von Eigenschaften finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fd23b-111">For more information about animating properties, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="fd23b-112">Weitere Informationen über Abhängigkeitseigenschaften (der Eigenschaftentyp, der in diesen Beispielen verwendet wird) und ihre Funktionen finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fd23b-112">For more information about dependency properties (the type of properties that are shown in these examples) and their features, see [Dependency Properties Overview](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span></span>  
  
 <span data-ttu-id="fd23b-113">Es gibt andere Möglichkeiten zum Animieren ohne <xref:System.Windows.Media.Animation.Storyboard> Objekte; Weitere Informationen finden Sie unter [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fd23b-113">There are other ways to animate without using <xref:System.Windows.Media.Animation.Storyboard> objects; for more information, see [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd23b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd23b-114">See Also</span></span>  
 <xref:System.Windows.Media.Animation.AnimationTimeline>  
 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>  
 <xref:System.Windows.Media.Animation>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [<span data-ttu-id="fd23b-115">Übersicht über die Verfahren zur Animation von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="fd23b-115">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [<span data-ttu-id="fd23b-116">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="fd23b-116">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
