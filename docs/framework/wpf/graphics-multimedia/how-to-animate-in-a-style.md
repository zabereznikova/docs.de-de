---
title: 'Gewusst wie: Animieren in einem Stil'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 10cd243c633e7a7e458d2026fc5e3d91d2996427
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-animate-in-a-style"></a><span data-ttu-id="244e9-102">Gewusst wie: Animieren in einem Stil</span><span class="sxs-lookup"><span data-stu-id="244e9-102">How to: Animate in a Style</span></span>
<span data-ttu-id="244e9-103">In diesem Beispiel wird gezeigt, wie zum Animieren von Eigenschaften in einem Format festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="244e9-103">This example shows how to animate properties within a style.</span></span> <span data-ttu-id="244e9-104">Wenn Sie innerhalb eines Stils animieren, kann nur die Framework-Element, das für das die Formatvorlage definiert wird direkt angesprochen werden.</span><span class="sxs-lookup"><span data-stu-id="244e9-104">When animating within a style, only the framework element for which the style is defined can be targeted directly.</span></span> <span data-ttu-id="244e9-105">Um ein freezable-Objekt als Ziel festzulegen, müssen Sie "nach unten aus einer Eigenschaft des formatierten Elements dot".</span><span class="sxs-lookup"><span data-stu-id="244e9-105">To target a freezable object, you must "dot down" from a property of the styled element.</span></span>  
  
 <span data-ttu-id="244e9-106">Im folgenden Beispiel werden mehrere Animationen in einem Stil definiert und angewendet eine <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="244e9-106">In the following example, several animations are defined within a style and applied to a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="244e9-107">Wenn der Benutzer die Maus auf die Schaltfläche richtet, es ausgeblendet wird von nicht transparenten, teilweise transparent und zurück wiederholt.</span><span class="sxs-lookup"><span data-stu-id="244e9-107">When the user moves the mouse over the button, it fades from opaque to partially translucent and back again, repeatedly.</span></span> <span data-ttu-id="244e9-108">Wenn der Benutzer die Maus deaktiviert die Schaltfläche richtet, wird es vollständig deckend.</span><span class="sxs-lookup"><span data-stu-id="244e9-108">When the user moves the mouse off the button, it becomes completely opaque.</span></span> <span data-ttu-id="244e9-109">Wenn die Schaltfläche geklickt wird, ändert sich die Hintergrundfarbe von Orange in Weiß und wieder zurück.</span><span class="sxs-lookup"><span data-stu-id="244e9-109">When the button is clicked, its background color changes from orange to white and back again.</span></span> <span data-ttu-id="244e9-110">Da die <xref:System.Windows.Media.SolidColorBrush> verwendet, um das Paint-Ereignis der Schaltfläche kann nicht direkt angewendet werden, wird darauf über der Schaltfläche Farbgebung <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="244e9-110">Because the <xref:System.Windows.Media.SolidColorBrush> used to paint the button can't be targeted directly, it is accessed by dotting down from the button's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="244e9-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="244e9-111">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]  
  
 <span data-ttu-id="244e9-112">Beachten Sie, dass wenn Sie innerhalb eines Stils animieren, ist es möglich, Zielobjekte, die nicht vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="244e9-112">Note that when animating within a style, it's possible to target objects that don't exist.</span></span> <span data-ttu-id="244e9-113">Nehmen wir beispielsweise an, die der Stil verwendet eine <xref:System.Windows.Media.SolidColorBrush> auf eine Schaltfläche Hintergrundeigenschaft festgelegt, aber zu einem bestimmten Zeitpunkt den Stil überschrieben werden, und der Hintergrund der Schaltfläche wird festgelegt, mit einem <xref:System.Windows.Media.LinearGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="244e9-113">For example, suppose your style uses a <xref:System.Windows.Media.SolidColorBrush> to set a Button's background property, but at some point the style is overridden and the button's background is set with a <xref:System.Windows.Media.LinearGradientBrush>.</span></span>  <span data-ttu-id="244e9-114">Versucht, die zu animierende den <xref:System.Windows.Media.SolidColorBrush> wird nicht lösen eine Ausnahme aus, die Animation fehl einfach im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="244e9-114">Trying to animate the <xref:System.Windows.Media.SolidColorBrush> won't throw an exception; the animation will simply fail silently.</span></span>  
  
 <span data-ttu-id="244e9-115">Weitere Informationen über Syntax zum finden Sie unter der [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="244e9-115">Fore more information about storyboard targeting syntax, see the [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span> <span data-ttu-id="244e9-116">Weitere Informationen zur Animation finden Sie unter der [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="244e9-116">For more information about animation, see the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="244e9-117">Weitere Informationen zu Stilen finden Sie unter der [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="244e9-117">For more information about styles, see the [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span>
