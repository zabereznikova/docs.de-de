---
title: Übersicht über das Animations- und Zeitsteuerungssystem
ms.date: 03/30/2017
helpviewer_keywords:
- timing system [WPF]
- animation [WPF]
ms.assetid: 172cd5a8-a333-4c81-9456-fafccc19f382
ms.openlocfilehash: f64431e7804ba6e068a3d05f512c6ead089d7712
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079317"
---
# <a name="animation-and-timing-system-overview"></a>Übersicht über das Animations- und Zeitsteuerungssystem
In diesem Thema wird beschrieben, wie das Zeitsteuerungssystem die Animation verwendet <xref:System.Windows.Media.Animation.Timeline>, und <xref:System.Windows.Media.Animation.Clock> Klassen zum Animieren von Eigenschaften.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Vorraussetzungen  
 Um dieses Thema zu verstehen, sollten Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animationen zum Animieren von Eigenschaften verwenden können, wie in [Übersicht über Animationen](animation-overview.md) beschrieben. Auch Kenntnisse über Abhängigkeitseigenschaften sind hilfreich. Weitere Informationen finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../advanced/dependency-properties-overview.md).  
  
<a name="timelinesandclocks"></a>   
## <a name="timelines-and-clocks"></a>Zeitachsen und Uhren  
 Die [Übersicht über Animationen](animation-overview.md) beschrieben, wie eine <xref:System.Windows.Media.Animation.Timeline> stellt ein Segment, und eine Animation ist eine Art von <xref:System.Windows.Media.Animation.Timeline> , die Ausgabewerte erzeugt. Selbst eine <xref:System.Windows.Media.Animation.Timeline>, nichts außer einen Zeitabschnitt beschreiben. Die Zeitachse <xref:System.Windows.Media.Animation.Clock> -Objekt, das die eigentliche Arbeit übernimmt. Ebenso Animation nicht tatsächlich Animieren von Eigenschaften: eine Animationsklasse beschreibt, wie Ausgabewerte berechnet werden soll, aber es ist die <xref:System.Windows.Media.Animation.Clock> , die für die Animation, die treibt die Animationsausgabe und wendet sie auf Eigenschaften erstellt wurde.  
  
 Ein <xref:System.Windows.Media.Animation.Clock> ist ein spezieller Typ des Objekts, die zeitbezogenen Laufzeitzustand für verwaltet die <xref:System.Windows.Media.Animation.Timeline>. Er bietet drei Informationen, die für das Animations- und Zeitsteuerungssystem wesentlich sind: <xref:System.Windows.Media.Animation.Clock.CurrentTime%2A>, <xref:System.Windows.Media.Animation.Clock.CurrentProgress%2A>, und <xref:System.Windows.Media.Animation.Clock.CurrentState%2A>. Ein <xref:System.Windows.Media.Animation.Clock> bestimmt Sie die aktuelle Uhrzeit, den Fortschritt und Status, indem Sie das Zeitsteuerungsverhalten von beschrieben die <xref:System.Windows.Media.Animation.Timeline>: <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>und so weiter.  
  
 In den meisten Fällen eine <xref:System.Windows.Media.Animation.Clock> wird automatisch für Ihre Zeitachse erstellt. Wenn Sie Animationen mit einem <xref:System.Windows.Media.Animation.Storyboard> oder <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> -Methode, Uhren automatisch für die Zeitachsen und Animationen erstellt und auf deren Zieleigenschaften angewendet. Sie können auch erstellen, eine <xref:System.Windows.Media.Animation.Clock> explizit durch Verwenden der <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> -Methode der Ihre <xref:System.Windows.Media.Animation.Timeline>. Die <xref:System.Windows.Media.MediaTimeline.CreateClock%2A?displayProperty=nameWithType> Methode erstellt eine Uhr des entsprechenden Typs für die <xref:System.Windows.Media.Animation.Timeline> auf die sie aufgerufen wird. Wenn die <xref:System.Windows.Media.Animation.Timeline> untergeordnete Zeitachsen enthält, erstellt <xref:System.Windows.Media.Animation.Clock> auch für diese Objekte. Die resultierende <xref:System.Windows.Media.Animation.Clock> Objekte werden in Strukturen, die die Struktur der entsprechen angeordnet der <xref:System.Windows.Media.Animation.Timeline> Objektstruktur, aus der sie erstellt werden.  
  
 Es gibt verschiedene Typen von Uhren für verschiedene Typen von Zeitachsen. Die folgende Tabelle zeigt die <xref:System.Windows.Media.Animation.Clock> Typen, die einige der unterschiedlichen entsprechen <xref:System.Windows.Media.Animation.Timeline> Typen.  
  
|Zeitachsentypen|Typ der Uhr|Zweck der Uhr|  
|-------------------|----------------|-------------------|  
|Animation (erbt von <xref:System.Windows.Media.Animation.AnimationTimeline>)|<xref:System.Windows.Media.Animation.AnimationClock>|Generiert Ausgabewerte für eine Abhängigkeitseigenschaft|  
|<xref:System.Windows.Media.MediaTimeline>|<xref:System.Windows.Media.MediaClock>|Verarbeitet eine Mediendatei|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|<xref:System.Windows.Media.Animation.ClockGroup>|Gruppiert und steuert die untergeordneten <xref:System.Windows.Media.Animation.Clock> Objekte|  
|<xref:System.Windows.Media.Animation.Storyboard>|<xref:System.Windows.Media.Animation.ClockGroup>|Gruppiert und steuert die untergeordneten <xref:System.Windows.Media.Animation.Clock> Objekte|  
  
 Sie können eine anwenden <xref:System.Windows.Media.Animation.AnimationClock> Objekte erstellen auf kompatible Abhängigkeitseigenschaften mithilfe der <xref:System.Windows.Media.Animation.IAnimatable.ApplyAnimationClock%2A> Methode.  
  
 In rechenintensiven Szenarios, z. B. Animieren einer großen Anzahl ähnlicher Objekte verwalten Ihre eigenen <xref:System.Windows.Media.Animation.Clock> verwenden, kann Leistungsvorteile bieten.  
  
<a name="timemanager"></a>   
## <a name="clocks-and-the-time-manager"></a>Uhren und der Zeit-Manager  
 Beim Animieren von Objekten im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], es ist die Zeit-Manager verwaltet die <xref:System.Windows.Media.MediaPlayer.Clock%2A> Objekte, die für Ihre Zeitachse erstellt. Der Zeit-Manager ist der Stamm einer Struktur von <xref:System.Windows.Media.MediaPlayer.Clock%2A> Objekten und steuert den Zeitablauf in dieser Struktur.  Ein Zeit-Manager wird automatisch für jede [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung erstellt und ist für den Anwendungsentwickler nicht sichtbar. Der Zeit-Manager „tickt“ mehrmals pro Sekunde. Die tatsächliche Anzahl von Ticks pro Sekunde variiert je nach den verfügbaren Systemressourcen. Während jedes einzelnen Ticks, berechnet der Zeit-Manager den Status aller <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> Objekte in der Zeitstruktur.  
  
 Die folgende Abbildung zeigt die Beziehung zwischen der Zeit-Manager, und <xref:System.Windows.Media.Animation.AnimationClock>, und einer animierten Abhängigkeitseigenschaft.  
  
 ![Komponenten des Informationssystems Zeitsteuerungssystem](./media/graphicsmm-clocks-1clock1prop.png "graphicsmm_clocks_1clock1prop")  
Animieren einer Eigenschaft  
  
 Wenn der Zeit-Manager tickt, aktualisiert er die Zeit von jedem <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> in der Anwendung. Wenn die <xref:System.Windows.Media.Animation.Clock> ist ein <xref:System.Windows.Media.Animation.AnimationClock>, verwendet der <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> Methode der <xref:System.Windows.Media.Animation.AnimationTimeline> aus dem er erstellt wurde, berechnen Sie die aktuelle Ausgabe Wert. Die <xref:System.Windows.Media.Animation.AnimationClock> liefert die <xref:System.Windows.Media.Animation.AnimationTimeline> mit der aktuellen Ortszeit, einen Eingabewert, in der Regel der Basiswert der Eigenschaft, und ein Standardzielwert. Beim Abrufen des Werts einer animierten Eigenschaft mithilfe der <xref:System.Windows.DependencyObject.GetValue%2A> Methode oder dem CLR-Accessor, rufen Sie die Ausgabe von dessen <xref:System.Windows.Media.Animation.AnimationClock>.  
  
#### <a name="clock-groups"></a>Uhrgruppen  
 Im vorherigen Abschnitt beschrieben, wie es gibt verschiedene Typen von <xref:System.Windows.Media.Animation.Clock> Objekte für verschiedene Typen von Zeitachsen. Die folgende Abbildung zeigt die Beziehung zwischen der Zeit-Manager, eine <xref:System.Windows.Media.Animation.ClockGroup>, <xref:System.Windows.Media.Animation.AnimationClock>, und einer animierten Abhängigkeitseigenschaft. Ein <xref:System.Windows.Media.Animation.ClockGroup> wird erstellt, für die Zeitachsen, die andere Zeitachsen gruppieren, z. B. die <xref:System.Windows.Media.Animation.Storyboard> -Klasse, die Animationen und andere Zeitachsen gruppiert.  
  
 ![Komponenten des Informationssystems Zeitsteuerungssystem](./media/graphicsmm-clocks-2clock1clockgroup2prop.png "graphicsmm_clocks_2clock1clockgroup2prop")  
Eine ClockGroup  
  
#### <a name="composition"></a>Komposition  
 Es ist möglich, mehrere Uhren einer einzelnen Eigenschaft zuzuordnen. Jede Uhr verwendet dann den Ausgabewert der vorangehenden Uhr als Basiswert. Die folgende Abbildung zeigt drei <xref:System.Windows.Media.Animation.AnimationClock> Objekte auf dieselbe Eigenschaft angewendet. Uhr1 verwendet den Basiswert der animierten Eigenschaft als Eingabe und verwendet ihn, um die Ausgabe zu generieren. Uhr2 nimmt die Ausgabe von Uhr1 als Eingabe und verwendet sie, um die Ausgabe zu generieren. Uhr3 nimmt die Ausgabe von Uhr2 als Eingabe und verwendet sie, um die Ausgabe zu generieren. Wenn mehrere Uhren gleichzeitig dieselbe Eigenschaft beeinflussen, befinden sie sich in einer Kompositionskette.  
  
 ![Komponenten des Informationssystems Zeitsteuerungssystem](./media/graphicsmm-clocks-2clock1prop.png "graphicsmm_clocks_2clock1prop")  
Eine Kompositionskette  
  
 Beachten Sie, dass, obwohl eine Beziehung zwischen Eingabe und Ausgabe erstellt, wird die <xref:System.Windows.Media.Animation.AnimationClock> Objekte in der Kompositionskette, ihr Zeitsteuerungsverhalten sind nicht betroffen. <xref:System.Windows.Media.Animation.Clock> Objekte (einschließlich <xref:System.Windows.Media.Animation.AnimationClock> Objekten) besitzen eine hierarchische Abhängigkeit von ihren übergeordneten <xref:System.Windows.Media.Animation.Clock> Objekte.  
  
 Um mehrere Uhren auf dieselbe Eigenschaft anzuwenden, verwenden die <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior> beim Anwenden einer <xref:System.Windows.Media.Animation.Storyboard>, Animation oder <xref:System.Windows.Media.Animation.AnimationClock>.  
  
#### <a name="ticks-and-event-consolidation"></a>Tick- und Ereigniskonsolidierung  
 Zusätzlich zum Berechnen von Ausgabewerten verrichtet der Zeit-Manager andere Aufgaben bei jedem Tick: Er bestimmt den Zustand jeder Uhr und löst ggf. Ereignisse aus.  
  
 Wenn Ticks häufiger auftreten, kann zwischen den einzelnen Ticks Vieles geschehen. Z. B. eine <xref:System.Windows.Media.Animation.Clock> möglicherweise werden beendet, gestartet und in diesem Fall in diesem Fall die <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> Wert wird dreimal geändert haben. In der Theorie der <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> Ereignis kann mehrere Male in einem einzelnen Tick ausgelöst werden; die zeitsteuerungs-Engine konsolidiert jedoch Ereignisse, sodass die <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> -Ereignis höchstens einmal pro Teilstrich ausgelöst werden kann. Dies gilt für alle Zeitsteuerungsereignisse: maximal ein Ereignis jedes Typs wird ausgelöst, für einen bestimmten <xref:System.Windows.Media.Animation.Clock> Objekt.  
  
 Wenn eine <xref:System.Windows.Media.Animation.Clock> Zustände wechselt und wieder in den ursprünglichen Zustand zwischen Ticks (z. B. von <xref:System.Windows.Media.Animation.ClockState.Active> zu <xref:System.Windows.Media.Animation.ClockState.Stopped> und zurück zum <xref:System.Windows.Media.Animation.ClockState.Active>), das zugeordnete Ereignis weiterhin auftritt.  
  
 Weitere Informationen zu Zeitsteuerungsereignissen finden Sie unter [Übersicht über Zeitsteuerungsereignisse](timing-events-overview.md).  
  
<a name="currentvaluesbasevaluesofproperties"></a>   
## <a name="current-values-and-base-values-of-properties"></a>Aktuelle Werte und Basiswerte von Eigenschaften  
 Eine animierbare Eigenschaft kann zwei Werte haben: einen Basiswert und einen aktuellen Wert. Beim Festlegen der Eigenschaft mit dem CLR-Accessor oder <xref:System.Windows.DependencyObject.SetValue%2A> -Methode, die den Basiswert festlegen. Wenn eine Eigenschaft nicht animiert ist, sind der Basiswert und der aktuelle Wert identisch.  
  
 Wenn Sie eine Eigenschaft animieren der <xref:System.Windows.Media.Animation.AnimationClock> legt die Eigenschaft des *aktuelle* Wert. Abrufen des Eigenschaftswerts über dessen CLR-Accessor oder <xref:System.Windows.DependencyObject.GetValue%2A> Methode wird die Ausgabe von der <xref:System.Windows.Media.Animation.AnimationClock> bei der <xref:System.Windows.Media.Animation.AnimationClock> ist <xref:System.Windows.Media.Animation.ClockState.Active> oder <xref:System.Windows.Media.Animation.ClockState.Filling>. Sie können den Basiswert der Eigenschaft abrufen, mithilfe der <xref:System.Windows.Media.Animation.IAnimatable.GetAnimationBaseValue%2A> Methode.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über Zeitsteuerungsereignisse](timing-events-overview.md)
- [Übersicht über Zeitsteuerungsverhalten](timing-behaviors-overview.md)
