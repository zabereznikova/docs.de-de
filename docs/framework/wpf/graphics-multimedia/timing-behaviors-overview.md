---
title: "&#220;bersicht &#252;ber Zeitsteuerungsverhalten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Verhalten, Planen"
  - "Zeitsteuerungsverhalten"
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# &#220;bersicht &#252;ber Zeitsteuerungsverhalten
In diesem Thema wird das Zeitsteuerungsverhalten von Animationen und anderen <xref:System.Windows.Media.Animation.Timeline>\-Objekten beschrieben.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 Für dieses Thema sollten Sie mit grundlegenden Animationsfeatures vertraut sein.  Weitere Informationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="timelinetypes"></a>   
## Zeitachsentypen  
 Eine <xref:System.Windows.Media.Animation.Timeline> stellt einen Zeitabschnitt dar.  Sie stellt Eigenschaften bereit, mit denen Sie für das jeweilige Zeitsegment die Länge, den Zeitpunkt des Starts, die Anzahl der Wiederholungen, wie schnell die Zeit durchlaufen wird und vieles mehr festlegen können.  
  
 Klassen, die von der Zeitachsenklasse erben, stellen zusätzliche Funktionen bereit, z. B. Animation und Medienwiedergabe.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt die folgenden <xref:System.Windows.Media.Animation.Timeline>\-Typen zur Verfügung.  
  
|Zeitachsentyp|Beschreibung|  
|-------------------|------------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|Abstrakte Basisklasse für <xref:System.Windows.Media.Animation.Timeline>\-Objekte, die Ausgabewerte für das Animieren von Eigenschaften generieren.|  
|<xref:System.Windows.Media.MediaTimeline>|Generiert eine Ausgabe aus einer Mediendatei.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|Ein <xref:System.Windows.Media.Animation.TimelineGroup>\-Typ, der untergeordnete <xref:System.Windows.Media.Animation.Timeline>\-Objekte gruppiert und steuert.|  
|<xref:System.Windows.Media.Animation.Storyboard>|Ein <xref:System.Windows.Media.Animation.ParallelTimeline>\-Typ, durch den Zielinformationen für die in ihm enthaltenen Zeitachsenobjekte zur Verfügung gestellt werden.|  
|<xref:System.Windows.Media.Animation.Timeline>|Abstrakte Basisklasse, die Zeitsteuerungsverhalten definiert.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|Abstrakte Klasse für <xref:System.Windows.Media.Animation.Timeline>\-Objekte, die andere <xref:System.Windows.Media.Animation.Timeline>\-Objekte enthalten können.|  
  
<a name="propertiesthatcontroltimelinelength"></a>   
## Eigenschaften, die die Länge einer Zeitachse steuern  
 Eine <xref:System.Windows.Media.Animation.Timeline> stellt einen Zeitabschnitt dar. Die Länge einer Zeitachse kann auf verschiedene Arten beschrieben werden.  In der folgenden Tabelle werden mehrere Begriffe für die Beschreibung der Länge einer Zeitachse definiert.  
  
|Begriff|Beschreibung|Eigenschaften||||  
|-------------|------------------|-------------------|-|-|-|  
|Einfache Dauer|Die Zeit, die eine Zeitachse benötigt, um eine einzelne Vorwärtsiteration auszuführen.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|Eine Wiederholung|Die Zeit, die eine Zeitachse benötigt, um einmal vorwärts und, wenn der Wert der <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>\-Eigenschaft True ist, einmal rückwärts abgespielt zu werden.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|Aktiver Zeitraum|Die Zeit, die eine Zeitachse benötigt, um alle Wiederholungen abzuschließen, die von ihrer <xref:System.Windows.Media.Animation.RepeatBehavior>\-Eigenschaft festgelegt sind.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>   
### Duration\-Eigenschaft  
 Wie bereits erwähnt stellt ein Timeline\-Objekt einen Zeitabschnitt dar.  Die Länge dieses Abschnitts wird von der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> der Zeitachse bestimmt.  Wenn eine Zeitachse das Ende ihrer Dauer erreicht, wird ihre Wiedergabe beendet.  Wenn die Zeitachse über untergeordnete Zeitachsen verfügt, wird deren Wiedergabe ebenfalls beendet.  Bei einer Animation gibt die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> an, wie viel Zeit die Animation für den Übergang vom Startwert zum Endwert benötigt.  Die Dauer einer Zeitachse wird manchmal auch als deren *einfache Dauer* bezeichnet, um zwischen der Dauer einer einzelnen Iteration und der gesamten Wiedergabedauer der Animation einschließlich Wiederholungen zu unterscheiden.  Sie können eine Dauer mit einem endlichen Zeitwert oder den speziellen Werten <xref:System.Windows.Duration.Automatic%2A> oder <xref:System.Windows.Duration.Forever%2A> angeben.  Die Dauer einer Animation sollte in einen <xref:System.Windows.Duration.TimeSpan%2A>\-Wert aufgelöst werden, damit sie einen Übergang zwischen den Werten ausführen kann.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> mit einer <xref:System.Windows.Media.Animation.Timeline.Duration%2A> von fünf Sekunden veranschaulicht.  
  
  
  
 Containerzeitachsen wie <xref:System.Windows.Media.Animation.Storyboard> und <xref:System.Windows.Media.Animation.ParallelTimeline> verfügen standardmäßig über die Dauer <xref:System.Windows.Duration.Automatic%2A>. Das heißt, sie enden automatisch, sobald die Wiedergabe ihres letzten untergeordneten Elements beendet ist.  Im folgenden Beispiel wird ein <xref:System.Windows.Media.Animation.Storyboard> veranschaulicht, dessen <xref:System.Windows.Media.Animation.Timeline.Duration%2A> in fünf Sekunden aufgelöst wird. Diese Zeit wird benötigt, bis alle untergeordneten <xref:System.Windows.Media.Animation.DoubleAnimation>\-Objekte abgeschlossen sind.  
  
  
  
 Indem Sie für die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> einer Containerzeitachse einen <xref:System.Windows.Duration.TimeSpan%2A>\-Wert festlegen, können Sie erzwingen, dass die Abspielzeit der Containerzeitachse länger oder kürzer ist, als die ihrer untergeordneten <xref:System.Windows.Media.Animation.Timeline>\-Objekte.  Wenn Sie für die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> einen Wert festlegen, der kleiner ist als die Länge der untergeordneten <xref:System.Windows.Media.Animation.Timeline>\-Objekte der Containerzeitachse, wird die Wiedergabe der untergeordneten <xref:System.Windows.Media.Animation.Timeline>\-Objekte zum selben Zeitpunkt beendet wie die Wiedergabe der Containerzeitachse.  Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> für das <xref:System.Windows.Media.Animation.Storyboard> aus den vorangehenden Beispielen auf drei Sekunden festgelegt.  Dadurch wird die erste <xref:System.Windows.Media.Animation.DoubleAnimation> nach drei Sekunden angehalten, sobald sie die Breite des Zielrechtecks auf 60 animiert hat.  
  
  
  
<a name="repeatinganimations"></a>   
### RepeatBehavior\-Eigenschaft  
 Die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>\-Eigenschaft einer <xref:System.Windows.Media.Animation.Timeline> legt fest, wie oft diese ihre einfache Dauer wiederholt.  Mithilfe der <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>\-Eigenschaft können Sie festlegen, wie oft \(Iteration\-<xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>\) oder wie lange \(Wiederholungs\-<xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A> eine Zeitachse insgesamt wiedergegeben wird.  In beiden Fällen wird die Animation so oft von Anfang bis Ende wiederholt, bis die Vorgaben für die Anzahl bzw. die Zeit der Wiederholungsläufe erfüllt sind.  Die Standardeinstellung der Iterationen von Zeitachsen ist `1.0`, d. h. sie wird einmal abgespielt und nicht wiederholt.  
  
 Im nächsten Beispiel wird mithilfe der <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>\-Eigenschaft ein Iterationszähler festgelegt, damit die <xref:System.Windows.Media.Animation.DoubleAnimation> doppelt so lang wie ihre einfache Dauer wiedergegeben wird.  
  
  
  
 Im nächsten Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>\-Eigenschaft verwendet, damit die <xref:System.Windows.Media.Animation.DoubleAnimation> nur zur Hälfte ihrer einfachen Dauer wiedergegeben wird.  
  
  
  
 Wenn Sie die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>\-Eigenschaft einer <xref:System.Windows.Media.Animation.Timeline> auf <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A> festlegen, wird die <xref:System.Windows.Media.Animation.Timeline> unbegrenzt wiederholt, bis ihre Wiedergabe interaktiv oder durch das Zeitsteuerungssystem beendet wird.  Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>\-Eigenschaft verwendet, damit die <xref:System.Windows.Media.Animation.DoubleAnimation> unbegrenzt wiederholt wird.  
  
  
  
 Ein zusätzliches Beispiel finden Sie unter [Wiederholen einer Animation](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md).  
  
<a name="autoreverseproperty"></a>   
### AutoReverse\-Eigenschaft  
 Die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>\-Eigenschaft gibt an, ob eine <xref:System.Windows.Media.Animation.Timeline> am Ende jeder Vorwärtsiteration rückwärts wiedergegeben wird.  Im folgenden Beispiel wird für die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>\-Eigenschaft einer <xref:System.Windows.Media.Animation.DoubleAnimation> der Wert `true` festgelegt. Dadurch wird sie von 0 zu 100 und anschließend von 100 zu 0 animiert.  Sie wird insgesamt 10 Sekunden lang abgespielt.  
  
  
  
 Wenn Sie einen <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>\-Wert verwenden, um das <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> einer <xref:System.Windows.Media.Animation.Timeline> festzulegen und für die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>\-Eigenschaft dieser <xref:System.Windows.Media.Animation.Timeline> der Wert `true` festgelegt ist, besteht eine einzelne Wiederholung aus einer Vorwärtsiteration gefolgt von einer Rückwärtsiteration.  Im folgenden Beispiel wird für das <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> der <xref:System.Windows.Media.Animation.DoubleAnimation> aus dem vorangehenden Beispiel eine <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> von zwei festgelegt.  Dadurch wird die <xref:System.Windows.Media.Animation.DoubleAnimation> 20 Sekunden lang abgespielt: fünf Sekunden vorwärts, fünf Sekunden rückwärts, erneut fünf Sekunden vorwärts und schließlich erneut fünf Sekunden rückwärts.  
  
  
  
 Wenn eine Containerzeitachse über untergeordnete <xref:System.Windows.Media.Animation.Timeline>\-Objekte verfügt, ändert sich deren Wiedergaberichtung parallel zur Wiedergaberichtung der Containerzeitachse.  Weitere Beispiele finden Sie unter [Festlegen, ob eine Zeitachse automatisch umgekehrt wird](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md).  
  
<a name="timelinebegin"></a>   
## BeginTime\-Eigenschaft  
 Mit der <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>\-Eigenschaft können Sie angeben, wann eine Zeitachse beginnt.  Die Anfangszeit einer Zeitachse ist zu ihrer übergeordneten Zeitachse relativ.  Eine Anfangszeit von 0 \(null\) Sekunden bedeutet, dass die Zeitachse zeitgleich mit ihrer übergeordneten Zeitachse beginnt. Jeder andere Wert bewirkt eine Verschiebung zwischen den Zeitpunkten, zu denen die Wiedergabe der übergeordneten und die der untergeordneten Zeitachse beginnt.  Bei einer Anfangszeit von zwei Sekunden beginnt die Wiedergabe der Zeitachse, sobald ihre übergeordnete Zeitachse die Dauer von zwei Sekunden überschritten hat.  Standardmäßig haben alle Zeitachsen eine Anfangszeit von 0 \(null\) Sekunden.  Sie können als Anfangszeit einer Zeitachse auch `null` festlegen. Dadurch wird verhindert, dass die Zeitachse beginnt.  In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird NULL mithilfe der [x:Null\-Markuperweiterung](../../../../docs/framework/xaml-services/x-null-markup-extension.md) angegeben.  
  
 Beachten Sie, dass die Anfangszeit nicht jedes Mal erneut angewendet wird, wenn eine Zeitachse aufgrund ihrer <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>\-Einstellung wiederholt wird.  Wenn Sie eine Animation mit einer <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> von zehn Sekunden erstellen und für das <xref:System.Windows.Media.Animation.RepeatBehavior> den Wert <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A> festlegen, gibt es vor der ersten Wiedergabe der Animation eine Verzögerung von zehn Sekunden, bei den darauf folgenden Wiederholungen jedoch nicht.  Wenn die übergeordnete Zeitachse der Animation jedoch neu gestartet oder wiederholt wird, tritt diese zehn Sekunden lange Verzögerung auf.  
  
 Die <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>\-Eigenschaft eignet sich für die Staffelung von Zeitachsen.  Im folgenden Beispiel wird ein <xref:System.Windows.Media.Animation.Storyboard> erstellt, das über zwei untergeordnete <xref:System.Windows.Media.Animation.DoubleAnimation>\-Objekte verfügt.  Die erste Animation verfügt über eine <xref:System.Windows.Media.Animation.Timeline.Duration%2A> von fünf Sekunden, die zweite über eine <xref:System.Windows.Media.Animation.Timeline.Duration%2A> von drei Sekunden.  Im Beispiel wird die <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> der zweiten <xref:System.Windows.Media.Animation.DoubleAnimation> auf fünf Sekunden festgelegt, sodass die Wiedergabe beginnt, sobald die erste <xref:System.Windows.Media.Animation.DoubleAnimation> beendet ist.  
  
  
  
<a name="fillbehaviorproperty"></a>   
## FillBehavior\-Eigenschaft  
 Wenn eine <xref:System.Windows.Media.Animation.Timeline> das Ende ihrer gesamten Aktivitätsdauer erreicht, bestimmt die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>\-Eigenschaft, ob sie beendet wird oder ihren letzten Wert beibehält.  Eine Animation mit einem <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> von <xref:System.Windows.Media.Animation.FillBehavior> "behält" ihren Ausgabewert: Die animierte Eigenschaft behält den letzten Wert der Animation bei.  Ein Wert von <xref:System.Windows.Media.Animation.FillBehavior> bewirkt, dass das Beenden der Animation keine Auswirkungen auf ihre Zieleigenschaft hat.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.Animation.Storyboard> erstellt, das über zwei untergeordnete <xref:System.Windows.Media.Animation.DoubleAnimation>\-Objekte verfügt.  Beide <xref:System.Windows.Media.Animation.DoubleAnimation>\-Objekte animieren die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft für ein <xref:System.Windows.Shapes.Rectangle>\-Element von 0 zu 100.  Die <xref:System.Windows.Shapes.Rectangle>\-Elemente verfügen über nicht animierte <xref:System.Windows.FrameworkElement.Width%2A>\-Werte von 500 [geräteunabhängigen Pixeln](GTMT).  
  
-   Die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>\-Eigenschaft der ersten <xref:System.Windows.Media.Animation.DoubleAnimation> wird auf den Standardwert <xref:System.Windows.Media.Animation.FillBehavior> festgelegt.  Dadurch bleibt der Wert für die Breite des Rechtecks bei 100, sobald die <xref:System.Windows.Media.Animation.DoubleAnimation> beendet wird.  
  
-   Die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>\-Eigenschaft der zweiten <xref:System.Windows.Media.Animation.DoubleAnimation> wird auf <xref:System.Windows.Media.Animation.FillBehavior> festgelegt.  Dadurch wird die <xref:System.Windows.FrameworkElement.Width%2A> für das zweite <xref:System.Windows.Shapes.Rectangle> auf den Wert 500 zurückgesetzt, sobald die <xref:System.Windows.Media.Animation.DoubleAnimation> beendet wird.  
  
  
  
<a name="speedproperties"></a>   
## Eigenschaften, die die Geschwindigkeit einer Zeitachse steuern  
 Die <xref:System.Windows.Media.Animation.Timeline>\-Klasse stellt drei Eigenschaften zum Festlegen ihrer Geschwindigkeit zur Verfügung:  
  
-   <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>: Gibt die Geschwindigkeit an, mit der die Zeit für eine <xref:System.Windows.Media.Animation.Timeline> relativ zu ihrem übergeordneten Element fortschreitet.  Werte, die größer sind als eins, erhöhen die Geschwindigkeit der <xref:System.Windows.Media.Animation.Timeline> und ihrer untergeordneten <xref:System.Windows.Media.Animation.Timeline>\-Objekte. Werte zwischen 0 \(null\) und 1 verringern die Geschwindigkeit.  Der Wert 1 gibt an, dass die <xref:System.Windows.Media.Animation.Timeline> mit derselben Geschwindigkeit fortschreitet wie ihr übergeordnetes Element.  Die <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>\-Einstellung einer Containerzeitachse beeinflusst auch alle ihre untergeordneten <xref:System.Windows.Media.Animation.Timeline>\-Objekte.  
  
-   <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A>: Gibt den Prozentwert der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> einer Zeitachse an, der für das Beschleunigen verwendet wird.  Ein Beispiel finden Sie unter [Beschleunigen oder Verlangsamen einer Animation](../../../../docs/framework/wpf/graphics-multimedia/how-to-accelerate-or-decelerate-an-animation.md).  
  
-   <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>: Gibt den Prozentwert der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> einer Zeitachse an, der für das Verlangsamen verwendet wird.  Ein Beispiel finden Sie unter [Beschleunigen oder Verlangsamen einer Animation](../../../../docs/framework/wpf/graphics-multimedia/how-to-accelerate-or-decelerate-an-animation.md).  
  
## Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über das Animations\- und Zeitsteuerungssystem](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)   
 [Übersicht über Zeitsteuerungsereignisse](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)   
 [Beispiel zum Verhalten der Animationszeitsteuerung](http://go.microsoft.com/fwlink/?LinkID=159970)