---
title: "&#220;bersicht &#252;ber Zeitsteuerungsereignisse | Microsoft Docs"
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
  - "Clock-Klasse"
  - "Uhr-Klassen"
  - "Zeitachsen"
  - "Zeitsteuerungsereignisse"
ms.assetid: 597e3280-0867-4359-a97b-5b2f4149e350
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# &#220;bersicht &#252;ber Zeitsteuerungsereignisse
Dieses Thema beschreibt, wie die fünf Zeitsteuerungsereignisse auf <xref:System.Windows.Media.Animation.Timeline> und <xref:System.Windows.Media.Animation.Clock> Objekte.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Um dieses Thema zu verstehen, sollten Sie das Erstellen und verwenden Sie Animationen verstehen. Um mit der Animation beginnen, finden Sie unter der [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Es gibt mehrere Methoden zum Animieren von Eigenschaften im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   **Mit Storyboard-Objekten** (Markup und Code): Sie können <xref:System.Windows.Media.Animation.Storyboard> Objekte anzuordnen und Animationen auf ein oder mehrere Objekte zu verteilen. Ein Beispiel finden Sie unter [Animieren einer Eigenschaft mit einem Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).  
  
-   **Mit lokalen Animationen** (nur code): Sie können anwenden <xref:System.Windows.Media.Animation.AnimationTimeline> Objekte direkt auf die Eigenschaften, die sie animieren. Ein Beispiel finden Sie unter [Animieren einer Eigenschaft ohne Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
-   **Uhren mit** (nur code): können Sie explizit verwalten Uhr-Erstellung und die Animationsuhren zu verteilen.  Ein Beispiel finden Sie unter [Animieren einer Eigenschaft mit AnimationClock](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md).  
  
 Da Sie diese in Markup und Code verwenden können, verwenden Sie in den Beispielen in dieser Übersicht <xref:System.Windows.Media.Animation.Storyboard> Objekte. Die beschriebenen Konzepte können jedoch auf die anderen Methoden der Animation von Eigenschaften angewendet werden.  
  
### <a name="what-is-a-clock"></a>Was ist eine Uhr?  
 Eine Zeitachse selbst, lediglich einen Zeitabschnitt beschreibt. Die Zeitachse <xref:System.Windows.Media.Animation.Clock> -Objekt, das die eigentliche Arbeit übernimmt: Es verwaltet zeitbezogenen Laufzeitzustand der Zeitachse. In den meisten Fällen, z. B. bei Verwendung von storyboards wird für die Zeitachse automatisch eine Uhr erstellt. Sie können auch erstellen eine <xref:System.Windows.Media.Animation.Clock> explizit mithilfe der <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> Methode. Weitere Informationen zu <xref:System.Windows.Media.Animation.Clock> von Objekten finden Sie die [Animation and Timing System Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## <a name="why-use-events"></a>Gründe für die Verwendung von Ereignissen  
 Mit einer Ausnahme (seek letzten Tick ausgerichtet), alle interaktiven Timing-Vorgänge sind asynchron. Es gibt keine Möglichkeit für Sie wissen genau, wann sie ausgeführt werden. Dies könnte ein Problem sein, bei anderen Code, der von der zeitlichen Steuerung-Vorgang abhängig ist. Angenommen Sie, Sie möchten eine Zeitachse anhalten, die ein Rechteck animiert. Nachdem die Zeitachse angehalten wurde, ändern Sie die Farbe des Rechtecks.  
  
 [!code-csharp[events_procedural#NeedForEventsFragment](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#needforeventsfragment)]
 [!code-vb[events_procedural#NeedForEventsFragment](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#needforeventsfragment)]  
  
 Im vorherigen Beispiel könnte die zweite Codezeile vor das Storyboard beendet ausgeführt werden. Das liegt daran beenden ein asynchroner Vorgang ist. Mitteilt, eine Zeitachse oder Uhr Beenden erstellt eine "Stop" Art, die bis zum nächsten Teilstrich das Timing-Modul verarbeitet ist.  
  
 Verwenden Sie zum Ausführen von Befehlen nach dem Abschluss einer Zeitachse Zeitsteuerungsereignisse. Im folgenden Beispiel wird ein Ereignishandler verwendet, die Farbe eines Rechtecks ändern, nachdem das Storyboard Wiedergabe beendet wurde.  
  
 [!code-csharp[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#registerforstoryboardcurrentstateinvalidatedevent)]
 [!code-vb[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#registerforstoryboardcurrentstateinvalidatedevent)]  
[!code-csharp[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#storyboardcurrentstateinvalidatedevent2)]
[!code-vb[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#storyboardcurrentstateinvalidatedevent2)]  
  
 Ein ausführlicheres Beispiel finden Sie unter [empfangen Benachrichtigung bei einer Uhr Zustandsänderungen](../../../../docs/framework/wpf/graphics-multimedia/how-to-receive-notification-when-clock-state-changes.md).  
  
## <a name="public-events"></a>Öffentliche Ereignisse  
 Die <xref:System.Windows.Media.Animation.Timeline> und <xref:System.Windows.Media.Animation.Clock> beide Klassen bieten fünf Zeitsteuerungsereignisse. Die folgende Tabelle enthält diese Ereignisse und die Umstände, die sie auslösen.  
  
|Ereignis|Interaktive auslösende|Andere Trigger auslösen|  
|-----------|--------------------------------------|--------------------|  
|**Abgeschlossen**|Fahren Sie mit füllen|Die Uhr wird beendet.|  
|**CurrentGlobalSpeedInvalidated**|Halten Sie an, fortsetzen Sie, suchen Sie, legen Sie die Geschwindigkeit, fahren Sie mit, beenden|Die Uhr kehrt, beschleunigt, startet oder beendet.|  
|**CurrentStateInvalidated**|Starten Sie, fahren Sie mit, beenden|Die Uhr gestartet, beendet oder ausgefüllt wird.|  
|**CurrentTimeInvalidated**|Starten Sie, suchen Sie, überspringen Sie, beenden|Die Uhr ausgeführt.|  
|**RemoveRequested**|Remove||  
  
## <a name="ticking-and-event-consolidation"></a>Tickende und Ereigniskonsolidierung  
 Wenn Sie animieren von Objekten in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], es ist der zeitlichen Steuerung, die Animationen verwaltet. Das Timing-Modul verfolgt den zeitlichen Ablauf und berechnet den Zustand jeder Animation. Es Durchläufen viele dieser Auswertung in einer Sekunde. Diese Auswertung übergibt bekanntermaßen als "Ticks"angegeben.  
  
 Teilstriche treten häufig auf, ist es möglich, für viele Dinge zwischen einzelnen Teilstrichen geschehen. Zum Beispiel eine Zeitachse möglicherweise werden beendet, gestartet und wieder angehalten in diesem Fall der aktuelle Zustand wird dreimal geändert haben. Theoretisch kann das Ereignis mehrmals in einem einzelnen Takt ausgelöst. Das Timing-Modul konsolidiert jedoch Ereignisse, sodass jedes Ereignis höchstens einmal pro Teilstrich ausgelöst werden kann.  
  
## <a name="registering-for-events"></a>Registrieren für Ereignisse  
 Es gibt zwei Möglichkeiten für Zeitsteuerungsereignisse zu registrieren: Sie können über die Zeitachse oder mit der Uhr aus der Zeitachse erstellt registrieren. Registrierung für ein Ereignis direkt mit einer Uhr ist relativ einfach ist, obwohl er nur über Code ausgeführt werden kann. Sie können Ereignisse mit einem Zeitplan von Markup oder Code registrieren. Im nächsten Abschnitt beschrieben registrieren für Uhrenereignisse mit einem Zeitplan.  
  
<a name="registeringforclockeventswithatimeline"></a>   
## <a name="registering-for-clock-events-with-a-timeline"></a>Registrieren für Uhrenereignisse mit einer Zeitachse  
 Obwohl einer Zeitachse <xref:System.Windows.Media.Animation.Timeline.Completed>, <xref:System.Windows.Media.Animation.Timeline.CurrentGlobalSpeedInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentTimeInvalidated>, und <xref:System.Windows.Media.Animation.Timeline.RemoveRequested> Ereignisse angezeigt, mit der Registrierung für diese Ereignisse tatsächlich ordnet einen Ereignishandler mit Zeitleiste verknüpft werden, die <xref:System.Windows.Media.Animation.Clock> für die Zeitachse erstellt.  
  
 Beim Registrieren für die <xref:System.Windows.Media.Animation.Timeline.Completed> Ereignis auf einer Zeitachse, z. B. veranlassen Sie das System zur Registrierung für die <xref:System.Windows.Media.Animation.Clock.Completed> -Ereignis jeder Uhr für die Zeitachse erstellt wird. Im Code müssen Sie für dieses Ereignis vor dem Registrieren der <xref:System.Windows.Media.Animation.Clock> wird erstellt, für diese Zeitachse; andernfalls, Sie wird nicht benachrichtigt. Dies geschieht automatisch in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; der Parser registriert sich automatisch für das Ereignis vor der <xref:System.Windows.Media.Animation.Clock> wird erstellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Das Animations- und Zeitsteuerungssystem Systemübersicht](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)   
 [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über Zeitsteuerungsverhalten](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)