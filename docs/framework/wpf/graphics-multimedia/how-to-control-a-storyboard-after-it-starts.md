---
title: 'Vorgehensweise: Steuern eines Storyboards, nachdem es gestartet wurde'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: 98eba600f64c8b656e3597b429cc69766f398f7b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361056"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="5d70c-102">Vorgehensweise: Steuern eines Storyboards, nachdem es gestartet wurde</span><span class="sxs-lookup"><span data-stu-id="5d70c-102">How to: Control a Storyboard After It Starts</span></span>
<span data-ttu-id="5d70c-103">Dieses Beispiel zeigt, wie Sie mit Code zum Steuern einer <xref:System.Windows.Media.Animation.Storyboard> nachdem es gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="5d70c-103">This example shows how to use code to control a <xref:System.Windows.Media.Animation.Storyboard> after it has started.</span></span> <span data-ttu-id="5d70c-104">Zum Steuern eines Storyboards in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], verwenden Sie <xref:System.Windows.Trigger> und <xref:System.Windows.TriggerAction> Objekte; ein Beispiel finden Sie unter [Verwenden von Ereignistriggern zum Steuern einer Storyboards nach dessen Start](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="5d70c-104">To control a storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Trigger> and <xref:System.Windows.TriggerAction> objects; for an example, see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 <span data-ttu-id="5d70c-105">Um ein Storyboard zu starten, verwenden Sie die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> -Methode, die die Storyboard Animationen auf die Eigenschaften animierenden verteilt werden und startet das Storyboard.</span><span class="sxs-lookup"><span data-stu-id="5d70c-105">To start a storyboard, you use its <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method, which distributes the storyboard's animations to the properties they animate and starts the storyboard.</span></span>  
  
 <span data-ttu-id="5d70c-106">Um ein Storyboard steuerbar ist, verwenden Sie die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode, und geben Sie **"true"** als zweiten Parameter.</span><span class="sxs-lookup"><span data-stu-id="5d70c-106">To make a storyboard controllable, you use the <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method and specify **true** as the second parameter.</span></span> <span data-ttu-id="5d70c-107">Können Sie dann die Storyboard interaktiven Methoden zum Anhalten, fortsetzen, suchen, beenden, beschleunigen, oder das Storyboard verlangsamen oder können es auf seines Füllbereichs.</span><span class="sxs-lookup"><span data-stu-id="5d70c-107">You can then use the storyboard's interactive methods to pause, resume, seek, stop, speed up, or slow down the storyboard, or advance it to its fill period.</span></span> <span data-ttu-id="5d70c-108">Im folgenden finden eine Liste der Storyboard interaktiven Methoden:</span><span class="sxs-lookup"><span data-stu-id="5d70c-108">The following is a list of the storyboard's interactive methods:</span></span>  
  
-   <span data-ttu-id="5d70c-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Hält das Storyboard an.</span><span class="sxs-lookup"><span data-stu-id="5d70c-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Pauses the storyboard.</span></span>  
  
-   <span data-ttu-id="5d70c-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Setzt ein angehaltenes Storyboard fort.</span><span class="sxs-lookup"><span data-stu-id="5d70c-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Resumes a paused storyboard.</span></span>  
  
-   <span data-ttu-id="5d70c-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Legt die Geschwindigkeit des Storyboards interaktive fest.</span><span class="sxs-lookup"><span data-stu-id="5d70c-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Sets the storyboard's interactive speed.</span></span>  
  
-   <span data-ttu-id="5d70c-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Suchen das Storyboard aus der angegebenen Position ein.</span><span class="sxs-lookup"><span data-stu-id="5d70c-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Seeks the storyboard the specified location.</span></span>  
  
-   <span data-ttu-id="5d70c-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Sucht das Storyboard am angegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="5d70c-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Seeks the storyboard to the specified location.</span></span> <span data-ttu-id="5d70c-114">Im Gegensatz zu den <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> -Methode, diesen Vorgang wird verarbeitet, bevor das nächste Ticken.</span><span class="sxs-lookup"><span data-stu-id="5d70c-114">Unlike the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method, this operation is processed before the next tick.</span></span>  
  
-   <span data-ttu-id="5d70c-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Setzt das Storyboard, um seines Füllbereichs, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="5d70c-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Advances the storyboard to its fill period, if it has one.</span></span>  
  
-   <span data-ttu-id="5d70c-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Hält das Storyboard an.</span><span class="sxs-lookup"><span data-stu-id="5d70c-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Stops the storyboard.</span></span>  
  
 <span data-ttu-id="5d70c-117">Im folgenden Beispiel werden mehrere Storyboard-Methoden zum interaktiven Steuern eines Storyboards.</span><span class="sxs-lookup"><span data-stu-id="5d70c-117">In the following example, several storyboard methods are used to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="5d70c-118">**Hinweis**: Finden Sie ein Beispiel zum Steuern eines Storyboards mithilfe von Triggern mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], finden Sie unter [Verwenden von Ereignistriggern zum Steuern einer Storyboards nach dessen Start](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="5d70c-118">**Note:** To see an example of controlling a storyboard using triggers with [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d70c-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d70c-119">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="5d70c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d70c-120">See also</span></span>
- [<span data-ttu-id="5d70c-121">Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start</span><span class="sxs-lookup"><span data-stu-id="5d70c-121">Use Event Triggers to Control a Storyboard After It Starts</span></span>](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
