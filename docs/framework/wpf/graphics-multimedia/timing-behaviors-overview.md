---
title: Übersicht über Zeitsteuerungsverhalten
ms.date: 03/30/2017
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
ms.openlocfilehash: a85f980a0cefaa282e9e92d533a2306a9009e3e7
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559949"
---
# <a name="timing-behaviors-overview"></a>Übersicht über Zeitsteuerungsverhalten
In diesem Thema wird das Zeit Steuerungs Verhalten von Animationen und anderen <xref:System.Windows.Media.Animation.Timeline> Objekten beschrieben.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Als Voraussetzung für dieses Thema sollten Sie mit grundlegenden Animationsfunktionen vertraut sein. Weitere Informationen finden Sie unter [Übersicht über Animationen](animation-overview.md).  
  
<a name="timelinetypes"></a>   
## <a name="timeline-types"></a>Zeitachsentypen  
 Ein-<xref:System.Windows.Media.Animation.Timeline> der einen Zeitabschnitt darstellt. Sie bietet Eigenschaften, mit denen Sie z.B. die Länge dieses Abschnitts, seinen Start, die Anzahl der Wiederholungen und die Geschwindigkeit des Fortschreitens der Zeit im Abschnitt Segment angeben.  
  
 Klassen, die von der Timeline-Klasse erben, bieten zusätzliche Funktionen, wie z.B. Animation und Medienwiedergabe. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt die folgenden <xref:System.Windows.Media.Animation.Timeline> Typen bereit.  
  
|Zeitachsentypen|Beschreibung|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|Eine abstrakte Basisklasse für <xref:System.Windows.Media.Animation.Timeline> Objekte, die Ausgabewerte zum Animieren von Eigenschaften generieren.|  
|<xref:System.Windows.Media.MediaTimeline>|Erzeugt eine Ausgabe aus einer Mediendatei.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|Ein Typ von <xref:System.Windows.Media.Animation.TimelineGroup>, der untergeordnete <xref:System.Windows.Media.Animation.Timeline> Objekte gruppiert und steuert.|  
|<xref:System.Windows.Media.Animation.Storyboard>|Ein Typ von <xref:System.Windows.Media.Animation.ParallelTimeline>, der Ziel Informationen für die in ihm enthaltenen Zeitachsen Objekte bereitstellt.|  
|<xref:System.Windows.Media.Animation.Timeline>|Abstrakte Basisklasse, die Zeitsteuerungsverhalten definiert.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|Abstrakte Klasse für <xref:System.Windows.Media.Animation.Timeline> Objekte, die andere <xref:System.Windows.Media.Animation.Timeline> Objekte enthalten können.|  
  
<a name="propertiesthatcontroltimelinelength"></a>   
## <a name="properties-that-control-the-length-of-a-timeline"></a>Eigenschaften, die die Länge einer Zeitachse steuern  
 Ein <xref:System.Windows.Media.Animation.Timeline> der einen Zeitabschnitt darstellt, und die Länge einer Zeitachse kann auf unterschiedliche Weise beschrieben werden. In der folgenden Tabelle werden mehrere Begriffe für die Beschreibung der Länge einer Zeitachse definiert.  
  
|Begriff|Beschreibung|Eigenschaften||||  
|----------|-----------------|----------------|-|-|-|  
|Einfache Dauer|Zeitspanne, die eine Zeitachse für eine Vorwärtsiteration benötigt.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|Eine Wiederholung|Die Zeitspanne, die für die Wiedergabe einer Zeitachse benötigt wird, und, wenn die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>-Eigenschaft den Wert true hat, wird einmal rückwärts gespielt.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|Aktiver Zeitraum|Die Zeitspanne, die eine Zeitachse benötigt, um alle Wiederholungen abzuschließen, die von der <xref:System.Windows.Media.Animation.RepeatBehavior>-Eigenschaft angegeben werden.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>ist <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>ist <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>   
### <a name="the-duration-property"></a>Duration-Eigenschaft  
 Wie bereits erwähnt, stellt eine Zeitachse einen Zeitabschnitt dar. Die Länge dieses Segments wird durch die <xref:System.Windows.Media.Animation.Timeline.Duration%2A>der Zeitachse bestimmt. Wenn eine Zeitachse das Ende ihrer Dauer erreicht, wird die Wiedergabe beendet. Wenn die Zeitachse über untergeordnete Zeitachsen verfügt, wird deren Wiedergabe ebenfalls beendet. Im Fall einer Animation gibt der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> an, wie lange die Animation für den Übergang vom Startwert zum Endwert benötigt. Die Dauer einer Zeitachse wird manchmal als *einfache Dauer*bezeichnet, um zwischen der Dauer einer einzelnen Iteration und der Gesamtdauer der Wiedergabe der Animation einschließlich Wiederholungen zu unterscheiden. Sie können eine Dauer mithilfe eines begrenzten Uhrzeitwerts oder der besonderen Werte <xref:System.Windows.Duration.Automatic%2A> oder <xref:System.Windows.Duration.Forever%2A>angeben. Die Dauer einer Animation sollte in einen <xref:System.Windows.Duration.TimeSpan%2A> Wert aufgelöst werden, sodass Sie zwischen den Werten wechseln kann.  
  
 Das folgende Beispiel zeigt eine <xref:System.Windows.Media.Animation.DoubleAnimation> mit einer <xref:System.Windows.Media.Animation.Timeline.Duration%2A> von fünf Sekunden.  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 Container Zeitachsen, wie <xref:System.Windows.Media.Animation.Storyboard> und <xref:System.Windows.Media.Animation.ParallelTimeline>, haben eine Standarddauer von <xref:System.Windows.Duration.Automatic%2A>. Dies bedeutet, dass Sie automatisch beendet werden, wenn das letzte untergeordnete Element beendet wird. Das folgende Beispiel zeigt eine <xref:System.Windows.Media.Animation.Storyboard>, deren <xref:System.Windows.Media.Animation.Timeline.Duration%2A> in fünf Sekunden aufgelöst wird, die Zeitspanne, die alle untergeordneten <xref:System.Windows.Media.Animation.DoubleAnimation>-Objekte vollständig benötigt.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 Durch Festlegen des <xref:System.Windows.Media.Animation.Timeline.Duration%2A> einer Container Zeitachse auf einen <xref:System.Windows.Duration.TimeSpan%2A> Wert können Sie erzwingen, dass die Wiedergabe länger oder kürzer ist als die untergeordneten <xref:System.Windows.Media.Animation.Timeline> Objekte wiedergegeben werden. Wenn Sie die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> auf einen Wert festlegen, der kleiner als die Länge der untergeordneten <xref:System.Windows.Media.Animation.Timeline> Objekte der Container Zeitachse ist, wird die Wiedergabe der untergeordneten <xref:System.Windows.Media.Animation.Timeline> Objekte beendet, wenn die Container Zeitachse funktioniert. Im folgenden Beispiel wird der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> der <xref:System.Windows.Media.Animation.Storyboard> aus den vorangehenden Beispielen auf drei Sekunden festgelegt. Folglich wird der erste <xref:System.Windows.Media.Animation.DoubleAnimation> nach drei Sekunden nicht mehr fortgesetzt, wenn die Breite des Ziel Rechtecks auf 60 animiert wurde.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>   
### <a name="the-repeatbehavior-property"></a>RepeatBehavior-Eigenschaft  
 Die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>-Eigenschaft einer <xref:System.Windows.Media.Animation.Timeline> steuert, wie oft die einfache Dauer wiederholt wird. Mithilfe der <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>-Eigenschaft können Sie angeben, wie oft die Zeitachse wiedergegeben wird (eine Iterations <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>) oder wie lange die Zeit wiedergegeben werden soll (eine Wiederholung <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A>). In beiden Fällen durchläuft die Animation so viele vollständige Ausführungen, wie für die erforderliche Anzahl oder Dauer nötig. Standardmäßig haben Zeitachsen eine Iterations Anzahl von `1.0`. Dies bedeutet, dass Sie einmal abgespielt werden und nicht wiederholt werden.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>-Eigenschaft verwendet, um eine <xref:System.Windows.Media.Animation.DoubleAnimation> für die doppelte Dauer wiederzugeben, indem eine Iterations Anzahl angegeben wird.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 Im nächsten Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>-Eigenschaft verwendet, um die <xref:System.Windows.Media.Animation.DoubleAnimation> für eine halbe einfache Dauer wiederzugeben.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 Wenn Sie die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>-Eigenschaft einer <xref:System.Windows.Media.Animation.Timeline> auf <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>festlegen, wird die <xref:System.Windows.Media.Animation.Timeline> wiederholt, bis Sie interaktiv oder über das Zeit Steuerungssystem beendet wird. Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>-Eigenschaft verwendet, um die <xref:System.Windows.Media.Animation.DoubleAnimation> auf unbestimmte Zeit wiederzugeben.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 Ein weiteres Beispiel finden Sie unter [Wiederholen einer Animation](how-to-repeat-an-animation.md).  
  
<a name="autoreverseproperty"></a>   
### <a name="the-autoreverse-property"></a>AutoReverse-Eigenschaft  
 Die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>-Eigenschaft gibt an, ob ein <xref:System.Windows.Media.Animation.Timeline> am Ende jeder Forward-Iterationen rückwärts wiedergegeben wird. Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>-Eigenschaft eines <xref:System.Windows.Media.Animation.DoubleAnimation> auf `true`festgelegt. Daher wird die Animation von 0 bis 100 und von 100 bis 0 (null) animiert. Sie wird insgesamt 10 Sekunden wiedergegeben.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 Wenn Sie einen <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> Wert verwenden, um die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> eines <xref:System.Windows.Media.Animation.Timeline> anzugeben, und die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>-Eigenschaft dieses <xref:System.Windows.Media.Animation.Timeline> `true`ist, besteht eine einzelne Wiederholung aus einer vorwärts Iterations Folge, auf die eine rückwärts iterierung folgt.  Im folgenden Beispiel wird der <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> der <xref:System.Windows.Media.Animation.DoubleAnimation> aus dem vorherigen Beispiel auf einen <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> von zwei festgelegt. Folglich wird der <xref:System.Windows.Media.Animation.DoubleAnimation> 20 Sekunden lang wiederholt: fünf Sekunden lang rückwärts, 5 Sekunden lang vorwärts und dann fünf Sekunden rückwärts.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 Wenn eine Container Zeitachse über untergeordnete <xref:System.Windows.Media.Animation.Timeline> Objekte verfügt, werden Sie bei der Container Zeitachse umkehren. Weitere Beispiele finden Sie unter Geben Sie an, [ob eine Zeitachse automatisch umgekehrt](how-to-specify-whether-a-timeline-automatically-reverses.md)wird.  
  
<a name="timelinebegin"></a>   
## <a name="the-begintime-property"></a>BeginTime-Eigenschaft  
 Mit der <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>-Eigenschaft können Sie angeben, wann eine Zeitachse gestartet wird.  Die Startzeit einer Zeitachse bezieht sich auf die übergeordnete Zeitachse. Eine Anfangszeit von 0 (null) Sekunden bedeutet, dass die Zeitachse gestartet wird, sobald die übergeordnete gestartet wird. Jeder andere Wert erstellt einen Offset zwischen dem Zeitpunkt des Starts der Wiedergabe der übergeordneten Zeitachse und der Wiedergabe der untergeordneten Zeitachse. Beispielsweise bedeutet eine Startzeit von 2 Sekunden, dass die Wiedergabe der Zeitachse gestartet wird, wenn ihre übergeordnete Zeitachse eine Zeit von 2 Sekunden erreicht hat. Standardmäßig haben alle Zeitachsen eine Startzeit von 0 Sekunden. Sie können auch die Startzeit einer Zeitachse auf `null`festlegen, wodurch verhindert wird, dass die Zeitachse gestartet wird. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]geben Sie mithilfe der [x:Null-Markuperweiterung](../../../desktop-wpf/xaml-services/xnull-markup-extension.md)NULL an.  
  
 Beachten Sie, dass die Anfangszeit nicht jedes Mal angewendet wird, wenn eine Zeitachse aufgrund ihrer <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Einstellung wiederholt wird. Wenn Sie eine Animation mit einer <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> von 10 Sekunden und einer <xref:System.Windows.Media.Animation.RepeatBehavior> <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>erstellen möchten, liegt eine Verzögerung von 10 Sekunden vor, bevor die Animation zum ersten Mal wiedergegeben wird, jedoch nicht für jede nachfolgende Wiederholung. Soll jedoch die übergeordnete Zeitachse der Animation neu gestartet oder wiederholt werden, tritt die Verzögerung von 10 Sekunden auf.  
  
 Die <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>-Eigenschaft eignet sich für die Staffelung von Zeitachsen. Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.Storyboard> erstellt, die über zwei untergeordnete <xref:System.Windows.Media.Animation.DoubleAnimation>-Objekte verfügt. Die erste Animation weist eine <xref:System.Windows.Media.Animation.Timeline.Duration%2A> von fünf Sekunden auf, die zweite <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 3 Sekunden. Im Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> des zweiten <xref:System.Windows.Media.Animation.DoubleAnimation> auf 5 Sekunden festgelegt, sodass die Wiedergabe beginnt, nachdem die erste <xref:System.Windows.Media.Animation.DoubleAnimation> endet.  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>   
## <a name="the-fillbehavior-property"></a>FillBehavior-Eigenschaft  
 Wenn ein <xref:System.Windows.Media.Animation.Timeline> das Ende seiner gesamten aktiven Dauer erreicht, gibt die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>-Eigenschaft an, ob Sie den letzten Wert beendet oder enthält. Eine Animation mit einer <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> "enthält" ihren Ausgabewert: die zu animierende Eigenschaft behält den letzten Wert der Animation bei. Der Wert <xref:System.Windows.Media.Animation.FillBehavior.Stop> bewirkt, dass der Animations Vorgang seine Ziel Eigenschaft nicht mehr beeinträchtigt, nachdem er beendet wurde.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.Storyboard> erstellt, die über zwei untergeordnete <xref:System.Windows.Media.Animation.DoubleAnimation>-Objekte verfügt. Beide <xref:System.Windows.Media.Animation.DoubleAnimation> Objekte animieren die <xref:System.Windows.FrameworkElement.Width%2A> eines <xref:System.Windows.Shapes.Rectangle> von 0 bis 100. Die <xref:System.Windows.Shapes.Rectangle> Elemente haben nicht animierte <xref:System.Windows.FrameworkElement.Width%2A> Werte von 500 [geräteunabhängige Pixel].  
  
- Die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>-Eigenschaft des ersten <xref:System.Windows.Media.Animation.DoubleAnimation> wird auf <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, den Standardwert, festgelegt. Folglich bleibt die Breite des Rechtecks bei 100, nachdem die <xref:System.Windows.Media.Animation.DoubleAnimation> endet.  
  
- Die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>-Eigenschaft des zweiten <xref:System.Windows.Media.Animation.DoubleAnimation> ist auf <xref:System.Windows.Media.Animation.FillBehavior.Stop>festgelegt. Demzufolge wird der <xref:System.Windows.FrameworkElement.Width%2A> des zweiten <xref:System.Windows.Shapes.Rectangle> nach Ende der <xref:System.Windows.Media.Animation.DoubleAnimation> auf 500 zurückgesetzt.  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>   
## <a name="properties-that-control-the-speed-of-a-timeline"></a>Eigenschaften, die die Geschwindigkeit einer Zeitachse steuern  
 Die <xref:System.Windows.Media.Animation.Timeline>-Klasse stellt drei Eigenschaften zum Angeben der Geschwindigkeit bereit:  
  
- <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> – gibt die Rate an, die relativ zum übergeordneten Element ist, zu dem die Zeit für einen <xref:System.Windows.Media.Animation.Timeline>fortschreitet. Werte, die größer als 1 sind, erhöhen die Geschwindigkeit der <xref:System.Windows.Media.Animation.Timeline> und der untergeordneten <xref:System.Windows.Media.Animation.Timeline> Objekte. Werte zwischen 0 und 1 verlangsamen diese. Der Wert 1 gibt an, dass <xref:System.Windows.Media.Animation.Timeline> mit derselben Rate wie das übergeordnete Element fortschreitet. Die <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> Einstellung einer Container Zeitachse wirkt sich auch auf alle untergeordneten <xref:System.Windows.Media.Animation.Timeline> Objekte aus.  
  
- <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> – gibt den Prozentsatz der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> einer Zeitspanne an, die für die Beschleunigung aufgewendet wurde. Ein Beispiel finden Sie unter Gewusst [wie: beschleunigen oder verlangsamen einer Animation](how-to-accelerate-or-decelerate-an-animation.md). 
  
- <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>: gibt den Prozentsatz der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> einer Zeitachse an, die für die Verlangsamung aufgewendet wurde. Ein Beispiel finden Sie unter Gewusst [wie: beschleunigen oder verlangsamen einer Animation](how-to-accelerate-or-decelerate-an-animation.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über das Animations- und Zeitsteuerungssystem](animation-and-timing-system-overview.md)
- [Übersicht über Zeitsteuerungsereignisse](timing-events-overview.md)
- [Gewusst wie-Themen](animation-and-timing-how-to-topics.md)
- [Beispiel zum Verhalten der Animationszeitsteuerung](https://go.microsoft.com/fwlink/?LinkID=159970)
