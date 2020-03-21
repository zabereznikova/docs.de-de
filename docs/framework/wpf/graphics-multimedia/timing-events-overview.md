---
title: Übersicht über Zeitsteuerungsereignisse
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- timelines [WPF]
- timing events [WPF]
ms.assetid: 597e3280-0867-4359-a97b-5b2f4149e350
ms.openlocfilehash: ee45441e9ad09c60d8b61ecce4ef08b0027ce29e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145409"
---
# <a name="timing-events-overview"></a>Übersicht über Zeitsteuerungsereignisse
In diesem Thema wird beschrieben, wie <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Clock> die fünf verfügbaren Zeitereignisse und Objekte verwendet werden.  
  
## <a name="prerequisites"></a>Voraussetzungen  
 Als Voraussetzung für dieses Thema sollten Sie wissen, wie Animationen erstellt und verwendet werden. Informationen zu den ersten Informationen finden Sie in der [Animationsübersicht](animation-overview.md).  
  
 Es gibt mehrere Möglichkeiten, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Eigenschaften in zu animieren:  
  
- **Verwenden von Storyboardobjekten** (Markup und <xref:System.Windows.Media.Animation.Storyboard> Code): Sie können Objekte verwenden, um Animationen an ein oder mehrere Objekte anzuordnen und zu verteilen. Ein Beispiel finden Sie unter [Animieren einer Eigenschaft mithilfe eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md).  
  
- **Verwenden lokaler Animationen** (nur <xref:System.Windows.Media.Animation.AnimationTimeline> Code): Sie können Objekte direkt auf die Eigenschaften anwenden, die sie animieren. Ein Beispiel finden Sie unter [Animieren einer Eigenschaft ohne Verwendung eines Storyboards](how-to-animate-a-property-without-using-a-storyboard.md).  
  
- **Mit Uhren** (nur Code): Sie können die Uhrerstellung explizit verwalten und die Animationsuhren zu verteilen.  Ein Beispiel finden Sie unter [Animieren einer Eigenschaft mithilfe einer AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).  
  
 Da Sie sie in Markup und Code verwenden <xref:System.Windows.Media.Animation.Storyboard> können, verwenden die Beispiele in dieser Übersicht Objekte. Die beschriebenen Konzepte können jedoch auf die anderen Methoden der Animation von Eigenschaften angewendet werden.  
  
### <a name="what-is-a-clock"></a>Was ist eine Uhr?  
 Eine Zeitachse beschreibt eigentlich lediglich einen Zeitabschnitt. Es ist das <xref:System.Windows.Media.Animation.Clock> Objekt der Zeitachse, das die eigentliche Arbeit leistet: Es behält den zeitbezogenen Laufzeitstatus für die Zeitachse bei. In den meisten Fällen, z.B. bei Verwendung von Storyboards, wird für die Zeitachse automatisch eine Uhr erstellt. Sie können auch <xref:System.Windows.Media.Animation.Clock> eine explizit <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> eerstellen, indem Sie die Methode verwenden. Weitere Informationen <xref:System.Windows.Media.Animation.Clock> zu Objekten finden Sie in der [Animation und Timing System Overview](animation-and-timing-system-overview.md).  
  
## <a name="why-use-events"></a>Gründe für die Verwendung von Ereignissen  
 Bis auf einen (ausgerichtet am letzten Teilstrich) sind alle interaktiven Zeitsteuerungsvorgänge asynchron. Sie haben keine Möglichkeit, den genauen Zeitpunkt ihrer Ausführung herauszufinden. Dies kann problematisch sein, wenn Sie anderen Code haben, der von Ihrem Zeitsteuerungsvorgang abhängig ist. Angenommen, Sie möchten eine Zeitachse stoppen, die ein Rechteck animiert. Nachdem die Zeitachse gestoppt wurde, können Sie die Farbe des Rechtecks ändern.  
  
 [!code-csharp[events_procedural#NeedForEventsFragment](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#needforeventsfragment)]
 [!code-vb[events_procedural#NeedForEventsFragment](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#needforeventsfragment)]  
  
 Im vorherigen Beispiel kann die zweite Codezeile ausgeführt werden, bevor das Storyboard gestoppt wird. Das liegt daran, dass das Stoppen ein asynchroner Vorgang ist. Wenn das Stoppen einer Zeitachse oder Uhr angefordert wird, wird eine Art „Beendigungsanforderung“ erstellt, die erst nach dem nächsten Teilstrich der Zeitsteuerungs-Engine verarbeitet wird.  
  
 Verwenden Sie zum Ausführen von Befehlen nach dem Abschluss einer Zeitachse Zeitsteuerungsereignisse. Im folgenden Beispiel wird ein Ereignishandler verwendet, um die Farbe eines Rechtecks ändern, nachdem die Storyboard-Wiedergabe gestoppt wurde.  
  
 [!code-csharp[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#registerforstoryboardcurrentstateinvalidatedevent)]
 [!code-vb[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#registerforstoryboardcurrentstateinvalidatedevent)]  
[!code-csharp[events_procedural#StoryboardCurrentStateInvalidatedEvent2](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#storyboardcurrentstateinvalidatedevent2)]
[!code-vb[events_procedural#StoryboardCurrentStateInvalidatedEvent2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#storyboardcurrentstateinvalidatedevent2)]  
  
 Ein vollständigeres Beispiel finden Sie unter Empfangen von [Benachrichtigungen, wenn sich der Status einer Uhr ändert.](how-to-receive-notification-when-clock-state-changes.md)  
  
## <a name="public-events"></a>Öffentliche Ereignisse  
 Die <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Clock> und die Klassen bieten fünf Timing-Ereignisse. Die folgende Tabelle enthält diese Ereignisse und die Umstände, die sie auslösen.  
  
|Ereignis|Auslösen von interaktiven Vorgängen|Andere Trigger|  
|-----------|--------------------------------------|--------------------|  
|**Erledigt**|Zur Füllung überspringen|Die Uhr wird beendet.|  
|**CurrentGlobalSpeedInvalidated**|Anhalten, Fortsetzen, Suchen, Geschwindigkeitsverhältnis festlegen, Zur Füllung überspringen, Stoppen|Die Uhr kehrt um, beschleunigt, startet oder stoppt.|  
|**CurrentStateInvalidated**|Beginnen, Zur Füllung überspringen, Stoppen|Die Uhr startet, stoppt oder füllt.|  
|**CurrentTimeInvalidated**|Beginnen, Suchen, Zur Füllung überspringen, Stoppen|Die Uhr läuft.|  
|**RemoveRequested**|Remove (Entfernen)||  
  
## <a name="ticking-and-event-consolidation"></a>Teilstrich- und Ereigniskonsolidierung  
 Wenn Sie Objekte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]in animieren, ist es die Timing-Engine, die Ihre Animationen verwaltet. Die Zeitsteuerungs-Engine verfolgt den zeitlichen Ablauf und berechnet den Status der einzelnen Animationen. In einer Sekunde werden viele dieser Auswertungsdurchläufe durchgeführt. Die Auswertungsdurchläufe heißen „Teilstriche“.  
  
 Wenn Ticks häufiger auftreten, kann zwischen den einzelnen Ticks Vieles geschehen. Beispielsweise kann eine Zeitachse gestoppt, gestartet und wieder gestoppt werden. In diesem Fall ändert sich ihr aktueller Status drei Mal. Theoretisch kann das Ereignis mehrere Male in einem Teilstrich ausgelöst werden. Die Zeitsteuerungs-Engine konsolidiert jedoch Ereignisse, damit jedes Ereignis höchstens einmal pro Teilstrich ausgelöst werden kann.  
  
## <a name="registering-for-events"></a>Registrieren für Ereignisse  
 Es gibt mehrere Möglichkeiten, um sich für Zeitsteuerungsereignisse zu registrieren: Sie könne sich bei der Zeitachse oder der aus der Zeitachse erstellten Uhr registrieren. Registrierung für ein Ereignis direkt bei einer Uhr ist relativ einfach, obwohl sie nur über Code ausgeführt werden kann. Sie können sich über Markup oder Code für Ereignisse bei einer Zeitachse registrieren. Im nächsten Abschnitt wird beschrieben, wie sie sich für Uhrereignisse bei einer Zeitachse registrieren.  
  
<a name="registeringforclockeventswithatimeline"></a>
## <a name="registering-for-clock-events-with-a-timeline"></a>Registrieren für Uhrereignisse bei einer Zeitachse  
 <xref:System.Windows.Media.Animation.Timeline.Completed>Obwohl die Ereignisse <xref:System.Windows.Media.Animation.Timeline.CurrentGlobalSpeedInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> <xref:System.Windows.Media.Animation.Timeline.CurrentTimeInvalidated>, <xref:System.Windows.Media.Animation.Timeline.RemoveRequested> , und Ereignisse einer Zeitachse der Zeitachse zugeordnet zu sein <xref:System.Windows.Media.Animation.Clock> scheinen, ordnet die Registrierung für diese Ereignisse tatsächlich einen Ereignishandler dem für die Zeitachse erstellten Ereignishandler zu.  
  
 Wenn Sie sich <xref:System.Windows.Media.Animation.Timeline.Completed> z. B. auf einer Zeitachse für das Ereignis <xref:System.Windows.Media.Animation.Clock.Completed> registrieren, sagen Sie dem System, dass es sich für das Ereignis jeder Uhr registrieren soll, die für die Zeitachse erstellt wird. Im Code müssen Sie sich für <xref:System.Windows.Media.Animation.Clock> dieses Ereignis registrieren, bevor der für diese Zeitachse erstellt wird. Andernfalls erhalten Sie keine Benachrichtigung. Dies geschieht [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]automatisch in ; Der Parser registriert sich automatisch <xref:System.Windows.Media.Animation.Clock> für das Ereignis, bevor der erstellt wird.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über das Animations- und Zeitsteuerungssystem](animation-and-timing-system-overview.md)
- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über Zeitsteuerungsverhalten](timing-behaviors-overview.md)
