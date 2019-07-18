---
title: Übersicht über Zeitsteuerungsverhalten
ms.date: 03/30/2017
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
ms.openlocfilehash: 1433583c4c8e20533e7e18f1722d5481ffed3bbc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625687"
---
# <a name="timing-behaviors-overview"></a>Übersicht über Zeitsteuerungsverhalten
Dieses Thema beschreibt das Zeitsteuerungsverhalten von Animationen und andere <xref:System.Windows.Media.Animation.Timeline> Objekte.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Vorraussetzungen  
 Als Voraussetzung für dieses Thema sollten Sie mit grundlegenden Animationsfunktionen vertraut sein. Weitere Informationen finden Sie unter den [Übersicht über Animationen](animation-overview.md).  
  
<a name="timelinetypes"></a>   
## <a name="timeline-types"></a>Zeitachsentypen  
 Ein <xref:System.Windows.Media.Animation.Timeline> stellt einen Zeitabschnitt dar. Sie bietet Eigenschaften, mit denen Sie z.B. die Länge dieses Abschnitts, seinen Start, die Anzahl der Wiederholungen und die Geschwindigkeit des Fortschreitens der Zeit im Abschnitt Segment angeben.  
  
 Klassen, die von der Timeline-Klasse erben, bieten zusätzliche Funktionen, wie z.B. Animation und Medienwiedergabe. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet die folgenden <xref:System.Windows.Media.Animation.Timeline> Typen.  
  
|Zeitachsentypen|Beschreibung|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|Abstrakte Basisklasse für <xref:System.Windows.Media.Animation.Timeline> Objekte, die Ausgabewerte für das Animieren von Eigenschaften zu generieren.|  
|<xref:System.Windows.Media.MediaTimeline>|Erzeugt eine Ausgabe aus einer Mediendatei.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|Eine Art von <xref:System.Windows.Media.Animation.TimelineGroup> , untergeordneten Gruppen und Steuerelemente <xref:System.Windows.Media.Animation.Timeline> Objekte.|  
|<xref:System.Windows.Media.Animation.Storyboard>|Eine Art von <xref:System.Windows.Media.Animation.ParallelTimeline> , die Zielinformationen für die in ihm enthaltenen Zeitachsenobjekte bereitstellt.|  
|<xref:System.Windows.Media.Animation.Timeline>|Abstrakte Basisklasse, die Zeitsteuerungsverhalten definiert.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|Abstrakte Klasse zum <xref:System.Windows.Media.Animation.Timeline> Objekte, die andere enthält können <xref:System.Windows.Media.Animation.Timeline> Objekte.|  
  
<a name="propertiesthatcontroltimelinelength"></a>   
## <a name="properties-that-control-the-length-of-a-timeline"></a>Eigenschaften, die die Länge einer Zeitachse steuern  
 Ein <xref:System.Windows.Media.Animation.Timeline> stellt einen Zeitabschnitt, und die Länge einer Zeitachse auf unterschiedliche Weise beschrieben werden kann. In der folgenden Tabelle werden mehrere Begriffe für die Beschreibung der Länge einer Zeitachse definiert.  
  
|Begriff|Beschreibung|Eigenschaften||||  
|----------|-----------------|----------------|-|-|-|  
|Einfache Dauer|Zeitspanne, die eine Zeitachse für eine Vorwärtsiteration benötigt.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|Eine Wiederholung|Die Zeitspanne für eine Zeitachse vorwärts nach und bei Spielen dauert die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> -Eigenschaft "true" ist, einmal rückwärts abgespielt.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|Aktiver Zeitraum|Die Zeitdauer für ein Timeline alle angegebenen von Wiederholungen ausführen dauert seine <xref:System.Windows.Media.Animation.RepeatBehavior> Eigenschaft.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>   
### <a name="the-duration-property"></a>Die Duration-Eigenschaft  
 Wie bereits erwähnt, stellt eine Zeitachse einen Zeitabschnitt dar. Die Länge dieses Abschnitts richtet sich nach der Zeitachse <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Wenn eine Zeitachse das Ende ihrer Dauer erreicht, wird die Wiedergabe beendet. Wenn die Zeitachse über untergeordnete Zeitachsen verfügt, wird deren Wiedergabe ebenfalls beendet. Bei einer Animation die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> gibt an, wie lange die Animation einen Übergang vom Startwert zum Endwert benötigt. Die Dauer einer Zeitachse bezeichnet die *einfache Dauer*, um die Dauer einer einzelnen Iteration und die Gesamtlänge der Wiedergabezeit die Animation einschl. Wiederholungen unterscheiden. Sie können angeben, dass eine Dauer mit einem endlichen Zeitwert oder den speziellen Werten <xref:System.Windows.Duration.Automatic%2A> oder <xref:System.Windows.Duration.Forever%2A>. Die Dauer einer Animation sollte zum Auflösen einer <xref:System.Windows.Duration.TimeSpan%2A> Wert, sodass sie einen Übergang zwischen Werten ausführen kann.  
  
 Das folgende Beispiel zeigt eine <xref:System.Windows.Media.Animation.DoubleAnimation> mit einem <xref:System.Windows.Media.Animation.Timeline.Duration%2A> von fünf Sekunden.  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 Zeitpläne für Container, z. B. <xref:System.Windows.Media.Animation.Storyboard> und <xref:System.Windows.Media.Animation.ParallelTimeline>, verfügen über eine Standarddauer von <xref:System.Windows.Duration.Automatic%2A>, was bedeutet, sie werden automatisch beendet, wenn das letzte untergeordnete Element-Wiedergabe gestoppt wurde. Das folgende Beispiel zeigt eine <xref:System.Windows.Media.Animation.Storyboard> , deren <xref:System.Windows.Media.Animation.Timeline.Duration%2A> auf fünf Sekunden, die Länge der Zeit, die alle untergeordneten löst <xref:System.Windows.Media.Animation.DoubleAnimation> Objekte ausführen.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 Durch Festlegen der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> einer Containerzeitachse auf einem <xref:System.Windows.Duration.TimeSpan%2A> Wert, Sie können erzwingen, dass länger oder kürzer als untergeordnetes Element <xref:System.Windows.Media.Animation.Timeline> Objekte würde abspielen. Setzen Sie die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> auf einen Wert, der kleiner als die Länge der Containerzeitachse untergeordneter <xref:System.Windows.Media.Animation.Timeline> Objekten, das untergeordnete Element <xref:System.Windows.Media.Animation.Timeline> Objekte beenden wiedergeben, wenn die Containerzeitachse ist. Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> von der <xref:System.Windows.Media.Animation.Storyboard> aus den vorherigen Beispielen auf drei Sekunden. Daher die erste <xref:System.Windows.Media.Animation.DoubleAnimation> beendet wird, nach drei Sekunden, sobald sie das der Breite des Zielrechtecks auf 60 animiert hat.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>   
### <a name="the-repeatbehavior-property"></a>RepeatBehavior-Eigenschaft  
 Die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> steuert, wie oft sie ihre einfache Dauer wiederholt. Mithilfe der <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> -Eigenschaft, können Sie angeben, wie oft die Wiedergabe der Zeitachse (einer Iteration <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>) oder die gesamte Länge der Zeit, die wiedergegeben werden soll (eine Wiederholung <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A>). In beiden Fällen durchläuft die Animation so viele vollständige Ausführungen, wie für die erforderliche Anzahl oder Dauer nötig. In der Standardeinstellung haben Zeitachsen einen Iterationszähler von `1.0`, d. h., sie wird einmal abgespielt und überhaupt nicht wiederholen.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft, um eine <xref:System.Windows.Media.Animation.DoubleAnimation> zweimal ihre einfache Dauer wiedergegeben werden, durch eine Iterationsanzahl angeben.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 Im nächsten Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft, um die <xref:System.Windows.Media.Animation.DoubleAnimation> für die Hälfte ihrer einfachen Dauer wiedergegeben.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 Setzen Sie die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> zu <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, <xref:System.Windows.Media.Animation.Timeline> wird wiederholt, bis Sie interaktiv oder durch das Zeitsteuerungssystem beendet. Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft, um die <xref:System.Windows.Media.Animation.DoubleAnimation> Spielen auf unbestimmte Zeit.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 Ein zusätzliches Beispiel finden Sie unter [Wiederholen einer Animation](how-to-repeat-an-animation.md).  
  
<a name="autoreverseproperty"></a>   
### <a name="the-autoreverse-property"></a>AutoReverse-Eigenschaft  
 Die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft gibt an, ob eine <xref:System.Windows.Media.Animation.Timeline> am Ende jeder Vorwärtsiteration rückwärts wiedergegeben wird. Im folgende Beispiel wird auf die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.DoubleAnimation> zu `true`; daher es erstellt eine Animation von 0 bis 100 und dann von 100 auf 0 (null). Sie wird insgesamt 10 Sekunden wiedergegeben.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 Bei Verwendung von eine <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> -Wert an die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> von eine <xref:System.Windows.Media.Animation.Timeline> und die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> -Eigenschaft dieses <xref:System.Windows.Media.Animation.Timeline> ist `true`, besteht eine Wiederholung einer gefolgt von einer Iteration Vorwärtsiteration.  Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> von der <xref:System.Windows.Media.Animation.DoubleAnimation> aus dem vorherigen Beispiel auf einem <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> von zwei. Daher die <xref:System.Windows.Media.Animation.DoubleAnimation> 20 Sekunden lang abgespielt: Weiterleiten von fünf Sekunden rückwärts, fünf Sekunden in diesem Fall 5 Sekunden vorwärts und rückwärts für fünf Sekunden.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 Verfügt eine Containerzeitachse untergeordneten <xref:System.Windows.Media.Animation.Timeline> Objekten, die sie umkehren, wenn die Containerzeitachse ist. Weitere Beispiele finden Sie unter [angeben, ob eine Zeitachse automatisch umgekehrt wird](how-to-specify-whether-a-timeline-automatically-reverses.md).  
  
<a name="timelinebegin"></a>   
## <a name="the-begintime-property"></a>BeginTime-Eigenschaft  
 Die <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> Eigenschaft können Sie angeben, wenn eine Zeitachse gestartet wird.  Die Startzeit einer Zeitachse bezieht sich auf die übergeordnete Zeitachse. Eine Anfangszeit von 0 (null) Sekunden bedeutet, dass die Zeitachse gestartet wird, sobald die übergeordnete gestartet wird. Jeder andere Wert erstellt einen Offset zwischen dem Zeitpunkt des Starts der Wiedergabe der übergeordneten Zeitachse und der Wiedergabe der untergeordneten Zeitachse. Beispielsweise bedeutet eine Startzeit von 2 Sekunden, dass die Wiedergabe der Zeitachse gestartet wird, wenn ihre übergeordnete Zeitachse eine Zeit von 2 Sekunden erreicht hat. Standardmäßig haben alle Zeitachsen eine Startzeit von 0 Sekunden. Einer Zeitachse kann auch festgelegt werden Startzeit, `null`, wodurch verhindert wird, dass die Zeitachse ab. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], Angabe von null mithilfe der [X: Null Markup Extension](../../xaml-services/x-null-markup-extension.md).  
  
 Beachten Sie, dass die Startzeit nicht angewendet, jedes Mal eine Zeitachse wird, da wiederholt die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> festlegen. Würden Sie eine Animation erstellen eine <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> von 10 Sekunden und eine <xref:System.Windows.Media.Animation.RepeatBehavior> von <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, gäbe es eine Verzögerung von 10 Sekunden, bevor die Animation zum ersten Mal, jedoch nicht für jede nachfolgende Wiederholung wiedergegeben. Soll jedoch die übergeordnete Zeitachse der Animation neu gestartet oder wiederholt werden, tritt die Verzögerung von 10 Sekunden auf.  
  
 Die <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> Eigenschaft ist nützlich für das Staffeln von Zeitachsen. Das folgende Beispiel erstellt eine <xref:System.Windows.Media.Animation.Storyboard> Listenfeldsteuerelement mit zwei untergeordneten <xref:System.Windows.Media.Animation.DoubleAnimation> Objekte. Die erste Animation hat eine <xref:System.Windows.Media.Animation.Timeline.Duration%2A> von fünf Sekunden, und die zweite hat eine <xref:System.Windows.Media.Animation.Timeline.Duration%2A> von 3 Sekunden. Im Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> des zweiten <xref:System.Windows.Media.Animation.DoubleAnimation> auf 5 Sekunden, sodass die Wiedergabe beginnt nach dem ersten <xref:System.Windows.Media.Animation.DoubleAnimation> endet.  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>   
## <a name="the-fillbehavior-property"></a>FillBehavior-Eigenschaft  
 Wenn eine <xref:System.Windows.Media.Animation.Timeline> das Ende ihrer aktiven Gesamtdauer erreicht die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft gibt an, ob sie beendet wird oder ihren letzten Wert behält. Eine Animation mit einer <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> von <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> "behält" ihren Ausgabewert: die animierte Eigenschaft behält den letzten Wert der Animation. Der Wert <xref:System.Windows.Media.Animation.FillBehavior.Stop> bewirkt, dass die Animation beendet, die auf die Zieleigenschaft, nachdem er beendet.  
  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Media.Animation.Storyboard> Listenfeldsteuerelement mit zwei untergeordneten <xref:System.Windows.Media.Animation.DoubleAnimation> Objekte. Beide <xref:System.Windows.Media.Animation.DoubleAnimation> Objekte animieren das <xref:System.Windows.FrameworkElement.Width%2A> von einer <xref:System.Windows.Shapes.Rectangle> von 0 bis 100. Die <xref:System.Windows.Shapes.Rectangle> Elemente verfügen über nicht animiert <xref:System.Windows.FrameworkElement.Width%2A> -Werte von 500 [geräteunabhängigen Pixeln].  
  
- Die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft des ersten <xref:System.Windows.Media.Animation.DoubleAnimation> nastaven NA hodnotu <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, der Standardwert. Daher bleibt die Breite des Rechtecks bei 100, sobald die <xref:System.Windows.Media.Animation.DoubleAnimation> endet.  
  
- Die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> -Eigenschaft der zweiten <xref:System.Windows.Media.Animation.DoubleAnimation> nastaven NA hodnotu <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Daher die <xref:System.Windows.FrameworkElement.Width%2A> des zweiten <xref:System.Windows.Shapes.Rectangle> wird auf 500 nach der <xref:System.Windows.Media.Animation.DoubleAnimation> endet.  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>   
## <a name="properties-that-control-the-speed-of-a-timeline"></a>Eigenschaften, die die Geschwindigkeit einer Zeitachse steuern  
 Die <xref:System.Windows.Media.Animation.Timeline> -Klasse stellt drei Eigenschaften zum Festlegen ihrer Geschwindigkeit bereit:  
  
- <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> – Gibt die Geschwindigkeit relativ zum übergeordneten Element, an dem die Zeit, für abläuft eine <xref:System.Windows.Media.Animation.Timeline>. Werte größer als 1 erhöhen die Geschwindigkeit der <xref:System.Windows.Media.Animation.Timeline> und ihre untergeordneten <xref:System.Windows.Media.Animation.Timeline> Objekte; die Werte zwischen 0 und 1 verlangsamen sie. Der Wert 1 gibt an, dass <xref:System.Windows.Media.Animation.Timeline> im Verlauf der gleiche Tarif wie das übergeordnete Element. Die <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> Einstellung einer Containerzeitachse wirkt sich auf alle untergeordneten <xref:System.Windows.Media.Animation.Timeline> auch Objekte.  
  
- <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> – Legt den prozentualen Anteil der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> einer Zeitachse für die Beschleunigung aufgewendet. Ein Beispiel finden Sie unter [Gewusst wie: Beschleunigen oder verlangsamen einer Animation](how-to-accelerate-or-decelerate-an-animation.md). 
  
- <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> -Legt den prozentualen Anteil der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> einer Zeitachse für die Verlangsamung aufgewendet. Ein Beispiel finden Sie unter [Gewusst wie: Beschleunigen oder verlangsamen einer Animation](how-to-accelerate-or-decelerate-an-animation.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über das Animations- und Zeitsteuerungssystem](animation-and-timing-system-overview.md)
- [Übersicht über Zeitsteuerungsereignisse](timing-events-overview.md)
- [Themen zu Vorgehensweisen](animation-and-timing-how-to-topics.md)
- [Beispiel zum Verhalten der Animationszeitsteuerung](https://go.microsoft.com/fwlink/?LinkID=159970)
