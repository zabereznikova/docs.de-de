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
ms.openlocfilehash: 05989b6a03e03fb5723a70c9c36d5e32f9117049
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186588"
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="342d2-102">Vorgehensweise: Interaktives Steuern einer Uhr</span><span class="sxs-lookup"><span data-stu-id="342d2-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="342d2-103">Ein <xref:System.Windows.Media.Animation.Clock> des Objekts <xref:System.Windows.Media.Animation.ClockController> Eigenschaft können Sie interaktiv starten, anhalten, fortsetzen, suchen, fahren fort, um die Uhr um seines Füllbereichs, und Beenden der Uhr.</span><span class="sxs-lookup"><span data-stu-id="342d2-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="342d2-104">Nur die Stammuhr einer Zeitstruktur kann interaktiv gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="342d2-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="342d2-105">Es gibt andere Möglichkeiten, interaktiv Kontrolle-Animationen, die Sie direkt mit Uhren arbeiten benötigen nicht: Sie können auch die Storyboards.</span><span class="sxs-lookup"><span data-stu-id="342d2-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="342d2-106">Storyboards werden in Markup und Code unterstützt.</span><span class="sxs-lookup"><span data-stu-id="342d2-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="342d2-107">Ein Beispiel finden Sie unter [Animieren einer Eigenschaft unter Verwendung eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md) oder [Übersicht über Animationen](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="342d2-107">For an example, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="342d2-108">Im folgenden Beispiel werden mehrere Schaltflächen zum eine Animationsuhr interaktiv steuern.</span><span class="sxs-lookup"><span data-stu-id="342d2-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="342d2-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="342d2-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="342d2-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="342d2-110">See also</span></span>

- [<span data-ttu-id="342d2-111">Animieren einer Eigenschaft unter Verwendung eines Storyboards</span><span class="sxs-lookup"><span data-stu-id="342d2-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="342d2-112">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="342d2-112">Animation Overview</span></span>](animation-overview.md)
