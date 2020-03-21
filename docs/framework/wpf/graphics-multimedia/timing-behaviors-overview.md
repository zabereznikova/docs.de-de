---
title: Übersicht über Zeitsteuerungsverhalten
ms.date: 03/30/2017
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
ms.openlocfilehash: 3bb42ddd991d3ae1221cc794afdd4aafc74a6046
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145396"
---
# <a name="timing-behaviors-overview"></a>Übersicht über Zeitsteuerungsverhalten
In diesem Thema wird das Timingverhalten von Animationen und anderen <xref:System.Windows.Media.Animation.Timeline> Objekten beschrieben.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Voraussetzungen  
 Als Voraussetzung für dieses Thema sollten Sie mit grundlegenden Animationsfunktionen vertraut sein. Weitere Informationen finden Sie in der [Animationsübersicht](animation-overview.md).  
  
<a name="timelinetypes"></a>
## <a name="timeline-types"></a>Zeitachsentypen  
 A <xref:System.Windows.Media.Animation.Timeline> stellt ein Segment der Zeit dar. Sie bietet Eigenschaften, mit denen Sie z.B. die Länge dieses Abschnitts, seinen Start, die Anzahl der Wiederholungen und die Geschwindigkeit des Fortschreitens der Zeit im Abschnitt Segment angeben.  
  
 Klassen, die von der Timeline-Klasse erben, bieten zusätzliche Funktionen, wie z.B. Animation und Medienwiedergabe. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]stellt die <xref:System.Windows.Media.Animation.Timeline> folgenden Typen bereit.  
  
|Zeitachsentypen|Beschreibung|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|Abstrakte Basisklasse <xref:System.Windows.Media.Animation.Timeline> für Objekte, die Ausgabewerte für animierende Eigenschaften generieren.|  
|<xref:System.Windows.Media.MediaTimeline>|Erzeugt eine Ausgabe aus einer Mediendatei.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|Ein Typ, der <xref:System.Windows.Media.Animation.TimelineGroup> untergeordnete <xref:System.Windows.Media.Animation.Timeline> Objekte gruppiert und steuert.|  
|<xref:System.Windows.Media.Animation.Storyboard>|Ein Typ, der <xref:System.Windows.Media.Animation.ParallelTimeline> Zielinformationen für die darin enthaltenen Zeitleistenobjekte bereitstellt.|  
|<xref:System.Windows.Media.Animation.Timeline>|Abstrakte Basisklasse, die Zeitsteuerungsverhalten definiert.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|Abstrakte Klasse <xref:System.Windows.Media.Animation.Timeline> für Objekte, <xref:System.Windows.Media.Animation.Timeline> die andere Objekte enthalten können.|  
  
<a name="propertiesthatcontroltimelinelength"></a>
## <a name="properties-that-control-the-length-of-a-timeline"></a>Eigenschaften, die die Länge einer Zeitachse steuern  
 A <xref:System.Windows.Media.Animation.Timeline> stellt ein Zeitsegment dar, und die Länge einer Zeitachse kann auf unterschiedliche Weise beschrieben werden. In der folgenden Tabelle werden mehrere Begriffe für die Beschreibung der Länge einer Zeitachse definiert.  
  
|Begriff|Beschreibung|Eigenschaften||||  
|----------|-----------------|----------------|-|-|-|  
|Einfache Dauer|Zeitspanne, die eine Zeitachse für eine Vorwärtsiteration benötigt.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|Eine Wiederholung|Die Zeitdauer, die es dauert, bis eine <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Zeitleiste einmal vorwärts gespielt und, wenn die Eigenschaft wahr ist, einmal rückwärts spielt.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|Aktiver Zeitraum|Die Zeitdauer, die eine Zeitachse benötigt, um alle <xref:System.Windows.Media.Animation.RepeatBehavior> Wiederholungen abzuschließen, die durch ihre Eigenschaft angegeben werden.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>
### <a name="the-duration-property"></a>Duration-Eigenschaft  
 Wie bereits erwähnt, stellt eine Zeitachse einen Zeitabschnitt dar. Die Länge dieses Segments wird durch <xref:System.Windows.Media.Animation.Timeline.Duration%2A>die Zeitachse bestimmt. Wenn eine Zeitachse das Ende ihrer Dauer erreicht, wird die Wiedergabe beendet. Wenn die Zeitachse über untergeordnete Zeitachsen verfügt, wird deren Wiedergabe ebenfalls beendet. Im Fall einer Animation <xref:System.Windows.Media.Animation.Timeline.Duration%2A> gibt der an, wie lange die Animation benötigt, um vom Startwert zum Endwert überzusteigen. Die Dauer einer Zeitachse wird manchmal als *einfache Dauer*bezeichnet, um zwischen der Dauer einer einzelnen Iteration und der Gesamtdauer der Wiedergabe der Animation einschließlich Wiederholungen zu unterscheiden. Sie können eine Dauer mit einem endlichen Zeitwert <xref:System.Windows.Duration.Automatic%2A> <xref:System.Windows.Duration.Forever%2A>oder den Sonderwerten oder angeben. Die Dauer einer Animation sollte <xref:System.Windows.Duration.TimeSpan%2A> in einen Wert aufgelöst werden, damit sie zwischen Werten wechseln kann.  
  
 Das folgende Beispiel <xref:System.Windows.Media.Animation.DoubleAnimation> zeigt <xref:System.Windows.Media.Animation.Timeline.Duration%2A> eine mit einer Zeit von fünf Sekunden.  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 Container-Zeitpläne, <xref:System.Windows.Media.Animation.Storyboard> z. B. <xref:System.Windows.Media.Animation.ParallelTimeline>und <xref:System.Windows.Duration.Automatic%2A>, haben eine Standarddauer von , d. h. sie enden automatisch, wenn das letzte Kind nicht mehr abgespielt wird. Das folgende Beispiel <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Timeline.Duration%2A> zeigt eine, deren Auflösung auf fünf Sekunden, die Länge der Zeit, die alle seine untergeordneten <xref:System.Windows.Media.Animation.DoubleAnimation> Objekte abgeschlossen werden.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 Wenn Sie <xref:System.Windows.Media.Animation.Timeline.Duration%2A> die Containerzeitachse <xref:System.Windows.Duration.TimeSpan%2A> auf einen Wert festlegen, können Sie <xref:System.Windows.Media.Animation.Timeline> erzwingen, länger oder kürzer zu spielen, als die untergeordneten Objekte spielen würden. Wenn Sie <xref:System.Windows.Media.Animation.Timeline.Duration%2A> den Wert auf einen Wert festlegen, der kleiner <xref:System.Windows.Media.Animation.Timeline> als die <xref:System.Windows.Media.Animation.Timeline> Länge der untergeordneten Objekte der Containerzeitachse ist, werden die untergeordneten Objekte nicht mehr abgespielt, wenn die Containerzeitachse dies tut. Im folgenden Beispiel <xref:System.Windows.Media.Animation.Timeline.Duration%2A> wird <xref:System.Windows.Media.Animation.Storyboard> die der der vorherigen Beispiele auf drei Sekunden festgelegt. Daher wird der <xref:System.Windows.Media.Animation.DoubleAnimation> erste Fortschritt nach drei Sekunden beendet, wenn die Breite des Zielrechtecks auf 60 animiert wurde.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>
### <a name="the-repeatbehavior-property"></a>RepeatBehavior-Eigenschaft  
 Die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft <xref:System.Windows.Media.Animation.Timeline> eines steuert, wie oft seine einfache Dauer wiederholt wird. Mithilfe <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> der Eigenschaft können Sie angeben, wie oft <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>die Zeitachse wiedergegeben wird (eine <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A>Iteration ) oder wie lange sie abgespielt werden soll (eine Wiederholung ). In beiden Fällen durchläuft die Animation so viele vollständige Ausführungen, wie für die erforderliche Anzahl oder Dauer nötig. Standardmäßig haben Zeitachsen eine Iterationsanzahl von `1.0`, was bedeutet, dass sie einmal wiedergegeben werden und sich überhaupt nicht wiederholen.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> wird die <xref:System.Windows.Media.Animation.DoubleAnimation> Eigenschaft verwendet, um eine Wiedergabe für die doppelte einfache Dauer zu erstellen, indem eine Iterationsanzahl angegeben wird.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 Im nächsten Beispiel <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> wird die <xref:System.Windows.Media.Animation.DoubleAnimation> Eigenschaft verwendet, um das Spiel für die Hälfte seiner einfachen Dauer zu machen.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 Wenn Sie <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> die Eigenschaft <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>von <xref:System.Windows.Media.Animation.Timeline> a festlegen, werden die Wiederholungen bis zum interaktiven Stopp oder durch das Timingsystem festgelegt. Im folgenden Beispiel <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> wird die <xref:System.Windows.Media.Animation.DoubleAnimation> Eigenschaft verwendet, um das Spiel auf unbestimmte Zeit zu erstellen.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 Ein weiteres Beispiel finden Sie unter [Wiederholen einer Animation](how-to-repeat-an-animation.md).  
  
<a name="autoreverseproperty"></a>
### <a name="the-autoreverse-property"></a>AutoReverse-Eigenschaft  
 Die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft gibt <xref:System.Windows.Media.Animation.Timeline> an, ob eine am Ende jeder Vorwärtsiteration rückwärts abgespielt wird. Im folgenden Beispiel <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> wird die <xref:System.Windows.Media.Animation.DoubleAnimation> `true`Eigenschaft von a an festgelegt. Infolgedessen wird es von Null auf 100 und dann von 100 bis Null animiert. Sie wird insgesamt 10 Sekunden wiedergegeben.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 Wenn Sie <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> einen Wert <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> verwenden, <xref:System.Windows.Media.Animation.Timeline> um <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> die <xref:System.Windows.Media.Animation.Timeline> von `true`a und die Eigenschaft dessen anzugeben, besteht eine einzelne Wiederholung aus einer Vorwärtsiteration gefolgt von einer Rückwärtsiteration.  Im folgenden Beispiel <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> wird <xref:System.Windows.Media.Animation.DoubleAnimation> die des vorherigen <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> Beispiels auf ein von zwei festgelegt. Als Ergebnis spielt <xref:System.Windows.Media.Animation.DoubleAnimation> die für 20 Sekunden: vorwärts für fünf Sekunden, rückwärts für fünf Sekunden, vorwärts für 5 Sekunden wieder, und dann rückwärts für fünf Sekunden.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 Wenn eine Container-Zeitachse untergeordnete <xref:System.Windows.Media.Animation.Timeline> Objekte enthält, werden diese umgekehrt, wenn die Container-Zeitachse dies tut. Weitere Beispiele finden Sie unter [Angeben, ob eine Zeitleiste automatisch umkehrt.](how-to-specify-whether-a-timeline-automatically-reverses.md)  
  
<a name="timelinebegin"></a>
## <a name="the-begintime-property"></a>BeginTime-Eigenschaft  
 Mit <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> der Eigenschaft können Sie angeben, wann eine Zeitachse gestartet wird.  Die Startzeit einer Zeitachse bezieht sich auf die übergeordnete Zeitachse. Eine Anfangszeit von 0 (null) Sekunden bedeutet, dass die Zeitachse gestartet wird, sobald die übergeordnete gestartet wird. Jeder andere Wert erstellt einen Offset zwischen dem Zeitpunkt des Starts der Wiedergabe der übergeordneten Zeitachse und der Wiedergabe der untergeordneten Zeitachse. Beispielsweise bedeutet eine Startzeit von 2 Sekunden, dass die Wiedergabe der Zeitachse gestartet wird, wenn ihre übergeordnete Zeitachse eine Zeit von 2 Sekunden erreicht hat. Standardmäßig haben alle Zeitachsen eine Startzeit von 0 Sekunden. Sie können auch die Anfangszeit `null`einer Zeitachse auf festlegen, wodurch verhindert wird, dass die Zeitachse gestartet wird. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]geben Sie null mit der [x:Null Markup Extension](../../../desktop-wpf/xaml-services/xnull-markup-extension.md)an.  
  
 Beachten Sie, dass die Anfangszeit nicht jedes Mal <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> angewendet wird, wenn eine Zeitachse aufgrund ihrer Einstellung wiederholt wird. Wenn Sie eine Animation mit <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> einer von 10 Sekunden und einer <xref:System.Windows.Media.Animation.RepeatBehavior> von <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>erstellen würden, würde es eine Verzögerung von 10 Sekunden geben, bevor die Animation zum ersten Mal wiedergegeben wird, jedoch nicht für jede aufeinanderfolgende Wiederholung. Soll jedoch die übergeordnete Zeitachse der Animation neu gestartet oder wiederholt werden, tritt die Verzögerung von 10 Sekunden auf.  
  
 Die <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> Eigenschaft ist nützlich für staffelende Zeitachsen. Im folgenden Beispiel <xref:System.Windows.Media.Animation.Storyboard> wird ein <xref:System.Windows.Media.Animation.DoubleAnimation> mit zwei untergeordneten Objekten erstellt. Die erste Animation <xref:System.Windows.Media.Animation.Timeline.Duration%2A> hat eine von fünf <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Sekunden, die zweite 3 Sekunden. Das Beispiel <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> legt die <xref:System.Windows.Media.Animation.DoubleAnimation> Sekunde auf 5 Sekunden fest, <xref:System.Windows.Media.Animation.DoubleAnimation> sodass sie nach dem ersten Ende mit der Wiedergabe beginnt.  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>
## <a name="the-fillbehavior-property"></a>FillBehavior-Eigenschaft  
 Wenn <xref:System.Windows.Media.Animation.Timeline> a das Ende seiner gesamten <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> aktiven Dauer erreicht, gibt die Eigenschaft an, ob sie ihren letzten Wert beendet oder hält. Eine Animation <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> mit <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> einem von "holds" its output value: Die animierte Eigenschaft behält den letzten Wert der Animation bei. Ein Wert <xref:System.Windows.Media.Animation.FillBehavior.Stop> von Ursachen, aus denen die Animation ihre Zieleigenschaft nach dem Ende nicht mehr beeinflusst.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.Storyboard> wird ein <xref:System.Windows.Media.Animation.DoubleAnimation> mit zwei untergeordneten Objekten erstellt. Beide <xref:System.Windows.Media.Animation.DoubleAnimation> Objekte <xref:System.Windows.FrameworkElement.Width%2A> animieren die <xref:System.Windows.Shapes.Rectangle> von 0 bis 100. Die <xref:System.Windows.Shapes.Rectangle> Elemente haben <xref:System.Windows.FrameworkElement.Width%2A> nicht animierte Werte von 500 [geräteunabhängige Pixel].  
  
- Die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft der <xref:System.Windows.Media.Animation.DoubleAnimation> ersten <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>ist auf , den Standardwert festgelegt. Daher bleibt die Breite des Rechtecks nach den <xref:System.Windows.Media.Animation.DoubleAnimation> Enden bei 100.  
  
- Die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft der <xref:System.Windows.Media.Animation.DoubleAnimation> zweiten <xref:System.Windows.Media.Animation.FillBehavior.Stop>ist auf festgelegt. Als Ergebnis wird <xref:System.Windows.FrameworkElement.Width%2A> die <xref:System.Windows.Shapes.Rectangle> der zweiten auf 500 <xref:System.Windows.Media.Animation.DoubleAnimation> nach den Enden zurückgesetzt.  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>
## <a name="properties-that-control-the-speed-of-a-timeline"></a>Eigenschaften, die die Geschwindigkeit einer Zeitachse steuern  
 Die <xref:System.Windows.Media.Animation.Timeline> Klasse stellt drei Eigenschaften zum Angeben ihrer Geschwindigkeit bereit:  
  
- <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>– Gibt diese Rate relativ zu ihrem übergeordneten Element <xref:System.Windows.Media.Animation.Timeline>an, zu dem der Zeitpunkt für eine fortschreitet. Werte größer als eins <xref:System.Windows.Media.Animation.Timeline> erhöhen die <xref:System.Windows.Media.Animation.Timeline> Geschwindigkeit der und ihrer untergeordneten Objekte; Werte zwischen Null und eins verlangsamen ihn. Ein Wert von <xref:System.Windows.Media.Animation.Timeline> 1 gibt an, dass der Wert mit der gleichen Rate wie das übergeordnete Element fortschreitet. Die <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> Einstellung einer Containerzeitachse wirkt <xref:System.Windows.Media.Animation.Timeline> sich auch auf alle untergeordneten Objekte aus.  
  
- <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A>– Gibt den Prozentsatz <xref:System.Windows.Media.Animation.Timeline.Duration%2A> der Zeitachse an, die für die Beschleunigung ausgegeben wurde. Ein Beispiel finden Sie unter [Gewusst wie: Beschleunigen oder Verlangsamen einer Animation](how-to-accelerate-or-decelerate-an-animation.md).
  
- <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>- Gibt den Prozentsatz <xref:System.Windows.Media.Animation.Timeline.Duration%2A> der Zeitleiste an, die für die Verlangsamung ausgegeben wurde. Ein Beispiel finden Sie unter [Gewusst wie: Beschleunigen oder Verlangsamen einer Animation](how-to-accelerate-or-decelerate-an-animation.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über das Animations- und Zeitsteuerungssystem](animation-and-timing-system-overview.md)
- [Übersicht über Zeitsteuerungsereignisse](timing-events-overview.md)
- [How-to-Themen](animation-and-timing-how-to-topics.md)
- [Beispiel zum Verhalten der Animationszeitsteuerung](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
