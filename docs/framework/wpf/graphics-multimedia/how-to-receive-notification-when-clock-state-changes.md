---
title: "Vorgehensweise: Benachrichtigung bei einer Uhr &#39; s Statusänderungen"
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
- clocks [WPF], notification of state changes
- notifications [WPF], clocks' state changes
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f59fddb1add29d52ccba6fc8b8ce84938b53a1c2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-receive-notification-when-a-clock39s-state-changes"></a><span data-ttu-id="c16d9-102">Vorgehensweise: Benachrichtigung bei einer Uhr &#39; s Statusänderungen</span><span class="sxs-lookup"><span data-stu-id="c16d9-102">How to: Receive Notification When a Clock&#39;s State Changes</span></span>
<span data-ttu-id="c16d9-103">Einer Uhr <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> Ereignis tritt auf, wenn seine <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> ungültig, z. B. wenn die Uhr startet oder beendet wird.</span><span class="sxs-lookup"><span data-stu-id="c16d9-103">A clock's <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> event occurs when its <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> becomes invalid, such as when the clock starts or stops.</span></span> <span data-ttu-id="c16d9-104">Registrieren Sie sich, für dieses Ereignis mit der Verwendung von direkt eine <xref:System.Windows.Media.Animation.Clock>, oder registrieren Sie mithilfe einer <xref:System.Windows.Media.Animation.Timeline>.</span><span class="sxs-lookup"><span data-stu-id="c16d9-104">You can register for this event with directly using a <xref:System.Windows.Media.Animation.Clock>, or you can register using a <xref:System.Windows.Media.Animation.Timeline>.</span></span>  
  
 <span data-ttu-id="c16d9-105">Im folgenden Beispiel ein <xref:System.Windows.Media.Animation.Storyboard> und zwei <xref:System.Windows.Media.Animation.DoubleAnimation> Objekte werden verwendet, um die Breite von zwei Rechtecken zu animieren.</span><span class="sxs-lookup"><span data-stu-id="c16d9-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> and two <xref:System.Windows.Media.Animation.DoubleAnimation> objects are used to animate the width of two rectangles.</span></span> <span data-ttu-id="c16d9-106">Die <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> Ereignis wird verwendet, um die Uhr Zustandsänderungen abhören.</span><span class="sxs-lookup"><span data-stu-id="c16d9-106">The <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event is used to listen for clock state changes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c16d9-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c16d9-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 <span data-ttu-id="c16d9-108">Die folgende Abbildung zeigt die verschiedenen Zustände-Animationen geben Sie als die übergeordnete Zeitachse (*Storyboard*) im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="c16d9-108">The following illustration shows the different states the animations enter as the parent timeline (*Storyboard*) progresses.</span></span>  
  
 <span data-ttu-id="c16d9-109">![Zustände für ein Drehbuch mit zwei Animationen Clock](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span><span class="sxs-lookup"><span data-stu-id="c16d9-109">![Clock states for a Storyboard with two animations](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span></span>  
  
 <span data-ttu-id="c16d9-110">Die folgende Tabelle zeigt die Zeiten, zu dem *Animation1*des <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> -Ereignis ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="c16d9-110">The following table shows the times at which *Animation1*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||  
|-|-|-|-|-|-|-|  
|<span data-ttu-id="c16d9-111">Zeit (in Sekunden)</span><span class="sxs-lookup"><span data-stu-id="c16d9-111">Time (Seconds)</span></span>|<span data-ttu-id="c16d9-112">1</span><span class="sxs-lookup"><span data-stu-id="c16d9-112">1</span></span>|<span data-ttu-id="c16d9-113">10</span><span class="sxs-lookup"><span data-stu-id="c16d9-113">10</span></span>|<span data-ttu-id="c16d9-114">19</span><span class="sxs-lookup"><span data-stu-id="c16d9-114">19</span></span>|<span data-ttu-id="c16d9-115">21</span><span class="sxs-lookup"><span data-stu-id="c16d9-115">21</span></span>|<span data-ttu-id="c16d9-116">30</span><span class="sxs-lookup"><span data-stu-id="c16d9-116">30</span></span>|<span data-ttu-id="c16d9-117">39</span><span class="sxs-lookup"><span data-stu-id="c16d9-117">39</span></span>|  
|<span data-ttu-id="c16d9-118">Zustand</span><span class="sxs-lookup"><span data-stu-id="c16d9-118">State</span></span>|<span data-ttu-id="c16d9-119">Aktiv</span><span class="sxs-lookup"><span data-stu-id="c16d9-119">Active</span></span>|<span data-ttu-id="c16d9-120">Aktiv</span><span class="sxs-lookup"><span data-stu-id="c16d9-120">Active</span></span>|<span data-ttu-id="c16d9-121">Beendet</span><span class="sxs-lookup"><span data-stu-id="c16d9-121">Stopped</span></span>|<span data-ttu-id="c16d9-122">Aktiv</span><span class="sxs-lookup"><span data-stu-id="c16d9-122">Active</span></span>|<span data-ttu-id="c16d9-123">Aktiv</span><span class="sxs-lookup"><span data-stu-id="c16d9-123">Active</span></span>|<span data-ttu-id="c16d9-124">Beendet</span><span class="sxs-lookup"><span data-stu-id="c16d9-124">Stopped</span></span>|  
  
 <span data-ttu-id="c16d9-125">Die folgende Tabelle zeigt die Zeiten, zu dem *Animation2*des <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> -Ereignis ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="c16d9-125">The following table shows the times at which *Animation2*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="c16d9-126">Zeit (in Sekunden)</span><span class="sxs-lookup"><span data-stu-id="c16d9-126">Time (Seconds)</span></span>|<span data-ttu-id="c16d9-127">1</span><span class="sxs-lookup"><span data-stu-id="c16d9-127">1</span></span>|<span data-ttu-id="c16d9-128">9</span><span class="sxs-lookup"><span data-stu-id="c16d9-128">9</span></span>|<span data-ttu-id="c16d9-129">11</span><span class="sxs-lookup"><span data-stu-id="c16d9-129">11</span></span>|<span data-ttu-id="c16d9-130">19</span><span class="sxs-lookup"><span data-stu-id="c16d9-130">19</span></span>|<span data-ttu-id="c16d9-131">21</span><span class="sxs-lookup"><span data-stu-id="c16d9-131">21</span></span>|<span data-ttu-id="c16d9-132">29</span><span class="sxs-lookup"><span data-stu-id="c16d9-132">29</span></span>|<span data-ttu-id="c16d9-133">31</span><span class="sxs-lookup"><span data-stu-id="c16d9-133">31</span></span>|<span data-ttu-id="c16d9-134">39</span><span class="sxs-lookup"><span data-stu-id="c16d9-134">39</span></span>|  
|<span data-ttu-id="c16d9-135">Zustand</span><span class="sxs-lookup"><span data-stu-id="c16d9-135">State</span></span>|<span data-ttu-id="c16d9-136">Aktiv</span><span class="sxs-lookup"><span data-stu-id="c16d9-136">Active</span></span>|<span data-ttu-id="c16d9-137">Ausfüllen</span><span class="sxs-lookup"><span data-stu-id="c16d9-137">Filling</span></span>|<span data-ttu-id="c16d9-138">Aktiv</span><span class="sxs-lookup"><span data-stu-id="c16d9-138">Active</span></span>|<span data-ttu-id="c16d9-139">Beendet</span><span class="sxs-lookup"><span data-stu-id="c16d9-139">Stopped</span></span>|<span data-ttu-id="c16d9-140">Aktiv</span><span class="sxs-lookup"><span data-stu-id="c16d9-140">Active</span></span>|<span data-ttu-id="c16d9-141">Ausfüllen</span><span class="sxs-lookup"><span data-stu-id="c16d9-141">Filling</span></span>|<span data-ttu-id="c16d9-142">Aktiv</span><span class="sxs-lookup"><span data-stu-id="c16d9-142">Active</span></span>|<span data-ttu-id="c16d9-143">Beendet</span><span class="sxs-lookup"><span data-stu-id="c16d9-143">Stopped</span></span>|  
  
 <span data-ttu-id="c16d9-144">Beachten Sie, dass *Animation1*des <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> Ereignis bei 10 Sekunden ausgelöst wird, obwohl Datenbankzustands bleibt <xref:System.Windows.Media.Animation.ClockState.Active>.</span><span class="sxs-lookup"><span data-stu-id="c16d9-144">Notice that *Animation1*'s  <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires at 10 seconds, even though its state remains <xref:System.Windows.Media.Animation.ClockState.Active>.</span></span> <span data-ttu-id="c16d9-145">Liegt darin, dass seinen Status geändert 10 Sekunden, aber es von <xref:System.Windows.Media.Animation.ClockState.Active> auf <xref:System.Windows.Media.Animation.ClockState.Filling> und dann zurück in <xref:System.Windows.Media.Animation.ClockState.Active> am selben Teilstrich.</span><span class="sxs-lookup"><span data-stu-id="c16d9-145">That's because its state changed at 10 seconds, but it changed from <xref:System.Windows.Media.Animation.ClockState.Active> to <xref:System.Windows.Media.Animation.ClockState.Filling> and then back to <xref:System.Windows.Media.Animation.ClockState.Active> in the same tick.</span></span>
