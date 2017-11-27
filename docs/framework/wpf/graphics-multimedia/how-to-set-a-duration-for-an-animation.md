---
title: 'Gewusst wie: Festlegen der Dauer einer Animation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9560e9d0a2809ae8f55a060eaec3b271539d5f94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-a-duration-for-an-animation"></a>Gewusst wie: Festlegen der Dauer einer Animation
Ein <xref:System.Windows.Media.Animation.Timeline> stellt ein Segment der Zeit und die Länge des Abschnitts sich nach der Zeitachse richtet <xref:System.Windows.Duration>. Wenn eine <xref:System.Windows.Media.Animation.Timeline> Erreichen des Endes des seine Dauer Wiedergabe beendet. Wenn die <xref:System.Windows.Media.Animation.Timeline> untergeordnete Zeitachsen, hat sie Wiedergabe ebenfalls beendet. Im Fall einer Animation die <xref:System.Windows.Duration> gibt an, wie lange die Animation für den Übergang vom Startwert zum Endwert benötigt.  
  
 Sie können angeben, ein <xref:System.Windows.Duration> mit einem bestimmten, endlichen Zeitwert oder die speziellen Werte <xref:System.Windows.Duration.Automatic%2A> oder <xref:System.Windows.Duration.Forever%2A>. Die Dauer einer Animation muss immer einen Time-Wert sein, da eine Animation immer eine Länge definierte ist, endliche sein muss, andernfalls die Animation würde nicht wissen, wie Sie zwischen den Zielwerten umgestellt werden. Container-Zeitplänen (<xref:System.Windows.Media.Animation.TimelineGroup> Objekte), wie z. B. <xref:System.Windows.Media.Animation.Storyboard> und <xref:System.Windows.Media.Animation.ParallelTimeline>, haben eine Standarddauer von <xref:System.Windows.Duration.Automatic%2A>, d. h., sie automatisch beendet, wenn das letzte untergeordnete Element Wiedergabe beendet wird.  
  
 In der folgenden Beispiel, Breite, Höhe und ausfüllen Farbe ein <xref:System.Windows.Shapes.Rectangle> animiert wird. Zeitdauern werden für Animationen und Container Zeitachsen, wodurch Animationseffekte einschließlich steuern die wahrgenommene Geschwindigkeit einer Animation und überschreiben die Dauer der untergeordnete Zeitachsen mit der Dauer einer Containerzeitachse festgelegt.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Duration>  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
