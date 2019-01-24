---
title: 'Vorgehensweise: Interaktives Steuern einer Uhr'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 93c2d754ec899c96a50fef3dcef680434f564276
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657544"
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="027b1-102">Vorgehensweise: Interaktives Steuern einer Uhr</span><span class="sxs-lookup"><span data-stu-id="027b1-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="027b1-103">Ein <xref:System.Windows.Media.Animation.Clock> des Objekts <xref:System.Windows.Media.Animation.ClockController> Eigenschaft können Sie interaktiv starten, anhalten, fortsetzen, suchen, fahren fort, um die Uhr um seines Füllbereichs, und Beenden der Uhr.</span><span class="sxs-lookup"><span data-stu-id="027b1-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="027b1-104">Nur die Stammuhr einer Zeitstruktur kann interaktiv gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="027b1-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="027b1-105">Es gibt andere Möglichkeiten, interaktiv Kontrolle-Animationen, die Sie direkt mit Uhren arbeiten benötigen nicht: Sie können auch die Storyboards.</span><span class="sxs-lookup"><span data-stu-id="027b1-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="027b1-106">Storyboards werden in Markup und Code unterstützt.</span><span class="sxs-lookup"><span data-stu-id="027b1-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="027b1-107">Ein Beispiel finden Sie unter [Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) oder [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="027b1-107">For an example, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span>  
  
 <span data-ttu-id="027b1-108">Im folgenden Beispiel werden mehrere Schaltflächen zum eine Animationsuhr interaktiv steuern.</span><span class="sxs-lookup"><span data-stu-id="027b1-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="027b1-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="027b1-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="027b1-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="027b1-110">See also</span></span>
- [<span data-ttu-id="027b1-111">Animieren einer Eigenschaft unter Verwendung eines Storyboards</span><span class="sxs-lookup"><span data-stu-id="027b1-111">Animate a Property by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="027b1-112">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="027b1-112">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
