---
title: Muster für die asynchrone Programmierung
description: Erfahren Sie mehr über das aufgabenbasierte asynchrone Muster (TAP, Task-based Asynchronous Pattern), das ereignisbasierte asynchrone Muster (EAP, Event-based Asynchronous Pattern) und das asynchrone Programmiermodell (APM, Asynchronous Programming Model) in .NET.
ms.date: 10/16/2018
helpviewer_keywords:
- asynchronous design patterns, .NET
- .NET, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
ms.openlocfilehash: bc0e37c060ab6375f943b4b50053e3046c05a556
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830336"
---
# <a name="asynchronous-programming-patterns"></a><span data-ttu-id="1a388-103">Muster für die asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="1a388-103">Asynchronous programming patterns</span></span>

<span data-ttu-id="1a388-104">In .NET werden drei Muster für das Ausführen asynchroner Vorgänge bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="1a388-104">.NET provides three patterns for performing asynchronous operations:</span></span>  

- <span data-ttu-id="1a388-105">Das **Taskbasierte asynchrone Muster (Task-based Asynchronous Pattern, TAP)** verwendet eine einzelne Methode, um die Initiierung und den Abschluss eines asynchronen Vorgangs darzustellen.</span><span class="sxs-lookup"><span data-stu-id="1a388-105">**Task-based Asynchronous Pattern (TAP)**, which uses a single method to represent the initiation and completion of an asynchronous operation.</span></span> <span data-ttu-id="1a388-106">TAP wurde in .NET Framework 4 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1a388-106">TAP was introduced in .NET Framework 4.</span></span> <span data-ttu-id="1a388-107">**TAP ist das empfohlene Muster für die asynchrone Programmierung in .NET.**</span><span class="sxs-lookup"><span data-stu-id="1a388-107">**It's the recommended approach to asynchronous programming in .NET.**</span></span> <span data-ttu-id="1a388-108">Die Schlüsselwörter [async](../../csharp/language-reference/keywords/async.md) und [await](../../csharp/language-reference/operators/await.md) in C# und die Operatoren [Async](../../visual-basic/language-reference/modifiers/async.md) und [Await](../../visual-basic/language-reference/operators/await-operator.md) in Visual Basic fügen Sprachunterstützung für TAP hinzu.</span><span class="sxs-lookup"><span data-stu-id="1a388-108">The [async](../../csharp/language-reference/keywords/async.md) and [await](../../csharp/language-reference/operators/await.md) keywords in C# and the [Async](../../visual-basic/language-reference/modifiers/async.md) and [Await](../../visual-basic/language-reference/operators/await-operator.md) operators in Visual Basic add language support for TAP.</span></span> <span data-ttu-id="1a388-109">Weitere Informationen finden Sie unter [Task-based Asynchronous Pattern (TAP) (Aufgabenbasiertes asynchrones Muster (TAP))](task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="1a388-109">For more information, see [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>  

- <span data-ttu-id="1a388-110">Das **Ereignisbasierte asynchrones Muster (Event-based Asynchronous Pattern, EAP)** , das das ereignisbasierte Legacymodell für die Bereitstellung des asynchronen Verhaltens ist.</span><span class="sxs-lookup"><span data-stu-id="1a388-110">**Event-based Asynchronous Pattern (EAP)**, which is the event-based legacy model for providing asynchronous behavior.</span></span> <span data-ttu-id="1a388-111">Dieses Muster erfordert eine Methode, die das `Async`-Suffix und mindestens ein Ereignis, einen Ereignishandler-Delegattypen und aus `EventArg` abgeleitete Typen hat.</span><span class="sxs-lookup"><span data-stu-id="1a388-111">It requires a method that has the `Async` suffix and one or more events, event handler delegate types, and `EventArg`-derived types.</span></span> <span data-ttu-id="1a388-112">EAP wurde in .NET Framework 2.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1a388-112">EAP was introduced in .NET Framework 2.0.</span></span> <span data-ttu-id="1a388-113">EAP ist für neue Entwicklungen nicht mehr empfehlenswert.</span><span class="sxs-lookup"><span data-stu-id="1a388-113">It's no longer recommended for new development.</span></span> <span data-ttu-id="1a388-114">Weitere Informationen finden Sie unter [Ereignisbasiertes asynchrones Muster (EAP)](event-based-asynchronous-pattern-eap.md).</span><span class="sxs-lookup"><span data-stu-id="1a388-114">For more information, see [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md).</span></span>  

- <span data-ttu-id="1a388-115">Das Muster für das **Asynchrone Programmiermodell (APM)** (wird auch als <xref:System.IAsyncResult>-Muster bezeichnet), das das Legacymodell ist, in dem die <xref:System.IAsyncResult>-Schnittstelle verwendet wird, um asynchrones Verhalten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1a388-115">**Asynchronous Programming Model (APM)** pattern (also called the <xref:System.IAsyncResult> pattern), which is the legacy model that uses the <xref:System.IAsyncResult> interface to provide asynchronous behavior.</span></span> <span data-ttu-id="1a388-116">In diesem Muster sind für synchrone Vorgänge eine `Begin`- und eine `End`-Methode erforderlich (z. B. `BeginWrite` und `EndWrite`), um einen asynchronen Schreibvorgang zu implementieren).</span><span class="sxs-lookup"><span data-stu-id="1a388-116">In this pattern, synchronous operations require `Begin` and `End` methods (for example, `BeginWrite` and `EndWrite` to implement an asynchronous write operation).</span></span> <span data-ttu-id="1a388-117">Dieses Muster ist für neue Entwicklungen nicht mehr empfehlenswert.</span><span class="sxs-lookup"><span data-stu-id="1a388-117">This pattern is no longer recommended for new development.</span></span> <span data-ttu-id="1a388-118">Weitere Informationen finden Sie unter [Asynchronous Programming Model (APM) (Asynchrones Programmiermodell (APM))](asynchronous-programming-model-apm.md).</span><span class="sxs-lookup"><span data-stu-id="1a388-118">For more information, see [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md).</span></span>  
  
## <a name="comparison-of-patterns"></a><span data-ttu-id="1a388-119">Vergleich der Muster</span><span class="sxs-lookup"><span data-stu-id="1a388-119">Comparison of patterns</span></span>

<span data-ttu-id="1a388-120">Für einen schnellen Vergleich dazu, wie die drei Muster asynchrone Vorgänge modellieren, sollten Sie eine `Read`-Methode verwenden, die eine angegebene Datenmenge in einen bereitgestellten Puffer beginnend an einem angegebenen Offset liest:</span><span class="sxs-lookup"><span data-stu-id="1a388-120">For a quick comparison of how the three patterns model asynchronous operations, consider a `Read` method that reads a specified amount of data into a provided buffer starting at a specified offset:</span></span>  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  

<span data-ttu-id="1a388-121">Das TAP-Gegenstück zu dieser Methode würde die folgende einzelne `ReadAsync` Methode verfügbar machen:</span><span class="sxs-lookup"><span data-stu-id="1a388-121">The TAP counterpart of this method would expose the following single `ReadAsync` method:</span></span>  
  
```csharp
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```

<span data-ttu-id="1a388-122">Das EAP-Gegenstück würde den folgenden Satz von Typen und Membern verfügbar machen:</span><span class="sxs-lookup"><span data-stu-id="1a388-122">The EAP counterpart would expose the following set of types and members:</span></span>  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
<span data-ttu-id="1a388-123">Das APM-Gegenstück würde die Methoden `BeginRead` und `EndRead` verfügbar machen:</span><span class="sxs-lookup"><span data-stu-id="1a388-123">The APM counterpart would expose the `BeginRead` and `EndRead` methods:</span></span>  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  

## <a name="see-also"></a><span data-ttu-id="1a388-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a388-124">See also</span></span>

- [<span data-ttu-id="1a388-125">Async ausführlich</span><span class="sxs-lookup"><span data-stu-id="1a388-125">Async in depth</span></span>](../async-in-depth.md)
- [<span data-ttu-id="1a388-126">Asynchrone Programmierung in C#</span><span class="sxs-lookup"><span data-stu-id="1a388-126">Asynchronous programming in C#</span></span>](../../csharp/async.md)
- [<span data-ttu-id="1a388-127">Asynchrone Programmierung in F#</span><span class="sxs-lookup"><span data-stu-id="1a388-127">Async Programming in F#</span></span>](../../fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)
- [<span data-ttu-id="1a388-128">Asynchrone Programmierung mit „Async“ und „Await“ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a388-128">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/async/index.md)
