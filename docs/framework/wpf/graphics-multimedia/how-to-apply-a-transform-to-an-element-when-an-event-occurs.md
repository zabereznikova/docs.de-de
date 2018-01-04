---
title: 'Gewusst wie: Anwenden einer Transformation auf ein Element beim Auftreten eines Ereignisses'
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
- graphics [WPF], transformations as event responses
- properties [WPF], LayoutTransform
- transformations as event responses [WPF]
- properties [WPF], RenderTransform
- LayoutTransform property [WPF]
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e58e49ecc852b87d03d4112208354e608248984
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a><span data-ttu-id="670c1-102">Gewusst wie: Anwenden einer Transformation auf ein Element beim Auftreten eines Ereignisses</span><span class="sxs-lookup"><span data-stu-id="670c1-102">How to: Apply a Transform to an Element When an Event Occurs</span></span>
<span data-ttu-id="670c1-103">In diesem Beispiel wird gezeigt, wie zum Anwenden einer <xref:System.Windows.Media.ScaleTransform> bei Auftreten eines Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="670c1-103">This example shows how to apply a <xref:System.Windows.Media.ScaleTransform> when an event occurs.</span></span> <span data-ttu-id="670c1-104">Mithilfe des hier dargestellten Konzepts können Sie auch andere Transformationstypen anwenden.</span><span class="sxs-lookup"><span data-stu-id="670c1-104">The concept that is shown here is the same that you use for applying other types of transformations.</span></span> <span data-ttu-id="670c1-105">Weitere Informationen zu den verfügbaren Typen von Transformationen finden Sie unter der <xref:System.Windows.Media.Transform> Klasse oder [Transforms Overview](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).</span><span class="sxs-lookup"><span data-stu-id="670c1-105">For more information about the available types of transformations, see the <xref:System.Windows.Media.Transform> class or [Transforms Overview](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).</span></span>  
  
 <span data-ttu-id="670c1-106">Sie können mit einem der folgenden beiden Verfahren eine Transformation auf ein Element anwenden:</span><span class="sxs-lookup"><span data-stu-id="670c1-106">You can apply a transform to an element in either of these two ways:</span></span>  
  
-   <span data-ttu-id="670c1-107">Wenn Sie dies tun *nicht* möchten Sie die Transformation auf das Layout auswirken, verwenden Sie die <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft des Elements.</span><span class="sxs-lookup"><span data-stu-id="670c1-107">If you do *not* want the transform to affect layout, use the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
-   <span data-ttu-id="670c1-108">Wenn Sie die Transformation auf das Layout auswirken soll, verwenden Sie die <xref:System.Windows.FrameworkElement.LayoutTransform%2A> -Eigenschaft des Elements.</span><span class="sxs-lookup"><span data-stu-id="670c1-108">If you do want the transform to affect layout, use the <xref:System.Windows.FrameworkElement.LayoutTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="670c1-109">Das folgende Beispiel wendet eine <xref:System.Windows.Media.ScaleTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="670c1-109">The following example applies a <xref:System.Windows.Media.ScaleTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a button.</span></span> <span data-ttu-id="670c1-110">Beim Bewegen der Maus auf die Schaltfläche der <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> Eigenschaften der <xref:System.Windows.Media.ScaleTransform> festgelegt `2`, dies bedeutet, dass die Schaltfläche größer wird.</span><span class="sxs-lookup"><span data-stu-id="670c1-110">When the mouse moves over the button, the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties of the <xref:System.Windows.Media.ScaleTransform> are set to `2`, which causes the button to become larger.</span></span> <span data-ttu-id="670c1-111">Wenn die Maus bewegt wird, deaktiviert die Schaltfläche <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> festgelegt `1`, dies bedeutet, dass die Schaltfläche, um die ursprüngliche Größe zurück.</span><span class="sxs-lookup"><span data-stu-id="670c1-111">When the mouse moves off the button, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> are set to `1`, which causes the button to return to its original size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="670c1-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="670c1-112">Example</span></span>  
 [!code-xaml[ButtonTransform#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a><span data-ttu-id="670c1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="670c1-113">See Also</span></span>  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.ScaleTransform>  
 [<span data-ttu-id="670c1-114">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="670c1-114">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="670c1-115">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="670c1-115">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)  
 [<span data-ttu-id="670c1-116">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="670c1-116">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
