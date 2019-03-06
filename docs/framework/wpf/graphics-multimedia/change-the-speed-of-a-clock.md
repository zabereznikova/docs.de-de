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
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358274"
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a>Vorgehensweise: Ändern der Geschwindigkeit einer Uhr, ohne die Geschwindigkeit ihrer Zeitachse zu ändern
Ein <xref:System.Windows.Media.Animation.ClockController> des Objekts <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> Eigenschaft können Sie so ändern Sie die Geschwindigkeit von ein <xref:System.Windows.Media.Animation.Clock> ohne eine Änderung der <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> der Uhr des <xref:System.Windows.Media.Animation.Timeline>. Im folgenden Beispiel eine <xref:System.Windows.Media.Animation.ClockController> wird verwendet, um interaktiv ändern der <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> einer Uhr. Die <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> Ereignis- und der Uhr <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> Eigenschaft werden verwendet, um die Uhr für die aktuelle globale Geschwindigkeit anzeigen jedes Mal, wenn der interaktive <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> geändert wird.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
