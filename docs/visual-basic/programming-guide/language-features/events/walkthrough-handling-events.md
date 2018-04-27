---
title: Behandlung von Ereignissen (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c1743e5f5d9dcdf83ab646407cd1fcdc77ff71cd
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-handling-events-visual-basic"></a>Exemplarische Vorgehensweise: Behandeln von Ereignissen (Visual Basic)
Dies ist die zweite von zwei Themen, die zum Arbeiten mit Ereignissen zu veranschaulichen. Das erste Thema [Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), deklarieren und Auslösen von Ereignissen veranschaulicht. In diesem Abschnitt werden das Formular und die Klasse aus der dieser exemplarischen Vorgehensweise verwendet, um die zeigen, wie Sie das Behandeln von Ereignissen, die sie vorgenommen werden.  
  
 Die `Widget` Klasse-Beispiel verwendet die herkömmliche Ereignisbehandlung Anweisungen. Visual Basic bietet andere Techniken zum Arbeiten mit Ereignissen. Als Übung, können Sie ändern, in diesem Beispiel verwendet die `AddHandler` und `Handles` Anweisungen.  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>Behandlung des Ereignisses PercentDone der Widget-Klasse  
  
1.  Fügen Sie den folgenden Code in `Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]  
  
     Die `WithEvents` Schlüsselwort Gibt an, dass die Variable `mWidget` wird verwendet, um ein Objekt Ereignisse zu behandeln. Sie geben die Art des Objekts, indem der Name der Klasse, von der das Objekt erstellt wird.  
  
     Die Variable `mWidget` im deklarierten `Form1` da `WithEvents` Variablen auf Klassenebene sein müssen. Dies gilt unabhängig vom Typ der Klasse, die in den sie eingefügt.  
  
     Die Variable `mblnCancel` wird verwendet, um das Abbrechen der `LongTask` Methode.  
  
## <a name="writing-code-to-handle-an-event"></a>Schreiben von Code zum Behandeln eines Ereignisses  
 Sobald Sie deklarieren eine Variable mit `WithEvents`, der Variablennamen angezeigt, in der linken Dropdownliste der Klasse **Code-Editor**. Bei Auswahl `mWidget`die `Widget` Klasse Ereignisse in der rechten Dropdownliste angezeigt werden. Auswahl eines Ereignisses wird der entsprechende Ereignisprozedur mit dem Präfix `mWidget` und einen Unterstrich. Alle zugeordneten Ereignisprozeduren eine `WithEvents` Variable den Variablennamen als Präfix erhalten.  
  
#### <a name="to-handle-an-event"></a>So behandeln Sie ein Ereignis  
  
1.  Wählen Sie `mWidget` aus der linken Dropdownliste in der **Code-Editor**.  
  
2.  Wählen Sie die `PercentDone` Ereignis aus der rechten Dropdownliste. Die **Code-Editor** öffnet die `mWidget_PercentDone` Ereignisprozedur.  
  
    > [!NOTE]
    >  Die **Code-Editor** ist nützlich, aber nicht erforderlich, für das Einfügen von neuen Ereignishandler. In dieser exemplarischen Vorgehensweise ist es eine direktere an die Ereignishandler einfach direkt in den Code zu kopieren.  
  
3.  Fügen Sie dem `mWidget_PercentDone`-Ereignishandler folgenden Code hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]  
  
     Wenn die `PercentDone` Ereignis wird ausgelöst, der die Ereignisprozedur zeigt die abgeschlossenen Prozentsatz in einer `Label` Steuerelement. Die `DoEvents` Methode ermöglicht die Bezeichnung zu zeichnen, und gibt dem Benutzer die Möglichkeit, klicken Sie auf die **"Abbrechen"** Schaltfläche.  
  
4.  Fügen Sie den folgenden Code für die `Button2_Click` Ereignishandler:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]  
  
 Wenn der Benutzer klickt der **"Abbrechen"** Schaltfläche beim `LongTask` ausgeführt wird, die `Button2_Click` Ereignis ausgeführt wird, sobald der `DoEvents` -Anweisung erlaubt die Verarbeitung von Ereignissen auftreten. Der Variablen auf Klassenebene `mblnCancel` auf festgelegt ist `True`, und die `mWidget_PercentDone` Ereignis überprüft, und legt die `ByRef Cancel` Argument für `True`.  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>Herstellen einer Verbindung eine WithEvents-Variable auf ein Objekt  
 `Form1` ist nun eingerichtet, behandeln eine `Widget` Ereignisse des Objekts. Übrig bleibt zum Suchen einer `Widget` an einer beliebigen Stelle.  
  
 Wenn Sie eine Variable deklarieren `WithEvents` zur Entwurfszeit kein Objekt zugeordnet ist. Ein `WithEvents` Variable ist, genau wie jede andere Objektvariable. Sie haben ein Objekt erstellt, und weisen Sie einen Verweis darauf mit der `WithEvents` Variable.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>Ein Objekt erstellt, und weisen Sie einen Verweis darauf  
  
1.  Wählen Sie **(Form1-Ereignisse)** aus der linken Dropdownliste in der **Code-Editor**.  
  
2.  Wählen Sie die `Load` Ereignis aus der rechten Dropdownliste. Die **Code-Editor** öffnet die `Form1_Load` Ereignisprozedur.  
  
3.  Fügen Sie den folgenden Code für die `Form1_Load` Ereignisprozedur zum Erstellen der `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]  
  
 Wenn dieser Code ausgeführt wird, erstellt Visual Basic eine `Widget` -Objekt und verbindet die zugehörigen Ereignisse auf die zugeordnete Ereignisprozeduren `mWidget`. Von diesem Zeitpunkt an, wenn die `Widget` löst seine `PercentDone` -Ereignis der `mWidget_PercentDone` Ereignisprozedur ausgeführt wird.  
  
#### <a name="to-call-the-longtask-method"></a>Zum Aufrufen der LongTask-Methode  
  
-   Fügen Sie dem `Button1_Click`-Ereignishandler folgenden Code hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]  
  
 Bevor Sie die `LongTask` -Methode aufgerufen wird, wird die Bezeichnung zeigt den Prozentsatz der Fertigstellung initialisiert werden müssen, und der Klassenebene `Boolean` flag für das Abbrechen der Methodennamens festgelegt werden muss, `False`.  
  
 `LongTask` wird mit einer Aufgabendauer von 12,2 Sekunden aufgerufen. Die `PercentDone` Ereignis wird ausgelöst, einmal alle ein Drittel von einer Sekunde. Jedes Mal, die das Ereignis ausgelöst wird, die `mWidget_PercentDone` Ereignisprozedur ausgeführt wird.  
  
 Wenn `LongTask` erfolgt, `mblnCancel` wird getestet, um konsultieren `LongTask` normal beendet oder angehalten wurde, weil `mblnCancel` wurde festgelegt, um `True`. Der Prozentsatz der Fertigstellung wird nur im ersten Fall aktualisiert.  
  
#### <a name="to-run-the-program"></a>So führen Sie das Programm aus  
  
1.  Drücken Sie F5, um das Projekt im Ausführungsmodus.  
  
2.  Klicken Sie auf die **Aufgabe starten** Schaltfläche. Jedes Mal die `PercentDone` Ereignis ausgelöst wird, wird die Bezeichnung mit dem Prozentsatz der Aufgabe, die abgeschlossen wird aktualisiert.  
  
3.  Klicken Sie auf die **"Abbrechen"** Schaltfläche, um den Vorgang zu beenden. Beachten Sie, dass die Darstellung der **"Abbrechen"** Schaltfläche nicht direkt ändert, wenn Sie darauf klicken. Die `Click` Ereignis nicht auftreten, bis die `My.Application.DoEvents` -Anweisung erlaubt die Verarbeitung von Ereignissen.  
  
    > [!NOTE]
    >  Die `My.Application.DoEvents` -Methode verarbeitet Ereignisse nicht auf genau die gleiche Weise wie das Formular. Klicken Sie beispielsweise in dieser exemplarischen Vorgehensweise, Sie müssen auf die **"Abbrechen"** zweimal Schaltfläche. Damit wird das Formular, um die Ereignisse direkt verarbeiten, können Sie multithreading. Weitere Informationen finden Sie unter [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).  
  
 Sie finden es vielleicht hilfreich, das Programm mit F11 auszuführen und den Code zeilenweise durchlaufen. Klar erkennbar, wie die Ausführung eingibt `LongTask`, und klicken Sie dann eine kurze wieder hinzugefügt `Form1` jedes Mal die `PercentDone` Ereignis wird ausgelöst.  
  
 Was geschieht, If, während der Ausführung wieder in den Code der war `Form1`, die `LongTask` Methode erneut aufrufen würden? Im schlimmsten Fall kann ein Stapelüberlauf auftreten, wenn `LongTask` aufgerufen wurden, jedes Mal, wenn das Ereignis ausgelöst wurde.  
  
 Sie können dazu führen, dass die Variable `mWidget` zum Behandeln von Ereignissen für einen anderen `Widget` Objekt, indem Sie einen Verweis auf das neue `Widget` auf `mWidget`. Tatsächlich können Sie den Code in vornehmen `Button1_Click` dazu jedes Mal, wenn Sie auf die Schaltfläche klicken.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>So behandeln Sie Ereignisse für einen anderen Widgets  
  
-   Fügen Sie die folgende Codezeile, die `Button1_Click` Prozedur, die direkt vor der Zeile `mWidget.LongTask(12.2, 0.33)`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]  
  
 Der obige Code erstellt ein neues `Widget` jedes Mal die Schaltfläche geklickt wird. Sobald die `LongTask` Methode ausgeführt wird, den Verweis auf die `Widget` freigegeben wird, und die `Widget` zerstört wird.  
  
 Ein `WithEvents` Variable darf nur einen Objektverweis zu einem Zeitpunkt, wenn Sie ein anderes zuweisen `Widget` -Objekt `mWidget`, der vorherigen `Widget` objektspezifischen Ereignisse werden nicht mehr bearbeitet werden. Wenn `mWidget` ist die einzige Object-Variablen, die mit einem Verweis auf das alte `Widget`, das Objekt zerstört wird. Wenn Sie mehrere Ereignisse behandeln möchten `Widget` Objekte, verwenden die `AddHandler` Anweisung, um Ereignisse aus jedem Objekt separat zu verarbeiten.  
  
> [!NOTE]
>  Sie können beliebig viele deklarieren `WithEvents` Variablen als Sie benötigen, aber Arrays von `WithEvents` Variablen werden nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)  
 [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)
