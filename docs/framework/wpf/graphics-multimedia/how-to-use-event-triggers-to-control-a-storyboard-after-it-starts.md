---
title: 'Gewusst wie: Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d9e096969713cc4b9c42261b238691d51cb49d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="2acde-102">Gewusst wie: Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start</span><span class="sxs-lookup"><span data-stu-id="2acde-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>
<span data-ttu-id="2acde-103">In diesem Beispiel wird gezeigt, wie zur Steuerung einer <xref:System.Windows.Media.Animation.Storyboard> nach dem Start.</span><span class="sxs-lookup"><span data-stu-id="2acde-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="2acde-104">Starten einer <xref:System.Windows.Media.Animation.Storyboard> mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], verwenden <xref:System.Windows.Media.Animation.BeginStoryboard>, die verteilt der Animationen an die Objekte und Eigenschaften, die sie dem animiert werden soll, und startet dann das Storyboard.</span><span class="sxs-lookup"><span data-stu-id="2acde-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="2acde-105">Wenn verfügt <xref:System.Windows.Media.Animation.BeginStoryboard> einen Namen durch Angabe seiner <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> -Eigenschaft, ist er ein Storyboard steuerbares.</span><span class="sxs-lookup"><span data-stu-id="2acde-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="2acde-106">Sie können dann das Storyboard interaktiv steuern nach dem Start.</span><span class="sxs-lookup"><span data-stu-id="2acde-106">You can then interactively control the storyboard after it starts.</span></span>  
  
 <span data-ttu-id="2acde-107">Verwenden Sie die folgenden Storyboardaktionen zusammen mit <xref:System.Windows.EventTrigger> Objekte zum Steuern eines Storyboards.</span><span class="sxs-lookup"><span data-stu-id="2acde-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>  
  
-   <span data-ttu-id="2acde-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Hält das Storyboard.</span><span class="sxs-lookup"><span data-stu-id="2acde-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>  
  
-   <span data-ttu-id="2acde-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Nimmt eine angehaltene Storyboards.</span><span class="sxs-lookup"><span data-stu-id="2acde-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>  
  
-   <span data-ttu-id="2acde-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Ändert die Geschwindigkeit des Storyboards.</span><span class="sxs-lookup"><span data-stu-id="2acde-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>  
  
-   <span data-ttu-id="2acde-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Setzt ein Storyboard bis zum Ende des Füllzeitraums, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2acde-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>  
  
-   <span data-ttu-id="2acde-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Das Storyboard beendet.</span><span class="sxs-lookup"><span data-stu-id="2acde-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>  
  
-   <span data-ttu-id="2acde-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Entfernt das Storyboard und Verfügbarmachen von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="2acde-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2acde-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2acde-114">Example</span></span>  
 <span data-ttu-id="2acde-115">Im folgenden Beispiel wird steuerbare Storyboard-Aktionen, um ein Storyboard interaktiv zu steuern.</span><span class="sxs-lookup"><span data-stu-id="2acde-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="2acde-116">**Hinweis:** ein Beispiel zum Steuern eines Storyboards mithilfe von Code finden Sie unter [ein Storyboard nach er startet mithilfe seiner interaktiven Methoden steuern](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="2acde-116">**Note:** To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 <span data-ttu-id="2acde-117">Weitere Beispiele finden Sie unter der [Beispielsammlung](http://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="2acde-117">For additional examples, see the [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2acde-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2acde-118">See Also</span></span>  
 <xref:System.Windows.Media.Animation.ResumeStoryboard>  
 <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>  
 <xref:System.Windows.Media.Animation.SkipStoryboardToFill>  
 <xref:System.Windows.Media.Animation.PauseStoryboard>  
 <xref:System.Windows.Media.Animation.StopStoryboard>  
 <xref:System.Windows.Media.Animation.SeekStoryboard>  
 [<span data-ttu-id="2acde-119">Interaktives Steuern eines Storyboards, nachdem es gestartet wurde</span><span class="sxs-lookup"><span data-stu-id="2acde-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)  
 [<span data-ttu-id="2acde-120">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="2acde-120">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="2acde-121">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="2acde-121">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
