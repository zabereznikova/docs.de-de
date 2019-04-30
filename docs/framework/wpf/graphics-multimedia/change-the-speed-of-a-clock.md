---
title: 'Vorgehensweise: Ändern der Geschwindigkeit einer Uhr, ohne die Geschwindigkeit ihrer Zeitachse zu ändern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- speed of Clock [WPF], changing
- clocks [WPF], changing speed of
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
ms.openlocfilehash: 19e6874b9b472cb4a5f716677f99af03f2b73b10
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010188"
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a><span data-ttu-id="86d80-102">Vorgehensweise: Ändern der Geschwindigkeit einer Uhr, ohne die Geschwindigkeit ihrer Zeitachse zu ändern</span><span class="sxs-lookup"><span data-stu-id="86d80-102">How to: Change the Speed of a Clock Without Changing the Speed of Its Timeline</span></span>
<span data-ttu-id="86d80-103">Ein <xref:System.Windows.Media.Animation.ClockController> des Objekts <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> Eigenschaft können Sie so ändern Sie die Geschwindigkeit von ein <xref:System.Windows.Media.Animation.Clock> ohne eine Änderung der <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> der Uhr des <xref:System.Windows.Media.Animation.Timeline>.</span><span class="sxs-lookup"><span data-stu-id="86d80-103">A <xref:System.Windows.Media.Animation.ClockController> object's <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> property enables you to change the speed of a <xref:System.Windows.Media.Animation.Clock> without altering the <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> of the clock's <xref:System.Windows.Media.Animation.Timeline>.</span></span> <span data-ttu-id="86d80-104">Im folgenden Beispiel eine <xref:System.Windows.Media.Animation.ClockController> wird verwendet, um interaktiv ändern der <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> einer Uhr.</span><span class="sxs-lookup"><span data-stu-id="86d80-104">In the following example, a <xref:System.Windows.Media.Animation.ClockController> is used to interactively modify the <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> of a clock.</span></span> <span data-ttu-id="86d80-105">Die <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> Ereignis- und der Uhr <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> Eigenschaft werden verwendet, um die Uhr für die aktuelle globale Geschwindigkeit anzeigen jedes Mal, wenn der interaktive <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> geändert wird.</span><span class="sxs-lookup"><span data-stu-id="86d80-105">The <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> event and the clock's <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> property are used to display the clock's current global speed each time its interactive <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> is changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86d80-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="86d80-106">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
