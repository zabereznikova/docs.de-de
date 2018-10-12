---
title: lock-Anweisung (C#-Referenz)
description: Verwenden Sie die lock-Anweisung von C#, um den Threadzugriff auf eine freigegebene Ressource zu synchronisieren.
ms.date: 08/28/2018
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 2b6fbfb2f81d7745c4effb9ea0087f34cc872a6c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858355"
---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="41f61-103">lock-Anweisung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="41f61-103">lock statement (C# Reference)</span></span>

<span data-ttu-id="41f61-104">Mit der `lock`-Anweisung wird die Sperre für gegenseitigen Ausschluss für ein bestimmtes Objekt abgerufen, ein Anweisungsblock ausgeführt und die Sperre anschließend aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="41f61-104">The `lock` statement obtains the mutual-exclusion lock for a given object, executes a statement block, and then releases the lock.</span></span> <span data-ttu-id="41f61-105">Während eine Sperre aufrechterhalten wird, kann der Thread, der die Sperre aufrechterhält, die Sperre abrufen und aufheben.</span><span class="sxs-lookup"><span data-stu-id="41f61-105">While a lock is held, the thread that holds the lock can again obtain and release the lock.</span></span> <span data-ttu-id="41f61-106">Für jeden anderen Thread wird das Abrufen der Sperre blockiert, und die Sperre wartet auf die Aufhebung.</span><span class="sxs-lookup"><span data-stu-id="41f61-106">Any other thread is blocked from obtaining the lock and waits until the lock is released.</span></span>

<span data-ttu-id="41f61-107">Die `lock`-Anweisung weist folgendes Format auf:</span><span class="sxs-lookup"><span data-stu-id="41f61-107">The `lock` statement is of the form</span></span>

```csharp
lock (x)
{
    // Your code...
}
```

<span data-ttu-id="41f61-108">`x` entspricht einem Ausdruck eines [Verweistyps](reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="41f61-108">where `x` is an expression of a [reference type](reference-types.md).</span></span> <span data-ttu-id="41f61-109">Dieser entspricht exakt Folgendem:</span><span class="sxs-lookup"><span data-stu-id="41f61-109">It's precisely equivalent to</span></span>

```csharp
object __lockObj = x;
bool __lockWasTaken = false;
try
{
    System.Threading.Monitor.Enter(__lockObj, ref __lockWasTaken);
    // Your code...
}
finally
{
    if (__lockWasTaken) System.Threading.Monitor.Exit(__lockObj);
}
```

<span data-ttu-id="41f61-110">Da ein [try...finally](try-finally.md)-Block in diesem Code verwendet wird, wird die Sperre aufgehoben, wenn eine Ausnahme innerhalb des Texts einer `lock`-Anweisung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="41f61-110">Since the code uses a [try...finally](try-finally.md) block, the lock is released even if an exception is thrown within the body of a `lock` statement.</span></span>

<span data-ttu-id="41f61-111">Sie können das Schlüsselwort [await](await.md) nicht im Text einer `lock`-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="41f61-111">You can't use the [await](await.md) keyword in the body of a `lock` statement.</span></span>

## <a name="remarks"></a><span data-ttu-id="41f61-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41f61-112">Remarks</span></span>

<span data-ttu-id="41f61-113">Wenn Sie den Threadzugriff auf freigegebene Ressourcen synchronisieren, sperren Sie eine dedizierte Objektinstanz (z.B. `private readonly object balanceLock = new object();`) oder eine andere Instanz, für die es unwahrscheinlich ist, dass sie von anderen Teilen des Codes als lock-Objekt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="41f61-113">When you synchronize thread access to shared resource, lock on a dedicated object instance (for example, `private readonly object balanceLock = new object();`) or another instance that is unlikely to be used as a lock object by unrelated parts of the code.</span></span> <span data-ttu-id="41f61-114">Vermeiden Sie, die gleiche lock-Objektinstanz für verschiedene freigegebene Ressourcen zu verwenden, da dies zu einem Deadlock oder Sperrkonflikt führen kann.</span><span class="sxs-lookup"><span data-stu-id="41f61-114">Avoid using the same lock object instance for different shared resources, as it might result in deadlock or lock contention.</span></span> <span data-ttu-id="41f61-115">Vermeiden Sie insbesondere die Verwendung von</span><span class="sxs-lookup"><span data-stu-id="41f61-115">In particular, avoid using</span></span>

- <span data-ttu-id="41f61-116">`this` (kann von den Aufrufern als Sperre verwendet werden),</span><span class="sxs-lookup"><span data-stu-id="41f61-116">`this` (might be used by the callers as a lock),</span></span>
- <span data-ttu-id="41f61-117"><xref:System.Type>-Instanzen (kann vom [typeof](typeof.md)-Operator oder der Reflektion abgerufen werden),</span><span class="sxs-lookup"><span data-stu-id="41f61-117"><xref:System.Type> instances (might be obtained by the [typeof](typeof.md) operator or reflection),</span></span>
- <span data-ttu-id="41f61-118">Zeichenfolgeninstanzen, die Zeichenfolgenliterale enthalten,</span><span class="sxs-lookup"><span data-stu-id="41f61-118">string instances, including string literals,</span></span>

<span data-ttu-id="41f61-119">als lock-Objekte.</span><span class="sxs-lookup"><span data-stu-id="41f61-119">as lock objects.</span></span>

## <a name="example"></a><span data-ttu-id="41f61-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="41f61-120">Example</span></span>

<span data-ttu-id="41f61-121">Im folgenden Beispiel wird eine `Account`-Klasse definiert, die den Zugriff auf das private `balance`-Feld synchronisiert, indem eine dedizierte `balanceLock`-Instanz gesperrt wird.</span><span class="sxs-lookup"><span data-stu-id="41f61-121">The following example defines an `Account` class that synchronizes access to its private `balance` field by locking on a dedicated `balanceLock` instance.</span></span> <span data-ttu-id="41f61-122">Durch Verwendung der gleichen Instanz für die Sperre wird sichergestellt, dass das `balance`-Feld nicht von zwei Threads gleichzeitig aktualisiert werden kann, die zur gleichen Zeit versuchen, die Methoden `Debit` oder `Credit` aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="41f61-122">Using the same instance for locking ensures that the `balance` field cannot be updated simultaneously by two threads attempting to call the `Debit` or `Credit` methods simultaneously.</span></span>

[!code-csharp[lock-statement-example](~/samples/snippets/csharp/keywords/LockStatementExample.cs)]

## <a name="c-language-specification"></a><span data-ttu-id="41f61-123">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="41f61-123">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="41f61-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41f61-124">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.SpinLock?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="41f61-125">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="41f61-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="41f61-126">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="41f61-126">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="41f61-127">Anweisungsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="41f61-127">Statement Keywords</span></span>](statement-keywords.md)
- [<span data-ttu-id="41f61-128">Interlocked-Vorgänge</span><span class="sxs-lookup"><span data-stu-id="41f61-128">Interlocked operations</span></span>](../../../standard/threading/interlocked-operations.md)
- [<span data-ttu-id="41f61-129">Übersicht über Synchronisierungsprimitiven</span><span class="sxs-lookup"><span data-stu-id="41f61-129">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)