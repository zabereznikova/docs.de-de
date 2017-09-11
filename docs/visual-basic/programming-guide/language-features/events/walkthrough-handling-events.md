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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b4ad77b3b0236e762fc17b8aba9d34108c8d75b5
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-handling-events-visual-basic"></a><span data-ttu-id="be981-102">Exemplarische Vorgehensweise: Behandeln von Ereignissen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be981-102">Walkthrough: Handling Events (Visual Basic)</span></span>
<span data-ttu-id="be981-103">Dies ist die zweite von zwei Themen, die zum Arbeiten mit Ereignissen zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="be981-103">This is the second of two topics that demonstrate how to work with events.</span></span> <span data-ttu-id="be981-104">Das erste Thema [Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), zeigt, wie Ereignisse deklariert und ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="be981-104">The first topic, [Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), shows how to declare and raise events.</span></span> <span data-ttu-id="be981-105">Dieser Abschnitt verwendet die Form und die Klasse aus dieser exemplarischen Vorgehensweise veranschaulicht, wie Ereignisse werden behandelt.</span><span class="sxs-lookup"><span data-stu-id="be981-105">This section uses the form and class from that walkthrough to show how to handle events when they take place.</span></span>  
  
 <span data-ttu-id="be981-106">Die `Widget` Beispiel verwendet herkömmliche Ereignisbehandlung-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="be981-106">The `Widget` class example uses traditional event-handling statements.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="be981-107">bietet andere Verfahren zum Arbeiten mit Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="be981-107"> provides other techniques for working with events.</span></span> <span data-ttu-id="be981-108">Als Übung, können Sie dieses Beispiel verwenden Sie ändern die `AddHandler` und `Handles` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="be981-108">As an exercise, you can modify this example to use the `AddHandler` and `Handles` statements.</span></span>  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a><span data-ttu-id="be981-109">Der Widget-Klasse das PercentDone-Ereignis behandeln</span><span class="sxs-lookup"><span data-stu-id="be981-109">To handle the PercentDone event of the Widget class</span></span>  
  
1.  <span data-ttu-id="be981-110">Fügen Sie folgenden Code im `Form1`:</span><span class="sxs-lookup"><span data-stu-id="be981-110">Place the following code in `Form1`:</span></span>  
  
     <span data-ttu-id="be981-111">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&4;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="be981-111">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]</span></span>  
  
     <span data-ttu-id="be981-112">Die `WithEvents` Schlüsselwort Gibt an, dass die Variable `mWidget` zum Behandeln der Ereignisse eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="be981-112">The `WithEvents` keyword specifies that the variable `mWidget` is used to handle an object's events.</span></span> <span data-ttu-id="be981-113">Geben Sie die Art des Objekts, indem der Name der Klasse, von der das Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="be981-113">You specify the kind of object by supplying the name of the class from which the object will be created.</span></span>  
  
     <span data-ttu-id="be981-114">Die Variable `mWidget` im deklarierten `Form1` da `WithEvents` Variablen auf Klassenebene werden müssen.</span><span class="sxs-lookup"><span data-stu-id="be981-114">The variable `mWidget` is declared in `Form1` because `WithEvents` variables must be class-level.</span></span> <span data-ttu-id="be981-115">Dies gilt unabhängig vom Typ der Klasse, die in den sie eingefügt.</span><span class="sxs-lookup"><span data-stu-id="be981-115">This is true regardless of the type of class you place them in.</span></span>  
  
     <span data-ttu-id="be981-116">Die Variable `mblnCancel` wird verwendet, um das Abbrechen der `LongTask` Methode.</span><span class="sxs-lookup"><span data-stu-id="be981-116">The variable `mblnCancel` is used to cancel the `LongTask` method.</span></span>  
  
## <a name="writing-code-to-handle-an-event"></a><span data-ttu-id="be981-117">Schreiben von Code zum Behandeln eines Ereignisses</span><span class="sxs-lookup"><span data-stu-id="be981-117">Writing Code to Handle an Event</span></span>  
 <span data-ttu-id="be981-118">Sobald Sie deklarieren eine Variable mit `WithEvents`, der Variablennamen angezeigt, in der linken Dropdown-Liste die Klasse **Code-Editor**.</span><span class="sxs-lookup"><span data-stu-id="be981-118">As soon as you declare a variable using `WithEvents`, the variable name appears in the left drop-down list of the class's **Code Editor**.</span></span> <span data-ttu-id="be981-119">Wenn Sie die Option `mWidget`, die `Widget` -Klasse Ereignisse werden in der rechten Dropdownliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="be981-119">When you select `mWidget`, the `Widget` class's events appear in the right drop-down list.</span></span> <span data-ttu-id="be981-120">Auswahl eines Ereignisses wird die entsprechende Ereignisprozedur mit dem Präfix `mWidget` und der Unterstrich.</span><span class="sxs-lookup"><span data-stu-id="be981-120">Selecting an event displays the corresponding event procedure, with the prefix `mWidget` and an underscore.</span></span> <span data-ttu-id="be981-121">Alle zugeordneten Ereignisprozeduren eine `WithEvents` Variable den Variablennamen als Präfix erhalten.</span><span class="sxs-lookup"><span data-stu-id="be981-121">All the event procedures associated with a `WithEvents` variable are given the variable name as a prefix.</span></span>  
  
#### <a name="to-handle-an-event"></a><span data-ttu-id="be981-122">So behandeln Sie ein Ereignis</span><span class="sxs-lookup"><span data-stu-id="be981-122">To handle an event</span></span>  
  
1.  <span data-ttu-id="be981-123">Wählen Sie `mWidget` aus der linken Dropdown-Liste in der **Code-Editor**.</span><span class="sxs-lookup"><span data-stu-id="be981-123">Select `mWidget` from the left drop-down list in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="be981-124">Wählen Sie die `PercentDone` aus der Liste rechts Dropdown-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="be981-124">Select the `PercentDone` event from the right drop-down list.</span></span> <span data-ttu-id="be981-125">Die **Code-Editor** öffnet der `mWidget_PercentDone` -Ereignisprozedur.</span><span class="sxs-lookup"><span data-stu-id="be981-125">The **Code Editor** opens the `mWidget_PercentDone` event procedure.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="be981-126">Die **Code-Editor** ist nützlich, aber nicht erforderlich, für das Einfügen eines neuen Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="be981-126">The **Code Editor** is useful, but not required, for inserting new event handlers.</span></span> <span data-ttu-id="be981-127">In dieser exemplarischen Vorgehensweise ist es eine direktere, kopieren Sie die Ereignishandler einfach direkt in den Code.</span><span class="sxs-lookup"><span data-stu-id="be981-127">In this walkthrough, it is more direct to just copy the event handlers directly into your code.</span></span>  
  
3.  <span data-ttu-id="be981-128">Fügen Sie dem `mWidget_PercentDone`-Ereignishandler folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="be981-128">Add the following code to the `mWidget_PercentDone` event handler:</span></span>  
  
     <span data-ttu-id="be981-129">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&5;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="be981-129">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]</span></span>  
  
     <span data-ttu-id="be981-130">Wenn die `PercentDone` -Ereignis ausgelöst wird, zeigt die Ereignisprozedur die abgeschlossenen Prozentsatz in eine `Label` Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="be981-130">Whenever the `PercentDone` event is raised, the event procedure displays the percent complete in a `Label` control.</span></span> <span data-ttu-id="be981-131">Die `DoEvents` -Methode ermöglicht es, die Bezeichnung neu zu zeichnen, und auch dem Benutzer die Möglichkeit, klicken Sie auf die **Abbrechen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="be981-131">The `DoEvents` method allows the label to repaint, and also gives the user the opportunity to click the **Cancel** button.</span></span>  
  
4.  <span data-ttu-id="be981-132">Fügen Sie den folgenden Code für den `Button2_Click` -Ereignishandler:</span><span class="sxs-lookup"><span data-stu-id="be981-132">Add the following code for the `Button2_Click` event handler:</span></span>  
  
     <span data-ttu-id="be981-133">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&6;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="be981-133">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]</span></span>  
  
 <span data-ttu-id="be981-134">Klickt der Benutzer auf die **Abbrechen** Schaltfläche `LongTask` ausgeführt wird, die `Button2_Click` Ereignis wird ausgeführt, sobald die `DoEvents` Anweisung ermöglicht die Verarbeitung von Ereignissen auftreten.</span><span class="sxs-lookup"><span data-stu-id="be981-134">If the user clicks the **Cancel** button while `LongTask` is running, the `Button2_Click` event is executed as soon as the `DoEvents` statement allows event processing to occur.</span></span> <span data-ttu-id="be981-135">Die Variable auf Klassenebene `mblnCancel` auf festgelegt ist `True`, und die `mWidget_PercentDone` Ereignis überprüft, und legt die `ByRef Cancel` Argument `True`.</span><span class="sxs-lookup"><span data-stu-id="be981-135">The class-level variable `mblnCancel` is set to `True`, and the `mWidget_PercentDone` event then tests it and sets the `ByRef Cancel` argument to `True`.</span></span>  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a><span data-ttu-id="be981-136">Herstellen einer Verbindung eine WithEvents-Variable auf ein Objekt</span><span class="sxs-lookup"><span data-stu-id="be981-136">Connecting a WithEvents Variable to an Object</span></span>  
 <span data-ttu-id="be981-137">`Form1`ist nun eingerichtet, behandeln eine `Widget` Ereignisse des Objekts.</span><span class="sxs-lookup"><span data-stu-id="be981-137">`Form1` is now set up to handle a `Widget` object's events.</span></span> <span data-ttu-id="be981-138">Übrig bleibt, suchen Sie einen `Widget` an.</span><span class="sxs-lookup"><span data-stu-id="be981-138">All that remains is to find a `Widget` somewhere.</span></span>  
  
 <span data-ttu-id="be981-139">Wenn Sie eine Variable deklarieren `WithEvents` zur Entwurfszeit kein Objekt zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="be981-139">When you declare a variable `WithEvents` at design time, no object is associated with it.</span></span> <span data-ttu-id="be981-140">Ein `WithEvents` -Variable funktioniert genau wie jede andere Objektvariable.</span><span class="sxs-lookup"><span data-stu-id="be981-140">A `WithEvents` variable is just like any other object variable.</span></span> <span data-ttu-id="be981-141">Sie müssen ein Objekt erstellen, und weisen Sie einen Verweis mit dem `WithEvents` Variable.</span><span class="sxs-lookup"><span data-stu-id="be981-141">You have to create an object and assign a reference to it with the `WithEvents` variable.</span></span>  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a><span data-ttu-id="be981-142">Erstellen Sie ein Objekt und einen Verweis darauf zuweisen</span><span class="sxs-lookup"><span data-stu-id="be981-142">To create an object and assign a reference to it</span></span>  
  
1.  <span data-ttu-id="be981-143">Wählen Sie **(Form1-Ereignisse)** aus der linken Dropdown-Liste in der **Code-Editor**.</span><span class="sxs-lookup"><span data-stu-id="be981-143">Select **(Form1 Events)** from the left drop-down list in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="be981-144">Wählen Sie die `Load` aus der Liste rechts Dropdown-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="be981-144">Select the `Load` event from the right drop-down list.</span></span> <span data-ttu-id="be981-145">Die **Code-Editor** öffnet der `Form1_Load` -Ereignisprozedur.</span><span class="sxs-lookup"><span data-stu-id="be981-145">The **Code Editor** opens the `Form1_Load` event procedure.</span></span>  
  
3.  <span data-ttu-id="be981-146">Fügen Sie den folgenden Code für die `Form1_Load` Ereignis Verfahren zum Erstellen der `Widget`:</span><span class="sxs-lookup"><span data-stu-id="be981-146">Add the following code for the `Form1_Load` event procedure to create the `Widget`:</span></span>  
  
     <span data-ttu-id="be981-147">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#7;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="be981-147">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]</span></span>  
  
 <span data-ttu-id="be981-148">Wenn dieser Code ausgeführt wird, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] erstellt eine `Widget` -Objekt und verbindet die zugehörigen Ereignisse auf das Ereignis Verfahren im Zusammenhang mit `mWidget`.</span><span class="sxs-lookup"><span data-stu-id="be981-148">When this code executes, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] creates a `Widget` object and connects its events to the event procedures associated with `mWidget`.</span></span> <span data-ttu-id="be981-149">Von diesem Zeitpunkt an, wenn die `Widget` löst seine `PercentDone` -Ereignis, das `mWidget_PercentDone` Ereignisprozedur ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="be981-149">From that point on, whenever the `Widget` raises its `PercentDone` event, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
#### <a name="to-call-the-longtask-method"></a><span data-ttu-id="be981-150">Zum Aufrufen der Methode von LongTask</span><span class="sxs-lookup"><span data-stu-id="be981-150">To call the LongTask method</span></span>  
  
-   <span data-ttu-id="be981-151">Fügen Sie dem `Button1_Click`-Ereignishandler folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="be981-151">Add the following code to the `Button1_Click` event handler:</span></span>  
  
     <span data-ttu-id="be981-152">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#8;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="be981-152">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]</span></span>  
  
 <span data-ttu-id="be981-153">Bevor Sie die `LongTask` -Methode aufgerufen wird, wird die Bezeichnung, zeigt der abgeschlossene Prozentsatz initialisiert werden müssen, und der Klassenebene `Boolean` flag für das Abbrechen der Methode festgelegt werden muss, `False`.</span><span class="sxs-lookup"><span data-stu-id="be981-153">Before the `LongTask` method is called, the label that displays the percent complete must be initialized, and the class-level `Boolean` flag for canceling the method must be set to `False`.</span></span>  
  
 <span data-ttu-id="be981-154">`LongTask`wird mit einer Aufgabendauer von 12,2 Sekunden aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="be981-154">`LongTask` is called with a task duration of 12.2 seconds.</span></span> <span data-ttu-id="be981-155">Das `PercentDone` -Ereignis wird ausgelöst, einmal alle ein Drittel von einer Sekunde.</span><span class="sxs-lookup"><span data-stu-id="be981-155">The `PercentDone` event is raised once every one-third of a second.</span></span> <span data-ttu-id="be981-156">Jedes Mal das Ereignis ausgelöst wird, die `mWidget_PercentDone` Ereignisprozedur ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="be981-156">Each time the event is raised, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
 <span data-ttu-id="be981-157">Wenn `LongTask` erfolgt, `mblnCancel` wird daraufhin überprüft, ob `LongTask` normal beendet oder angehalten wurde, weil `mblnCancel` wurde `True`.</span><span class="sxs-lookup"><span data-stu-id="be981-157">When `LongTask` is done, `mblnCancel` is tested to see if `LongTask` ended normally, or if it stopped because `mblnCancel` was set to `True`.</span></span> <span data-ttu-id="be981-158">Der Prozentsatz der Fertigstellung wird nur im ersten Fall aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="be981-158">The percent complete is updated only in the former case.</span></span>  
  
#### <a name="to-run-the-program"></a><span data-ttu-id="be981-159">So führen Sie das Programm aus</span><span class="sxs-lookup"><span data-stu-id="be981-159">To run the program</span></span>  
  
1.  <span data-ttu-id="be981-160">Drücken Sie F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="be981-160">Press F5 to put the project in run mode.</span></span>  
  
2.  <span data-ttu-id="be981-161">Klicken Sie auf die **Aufgabe** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="be981-161">Click the **Start Task** button.</span></span> <span data-ttu-id="be981-162">Jedes Mal die `PercentDone` -Ereignis ausgelöst wird, wird die Bezeichnung mit dem Prozentsatz der Aufgabe, die abgeschlossen wurde aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="be981-162">Each time the `PercentDone` event is raised, the label is updated with the percentage of the task that is complete.</span></span>  
  
3.  <span data-ttu-id="be981-163">Klicken Sie auf die **Abbrechen** Schaltfläche, um den Vorgang zu beenden.</span><span class="sxs-lookup"><span data-stu-id="be981-163">Click the **Cancel** button to stop the task.</span></span> <span data-ttu-id="be981-164">Beachten Sie, dass die Darstellung der **Abbrechen** Schaltfläche nicht direkt ändert, wenn Sie darauf klicken.</span><span class="sxs-lookup"><span data-stu-id="be981-164">Notice that the appearance of the **Cancel** button does not change immediately when you click it.</span></span> <span data-ttu-id="be981-165">Die `Click` Ereignis nicht auftreten, bis die `My.Application.DoEvents` Anweisung ermöglicht die Verarbeitung von Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="be981-165">The `Click` event cannot happen until the `My.Application.DoEvents` statement allows event processing.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="be981-166">Die `My.Application.DoEvents` -Methode verarbeitet Ereignisse nicht auf genau die gleiche Weise wie das Formular.</span><span class="sxs-lookup"><span data-stu-id="be981-166">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="be981-167">Klicken Sie beispielsweise in dieser exemplarischen Vorgehensweise, Sie müssen auf die **Abbrechen** zweimal auf die Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="be981-167">For example, in this walkthrough, you must click the **Cancel** button twice.</span></span> <span data-ttu-id="be981-168">Um das Formular die Ereignisse direkt behandeln kann, können Sie multithreading.</span><span class="sxs-lookup"><span data-stu-id="be981-168">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="be981-169">Weitere Informationen finden Sie unter [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span><span class="sxs-lookup"><span data-stu-id="be981-169">For more information, see [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span></span>  
  
 <span data-ttu-id="be981-170">Möglicherweise ist es hilfreich, das Programm durch Drücken von F11 auszuführen und den Code zu einem Zeitpunkt schrittweise.</span><span class="sxs-lookup"><span data-stu-id="be981-170">You may find it instructive to run the program with F11 and step through the code a line at a time.</span></span> <span data-ttu-id="be981-171">Klar erkennbar, wie die Ausführung von eingegeben `LongTask`, und klicken Sie dann kurz erneut eingegeben `Form1` jedes Mal die `PercentDone` -Ereignis wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="be981-171">You can clearly see how execution enters `LongTask`, and then briefly re-enters `Form1` each time the `PercentDone` event is raised.</span></span>  
  
 <span data-ttu-id="be981-172">Was geschieht, wenn ist, bei der Ausführung wieder im Code ist `Form1`, die `LongTask` Methode erneut aufrufen würden?</span><span class="sxs-lookup"><span data-stu-id="be981-172">What would happen if, while execution was back in the code of `Form1`, the `LongTask` method were called again?</span></span> <span data-ttu-id="be981-173">Im schlimmsten Fall ein Stapelüberlauf auftreten, wenn `LongTask` aufgerufen wurden, jedes Mal, wenn das Ereignis ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="be981-173">At worst, a stack overflow might occur if `LongTask` were called every time the event was raised.</span></span>  
  
 <span data-ttu-id="be981-174">Veranlassen Sie, dass die Variable `mWidget` zum Behandeln von Ereignissen für eine andere `Widget` Objekt durch einen Verweis auf die neue zuweisen `Widget` auf `mWidget`.</span><span class="sxs-lookup"><span data-stu-id="be981-174">You can cause the variable `mWidget` to handle events for a different `Widget` object by assigning a reference to the new `Widget` to `mWidget`.</span></span> <span data-ttu-id="be981-175">In der Tat können Sie den Code in vornehmen `Button1_Click` dazu, jedes Mal, wenn Sie auf die Schaltfläche klicken.</span><span class="sxs-lookup"><span data-stu-id="be981-175">In fact, you can make the code in `Button1_Click` do this every time you click the button.</span></span>  
  
#### <a name="to-handle-events-for-a-different-widget"></a><span data-ttu-id="be981-176">So behandeln Sie Ereignisse für ein anderes Widget-Objekt</span><span class="sxs-lookup"><span data-stu-id="be981-176">To handle events for a different widget</span></span>  
  
-   <span data-ttu-id="be981-177">Fügen Sie die folgende Codezeile, die `Button1_Click` Verfahren, die unmittelbar vor der Zeile `mWidget.LongTask(12.2, 0.33)`:</span><span class="sxs-lookup"><span data-stu-id="be981-177">Add the following line of code to the `Button1_Click` procedure, immediately preceding the line that reads `mWidget.LongTask(12.2, 0.33)`:</span></span>  
  
     <span data-ttu-id="be981-178">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#9;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="be981-178">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]</span></span>  
  
 <span data-ttu-id="be981-179">Der obige Code erstellt ein neues `Widget` jedes Mal die Schaltfläche geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="be981-179">The code above creates a new `Widget` each time the button is clicked.</span></span> <span data-ttu-id="be981-180">Sobald die `LongTask` Methode ausgeführt wird, den Verweis auf die `Widget` freigegeben wird, und die `Widget` zerstört wird.</span><span class="sxs-lookup"><span data-stu-id="be981-180">As soon as the `LongTask` method completes, the reference to the `Widget` is released, and the `Widget` is destroyed.</span></span>  
  
 <span data-ttu-id="be981-181">Ein `WithEvents` -Variable kann jeweils nur einen Objektverweis enthalten, wenn Sie eine andere zuweisen `Widget` -Objekt `mWidget`, die vorherige `Widget` Ereignisse des Objekts nicht mehr verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="be981-181">A `WithEvents` variable can contain only one object reference at a time, so if you assign a different `Widget` object to `mWidget`, the previous `Widget` object's events will no longer be handled.</span></span> <span data-ttu-id="be981-182">Wenn `mWidget` ist der einzige Objektvariable einen Verweis auf die alte `Widget`, das Objekt zerstört wird.</span><span class="sxs-lookup"><span data-stu-id="be981-182">If `mWidget` is the only object variable containing a reference to the old `Widget`, the object is destroyed.</span></span> <span data-ttu-id="be981-183">Wenn Sie mehrere Ereignisse behandeln möchten `Widget` -Objekten, die `AddHandler` Anweisung, um die Ereignisse der einzelnen Objekte gesondert zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="be981-183">If you want to handle events from several `Widget` objects, use the `AddHandler` statement to process events from each object separately.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be981-184">Sie können beliebig viele deklarieren `WithEvents` Variablen als Sie benötigen, aber Arrays `WithEvents` Variablen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="be981-184">You can declare as many `WithEvents` variables as you need, but arrays of `WithEvents` variables are not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be981-185">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be981-185">See Also</span></span>  
 <span data-ttu-id="be981-186">[Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md) </span><span class="sxs-lookup"><span data-stu-id="be981-186">[Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md) </span></span>  
<span data-ttu-id="be981-187"> [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="be981-187"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
