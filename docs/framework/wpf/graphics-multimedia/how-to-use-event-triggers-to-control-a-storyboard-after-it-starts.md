---
title: 'Vorgehensweise: Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: d444349f8bc9236e1d15f484f35b1326c77e2425
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170650"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="6ef1d-102">Vorgehensweise: Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start</span><span class="sxs-lookup"><span data-stu-id="6ef1d-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>
<span data-ttu-id="6ef1d-103">Dieses Beispiel zeigt, wie Sie steuern eine <xref:System.Windows.Media.Animation.Storyboard> nachdem es gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="6ef1d-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="6ef1d-104">Starten einer <xref:System.Windows.Media.Animation.Storyboard> mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], verwenden Sie <xref:System.Windows.Media.Animation.BeginStoryboard>, das verteilt der Animationen an die Objekte und Eigenschaften, die sie animieren, und klicken Sie dann das Storyboard gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="6ef1d-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="6ef1d-105">Wenn Sie geben <xref:System.Windows.Media.Animation.BeginStoryboard> einen Namen durch Angabe der <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> -Eigenschaft, Sie machen es ein steuerbares Storyboard.</span><span class="sxs-lookup"><span data-stu-id="6ef1d-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="6ef1d-106">Sie können das Storyboard dann interaktiv steuern, nachdem es gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="6ef1d-106">You can then interactively control the storyboard after it starts.</span></span>  
  
 <span data-ttu-id="6ef1d-107">Verwenden Sie die folgenden Storyboard Aktionen zusammen mit <xref:System.Windows.EventTrigger> Objekte zum Steuern eines Storyboards.</span><span class="sxs-lookup"><span data-stu-id="6ef1d-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard><span data-ttu-id="6ef1d-108">: Hält das Storyboard an.</span><span class="sxs-lookup"><span data-stu-id="6ef1d-108">: Pauses the storyboard.</span></span>  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard><span data-ttu-id="6ef1d-109">: Setzt ein angehaltenes Storyboard fort.</span><span class="sxs-lookup"><span data-stu-id="6ef1d-109">: Resumes a paused storyboard.</span></span>  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio><span data-ttu-id="6ef1d-110">: Ändert die Geschwindigkeit des Storyboards.</span><span class="sxs-lookup"><span data-stu-id="6ef1d-110">: Changes the storyboard speed.</span></span>  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill><span data-ttu-id="6ef1d-111">: Setzt ein Storyboard an das Ende seines Füllbereichs, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="6ef1d-111">: Advances a storyboard to the end of its fill period, if it has one.</span></span>  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard><span data-ttu-id="6ef1d-112">: Hält das Storyboard an.</span><span class="sxs-lookup"><span data-stu-id="6ef1d-112">: Stops the storyboard.</span></span>  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard><span data-ttu-id="6ef1d-113">: Entfernt das Storyboard, das Freigeben von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="6ef1d-113">: Removes the storyboard, freeing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ef1d-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6ef1d-114">Example</span></span>  
 <span data-ttu-id="6ef1d-115">Im folgenden Beispiel wird die Aktionen des steuerbaren Storyboards zum interaktiven Steuern eines Storyboards.</span><span class="sxs-lookup"><span data-stu-id="6ef1d-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="6ef1d-116">**Hinweis**: Ein Beispiel zum Steuern eines Storyboards mithilfe von Code finden Sie unter [steuern Sie ein Storyboard nach es beginnt mithilfe von einem interaktiven Methoden](how-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="6ef1d-116">**Note:** To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](how-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 <span data-ttu-id="6ef1d-117">Weitere Beispiele finden Sie unter den [Beispielsammlung](https://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="6ef1d-117">For additional examples, see the [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef1d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ef1d-118">See also</span></span>

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [<span data-ttu-id="6ef1d-119">Interaktives Steuern eines Storyboards, nachdem es gestartet wurde</span><span class="sxs-lookup"><span data-stu-id="6ef1d-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](how-to-control-a-storyboard-after-it-starts.md)
- [<span data-ttu-id="6ef1d-120">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="6ef1d-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="6ef1d-121">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="6ef1d-121">Storyboards Overview</span></span>](storyboards-overview.md)
