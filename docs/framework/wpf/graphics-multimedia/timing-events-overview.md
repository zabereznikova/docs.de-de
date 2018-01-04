---
title: "Übersicht über Zeitsteuerungsereignisse"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- timelines [WPF]
- timing events [WPF]
ms.assetid: 597e3280-0867-4359-a97b-5b2f4149e350
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 79669bdc4b5f9cfb8bdac92efa07e932cc14ac57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="timing-events-overview"></a>Übersicht über Zeitsteuerungsereignisse
Dieses Thema beschreibt, wie die fünf Ereignisse zu abfrageantwortzeiten verfügbar <xref:System.Windows.Media.Animation.Timeline> und <xref:System.Windows.Media.Animation.Clock> Objekte.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Als Voraussetzung für dieses Thema sollten Sie wissen, wie Animationen erstellt und verwendet werden. Um mit der Animation beginnen, finden Sie unter der [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Es gibt mehrere Möglichkeiten zum Animieren von Eigenschaften in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   **Mit Storyboard-Objekten** (Markup und Code): Sie können <xref:System.Windows.Media.Animation.Storyboard> Objekte anordnen und Animationen auf ein oder mehrere Objekte zu verteilen. Ein Beispiel finden Sie unter [Animieren einer Eigenschaft eines Drehbuchs mit](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).  
  
-   **Mit lokalen Animationen** (nur code): Sie können anwenden <xref:System.Windows.Media.Animation.AnimationTimeline> Objekte direkt auf die Eigenschaften, die sie dem animiert werden soll. Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
-   **Mit Uhren** (nur Code): Sie können die Uhrerstellung explizit verwalten und die Animationsuhren zu verteilen.  Ein Beispiel finden Sie unter [Animieren einer Eigenschaft mit AnimationClock](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md).  
  
 Da Sie diese im Markup und Code verwenden können, verwenden Sie in den Beispielen in dieser Übersicht <xref:System.Windows.Media.Animation.Storyboard> Objekte. Die beschriebenen Konzepte können jedoch auf die anderen Methoden der Animation von Eigenschaften angewendet werden.  
  
### <a name="what-is-a-clock"></a>Was ist eine Uhr?  
 Eine Zeitachse beschreibt eigentlich lediglich einen Zeitabschnitt. Es handelt sich um der Zeitachse <xref:System.Windows.Media.Animation.Clock> -Objekt, das die eigentliche Arbeit übernimmt: Es verwaltet zeitbezogenen Laufzeitzustand der Zeitachse. In den meisten Fällen, z.B. bei Verwendung von Storyboards, wird für die Zeitachse automatisch eine Uhr erstellt. Sie können auch erstellen eine <xref:System.Windows.Media.Animation.Clock> explizit mithilfe der <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> Methode. Weitere Informationen zu <xref:System.Windows.Media.Animation.Clock> anzuzeigen, die [Animationen und zeitlichen Steuerung Systemübersicht](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## <a name="why-use-events"></a>Gründe für die Verwendung von Ereignissen  
 Bis auf einen (ausgerichtet am letzten Teilstrich) sind alle interaktiven Zeitsteuerungsvorgänge asynchron. Sie haben keine Möglichkeit, den genauen Zeitpunkt ihrer Ausführung herauszufinden. Dies kann problematisch sein, wenn Sie anderen Code haben, der von Ihrem Zeitsteuerungsvorgang abhängig ist. Angenommen, Sie möchten eine Zeitachse stoppen, die ein Rechteck animiert. Nachdem die Zeitachse gestoppt wurde, können Sie die Farbe des Rechtecks ändern.  
  
 [!code-csharp[events_procedural#NeedForEventsFragment](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#needforeventsfragment)]
 [!code-vb[events_procedural#NeedForEventsFragment](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#needforeventsfragment)]  
  
 Im vorherigen Beispiel kann die zweite Codezeile ausgeführt werden, bevor das Storyboard gestoppt wird. Das liegt daran, dass das Stoppen ein asynchroner Vorgang ist. Wenn das Stoppen einer Zeitachse oder Uhr angefordert wird, wird eine Art „Beendigungsanforderung“ erstellt, die erst nach dem nächsten Teilstrich des Zeitsteuerungsmoduls verarbeitet wird.  
  
 Verwenden Sie zum Ausführen von Befehlen nach dem Abschluss einer Zeitachse Zeitsteuerungsereignisse. Im folgenden Beispiel wird ein Ereignishandler verwendet, um die Farbe eines Rechtecks ändern, nachdem die Storyboard-Wiedergabe gestoppt wurde.  
  
 [!code-csharp[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#registerforstoryboardcurrentstateinvalidatedevent)]
 [!code-vb[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#registerforstoryboardcurrentstateinvalidatedevent)]  
[!code-csharp[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#storyboardcurrentstateinvalidatedevent2)]
[!code-vb[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#storyboardcurrentstateinvalidatedevent2)]  
  
 Ein vollständigeres Beispiel finden Sie unter [empfangen Benachrichtigung bei einer Uhr Zustandsänderungen](../../../../docs/framework/wpf/graphics-multimedia/how-to-receive-notification-when-clock-state-changes.md).  
  
## <a name="public-events"></a>Öffentliche Ereignisse  
 Die <xref:System.Windows.Media.Animation.Timeline> und <xref:System.Windows.Media.Animation.Clock> beide Klassen bieten fünf Ereignisse zu abfrageantwortzeiten. Die folgende Tabelle enthält diese Ereignisse und die Umstände, die sie auslösen.  
  
|event|Auslösen von interaktiven Vorgängen|Andere Trigger|  
|-----------|--------------------------------------|--------------------|  
|**Abgeschlossen**|Zur Füllung überspringen|Die Uhr wird beendet.|  
|**CurrentGlobalSpeedInvalidated**|Anhalten, Fortsetzen, Suchen, Geschwindigkeitsverhältnis festlegen, Zur Füllung überspringen, Stoppen|Die Uhr kehrt um, beschleunigt, startet oder stoppt.|  
|**CurrentStateInvalidated**|Beginnen, Zur Füllung überspringen, Stoppen|Die Uhr startet, stoppt oder füllt.|  
|**CurrentTimeInvalidated**|Beginnen, Suchen, Zur Füllung überspringen, Stoppen|Die Uhr läuft.|  
|**RemoveRequested**|Remove||  
  
## <a name="ticking-and-event-consolidation"></a>Teilstrich- und Ereigniskonsolidierung  
 Wenn Sie animieren von Objekten in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], es ist ein Timeout-Modul, das die Animationen verwaltet. Die Zeitsteuerungsmodul verfolgt den zeitlichen Ablauf und berechnet den Status der einzelnen Animationen. In einer Sekunde werden viele dieser Auswertungsdurchläufe durchgeführt. Die Auswertungsdurchläufe heißen „Teilstriche“.  
  
 Wenn Teilstriche häufiger auftreten, können zwischen den einzelnen Teilstrichen viele Dinge geschehen. Beispielsweise kann eine Zeitachse gestoppt, gestartet und wieder gestoppt werden. In diesem Fall ändert sich ihr aktueller Status drei Mal. Theoretisch kann das Ereignis mehrere Male in einem Teilstrich ausgelöst werden. Die Zeitsteuerungsmodul konsolidiert jedoch Ereignisse, damit jedes Ereignis höchstens einmal pro Teilstrich ausgelöst werden kann.  
  
## <a name="registering-for-events"></a>Registrieren für Ereignisse  
 Es gibt mehrere Möglichkeiten, um sich für Zeitsteuerungsereignisse zu registrieren: Sie könne sich bei der Zeitachse oder der aus der Zeitachse erstellten Uhr registrieren. Registrierung für ein Ereignis direkt bei einer Uhr ist relativ einfach, obwohl sie nur über Code ausgeführt werden kann. Sie können sich über Markup oder Code für Ereignisse bei einer Zeitachse registrieren. Im nächsten Abschnitt wird beschrieben, wie sie sich für Uhrereignisse bei einer Zeitachse registrieren.  
  
<a name="registeringforclockeventswithatimeline"></a>   
## <a name="registering-for-clock-events-with-a-timeline"></a>Registrieren für Uhrereignisse bei einer Zeitachse  
 Obwohl einer Zeitachse <xref:System.Windows.Media.Animation.Timeline.Completed>, <xref:System.Windows.Media.Animation.Timeline.CurrentGlobalSpeedInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentTimeInvalidated>, und <xref:System.Windows.Media.Animation.Timeline.RemoveRequested> Ereignisse angezeigt werden, auf der Zeitachse, die Registrierung für diese Ereignisse tatsächlich ordnet einen Ereignishandler mit zugeordnet werden die <xref:System.Windows.Media.Animation.Clock> für den Zeitplan erstellt.  
  
 Beim Registrieren für die <xref:System.Windows.Media.Animation.Timeline.Completed> Ereignis auf einer Zeitachse, z. B. veranlassen Sie das System so registrieren Sie für die <xref:System.Windows.Media.Animation.Clock.Completed> -Ereignis für jedes Uhr für den Zeitplan erstellt wird. Im Code müssen Sie für dieses Ereignis vor dem Registrieren der <xref:System.Windows.Media.Animation.Clock> wird erstellt, für diese Zeitachse; andernfalls, Sie wird nicht benachrichtigt. Dies geschieht automatisch in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; der Parser automatisch registriert werden, für das Ereignis vor der <xref:System.Windows.Media.Animation.Clock> wird erstellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über das Animations- und Zeitsteuerungssystem](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über Zeitsteuerungsverhalten](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)
