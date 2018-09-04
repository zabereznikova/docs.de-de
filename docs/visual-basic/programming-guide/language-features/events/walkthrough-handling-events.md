---
title: Behandeln von Ereignissen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
ms.openlocfilehash: 3ade8eae67d29e2f3cb42911e42ed8696623db62
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507897"
---
# <a name="walkthrough-handling-events-visual-basic"></a>Exemplarische Vorgehensweise: Behandeln von Ereignissen (Visual Basic)
Dies ist die zweite von zwei Themen, die veranschaulichen, wie Sie mit Ereignissen zu arbeiten. Das erste Thema [Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), deklarieren und Auslösen von Ereignissen veranschaulicht. In diesem Abschnitt werden das Formular und die Klasse aus dieser exemplarischen Vorgehensweise verwendet, um die zeigen, wie Sie behandeln Ereignisse aus, wenn sie auftreten.  
  
 Die `Widget` Klassenbeispiel werden herkömmliche Ereignisbehandlung-Anweisungen verwendet. Visual Basic bietet andere Techniken zum Arbeiten mit Ereignissen. Als Übung ausführen, können Sie in diesem Beispiel verwendet die `AddHandler` und `Handles` Anweisungen.  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>Zum Behandeln des Ereignisses PercentDone der Widget-Klasse  
  
1.  Platzieren Sie den folgenden Code in `Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]  
  
     Die `WithEvents` Schlüsselwort Gibt an, dass die Variable `mWidget` dient zur Verarbeitung der Ereignisse eines Objekts. Geben Sie die Art des Objekts, indem der Name der Klasse aus der das Objekt erstellt wird.  
  
     Die Variable `mWidget` im deklarierten `Form1` da `WithEvents` Variablen müssen auf Klassenebene sein. Dies gilt unabhängig vom Typ der Klasse, die in den sie eingefügt.  
  
     Die Variable `mblnCancel` wird verwendet, um das Abbrechen der `LongTask` Methode.  
  
## <a name="writing-code-to-handle-an-event"></a>Schreiben von Code zum Behandeln eines Ereignisses  
 Sobald Sie deklarieren eine Variable mit `WithEvents`, den Namen der Variable wird angezeigt, in der linken Dropdown-Liste von der Klasse **Code-Editor**. Bei der Auswahl `mWidget`, `Widget` -Klasse-Ereignisse in der rechten Dropdownliste angezeigt werden. Wenn Sie ein Ereignis auswählen, werden die entsprechende Ereignisprozedur mit dem Präfix `mWidget` und einen Unterstrich. Alle zugeordneten Ereignisprozeduren eine `WithEvents` Variable den Namen den Variablen ein Präfix erhalten.  
  
#### <a name="to-handle-an-event"></a>So behandeln Sie ein Ereignis  
  
1.  Wählen Sie `mWidget` aus der linken Dropdownliste in der **Code-Editor**.  
  
2.  Wählen Sie die `PercentDone` Ereignis von der rechten Dropdownliste aus. Die **Code-Editor** öffnet die `mWidget_PercentDone` Ereignisprozedur.  
  
    > [!NOTE]
    >  Die **Code-Editor** ist nützlich, aber nicht erforderlich, für das Einfügen von neuen Ereignishandler. In dieser exemplarischen Vorgehensweise ist es direktere Ereignishandler nur direkt in Ihren Code zu kopieren.  
  
3.  Fügen Sie dem `mWidget_PercentDone`-Ereignishandler folgenden Code hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]  
  
     Wenn die `PercentDone` -Ereignis ausgelöst wird, der die Ereignisprozedur zeigt die abgeschlossenen Prozentsatz in eine `Label` Steuerelement. Die `DoEvents` Methode ermöglicht die Bezeichnung neu zu zeichnen, und gibt dem Benutzer die Möglichkeit, klicken Sie auf die **Abbrechen** Schaltfläche.  
  
4.  Fügen Sie den folgenden Code für die `Button2_Click` -Ereignishandler:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]  
  
 Wenn der Benutzer klickt der **Abbrechen** Schaltfläche beim `LongTask` ausgeführt wird, die `Button2_Click` -Ereignis immer ausgeführt wird, sobald die `DoEvents` -Anweisung können die Verarbeitung von Ereignissen auftreten. Die Variable auf Klassenebene `mblnCancel` nastaven NA hodnotu `True`, und die `mWidget_PercentDone` Ereignis überprüft, und legt sie fest der `ByRef Cancel` Argument `True`.  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>Herstellen einer Verbindung eine WithEvents-Variable auf ein Objekt  
 `Form1` ist nun eingerichtet, behandeln eine `Widget` Ereignisse des Objekts. Übrig bleibt, finden Sie eine `Widget` an einer beliebigen Stelle.  
  
 Wenn Sie eine Variable deklarieren `WithEvents` zur Entwurfszeit, kein Objekt zugeordnet ist. Ein `WithEvents` Variable ist, genau wie jede andere Objektvariable. Müssen Sie ein Objekt erstellen, und weisen Sie einen Verweis darauf mit der `WithEvents` Variable.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>Erstellen Sie ein Objekt, und weisen Sie einen Verweis darauf  
  
1.  Wählen Sie **(Form1-Ereignisse)** aus der linken Dropdownliste in der **Code-Editor**.  
  
2.  Wählen Sie die `Load` Ereignis von der rechten Dropdownliste aus. Die **Code-Editor** öffnet die `Form1_Load` Ereignisprozedur.  
  
3.  Fügen Sie den folgenden Code für die `Form1_Load` Ereignis Verfahren zum Erstellen der `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]  
  
 Wenn dieser Code ausgeführt wird, erstellt Visual Basic eine `Widget` Objekt aus, und verbindet die zugehörigen Ereignisse mit den zugeordneten Ereignisprozeduren `mWidget`. Von diesem Zeitpunkt an, wenn die `Widget` löst die `PercentDone` -Ereignis, das `mWidget_PercentDone` Ereignisprozedur ausgeführt wird.  
  
#### <a name="to-call-the-longtask-method"></a>Zum Aufrufen der Methode von LongTask  
  
-   Fügen Sie dem `Button1_Click`-Ereignishandler folgenden Code hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]  
  
 Bevor Sie die `LongTask` -Methode aufgerufen wird, wird die Bezeichnung an, dass der Fortschritt in Prozent angezeigt, die initialisiert werden müssen, und die auf Klassenebene `Boolean` flag für das Abbrechen der Methode festgelegt werden muss, `False`.  
  
 `LongTask` wird mit einer Dauer für die Aufgabe von 12,2 Sekunden aufgerufen. Die `PercentDone` Ereignis wird ausgelöst, einmal alle ein Drittel einer Sekunde. Jedes Mal, die das Ereignis ausgelöst wird, die `mWidget_PercentDone` Ereignisprozedur ausgeführt wird.  
  
 Wenn `LongTask` erfolgt, `mblnCancel` wird getestet, um finden Sie unter `LongTask` normal beendet oder angehalten wurde, weil `mblnCancel` wurde `True`. Der Prozentsatz der Fertigstellung wird nur im ersten Fall aktualisiert.  
  
#### <a name="to-run-the-program"></a>So führen Sie das Programm aus  
  
1.  Drücken Sie F5, um das Projekt im Ausführungsmodus.  
  
2.  Klicken Sie auf die **Starttask** Schaltfläche. Jedes Mal die `PercentDone` -Ereignis ausgelöst wird, die Bezeichnung wird aktualisiert, mit dem Prozentsatz der der Vorgang abgeschlossen ist.  
  
3.  Klicken Sie auf die **Abbrechen** Schaltfläche, um den Vorgang zu beenden. Beachten Sie, dass die Darstellung der **Abbrechen** Schaltfläche nicht direkt ändert, wenn Sie darauf klicken. Die `Click` Ereignis kann nicht ausgeführt, bis die `My.Application.DoEvents` -Anweisung können die Verarbeitung von Ereignissen.  
  
    > [!NOTE]
    >  Die `My.Application.DoEvents` -Methode verarbeitet Ereignisse nicht in die gleiche Weise wie das Formular. Klicken Sie beispielsweise in dieser exemplarischen Vorgehensweise, Sie müssen auf die **Abbrechen** Schaltfläche zweimal. Damit das Formular, um die Ereignisse direkt verarbeiten kann, können Sie multithreading. Weitere Informationen finden Sie unter [Threading](https://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).  
  
 Möglicherweise ist es lehrreich, führen Sie das Programm durch Drücken von F11 und den Code zu einem Zeitpunkt durchlaufen. Klar erkennbar, wie die Ausführung beginnt `LongTask`, und klicken Sie dann kurz erneut eingegeben `Form1` jedes Mal die `PercentDone` Ereignis wird ausgelöst.  
  
 Was geschieht, If, während der Ausführung wieder im Code war `Form1`, `LongTask` Methode erneut aufrufen würden? Im schlimmsten Fall kann ein Stapelüberlauf auftreten, wenn `LongTask` aufgerufen wurden, jedes Mal, wenn das Ereignis ausgelöst wurde.  
  
 Sie können dazu führen, dass die Variable `mWidget` zum Behandeln von Ereignissen für ein anderes `Widget` Objekt durch einen Verweis auf das neue zuweisen `Widget` zu `mWidget`. In der Tat können Sie den Code in vornehmen `Button1_Click` dazu jedes Mal, wenn Sie auf die Schaltfläche klicken.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>Zum Behandeln von Ereignissen für einen anderen widget  
  
-   Fügen Sie die folgende Codezeile, die `Button1_Click` Prozedur, die unmittelbar vor der Zeile `mWidget.LongTask(12.2, 0.33)`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]  
  
 Der obige Code erstellt ein neues `Widget` jedes Mal die Schaltfläche geklickt wird. Sobald die `LongTask` Methode ausgeführt wird, den Verweis auf die `Widget` freigegeben wird, und die `Widget` zerstört wird.  
  
 Ein `WithEvents` Variable darf nur einen Objektverweis zu einem Zeitpunkt, wenn Sie einen anderen zuweisen `Widget` -Objekt `mWidget`, der vorherigen `Widget` des Objekts Ereignisse werden nicht mehr bearbeitet werden. Wenn `mWidget` ist die einzige Objektvariable, die mit einem Verweis auf das alte `Widget`, das Objekt zerstört wird. Wenn mehrere Ereignisse behandelt werden sollen `Widget` Objekte zu verwenden, die `AddHandler` Anweisung, um Ereignisse aus jedem Objekt separat zu verarbeiten.  
  
> [!NOTE]
>  Sie können beliebig viele deklarieren `WithEvents` Variablen benötigen, aber Arrays von `WithEvents` Variablen werden nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)  
 [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)
