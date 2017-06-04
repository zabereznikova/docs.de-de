---
title: "&#220;bersicht &#252;ber das Animations- und Zeitsteuerungssystem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Animation [WPF]"
  - "Zeitsteuerungssystem [WPF]"
ms.assetid: 172cd5a8-a333-4c81-9456-fafccc19f382
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# &#220;bersicht &#252;ber das Animations- und Zeitsteuerungssystem
In diesem Thema wird beschrieben, wie das Zeitsteuerungssystem die Animationsklasse, die <xref:System.Windows.Media.Animation.Timeline>\-Klasse und die <xref:System.Windows.Media.Animation.Clock>\-Klasse verwendet, um Eigenschaften zu animieren.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 Für dieses Thema sollten Sie mit der Verwendung der unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) beschriebenen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Animationen zum Animieren von Eigenschaften vertraut sein.  Es ist auch hilfreich, mit [Abhängigkeitseigenschaften](GTMT) vertraut zu sein. Weitere Informationen finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
<a name="timelinesandclocks"></a>   
## Zeitachsen und Uhren  
 In [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) wurde beschrieben, wie eine <xref:System.Windows.Media.Animation.Timeline> ein Zeitsegment darstellt, und dass eine Animation ein Typ einer <xref:System.Windows.Media.Animation.Timeline> ist, die Ausgabewerte erzeugt.  Eine <xref:System.Windows.Media.Animation.Timeline> selbst hat lediglich die Funktion, einen bestimmten Zeitabschnitt zu beschreiben.  Die eigentliche Arbeit übernimmt das <xref:System.Windows.Media.Animation.Clock>\-Objekt der Zeitachse.  Ebenso animiert eine Animation eigentlich keine Eigenschaften: Eine Animationsklasse beschreibt, wie Ausgabewerte berechnet werden sollen, aber die für die Animation erstellte <xref:System.Windows.Media.Animation.Clock> steuert die Animationsausgabe und wendet sie auf Eigenschaften an.  
  
 Eine <xref:System.Windows.Media.Animation.Clock> ist ein besonderer Objekttyp, der den zeitbezogenen Laufzeitzustand für die <xref:System.Windows.Media.Animation.Timeline> verwaltet.  Sie bietet drei Informationen, die für das Animations\- und Zeitsteuerungssystem sehr wichtig sind: <xref:System.Windows.Media.Animation.Clock.CurrentTime%2A>, <xref:System.Windows.Media.Animation.Clock.CurrentProgress%2A> und <xref:System.Windows.Media.Animation.Clock.CurrentState%2A>.  Eine <xref:System.Windows.Media.Animation.Clock> bestimmt die aktuelle Uhrzeit, den Fortschritt und den Zustand mithilfe des Zeitverhaltens, das von ihrer <xref:System.Windows.Media.Animation.Timeline> beschrieben wird: <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> usw.  
  
 In den meisten Fällen wird für die Zeitachse automatisch eine <xref:System.Windows.Media.Animation.Clock> erstellt.  Wenn Sie Animationen mit einem <xref:System.Windows.Media.Animation.Storyboard> oder der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>\-Methode ausführen, werden Uhren für die Zeitachsen und Animationen automatisch erstellt und auf die Zieleigenschaften angewendet.  Sie können mit der <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A>\-Methode der <xref:System.Windows.Media.Animation.Timeline> auch explizit eine <xref:System.Windows.Media.Animation.Clock> erstellen.  Die <xref:System.Windows.Media.MediaTimeline.CreateClock%2A?displayProperty=fullName>\-Methode erstellt für die <xref:System.Windows.Media.Animation.Timeline>, für die sie aufgerufen wird, eine Uhr des entsprechenden Typs.  Wenn die <xref:System.Windows.Media.Animation.Timeline> untergeordnete Zeitachsen enthält, erstellt sie auch für diese <xref:System.Windows.Media.Animation.Clock>\-Objekte.  Die resultierenden <xref:System.Windows.Media.Animation.Clock>\-Objekte werden in Strukturen angeordnet, die der Struktur der <xref:System.Windows.Media.Animation.Timeline>\-Objektstruktur, aus der sie erstellt werden, entsprechen.  
  
 Es gibt verschiedene Typen von Uhren für verschiedene Typen von Zeitachsen.  In der folgenden Tabelle werden die <xref:System.Windows.Media.Animation.Clock>\-Typen dargestellt, die einigen der verschiedenen <xref:System.Windows.Media.Animation.Timeline>\-Typen entsprechen.  
  
|Zeitachsentyp|Uhrtyp|Zweck der Uhr|  
|-------------------|------------|-------------------|  
|Animation \(erbt von <xref:System.Windows.Media.Animation.AnimationTimeline>\)|<xref:System.Windows.Media.Animation.AnimationClock>|Generiert Ausgabewerte für eine Abhängigkeitseigenschaft.|  
|<xref:System.Windows.Media.MediaTimeline>|<xref:System.Windows.Media.MediaClock>|Verarbeitet eine Mediendatei.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|<xref:System.Windows.Media.Animation.ClockGroup>|Gruppiert und steuert die untergeordneten <xref:System.Windows.Media.Animation.Clock>\-Objekte|  
|<xref:System.Windows.Media.Animation.Storyboard>|<xref:System.Windows.Media.Animation.ClockGroup>|Gruppiert und steuert die untergeordneten <xref:System.Windows.Media.Animation.Clock>\-Objekte|  
  
 Sie können alle von Ihnen erstellten <xref:System.Windows.Media.Animation.AnimationClock>\-Objekte mithilfe der <xref:System.Windows.Media.Animation.IAnimatable.ApplyAnimationClock%2A>\-Methode auf kompatible Abhängigkeitseigenschaften anwenden.  
  
 In ressourcenintensiven Szenarien, z. B. beim Animieren einer großen Anzahl ähnlicher Objekte, kann das Verwalten der eigenen <xref:System.Windows.Media.Animation.Clock>\-Verwendung Leistungsvorteile bieten.  
  
<a name="timemanager"></a>   
## Uhren und Zeit\-Manager  
 Wenn Sie Objekte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] animieren, werden die für die Zeitachsen erstellten <xref:System.Windows.Media.MediaPlayer.Clock%2A>\-Objekte vom Zeit\-Manager verwaltet.  Der Zeit\-Manager ist der Stamm einer Struktur von <xref:System.Windows.Media.MediaPlayer.Clock%2A>\-Objekten und steuert den Zeitablauf in dieser Struktur.  Ein Zeit\-Manager wird automatisch für jede [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung erstellt und ist für den Anwendungsentwickler nicht sichtbar. Der Zeit\-Manager erfasst viele "Ticks" pro Sekunde. Wie viele Ticks tatsächlich in jeder Sekunde auftreten, variiert abhängig von den verfügbaren Systemressourcen.  Während jedes einzelnen Teilstrichs berechnet der Zeit\-Manager den Zustand aller <xref:System.Windows.Media.Animation.ClockState> <xref:System.Windows.Media.Animation.Clock>\-Objekte in der Zeitstruktur.  
  
 In der folgenden Abbildung wird die Beziehung zwischen dem Zeit\-Manager und <xref:System.Windows.Media.Animation.AnimationClock> sowie einer animierten Abhängigkeitseigenschaft veranschaulicht.  
  
 ![Zeitsteuerungssystemkomponenten](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-1clock1prop.png "graphicsmm\_clocks\_1clock1prop")  
Animieren einer Eigenschaft  
  
 Bei jedem Teilstrich des Zeit\-Managers aktualisiert er die Zeit von jeder <xref:System.Windows.Media.Animation.ClockState> <xref:System.Windows.Media.Animation.Clock> in der Anwendung.  Wenn die <xref:System.Windows.Media.Animation.Clock> eine <xref:System.Windows.Media.Animation.AnimationClock> ist, wird mit der <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>\-Methode der <xref:System.Windows.Media.Animation.AnimationTimeline>, aus der sie erstellt wurde, der aktuelle Ausgabewert berechnet.  Die <xref:System.Windows.Media.Animation.AnimationClock> stellt die <xref:System.Windows.Media.Animation.AnimationTimeline> mit der aktuellen Ortszeit, einem Eingabewert, bei dem es sich üblicherweise um den Basiswert der Eigenschaft handelt, und einem Standardzielwert bereit.  Wenn Sie mit der <xref:System.Windows.DependencyObject.GetValue%2A>\-Methode oder dem CLR\-Accessor den Wert einer animierten Eigenschaft abrufen, erhalten Sie die Ausgabe der zugehörigen <xref:System.Windows.Media.Animation.AnimationClock>.  
  
#### ClockGroups  
 Im vorherigen Abschnitt wurde beschrieben, dass es verschiedene Typen von <xref:System.Windows.Media.Animation.Clock>\-Objekten für verschiedene Typen von Zeitachsen gibt.  In der folgenden Abbildung wird die Beziehung zwischen dem Zeit\-Manager, einer <xref:System.Windows.Media.Animation.ClockGroup>, einer <xref:System.Windows.Media.Animation.AnimationClock> und einer animierten Abhängigkeitseigenschaft veranschaulicht.  Es wird eine <xref:System.Windows.Media.Animation.ClockGroup> für Zeitachsen erstellt, die andere Zeitachsen gruppieren, z. B. die <xref:System.Windows.Media.Animation.Storyboard>\-Klasse, die Animationen und andere Zeitachsen gruppiert.  
  
 ![Zeitsteuerungssystemkomponenten](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-2clock1clockgroup2prop.png "graphicsmm\_clocks\_2clock1clockgroup2prop")  
Eine ClockGroup  
  
#### Komposition  
 Es ist möglich, einer einzelnen Eigenschaft mehrere Uhren zuzuordnen. In diesem Fall verwendet jede Uhr den Ausgabewert der vorherigen Uhr als Basiswert.  In der folgenden Abbildung werden drei <xref:System.Windows.Media.Animation.AnimationClock>\-Objekte dargestellt, die auf dieselbe Eigenschaft angewendet werden.  Clock1 verwendet den Basiswert der animierten Eigenschaft als Eingabe und verwendet diese wiederum zum Generieren einer Ausgabe.  Clock2 verwendet die Ausgabe von Clock1 als Eingabe und verwendet diese wiederum zum Generieren einer Ausgabe.  Clock3 verwendet die Ausgabe von Clock2 als Eingabe und verwendet diese wiederum zum Generieren einer Ausgabe.  Wenn mehrere Uhren gleichzeitig dieselbe Eigenschaft beeinflussen, werden sie als Kompositionskette bezeichnet.  
  
 ![Zeitsteuerungssystemkomponenten](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-2clock1prop.png "graphicsmm\_clocks\_2clock1prop")  
Eine Kompositionskette  
  
 Beachten Sie, dass, obwohl zwischen Ein\- und Ausgabe der <xref:System.Windows.Media.Animation.AnimationClock>\-Objekte in der Kompositionskette eine Beziehung erstellt wird, ihr Zeitverhalten nicht beeinflusst wird. <xref:System.Windows.Media.Animation.Clock>\-Objekte \(einschließlich <xref:System.Windows.Media.Animation.AnimationClock>\-Objekten\) besitzen eine hierarchische Abhängigkeit von ihren übergeordneten <xref:System.Windows.Media.Animation.Clock>\-Objekten.  
  
 Um mehrere Uhren auf dieselbe Eigenschaft anzuwenden, verwenden Sie <xref:System.Windows.Media.Animation.HandoffBehavior> <xref:System.Windows.Media.Animation.HandoffBehavior>, wenn Sie ein <xref:System.Windows.Media.Animation.Storyboard>, eine Animation oder eine <xref:System.Windows.Media.Animation.AnimationClock> anwenden.  
  
#### Teilstriche und Ereigniskonsolidierung  
 Zusätzlich zum Berechnen von Ausgabewerten erledigt der Zeit\-Manager bei jedem Teilstrich noch weitere Aufgaben: Er bestimmt den Zustand jeder Uhr und löst ggf. Ereignisse aus.  
  
 Teilstriche treten häufig auf, und es können viele Dinge zwischen einzelnen Teilstrichen geschehen.  Beispielsweise kann eine <xref:System.Windows.Media.Animation.Clock> angehalten, gestartet und wieder angehalten werden. Dabei hätte sich der <xref:System.Windows.Media.Animation.Clock.CurrentState%2A>\-Wert insgesamt dreimal geändert.  Theoretisch kann das <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated>\-Ereignis für einen einzelnen Teilstrich mehrere Male ausgelöst werden. Das Zeitgebermodul konsolidiert jedoch Ereignisse, sodass das <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated>\-Ereignis höchstens einmal pro Teilstrich ausgelöst werden kann.  Dies gilt für alle Zeitsteuerungsereignisse: Maximal ein Ereignis von jedem Typ wird für ein bestimmtes <xref:System.Windows.Media.Animation.Clock>\-Objekt ausgelöst.  
  
 Wenn eine <xref:System.Windows.Media.Animation.Clock> die Zustände wechselt und zwischen den Teilstrichen zum ursprünglichen Zustand zurückkehrt \(z. B. beim Wechsel von <xref:System.Windows.Media.Animation.ClockState> zu <xref:System.Windows.Media.Animation.ClockState> und zurück zu <xref:System.Windows.Media.Animation.ClockState>\), tritt das zugeordnete Ereignis weiterhin auf.  
  
 Weitere Informationen zu Zeitsteuerungsereignissen finden Sie unter [Übersicht über Zeitsteuerungsereignisse](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md).  
  
<a name="currentvaluesbasevaluesofproperties"></a>   
## Aktuelle Werte und Basiswerte von Eigenschaften  
 Eine animierbare Eigenschaft kann zwei Werte besitzen: einen Basiswert und einen aktuellen Wert.  Wenn Sie die Eigenschaft mit dem CLR\-Accessor oder der <xref:System.Windows.DependencyObject.SetValue%2A>\-Methode festlegen, legen Sie den Basiswert fest.  Bei einer nicht animierten Eigenschaft sind Basiswert und aktueller Wert gleich.  
  
 Wenn Sie eine Eigenschaft animieren, legt <xref:System.Windows.Media.Animation.AnimationClock> den *aktuellen* Wert der Eigenschaft fest.  Beim Abrufen des Eigenschaftswerts mit dem CLR\-Accessor oder der <xref:System.Windows.DependencyObject.GetValue%2A>\-Methode wird die Ausgabe von <xref:System.Windows.Media.Animation.AnimationClock> zurückgegeben, wenn <xref:System.Windows.Media.Animation.AnimationClock> den Wert <xref:System.Windows.Media.Animation.ClockState> oder <xref:System.Windows.Media.Animation.ClockState> aufweist.  Sie können den Basiswert der Eigenschaft mit der <xref:System.Windows.Media.Animation.IAnimatable.GetAnimationBaseValue%2A>\-Methode abrufen.  
  
## Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über Zeitsteuerungsereignisse](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)   
 [Übersicht über Zeitsteuerungsverhalten](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)