---
title: 'Gewusst wie: Aufrufen von einem Ereignishandler in Visual Basic | Microsoft-Dokumentation'
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
- Visual Basic code, procedures
- event handlers, calling
- event handlers
- procedures, event handlers
- procedures, calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
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
ms.openlocfilehash: dc0174d50c7b5f5cda9d057bce39960b3e563f4e
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="4c067-102">Gewusst wie: Aufrufen eines Ereignishandlers in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c067-102">How to: Call an Event Handler in Visual Basic</span></span>
<span data-ttu-id="4c067-103">Ein *Ereignis* ist eine Aktion oder ein vorkommen, z. B. ein Mausklick klicken oder ein Kreditlimit überschritten –, durch eine Anwendungskomponente, und für die Sie Code schreiben können, reagieren erkannt.</span><span class="sxs-lookup"><span data-stu-id="4c067-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="4c067-104">Ein *-Ereignishandler* ist der Code, der auf ein Ereignis reagieren.</span><span class="sxs-lookup"><span data-stu-id="4c067-104">An *event handler* is the code you write to respond to an event.</span></span>  
  
 <span data-ttu-id="4c067-105">Ein Ereignishandler in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ist ein `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="4c067-105">An event handler in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is a `Sub` procedure.</span></span> <span data-ttu-id="4c067-106">Allerdings Sie normalerweise rufen ihn nicht die gleiche Weise wie andere `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="4c067-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="4c067-107">Stattdessen geben Sie die Prozedur als Handler für das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="4c067-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="4c067-108">Hierzu können Sie entweder mit einer [behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) -Klausel und eine [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) Variable, oder mit einer [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4c067-108">You can do this either with a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause and a [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="4c067-109">Mithilfe einer `Handles` -Klausel ist die Standardmethode, deklarieren einen Ereignishandler in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c067-109">Using a `Handles` clause is the default way to declare an event handler in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="4c067-110">Dies ist die Möglichkeit, die die Ereignishandler von Entwicklern geschrieben werden, wenn Sie in der integrierten Entwicklungsumgebung (IDE) programmieren.</span><span class="sxs-lookup"><span data-stu-id="4c067-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="4c067-111">Die `AddHandler` -Anweisung eignet sich zum Auslösen von Ereignissen dynamisch zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="4c067-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>  
  
 <span data-ttu-id="4c067-112">Wenn das Ereignis eintritt, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ruft automatisch die Ereignis-Handler-Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4c067-112">When the event occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically calls the event handler procedure.</span></span> <span data-ttu-id="4c067-113">Jeglicher Code, der Zugriff auf das Ereignis kann dazu führen, dass es durch die Ausführung einer [RaiseEvent-Anweisung](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4c067-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>  
  
 <span data-ttu-id="4c067-114">Sie können das gleiche Ereignis mehrere Ereignishandler zuordnen.</span><span class="sxs-lookup"><span data-stu-id="4c067-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="4c067-115">In einigen Fällen können Sie einen Ereignishandler aus einem Ereignis zu trennen.</span><span class="sxs-lookup"><span data-stu-id="4c067-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="4c067-116">Weitere Informationen finden Sie unter [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="4c067-116">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a><span data-ttu-id="4c067-117">Mit Handles und WithEvents einen Ereignishandler aufrufen</span><span class="sxs-lookup"><span data-stu-id="4c067-117">To call an event handler using Handles and WithEvents</span></span>  
  
1.  <span data-ttu-id="4c067-118">Stellen Sie sicher, dass das Ereignis mit deklariert eine [Event-Anweisung](../../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4c067-118">Make sure the event is declared with an [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
2.  <span data-ttu-id="4c067-119">Deklarieren Sie eine Objektvariable auf Modul- oder Ebene, mit der [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="4c067-119">Declare an object variable at module or class level, using the [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="4c067-120">Die `As` -Klausel für diese Variable muss die Klasse angeben, die das Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="4c067-120">The `As` clause for this variable must specify the class that raises the event.</span></span>  
  
3.  <span data-ttu-id="4c067-121">In der Deklaration der Ereignisbehandlung `Sub` Verfahren Hinzufügen einer [behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) -Klausel, in der `WithEvents` Variable und der Name des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="4c067-121">In the declaration of the event-handling `Sub` procedure, add a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>  
  
4.  <span data-ttu-id="4c067-122">Wenn das Ereignis eintritt, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ruft automatisch die `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="4c067-122">When the event occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="4c067-123">Code können Sie eine `RaiseEvent` Anweisung, damit das Ereignis auftreten.</span><span class="sxs-lookup"><span data-stu-id="4c067-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="4c067-124">Im folgende Beispiel wird ein Ereignis definiert und ein `WithEvents` Variable, die auf die Klasse verweist, die das Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="4c067-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="4c067-125">Die Ereignisbehandlung `Sub` Prozedur verwendet einen `Handles` -Klausel zur Angabe der Klasse und das Ereignis behandelt.</span><span class="sxs-lookup"><span data-stu-id="4c067-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>  
  
     <span data-ttu-id="4c067-126">[!code-vb[VbVbcnProcedures&4;](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4c067-126">[!code-vb[VbVbcnProcedures#4](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]</span></span>  
  
### <a name="to-call-an-event-handler-using-addhandler"></a><span data-ttu-id="4c067-127">Mit AddHandler einen Ereignishandler aufrufen</span><span class="sxs-lookup"><span data-stu-id="4c067-127">To call an event handler using AddHandler</span></span>  
  
1.  <span data-ttu-id="4c067-128">Stellen Sie sicher, dass das Ereignis mit deklariert eine `Event` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4c067-128">Make sure the event is declared with an `Event` statement.</span></span>  
  
2.  <span data-ttu-id="4c067-129">Führen Sie eine [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md) dynamisch die Ereignisbehandlung zu verknüpfen `Sub` Prozedur mit dem Ereignis.</span><span class="sxs-lookup"><span data-stu-id="4c067-129">Execute an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>  
  
3.  <span data-ttu-id="4c067-130">Wenn das Ereignis eintritt, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ruft automatisch die `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="4c067-130">When the event occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="4c067-131">Code können Sie eine `RaiseEvent` Anweisung, damit das Ereignis auftreten.</span><span class="sxs-lookup"><span data-stu-id="4c067-131">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="4c067-132">Das folgende Beispiel definiert eine `Sub` Prozedur zum Behandeln der <xref:System.Windows.Forms.Form.Closing>-Ereignis eines Formulars.</xref:System.Windows.Forms.Form.Closing></span><span class="sxs-lookup"><span data-stu-id="4c067-132">The following example defines a `Sub` procedure to handle the <xref:System.Windows.Forms.Form.Closing> event of a form.</span></span> <span data-ttu-id="4c067-133">Anschließend wird mithilfe der [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md) Zuordnen der `catchClose` Prozedur als Ereignishandler für <xref:System.Windows.Forms.Form.Closing>.</xref:System.Windows.Forms.Form.Closing></span><span class="sxs-lookup"><span data-stu-id="4c067-133">It then uses the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to associate the `catchClose` procedure as an event handler for <xref:System.Windows.Forms.Form.Closing>.</span></span>  
  
     <span data-ttu-id="4c067-134">[!code-vb[VbVbcnProcedures&5;](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="4c067-134">[!code-vb[VbVbcnProcedures#5](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]</span></span>  
  
     <span data-ttu-id="4c067-135">Sie können einen Ereignishandler aus einem Ereignis trennen, durch Ausführen der [RemoveHandler-Anweisung](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4c067-135">You can dissociate an event handler from an event by executing the [RemoveHandler Statement](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c067-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c067-136">See Also</span></span>  
 <span data-ttu-id="4c067-137">[Verfahren](./index.md) </span><span class="sxs-lookup"><span data-stu-id="4c067-137">[Procedures](./index.md) </span></span>  
<span data-ttu-id="4c067-138"> [Sub-Prozeduren](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="4c067-138"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="4c067-139"> [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4c067-139"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="4c067-140"> [AddressOf-Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="4c067-140"> [AddressOf Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="4c067-141"> [Gewusst wie: Erstellen einer Prozedur](./how-to-create-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="4c067-141"> [How to: Create a Procedure](./how-to-create-a-procedure.md) </span></span>  
<span data-ttu-id="4c067-142"> [Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span><span class="sxs-lookup"><span data-stu-id="4c067-142"> [How to: Call a Procedure that Does Not Return a Value](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span></span>
