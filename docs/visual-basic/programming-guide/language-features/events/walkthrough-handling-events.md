---
title: Behandeln von Ereignissen
ms.date: 07/20/2015
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
ms.openlocfilehash: cb42f2e41e366cf8765cb9395d1a5641434bab40
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345080"
---
# <a name="walkthrough-handling-events-visual-basic"></a>Exemplarische Vorgehensweise: Behandeln von Ereignissen (Visual Basic)
Dies ist der zweite von zwei Themen, die veranschaulichen, wie mit Ereignissen gearbeitet wird. Das erste Thema, Exemplarische Vorgehensweise [: Deklarieren und Auswerfen von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), zeigt, wie Sie Ereignisse deklarieren und Auswerfen. In diesem Abschnitt wird das Formular und die Klasse aus dieser exemplarischen Vorgehensweise verwendet, um zu veranschaulichen, wie Ereignisse behandelt werden.  
  
 Im Beispiel für die `Widget`-Klasse werden herkömmliche Ereignis behandlungsanweisungen verwendet. Visual Basic bietet weitere Techniken zum Arbeiten mit Ereignissen. Als Übung können Sie dieses Beispiel so ändern, dass die Anweisungen `AddHandler` und `Handles` verwendet werden.  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>So behandeln Sie das Ereignis "-Ereignis" der Widget-Klasse  
  
1. Fügen Sie den folgenden Code in `Form1`ein:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#4)]  
  
     Das `WithEvents`-Schlüsselwort gibt an, dass die Variable `mWidget` verwendet wird, um die Ereignisse eines Objekts zu verarbeiten. Sie geben die Art des Objekts an, indem Sie den Namen der Klasse angeben, aus der das Objekt erstellt wird.  
  
     Die Variable `mWidget` wird in `Form1` deklariert, da `WithEvents` Variablen auf Klassenebene basieren müssen. Dies gilt unabhängig vom Typ der Klasse, in der Sie Sie platzieren.  
  
     Die Variable `mblnCancel` wird verwendet, um die `LongTask` Methode abzubrechen.  
  
## <a name="writing-code-to-handle-an-event"></a>Schreiben von Code zum Behandeln eines Ereignisses  
 Sobald Sie eine Variable mit `WithEvents`deklarieren, wird der Variablenname in der linken Dropdown Liste des **Code-Editors**der Klasse angezeigt. Wenn Sie `mWidget`auswählen, werden die Ereignisse der `Widget`-Klasse in der rechten Dropdown Liste angezeigt. Wenn Sie ein Ereignis auswählen, wird die entsprechende Ereignis Prozedur mit dem Präfix `mWidget` und einem Unterstrich angezeigt. Alle Ereignis Prozeduren, die einer `WithEvents` Variablen zugeordnet sind, erhalten den Variablennamen als Präfix.  
  
#### <a name="to-handle-an-event"></a>So behandeln Sie ein Ereignis  
  
1. Wählen Sie im **Code-Editor**in der Dropdown Liste links die Option `mWidget` aus.  
  
2. Wählen Sie das `PercentDone`-Ereignis in der rechten Dropdown Liste aus. Der **Code-Editor** öffnet die `mWidget_PercentDone` Ereignis Prozedur.  
  
    > [!NOTE]
    > Der **Code-Editor** ist für das Einfügen neuer Ereignishandler nützlich, jedoch nicht erforderlich. In dieser exemplarischen Vorgehensweise ist es direkter, einfach die Ereignishandler direkt in Ihren Code zu kopieren.  
  
3. Fügen Sie dem `mWidget_PercentDone` -Ereignishandler folgenden Code hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#5)]  
  
     Wenn das `PercentDone`-Ereignis ausgelöst wird, zeigt die Ereignis Prozedur den in einem `Label`-Steuerelement abgeschlossenen Prozentsatz an. Mit der `DoEvents`-Methode kann die Bezeichnung neu gezeichnet werden, und der Benutzer erhält die Möglichkeit, auf die Schaltfläche " **Abbrechen** " zu klicken.  
  
4. Fügen Sie den folgenden Code für den `Button2_Click`-Ereignishandler hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#6)]  
  
 Wenn der Benutzer auf die Schaltfläche **Abbrechen** klickt, während `LongTask` ausgeführt wird, wird das `Button2_Click`-Ereignis ausgeführt, sobald die `DoEvents`-Anweisung das Eintreten der Ereignisverarbeitung zulässt. Die Variable auf Klassenebene `mblnCancel` ist auf `True`festgelegt, und das `mWidget_PercentDone` Ereignis testet Sie, und legt das `ByRef Cancel`-Argument auf `True`fest.  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>Verbinden einer widervents-Variablen mit einem Objekt  
 `Form1` ist nun so eingerichtet, dass die Ereignisse eines `Widget` Objekts behandelt werden. Sie müssen nur noch eine `Widget` finden.  
  
 Wenn Sie zur Entwurfszeit eine Variable `WithEvents` deklarieren, ist ihr kein Objekt zugeordnet. Eine `WithEvents` Variable ist genau wie jede andere Objekt Variable. Sie müssen ein-Objekt erstellen und einen Verweis darauf mit der `WithEvents`-Variablen zuweisen.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>So erstellen Sie ein Objekt und weisen ihm einen Verweis zu  
  
1. Wählen Sie **(Form1-Ereignisse)** in der linken Dropdown Liste im **Code-Editor**aus.  
  
2. Wählen Sie das `Load`-Ereignis in der rechten Dropdown Liste aus. Der **Code-Editor** öffnet die `Form1_Load` Ereignis Prozedur.  
  
3. Fügen Sie den folgenden Code für die `Form1_Load` Ereignis Prozedur hinzu, um die `Widget`zu erstellen:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#7)]  
  
 Wenn dieser Code ausgeführt wird, erstellt Visual Basic ein `Widget` Objekt und verbindet seine Ereignisse mit den Ereignis Prozeduren, die `mWidget`zugeordnet sind. Ab diesem Zeitpunkt wird die `mWidget_PercentDone` Ereignis Prozedur ausgeführt, wenn die `Widget` das `PercentDone`-Ereignis auslöst.  
  
#### <a name="to-call-the-longtask-method"></a>So greifen Sie auf die LongTask-Methode zu  
  
- Fügen Sie dem `Button1_Click` -Ereignishandler folgenden Code hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#8)]  
  
 Bevor die `LongTask`-Methode aufgerufen wird, muss die Bezeichnung, die den Prozentsatz anzeigt, initialisiert werden, und das `Boolean` Flag auf Klassenebene für das Abbrechen der Methode muss auf `False`festgelegt werden.  
  
 `LongTask` wird mit einer Task Dauer von 12,2 Sekunden aufgerufen. Das `PercentDone`-Ereignis wird einmal alle ein Drittel einer Sekunde ausgelöst. Jedes Mal, wenn das Ereignis ausgelöst wird, wird die `mWidget_PercentDone` Ereignis Prozedur ausgeführt.  
  
 Wenn `LongTask` abgeschlossen ist, wird `mblnCancel` getestet, um zu prüfen, ob `LongTask` normal beendet wurde, oder ob er beendet wurde, weil `mblnCancel` auf `True`festgelegt wurde. Der Prozentsatz der Fertigstellung wird nur im ersten Fall aktualisiert.  
  
#### <a name="to-run-the-program"></a>So führen Sie das Programm aus  
  
1. Drücken Sie F5, um das Projekt in den Testlauf zu versetzen.  
  
2. Klicken Sie auf die Schaltfläche **Task starten** . Jedes Mal, wenn das `PercentDone` Ereignis ausgelöst wird, wird die Bezeichnung mit dem Prozentsatz der abgeschlossenen Aufgabe aktualisiert.  
  
3. Klicken Sie auf die Schaltfläche **Abbrechen** , um den Task zu beenden. Beachten Sie, dass sich die Darstellung der Schaltfläche **Abbrechen** nicht sofort ändert, wenn Sie darauf klicken. Das `Click`-Ereignis kann erst auftreten, wenn die `My.Application.DoEvents`-Anweisung die Ereignisverarbeitung zulässt.  
  
    > [!NOTE]
    > Die `My.Application.DoEvents`-Methode verarbeitet Ereignisse nicht exakt auf die gleiche Weise wie das Formular. Beispielsweise müssen Sie in dieser exemplarischen Vorgehensweise zweimal auf die Schaltfläche **Abbrechen** klicken. Um dem Formular das direkte behandeln der Ereignisse zu ermöglichen, können Sie Multithreading verwenden. Weitere Informationen finden Sie unter [verwaltetes Threading](../../../../standard/threading/index.md).
  
 Sie finden es möglicherweise Lehrweise, das Programm mit F11 auszuführen und den Codezeilen Weise schrittweise durchlaufen. Sie können deutlich erkennen, wie die Ausführung `LongTask`eintritt, und die `Form1` dann bei jedem ausgelöst des `PercentDone` Ereignisses kurz wieder eingibt.  
  
 Was geschieht, wenn die `LongTask`-Methode erneut aufgerufen wurde, während die Ausführung wieder im Code von `Form1`war? Im schlimmsten Fall kann ein Stapelüberlauf auftreten, wenn `LongTask` jedes Mal aufgerufen werden, wenn das Ereignis ausgelöst wurde.  
  
 Sie können bewirken, dass die Variable `mWidget` Ereignisse für ein anderes `Widget` Objekt behandelt, indem Sie einen Verweis auf den neuen `Widget` `mWidget`zuweisen. Tatsächlich können Sie den Code in erstellen, `Button1_Click` diesen Schritt jedes Mal ausführen, wenn Sie auf die Schaltfläche klicken.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>So behandeln Sie Ereignisse für ein anderes widget  
  
- Fügen Sie die folgende Codezeile zur `Button1_Click` Prozedur hinzu, die unmittelbar vor der Zeile steht, die `mWidget.LongTask(12.2, 0.33)`liest:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#9)]  
  
 Der obige Code erstellt einen neuen `Widget` jedes Mal, wenn auf die Schaltfläche geklickt wird. Sobald die `LongTask`-Methode abgeschlossen ist, wird der Verweis auf die `Widget` freigegeben, und die `Widget` wird zerstört.  
  
 Eine `WithEvents` Variable kann jeweils nur einen Objekt Verweis enthalten. Wenn Sie also `mWidget`ein anderes `Widget` Objekt zuweisen, werden die Ereignisse des vorherigen `Widget` Objekts nicht mehr behandelt. Wenn `mWidget` die einzige Objekt Variable ist, die einen Verweis auf die alte `Widget`enthält, wird das Objekt zerstört. Wenn Sie Ereignisse aus mehreren `Widget` Objekten verarbeiten möchten, können Sie die `AddHandler`-Anweisung verwenden, um Ereignisse aus den einzelnen Objekten separat zu verarbeiten.  
  
> [!NOTE]
> Sie können beliebig viele `WithEvents` Variablen deklarieren, aber Arrays von `WithEvents` Variablen werden nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- [Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)
- [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)
