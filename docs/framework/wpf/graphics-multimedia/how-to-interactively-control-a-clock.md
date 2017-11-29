---
title: 'Gewusst wie: Interaktives Steuern einer Uhr'
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
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: debe65ef1587171dc2f324a19da4b43e7274c438
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="1ef24-102">Gewusst wie: Interaktives Steuern einer Uhr</span><span class="sxs-lookup"><span data-stu-id="1ef24-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="1ef24-103">Ein <xref:System.Windows.Media.Animation.Clock> des Objekts <xref:System.Windows.Media.Animation.ClockController> Eigenschaft können Sie interaktiv starten, anhalten, fortsetzen, seek, setzen die Uhr auf den Füllzeitraum, und beenden die Uhr.</span><span class="sxs-lookup"><span data-stu-id="1ef24-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="1ef24-104">Nur die Stammuhr einer Zeitstruktur kann interaktiv gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="1ef24-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ef24-105">Es gibt andere Möglichkeiten, interaktiv Steuerelement-Animationen, die Sie direkt mit Uhren arbeiten erfordern: Sie können auch die Storyboards.</span><span class="sxs-lookup"><span data-stu-id="1ef24-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="1ef24-106">Storyboards sind im Markup und Code unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1ef24-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="1ef24-107">Ein Beispiel finden Sie unter [Animieren einer Eigenschaft eines Drehbuchs mit](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) oder [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1ef24-107">For an example, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span>  
  
 <span data-ttu-id="1ef24-108">Im folgenden Beispiel werden mehrere Schaltflächen zum eine Animationsuhr interaktiv steuern.</span><span class="sxs-lookup"><span data-stu-id="1ef24-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ef24-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ef24-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="1ef24-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ef24-110">See Also</span></span>  
 [<span data-ttu-id="1ef24-111">Animieren einer Eigenschaft unter Verwendung eines Storyboards</span><span class="sxs-lookup"><span data-stu-id="1ef24-111">Animate a Property by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [<span data-ttu-id="1ef24-112">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="1ef24-112">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
