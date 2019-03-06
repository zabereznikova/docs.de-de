---
title: 'Vorgehensweise: Festlegen einer Dauer für eine Animation'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
ms.openlocfilehash: 83f87e911d9d5412eaba1eb88aea74b9325bc899
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351625"
---
# <a name="how-to-set-a-duration-for-an-animation"></a>Vorgehensweise: Festlegen einer Dauer für eine Animation
Ein <xref:System.Windows.Media.Animation.Timeline> stellt einen Zeitabschnitt und die Länge dieses Abschnitts sich nach der Zeitachse richtet <xref:System.Windows.Duration>. Wenn eine <xref:System.Windows.Media.Animation.Timeline> Erreichen des Endes des seine Dauer, stoppt Sie die Wiedergabe. Wenn die <xref:System.Windows.Media.Animation.Timeline> untergeordnete Zeitachsen, hat sie die Wiedergabe ebenfalls beendet. Bei einer Animation die <xref:System.Windows.Duration> gibt an, wie lange die Animation einen Übergang vom Startwert zum Endwert benötigt.  
  
 Sie können angeben, ein <xref:System.Windows.Duration> mit einem bestimmten, endlichen Zeitwert oder den speziellen Werten <xref:System.Windows.Duration.Automatic%2A> oder <xref:System.Windows.Duration.Forever%2A>. Die Dauer einer Animation muss immer einen Uhrzeitwert sein, da eine Animation immer eine definierte, begrenzte Länge aufweisen muss, andernfalls die Animation wäre nicht wissen, wie Sie Übergang zwischen den Zielwerten. Zeitpläne für Container (<xref:System.Windows.Media.Animation.TimelineGroup> Objekte), wie z. B. <xref:System.Windows.Media.Animation.Storyboard> und <xref:System.Windows.Media.Animation.ParallelTimeline>, verfügen über eine Standarddauer von <xref:System.Windows.Duration.Automatic%2A>, was bedeutet, sie werden automatisch beendet, wenn das letzte untergeordnete Element-Wiedergabe gestoppt wurde.  
  
 In der folgenden Beispiel, Breite, Höhe und füllen die Farbe von einem <xref:System.Windows.Shapes.Rectangle> animiert ist. Dauer werden für das Animations- und Container Zeitachsen, was zu Animationseffekten, einschließlich steuern die wahrgenommene Geschwindigkeit einer Animation aus, und überschreiben die Dauer der untergeordnete Zeitachsen mit der Dauer einer Containerzeitachse festgelegt.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Duration>
- [Übersicht über Animationen](animation-overview.md)
