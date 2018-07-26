---
title: lock-Anweisung (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 2ce870e8caa67d780ce603a6f1dbcc7cd303b842
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37960951"
---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="4a1d9-102">lock-Anweisung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4a1d9-102">lock Statement (C# Reference)</span></span>
<span data-ttu-id="4a1d9-103">Das Schlüsselwort `lock` kennzeichnet einen Anweisungsblock als kritischen Abschnitt, indem es die sich gegenseitig ausschließende Sperre für ein gegebenes Objekt abruft, eine Anweisung ausführt und anschließend die Sperre aufhebt.</span><span class="sxs-lookup"><span data-stu-id="4a1d9-103">The `lock` keyword marks a statement block as a critical section by obtaining the mutual-exclusion lock for a given object, executing a statement, and then releasing the lock.</span></span> <span data-ttu-id="4a1d9-104">Das folgende Beispiel enthält eine `lock`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4a1d9-104">The following example includes a `lock` statement.</span></span>  
  
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
  
 <span data-ttu-id="4a1d9-105">Weitere Informationen finden Sie unter [Threadsynchronisierung](../../programming-guide/concepts/threading/thread-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="4a1d9-105">For more information, see [Thread Synchronization](../../programming-guide/concepts/threading/thread-synchronization.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a1d9-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4a1d9-106">Remarks</span></span>  
 <span data-ttu-id="4a1d9-107">Das Schlüsselwort `lock` stellt sicher, dass ein Thread keinen kritischen Abschnitt eines Codes betritt, während ein anderer Thread in diesem Abschnitt ist.</span><span class="sxs-lookup"><span data-stu-id="4a1d9-107">The `lock` keyword ensures that one thread does not enter a critical section of code while another thread is in the critical section.</span></span> <span data-ttu-id="4a1d9-108">Wenn ein anderer Thread versucht, auf einen gesperrten Code zuzugreifen, wartet er, sperrt, bis das Objekt freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4a1d9-108">If another thread tries to enter a locked code, it will wait, block, until the object is released.</span></span>  
  
 <span data-ttu-id="4a1d9-109">Der Abschnitt [Threading](../../programming-guide/concepts/threading/index.md) wird das Threading behandeln.</span><span class="sxs-lookup"><span data-stu-id="4a1d9-109">The section [Threading](../../programming-guide/concepts/threading/index.md) discusses threading.</span></span>  
  
 <span data-ttu-id="4a1d9-110">Das `lock`-Schlüsselwort ruft am Anfang des Blocks <xref:System.Threading.Monitor.Enter%2A> und am Ende des Blocks <xref:System.Threading.Monitor.Exit%2A> auf.</span><span class="sxs-lookup"><span data-stu-id="4a1d9-110">The `lock` keyword calls <xref:System.Threading.Monitor.Enter%2A> at the start of the block and <xref:System.Threading.Monitor.Exit%2A> at the end of the block.</span></span> <span data-ttu-id="4a1d9-111">Ein <xref:System.Threading.ThreadInterruptedException> wird ausgelöst, wenn <xref:System.Threading.Thread.Interrupt%2A> einen Thread unterbricht, der darauf wartet eine `lock`-Anweisung einzugeben.</span><span class="sxs-lookup"><span data-stu-id="4a1d9-111">A <xref:System.Threading.ThreadInterruptedException> is thrown if <xref:System.Threading.Thread.Interrupt%2A> interrupts a thread that is waiting to enter a `lock` statement.</span></span>  
  
 <span data-ttu-id="4a1d9-112">Vermeiden Sie generell das Sperren eines `public`-Typs oder von Instanzen außerhalb der Kontrolle Ihres Codes.</span><span class="sxs-lookup"><span data-stu-id="4a1d9-112">In general, avoid locking on a `public` type, or instances beyond your code's control.</span></span> <span data-ttu-id="4a1d9-113">Die gemeinsamen Konstrukte `lock (this)`, `lock (typeof (MyType))` und `lock ("myLock")` verstoßen gegen diese Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="4a1d9-113">The common constructs `lock (this)`, `lock (typeof (MyType))`, and `lock ("myLock")` violate this guideline:</span></span>  
  
-   <span data-ttu-id="4a1d9-114">`lock (this)` ist ein Problem, wenn auf die Instanz öffentlich zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="4a1d9-114">`lock (this)` is a problem if the instance can be accessed publicly.</span></span>  
  
-   <span data-ttu-id="4a1d9-115">`lock (typeof (MyType))` ist problematisch, wenn auf `MyType` öffentlich zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="4a1d9-115">`lock (typeof (MyType))` is a problem if `MyType` is publicly accessible.</span></span>  
  
-   <span data-ttu-id="4a1d9-116">`lock("myLock")` ist problematisch, weil jeder andere Code in diesem Prozess, der die selbe Zeichenfolge verwendet, die gleiche Sperre teilt.</span><span class="sxs-lookup"><span data-stu-id="4a1d9-116">`lock("myLock")` is a problem because any other code in the process using the same string, will share the same lock.</span></span>  
  
 <span data-ttu-id="4a1d9-117">Eine bewährte Methode ist es, ein `private`-Objekt zum Sperren, oder eine `private static`-Objektvariable zu definieren, die Daten schützt, die in allen Instanzen häufig vorkommen.</span><span class="sxs-lookup"><span data-stu-id="4a1d9-117">Best practice is to define a `private` object to lock on, or a `private static` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="4a1d9-118">Sie können das Schlüsselwort [await](../../../csharp/language-reference/keywords/await.md) nicht im Text einer `lock`-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a1d9-118">You can't use the [await](../../../csharp/language-reference/keywords/await.md) keyword in the body of a `lock` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a1d9-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4a1d9-119">Example</span></span>  
 <span data-ttu-id="4a1d9-120">Im folgenden Beispiel wird eine einfache Verwendung von Threads ohne das Sperren in C# gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4a1d9-120">The following sample shows a simple use of threads without locking in C#.</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="4a1d9-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4a1d9-121">Example</span></span>  
 <span data-ttu-id="4a1d9-122">Im folgenden Beispiel werden Threads und `lock` verwendet.</span><span class="sxs-lookup"><span data-stu-id="4a1d9-122">The following sample uses threads and `lock`.</span></span> <span data-ttu-id="4a1d9-123">Solange die `lock`-Anweisung vorhanden ist, ist der Anweisungsblock ein kritischer Abschnitt, und `balance` wird nie eine negative Zahl werden.</span><span class="sxs-lookup"><span data-stu-id="4a1d9-123">As long as the `lock` statement is present, the statement block is a critical section and `balance` will never become a negative number.</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="4a1d9-124">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="4a1d9-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4a1d9-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a1d9-125">See Also</span></span>  
 <xref:System.Reflection.MethodImplAttributes>  
 <xref:System.Threading.Mutex>  
 [<span data-ttu-id="4a1d9-126">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="4a1d9-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4a1d9-127">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4a1d9-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4a1d9-128">Threading</span><span class="sxs-lookup"><span data-stu-id="4a1d9-128">Threading</span></span>](../../programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="4a1d9-129">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="4a1d9-129">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="4a1d9-130">Anweisungsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="4a1d9-130">Statement Keywords</span></span>](../../../csharp/language-reference/keywords/statement-keywords.md)  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="4a1d9-131">Interlocked-Vorgänge</span><span class="sxs-lookup"><span data-stu-id="4a1d9-131">Interlocked Operations</span></span>](../../../standard/threading/interlocked-operations.md)  
 [<span data-ttu-id="4a1d9-132">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="4a1d9-132">AutoResetEvent</span></span>](../../../standard/threading/autoresetevent.md)  
 [<span data-ttu-id="4a1d9-133">Threadsynchronisierung</span><span class="sxs-lookup"><span data-stu-id="4a1d9-133">Thread Synchronization</span></span>](../../programming-guide/concepts/threading/thread-synchronization.md)
