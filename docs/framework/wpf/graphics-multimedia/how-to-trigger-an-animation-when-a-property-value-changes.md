---
title: "Gewusst wie: Auslösen einer Animation bei Änderung eines Eigenschaftswerts"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0eb4542d8baf86f01417eb1925028a00471b40b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a><span data-ttu-id="0e2ba-102">Gewusst wie: Auslösen einer Animation bei Änderung eines Eigenschaftswerts</span><span class="sxs-lookup"><span data-stu-id="0e2ba-102">How to: Trigger an Animation When a Property Value Changes</span></span>
<span data-ttu-id="0e2ba-103">Dieses Beispiel zeigt, wie eine <xref:System.Windows.Trigger> zum Starten einer <xref:System.Windows.Media.Animation.Storyboard> Wenn sich ein Eigenschaftswert ändert.</span><span class="sxs-lookup"><span data-stu-id="0e2ba-103">This example shows how to use a <xref:System.Windows.Trigger> to start a <xref:System.Windows.Media.Animation.Storyboard> when a property value changes.</span></span> <span data-ttu-id="0e2ba-104">Sie können eine <xref:System.Windows.Trigger> innerhalb einer <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, oder <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="0e2ba-104">You can use a <xref:System.Windows.Trigger> inside a <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, or <xref:System.Windows.DataTemplate>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e2ba-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e2ba-105">Example</span></span>  
 <span data-ttu-id="0e2ba-106">Im folgenden Beispiel wird eine <xref:System.Windows.Trigger> zum Animieren der <xref:System.Windows.UIElement.Opacity%2A> des eine <xref:System.Windows.Controls.Button> beim seine <xref:System.Windows.UIElement.IsMouseOver%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="0e2ba-106">The following example uses a <xref:System.Windows.Trigger> to animate the <xref:System.Windows.UIElement.Opacity%2A> of a <xref:System.Windows.Controls.Button> when its <xref:System.Windows.UIElement.IsMouseOver%2A> property becomes `true`.</span></span>  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 <span data-ttu-id="0e2ba-107">Animationen, die von der Eigenschaft angewendet <xref:System.Windows.Trigger> Objekte verhalten sich in einer komplexeren Weise als <xref:System.Windows.EventTrigger> Animationen oder Animationen Schritte mit <xref:System.Windows.Media.Animation.Storyboard> Methoden.</span><span class="sxs-lookup"><span data-stu-id="0e2ba-107">Animations applied by property <xref:System.Windows.Trigger> objects behave in a more complex fashion than <xref:System.Windows.EventTrigger> animations or animations started using <xref:System.Windows.Media.Animation.Storyboard> methods.</span></span>  <span data-ttu-id="0e2ba-108">Diese "Übergabe" mit Animationen definiert, die von anderen <xref:System.Windows.Trigger> Objekte, bilden jedoch mit <xref:System.Windows.EventTrigger> und Animationen Methode ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0e2ba-108">They "handoff" with animations defined by other <xref:System.Windows.Trigger> objects, but compose with <xref:System.Windows.EventTrigger> and method-triggered animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e2ba-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e2ba-109">See Also</span></span>  
 <xref:System.Windows.Trigger>  
 [<span data-ttu-id="0e2ba-110">Übersicht über die Verfahren zur Animation von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0e2ba-110">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [<span data-ttu-id="0e2ba-111">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="0e2ba-111">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
