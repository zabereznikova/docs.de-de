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
ms.openlocfilehash: 2d18f395974750a6b85458f636a27f6101e7978f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951337"
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="b9a74-102">Vorgehensweise: Interaktives Steuern einer Uhr</span><span class="sxs-lookup"><span data-stu-id="b9a74-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="b9a74-103">Mit <xref:System.Windows.Media.Animation.Clock> der- <xref:System.Windows.Media.Animation.ClockController> Eigenschaft eines-Objekts können Sie die Uhr interaktiv starten, anhalten, fortsetzen, suchen, die Uhr bis zum Füllzeitraum verschieben und die Uhr anhalten.</span><span class="sxs-lookup"><span data-stu-id="b9a74-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="b9a74-104">Nur die Stammuhr einer Zeit Steuerungsstruktur kann interaktiv gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="b9a74-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b9a74-105">Es gibt weitere Möglichkeiten, Animationen interaktiv zu steuern, die nicht direkt mit Uhren arbeiten müssen: Sie können auch Storyboards verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9a74-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="b9a74-106">Storyboards werden sowohl in Markup als auch im Code unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b9a74-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="b9a74-107">Ein Beispiel finden Sie unter [Animieren einer Eigenschaft mithilfe eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md) oder der [Übersicht über Animationen](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b9a74-107">For an example, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="b9a74-108">Im folgenden Beispiel werden mehrere Schaltflächen verwendet, um eine Animations Uhr interaktiv zu steuern.</span><span class="sxs-lookup"><span data-stu-id="b9a74-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9a74-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9a74-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="b9a74-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9a74-110">See also</span></span>

- [<span data-ttu-id="b9a74-111">Animieren einer Eigenschaft unter Verwendung eines Storyboards</span><span class="sxs-lookup"><span data-stu-id="b9a74-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="b9a74-112">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="b9a74-112">Animation Overview</span></span>](animation-overview.md)
