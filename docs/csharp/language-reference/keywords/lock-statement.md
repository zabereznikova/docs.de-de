---
title: lock-Anweisung (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- lock_CSharpKeyword
- lock
dev_langs:
- CSharp
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
caps.latest.revision: 43
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
ms.openlocfilehash: 00dcbb9feec11587265bf61667d91c2c1598065b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="d7d56-102">lock-Anweisung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d7d56-102">lock Statement (C# Reference)</span></span>
<span data-ttu-id="d7d56-103">Das Schlüsselwort `lock` kennzeichnet einen Anweisungsblock als kritischen Abschnitt, indem es die sich gegenseitig ausschließende Sperre für ein gegebenes Objekt abruft, eine Anweisung ausführt und anschließend die Sperre aufhebt.</span><span class="sxs-lookup"><span data-stu-id="d7d56-103">The `lock` keyword marks a statement block as a critical section by obtaining the mutual-exclusion lock for a given object, executing a statement, and then releasing the lock.</span></span> <span data-ttu-id="d7d56-104">Das folgende Beispiel enthält eine `lock`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d7d56-104">The following example includes a `lock` statement.</span></span>  
  
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
  
 <span data-ttu-id="d7d56-105">Weitere Informationen finden Sie unter [Threadsynchronisierung](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4).</span><span class="sxs-lookup"><span data-stu-id="d7d56-105">For more information, see [Thread Synchronization](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7d56-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7d56-106">Remarks</span></span>  
 <span data-ttu-id="d7d56-107">Das Schlüsselwort `lock` stellt sicher, dass ein Thread keinen kritischen Abschnitt eines Codes betritt, während ein anderer Thread in diesem Abschnitt ist.</span><span class="sxs-lookup"><span data-stu-id="d7d56-107">The `lock` keyword ensures that one thread does not enter a critical section of code while another thread is in the critical section.</span></span> <span data-ttu-id="d7d56-108">Wenn ein anderer Thread versucht, auf einen gesperrten Code zuzugreifen, wartet er, sperrt, bis das Objekt freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d7d56-108">If another thread tries to enter a locked code, it will wait, block, until the object is released.</span></span>  
  
 <span data-ttu-id="d7d56-109">Der Abschnitt [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c) wird das Threading behandeln.</span><span class="sxs-lookup"><span data-stu-id="d7d56-109">The section [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c) discusses threading.</span></span>  
  
 <span data-ttu-id="d7d56-110">Das `lock`-Schlüsselwort ruft am Anfang des Blocks <xref:System.Threading.Monitor.Enter%2A> und am Ende des Blocks <xref:System.Threading.Monitor.Exit%2A> auf.</span><span class="sxs-lookup"><span data-stu-id="d7d56-110">The `lock` keyword calls <xref:System.Threading.Monitor.Enter%2A> at the start of the block and <xref:System.Threading.Monitor.Exit%2A> at the end of the block.</span></span> <span data-ttu-id="d7d56-111">Ein <xref:System.Threading.ThreadInterruptedException> wird ausgelöst, wenn <xref:System.Threading.Thread.Interrupt%2A> einen Thread unterbricht, der darauf wartet eine `lock`-Anweisung einzugeben.</span><span class="sxs-lookup"><span data-stu-id="d7d56-111">A <xref:System.Threading.ThreadInterruptedException> is thrown if <xref:System.Threading.Thread.Interrupt%2A> interrupts a thread that is waiting to enter a `lock` statement.</span></span>  
  
 <span data-ttu-id="d7d56-112">Vermeiden Sie generell das Sperren eines `public`-Typs oder von Instanzen außerhalb der Kontrolle Ihres Codes.</span><span class="sxs-lookup"><span data-stu-id="d7d56-112">In general, avoid locking on a `public` type, or instances beyond your code's control.</span></span> <span data-ttu-id="d7d56-113">Die gemeinsamen Konstrukte `lock (this)`, `lock (typeof (MyType))` und `lock ("myLock")` verstoßen gegen diese Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="d7d56-113">The common constructs `lock (this)`, `lock (typeof (MyType))`, and `lock ("myLock")` violate this guideline:</span></span>  
  
-   <span data-ttu-id="d7d56-114">`lock (this)` ist ein Problem, wenn auf die Instanz öffentlich zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d7d56-114">`lock (this)` is a problem if the instance can be accessed publicly.</span></span>  
  
-   <span data-ttu-id="d7d56-115">`lock (typeof (MyType))` ist problematisch, wenn auf `MyType` öffentlich zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="d7d56-115">`lock (typeof (MyType))` is a problem if `MyType` is publicly accessible.</span></span>  
  
-   <span data-ttu-id="d7d56-116">`lock("myLock")` ist problematisch, weil jeder andere Code in diesem Prozess, der die selbe Zeichenfolge verwendet, die gleiche Sperre teilt.</span><span class="sxs-lookup"><span data-stu-id="d7d56-116">`lock("myLock")` is a problem because any other code in the process using the same string, will share the same lock.</span></span>  
  
 <span data-ttu-id="d7d56-117">Eine bewährte Methode ist es, ein `private`-Objekt zum Sperren, oder eine `private static`-Objektvariable zu definieren, die Daten schützt, die in allen Instanzen häufig vorkommen.</span><span class="sxs-lookup"><span data-stu-id="d7d56-117">Best practice is to define a `private` object to lock on, or a `private static` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="d7d56-118">Sie können das Schlüsselwort [await](../../../csharp/language-reference/keywords/await.md) nicht im Text einer `lock`-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7d56-118">You can't use the [await](../../../csharp/language-reference/keywords/await.md) keyword in the body of a `lock` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7d56-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7d56-119">Example</span></span>  
 <span data-ttu-id="d7d56-120">Im folgenden Beispiel wird eine einfache Verwendung von Threads ohne das Sperren in C# gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d7d56-120">The following sample shows a simple use of threads without locking in C#.</span></span>  
  
 <span data-ttu-id="d7d56-121">[!code-cs[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d7d56-121">[!code-cs[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7d56-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7d56-122">Example</span></span>  
 <span data-ttu-id="d7d56-123">Im folgenden Beispiel werden Threads und `lock` verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7d56-123">The following sample uses threads and `lock`.</span></span> <span data-ttu-id="d7d56-124">Solange die `lock`-Anweisung vorhanden ist, ist der Anweisungsblock ein kritischer Abschnitt, und `balance` wird nie eine negative Zahl werden.</span><span class="sxs-lookup"><span data-stu-id="d7d56-124">As long as the `lock` statement is present, the statement block is a critical section and `balance` will never become a negative number.</span></span>  
  
 <span data-ttu-id="d7d56-125">[!code-cs[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d7d56-125">[!code-cs[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d7d56-126">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="d7d56-126">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d7d56-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7d56-127">See Also</span></span>  
 <span data-ttu-id="d7d56-128"><xref:System.Reflection.MethodImplAttributes></span><span class="sxs-lookup"><span data-stu-id="d7d56-128"><xref:System.Reflection.MethodImplAttributes></span></span>   
 <span data-ttu-id="d7d56-129"><xref:System.Threading.Mutex></span><span class="sxs-lookup"><span data-stu-id="d7d56-129"><xref:System.Threading.Mutex></span></span>   
 <span data-ttu-id="d7d56-130">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d7d56-130">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d7d56-131">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d7d56-131">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d7d56-132">[Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c) </span><span class="sxs-lookup"><span data-stu-id="d7d56-132">[Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c) </span></span>  
 <span data-ttu-id="d7d56-133">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="d7d56-133">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="d7d56-134">[Anweisungsschlüsselwörter](../../../csharp/language-reference/keywords/statement-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="d7d56-134">[Statement Keywords](../../../csharp/language-reference/keywords/statement-keywords.md) </span></span>  
 <span data-ttu-id="d7d56-135">@System.Threading.Monitor</span><span class="sxs-lookup"><span data-stu-id="d7d56-135">@System.Threading.Monitor</span></span>   
 <span data-ttu-id="d7d56-136">[Interlocked-Vorgänge](../../../standard/threading/interlocked-operations.md) </span><span class="sxs-lookup"><span data-stu-id="d7d56-136">[Interlocked Operations](../../../standard/threading/interlocked-operations.md) </span></span>  
 <span data-ttu-id="d7d56-137">[AutoResetEvent](../../../standard/threading/autoresetevent.md) </span><span class="sxs-lookup"><span data-stu-id="d7d56-137">[AutoResetEvent](../../../standard/threading/autoresetevent.md) </span></span>  
 [<span data-ttu-id="d7d56-138">Threadsynchronisierung</span><span class="sxs-lookup"><span data-stu-id="d7d56-138">Thread Synchronization</span></span>](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4)

