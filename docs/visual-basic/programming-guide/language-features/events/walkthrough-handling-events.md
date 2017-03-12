---
title: "Walkthrough: Handling Events (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "event handling [Visual Basic], walkthroughs"
  - "walkthroughs [Visual Basic], event handling"
  - "variables [Visual Basic], WithEvents"
  - "events [Visual Basic], walkthroughs"
  - "WithEvents keyword, walkthroughs"
  - "event handlers [Visual Basic], walkthroughs"
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Walkthrough: Handling Events (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

In diesem Thema, dem zweiten von zwei verwandten Themen, wird die Arbeit mit Ereignissen veranschaulicht.  Im ersten Thema \([Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)\) wird beschrieben, wie Ereignisse deklariert und ausgelöst werden.  In diesem Abschnitt werden das Formular und die Klasse aus der erwähnten exemplarischen Vorgehensweise verwendet, um zu demonstrieren, wie eingetretene Ereignisse behandelt werden.  
  
 Im Beispiel mit der `Widget`\-Klasse werden herkömmliche Ereignisbehandlungsanweisungen verwendet.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] stellt andere Techniken zur Arbeit mit Ereignissen bereit.  Um weitere praktische Erfahrungen zu gewinnen, können Sie dieses Beispiel für die Verwendung der `AddHandler`\-Anweisung und der `Handles`\-Anweisung abwandeln.  
  
### So verarbeiten Sie das PercentDone\-Ereignis der Widget\-Klasse  
  
1.  Fügen Sie in `Form1` folgenden Code ein:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](../../../../visual-basic/programming-guide/language-features/events/codesnippet/visualbasic/VbEventWalkthrough/Form1.vb#4)]  
  
     Das `WithEvents`\-Schlüsselwort legt fest, dass die Variable `mWidget` zur Behandlung von Objektereignissen verwendet wird.  Sie legen den Objekttyp fest, indem Sie den Namen der Klasse angeben, aus der das Objekt erstellt wird.  
  
     Die Variable `mWidget` wird in `Form1` deklariert, da `WithEvents`\-Variablen auf Klassenebene definiert werden müssen.  Dies gilt unabhängig vom Typ der Klasse, in die sie eingefügt werden.  
  
     Die `mblnCancel`\-Variable wird verwendet, um die `LongTask`\-Methode abzubrechen.  
  
## Schreiben von Code zur Ereignisbehandlung  
 Sobald Sie ein eVariable mit `WithEvents` deklarieren, wird der Variablenname in der linken Dropdownliste des **Code\-Editors** der Klasse angezeigt.  Wenn Sie `mWidget` auswählen, werden die Ereignisse der `Widget`\-Klasse in der rechten Dropdownliste angezeigt.  Bei Auswahl eines Ereignisses wird die entsprechende Ereignisprozedur mit dem Präfix `mWidget` und einem Unterstrich angezeigt.  Alle mit einer `WithEvents`\-Variablen verknüpften Ereignisprozeduren erhalten als Präfix den Variablennamen.  
  
#### So behandeln Sie ein Ereignis  
  
1.  Wählen Sie `mWidget` in der linken Dropdownliste des **Code\-Editors** aus.  
  
2.  Wählen Sie das `PercentDone`\-Ereignis aus der rechten Dropdownliste aus.  Der **Code\-Editor** öffnet die `mWidget_PercentDone`\-Ereignisprozedur.  
  
    > [!NOTE]
    >  Zum Einfügen neuer Ereignishandler ist der **Code\-Editor** hilfreich, doch nicht erforderlich.  In dieser exemplarischen Vorgehensweise werden die Ereignishandler einfach direkt in den Code eingefügt.  
  
3.  Fügen Sie dem `mWidget_PercentDone`\-Ereignishandler folgenden Code hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](../../../../visual-basic/programming-guide/language-features/events/codesnippet/visualbasic/VbEventWalkthrough/Form1.vb#5)]  
  
     Bei jedem Auslösen des `PercentDone`\-Ereignisses zeigt die Ereignisprozedur den Prozentsatz der bereits erfolgten Verarbeitung in einem `Label`\-Steuerelement an.  Die `DoEvents`\-Methode bietet nicht nur die Möglichkeit, die Bezeichnung neu zu zeichnen, sondern ermöglicht es darüber hinaus dem Benutzer, auf die Schaltfläche **Abbrechen** zu klicken.  
  
4.  Fügen Sie folgenden Code für den `Button2_Click`\-Ereignishandler hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](../../../../visual-basic/programming-guide/language-features/events/codesnippet/visualbasic/VbEventWalkthrough/Form1.vb#6)]  
  
 Wenn der Benutzer während der Ausführung von `LongTask` auf die Schaltfläche **Abbrechen** klickt, wird das `Button2_Click`\-Ereignis ausgeführt, sobald die `DoEvents`\-Anweisung die Ereignisverarbeitung zulässt.  Die Variable `mblnCancel` auf Klassenebene wird auf `True` festgelegt und anschließend vom `mWidget_PercentDone`\-Ereignis überprüft, und das `ByRef Cancel`\-Argument wird auf `True` festgelegt.  
  
## Verbinden einer WithEvents\-Variablen mit einem Objekt  
 `Form1` ist jetzt für die Behandlung von Ereignissen eines `Widget`\-Objekts eingerichtet.  Jetzt muss nur noch ein `Widget`\-Objekt gefunden werden.  
  
 Wenn Sie eine `WithEvents`\-Variable zur Entwurfszeit deklarieren, wird kein Objekt damit verknüpft.  Eine `WithEvents`\-Variable funktioniert genau wie jede andere Objektvariable.  Sie müssen ein Objekt erstellen und ihm mithilfe der `WithEvents`\-Variablen einen Verweis zuweisen.  
  
#### So erstellen Sie ein Objekt und weisen ihm einen Verweis zu  
  
1.  Wählen Sie **\(Form1\-Ereignisse\)** in der linken Dropdownliste des **Code\-Editors** aus.  
  
2.  Wählen Sie das `Load`\-Ereignis aus der rechten Dropdownliste aus.  Der **Code\-Editor** öffnet die `Form1_Load`\-Ereignisprozedur.  
  
3.  Fügen Sie folgenden Code für die `Form1_Load`\-Ereignisprozedur hinzu, um das `Widget` zu erstellen:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](../../../../visual-basic/programming-guide/language-features/events/codesnippet/visualbasic/VbEventWalkthrough/Form1.vb#7)]  
  
 Wenn dieser Code ausgeführt wird, erstellt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] ein `Widget`\-Objekt und verbindet die zugehörigen Ereignisse mit den Ereignisprozeduren, die `mWidget` zugeordnet sind.  Von diesem Zeitpunkt an wird die `mWidget_PercentDone`\-Ereignisprozedur immer ausgeführt, wenn das `PercentDone`\-Ereignis vom `Widget` ausgelöst wird.  
  
#### So rufen Sie die LongTask\-Methode auf  
  
-   Fügen Sie dem `Button1_Click`\-Ereignishandler folgenden Code hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](../../../../visual-basic/programming-guide/language-features/events/codesnippet/visualbasic/VbEventWalkthrough/Form1.vb#8)]  
  
 Bevor die `LongTask`\-Methode aufgerufen wird, muss die Bezeichnung initialisiert werden, die den Prozentsatz der bereits erfolgten Verarbeitung anzeigt. Außerdem muss das auf Klassenebene deklarierte `Boolean`\-Flag zum Abbrechen der Methode auf `False` festgelegt werden.  
  
 `LongTask` wird mit einer Aufgabendauer von 12,2 Sekunden aufgerufen.  Das `PercentDone`\-Ereignis wird jede Drittelsekunde einmal ausgelöst.  Bei jedem Auslösen des Ereignisses wird die `mWidget_PercentDone`\-Ereignisprozedur ausgeführt.  
  
 Nachdem `LongTask` abgeschlossen wurde, wird `mblnCancel` daraufhin überprüft, ob `LongTask` normal beendet oder angehalten wurde, weil `mblnCancel` auf `True` festgelegt war.  Der bereits verarbeitete Prozentsatz wird nur im ersten Fall aktualisiert.  
  
#### So führen Sie das Programm aus  
  
1.  Drücken Sie F5, um das Projekt auszuführen.  
  
2.  Klicken Sie auf die Schaltfläche **Start Task**.  Jedes Mal, wenn das `PercentDone`\-Ereignis ausgelöst wird, wird die Bezeichnung mit dem Prozentsatz der Aufgabe, der bereits erledigt wurde, aktualisiert.  
  
3.  Klicken Sie auf die **Cancel**\-Schaltfläche, um die Aufgabe abzubrechen.  Beachten Sie, dass sich das Erscheinungsbild der **Cancel**\-Schaltfläche nicht direkt ändert, wenn Sie darauf klicken.  Das `Click`\-Ereignis kann erst eintreten, wenn die `My.Application.DoEvents`\-Anweisung die Ereignisverarbeitung zulässt.  
  
    > [!NOTE]
    >  Die `My.Application.DoEvents`\-Methode verarbeitet Ereignisse nicht genau auf die gleiche Weise wie das Formular.  In dieser exemplarischen Vorgehensweise müssen Sie z. B. zweimal auf die Schaltfläche **Abbrechen** klicken.  Damit das Formular die Ereignisse direkt behandeln kann, können Sie Multithreading verwenden.  Weitere Informationen finden Sie unter [Threading](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Möglicherweise finden Sie es aufschlussreich, das Programm durch Drücken von F11 auszuführen und den Code zeilenweise durchzugehen.  In diesem Fall ist klar erkennbar, wie die Ausführung von `LongTask` beginnt und bei jedem Auslösen des `PercentDone`\-Ereignisses kurz wieder zu `Form1` zurückkehrt.  
  
 Was geschieht jedoch, wenn sich die Ausführungsroutine wieder im Code von `Form1` befindet, während die `LongTask`\-Methode erneut aufgerufen wird?  Wenn `LongTask` bei jedem Auslösen des Ereignisses aufgerufen würde, wäre im schlimmsten Fall ein Stapelüberlauf die Folge.  
  
 Sie können festlegen, dass die Variable `mWidget` Ereignisse für ein anderes `Widget`\-Objekt behandelt, indem Sie `mWidget` einen Verweis auf das neue `Widget` zuweisen.  Der Code in `Button1_Click` kann diesen Vorgang sogar jedes Mal ausführen, wenn Sie auf die Schaltfläche klicken.  
  
#### So behandeln Sie Ereignisse für ein anderes Widget\-Objekt  
  
-   Fügen Sie der `Button1_Click`\-Prozedur die folgende Codezeile direkt vor der Zeile `mWidget.LongTask(12.2, 0.33)` hinzu:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](../../../../visual-basic/programming-guide/language-features/events/codesnippet/visualbasic/VbEventWalkthrough/Form1.vb#9)]  
  
 Durch den oben stehenden Code wird bei jedem Klicken auf die Schaltfläche ein neues `Widget` erstellt.  Bei Abschluss der `LongTask`\-Methode wird der Verweis auf das `Widget` freigegeben und das `Widget` zerstört.  
  
 Eine `WithEvents`\-Variable kann jeweils nur einen Objektverweis enthalten. Wenn Sie `mWidget` ein anderes `Widget`\-Objekt zuweisen, werden daher die Ereignisse des vorherigen `Widget`\-Objekts nicht mehr behandelt.  Wenn `mWidget` als einzige Objektvariable einen Verweis auf das alte `Widget` enthält, wird das Objekt zerstört.  Wenn die Ereignisse mehrerer `Widget`\-Objekte behandelt werden sollen, verwenden Sie die `AddHandler`\-Anweisung, um die Ereignisse der einzelnen Objekte gesondert zu verarbeiten.  
  
> [!NOTE]
>  Sie können beliebig viele `WithEvents`\-Variablen deklarieren, Arrays von `WithEvents`\-Variablen werden jedoch nicht unterstützt.  
  
## Siehe auch  
 [Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)   
 [Events](../../../../visual-basic/programming-guide/language-features/events/events.md)