---
title: 'Vorgehensweise: Steuern eines Storyboards nach dem Start'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: de30cfdb49df721cb4d6845dc67464e8a5b61f93
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855862"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="e2b5b-102">Vorgehensweise: Steuern eines Storyboards nach dem Start</span><span class="sxs-lookup"><span data-stu-id="e2b5b-102">How to: Control a Storyboard After It Starts</span></span>

<span data-ttu-id="e2b5b-103">Dieses Beispiel zeigt, wie Sie mithilfe von Code eine <xref:System.Windows.Media.Animation.Storyboard> steuern können, nachdem Sie gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="e2b5b-103">This example shows how to use code to control a <xref:System.Windows.Media.Animation.Storyboard> after it has started.</span></span> <span data-ttu-id="e2b5b-104">Um ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]Storyboard in zu steuern, verwenden <xref:System.Windows.TriggerAction> <xref:System.Windows.Trigger> Sie die-und-Objekte. ein Beispiel finden Sie unter Verwenden von [Ereignis Triggern zum Steuern eines Storyboards nach dessen Start](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="e2b5b-104">To control a storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Trigger> and <xref:System.Windows.TriggerAction> objects; for an example, see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>

<span data-ttu-id="e2b5b-105">Zum Starten eines Storyboards verwenden <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Sie die zugehörige-Methode, die die Animationen des Storyboards an die Eigenschaften verteilt, die Sie animieren, und das Storyboard startet.</span><span class="sxs-lookup"><span data-stu-id="e2b5b-105">To start a storyboard, you use its <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method, which distributes the storyboard's animations to the properties they animate and starts the storyboard.</span></span>

<span data-ttu-id="e2b5b-106">Wenn Sie ein Storyboard steuerbar machen möchten, <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> verwenden Sie die-Methode, und geben Sie **true** als zweiten Parameter an.</span><span class="sxs-lookup"><span data-stu-id="e2b5b-106">To make a storyboard controllable, you use the <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method and specify **true** as the second parameter.</span></span> <span data-ttu-id="e2b5b-107">Anschließend können Sie die interaktiven Methoden des Storyboards verwenden, um das Storyboard anzuhalten, fortzusetzen, zu suchen, zu stoppen, zu beschleunigen oder zu verlangsamen, oder um das Storyboard in seine Füllzeit zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="e2b5b-107">You can then use the storyboard's interactive methods to pause, resume, seek, stop, speed up, or slow down the storyboard, or advance it to its fill period.</span></span> <span data-ttu-id="e2b5b-108">Im folgenden finden Sie eine Liste der interaktiven Methoden des Storyboards:</span><span class="sxs-lookup"><span data-stu-id="e2b5b-108">The following is a list of the storyboard's interactive methods:</span></span>

- <span data-ttu-id="e2b5b-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Hält das Storyboard an.</span><span class="sxs-lookup"><span data-stu-id="e2b5b-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Pauses the storyboard.</span></span>

- <span data-ttu-id="e2b5b-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Setzt ein angehaltene Storyboard fort.</span><span class="sxs-lookup"><span data-stu-id="e2b5b-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Resumes a paused storyboard.</span></span>

- <span data-ttu-id="e2b5b-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Legt die interaktive Geschwindigkeit des Storyboards fest.</span><span class="sxs-lookup"><span data-stu-id="e2b5b-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Sets the storyboard's interactive speed.</span></span>

- <span data-ttu-id="e2b5b-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Sucht das Storyboard an der angegebenen Position.</span><span class="sxs-lookup"><span data-stu-id="e2b5b-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Seeks the storyboard the specified location.</span></span>

- <span data-ttu-id="e2b5b-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Sucht das Storyboard an der angegebenen Position.</span><span class="sxs-lookup"><span data-stu-id="e2b5b-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Seeks the storyboard to the specified location.</span></span> <span data-ttu-id="e2b5b-114">Anders als <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> bei der-Methode wird dieser Vorgang vor dem nächsten Tick verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="e2b5b-114">Unlike the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method, this operation is processed before the next tick.</span></span>

- <span data-ttu-id="e2b5b-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Verschiebt das Storyboard in seine Füllzeit, wenn es eine hat.</span><span class="sxs-lookup"><span data-stu-id="e2b5b-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Advances the storyboard to its fill period, if it has one.</span></span>

- <span data-ttu-id="e2b5b-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Beendet das Storyboard.</span><span class="sxs-lookup"><span data-stu-id="e2b5b-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Stops the storyboard.</span></span>

<span data-ttu-id="e2b5b-117">Im folgenden Beispiel werden mehrere Storyboard-Methoden verwendet, um ein Storyboard interaktiv zu steuern.</span><span class="sxs-lookup"><span data-stu-id="e2b5b-117">In the following example, several storyboard methods are used to interactively control a storyboard.</span></span>

> [!NOTE]
> <span data-ttu-id="e2b5b-118">Ein Beispiel für die Steuerung eines Storyboards mithilfe von Triggern [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]mit finden [Sie unter Verwenden von Ereignis Triggern zum Steuern eines Storyboards, nachdem es gestartet](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)wurde.</span><span class="sxs-lookup"><span data-stu-id="e2b5b-118">To see an example of controlling a storyboard using triggers with [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>

## <a name="example"></a><span data-ttu-id="e2b5b-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e2b5b-119">Example</span></span>

[!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
[!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]

## <a name="see-also"></a><span data-ttu-id="e2b5b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2b5b-120">See also</span></span>

- [<span data-ttu-id="e2b5b-121">Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start</span><span class="sxs-lookup"><span data-stu-id="e2b5b-121">Use Event Triggers to Control a Storyboard After It Starts</span></span>](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
