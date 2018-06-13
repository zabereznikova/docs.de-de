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
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a>Gewusst wie: Ändern der Geschwindigkeit einer Uhr, ohne die Geschwindigkeit ihrer Zeitachse zu ändern
Ein <xref:System.Windows.Media.Animation.ClockController> des Objekts <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> -Eigenschaft ermöglicht es Ihnen so ändern Sie die Geschwindigkeit von einer <xref:System.Windows.Media.Animation.Clock> zuzuweisen, ohne dass die <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> der Uhr <xref:System.Windows.Media.Animation.Timeline>. Im folgenden Beispiel ein <xref:System.Windows.Media.Animation.ClockController> wird verwendet, um interaktiv ändern die <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> einer Uhr. Die <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> Ereignis und der Uhr <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> Eigenschaft dienen zum Anzeigen der aktuellen globalen Taktfrequenz jedes Mal, wenn der interaktive <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> geändert wird.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
