---
title: "Gewusst wie: Ändern der Geschwindigkeit einer Uhr, ohne die Geschwindigkeit ihrer Zeitachse zu ändern"
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
- speed of Clock [WPF], changing
- clocks [WPF], changing speed of
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 98cfa63eac4bc697c5412616de71395624408c63
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a>Gewusst wie: Ändern der Geschwindigkeit einer Uhr, ohne die Geschwindigkeit ihrer Zeitachse zu ändern
Ein <xref:System.Windows.Media.Animation.ClockController> des Objekts <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> -Eigenschaft ermöglicht es Ihnen so ändern Sie die Geschwindigkeit von einer <xref:System.Windows.Media.Animation.Clock> zuzuweisen, ohne dass die <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> der Uhr <xref:System.Windows.Media.Animation.Timeline>. Im folgenden Beispiel ein <xref:System.Windows.Media.Animation.ClockController> wird verwendet, um interaktiv ändern die <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> einer Uhr. Die <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> Ereignis und der Uhr <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> Eigenschaft dienen zum Anzeigen der aktuellen globalen Taktfrequenz jedes Mal, wenn der interaktive <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> geändert wird.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
