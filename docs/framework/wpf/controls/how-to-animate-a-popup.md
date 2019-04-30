---
title: 'Vorgehensweise: Animieren eines Popups'
ms.date: 03/30/2017
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
ms.openlocfilehash: b70d9c4cb1bca26a6c77d3a7c50add517ca8ef92
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911286"
---
# <a name="how-to-animate-a-popup"></a><span data-ttu-id="9d33e-102">Vorgehensweise: Animieren eines Popups</span><span class="sxs-lookup"><span data-stu-id="9d33e-102">How to: Animate a Popup</span></span>
<span data-ttu-id="9d33e-103">Dieses Beispiel zeigt zwei Methoden zum Animieren einer <xref:System.Windows.Controls.Primitives.Popup> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="9d33e-103">This example shows two ways to animate a <xref:System.Windows.Controls.Primitives.Popup> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d33e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9d33e-104">Example</span></span>  
 <span data-ttu-id="9d33e-105">Im folgenden Beispiel wird die <xref:System.Windows.Controls.Primitives.PopupAnimation> Eigenschaft mit einem Wert von <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, bewirkt, dass die <xref:System.Windows.Controls.Primitives.Popup> auf "Folie-in" Wenn es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9d33e-105">The following example sets the <xref:System.Windows.Controls.Primitives.PopupAnimation> property to a value of <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, which causes the <xref:System.Windows.Controls.Primitives.Popup> to "slide-in" when it appears.</span></span>  
  
 <span data-ttu-id="9d33e-106">Um eine Rotation zu der <xref:System.Windows.Controls.Primitives.Popup>, in diesem Beispiel wird eine <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft für die <xref:System.Windows.Controls.Canvas>, dies ist das untergeordnete Element des der <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="9d33e-106">In order to rotate the <xref:System.Windows.Controls.Primitives.Popup>, this example assigns a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property on the <xref:System.Windows.Controls.Canvas>, which is the child element of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  
  
 <span data-ttu-id="9d33e-107">Für die Transformation ordnungsgemäß funktioniert, muss die im Beispiel festgelegt die <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="9d33e-107">For the transform to work correctly, the example must set the <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> property to `true`.</span></span> <span data-ttu-id="9d33e-108">Darüber hinaus die <xref:System.Windows.FrameworkElement.Margin%2A> auf die <xref:System.Windows.Controls.Canvas> angeben Inhalts muss genügend Speicherplatz für die <xref:System.Windows.Controls.Primitives.Popup> gedreht.</span><span class="sxs-lookup"><span data-stu-id="9d33e-108">In addition, the <xref:System.Windows.FrameworkElement.Margin%2A> on the <xref:System.Windows.Controls.Canvas> content must specify enough space for the <xref:System.Windows.Controls.Primitives.Popup> to rotate.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 <span data-ttu-id="9d33e-109">Das folgende Beispiel zeigt wie eine <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis, das eintritt, wenn eine <xref:System.Windows.Controls.Button> geklickt wird, werden Trigger die <xref:System.Windows.Media.Animation.Storyboard> , beginnt die Animation.</span><span class="sxs-lookup"><span data-stu-id="9d33e-109">The following example shows how a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which occurs when a <xref:System.Windows.Controls.Button> is clicked, triggers the <xref:System.Windows.Media.Animation.Storyboard> that starts the animation.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a><span data-ttu-id="9d33e-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d33e-110">See also</span></span>

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Controls.Primitives.BulletDecorator>
- <xref:System.Windows.Media.RotateTransform>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="9d33e-111">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="9d33e-111">How-to Topics</span></span>](popup-how-to-topics.md)
- [<span data-ttu-id="9d33e-112">Übersicht über Popups</span><span class="sxs-lookup"><span data-stu-id="9d33e-112">Popup Overview</span></span>](popup-overview.md)
