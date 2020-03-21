---
title: 'Gewusst wie: Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 518f5d7ea0b5dc00677489f1383814563c565145
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186700"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="89f6f-102">Gewusst wie: Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start</span><span class="sxs-lookup"><span data-stu-id="89f6f-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>

<span data-ttu-id="89f6f-103">Dieses Beispiel zeigt, <xref:System.Windows.Media.Animation.Storyboard> wie sie nach dem Start eines steuert.</span><span class="sxs-lookup"><span data-stu-id="89f6f-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="89f6f-104">Um eine <xref:System.Windows.Media.Animation.Storyboard> mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]zu <xref:System.Windows.Media.Animation.BeginStoryboard>starten, verwenden Sie , die die Animationen an die Objekte und Eigenschaften verteilt, die sie animieren, und starten Sie dann das Storyboard.</span><span class="sxs-lookup"><span data-stu-id="89f6f-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="89f6f-105">Wenn Sie <xref:System.Windows.Media.Animation.BeginStoryboard> einen Namen angeben, indem Sie dessen <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> Eigenschaft angeben, machen Sie ihn zu einem kontrollierbaren Storyboard.</span><span class="sxs-lookup"><span data-stu-id="89f6f-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="89f6f-106">Sie können dann das Storyboard interaktiv steuern, nachdem es gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="89f6f-106">You can then interactively control the storyboard after it starts.</span></span>

<span data-ttu-id="89f6f-107">Verwenden Sie die folgenden <xref:System.Windows.EventTrigger> Storyboard-Aktionen zusammen mit Objekten, um ein Storyboard zu steuern.</span><span class="sxs-lookup"><span data-stu-id="89f6f-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>

- <span data-ttu-id="89f6f-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Hält das Storyboard an.</span><span class="sxs-lookup"><span data-stu-id="89f6f-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>

- <span data-ttu-id="89f6f-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Setzt ein angehaltenes Storyboard fort.</span><span class="sxs-lookup"><span data-stu-id="89f6f-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>

- <span data-ttu-id="89f6f-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Ändert die Storyboard-Geschwindigkeit.</span><span class="sxs-lookup"><span data-stu-id="89f6f-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>

- <span data-ttu-id="89f6f-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Verschiebt ein Storyboard bis zum Ende seiner Füllperiode, wenn es eins hat.</span><span class="sxs-lookup"><span data-stu-id="89f6f-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>

- <span data-ttu-id="89f6f-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stoppt das Storyboard.</span><span class="sxs-lookup"><span data-stu-id="89f6f-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>

- <span data-ttu-id="89f6f-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Entfernt das Storyboard und gibt Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="89f6f-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>

## <a name="example"></a><span data-ttu-id="89f6f-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89f6f-114">Example</span></span>

<span data-ttu-id="89f6f-115">Im folgenden Beispiel werden steuerbare Storyboardaktionen verwendet, um ein Storyboard interaktiv zu steuern.</span><span class="sxs-lookup"><span data-stu-id="89f6f-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>

> [!NOTE]
> <span data-ttu-id="89f6f-116">Ein Beispiel für die Steuerung eines Storyboards mithilfe von Code finden Sie unter [Steuern eines Storyboards, nachdem es mit seinen interaktiven Methoden beginnt.](how-to-control-a-storyboard-after-it-starts.md)</span><span class="sxs-lookup"><span data-stu-id="89f6f-116">To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](how-to-control-a-storyboard-after-it-starts.md).</span></span>

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

<span data-ttu-id="89f6f-117">Weitere Beispiele finden Sie in der [Animationsbeispielgalerie](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span><span class="sxs-lookup"><span data-stu-id="89f6f-117">For additional examples, see the [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>

## <a name="see-also"></a><span data-ttu-id="89f6f-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89f6f-118">See also</span></span>

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [<span data-ttu-id="89f6f-119">Interaktives Steuern eines Storyboards, nachdem es gestartet wurde</span><span class="sxs-lookup"><span data-stu-id="89f6f-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](how-to-control-a-storyboard-after-it-starts.md)
- [<span data-ttu-id="89f6f-120">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="89f6f-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="89f6f-121">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="89f6f-121">Storyboards Overview</span></span>](storyboards-overview.md)
