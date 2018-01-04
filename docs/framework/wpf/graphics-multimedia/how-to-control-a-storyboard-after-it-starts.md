---
title: 'Gewusst wie: Steuern eines Storyboards nach dem Start'
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
helpviewer_keywords: Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 051ac6fea73b207fb5ef4d6293c5e996552f1281
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="b8944-102">Gewusst wie: Steuern eines Storyboards nach dem Start</span><span class="sxs-lookup"><span data-stu-id="b8944-102">How to: Control a Storyboard After It Starts</span></span>
<span data-ttu-id="b8944-103">Dieses Beispiel zeigt, wie Code, um zu steuern verwendet eine <xref:System.Windows.Media.Animation.Storyboard> nachdem dieser gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="b8944-103">This example shows how to use code to control a <xref:System.Windows.Media.Animation.Storyboard> after it has started.</span></span> <span data-ttu-id="b8944-104">Zum Steuern eines Storyboards in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], verwenden Sie <xref:System.Windows.Trigger> und <xref:System.Windows.TriggerAction> Objekte ist ein Beispiel finden Sie unter [Ereignistriggern verwenden, um ein Storyboard nach Beginn steuern](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="b8944-104">To control a storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Trigger> and <xref:System.Windows.TriggerAction> objects; for an example, see [Use Event Triggers to Control a Storyboard After It Starts](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 <span data-ttu-id="b8944-105">Um ein Storyboard zu starten, verwenden Sie die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> -Methode, die das Storyboard-Animationen, um die Eigenschaften animierenden verteilt werden und das Storyboard gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="b8944-105">To start a storyboard, you use its <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method, which distributes the storyboard's animations to the properties they animate and starts the storyboard.</span></span>  
  
 <span data-ttu-id="b8944-106">Um ein Storyboard steuerbar festzulegen, verwenden Sie die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode, und geben Sie **"true"** als zweiten Parameter.</span><span class="sxs-lookup"><span data-stu-id="b8944-106">To make a storyboard controllable, you use the <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method and specify **true** as the second parameter.</span></span> <span data-ttu-id="b8944-107">Anschließend können Sie das Storyboard interaktiv Methoden anhalten, fortsetzen, seek, beenden, beschleunigen oder verlangsamen Sie das Storyboard oder auf den Füllzeitraum zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="b8944-107">You can then use the storyboard's interactive methods to pause, resume, seek, stop, speed up, or slow down the storyboard, or advance it to its fill period.</span></span> <span data-ttu-id="b8944-108">Im folgenden finden eine Liste der interaktiven das Storyboard-Methoden:</span><span class="sxs-lookup"><span data-stu-id="b8944-108">The following is a list of the storyboard's interactive methods:</span></span>  
  
-   <span data-ttu-id="b8944-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Hält das Storyboard.</span><span class="sxs-lookup"><span data-stu-id="b8944-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Pauses the storyboard.</span></span>  
  
-   <span data-ttu-id="b8944-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Nimmt eine angehaltene Storyboards.</span><span class="sxs-lookup"><span data-stu-id="b8944-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Resumes a paused storyboard.</span></span>  
  
-   <span data-ttu-id="b8944-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Legt fest, interaktive Geschwindigkeit des Storyboards.</span><span class="sxs-lookup"><span data-stu-id="b8944-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Sets the storyboard's interactive speed.</span></span>  
  
-   <span data-ttu-id="b8944-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Sucht die Storyboards am angegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="b8944-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Seeks the storyboard the specified location.</span></span>  
  
-   <span data-ttu-id="b8944-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Sucht die Storyboards am angegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="b8944-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Seeks the storyboard to the specified location.</span></span> <span data-ttu-id="b8944-114">Im Gegensatz zu den <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> -Methode, diesen Vorgang vor dem nächsten Teilstrich verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="b8944-114">Unlike the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method, this operation is processed before the next tick.</span></span>  
  
-   <span data-ttu-id="b8944-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Setzt das Storyboard mit den Füllzeitraum, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b8944-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Advances the storyboard to its fill period, if it has one.</span></span>  
  
-   <span data-ttu-id="b8944-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Das Storyboard beendet.</span><span class="sxs-lookup"><span data-stu-id="b8944-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Stops the storyboard.</span></span>  
  
 <span data-ttu-id="b8944-117">Im folgenden Beispiel werden verschiedene Storyboard-Methoden verwendet, um ein Storyboard interaktiv zu steuern.</span><span class="sxs-lookup"><span data-stu-id="b8944-117">In the following example, several storyboard methods are used to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="b8944-118">**Hinweis:** sehen Sie ein Beispiel zum Steuern eines Storyboards mithilfe von Triggern mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], finden Sie unter [Ereignistriggern verwenden, um ein Storyboard nach dem Start zu steuern](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="b8944-118">**Note:** To see an example of controlling a storyboard using triggers with [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Use Event Triggers to Control a Storyboard After It Starts](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8944-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8944-119">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b8944-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8944-120">See Also</span></span>  
 [<span data-ttu-id="b8944-121">Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start</span><span class="sxs-lookup"><span data-stu-id="b8944-121">Use Event Triggers to Control a Storyboard After It Starts</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
