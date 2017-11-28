---
title: "Deklarieren und Auslösen von Ereignissen (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0bf75cfba5102be5d837af385e2d3578f78a03c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen (Visual Basic)
Diese exemplarische Vorgehensweise veranschaulicht, wie deklarieren und Auslösen von Ereignissen für eine Klasse mit dem Namen `Widget`. Nachdem Sie die Schritte abgeschlossen haben, möglicherweise möchten die Begleit-Thema zu lesen [Exemplarische Vorgehensweise: Behandeln von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), die zeigt, wie Ereignisse aus `Widget` Objekte Statusinformationen in einer Anwendung bereitstellen.  
  
## <a name="the-widget-class"></a>Das Widget-Klasse  
 Angenommen, für den Moment, die Sie eine `Widget` Klasse. Die `Widget` -Klasse verfügt über eine Methode, die eine lange Zeit in Anspruch nehmen kann, und Sie möchten die Anwendung aus, um eine Art des Indikators Abschluss erstellen zu können.  
  
 Natürlich müssen Sie womöglich die `Widget` Objekt ein Prozent abgeschlossen Dialogfeld anzeigen, aber hängen mit diesem Dialogfeld in jedem Projekt, in dem Sie verwendet, die `Widget` Klasse. Ein gutes Prinzip der Objektdesign die Anwendung zu ermöglichen, das ein Objekthandle der Benutzeroberfläche verwendet werden – es sei denn, die gesamte des Objekts dient zum Verwalten von einem Formular oder Dialogfeld Feld.  
  
 Der Zweck der `Widget` andere Aufgaben ausführen, daher ist es besser, hinzuzufügen eine `PercentDone` Ereignis und legen Sie die Prozedur, die aufruft `Widget`Methoden des behandeln zu können, Ereignis und die Statusanzeige. Die `PercentDone` Ereignis kann auch einen Mechanismus zum Abbrechen der Aufgabe bereitstellen.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>Das Codebeispiel in diesem Thema erstellen  
  
1.  Öffnen Sie ein neues [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows-Anwendung und erstellen Sie ein Formular mit dem Namen `Form1`.  
  
2.  Fügen Sie zwei Schaltflächen und eine Bezeichnung für die `Form1`.  
  
3.  Benennen Sie die Objekte wie in der folgenden Tabelle gezeigt.  
  
    |Objekt|Eigenschaft|Einstellung|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Startaufgabe|  
    |`Button2`|`Text`|Abbrechen|  
    |`Label`|`(Name)`, `Text`|LblPercentDone, 0|  
  
4.  Auf der **Projekt** Menü Wählen Sie **Klasse hinzufügen** hinzufügen eine Klasse mit dem Namen `Widget.vb` zum Projekt.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Deklariert ein Ereignis für die Widget-Klasse  
  
-   Verwenden der `Event` -Schlüsselwort zu deklarieren, ein Ereignis in der `Widget` Klasse. Beachten Sie, dass ein Ereignis kann `ByVal` und `ByRef` Argumente als `Widget`des `PercentDone` Ereignis veranschaulicht:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]  
  
 Wenn das aufrufende Objekt empfängt ein `PercentDone` Ereignis, das `Percent` -Argument enthält den Prozentsatz der Aufgabe, die abgeschlossen ist. Die `Cancel` Argument festgelegt werden kann, um `True` zum Abbrechen der Methode, die das Ereignis ausgelöst hat.  
  
> [!NOTE]
>  Sie können Ereignisargumente deklarieren, ebenso wie die Argumente von Prozeduren mit den folgenden Ausnahmen: Ereignisse sind keine `Optional` oder `ParamArray` Argumente und Ereignisse müssen keine Werte zurückgeben.  
  
 Die `PercentDone` Ereignis wird ausgelöst, durch die `LongTask` Methode der `Widget` Klasse. `LongTask`akzeptiert zwei Argumente: die Zeitspanne arbeiten und die minimale Zeitintervall vor dem Ausführen der Methode vorgegeben `LongTask` Pausen zum Auslösen der `PercentDone` Ereignis.  
  
#### <a name="to-raise-the-percentdone-event"></a>Zum Auslösen des Ereignisses PercentDone  
  
1.  Zur Vereinfachung der Zugriff auf die `Timer` Eigenschaft, die von dieser Klasse verwendete hinzufügen ein `Imports` Anweisungen am Anfang des Abschnitts Deklarationen Ihrer Klassenmodul oberhalb der `Class Widget` Anweisung.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]  
  
2.  Fügen Sie der `Widget` -Klasse folgenden Code hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]  
  
 Bei einem Aufruf der `LongTask` -Methode, die `Widget` -Klasse ausgelösten der `PercentDone` Ereignis jede `MinimumInterval` Sekunden. Wenn das Ereignis zurückgegeben wird, `LongTask` überprüft, ob die `Cancel` Argument wurde festgelegt, um `True`.  
  
 Hier sind einige Haftungsausschlüsse erforderlich. Zur Vereinfachung der `LongTask` vorausgesetzt Sie Weiß im voraus, wie lange der Vorgang dauert. Dies ist fast nie die Groß-/Kleinschreibung. Unterteilen Aufgaben in Blöcke von gleichmäßiger Größe kann schwierig sein, und häufig die meisten Benutzer wichtig ist einfach die Zeitspanne, die schon vorbei, bevor erhalten sie einen Hinweis darauf, dass etwas geschehen ist.  
  
 Möglicherweise haben Sie ein weiterer Nachteil in diesem Beispiel entdeckt. Die `Timer` Eigenschaft gibt die Anzahl der Sekunden an, die seit Mitternacht vergangenen; die Anwendung ruft daher hängen, wenn sie unmittelbar vor Mitternacht gestartet wird. Ein mehr eine sorgfältige Ansatz zum Messen der Zeit Grenze Bedingungen wie z. B. Dies berücksichtigt werden würde, oder verzichten sie, wie z. B. mithilfe von Eigenschaften `Now`.  
  
 Nachdem die `Widget` Klasse Ereignisse auslösen kann, können Sie auf der nächsten exemplarischen Vorgehensweise verschieben. [Exemplarische Vorgehensweise: Behandlung von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) veranschaulicht, wie `WithEvents` , ordnen Sie einen Ereignishandler mit dem `PercentDone` Ereignis.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>  
 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>  
 [Exemplarische Vorgehensweise: Behandeln von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)  
 [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)
