---
title: SyncLock-Anweisung
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c0c826e1ba592dfc4f2899a26102466d2e7df54f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="synclock-statement"></a><span data-ttu-id="d2600-102">SyncLock-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d2600-102">SyncLock Statement</span></span>
<span data-ttu-id="d2600-103">Ruft eine exklusive Sperre für einen Anweisungsblock vor der Ausführung des Blocks ab.</span><span class="sxs-lookup"><span data-stu-id="d2600-103">Acquires an exclusive lock for a statement block before executing the block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2600-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2600-104">Syntax</span></span>  
  
```  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a><span data-ttu-id="d2600-105">Teile</span><span class="sxs-lookup"><span data-stu-id="d2600-105">Parts</span></span>  
 `lockobject`  
 <span data-ttu-id="d2600-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d2600-106">Required.</span></span> <span data-ttu-id="d2600-107">Ein Ausdruck, der einen Objektverweis ergibt.</span><span class="sxs-lookup"><span data-stu-id="d2600-107">Expression that evaluates to an object reference.</span></span>  
  
 `block`  
 <span data-ttu-id="d2600-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="d2600-108">Optional.</span></span> <span data-ttu-id="d2600-109">Der Block von Anweisungen, die ausgeführt werden, wenn die Sperre abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="d2600-109">Block of statements that are to execute when the lock is acquired.</span></span>  
  
 `End SyncLock`  
 <span data-ttu-id="d2600-110">Beendet eine `SyncLock` Block.</span><span class="sxs-lookup"><span data-stu-id="d2600-110">Terminates a `SyncLock` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2600-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d2600-111">Remarks</span></span>  
 <span data-ttu-id="d2600-112">Die `SyncLock` -Anweisung sicher, dass den Anweisungsblock nicht von mehreren Threads gleichzeitig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d2600-112">The `SyncLock` statement ensures that multiple threads do not execute the statement block at the same time.</span></span> <span data-ttu-id="d2600-113">`SyncLock`verhindert, dass jeder Thread den Block eintritt, bis keine anderen Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d2600-113">`SyncLock` prevents each thread from entering the block until no other thread is executing it.</span></span>  
  
 <span data-ttu-id="d2600-114">Die häufigste Verwendung von `SyncLock` zu verhindern, dass Daten von mehreren Threads gleichzeitig aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="d2600-114">The most common use of `SyncLock` is to protect data from being updated by more than one thread simultaneously.</span></span> <span data-ttu-id="d2600-115">Wenn die Anweisungen, die die Daten bearbeiten können bis zum Abschluss ohne Unterbrechung wechseln müssen, platzieren Sie sie innerhalb einer `SyncLock` Block.</span><span class="sxs-lookup"><span data-stu-id="d2600-115">If the statements that manipulate the data must go to completion without interruption, put them inside a `SyncLock` block.</span></span>  
  
 <span data-ttu-id="d2600-116">Ein Anweisungsblock geschützt durch eine exklusive Sperre bezeichnet eine *kritischen Abschnitt*.</span><span class="sxs-lookup"><span data-stu-id="d2600-116">A statement block protected by an exclusive lock is sometimes called a *critical section*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="d2600-117">Regeln</span><span class="sxs-lookup"><span data-stu-id="d2600-117">Rules</span></span>  
  
-   <span data-ttu-id="d2600-118">Verzweigen.</span><span class="sxs-lookup"><span data-stu-id="d2600-118">Branching.</span></span> <span data-ttu-id="d2600-119">Sie können keine Verzweigung in einer `SyncLock` Blockieren von außerhalb des Blocks.</span><span class="sxs-lookup"><span data-stu-id="d2600-119">You cannot branch into a `SyncLock` block from outside the block.</span></span>  
  
-   <span data-ttu-id="d2600-120">Der Wert der Lock-Objekts.</span><span class="sxs-lookup"><span data-stu-id="d2600-120">Lock Object Value.</span></span> <span data-ttu-id="d2600-121">Der Wert der `lockobject` nicht `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="d2600-121">The value of `lockobject` cannot be `Nothing`.</span></span> <span data-ttu-id="d2600-122">Sie müssen das Sperrenobjekt erstellen, bevor Sie es im Verwenden einer `SyncLock` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d2600-122">You must create the lock object before you use it in a `SyncLock` statement.</span></span>  
  
     <span data-ttu-id="d2600-123">Sie können den Wert der ändern `lockobject` während der Ausführung eine `SyncLock` Block.</span><span class="sxs-lookup"><span data-stu-id="d2600-123">You cannot change the value of `lockobject` while executing a `SyncLock` block.</span></span> <span data-ttu-id="d2600-124">Der Mechanismus ist erforderlich, dass das Sperrobjekt unverändert bleiben.</span><span class="sxs-lookup"><span data-stu-id="d2600-124">The mechanism requires that the lock object remain unchanged.</span></span>  
  
-   <span data-ttu-id="d2600-125">Können Sie keine der ["await"](../../../visual-basic/language-reference/operators/await-operator.md) Operator in einem `SyncLock` Block.</span><span class="sxs-lookup"><span data-stu-id="d2600-125">You can't use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in a `SyncLock` block.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="d2600-126">Verhalten</span><span class="sxs-lookup"><span data-stu-id="d2600-126">Behavior</span></span>  
  
-   <span data-ttu-id="d2600-127">Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="d2600-127">Mechanism.</span></span> <span data-ttu-id="d2600-128">Wenn ein Thread erreicht die `SyncLock` -Anweisung ausgewertet den `lockobject` Ausdruck und hält die Ausführung bis er eine exklusive Sperre für das Objekt, das von dem Ausdruck zurückgegeben erhält.</span><span class="sxs-lookup"><span data-stu-id="d2600-128">When a thread reaches the `SyncLock` statement, it evaluates the `lockobject` expression and suspends execution until it acquires an exclusive lock on the object returned by the expression.</span></span> <span data-ttu-id="d2600-129">Wenn ein anderer Thread erreicht die `SyncLock` -Anweisung, erwirbt er eine Sperre, bis der erste Thread führt die `End SyncLock` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d2600-129">When another thread reaches the `SyncLock` statement, it does not acquire a lock until the first thread executes the `End SyncLock` statement.</span></span>  
  
-   <span data-ttu-id="d2600-130">Stellen Sie geschützte Daten.</span><span class="sxs-lookup"><span data-stu-id="d2600-130">Protected Data.</span></span> <span data-ttu-id="d2600-131">Wenn `lockobject` ist ein `Shared` Variable, die exklusive Sperre verhindert, dass einen Thread in jeder Instanz der Klasse Ausführen der `SyncLock` blockieren, während ein anderer Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d2600-131">If `lockobject` is a `Shared` variable, the exclusive lock prevents a thread in any instance of the class from executing the `SyncLock` block while any other thread is executing it.</span></span> <span data-ttu-id="d2600-132">Dies schützt die Daten, die von allen Instanzen gemeinsam genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="d2600-132">This protects data that is shared among all the instances.</span></span>  
  
     <span data-ttu-id="d2600-133">Wenn `lockobject` wird von eine Instanzvariablen (nicht `Shared`), die Sperre verhindert, dass einen Thread in der aktuellen Instanz ausgeführt wird, verhindern Sie die Ausführung der `SyncLock` Block zur gleichen Zeit wie ein anderer Thread in der gleichen Instanz.</span><span class="sxs-lookup"><span data-stu-id="d2600-133">If `lockobject` is an instance variable (not `Shared`), the lock prevents a thread running in the current instance from executing the `SyncLock` block at the same time as another thread in the same instance.</span></span> <span data-ttu-id="d2600-134">Dies schützt die Daten, die von einzelnen Instanzen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d2600-134">This protects data maintained by the individual instance.</span></span>  
  
-   <span data-ttu-id="d2600-135">Erhalt und die Freigabe.</span><span class="sxs-lookup"><span data-stu-id="d2600-135">Acquisition and Release.</span></span> <span data-ttu-id="d2600-136">Ein `SyncLock` Block verhält sich wie ein `Try...Finally` Konstruktion, in dem die `Try` Block erhält eine exklusive Sperre auf `lockobject` und die `Finally` Block freigibt.</span><span class="sxs-lookup"><span data-stu-id="d2600-136">A `SyncLock` block behaves like a `Try...Finally` construction in which the `Try` block acquires an exclusive lock on `lockobject` and the `Finally` block releases it.</span></span> <span data-ttu-id="d2600-137">Aus diesem Grund die `SyncLock` Block wird sichergestellt, Freigabe der Sperre, unabhängig davon, wie Sie den Block zu beenden.</span><span class="sxs-lookup"><span data-stu-id="d2600-137">Because of this, the `SyncLock` block guarantees release of the lock, no matter how you exit the block.</span></span> <span data-ttu-id="d2600-138">Dies gilt sogar im Fall einer nicht behandelten Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="d2600-138">This is true even in the case of an unhandled exception.</span></span>  
  
-   <span data-ttu-id="d2600-139">Framework-Aufrufe.</span><span class="sxs-lookup"><span data-stu-id="d2600-139">Framework Calls.</span></span> <span data-ttu-id="d2600-140">Die `SyncLock` -Block erwirbt und hebt die exklusive Sperre durch Aufrufen der `Enter` und `Exit` Methoden die `Monitor` -Klasse in der <xref:System.Threading> Namespace.</span><span class="sxs-lookup"><span data-stu-id="d2600-140">The `SyncLock` block acquires and releases the exclusive lock by calling the `Enter` and `Exit` methods of the `Monitor` class in the <xref:System.Threading> namespace.</span></span>  
  
## <a name="programming-practices"></a><span data-ttu-id="d2600-141">Programmierung-Methoden</span><span class="sxs-lookup"><span data-stu-id="d2600-141">Programming Practices</span></span>  
 <span data-ttu-id="d2600-142">Die `lockobject` Ausdruck ergeben sollten immer ein Objekt, das ausschließlich auf die Klasse gehört.</span><span class="sxs-lookup"><span data-stu-id="d2600-142">The `lockobject` expression should always evaluate to an object that belongs exclusively to your class.</span></span> <span data-ttu-id="d2600-143">Deklarieren Sie eine `Private` Object-Variablen zum Schützen von Daten, die auf die aktuelle Instanz gehört oder eine `Private Shared` Object-Variablen zum Schützen von Daten, die alle Instanzen gemeinsam.</span><span class="sxs-lookup"><span data-stu-id="d2600-143">You should declare a `Private` object variable to protect data belonging to the current instance, or a `Private Shared` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="d2600-144">Verwenden Sie nicht die `Me` Schlüsselwort ermöglichen eine Sperre für die Instanz Objektdaten.</span><span class="sxs-lookup"><span data-stu-id="d2600-144">You should not use the `Me` keyword to provide a lock object for instance data.</span></span> <span data-ttu-id="d2600-145">Wenn Code außerhalb der Klasse einen Verweis auf eine Instanz der Klasse enthält, konnte es diesen Verweis verwenden, als ein Sperrobjekt für die für eine `SyncLock` Block ganz anderen von Ihnen, unterschiedliche Daten schützen.</span><span class="sxs-lookup"><span data-stu-id="d2600-145">If code external to your class has a reference to an instance of your class, it could use that reference as a lock object for a `SyncLock` block completely different from yours, protecting different data.</span></span> <span data-ttu-id="d2600-146">Auf diese Weise Ihre Klasse und die andere Klasse können einander blockieren Ausführung ihrer unabhängigen `SyncLock` blockiert.</span><span class="sxs-lookup"><span data-stu-id="d2600-146">In this way, your class and the other class could block each other from executing their unrelated `SyncLock` blocks.</span></span> <span data-ttu-id="d2600-147">Auf ähnliche Weise Sperren für eine Zeichenfolge kann problematisch werden, da es sich bei jedem anderen Code in den Prozess über die gleiche Zeichenfolge dieselbe Sperre freigibt.</span><span class="sxs-lookup"><span data-stu-id="d2600-147">Similarly locking on a string can be problematic since any other code in the process using the same string will share the same lock.</span></span>  
  
 <span data-ttu-id="d2600-148">Verwenden Sie zudem nicht die `Me.GetType` freigegebene Methode, um ein Sperrobjekt für die für bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d2600-148">You should also not use the `Me.GetType` method to provide a lock object for shared data.</span></span> <span data-ttu-id="d2600-149">Grund hierfür ist, `GetType` gibt immer die gleiche `Type` Objekt für einen bestimmten Klassennamen.</span><span class="sxs-lookup"><span data-stu-id="d2600-149">This is because `GetType` always returns the same `Type` object for a given class name.</span></span> <span data-ttu-id="d2600-150">Externer Code Aufrufen `GetType` für Ihre Klasse und erhalten dasselbe Sperrobjekt, das Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2600-150">External code could call `GetType` on your class and obtain the same lock object you are using.</span></span> <span data-ttu-id="d2600-151">Dies würde die beiden Klassen blockieren miteinander aus ihren `SyncLock` blockiert.</span><span class="sxs-lookup"><span data-stu-id="d2600-151">This would result in the two classes blocking each other from their `SyncLock` blocks.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d2600-152">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d2600-152">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="d2600-153">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2600-153">Description</span></span>  
 <span data-ttu-id="d2600-154">Das folgende Beispiel zeigt eine Klasse, die eine einfache Liste von Nachrichten verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d2600-154">The following example shows a class that maintains a simple list of messages.</span></span> <span data-ttu-id="d2600-155">Es enthält die Nachrichten in einem Array und das letzte Element des Arrays in einer Variablen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d2600-155">It holds the messages in an array and the last used element of that array in a variable.</span></span> <span data-ttu-id="d2600-156">Die `addAnotherMessage` erhöht das letzte Element und speichert die neue Nachricht.</span><span class="sxs-lookup"><span data-stu-id="d2600-156">The `addAnotherMessage` procedure increments the last element and stores the new message.</span></span> <span data-ttu-id="d2600-157">Diese beiden Vorgänge werden geschützt, indem die `SyncLock` und `End SyncLock` -Anweisungen, denn sobald das letzte Element erhöht wurde, die neue Nachricht gespeichert werden muss vor dem ein anderen Threads das letzte Element erneut inkrementieren kann.</span><span class="sxs-lookup"><span data-stu-id="d2600-157">Those two operations are protected by the `SyncLock` and `End SyncLock` statements, because once the last element has been incremented, the new message must be stored before any other thread can increment the last element again.</span></span>  
  
 <span data-ttu-id="d2600-158">Wenn die `simpleMessageList` Klasse eine Liste von Nachrichten zwischen alle zugehörigen Instanzen, die Variablen freigegebener `messagesList` und `messagesLast` deklariert werden als `Shared`.</span><span class="sxs-lookup"><span data-stu-id="d2600-158">If the `simpleMessageList` class shared one list of messages among all its instances, the variables `messagesList` and `messagesLast` would be declared as `Shared`.</span></span> <span data-ttu-id="d2600-159">In diesem Fall wird die Variable `messagesLock` muss auch `Shared`, sodass gäbe es ein einzelnes Lock-Objekt, das von jeder Instanz verwendet.</span><span class="sxs-lookup"><span data-stu-id="d2600-159">In this case, the variable `messagesLock` should also be `Shared`, so that there would be a single lock object used by every instance.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d2600-160">Code</span><span class="sxs-lookup"><span data-stu-id="d2600-160">Code</span></span>  
 [!code-vb[VbVbalrThreading#1](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_1.vb)]  
  
### <a name="description"></a><span data-ttu-id="d2600-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2600-161">Description</span></span>  
 <span data-ttu-id="d2600-162">Im folgenden Beispiel wird die Threads und `SyncLock`.</span><span class="sxs-lookup"><span data-stu-id="d2600-162">The following example uses threads and `SyncLock`.</span></span> <span data-ttu-id="d2600-163">Solange die `SyncLock` Anweisung vorhanden ist, der Anweisungsblock eines kritischen Abschnitts und `balance` wird nie eine negative Zahl.</span><span class="sxs-lookup"><span data-stu-id="d2600-163">As long as the `SyncLock` statement is present, the statement block is a critical section and `balance` never becomes a negative number.</span></span> <span data-ttu-id="d2600-164">Können Sie Auskommentieren der `SyncLock` und `End SyncLock` Anweisungen, die Auswirkungen der eingepasst finden Sie unter der `SyncLock` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="d2600-164">You can comment out the `SyncLock` and `End SyncLock` statements to see the effect of leaving out the `SyncLock` keyword.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d2600-165">Code</span><span class="sxs-lookup"><span data-stu-id="d2600-165">Code</span></span>  
 [!code-vb[VbVbalrThreading#21](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_2.vb)]  
  
### <a name="comments"></a><span data-ttu-id="d2600-166">Kommentare</span><span class="sxs-lookup"><span data-stu-id="d2600-166">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2600-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2600-167">See Also</span></span>  
 <xref:System.Threading>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="d2600-168">Threadsynchronisierung</span><span class="sxs-lookup"><span data-stu-id="d2600-168">Thread Synchronization</span></span>](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4)  
 [<span data-ttu-id="d2600-169">Threading</span><span class="sxs-lookup"><span data-stu-id="d2600-169">Threading</span></span>](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)
