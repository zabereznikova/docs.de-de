---
title: Verwenden von Ausnahmen (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], about exceptions
ms.assetid: 71472c62-320a-470a-97d2-67995180389d
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 96fc082d135d38f521429de7b4e9a668773982ea
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="using-exceptions-c-programming-guide"></a><span data-ttu-id="ef08a-102">Verwenden von Ausnahmen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ef08a-102">Using Exceptions (C# Programming Guide)</span></span>
<span data-ttu-id="ef08a-103">In C# werden Fehler im Programm zur Laufzeit mithilfe von sogenannten Ausnahmen durch das Programm weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="ef08a-103">In C#, errors in the program at run time are propagated through the program by using a mechanism called exceptions.</span></span> <span data-ttu-id="ef08a-104">Ausnahmen werden von Code ausgelöst, der auf einen Fehler stößt. Sie werden von Code abgefangen, der den Fehler beheben kann.</span><span class="sxs-lookup"><span data-stu-id="ef08a-104">Exceptions are thrown by code that encounters an error and caught by code that can correct the error.</span></span> <span data-ttu-id="ef08a-105">Ausnahmen können durch die Common Language Runtime (CLR) von .NET Framework oder durch Code in einem Programm ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="ef08a-105">Exceptions can be thrown by the .NET Framework common language runtime (CLR) or by code in a program.</span></span> <span data-ttu-id="ef08a-106">Sobald eine Ausnahme ausgelöst wird, wird sie in der Aufrufliste nach oben weitergegeben, bis eine `catch`-Anweisung für die Ausnahme gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="ef08a-106">Once an exception is thrown, it propagates up the call stack until a `catch` statement for the exception is found.</span></span> <span data-ttu-id="ef08a-107">Nicht abgefangene Ausnahmen werden von einem generischen Ausnahmehandler behandelt, der vom System bereitgestellt wird, das ein Dialogfeld anzeigt.</span><span class="sxs-lookup"><span data-stu-id="ef08a-107">Uncaught exceptions are handled by a generic exception handler provided by the system that displays a dialog box.</span></span>  
  
 <span data-ttu-id="ef08a-108">Ausnahmen werden von Klassen dargestellt, die von <xref:System.Exception> abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="ef08a-108">Exceptions are represented by classes derived from <xref:System.Exception>.</span></span> <span data-ttu-id="ef08a-109">Diese Klasse bestimmt den Typ der Ausnahme und enthält Eigenschaften, die über Details zur Ausnahme verfügen.</span><span class="sxs-lookup"><span data-stu-id="ef08a-109">This class identifies the type of exception and contains properties that have details about the exception.</span></span> <span data-ttu-id="ef08a-110">Das Auslösen einer Ausnahme umfasst das Erstellen einer Instanz einer von einer Ausnahme abgeleiteten Klasse, das optionale Konfigurieren von Eigenschaften der Ausnahme und das Auslösen des Objekts mithilfe des Schlüsselworts `throw`.</span><span class="sxs-lookup"><span data-stu-id="ef08a-110">Throwing an exception involves creating an instance of an exception-derived class, optionally configuring properties of the exception, and then throwing the object by using the `throw` keyword.</span></span> <span data-ttu-id="ef08a-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ef08a-111">For example:</span></span>  
  
 <span data-ttu-id="ef08a-112">[!code-cs[csProgGuideExceptions#1](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ef08a-112">[!code-cs[csProgGuideExceptions#1](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_1.cs)]</span></span>  
  
 <span data-ttu-id="ef08a-113">Nachdem eine Ausnahme ausgelöst wird, überprüft die Runtime die aktuelle Anweisung, um festzustellen, ob sie sich in einem `try`-Block befindet.</span><span class="sxs-lookup"><span data-stu-id="ef08a-113">After an exception is thrown, the runtime checks the current statement to see whether it is within a `try` block.</span></span> <span data-ttu-id="ef08a-114">Falls dies der Fall ist, werden alle mit dem `try`-Block verknüpften `catch`-Blöcke überprüft, um festzustellen, ob sie die Ausnahme abfangen können.</span><span class="sxs-lookup"><span data-stu-id="ef08a-114">If it is, any `catch` blocks associated with the `try` block are checked to see whether they can catch the exception.</span></span> <span data-ttu-id="ef08a-115">`Catch`-Blöcke geben normalerweise Ausnahmetypen an; wenn der Typ des `catch`-Blocks der gleiche Typ ist wie die Ausnahme oder die Basisklasse der Ausnahme, kann der `catch`-Block die Methode behandeln.</span><span class="sxs-lookup"><span data-stu-id="ef08a-115">`Catch` blocks typically specify exception types; if the type of the `catch` block is the same type as the exception, or a base class of the exception, the `catch` block can handle the method.</span></span> <span data-ttu-id="ef08a-116">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ef08a-116">For example:</span></span>  
  
 <span data-ttu-id="ef08a-117">[!code-cs[csProgGuideExceptions#2](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="ef08a-117">[!code-cs[csProgGuideExceptions#2](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_2.cs)]</span></span>  
  
 <span data-ttu-id="ef08a-118">Wenn sich die Anweisung, die eine Ausnahme auslöst, nicht innerhalb eines `try`-Blocks befindet, oder der `try`-Block, der sie umfasst, über keinen übereinstimmenden `catch`-Block verfügt, überprüft die Runtime die aufrufende Methode auf eine `try`-Anweisung und `catch`-Blöcke.</span><span class="sxs-lookup"><span data-stu-id="ef08a-118">If the statement that throws an exception is not within a `try` block or if the `try` block that encloses it has no matching `catch` block, the runtime checks the calling method for a `try` statement and `catch` blocks.</span></span> <span data-ttu-id="ef08a-119">Die Runtime geht die Aufrufliste weiter nach oben durch und sucht nach einem kompatiblen `catch`-Block.</span><span class="sxs-lookup"><span data-stu-id="ef08a-119">The runtime continues up the calling stack, searching for a compatible `catch` block.</span></span> <span data-ttu-id="ef08a-120">Nachdem der `catch`-Block gefunden und ausgeführt wurde, wird die Steuerung an die nächste Anweisung nach diesem `catch`-Block weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="ef08a-120">After the `catch` block is found and executed, control is passed to the next statement after that `catch` block.</span></span>  
  
 <span data-ttu-id="ef08a-121">Eine `try`-Anweisung kann mehr als einen `catch`-Block enthalten.</span><span class="sxs-lookup"><span data-stu-id="ef08a-121">A `try` statement can contain more than one `catch` block.</span></span> <span data-ttu-id="ef08a-122">Die erste `catch`-Anweisung, die die Ausnahme behandelt, wird ausgeführt; alle folgenden `catch`-Anweisungen werden ignoriert, selbst wenn sie kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="ef08a-122">The first `catch` statement that can handle the exception is executed; any following `catch` statements, even if they are compatible, are ignored.</span></span> <span data-ttu-id="ef08a-123">Daher sollten catch-Blöcke immer vom spezifischsten Element (oder am meisten abgeleiteten) zum am wenigsten spezifischen sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="ef08a-123">Therefore, catch blocks should always be ordered from most specific (or most-derived) to least specific.</span></span> <span data-ttu-id="ef08a-124">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ef08a-124">For example:</span></span>  
  
 <span data-ttu-id="ef08a-125">[!code-cs[csProgGuideExceptions#3](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="ef08a-125">[!code-cs[csProgGuideExceptions#3](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_3.cs)]</span></span>  
  
 <span data-ttu-id="ef08a-126">Bevor der `catch`-Block ausgeführt wird prüft die Runtime auf `finally`-Blöcke.</span><span class="sxs-lookup"><span data-stu-id="ef08a-126">Before the `catch` block is executed, the runtime checks for `finally` blocks.</span></span> <span data-ttu-id="ef08a-127">`Finally`-Blöcke ermöglichen dem Programmierer, mehrdeutige Zustände zu bereinigen, die möglicherweise von einem abgebrochenen `try`-Block übrig sind, oder externe Ressourcen freizugeben (z.B. Grafikhandles, Datenbankverbindungen oder Dateistreams), ohne auf Garbage Collector in der Runtime zum Finalisieren der Objekte zu warten.</span><span class="sxs-lookup"><span data-stu-id="ef08a-127">`Finally` blocks enable the programmer to clean up any ambiguous state that could be left over from an aborted `try` block, or to release any external resources (such as graphics handles, database connections or file streams) without waiting for the garbage collector in the runtime to finalize the objects.</span></span> <span data-ttu-id="ef08a-128">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ef08a-128">For example:</span></span>  
  
 <span data-ttu-id="ef08a-129">[!code-cs[csProgGuideExceptions#4](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="ef08a-129">[!code-cs[csProgGuideExceptions#4](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_4.cs)]</span></span>  
  
 <span data-ttu-id="ef08a-130">Wenn `WriteByte()` eine Ausnahme auslöst, schlägt der Code im zweiten `try`-Block fehl, der versucht, die Datei erneut zu öffnen, wenn `file.Close()` nicht aufgerufen wird. Die Datei bleibt gesperrt.</span><span class="sxs-lookup"><span data-stu-id="ef08a-130">If `WriteByte()` threw an exception, the code in the second `try` block that tries to reopen the file would fail if `file.Close()` is not called, and the file would remain locked.</span></span> <span data-ttu-id="ef08a-131">Da `finally`-Blocke ausgeführt werden, selbst wenn eine Ausnahme ausgelöst wird, ermöglicht es der `finally`-Block im vorherigen Beispiel, dass die Datei korrekt geschlossen wird und trägt so zur Fehlervermeidung bei.</span><span class="sxs-lookup"><span data-stu-id="ef08a-131">Because `finally` blocks are executed even if an exception is thrown, the `finally` block in the previous example allows for the file to be closed correctly and helps avoid an error.</span></span>  
  
 <span data-ttu-id="ef08a-132">Wenn in der Aufrufliste kein kompatibler `catch`-Block gefunden wird, nachdem eine Ausnahme ausgelöst wird, tritt eine der folgenden Situationen auf:</span><span class="sxs-lookup"><span data-stu-id="ef08a-132">If no compatible `catch` block is found on the call stack after an exception is thrown, one of three things occurs:</span></span>  
  
-   <span data-ttu-id="ef08a-133">Wenn die Ausnahme sich in einem Finalizer befindet, wird der Finalizer abgebrochen und der Basisfinalizer (sofern vorhanden) aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ef08a-133">If the exception is within a finalizer, the finalizer is aborted and the base finalizer, if any, is called.</span></span>  
  
-   <span data-ttu-id="ef08a-134">Wenn die Aufrufliste einen statischen Konstruktor oder einen statischen Feldinitialisierer enthält, wird <xref:System.TypeInitializationException> ausgelöst und die ursprüngliche Ausnahme der <xref:System.Exception.InnerException%2A>-Eigenschaft der neuen Ausnahme zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="ef08a-134">If the call stack contains a static constructor, or a static field initializer, a <xref:System.TypeInitializationException> is thrown, with the original exception assigned to the <xref:System.Exception.InnerException%2A> property of the new exception.</span></span>  
  
-   <span data-ttu-id="ef08a-135">Wenn der Anfang des Threads erreicht wird, wird der Thread beendet.</span><span class="sxs-lookup"><span data-stu-id="ef08a-135">If the start of the thread is reached, the thread is terminated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef08a-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef08a-136">See Also</span></span>  
 <span data-ttu-id="ef08a-137">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ef08a-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="ef08a-138">Ausnahmen und Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="ef08a-138">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)

