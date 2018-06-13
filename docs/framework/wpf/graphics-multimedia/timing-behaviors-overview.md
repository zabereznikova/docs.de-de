---
title: Übersicht über Zeitsteuerungsverhalten
ms.date: 03/30/2017
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
ms.openlocfilehash: 31a6b7d3b92e886d9c90fc39d69f31cf72b99666
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566323"
---
# <a name="timing-behaviors-overview"></a>Übersicht über Zeitsteuerungsverhalten
In diesem Thema wird beschrieben, die Zeitsteuerungsverhalten von Animationen und andere <xref:System.Windows.Media.Animation.Timeline> Objekte.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Als Voraussetzung für dieses Thema sollten Sie mit grundlegenden Animationsfunktionen vertraut sein. Weitere Informationen finden Sie unter der [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="timelinetypes"></a>   
## <a name="timeline-types"></a>Zeitachsentypen  
 Ein <xref:System.Windows.Media.Animation.Timeline> einen Zeitabschnitt darstellt. Sie bietet Eigenschaften, mit denen Sie z.B. die Länge dieses Abschnitts, seinen Start, die Anzahl der Wiederholungen und die Geschwindigkeit des Fortschreitens der Zeit im Abschnitt Segment angeben.  
  
 Klassen, die von der Timeline-Klasse erben, bieten zusätzliche Funktionen, wie z.B. Animation und Medienwiedergabe. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet die folgenden <xref:System.Windows.Media.Animation.Timeline> Typen.  
  
|Zeitachsentypen|Beschreibung|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|Abstrakte Basisklasse für <xref:System.Windows.Media.Animation.Timeline> Objekte, die Ausgabewerte zum Animieren von Eigenschaften zu generieren.|  
|<xref:System.Windows.Media.MediaTimeline>|Erzeugt eine Ausgabe aus einer Mediendatei.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|Ein Typ von <xref:System.Windows.Media.Animation.TimelineGroup> , untergeordneten Gruppen und Steuerelemente <xref:System.Windows.Media.Animation.Timeline> Objekte.|  
|<xref:System.Windows.Media.Animation.Storyboard>|Ein Typ von <xref:System.Windows.Media.Animation.ParallelTimeline> Zielinformationen für die darin enthaltenen Zeitachsenobjekte bereitstellt.|  
|<xref:System.Windows.Media.Animation.Timeline>|Abstrakte Basisklasse, die Zeitsteuerungsverhalten definiert.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|Abstrakte Klasse für <xref:System.Windows.Media.Animation.Timeline> Objekte, die andere enthält können <xref:System.Windows.Media.Animation.Timeline> Objekte.|  
  
<a name="propertiesthatcontroltimelinelength"></a>   
## <a name="properties-that-control-the-length-of-a-timeline"></a>Eigenschaften, die die Länge einer Zeitachse steuern  
 Ein <xref:System.Windows.Media.Animation.Timeline> stellt einen Zeitabschnitt, und die Länge einer Zeitachse auf unterschiedliche Weise beschrieben werden können. In der folgenden Tabelle werden mehrere Begriffe für die Beschreibung der Länge einer Zeitachse definiert.  
  
|Begriff|Beschreibung|Eigenschaften||||  
|----------|-----------------|----------------|-|-|-|  
|Einfache Dauer|Zeitspanne, die eine Zeitachse für eine Vorwärtsiteration benötigt.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|Eine Wiederholung|Die Zeitdauer für eine Zeitachse vorwärts nach, und wenn wiedergeben dauert die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft ist "true", einmal rückwärts wiedergegeben.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|Aktiver Zeitraum|Die Zeitdauer für einen Zeitplan alle Wiederholungen, die vom angegebenen abgeschlossen dauert seiner <xref:System.Windows.Media.Animation.RepeatBehavior> Eigenschaft.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>   
### <a name="the-duration-property"></a>Die Duration-Eigenschaft  
 Wie bereits erwähnt, stellt eine Zeitachse einen Zeitabschnitt dar. Die Länge des Abschnitts richtet sich nach der Zeitachse <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Wenn eine Zeitachse das Ende ihrer Dauer erreicht, wird die Wiedergabe beendet. Wenn die Zeitachse über untergeordnete Zeitachsen verfügt, wird deren Wiedergabe ebenfalls beendet. Im Fall einer Animation die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> gibt an, wie lange die Animation für den Übergang vom Startwert zum Endwert benötigt. Eine Zeitachse Dauer bezeichnet wird seine *einfache Dauer*, um die Dauer einer einzelnen Iteration und die Gesamtlänge der Zeit, die die Animation bei Wiederholungen einschließlich unterscheiden. Sie können angeben, dass eine Dauer mit einer endlichen Zeitwert oder die speziellen Werte <xref:System.Windows.Duration.Automatic%2A> oder <xref:System.Windows.Duration.Forever%2A>. Die Dauer einer Animation sollte sich auflösen, um eine <xref:System.Windows.Duration.TimeSpan%2A> Wert, damit sie einen Übergang zwischen Werten ausführen kann.  
  
 Das folgende Beispiel zeigt eine <xref:System.Windows.Media.Animation.DoubleAnimation> mit einem <xref:System.Windows.Media.Animation.Timeline.Duration%2A> von fünf Sekunden.  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 Containerzeitachsen, z. B. <xref:System.Windows.Media.Animation.Storyboard> und <xref:System.Windows.Media.Animation.ParallelTimeline>, haben Sie eine Standarddauer von <xref:System.Windows.Duration.Automatic%2A>, d. h., sie automatisch beendet, wenn das letzte untergeordnete Element Wiedergabe beendet wird. Das folgende Beispiel zeigt eine <xref:System.Windows.Media.Animation.Storyboard> , deren <xref:System.Windows.Media.Animation.Timeline.Duration%2A> löst in fünf Sekunden, die Länge der Zeit, die alle untergeordneten <xref:System.Windows.Media.Animation.DoubleAnimation> Objekte abgeschlossen.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 Durch Festlegen der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> ein Containerzeitachse, um eine <xref:System.Windows.Duration.TimeSpan%2A> Wert, Sie können erzwingen, dass länger oder kürzer als untergeordneten <xref:System.Windows.Media.Animation.Timeline> Objekte würde spielen. Wenn Sie festlegen, die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> auf einen Wert, der kleiner als die Länge der Containerzeitachse untergeordneten ist <xref:System.Windows.Media.Animation.Timeline> Objekten, das untergeordnete Element <xref:System.Windows.Media.Animation.Timeline> Objekte Beenden wiedergegeben, wenn der Containerzeitachse. Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> von der <xref:System.Windows.Media.Animation.Storyboard> aus den vorherigen Beispielen auf drei Sekunden. Daher die erste <xref:System.Windows.Media.Animation.DoubleAnimation> nach drei Sekunden, wenn sie das der Breite des Zielrechtecks auf 60 animiert wurde beendet.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>   
### <a name="the-repeatbehavior-property"></a>RepeatBehavior-Eigenschaft  
 Die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft von einem <xref:System.Windows.Media.Animation.Timeline> steuert, wie oft ihre einfache Dauer wiederholt. Mithilfe der <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> -Eigenschaft, können Sie angeben, wie oft die Zeitachse wiedergegeben wird (eine Iteration <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>) oder die gesamte Zeitdauer wiedergegeben werden soll (eine Wiederholung <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A>). In beiden Fällen durchläuft die Animation so viele vollständige Ausführungen, wie für die erforderliche Anzahl oder Dauer nötig. Wird standardmäßig von Zeitachsen ist eine Iteration `1.0`, d. h. sie einmal wiedergegeben und nicht wiederholt.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft, um eine <xref:System.Windows.Media.Animation.DoubleAnimation> für zweimal seine einfache Dauer wiedergegeben werden, durch eine Iterationsanzahl angeben.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 Im nächste Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft, um die <xref:System.Windows.Media.Animation.DoubleAnimation> für Hälfte seine einfache Dauer wiedergegeben.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 Wenn Sie festlegen, die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> auf <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, die <xref:System.Windows.Media.Animation.Timeline> wird wiederholt, bis Sie interaktiv oder durch das System ein Timeout beendet. Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft, um die <xref:System.Windows.Media.Animation.DoubleAnimation> unbegrenzt.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 Ein weiteres Beispiel finden Sie unter [Wiederholen einer Animation](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md).  
  
<a name="autoreverseproperty"></a>   
### <a name="the-autoreverse-property"></a>AutoReverse-Eigenschaft  
 Die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft gibt an, ob eine <xref:System.Windows.Media.Animation.Timeline> am Ende jeder Iteration forward rückwärts wiedergegeben wird. Im folgenden Beispiel wird auf die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.DoubleAnimation> auf `true`; daher es erstellt eine Animation von 0 bis 100, und klicken Sie dann von 100 auf 0 (null). Sie wird insgesamt 10 Sekunden wiedergegeben.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 Bei Verwendung von eine <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> -Wert an die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> von einer <xref:System.Windows.Media.Animation.Timeline> und die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> -Eigenschaft dieses <xref:System.Windows.Media.Animation.Timeline> ist `true`, eine einzelne Wiederholung besteht aus einer gefolgt von einer Iteration vorwärts.  Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> von der <xref:System.Windows.Media.Animation.DoubleAnimation> aus dem vorherigen Beispiel um eine <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> von zwei. Daher der <xref:System.Windows.Media.Animation.DoubleAnimation> 20 Sekunden abgespielt: Weiterleiten von fünf Sekunden, rückwärts fünf Sekunden, 5 Sekunden lang vorwärts und rückwärts für fünf Sekunden.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 Wenn ein untergeordnetes Element enthält <xref:System.Windows.Media.Animation.Timeline> Objekte, die sie umkehren, wenn der Containerzeitachse. Weitere Beispiele finden Sie unter [angeben, ob ein Zeitplan automatisch kehrt](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md).  
  
<a name="timelinebegin"></a>   
## <a name="the-begintime-property"></a>BeginTime-Eigenschaft  
 Die <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> Eigenschaft können Sie angeben, wann eine Zeitachse beginnt.  Die Startzeit einer Zeitachse bezieht sich auf die übergeordnete Zeitachse. Eine Anfangszeit von 0 (null) Sekunden bedeutet, dass die Zeitachse gestartet wird, sobald die übergeordnete gestartet wird. Jeder andere Wert erstellt einen Offset zwischen dem Zeitpunkt des Starts der Wiedergabe der übergeordneten Zeitachse und der Wiedergabe der untergeordneten Zeitachse. Beispielsweise bedeutet eine Startzeit von 2 Sekunden, dass die Wiedergabe der Zeitachse gestartet wird, wenn ihre übergeordnete Zeitachse eine Zeit von 2 Sekunden erreicht hat. Standardmäßig haben alle Zeitachsen eine Startzeit von 0 Sekunden. Sie können auch festlegen, einer Zeitachse Anfangszeit zu `null`, dadurch wird verhindert, dass die Zeitachse ab. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], Sie geben Sie null mithilfe der [X: Null-Markuperweiterung](../../../../docs/framework/xaml-services/x-null-markup-extension.md).  
  
 Beachten Sie, dass die Anfangszeit nicht angewendet, jedes Mal eine Zeitachse wird wegen der wiederholt seine <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Einstellung. Würden Sie zum Erstellen einer Animation mit einer <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> von 10 Sekunden und eine <xref:System.Windows.Media.Animation.RepeatBehavior> von <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, gäbe es eine Verzögerung von 10 Sekunden, bevor die Animation zum ersten Mal, jedoch nicht für die einzelnen aufeinander folgenden Wiederholung wiedergegeben. Soll jedoch die übergeordnete Zeitachse der Animation neu gestartet oder wiederholt werden, tritt die Verzögerung von 10 Sekunden auf.  
  
 Die <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> Eigenschaft ist nützlich für die Zeitachsen staffeln. Das folgende Beispiel erstellt eine <xref:System.Windows.Media.Animation.Storyboard> , besitzt zwei untergeordnete <xref:System.Windows.Media.Animation.DoubleAnimation> Objekte. Die erste Animation verfügt über eine <xref:System.Windows.Media.Animation.Timeline.Duration%2A> von fünf Sekunden und die zweite eine <xref:System.Windows.Media.Animation.Timeline.Duration%2A> von 3 Sekunden. Im Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> des zweiten <xref:System.Windows.Media.Animation.DoubleAnimation> auf 5 Sekunden, sodass die Wiedergabe beginnt nach dem ersten <xref:System.Windows.Media.Animation.DoubleAnimation> endet.  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>   
## <a name="the-fillbehavior-property"></a>FillBehavior-Eigenschaft  
 Wenn eine <xref:System.Windows.Media.Animation.Timeline> erreicht das Ende der aktiven Gesamtdauer der <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft gibt an, ob sie beendet wird oder den letzten Wert enthält. Eine Animation mit einer <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> von <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> Ausgabewert "enthält": der zu animierende Eigenschaft behält den letzten Wert der Animation. Ein Wert von <xref:System.Windows.Media.Animation.FillBehavior.Stop> bewirkt, dass das Beenden der Animation auf die Zieleigenschaft, nachdem er beendet.  
  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Media.Animation.Storyboard> , besitzt zwei untergeordnete <xref:System.Windows.Media.Animation.DoubleAnimation> Objekte. Beide <xref:System.Windows.Media.Animation.DoubleAnimation> Animieren von Objekten der <xref:System.Windows.FrameworkElement.Width%2A> von einem <xref:System.Windows.Shapes.Rectangle> von 0 bis 100. Die <xref:System.Windows.Shapes.Rectangle> Elemente verfügen über nicht animiert <xref:System.Windows.FrameworkElement.Width%2A> Werte 500 [geräteunabhängigen Pixeln].  
  
-   Die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft des ersten <xref:System.Windows.Media.Animation.DoubleAnimation> festgelegt ist, um <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, der Standardwert. Daher bleibt die Breite des Rechtecks bei 100 nach der <xref:System.Windows.Media.Animation.DoubleAnimation> endet.  
  
-   Die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft des zweiten <xref:System.Windows.Media.Animation.DoubleAnimation> festgelegt ist, um <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Daher die <xref:System.Windows.FrameworkElement.Width%2A> des zweiten <xref:System.Windows.Shapes.Rectangle> auf 500 nach zurückgesetzt der <xref:System.Windows.Media.Animation.DoubleAnimation> endet.  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>   
## <a name="properties-that-control-the-speed-of-a-timeline"></a>Eigenschaften, die die Geschwindigkeit einer Zeitachse steuern  
 Die <xref:System.Windows.Media.Animation.Timeline> -Klasse enthält drei Eigenschaften zum Angeben der Geschwindigkeit:  
  
-   <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> – Gibt die Geschwindigkeit relativ zum übergeordneten Element, an dem die Zeit, für abläuft eine <xref:System.Windows.Media.Animation.Timeline>. Werte größer als eins erhöhen die Geschwindigkeit von der <xref:System.Windows.Media.Animation.Timeline> und seiner untergeordneten <xref:System.Windows.Media.Animation.Timeline> Objekte; Werte zwischen 0 und 1 langsamer. Der Wert 1 gibt an, dass <xref:System.Windows.Media.Animation.Timeline> im Verlauf der Arbeit mit derselben Geschwindigkeit wie das übergeordnete Objekt. Die <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> Einstellung einer Containerzeitachse wirkt sich auf alle untergeordneten <xref:System.Windows.Media.Animation.Timeline> Objekte.  
  
-   <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> – Gibt den Prozentsatz der an die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> einer Zeitachse für das beschleunigen. Ein Beispiel finden Sie unter [wie: beschleunigen oder verlangsamen Sie eine Animation](../../../../docs/framework/wpf/graphics-multimedia/how-to-accelerate-or-decelerate-an-animation.md). 
  
-   <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> -Gibt den Prozentsatz von der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> einer Zeitachse verstrichenen. Ein Beispiel finden Sie unter [wie: beschleunigen oder verlangsamen Sie eine Animation](../../../../docs/framework/wpf/graphics-multimedia/how-to-accelerate-or-decelerate-an-animation.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über das Animations- und Zeitsteuerungssystem](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)  
 [Übersicht über Zeitsteuerungsereignisse](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)  
 [Beispiel zum Verhalten der Animationszeitsteuerung](http://go.microsoft.com/fwlink/?LinkID=159970)
