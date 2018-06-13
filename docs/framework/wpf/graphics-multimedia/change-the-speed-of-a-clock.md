---
title: 'Gewusst wie: Ändern der Geschwindigkeit einer Uhr, ohne die Geschwindigkeit ihrer Zeitachse zu ändern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- speed of Clock [WPF], changing
- clocks [WPF], changing speed of
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
ms.openlocfilehash: 126d260fbd59c1c35d8f56be6aa7dabe7688fa32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556613"
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a><span data-ttu-id="b9122-102">Gewusst wie: Ändern der Geschwindigkeit einer Uhr, ohne die Geschwindigkeit ihrer Zeitachse zu ändern</span><span class="sxs-lookup"><span data-stu-id="b9122-102">How to: Change the Speed of a Clock Without Changing the Speed of Its Timeline</span></span>
<span data-ttu-id="b9122-103">Ein <xref:System.Windows.Media.Animation.ClockController> des Objekts <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> -Eigenschaft ermöglicht es Ihnen so ändern Sie die Geschwindigkeit von einer <xref:System.Windows.Media.Animation.Clock> zuzuweisen, ohne dass die <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> der Uhr <xref:System.Windows.Media.Animation.Timeline>.</span><span class="sxs-lookup"><span data-stu-id="b9122-103">A <xref:System.Windows.Media.Animation.ClockController> object's <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> property enables you to change the speed of a <xref:System.Windows.Media.Animation.Clock> without altering the <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> of the clock's <xref:System.Windows.Media.Animation.Timeline>.</span></span> <span data-ttu-id="b9122-104">Im folgenden Beispiel ein <xref:System.Windows.Media.Animation.ClockController> wird verwendet, um interaktiv ändern die <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> einer Uhr.</span><span class="sxs-lookup"><span data-stu-id="b9122-104">In the following example, a <xref:System.Windows.Media.Animation.ClockController> is used to interactively modify the <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> of a clock.</span></span> <span data-ttu-id="b9122-105">Die <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> Ereignis und der Uhr <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> Eigenschaft dienen zum Anzeigen der aktuellen globalen Taktfrequenz jedes Mal, wenn der interaktive <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b9122-105">The <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> event and the clock's <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> property are used to display the clock's current global speed each time its interactive <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> is changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9122-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9122-106">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
