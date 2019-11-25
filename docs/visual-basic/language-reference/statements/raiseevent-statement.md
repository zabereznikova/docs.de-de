---
title: RaiseEvent-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
ms.openlocfilehash: e04f2bbaf57789f0bdaa07c1ebd68b22e3ae6178
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333055"
---
# <a name="raiseevent-statement"></a><span data-ttu-id="4604d-102">RaiseEvent-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4604d-102">RaiseEvent Statement</span></span>
<span data-ttu-id="4604d-103">Triggers an event declared at module level within a class, form, or document.</span><span class="sxs-lookup"><span data-stu-id="4604d-103">Triggers an event declared at module level within a class, form, or document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4604d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4604d-104">Syntax</span></span>  
  
```vb  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a><span data-ttu-id="4604d-105">Teile</span><span class="sxs-lookup"><span data-stu-id="4604d-105">Parts</span></span>  
 `eventname`  
 <span data-ttu-id="4604d-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4604d-106">Required.</span></span> <span data-ttu-id="4604d-107">Name of the event to trigger.</span><span class="sxs-lookup"><span data-stu-id="4604d-107">Name of the event to trigger.</span></span>  
  
 `argumentlist`  
 <span data-ttu-id="4604d-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4604d-108">Optional.</span></span> <span data-ttu-id="4604d-109">Comma-delimited list of variables, arrays, or expressions.</span><span class="sxs-lookup"><span data-stu-id="4604d-109">Comma-delimited list of variables, arrays, or expressions.</span></span> <span data-ttu-id="4604d-110">The `argumentlist` argument must be enclosed by parentheses.</span><span class="sxs-lookup"><span data-stu-id="4604d-110">The `argumentlist` argument must be enclosed by parentheses.</span></span> <span data-ttu-id="4604d-111">If there are no arguments, the parentheses must be omitted.</span><span class="sxs-lookup"><span data-stu-id="4604d-111">If there are no arguments, the parentheses must be omitted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4604d-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4604d-112">Remarks</span></span>  
 <span data-ttu-id="4604d-113">The required `eventname` is the name of an event declared within the module.</span><span class="sxs-lookup"><span data-stu-id="4604d-113">The required `eventname` is the name of an event declared within the module.</span></span> <span data-ttu-id="4604d-114">It follows Visual Basic variable naming conventions.</span><span class="sxs-lookup"><span data-stu-id="4604d-114">It follows Visual Basic variable naming conventions.</span></span>  
  
 <span data-ttu-id="4604d-115">If the event has not been declared within the module in which it is raised, an error occurs.</span><span class="sxs-lookup"><span data-stu-id="4604d-115">If the event has not been declared within the module in which it is raised, an error occurs.</span></span> <span data-ttu-id="4604d-116">The following code fragment illustrates an event declaration and a procedure in which the event is raised.</span><span class="sxs-lookup"><span data-stu-id="4604d-116">The following code fragment illustrates an event declaration and a procedure in which the event is raised.</span></span>  
  
 [!code-vb[VbVbalrEvents#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#37)]  
  
 <span data-ttu-id="4604d-117">You cannot use `RaiseEvent` to raise events that are not explicitly declared in the module.</span><span class="sxs-lookup"><span data-stu-id="4604d-117">You cannot use `RaiseEvent` to raise events that are not explicitly declared in the module.</span></span> <span data-ttu-id="4604d-118">For example, all forms inherit a <xref:System.Windows.Forms.Control.Click> event from <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, it cannot be raised using `RaiseEvent` in a derived form.</span><span class="sxs-lookup"><span data-stu-id="4604d-118">For example, all forms inherit a <xref:System.Windows.Forms.Control.Click> event from <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, it cannot be raised using `RaiseEvent` in a derived form.</span></span> <span data-ttu-id="4604d-119">If you declare a `Click` event in the form module, it shadows the form's own <xref:System.Windows.Forms.Control.Click> event.</span><span class="sxs-lookup"><span data-stu-id="4604d-119">If you declare a `Click` event in the form module, it shadows the form's own <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="4604d-120">You can still invoke the form's <xref:System.Windows.Forms.Control.Click> event by calling the <xref:System.Windows.Forms.Control.OnClick%2A> method.</span><span class="sxs-lookup"><span data-stu-id="4604d-120">You can still invoke the form's <xref:System.Windows.Forms.Control.Click> event by calling the <xref:System.Windows.Forms.Control.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="4604d-121">By default, an event defined in Visual Basic raises its event handlers in the order that the connections are established.</span><span class="sxs-lookup"><span data-stu-id="4604d-121">By default, an event defined in Visual Basic raises its event handlers in the order that the connections are established.</span></span> <span data-ttu-id="4604d-122">Because events can have `ByRef` parameters, a process that connects late may receive parameters that have been changed by an earlier event handler.</span><span class="sxs-lookup"><span data-stu-id="4604d-122">Because events can have `ByRef` parameters, a process that connects late may receive parameters that have been changed by an earlier event handler.</span></span> <span data-ttu-id="4604d-123">After the event handlers execute, control is returned to the subroutine that raised the event.</span><span class="sxs-lookup"><span data-stu-id="4604d-123">After the event handlers execute, control is returned to the subroutine that raised the event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4604d-124">Non-shared events should not be raised within the constructor of the class in which they are declared.</span><span class="sxs-lookup"><span data-stu-id="4604d-124">Non-shared events should not be raised within the constructor of the class in which they are declared.</span></span> <span data-ttu-id="4604d-125">Although such events do not cause run-time errors, they may fail to be caught by associated event handlers.</span><span class="sxs-lookup"><span data-stu-id="4604d-125">Although such events do not cause run-time errors, they may fail to be caught by associated event handlers.</span></span> <span data-ttu-id="4604d-126">Use the `Shared` modifier to create a shared event if you need to raise an event from a constructor.</span><span class="sxs-lookup"><span data-stu-id="4604d-126">Use the `Shared` modifier to create a shared event if you need to raise an event from a constructor.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4604d-127">You can change the default behavior of events by defining a custom event.</span><span class="sxs-lookup"><span data-stu-id="4604d-127">You can change the default behavior of events by defining a custom event.</span></span> <span data-ttu-id="4604d-128">For custom events, the `RaiseEvent` statement invokes the event's `RaiseEvent` accessor.</span><span class="sxs-lookup"><span data-stu-id="4604d-128">For custom events, the `RaiseEvent` statement invokes the event's `RaiseEvent` accessor.</span></span> <span data-ttu-id="4604d-129">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4604d-129">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4604d-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4604d-130">Example</span></span>  
 <span data-ttu-id="4604d-131">Im folgenden Beispiel werden Ereignisse zum Herunterzählen der Sekunden von 10 bis 0 verwendet.</span><span class="sxs-lookup"><span data-stu-id="4604d-131">The following example uses events to count down seconds from 10 to 0.</span></span> <span data-ttu-id="4604d-132">The code illustrates several of the event-related methods, properties, and statements, including the `RaiseEvent` statement.</span><span class="sxs-lookup"><span data-stu-id="4604d-132">The code illustrates several of the event-related methods, properties, and statements, including the `RaiseEvent` statement.</span></span>  
  
 <span data-ttu-id="4604d-133">Die Klasse, die ein Ereignis auslöst, ist die Ereignisquelle, und die Methoden, die das Ereignis verarbeiten, sind die Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="4604d-133">The class that raises an event is the event source, and the methods that process the event are the event handlers.</span></span> <span data-ttu-id="4604d-134">Eine Ereignisquelle kann über mehrere Handler für die Ereignisse verfügen, die sie generiert.</span><span class="sxs-lookup"><span data-stu-id="4604d-134">An event source can have multiple handlers for the events it generates.</span></span> <span data-ttu-id="4604d-135">Wenn die Klasse das Ereignis auslöst, wird dieses Ereignis in jeder Klasse ausgelöst, die das Verarbeiten von Ereignissen für diese Instanz des Objekts ausgewählt hat.</span><span class="sxs-lookup"><span data-stu-id="4604d-135">When the class raises the event, that event is raised on every class that has elected to handle events for that instance of the object.</span></span>  
  
 <span data-ttu-id="4604d-136">Im Beispiel wird außerdem ein Formular (`Form1`) mit einer Schaltfläche (`Button1`) und einem Textfeld (`TextBox1`) verwendet.</span><span class="sxs-lookup"><span data-stu-id="4604d-136">The example also uses a form (`Form1`) with a button (`Button1`) and a text box (`TextBox1`).</span></span> <span data-ttu-id="4604d-137">Wenn Sie auf die Schaltfläche klicken, zeigt das erste Textfeld einen Countdown von 10 bis 0 Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="4604d-137">When you click the button, the first text box displays a countdown from 10 to 0 seconds.</span></span> <span data-ttu-id="4604d-138">Nach Ablauf der vollständigen Zeitspanne (10 Sekunden) wird im ersten Textfeld „Fertig“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4604d-138">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
 <span data-ttu-id="4604d-139">Der Code für `Form1` gibt die Anfangs- und Beendigungsstatus des Formulars an.</span><span class="sxs-lookup"><span data-stu-id="4604d-139">The code for `Form1` specifies the initial and terminal states of the form.</span></span> <span data-ttu-id="4604d-140">Er enthält zudem den Code, der ausgeführt wird, wenn Ereignisse ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="4604d-140">It also contains the code executed when events are raised.</span></span>  
  
 <span data-ttu-id="4604d-141">To use this example, open a new Windows Application project, add a button named `Button1` and a text box named `TextBox1` to the main form, named `Form1`.</span><span class="sxs-lookup"><span data-stu-id="4604d-141">To use this example, open a new Windows Application project, add a button named `Button1` and a text box named `TextBox1` to the main form, named `Form1`.</span></span> <span data-ttu-id="4604d-142">Then right-click the form and click **View Code** to open the Code Editor.</span><span class="sxs-lookup"><span data-stu-id="4604d-142">Then right-click the form and click **View Code** to open the Code Editor.</span></span>  
  
 <span data-ttu-id="4604d-143">Add a `WithEvents` variable to the declarations section of the `Form1` class.</span><span class="sxs-lookup"><span data-stu-id="4604d-143">Add a `WithEvents` variable to the declarations section of the `Form1` class.</span></span>  
  
 [!code-vb[VbVbalrEvents#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="4604d-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4604d-144">Example</span></span>  
 <span data-ttu-id="4604d-145">Fügen Sie den folgenden Code zum Code für `Form1` hinzu.</span><span class="sxs-lookup"><span data-stu-id="4604d-145">Add the following code to the code for `Form1`.</span></span> <span data-ttu-id="4604d-146">Replace any duplicate procedures that may exist, such as `Form_Load`, or `Button_Click`.</span><span class="sxs-lookup"><span data-stu-id="4604d-146">Replace any duplicate procedures that may exist, such as `Form_Load`, or `Button_Click`.</span></span>  
  
 [!code-vb[VbVbalrEvents#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#15)]  
  
 <span data-ttu-id="4604d-147">Press F5 to run the preceding example, and click the button labeled **Start**.</span><span class="sxs-lookup"><span data-stu-id="4604d-147">Press F5 to run the preceding example, and click the button labeled **Start**.</span></span> <span data-ttu-id="4604d-148">Im ersten Textfeld werden die Sekunden heruntergezählt.</span><span class="sxs-lookup"><span data-stu-id="4604d-148">The first text box starts to count down the seconds.</span></span> <span data-ttu-id="4604d-149">Nach Ablauf der vollständigen Zeitspanne (10 Sekunden) wird im ersten Textfeld „Fertig“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4604d-149">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4604d-150">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span><span class="sxs-lookup"><span data-stu-id="4604d-150">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="4604d-151">To allow the form to handle the events directly, you can use multithreading.</span><span class="sxs-lookup"><span data-stu-id="4604d-151">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="4604d-152">For more information, see [Managed Threading](../../../standard/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="4604d-152">For more information, see [Managed Threading](../../../standard/threading/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4604d-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4604d-153">See also</span></span>

- [<span data-ttu-id="4604d-154">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="4604d-154">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="4604d-155">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4604d-155">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="4604d-156">AddHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4604d-156">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="4604d-157">RemoveHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4604d-157">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="4604d-158">Handles</span><span class="sxs-lookup"><span data-stu-id="4604d-158">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
