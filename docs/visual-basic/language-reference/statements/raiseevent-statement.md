---
title: RaiseEvent-Anweisung | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
dev_langs:
- VB
helpviewer_keywords:
- raising events, RaiseEvent statement
- RaiseEvent statement
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
caps.latest.revision: 19
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
ms.openlocfilehash: 6a0cf1c5635335f22fddd57c7dd2baaeca6ddd23
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="raiseevent-statement"></a><span data-ttu-id="8c388-102">RaiseEvent-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8c388-102">RaiseEvent Statement</span></span>
<span data-ttu-id="8c388-103">Trigger, die ein Ereignis auf Modulebene in einer Klasse, einem Formular oder einem Dokument deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="8c388-103">Triggers an event declared at module level within a class, form, or document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c388-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c388-104">Syntax</span></span>  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a><span data-ttu-id="8c388-105">Teile</span><span class="sxs-lookup"><span data-stu-id="8c388-105">Parts</span></span>  
 `eventname`  
 <span data-ttu-id="8c388-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8c388-106">Required.</span></span> <span data-ttu-id="8c388-107">Name des auszulösenden Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="8c388-107">Name of the event to trigger.</span></span>  
  
 `argumentlist`  
 <span data-ttu-id="8c388-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="8c388-108">Optional.</span></span> <span data-ttu-id="8c388-109">Durch Trennzeichen getrennte Liste von Variablen, Arrays oder Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="8c388-109">Comma-delimited list of variables, arrays, or expressions.</span></span> <span data-ttu-id="8c388-110">Die `argumentlist` -Argument muss in Klammern eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="8c388-110">The `argumentlist` argument must be enclosed by parentheses.</span></span> <span data-ttu-id="8c388-111">Wenn keine Argumente vorhanden sind, müssen die Klammern weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="8c388-111">If there are no arguments, the parentheses must be omitted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c388-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8c388-112">Remarks</span></span>  
 <span data-ttu-id="8c388-113">Die erforderlichen `eventname` ist der Name eines Ereignisses innerhalb des Moduls deklariert.</span><span class="sxs-lookup"><span data-stu-id="8c388-113">The required `eventname` is the name of an event declared within the module.</span></span> <span data-ttu-id="8c388-114">Daraus folgt Visual Basic Namenskonventionen Variable.</span><span class="sxs-lookup"><span data-stu-id="8c388-114">It follows Visual Basic variable naming conventions.</span></span>  
  
 <span data-ttu-id="8c388-115">Wenn das Ereignis innerhalb des Moduls, in dem es ausgelöst wird, nicht deklariert wurde, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="8c388-115">If the event has not been declared within the module in which it is raised, an error occurs.</span></span> <span data-ttu-id="8c388-116">Das folgende Codefragment zeigt eine Ereignisdeklaration und eine Prozedur, in der das Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="8c388-116">The following code fragment illustrates an event declaration and a procedure in which the event is raised.</span></span>  
  
 <span data-ttu-id="8c388-117">[!code-vb[VbVbalrEvents&#37;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8c388-117">[!code-vb[VbVbalrEvents#37](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]</span></span>  
  
 <span data-ttu-id="8c388-118">Sie können keine `RaiseEvent` zum Auslösen von Ereignissen, die nicht explizit im Modul deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="8c388-118">You cannot use `RaiseEvent` to raise events that are not explicitly declared in the module.</span></span> <span data-ttu-id="8c388-119">Beispielsweise erben alle Formulare ein <xref:System.Windows.Forms.Control.Click>Ereignis <xref:System.Windows.Forms.Form?displayProperty=fullName>, es kann nicht mit ausgelöst werden `RaiseEvent` in einem abgeleiteten Formular.</xref:System.Windows.Forms.Form?displayProperty=fullName> </xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="8c388-119">For example, all forms inherit a <xref:System.Windows.Forms.Control.Click> event from <xref:System.Windows.Forms.Form?displayProperty=fullName>, it cannot be raised using `RaiseEvent` in a derived form.</span></span> <span data-ttu-id="8c388-120">Wenn Sie deklarieren eine `Click` Ereignis im Modul Formulars shadows sie des Formulars eigene <xref:System.Windows.Forms.Control.Click>Ereignis.</xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="8c388-120">If you declare a `Click` event in the form module, it shadows the form's own <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="8c388-121">Rufen Sie immer noch des Formulars <xref:System.Windows.Forms.Control.Click>-Ereignis durch das Aufrufen der <xref:System.Windows.Forms.Control.OnClick%2A>-Methode.</xref:System.Windows.Forms.Control.OnClick%2A> </xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="8c388-121">You can still invoke the form's <xref:System.Windows.Forms.Control.Click> event by calling the <xref:System.Windows.Forms.Control.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="8c388-122">Standardmäßig löst ein Ereignis, die in Visual Basic definiert die Ereignishandler in der Reihenfolge, die Verbindungen hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8c388-122">By default, an event defined in Visual Basic raises its event handlers in the order that the connections are established.</span></span> <span data-ttu-id="8c388-123">Da Ereignisse besitzen können `ByRef` Parameter in ein Prozess, der später verbunden möglicherweise Parameter, die von einem vorherigen Ereignishandler geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="8c388-123">Because events can have `ByRef` parameters, a process that connects late may receive parameters that have been changed by an earlier event handler.</span></span> <span data-ttu-id="8c388-124">Nachdem die Ereignishandler ausgeführt wurden, wird die Steuerung an die Unterroutine zurückgegeben, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="8c388-124">After the event handlers execute, control is returned to the subroutine that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c388-125">Nicht freigegebene Ereignisse sollte nicht im Konstruktor der Klasse ausgelöst werden, in denen sie deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="8c388-125">Non-shared events should not be raised within the constructor of the class in which they are declared.</span></span> <span data-ttu-id="8c388-126">Obwohl solche Ereignisse keine Laufzeitfehler verursachen, können sie keine zugeordneten Ereignishandler abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="8c388-126">Although such events do not cause run-time errors, they may fail to be caught by associated event handlers.</span></span> <span data-ttu-id="8c388-127">Verwenden der `Shared` Modifizierer, um ein freigegebenes Ereignis zu erstellen, wenn Sie ein Ereignis von einem Konstruktor auslösen müssen.</span><span class="sxs-lookup"><span data-stu-id="8c388-127">Use the `Shared` modifier to create a shared event if you need to raise an event from a constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c388-128">Sie können das Standardverhalten von Ereignissen ändern, indem Sie ein benutzerdefiniertes Ereignis definieren.</span><span class="sxs-lookup"><span data-stu-id="8c388-128">You can change the default behavior of events by defining a custom event.</span></span> <span data-ttu-id="8c388-129">Für benutzerdefinierte Ereignisse die `RaiseEvent` -Anweisung ruft des Ereignis `RaiseEvent` Accessor.</span><span class="sxs-lookup"><span data-stu-id="8c388-129">For custom events, the `RaiseEvent` statement invokes the event's `RaiseEvent` accessor.</span></span> <span data-ttu-id="8c388-130">Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8c388-130">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c388-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c388-131">Example</span></span>  
 <span data-ttu-id="8c388-132">Im folgenden Beispiel werden Ereignisse zum Herunterzählen der Sekunden von 10 bis 0 verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c388-132">The following example uses events to count down seconds from 10 to 0.</span></span> <span data-ttu-id="8c388-133">Der Code veranschaulicht einige der Ereignisse, Methoden, Eigenschaften und Anweisungen, z. B. die `RaiseEvent` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8c388-133">The code illustrates several of the event-related methods, properties, and statements, including the `RaiseEvent` statement.</span></span>  
  
 <span data-ttu-id="8c388-134">Die Klasse, die ein Ereignis auslöst, ist die Ereignisquelle, und die Methoden, die das Ereignis verarbeiten, sind die Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="8c388-134">The class that raises an event is the event source, and the methods that process the event are the event handlers.</span></span> <span data-ttu-id="8c388-135">Eine Ereignisquelle kann über mehrere Handler für die Ereignisse verfügen, die sie generiert.</span><span class="sxs-lookup"><span data-stu-id="8c388-135">An event source can have multiple handlers for the events it generates.</span></span> <span data-ttu-id="8c388-136">Wenn die Klasse das Ereignis auslöst, wird dieses Ereignis in jeder Klasse ausgelöst, die das Verarbeiten von Ereignissen für diese Instanz des Objekts ausgewählt hat.</span><span class="sxs-lookup"><span data-stu-id="8c388-136">When the class raises the event, that event is raised on every class that has elected to handle events for that instance of the object.</span></span>  
  
 <span data-ttu-id="8c388-137">Im Beispiel wird außerdem ein Formular (`Form1`) mit einer Schaltfläche (`Button1`) und einem Textfeld (`TextBox1`) verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c388-137">The example also uses a form (`Form1`) with a button (`Button1`) and a text box (`TextBox1`).</span></span> <span data-ttu-id="8c388-138">Wenn Sie auf die Schaltfläche klicken, zeigt das erste Textfeld einen Countdown von 10 bis 0 Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="8c388-138">When you click the button, the first text box displays a countdown from 10 to 0 seconds.</span></span> <span data-ttu-id="8c388-139">Nach Ablauf der vollständigen Zeitspanne (10 Sekunden) wird im ersten Textfeld „Fertig“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8c388-139">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
 <span data-ttu-id="8c388-140">Der Code für `Form1` gibt die Anfangs- und Beendigungsstatus des Formulars an.</span><span class="sxs-lookup"><span data-stu-id="8c388-140">The code for `Form1` specifies the initial and terminal states of the form.</span></span> <span data-ttu-id="8c388-141">Er enthält zudem den Code, der ausgeführt wird, wenn Ereignisse ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="8c388-141">It also contains the code executed when events are raised.</span></span>  
  
 <span data-ttu-id="8c388-142">Um dieses Codebeispiel zu verwenden, öffnen Sie ein neues Windows-Anwendungsprojekt, fügen Sie eine Schaltfläche mit dem Namen `Button1` und ein Textfeld mit dem Namen `TextBox1` auf das Hauptformular mit dem Namen `Form1`.</span><span class="sxs-lookup"><span data-stu-id="8c388-142">To use this example, open a new Windows Application project, add a button named `Button1` and a text box named `TextBox1` to the main form, named `Form1`.</span></span> <span data-ttu-id="8c388-143">Klicken Sie dann mit der rechten Maustaste in des Formulars, und klicken Sie auf **Anzeigecode** Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8c388-143">Then right-click the form and click **View Code** to open the Code Editor.</span></span>  
  
 <span data-ttu-id="8c388-144">Hinzufügen einer `WithEvents` Abschnitt Deklarationen der Variablen der `Form1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="8c388-144">Add a `WithEvents` variable to the declarations section of the `Form1` class.</span></span>  
  
 <span data-ttu-id="8c388-145">[!code-vb[VbVbalrEvents&14;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8c388-145">[!code-vb[VbVbalrEvents#14](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c388-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c388-146">Example</span></span>  
 <span data-ttu-id="8c388-147">Fügen Sie den folgenden Code zum Code für `Form1` hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c388-147">Add the following code to the code for `Form1`.</span></span> <span data-ttu-id="8c388-148">Ersetzen Sie ggf. doppelte Prozeduren, z. B. möglicherweise `Form_Load`, oder `Button_Click`.</span><span class="sxs-lookup"><span data-stu-id="8c388-148">Replace any duplicate procedures that may exist, such as `Form_Load`, or `Button_Click`.</span></span>  
  
 <span data-ttu-id="8c388-149">[!code-vb[VbVbalrEvents&#15;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="8c388-149">[!code-vb[VbVbalrEvents#15](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]</span></span>  
  
 <span data-ttu-id="8c388-150">Drücken Sie F5, um das vorherige Beispiel auszuführen, und klicken Sie auf die Schaltfläche **Start**.</span><span class="sxs-lookup"><span data-stu-id="8c388-150">Press F5 to run the preceding example, and click the button labeled **Start**.</span></span> <span data-ttu-id="8c388-151">Im ersten Textfeld werden die Sekunden heruntergezählt.</span><span class="sxs-lookup"><span data-stu-id="8c388-151">The first text box starts to count down the seconds.</span></span> <span data-ttu-id="8c388-152">Nach Ablauf der vollständigen Zeitspanne (10 Sekunden) wird im ersten Textfeld „Fertig“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8c388-152">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c388-153">Die `My.Application.DoEvents` -Methode verarbeitet Ereignisse nicht auf genau die gleiche Weise wie das Formular.</span><span class="sxs-lookup"><span data-stu-id="8c388-153">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="8c388-154">Um das Formular die Ereignisse direkt behandeln kann, können Sie multithreading.</span><span class="sxs-lookup"><span data-stu-id="8c388-154">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="8c388-155">Weitere Informationen finden Sie unter [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span><span class="sxs-lookup"><span data-stu-id="8c388-155">For more information, see [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c388-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c388-156">See Also</span></span>  
 <span data-ttu-id="8c388-157">[Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="8c388-157">[Events](../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="8c388-158"> [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8c388-158"> [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="8c388-159"> [AddHandler-Anweisung](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8c388-159"> [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span></span>  
<span data-ttu-id="8c388-160"> [RemoveHandler-Anweisung](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8c388-160"> [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span></span>  
<span data-ttu-id="8c388-161"> [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)</span><span class="sxs-lookup"><span data-stu-id="8c388-161"> [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)</span></span>
