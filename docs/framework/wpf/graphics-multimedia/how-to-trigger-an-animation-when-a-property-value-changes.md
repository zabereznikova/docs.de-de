---
title: 'Vorgehensweise: Auslösen einer Animation, wenn sich eine Eigenschaft ändert'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: 7e3eecedf7d464eeb8e4f60f2f05fa06d2e23e09
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769303"
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a><span data-ttu-id="d999c-102">Vorgehensweise: Auslösen einer Animation, wenn sich eine Eigenschaft ändert</span><span class="sxs-lookup"><span data-stu-id="d999c-102">How to: Trigger an Animation When a Property Value Changes</span></span>
<span data-ttu-id="d999c-103">Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Trigger> zu einem <xref:System.Windows.Media.Animation.Storyboard> bei Änderung eines Eigenschaftswerts.</span><span class="sxs-lookup"><span data-stu-id="d999c-103">This example shows how to use a <xref:System.Windows.Trigger> to start a <xref:System.Windows.Media.Animation.Storyboard> when a property value changes.</span></span> <span data-ttu-id="d999c-104">Sie können eine <xref:System.Windows.Trigger> innerhalb einer <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, oder <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="d999c-104">You can use a <xref:System.Windows.Trigger> inside a <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, or <xref:System.Windows.DataTemplate>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d999c-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d999c-105">Example</span></span>  
 <span data-ttu-id="d999c-106">Im folgenden Beispiel wird eine <xref:System.Windows.Trigger> zum Animieren der <xref:System.Windows.UIElement.Opacity%2A> von einer <xref:System.Windows.Controls.Button> beim seine <xref:System.Windows.UIElement.IsMouseOver%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="d999c-106">The following example uses a <xref:System.Windows.Trigger> to animate the <xref:System.Windows.UIElement.Opacity%2A> of a <xref:System.Windows.Controls.Button> when its <xref:System.Windows.UIElement.IsMouseOver%2A> property becomes `true`.</span></span>  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 <span data-ttu-id="d999c-107">Eigenschaft angewendete Animationen <xref:System.Windows.Trigger> Objekte verhalten sich komplexer als <xref:System.Windows.EventTrigger> Animationen oder Animationen Einstieg <xref:System.Windows.Media.Animation.Storyboard> Methoden.</span><span class="sxs-lookup"><span data-stu-id="d999c-107">Animations applied by property <xref:System.Windows.Trigger> objects behave in a more complex fashion than <xref:System.Windows.EventTrigger> animations or animations started using <xref:System.Windows.Media.Animation.Storyboard> methods.</span></span>  <span data-ttu-id="d999c-108">Sie "übergeben" mit Animationen definiert, die von anderen <xref:System.Windows.Trigger> Objekte, aber verfassen mit <xref:System.Windows.EventTrigger> und Methoden ausgelösten Animationen.</span><span class="sxs-lookup"><span data-stu-id="d999c-108">They "handoff" with animations defined by other <xref:System.Windows.Trigger> objects, but compose with <xref:System.Windows.EventTrigger> and method-triggered animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d999c-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d999c-109">See also</span></span>

- <xref:System.Windows.Trigger>
- [<span data-ttu-id="d999c-110">Übersicht über die Verfahren zur Animation von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d999c-110">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
- [<span data-ttu-id="d999c-111">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="d999c-111">Storyboards Overview</span></span>](storyboards-overview.md)
