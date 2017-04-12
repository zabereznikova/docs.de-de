---
title: Behandlung von Ereignissen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword, walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 17cd0bddbe8c89cf60e19f3f2af6f448ad465d70
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-handling-events-visual-basic"></a>Exemplarische Vorgehensweise: Behandeln von Ereignissen (Visual Basic)
Dies ist die zweite von zwei Themen, die zum Arbeiten mit Ereignissen zu veranschaulichen. Das erste Thema [Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), zeigt, wie Ereignisse deklariert und ausgelöst. Dieser Abschnitt verwendet die Form und die Klasse aus dieser exemplarischen Vorgehensweise veranschaulicht, wie Ereignisse werden behandelt.  
  
 Die `Widget` Beispiel verwendet herkömmliche Ereignisbehandlung-Anweisungen. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]bietet andere Verfahren zum Arbeiten mit Ereignissen. Als Übung, können Sie dieses Beispiel verwenden Sie ändern die `AddHandler` und `Handles` Anweisungen.  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>Der Widget-Klasse das PercentDone-Ereignis behandeln  
  
1.  Fügen Sie folgenden Code im `Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&4;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]  
  
     Die `WithEvents` Schlüsselwort Gibt an, dass die Variable `mWidget` zum Behandeln der Ereignisse eines Objekts. Geben Sie die Art des Objekts, indem der Name der Klasse, von der das Objekt erstellt wird.  
  
     Die Variable `mWidget` im deklarierten `Form1` da `WithEvents` Variablen auf Klassenebene werden müssen. Dies gilt unabhängig vom Typ der Klasse, die in den sie eingefügt.  
  
     Die Variable `mblnCancel` wird verwendet, um das Abbrechen der `LongTask` Methode.  
  
## <a name="writing-code-to-handle-an-event"></a>Schreiben von Code zum Behandeln eines Ereignisses  
 Sobald Sie deklarieren eine Variable mit `WithEvents`, der Variablennamen angezeigt, in der linken Dropdown-Liste die Klasse **Code-Editor**. Wenn Sie die Option `mWidget`, die `Widget` -Klasse Ereignisse werden in der rechten Dropdownliste angezeigt. Auswahl eines Ereignisses wird die entsprechende Ereignisprozedur mit dem Präfix `mWidget` und der Unterstrich. Alle zugeordneten Ereignisprozeduren eine `WithEvents` Variable den Variablennamen als Präfix erhalten.  
  
#### <a name="to-handle-an-event"></a>So behandeln Sie ein Ereignis  
  
1.  Wählen Sie `mWidget` aus der linken Dropdown-Liste in der **Code-Editor**.  
  
2.  Wählen Sie die `PercentDone` aus der Liste rechts Dropdown-Ereignis. Die **Code-Editor** öffnet der `mWidget_PercentDone` -Ereignisprozedur.  
  
    > [!NOTE]
    >  Die **Code-Editor** ist nützlich, aber nicht erforderlich, für das Einfügen eines neuen Ereignishandler. In dieser exemplarischen Vorgehensweise ist es eine direktere, kopieren Sie die Ereignishandler einfach direkt in den Code.  
  
3.  Fügen Sie dem `mWidget_PercentDone`-Ereignishandler folgenden Code hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&5;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]  
  
     Wenn die `PercentDone` -Ereignis ausgelöst wird, zeigt die Ereignisprozedur die abgeschlossenen Prozentsatz in eine `Label` Steuerelement. Die `DoEvents` -Methode ermöglicht es, die Bezeichnung neu zu zeichnen, und auch dem Benutzer die Möglichkeit, klicken Sie auf die **Abbrechen** Schaltfläche.  
  
4.  Fügen Sie den folgenden Code für den `Button2_Click` -Ereignishandler:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&6;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]  
  
 Klickt der Benutzer auf die **Abbrechen** Schaltfläche `LongTask` ausgeführt wird, die `Button2_Click` Ereignis wird ausgeführt, sobald die `DoEvents` Anweisung ermöglicht die Verarbeitung von Ereignissen auftreten. Die Variable auf Klassenebene `mblnCancel` auf festgelegt ist `True`, und die `mWidget_PercentDone` Ereignis überprüft, und legt die `ByRef Cancel` Argument `True`.  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>Herstellen einer Verbindung eine WithEvents-Variable auf ein Objekt  
 `Form1`ist nun eingerichtet, behandeln eine `Widget` Ereignisse des Objekts. Übrig bleibt, suchen Sie einen `Widget` an.  
  
 Wenn Sie eine Variable deklarieren `WithEvents` zur Entwurfszeit kein Objekt zugeordnet ist. Ein `WithEvents` -Variable funktioniert genau wie jede andere Objektvariable. Sie müssen ein Objekt erstellen, und weisen Sie einen Verweis mit dem `WithEvents` Variable.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>Erstellen Sie ein Objekt und einen Verweis darauf zuweisen  
  
1.  Wählen Sie **(Form1-Ereignisse)** aus der linken Dropdown-Liste in der **Code-Editor**.  
  
2.  Wählen Sie die `Load` aus der Liste rechts Dropdown-Ereignis. Die **Code-Editor** öffnet der `Form1_Load` -Ereignisprozedur.  
  
3.  Fügen Sie den folgenden Code für die `Form1_Load` Ereignis Verfahren zum Erstellen der `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#7;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]  
  
 Wenn dieser Code ausgeführt wird, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] erstellt eine `Widget` -Objekt und verbindet die zugehörigen Ereignisse auf das Ereignis Verfahren im Zusammenhang mit `mWidget`. Von diesem Zeitpunkt an, wenn die `Widget` löst seine `PercentDone` -Ereignis, das `mWidget_PercentDone` Ereignisprozedur ausgeführt wird.  
  
#### <a name="to-call-the-longtask-method"></a>Zum Aufrufen der Methode von LongTask  
  
-   Fügen Sie dem `Button1_Click`-Ereignishandler folgenden Code hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#8;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]  
  
 Bevor Sie die `LongTask` -Methode aufgerufen wird, wird die Bezeichnung, zeigt der abgeschlossene Prozentsatz initialisiert werden müssen, und der Klassenebene `Boolean` flag für das Abbrechen der Methode festgelegt werden muss, `False`.  
  
 `LongTask`wird mit einer Aufgabendauer von 12,2 Sekunden aufgerufen. Das `PercentDone` -Ereignis wird ausgelöst, einmal alle ein Drittel von einer Sekunde. Jedes Mal das Ereignis ausgelöst wird, die `mWidget_PercentDone` Ereignisprozedur ausgeführt wird.  
  
 Wenn `LongTask` erfolgt, `mblnCancel` wird daraufhin überprüft, ob `LongTask` normal beendet oder angehalten wurde, weil `mblnCancel` wurde `True`. Der Prozentsatz der Fertigstellung wird nur im ersten Fall aktualisiert.  
  
#### <a name="to-run-the-program"></a>So führen Sie das Programm aus  
  
1.  Drücken Sie F5, um das Projekt auszuführen.  
  
2.  Klicken Sie auf die **Aufgabe** Schaltfläche. Jedes Mal die `PercentDone` -Ereignis ausgelöst wird, wird die Bezeichnung mit dem Prozentsatz der Aufgabe, die abgeschlossen wurde aktualisiert.  
  
3.  Klicken Sie auf die **Abbrechen** Schaltfläche, um den Vorgang zu beenden. Beachten Sie, dass die Darstellung der **Abbrechen** Schaltfläche nicht direkt ändert, wenn Sie darauf klicken. Die `Click` Ereignis nicht auftreten, bis die `My.Application.DoEvents` Anweisung ermöglicht die Verarbeitung von Ereignissen.  
  
    > [!NOTE]
    >  Die `My.Application.DoEvents` -Methode verarbeitet Ereignisse nicht auf genau die gleiche Weise wie das Formular. Klicken Sie beispielsweise in dieser exemplarischen Vorgehensweise, Sie müssen auf die **Abbrechen** zweimal auf die Schaltfläche. Um das Formular die Ereignisse direkt behandeln kann, können Sie multithreading. Weitere Informationen finden Sie unter [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).  
  
 Möglicherweise ist es hilfreich, das Programm durch Drücken von F11 auszuführen und den Code zu einem Zeitpunkt schrittweise. Klar erkennbar, wie die Ausführung von eingegeben `LongTask`, und klicken Sie dann kurz erneut eingegeben `Form1` jedes Mal die `PercentDone` -Ereignis wird ausgelöst.  
  
 Was geschieht, wenn ist, bei der Ausführung wieder im Code ist `Form1`, die `LongTask` Methode erneut aufrufen würden? Im schlimmsten Fall ein Stapelüberlauf auftreten, wenn `LongTask` aufgerufen wurden, jedes Mal, wenn das Ereignis ausgelöst wurde.  
  
 Veranlassen Sie, dass die Variable `mWidget` zum Behandeln von Ereignissen für eine andere `Widget` Objekt durch einen Verweis auf die neue zuweisen `Widget` auf `mWidget`. In der Tat können Sie den Code in vornehmen `Button1_Click` dazu, jedes Mal, wenn Sie auf die Schaltfläche klicken.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>So behandeln Sie Ereignisse für ein anderes Widget-Objekt  
  
-   Fügen Sie die folgende Codezeile, die `Button1_Click` Verfahren, die unmittelbar vor der Zeile `mWidget.LongTask(12.2, 0.33)`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#9;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]  
  
 Der obige Code erstellt ein neues `Widget` jedes Mal die Schaltfläche geklickt wird. Sobald die `LongTask` Methode ausgeführt wird, den Verweis auf die `Widget` freigegeben wird, und die `Widget` zerstört wird.  
  
 Ein `WithEvents` -Variable kann jeweils nur einen Objektverweis enthalten, wenn Sie eine andere zuweisen `Widget` -Objekt `mWidget`, die vorherige `Widget` Ereignisse des Objekts nicht mehr verarbeitet werden. Wenn `mWidget` ist der einzige Objektvariable einen Verweis auf die alte `Widget`, das Objekt zerstört wird. Wenn Sie mehrere Ereignisse behandeln möchten `Widget` -Objekten, die `AddHandler` Anweisung, um die Ereignisse der einzelnen Objekte gesondert zu verarbeiten.  
  
> [!NOTE]
>  Sie können beliebig viele deklarieren `WithEvents` Variablen als Sie benötigen, aber Arrays `WithEvents` Variablen werden nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)   
 [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)
