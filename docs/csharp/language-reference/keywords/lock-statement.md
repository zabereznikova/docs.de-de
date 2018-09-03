---
title: lock-Anweisung (C#-Referenz)
description: 'Das lock-Schlüsselwort wird in Threading verwendet. '
ms.date: 07/20/2015
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 6ed46837482642dfd7e1a96cd120fc18023c5e9f
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42931192"
---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="2b354-103">lock-Anweisung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2b354-103">lock statement (C# Reference)</span></span>

<span data-ttu-id="2b354-104">Das Schlüsselwort `lock` kennzeichnet einen Anweisungsblock als kritischen Abschnitt, indem es die sich gegenseitig ausschließende Sperre für ein gegebenes Objekt abruft, eine Anweisung ausführt und anschließend die Sperre aufhebt.</span><span class="sxs-lookup"><span data-stu-id="2b354-104">The `lock` keyword marks a statement block as a critical section by obtaining the mutual-exclusion lock for a given object, executing a statement, and then releasing the lock.</span></span> <span data-ttu-id="2b354-105">Das folgende Beispiel enthält eine `lock`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2b354-105">The following example includes a `lock` statement.</span></span>

```csharp
class Account
{
    decimal balance;
    private Object thisLock = new Object();

    public void Withdraw(decimal amount)
    {
        lock (thisLock)
        {
            if (amount > balance)
            {
                throw new Exception("Insufficient funds");
            }
            balance -= amount;
        }
    }
}
```

<span data-ttu-id="2b354-106">Weitere Informationen finden Sie unter [Threadsynchronisierung](../../programming-guide/concepts/threading/thread-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="2b354-106">For more information, see [Thread Synchronization](../../programming-guide/concepts/threading/thread-synchronization.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="2b354-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b354-107">Remarks</span></span>

<span data-ttu-id="2b354-108">Das Schlüsselwort `lock` stellt sicher, dass ein Thread keinen kritischen Abschnitt eines Codes betritt, während ein anderer Thread in diesem Abschnitt ist.</span><span class="sxs-lookup"><span data-stu-id="2b354-108">The `lock` keyword ensures that one thread does not enter a critical section of code while another thread is in the critical section.</span></span> <span data-ttu-id="2b354-109">Wenn ein anderer Thread versucht, auf einen gesperrten Code zuzugreifen, wartet er, sperrt, bis das Objekt freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2b354-109">If another thread tries to enter a locked code, it will wait, block, until the object is released.</span></span>

<span data-ttu-id="2b354-110">Der Abschnitt [Threading](../../programming-guide/concepts/threading/index.md) wird das Threading behandeln.</span><span class="sxs-lookup"><span data-stu-id="2b354-110">The section [Threading](../../programming-guide/concepts/threading/index.md) discusses threading.</span></span>

<span data-ttu-id="2b354-111">Das `lock`-Schlüsselwort ruft am Anfang des Blocks <xref:System.Threading.Monitor.Enter%2A> und am Ende des Blocks <xref:System.Threading.Monitor.Exit%2A> auf.</span><span class="sxs-lookup"><span data-stu-id="2b354-111">The `lock` keyword calls <xref:System.Threading.Monitor.Enter%2A> at the start of the block and <xref:System.Threading.Monitor.Exit%2A> at the end of the block.</span></span> <span data-ttu-id="2b354-112">Ein <xref:System.Threading.ThreadInterruptedException> wird ausgelöst, wenn <xref:System.Threading.Thread.Interrupt%2A> einen Thread unterbricht, der darauf wartet eine `lock`-Anweisung einzugeben.</span><span class="sxs-lookup"><span data-stu-id="2b354-112">A <xref:System.Threading.ThreadInterruptedException> is thrown if <xref:System.Threading.Thread.Interrupt%2A> interrupts a thread that is waiting to enter a `lock` statement.</span></span>

<span data-ttu-id="2b354-113">Vermeiden Sie generell das Sperren eines `public`-Typs oder von Instanzen außerhalb der Kontrolle Ihres Codes.</span><span class="sxs-lookup"><span data-stu-id="2b354-113">In general, avoid locking on a `public` type, or instances beyond your code's control.</span></span> <span data-ttu-id="2b354-114">Die gemeinsamen Konstrukte `lock (this)`, `lock (typeof (MyType))` und `lock ("myLock")` verstoßen gegen diese Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="2b354-114">The common constructs `lock (this)`, `lock (typeof (MyType))`, and `lock ("myLock")` violate this guideline:</span></span>

- <span data-ttu-id="2b354-115">`lock (this)` ist ein Problem, wenn auf die Instanz öffentlich zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="2b354-115">`lock (this)` is a problem if the instance can be accessed publicly.</span></span>

- <span data-ttu-id="2b354-116">`lock (typeof (MyType))` ist problematisch, wenn auf `MyType` öffentlich zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="2b354-116">`lock (typeof (MyType))` is a problem if `MyType` is publicly accessible.</span></span>

- <span data-ttu-id="2b354-117">`lock("myLock")` ist problematisch, weil jeder andere Code in diesem Prozess, der die selbe Zeichenfolge verwendet, die gleiche Sperre teilt.</span><span class="sxs-lookup"><span data-stu-id="2b354-117">`lock("myLock")` is a problem because any other code in the process using the same string, will share the same lock.</span></span>

<span data-ttu-id="2b354-118">Eine bewährte Methode ist es, ein `private`-Objekt zum Sperren, oder eine `private static`-Objektvariable zu definieren, die Daten schützt, die in allen Instanzen häufig vorkommen.</span><span class="sxs-lookup"><span data-stu-id="2b354-118">Best practice is to define a `private` object to lock on, or a `private static` object variable to protect data common to all instances.</span></span>

<span data-ttu-id="2b354-119">Sie können das Schlüsselwort [await](await.md) nicht im Text einer `lock`-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="2b354-119">You can't use the [await](await.md) keyword in the body of a `lock` statement.</span></span>

## <a name="example---threads-without-locking"></a><span data-ttu-id="2b354-120">Beispiel: Threads ohne Sperren</span><span class="sxs-lookup"><span data-stu-id="2b354-120">Example - Threads without locking</span></span>

<span data-ttu-id="2b354-121">Im folgenden Beispiel wird eine einfache Verwendung von Threads ohne das Sperren in C# gezeigt:</span><span class="sxs-lookup"><span data-stu-id="2b354-121">The following sample shows a simple use of threads without locking in C#:</span></span>

[!code-csharp[csrefKeywordsFixedLock#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsFixedLock/CS/csrefKeywordsFixedLock.cs#5)]

## <a name="example---threads-using-locking"></a><span data-ttu-id="2b354-122">Beispiel: Threads mit Sperren</span><span class="sxs-lookup"><span data-stu-id="2b354-122">Example - Threads using locking</span></span>

<span data-ttu-id="2b354-123">Im folgenden Beispiel werden Threads und `lock` verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b354-123">The following sample uses threads and `lock`.</span></span> <span data-ttu-id="2b354-124">Solange die `lock`-Anweisung vorhanden ist, ist der Anweisungsblock ein kritischer Abschnitt, und `balance` wird nie eine negative Zahl werden:</span><span class="sxs-lookup"><span data-stu-id="2b354-124">As long as the `lock` statement is present, the statement block is a critical section and `balance` will never become a negative number:</span></span>

[!code-csharp[csrefKeywordsFixedLock#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsFixedLock/CS/csrefKeywordsFixedLock.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="2b354-125">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="2b354-125">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="2b354-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b354-126">See also</span></span>

- <xref:System.Reflection.MethodImplAttributes>
- <xref:System.Threading.Mutex>
- <xref:System.Threading.Monitor>
- [<span data-ttu-id="2b354-127">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2b354-127">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="2b354-128">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2b354-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2b354-129">Threading</span><span class="sxs-lookup"><span data-stu-id="2b354-129">Threading</span></span>](../../programming-guide/concepts/threading/index.md)
- [<span data-ttu-id="2b354-130">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2b354-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="2b354-131">Anweisungsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2b354-131">Statement Keywords</span></span>](statement-keywords.md)
- [<span data-ttu-id="2b354-132">Interlocked-Vorgänge</span><span class="sxs-lookup"><span data-stu-id="2b354-132">Interlocked Operations</span></span>](../../../standard/threading/interlocked-operations.md)
- [<span data-ttu-id="2b354-133">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="2b354-133">AutoResetEvent</span></span>](../../../standard/threading/autoresetevent.md)
- [<span data-ttu-id="2b354-134">Threadsynchronisierung</span><span class="sxs-lookup"><span data-stu-id="2b354-134">Thread Synchronization</span></span>](../../programming-guide/concepts/threading/thread-synchronization.md)