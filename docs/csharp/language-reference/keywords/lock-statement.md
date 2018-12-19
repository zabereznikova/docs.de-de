---
title: lock-Anweisung – C#-Referenz
ms.custom: seodec18
description: Verwenden Sie die lock-Anweisung von C#, um den Threadzugriff auf eine freigegebene Ressource zu synchronisieren.
ms.date: 10/01/2018
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 63fadd3c37c7533211e7bd0ac07952ca99fd6a79
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244258"
---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="3e330-103">lock-Anweisung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3e330-103">lock statement (C# Reference)</span></span>

<span data-ttu-id="3e330-104">Die `lock`-Anweisung ruft die Sperre für gegenseitigen Ausschluss für ein bestimmtes Objekt ab, führt einen Anweisungsblock aus und hebt die Sperre anschließend auf.</span><span class="sxs-lookup"><span data-stu-id="3e330-104">The `lock` statement acquires the mutual-exclusion lock for a given object, executes a statement block, and then releases the lock.</span></span> <span data-ttu-id="3e330-105">Während eine Sperre aufrechterhalten wird, kann der Thread, der die Sperre aufrechterhält, die Sperre abrufen und aufheben.</span><span class="sxs-lookup"><span data-stu-id="3e330-105">While a lock is held, the thread that holds the lock can again acquire and release the lock.</span></span> <span data-ttu-id="3e330-106">Für jeden anderen Thread wird das Abrufen der Sperre blockiert, und die Sperre wartet auf die Aufhebung.</span><span class="sxs-lookup"><span data-stu-id="3e330-106">Any other thread is blocked from acquiring the lock and waits until the lock is released.</span></span>

<span data-ttu-id="3e330-107">Die `lock`-Anweisung weist folgendes Format auf:</span><span class="sxs-lookup"><span data-stu-id="3e330-107">The `lock` statement is of the form</span></span>

```csharp
lock (x)
{
    // Your code...
}
```

<span data-ttu-id="3e330-108">`x` entspricht einem Ausdruck eines [Verweistyps](reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="3e330-108">where `x` is an expression of a [reference type](reference-types.md).</span></span> <span data-ttu-id="3e330-109">Dieser entspricht exakt Folgendem:</span><span class="sxs-lookup"><span data-stu-id="3e330-109">It's precisely equivalent to</span></span>

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

<span data-ttu-id="3e330-110">Da ein [try...finally](try-finally.md)-Block in diesem Code verwendet wird, wird die Sperre aufgehoben, wenn eine Ausnahme innerhalb des Texts einer `lock`-Anweisung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="3e330-110">Since the code uses a [try...finally](try-finally.md) block, the lock is released even if an exception is thrown within the body of a `lock` statement.</span></span>

<span data-ttu-id="3e330-111">Sie können das Schlüsselwort [await](await.md) nicht im Text einer `lock`-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="3e330-111">You can't use the [await](await.md) keyword in the body of a `lock` statement.</span></span>

## <a name="remarks"></a><span data-ttu-id="3e330-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3e330-112">Remarks</span></span>

<span data-ttu-id="3e330-113">Wenn Sie den Threadzugriff auf eine freigegebene Ressource synchronisieren, sperren Sie eine dedizierte Objektinstanz (z.B. `private readonly object balanceLock = new object();`) oder eine andere Instanz, die wahrscheinlich nicht von anderen Teilen des Codes als lock-Objekt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3e330-113">When you synchronize thread access to a shared resource, lock on a dedicated object instance (for example, `private readonly object balanceLock = new object();`) or another instance that is unlikely to be used as a lock object by unrelated parts of the code.</span></span> <span data-ttu-id="3e330-114">Vermeiden Sie, die gleiche lock-Objektinstanz für verschiedene freigegebene Ressourcen zu verwenden, da dies zu einem Deadlock oder Sperrkonflikt führen kann.</span><span class="sxs-lookup"><span data-stu-id="3e330-114">Avoid using the same lock object instance for different shared resources, as it might result in deadlock or lock contention.</span></span> <span data-ttu-id="3e330-115">Vermeiden Sie insbesondere die Verwendung der folgenden Objekte als Sperre:</span><span class="sxs-lookup"><span data-stu-id="3e330-115">In particular, avoid using the following as lock objects:</span></span>

- <span data-ttu-id="3e330-116">`this` – kann von den Aufrufern als Sperre verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3e330-116">`this`, as it might be used by the callers as a lock.</span></span>
- <span data-ttu-id="3e330-117"><xref:System.Type>-Instanzen – können vom [typeof](typeof.md)-Operator oder der Reflektion abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3e330-117"><xref:System.Type> instances, as those might be obtained by the [typeof](typeof.md) operator or reflection.</span></span>
- <span data-ttu-id="3e330-118">Zeichenfolgeninstanzen, einschließlich Zeichenfolgenliteralen – können [internalisiert](/dotnet/api/system.string.intern#remarks) sein.</span><span class="sxs-lookup"><span data-stu-id="3e330-118">string instances, including string literals, as those might be [interned](/dotnet/api/system.string.intern#remarks).</span></span>

## <a name="example"></a><span data-ttu-id="3e330-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3e330-119">Example</span></span>

<span data-ttu-id="3e330-120">Im folgenden Beispiel wird eine `Account`-Klasse definiert, die den Zugriff auf das private `balance`-Feld synchronisiert, indem eine dedizierte `balanceLock`-Instanz gesperrt wird.</span><span class="sxs-lookup"><span data-stu-id="3e330-120">The following example defines an `Account` class that synchronizes access to its private `balance` field by locking on a dedicated `balanceLock` instance.</span></span> <span data-ttu-id="3e330-121">Durch Verwendung der gleichen Instanz für die Sperre wird sichergestellt, dass das `balance`-Feld nicht von zwei Threads gleichzeitig aktualisiert werden kann, die zur gleichen Zeit versuchen, die Methoden `Debit` oder `Credit` aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="3e330-121">Using the same instance for locking ensures that the `balance` field cannot be updated simultaneously by two threads attempting to call the `Debit` or `Credit` methods simultaneously.</span></span>

[!code-csharp[lock-statement-example](~/samples/snippets/csharp/keywords/LockStatementExample.cs)]

## <a name="c-language-specification"></a><span data-ttu-id="3e330-122">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="3e330-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="3e330-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e330-123">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.SpinLock?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="3e330-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="3e330-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3e330-125">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="3e330-125">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="3e330-126">Anweisungsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="3e330-126">Statement Keywords</span></span>](statement-keywords.md)
- [<span data-ttu-id="3e330-127">Übersicht über Synchronisierungsprimitiven</span><span class="sxs-lookup"><span data-stu-id="3e330-127">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)