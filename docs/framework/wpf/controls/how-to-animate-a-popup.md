---
title: 'Gewusst wie: Animieren eines Popups'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd79b29849510f40034dd0e2f1d9668c9b742929
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-popup"></a><span data-ttu-id="99646-102">Gewusst wie: Animieren eines Popups</span><span class="sxs-lookup"><span data-stu-id="99646-102">How to: Animate a Popup</span></span>
<span data-ttu-id="99646-103">Dieses Beispiel zeigt zwei Möglichkeiten zum Animieren einer <xref:System.Windows.Controls.Primitives.Popup> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="99646-103">This example shows two ways to animate a <xref:System.Windows.Controls.Primitives.Popup> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99646-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="99646-104">Example</span></span>  
 <span data-ttu-id="99646-105">Im folgenden Beispiel wird die <xref:System.Windows.Controls.Primitives.PopupAnimation> Eigenschaft auf einen Wert von <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, wodurch die <xref:System.Windows.Controls.Primitives.Popup> "Folie-in" Wenn es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="99646-105">The following example sets the <xref:System.Windows.Controls.Primitives.PopupAnimation> property to a value of <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, which causes the <xref:System.Windows.Controls.Primitives.Popup> to "slide-in" when it appears.</span></span>  
  
 <span data-ttu-id="99646-106">Um Drehen der <xref:System.Windows.Controls.Primitives.Popup>, in diesem Beispiel wird eine <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft auf die <xref:System.Windows.Controls.Canvas>, also das untergeordnete Element des der <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="99646-106">In order to rotate the <xref:System.Windows.Controls.Primitives.Popup>, this example assigns a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property on the <xref:System.Windows.Controls.Canvas>, which is the child element of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  
  
 <span data-ttu-id="99646-107">Für die Transformation ordnungsgemäß funktioniert, muss im Beispiel Festlegen der <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="99646-107">For the transform to work correctly, the example must set the <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> property to `true`.</span></span> <span data-ttu-id="99646-108">Darüber hinaus die <xref:System.Windows.FrameworkElement.Margin%2A> auf die <xref:System.Windows.Controls.Canvas> Inhalt muss genügend Speicherplatz für angeben der <xref:System.Windows.Controls.Primitives.Popup> drehen.</span><span class="sxs-lookup"><span data-stu-id="99646-108">In addition, the <xref:System.Windows.FrameworkElement.Margin%2A> on the <xref:System.Windows.Controls.Canvas> content must specify enough space for the <xref:System.Windows.Controls.Primitives.Popup> to rotate.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 <span data-ttu-id="99646-109">Das folgende Beispiel zeigt wie eine <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis, das auftritt, wenn eine <xref:System.Windows.Controls.Button> geklickt haben, werden Trigger die <xref:System.Windows.Media.Animation.Storyboard> , beginnt die Animation.</span><span class="sxs-lookup"><span data-stu-id="99646-109">The following example shows how a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which occurs when a <xref:System.Windows.Controls.Button> is clicked, triggers the <xref:System.Windows.Media.Animation.Storyboard> that starts the animation.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a><span data-ttu-id="99646-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99646-110">See Also</span></span>  
 <xref:System.Windows.UIElement.RenderTransform%2A>  
 <xref:System.Windows.Controls.Primitives.BulletDecorator>  
 <xref:System.Windows.Media.RotateTransform>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [<span data-ttu-id="99646-111">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="99646-111">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)  
 [<span data-ttu-id="99646-112">Übersicht über Popups</span><span class="sxs-lookup"><span data-stu-id="99646-112">Popup Overview</span></span>](../../../../docs/framework/wpf/controls/popup-overview.md)
