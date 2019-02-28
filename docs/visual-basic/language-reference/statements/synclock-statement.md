---
title: SyncLock-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: 3a12c3ac7250ee2904d571406d5008d451c9dc35
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979813"
---
# <a name="synclock-statement"></a><span data-ttu-id="1e680-102">SyncLock-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1e680-102">SyncLock Statement</span></span>
<span data-ttu-id="1e680-103">Ruft eine exklusive Sperre für einen Anweisungsblock vor der Ausführung des Blocks ab.</span><span class="sxs-lookup"><span data-stu-id="1e680-103">Acquires an exclusive lock for a statement block before executing the block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e680-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e680-104">Syntax</span></span>  
  
```  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a><span data-ttu-id="1e680-105">Teile</span><span class="sxs-lookup"><span data-stu-id="1e680-105">Parts</span></span>  
 `lockobject`  
 <span data-ttu-id="1e680-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1e680-106">Required.</span></span> <span data-ttu-id="1e680-107">Ein Ausdruck, einen Objektverweis ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="1e680-107">Expression that evaluates to an object reference.</span></span>  
  
 `block`  
 <span data-ttu-id="1e680-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="1e680-108">Optional.</span></span> <span data-ttu-id="1e680-109">Der Block von Anweisungen, die ausgeführt werden, wenn die Sperre abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="1e680-109">Block of statements that are to execute when the lock is acquired.</span></span>  
  
 `End SyncLock`  
 <span data-ttu-id="1e680-110">Beendet eine `SyncLock` Block.</span><span class="sxs-lookup"><span data-stu-id="1e680-110">Terminates a `SyncLock` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e680-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1e680-111">Remarks</span></span>  
 <span data-ttu-id="1e680-112">Die `SyncLock` Anweisung wird sichergestellt, dass den Anweisungsblock nicht von mehreren Threads gleichzeitig ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1e680-112">The `SyncLock` statement ensures that multiple threads do not execute the statement block at the same time.</span></span> <span data-ttu-id="1e680-113">`SyncLock` verhindert, dass jeder Thread den Block eingeben, bis kein anderer Thread sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1e680-113">`SyncLock` prevents each thread from entering the block until no other thread is executing it.</span></span>  
  
 <span data-ttu-id="1e680-114">Die häufigste Verwendung von `SyncLock` zum Schutz von Daten aus, die gleichzeitig von mehreren Threads aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="1e680-114">The most common use of `SyncLock` is to protect data from being updated by more than one thread simultaneously.</span></span> <span data-ttu-id="1e680-115">Wenn die Anweisungen, die die Daten bearbeiten können bis zum Abschluss ohne Unterbrechung wechseln müssen, platzieren Sie sie in einem `SyncLock` Block.</span><span class="sxs-lookup"><span data-stu-id="1e680-115">If the statements that manipulate the data must go to completion without interruption, put them inside a `SyncLock` block.</span></span>  
  
 <span data-ttu-id="1e680-116">Ein Anweisungsblock, die durch eine exklusive Sperre geschützt wird auch als bezeichnet. eine *kritischen Abschnitt*.</span><span class="sxs-lookup"><span data-stu-id="1e680-116">A statement block protected by an exclusive lock is sometimes called a *critical section*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="1e680-117">Regeln</span><span class="sxs-lookup"><span data-stu-id="1e680-117">Rules</span></span>  
  
-   <span data-ttu-id="1e680-118">Branch.</span><span class="sxs-lookup"><span data-stu-id="1e680-118">Branching.</span></span> <span data-ttu-id="1e680-119">Sie können keine branch in einen `SyncLock` Blockieren von außerhalb des Blocks.</span><span class="sxs-lookup"><span data-stu-id="1e680-119">You cannot branch into a `SyncLock` block from outside the block.</span></span>  
  
-   <span data-ttu-id="1e680-120">Der Wert der Sperre-Objekts.</span><span class="sxs-lookup"><span data-stu-id="1e680-120">Lock Object Value.</span></span> <span data-ttu-id="1e680-121">Der Wert des `lockobject` nicht `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="1e680-121">The value of `lockobject` cannot be `Nothing`.</span></span> <span data-ttu-id="1e680-122">Sie müssen das Sperrobjekt erstellen, bevor Sie ihn im Verwenden einer `SyncLock` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1e680-122">You must create the lock object before you use it in a `SyncLock` statement.</span></span>  
  
     <span data-ttu-id="1e680-123">Sie können den Wert nicht ändern `lockobject` während der Ausführung einer `SyncLock` Block.</span><span class="sxs-lookup"><span data-stu-id="1e680-123">You cannot change the value of `lockobject` while executing a `SyncLock` block.</span></span> <span data-ttu-id="1e680-124">Der Mechanismus ist erforderlich, dass das Sperrobjekt unverändert bleiben.</span><span class="sxs-lookup"><span data-stu-id="1e680-124">The mechanism requires that the lock object remain unchanged.</span></span>  
  
-   <span data-ttu-id="1e680-125">Können keine der ["await"](../../../visual-basic/language-reference/operators/await-operator.md) -Operator in einem `SyncLock` Block.</span><span class="sxs-lookup"><span data-stu-id="1e680-125">You can't use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in a `SyncLock` block.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="1e680-126">Verhalten</span><span class="sxs-lookup"><span data-stu-id="1e680-126">Behavior</span></span>  
  
-   <span data-ttu-id="1e680-127">Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="1e680-127">Mechanism.</span></span> <span data-ttu-id="1e680-128">Wenn ein Thread erreicht die `SyncLock` -Anweisung, es ergibt die `lockobject` Ausdruck und angehalten, bis er eine exklusive Sperre für das Objekt, das vom Ausdruck zurückgegebene erhält.</span><span class="sxs-lookup"><span data-stu-id="1e680-128">When a thread reaches the `SyncLock` statement, it evaluates the `lockobject` expression and suspends execution until it acquires an exclusive lock on the object returned by the expression.</span></span> <span data-ttu-id="1e680-129">Wenn ein anderer Thread erreicht die `SyncLock` -Anweisung, es ist nicht Ruft eine Sperre, bis der erste Thread führt die `End SyncLock` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1e680-129">When another thread reaches the `SyncLock` statement, it does not acquire a lock until the first thread executes the `End SyncLock` statement.</span></span>  
  
-   <span data-ttu-id="1e680-130">Stellen Sie geschützte Daten.</span><span class="sxs-lookup"><span data-stu-id="1e680-130">Protected Data.</span></span> <span data-ttu-id="1e680-131">Wenn `lockobject` ist eine `Shared` Variablen, die exklusive Sperre verhindert, dass einen Thread in jeder Instanz der Klasse Ausführen der `SyncLock` zu blockieren, während alle anderen Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1e680-131">If `lockobject` is a `Shared` variable, the exclusive lock prevents a thread in any instance of the class from executing the `SyncLock` block while any other thread is executing it.</span></span> <span data-ttu-id="1e680-132">Dies schützt die Daten, die von allen Instanzen gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1e680-132">This protects data that is shared among all the instances.</span></span>  
  
     <span data-ttu-id="1e680-133">Wenn `lockobject` ist eine Instanzvariable (nicht `Shared`), die Sperre verhindert einen Thread, in der aktuellen Instanz der Ausführung der `SyncLock` Block zur gleichen Zeit wie ein anderer Thread in der gleichen Instanz.</span><span class="sxs-lookup"><span data-stu-id="1e680-133">If `lockobject` is an instance variable (not `Shared`), the lock prevents a thread running in the current instance from executing the `SyncLock` block at the same time as another thread in the same instance.</span></span> <span data-ttu-id="1e680-134">Dies schützt die Daten, die von den einzelnen Instanzen verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="1e680-134">This protects data maintained by the individual instance.</span></span>  
  
-   <span data-ttu-id="1e680-135">Abruf und die Freigabe.</span><span class="sxs-lookup"><span data-stu-id="1e680-135">Acquisition and Release.</span></span> <span data-ttu-id="1e680-136">Ein `SyncLock` Block verhält sich wie ein `Try...Finally` Konstruktion, in dem die `Try` Block erhält eine exklusive Sperre auf `lockobject` und `Finally` Block freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1e680-136">A `SyncLock` block behaves like a `Try...Finally` construction in which the `Try` block acquires an exclusive lock on `lockobject` and the `Finally` block releases it.</span></span> <span data-ttu-id="1e680-137">Aus diesem Grund die `SyncLock` Block gewährleistet die Aufhebung der Sperre, unabhängig davon, wie Sie den Block zu beenden.</span><span class="sxs-lookup"><span data-stu-id="1e680-137">Because of this, the `SyncLock` block guarantees release of the lock, no matter how you exit the block.</span></span> <span data-ttu-id="1e680-138">Dies gilt auch im Falle einer nicht behandelten Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="1e680-138">This is true even in the case of an unhandled exception.</span></span>  
  
-   <span data-ttu-id="1e680-139">Framework-Aufrufe.</span><span class="sxs-lookup"><span data-stu-id="1e680-139">Framework Calls.</span></span> <span data-ttu-id="1e680-140">Die `SyncLock` Block erhält und hebt die exklusive Sperre durch Aufrufen der `Enter` und `Exit` Methoden der `Monitor` -Klasse in der <xref:System.Threading> Namespace.</span><span class="sxs-lookup"><span data-stu-id="1e680-140">The `SyncLock` block acquires and releases the exclusive lock by calling the `Enter` and `Exit` methods of the `Monitor` class in the <xref:System.Threading> namespace.</span></span>  
  
## <a name="programming-practices"></a><span data-ttu-id="1e680-141">Methoden für die Programmierung</span><span class="sxs-lookup"><span data-stu-id="1e680-141">Programming Practices</span></span>  
 <span data-ttu-id="1e680-142">Die `lockobject` Ausdruck ergeben sollten immer ein Objekt, das ausschließlich auf die Klasse gehört.</span><span class="sxs-lookup"><span data-stu-id="1e680-142">The `lockobject` expression should always evaluate to an object that belongs exclusively to your class.</span></span> <span data-ttu-id="1e680-143">Deklarieren Sie eine `Private` Objektvariable zum Schutz von Daten, die auf die aktuelle Instanz gehören oder `Private Shared` Objektvariable, um Daten in allen Instanzen häufig zu schützen.</span><span class="sxs-lookup"><span data-stu-id="1e680-143">You should declare a `Private` object variable to protect data belonging to the current instance, or a `Private Shared` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="1e680-144">Verwenden Sie nicht die `Me` Schlüsselwort, um eine Sperre geben z. B. Objektdaten.</span><span class="sxs-lookup"><span data-stu-id="1e680-144">You should not use the `Me` keyword to provide a lock object for instance data.</span></span> <span data-ttu-id="1e680-145">Wenn Code außerhalb der Klasse einen Verweis auf eine Instanz der Klasse enthält, können sie diesen Verweis verwenden, als Sperrobjekt für eine `SyncLock` blockieren, die von ihren Bildschirmen, grundlegend andere Daten geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="1e680-145">If code external to your class has a reference to an instance of your class, it could use that reference as a lock object for a `SyncLock` block completely different from yours, protecting different data.</span></span> <span data-ttu-id="1e680-146">Auf diese Weise Ihre Klasse und die andere Klasse können einander blockieren hindert, die nicht verknüpfte `SyncLock` Blöcke.</span><span class="sxs-lookup"><span data-stu-id="1e680-146">In this way, your class and the other class could block each other from executing their unrelated `SyncLock` blocks.</span></span> <span data-ttu-id="1e680-147">Auf ähnliche Weise Sperren für eine Zeichenfolge kann problematisch sein, da es sich bei jedem anderen Code in den Prozess über die gleiche Zeichenfolge die gleiche Sperre freigibt.</span><span class="sxs-lookup"><span data-stu-id="1e680-147">Similarly locking on a string can be problematic since any other code in the process using the same string will share the same lock.</span></span>  
  
 <span data-ttu-id="1e680-148">Sie sollten auch nicht verwenden, die `Me.GetType` freigegebene Methode, um ein Sperrobjekt für bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1e680-148">You should also not use the `Me.GetType` method to provide a lock object for shared data.</span></span> <span data-ttu-id="1e680-149">Grund hierfür ist, `GetType` gibt immer die gleiche `Type` Objekt für einen bestimmten Klassennamen.</span><span class="sxs-lookup"><span data-stu-id="1e680-149">This is because `GetType` always returns the same `Type` object for a given class name.</span></span> <span data-ttu-id="1e680-150">Externer Code Aufrufen `GetType` für Ihre Klasse und rufen Sie die gleiche Sperrobjekt, das Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e680-150">External code could call `GetType` on your class and obtain the same lock object you are using.</span></span> <span data-ttu-id="1e680-151">Dies führt zu die beiden Klassen, dass die von ihren `SyncLock` Blöcke.</span><span class="sxs-lookup"><span data-stu-id="1e680-151">This would result in the two classes blocking each other from their `SyncLock` blocks.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1e680-152">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1e680-152">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="1e680-153">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e680-153">Description</span></span>  
 <span data-ttu-id="1e680-154">Das folgende Beispiel zeigt eine Klasse, die eine einfache Liste von Nachrichten verwaltet.</span><span class="sxs-lookup"><span data-stu-id="1e680-154">The following example shows a class that maintains a simple list of messages.</span></span> <span data-ttu-id="1e680-155">Sie enthält die Nachrichten in einem Array und das letzte Element dieses Arrays in eine Variable verwendet.</span><span class="sxs-lookup"><span data-stu-id="1e680-155">It holds the messages in an array and the last used element of that array in a variable.</span></span> <span data-ttu-id="1e680-156">Die `addAnotherMessage` Prozedur erhöht das letzte Element und speichert die neue Meldung.</span><span class="sxs-lookup"><span data-stu-id="1e680-156">The `addAnotherMessage` procedure increments the last element and stores the new message.</span></span> <span data-ttu-id="1e680-157">Diese beiden Vorgänge sind geschützt, indem die `SyncLock` und `End SyncLock` -Anweisungen, da nach das letzte Element erhöht wurde, die neue Nachricht gespeichert werden muss, bevor ein anderer Thread das letzte Element erneut erhöhen kann.</span><span class="sxs-lookup"><span data-stu-id="1e680-157">Those two operations are protected by the `SyncLock` and `End SyncLock` statements, because once the last element has been incremented, the new message must be stored before any other thread can increment the last element again.</span></span>  
  
 <span data-ttu-id="1e680-158">Wenn die `simpleMessageList` Klasse freigegeben, eine Liste von Nachrichten auf alle zugehörigen Instanzen, die Variablen `messagesList` und `messagesLast` deklariert werden würde, als `Shared`.</span><span class="sxs-lookup"><span data-stu-id="1e680-158">If the `simpleMessageList` class shared one list of messages among all its instances, the variables `messagesList` and `messagesLast` would be declared as `Shared`.</span></span> <span data-ttu-id="1e680-159">In diesem Fall ist die Variable `messagesLock` außerdem sollte der `Shared`, sodass es gäbe eine einzige Sperre-Objekt, das von jeder Instanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1e680-159">In this case, the variable `messagesLock` should also be `Shared`, so that there would be a single lock object used by every instance.</span></span>  
  
### <a name="code"></a><span data-ttu-id="1e680-160">Code</span><span class="sxs-lookup"><span data-stu-id="1e680-160">Code</span></span>  
 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a><span data-ttu-id="1e680-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e680-161">Description</span></span>  
 <span data-ttu-id="1e680-162">Im folgenden Beispiel wird die Threads und `SyncLock`.</span><span class="sxs-lookup"><span data-stu-id="1e680-162">The following example uses threads and `SyncLock`.</span></span> <span data-ttu-id="1e680-163">Solange die `SyncLock` Anweisung vorhanden ist, der Anweisungsblock ein Kritischer Abschnitt und `balance` wird nie eine negative Zahl.</span><span class="sxs-lookup"><span data-stu-id="1e680-163">As long as the `SyncLock` statement is present, the statement block is a critical section and `balance` never becomes a negative number.</span></span> <span data-ttu-id="1e680-164">Können Sie Auskommentieren der `SyncLock` und `End SyncLock` Anweisungen, um die Auswirkungen der auslassen finden Sie unter den `SyncLock` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="1e680-164">You can comment out the `SyncLock` and `End SyncLock` statements to see the effect of leaving out the `SyncLock` keyword.</span></span>  
  
### <a name="code"></a><span data-ttu-id="1e680-165">Code</span><span class="sxs-lookup"><span data-stu-id="1e680-165">Code</span></span>  
 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a><span data-ttu-id="1e680-166">Kommentare</span><span class="sxs-lookup"><span data-stu-id="1e680-166">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e680-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e680-167">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="1e680-168">Übersicht über Synchronisierungsprimitiven</span><span class="sxs-lookup"><span data-stu-id="1e680-168">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)
