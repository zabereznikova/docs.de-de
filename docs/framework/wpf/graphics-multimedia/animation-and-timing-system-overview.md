---
title: "Übersicht über das Animations- und Zeitsteuerungssystem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- timing system [WPF]
- animation [WPF]
ms.assetid: 172cd5a8-a333-4c81-9456-fafccc19f382
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 484aa47744de95c849b237112f1a383c2c2cb0b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="animation-and-timing-system-overview"></a>Übersicht über das Animations- und Zeitsteuerungssystem
In diesem Thema wird beschrieben, wie die Zeitsteuerungssystems die Animation verwendet <xref:System.Windows.Media.Animation.Timeline>, und <xref:System.Windows.Media.Animation.Clock> Klassen zum Animieren von Eigenschaften.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Um dieses Thema zu verstehen, sollten Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animationen zum Animieren von Eigenschaften verwenden können, wie in [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) beschrieben. Auch Kenntnisse über Abhängigkeitseigenschaften sind hilfreich. Weitere Informationen finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
<a name="timelinesandclocks"></a>   
## <a name="timelines-and-clocks"></a>Zeitachsen und Uhren  
 Die [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) beschrieben, wie eine <xref:System.Windows.Media.Animation.Timeline> stellt ein Segment, und eine Animation ist eine Art von <xref:System.Windows.Media.Animation.Timeline> , die Ausgabewerte erzeugt. Selbst ein <xref:System.Windows.Media.Animation.Timeline>, nicht alles andere als nur einen Zeitabschnitt beschreiben. Es handelt sich um der Zeitachse <xref:System.Windows.Media.Animation.Clock> -Objekt, das die eigentliche Arbeit übernimmt. Ebenso keine Animation tatsächlich Eigenschaften animiert: eine Animationsklasse wird beschrieben, wie die Ausgabewerte berechnet werden soll, aber es ist die <xref:System.Windows.Media.Animation.Clock> , der für die Animation an, die die Animationsausgabe steuert und wendet sie auf Eigenschaften erstellt wurde.  
  
 Ein <xref:System.Windows.Media.Animation.Clock> ist eine besondere Art von Objekt, das zur Laufzeit-Status für zeitbezogenen verwaltet die <xref:System.Windows.Media.Animation.Timeline>. Sie bietet drei Informationen, die für die Animations- und Zeitsteuerungssystems sind: <xref:System.Windows.Media.Animation.Clock.CurrentTime%2A>, <xref:System.Windows.Media.Animation.Clock.CurrentProgress%2A>, und <xref:System.Windows.Media.Animation.Clock.CurrentState%2A>. Ein <xref:System.Windows.Media.Animation.Clock> bestimmt die aktuelle Uhrzeit, zum Fortschritt und Status der zeitlichen Steuerung Verhalten beschrieben, die durch seine <xref:System.Windows.Media.Animation.Timeline>: <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>und so weiter.  
  
 In den meisten Fällen eine <xref:System.Windows.Media.Animation.Clock> wird automatisch für den Zeitplan erstellt. Wenn Sie Animationen mit einer <xref:System.Windows.Media.Animation.Storyboard> oder die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> -Methode, Uhren automatisch für die Zeitachsen und Animationen erstellt und auf die Zieleigenschaften angewendet. Sie können auch erstellen eine <xref:System.Windows.Media.Animation.Clock> explizit mithilfe der <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> Methode Ihrer <xref:System.Windows.Media.Animation.Timeline>. Die <xref:System.Windows.Media.MediaTimeline.CreateClock%2A?displayProperty=nameWithType> Methode erstellt eine Uhr des entsprechenden Typs für die <xref:System.Windows.Media.Animation.Timeline> auf dem er aufgerufen wird. Wenn die <xref:System.Windows.Media.Animation.Timeline> untergeordnete Zeitachsen enthält, erstellt es <xref:System.Windows.Media.Animation.Clock> auch für diese Objekte. Das resultierende <xref:System.Windows.Media.Animation.Clock> Objekte in Strukturen, die die Struktur der entsprechen angeordnet sind die <xref:System.Windows.Media.Animation.Timeline> Objektstruktur, aus der sie erstellt werden.  
  
 Es gibt verschiedene Typen von Uhren für verschiedene Typen von Zeitachsen. Die folgende Tabelle zeigt die <xref:System.Windows.Media.Animation.Clock> Typen, die einige der verschiedenen entsprechen <xref:System.Windows.Media.Animation.Timeline> Typen.  
  
|Zeitachsentypen|Typ der Uhr|Zweck der Uhr|  
|-------------------|----------------|-------------------|  
|Animation (erbt von <xref:System.Windows.Media.Animation.AnimationTimeline>)|<xref:System.Windows.Media.Animation.AnimationClock>|Generiert Ausgabewerte für eine Abhängigkeitseigenschaft|  
|<xref:System.Windows.Media.MediaTimeline>|<xref:System.Windows.Media.MediaClock>|Verarbeitet eine Mediendatei|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|<xref:System.Windows.Media.Animation.ClockGroup>|Gruppiert und seine untergeordneten Steuerelemente <xref:System.Windows.Media.Animation.Clock> Objekte|  
|<xref:System.Windows.Media.Animation.Storyboard>|<xref:System.Windows.Media.Animation.ClockGroup>|Gruppiert und seine untergeordneten Steuerelemente <xref:System.Windows.Media.Animation.Clock> Objekte|  
  
 Sie können gelten alle <xref:System.Windows.Media.Animation.AnimationClock> an kompatibel Abhängigkeitseigenschaften mit erstellten Objekte die <xref:System.Windows.Media.Animation.IAnimatable.ApplyAnimationClock%2A> Methode.  
  
 Im ressourcenintensiven Szenarien, z. B. animieren zahlreiche ähnliche Objekte verwalten Ihren eigenen <xref:System.Windows.Media.Animation.Clock> verwenden kann Leistungsvorteile bieten.  
  
<a name="timemanager"></a>   
## <a name="clocks-and-the-time-manager"></a>Uhren und der Zeit-Manager  
 Wenn Animieren von Objekten in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], es ist Zeit-Manager verwaltet die <xref:System.Windows.Media.MediaPlayer.Clock%2A> für die Zeitachsen erstellten Objekte. Der Zeit-Manager ist der Stamm einer Struktur von <xref:System.Windows.Media.MediaPlayer.Clock%2A> Objekten und steuert den Zeitablauf in dieser Struktur.  Ein Zeit-Manager wird automatisch für jede [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung erstellt und ist für den Anwendungsentwickler nicht sichtbar. Der Zeit-Manager „tickt“ mehrmals pro Sekunde. Die tatsächliche Anzahl von Ticks pro Sekunde variiert je nach den verfügbaren Systemressourcen. Während jedes einzelnen Teilstrichs, berechnet der Zeit-Manager den Status aller <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> Objekte in der Zeitstruktur.  
  
 Die folgende Abbildung zeigt die Beziehung zwischen der Zeit-Manager und <xref:System.Windows.Media.Animation.AnimationClock>, und eine animierte Abhängigkeitseigenschaft.  
  
 ![Ein Timeout Systemkomponenten](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-1clock1prop.png "graphicsmm_clocks_1clock1prop")  
Animieren einer Eigenschaft  
  
 Bei der Zeit-Manager Takte, aktualisiert er die Zeit von jeder <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> in der Anwendung. Wenn die <xref:System.Windows.Media.Animation.Clock> ist ein <xref:System.Windows.Media.Animation.AnimationClock>, verwendet der <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> Methode von der <xref:System.Windows.Media.Animation.AnimationTimeline> aus dem er erstellt wurde zum Berechnen von seinem aktuellen Ausgabewert. Die <xref:System.Windows.Media.Animation.AnimationClock> liefert die <xref:System.Windows.Media.Animation.AnimationTimeline> mit der aktuellen lokalen Uhrzeit, einen Eingabewert, der dem Basiswert der Eigenschaft in der Regel ist, und einen Standardwert für das Ziel. Beim Abrufen des Wert einer animierten Eigenschaft mithilfe der <xref:System.Windows.DependencyObject.GetValue%2A> -Methode oder dem CLR-Accessor, erhalten Sie die Ausgabe von seiner <xref:System.Windows.Media.Animation.AnimationClock>.  
  
#### <a name="clock-groups"></a>Uhrgruppen  
 Im vorherigen Abschnitt beschrieben, wie es gibt verschiedene Typen von <xref:System.Windows.Media.Animation.Clock> Objekte für verschiedene Typen von Zeitplänen. Die folgende Abbildung zeigt die Beziehung zwischen der Zeit-Manager eine <xref:System.Windows.Media.Animation.ClockGroup>, einem <xref:System.Windows.Media.Animation.AnimationClock>, und eine animierte Abhängigkeitseigenschaft. Ein <xref:System.Windows.Media.Animation.ClockGroup> wird erstellt, für die Zeitachsen, die andere Zeitachsen gruppieren, z. B. die <xref:System.Windows.Media.Animation.Storyboard> -Klasse, die Animationen und andere Zeitachsen gruppiert.  
  
 ![Ein Timeout Systemkomponenten](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-2clock1clockgroup2prop.png "graphicsmm_clocks_2clock1clockgroup2prop")  
Eine ClockGroup  
  
#### <a name="composition"></a>Komposition  
 Es ist möglich, mehrere Uhren einer einzelnen Eigenschaft zuzuordnen. Jede Uhr verwendet dann den Ausgabewert der vorangehenden Uhr als Basiswert. Die folgende Abbildung zeigt drei <xref:System.Windows.Media.Animation.AnimationClock> Objekte auf dieselbe Eigenschaft angewendet. Uhr1 verwendet den Basiswert der animierten Eigenschaft als Eingabe und verwendet ihn, um die Ausgabe zu generieren. Uhr2 nimmt die Ausgabe von Uhr1 als Eingabe und verwendet sie, um die Ausgabe zu generieren. Uhr3 nimmt die Ausgabe von Uhr2 als Eingabe und verwendet sie, um die Ausgabe zu generieren. Wenn mehrere Uhren gleichzeitig dieselbe Eigenschaft beeinflussen, befinden sie sich in einer Kompositionskette.  
  
 ![Ein Timeout Systemkomponenten](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-2clock1prop.png "graphicsmm_clocks_2clock1prop")  
Eine Kompositionskette  
  
 Beachten Sie, dass, obwohl eine Beziehung zwischen Eingabe und Ausgabe der erstellt wird die <xref:System.Windows.Media.Animation.AnimationClock> -Objekte in der Kompositionskette ihre Zeitsteuerungsverhalten sind nicht betroffen. <xref:System.Windows.Media.Animation.Clock> Objekte (einschließlich <xref:System.Windows.Media.Animation.AnimationClock> Objekte) haben eine hierarchische Abhängigkeit auf der übergeordneten <xref:System.Windows.Media.Animation.Clock> Objekte.  
  
 Um mehrere Uhren auf dieselbe Eigenschaft anzuwenden, verwenden die <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior> beim Anwenden einer <xref:System.Windows.Media.Animation.Storyboard>, Animation oder <xref:System.Windows.Media.Animation.AnimationClock>.  
  
#### <a name="ticks-and-event-consolidation"></a>Tick- und Ereigniskonsolidierung  
 Zusätzlich zum Berechnen von Ausgabewerten verrichtet der Zeit-Manager andere Aufgaben bei jedem Tick: Er bestimmt den Zustand jeder Uhr und löst ggf. Ereignisse aus.  
  
 Wenn Ticks häufiger auftreten, kann zwischen den einzelnen Ticks Vieles geschehen. Z. B. eine <xref:System.Windows.Media.Animation.Clock> beendet, gestartet und beendet, in diesem Fall werden möglicherweise ihre <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> Wert wird dreimal geändert haben. In der Theorie der <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> Ereignis kann mehrere Male in einem einzelnen Takt ausgelöst werden; jedoch das Timing Modul Ereignisse konsolidiert, damit die <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> -Ereignis höchstens einmal pro Takt ausgelöst werden kann. Dies gilt für alle Ereignisse zu abfrageantwortzeiten: jedes Typs darf höchstens ein Ereignis wird ausgelöst, für einen bestimmten <xref:System.Windows.Media.Animation.Clock> Objekt.  
  
 Wenn eine <xref:System.Windows.Media.Animation.Clock> wechselt den Status auf und gibt Sie an den ursprünglichen Zustand zurück, zwischen den Teilstrichen (z. B. das Ändern von <xref:System.Windows.Media.Animation.ClockState.Active> auf <xref:System.Windows.Media.Animation.ClockState.Stopped> und zurück zum <xref:System.Windows.Media.Animation.ClockState.Active>), das zugeordnete Ereignis weiterhin auftritt.  
  
 Weitere Informationen zu Zeitsteuerungsereignissen finden Sie unter [Übersicht über Zeitsteuerungsereignisse](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md).  
  
<a name="currentvaluesbasevaluesofproperties"></a>   
## <a name="current-values-and-base-values-of-properties"></a>Aktuelle Werte und Basiswerte von Eigenschaften  
 Eine animierbare Eigenschaft kann zwei Werte haben: einen Basiswert und einen aktuellen Wert. Wenn Sie mit dem CLR-Accessor Eigenschaft festlegen oder die <xref:System.Windows.DependencyObject.SetValue%2A> -Methode, legen Sie den Basiswert. Wenn eine Eigenschaft nicht animiert ist, sind der Basiswert und der aktuelle Wert identisch.  
  
 Wenn Sie eine Eigenschaft animieren der <xref:System.Windows.Media.Animation.AnimationClock> legt die Eigenschaft *aktuelle* Wert. Abrufen des Eigenschaftswerts über dem CLR-Accessor oder die <xref:System.Windows.DependencyObject.GetValue%2A> Methodenrückgabe die Ausgabe von der <xref:System.Windows.Media.Animation.AnimationClock> bei der <xref:System.Windows.Media.Animation.AnimationClock> ist <xref:System.Windows.Media.Animation.ClockState.Active> oder <xref:System.Windows.Media.Animation.ClockState.Filling>. Sie können den Wert der Eigenschaft Basis abrufen, mithilfe der <xref:System.Windows.Media.Animation.IAnimatable.GetAnimationBaseValue%2A> Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über Zeitsteuerungsereignisse](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)  
 [Übersicht über Zeitsteuerungsverhalten](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)
