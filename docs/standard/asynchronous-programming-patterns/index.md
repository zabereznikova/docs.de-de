---
title: "Muster für die asynchrone Programmierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- asynchronous design patterns, .NET Framework
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a527824ba11928d59bc700f253c5a4d77056abf0
ms.contentlocale: de-de
ms.lasthandoff: 09/05/2017

---

# <a name="asynchronous-programming-patterns"></a><span data-ttu-id="f6f95-102">Muster für die asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="f6f95-102">Asynchronous Programming Patterns</span></span>

<span data-ttu-id="f6f95-103">Das.NET Framework bietet drei Muster für das Durchführen asynchroner Vorgänge:</span><span class="sxs-lookup"><span data-stu-id="f6f95-103">The .NET Framework provides three patterns for performing asynchronous operations:</span></span>  
  
- <span data-ttu-id="f6f95-104">APM-Muster (Asynchronous Programming Model, auch <xref:System.IAsyncResult>-Muster genannt), in dem asynchrone Vorgänge `Begin`- und `End`-Methoden erfordern (z. B. `BeginWrite` und `EndWrite` für asynchrone Schreibvorgänge).</span><span class="sxs-lookup"><span data-stu-id="f6f95-104">Asynchronous Programming Model (APM) pattern (also called the <xref:System.IAsyncResult> pattern), where asynchronous operations require `Begin` and `End` methods (for example, `BeginWrite` and `EndWrite` for asynchronous write operations).</span></span> <span data-ttu-id="f6f95-105">Dieses Muster ist für neue Entwicklungen nicht mehr empfehlenswert.</span><span class="sxs-lookup"><span data-stu-id="f6f95-105">This pattern is no longer recommended for new development.</span></span> <span data-ttu-id="f6f95-106">Weitere Informationen finden Sie unter [Asynchronous Programming Model (APM) (Asynchrones Programmiermodell (APM))](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).</span><span class="sxs-lookup"><span data-stu-id="f6f95-106">For more information, see [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).</span></span>  
  
- <span data-ttu-id="f6f95-107">Das ereignisbasierte asynchrone Muster (EAP), das eine Methode mit einem `Async`-Suffix und ein oder mehrere Ereignisse, Ereignishandler-Delegattypen und von `EventArg` abgeleitete Typen erfordert.</span><span class="sxs-lookup"><span data-stu-id="f6f95-107">Event-based Asynchronous Pattern (EAP), which requires a method that has the `Async` suffix, and also requires one or more events, event handler delegate types, and `EventArg`-derived types.</span></span> <span data-ttu-id="f6f95-108">EAP wurde in .NET Framework 2.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f6f95-108">EAP was introduced in the .NET Framework 2.0.</span></span> <span data-ttu-id="f6f95-109">Es für neue Entwicklungen nicht mehr empfehlenswert.</span><span class="sxs-lookup"><span data-stu-id="f6f95-109">It is no longer recommended for new development.</span></span> <span data-ttu-id="f6f95-110">Weitere Informationen finden Sie unter [Ereignisbasiertes asynchrones Muster (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span><span class="sxs-lookup"><span data-stu-id="f6f95-110">For more information, see [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span></span>  
  
- <span data-ttu-id="f6f95-111">Aufgabenbasierte asynchrone Muster (Task-based Asynchronous Pattern, TAP) verwendet eine einzelne Methode, um die Initiierung und den Abschluss eines asynchronen Vorgangs darzustellen.</span><span class="sxs-lookup"><span data-stu-id="f6f95-111">Task-based Asynchronous Pattern (TAP), which uses a single method to represent the initiation and completion of an asynchronous operation.</span></span> <span data-ttu-id="f6f95-112">TAP wurde in .NET Framework 4 eingeführt und ist die empfohlene Vorgehensweise für die asynchrone Programmierung im .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f6f95-112">TAP was introduced in the .NET Framework 4 and is the recommended approach to asynchronous programming in the .NET Framework.</span></span> <span data-ttu-id="f6f95-113">Die Schlüsselwörter [async](~/docs/csharp/language-reference/keywords/async.md) und [await](~/docs/csharp/language-reference/keywords/await.md) in C# und die Operatoren [Async](~/docs/visual-basic/language-reference/modifiers/async.md) und [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) in Visual Basic Language fügen Sprachunterstützung für TAP hinzu.</span><span class="sxs-lookup"><span data-stu-id="f6f95-113">The [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) keywords in C# and the [Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) operators in Visual Basic Language add language support for TAP.</span></span> <span data-ttu-id="f6f95-114">Weitere Informationen finden Sie unter [Task-based Asynchronous Pattern (TAP) (Aufgabenbasiertes asynchrones Muster (TAP))](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="f6f95-114">For more information, see [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span>  
  
## <a name="comparing-patterns"></a><span data-ttu-id="f6f95-115">Vergleichen von Mustern</span><span class="sxs-lookup"><span data-stu-id="f6f95-115">Comparing Patterns</span></span>  

<span data-ttu-id="f6f95-116">Für einen schnellen Vergleich dazu, wie die drei Muster asynchrone Vorgänge modellieren, sollten Sie eine `Read`-Methode verwenden, die eine angegebene Datenmenge in einen bereitgestellten Puffer beginnend an einem angegebenen Offset liest:</span><span class="sxs-lookup"><span data-stu-id="f6f95-116">For a quick comparison of how the three patterns model asynchronous operations, consider a `Read` method that reads a specified amount of data into a provided buffer starting at a specified offset:</span></span>  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  
  
<span data-ttu-id="f6f95-117">Das APM-Gegenstück dieser Methode würde die Methoden `BeginRead` und `EndRead` verfügbar machen:</span><span class="sxs-lookup"><span data-stu-id="f6f95-117">The APM counterpart of this method would expose the `BeginRead` and `EndRead` methods:</span></span>  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  
  
<span data-ttu-id="f6f95-118">Das EAP-Gegenstück würde den folgenden Satz von Typen und Membern verfügbar machen:</span><span class="sxs-lookup"><span data-stu-id="f6f95-118">The EAP counterpart would expose the following set of types and members:</span></span>  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
<span data-ttu-id="f6f95-119">Das TAP-Gegenstück würde die folgende einzelne `ReadAsync`-Methode verfügbar machen:</span><span class="sxs-lookup"><span data-stu-id="f6f95-119">The TAP counterpart would expose the following single `ReadAsync` method:</span></span>  
  
```csharp  
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```  
  
<span data-ttu-id="f6f95-120">Eine umfassende Erörterung von TAP, APM und EAP finden Sie unter den Links im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="f6f95-120">For a comprehensive discussion of TAP, APM, and EAP, see the links provided in the next section.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="f6f95-121">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f6f95-121">Related topics</span></span>

| <span data-ttu-id="f6f95-122">Titel</span><span class="sxs-lookup"><span data-stu-id="f6f95-122">Title</span></span> | <span data-ttu-id="f6f95-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6f95-123">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="f6f95-124">Asynchronous Programming Model (APM) (Asynchrones Programmiermodell (APM))</span><span class="sxs-lookup"><span data-stu-id="f6f95-124">Asynchronous Programming Model (APM)</span></span>](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) | <span data-ttu-id="f6f95-125">Beschreibt das Legacymodell, das die <xref:System.IAsyncResult>-Schnittstelle verwendet, um asynchrones Verhalten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f6f95-125">Describes the legacy model that uses the <xref:System.IAsyncResult> interface to provide asynchronous behavior.</span></span> <span data-ttu-id="f6f95-126">Dieses Modell ist für neue Entwicklungen nicht mehr empfehlenswert.</span><span class="sxs-lookup"><span data-stu-id="f6f95-126">This model is no longer recommended for new development.</span></span> |
| [<span data-ttu-id="f6f95-127">Ereignisbasiertes asynchrones Muster (EAP)</span><span class="sxs-lookup"><span data-stu-id="f6f95-127">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) | <span data-ttu-id="f6f95-128">Beschreibt das ereignisbasierte Legacymodell für die Bereitstellung des asynchronen Verhaltens.</span><span class="sxs-lookup"><span data-stu-id="f6f95-128">Describes the event-based legacy model for providing asynchronous behavior.</span></span> <span data-ttu-id="f6f95-129">Dieses Modell ist für neue Entwicklungen nicht mehr empfehlenswert.</span><span class="sxs-lookup"><span data-stu-id="f6f95-129">This model is no longer recommended for new development.</span></span> |
| <span data-ttu-id="f6f95-130">[Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Aufgabenbasiertes asynchrones Muster)</span><span class="sxs-lookup"><span data-stu-id="f6f95-130">[Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)</span></span> | <span data-ttu-id="f6f95-131">Beschreibt das neue asynchrone Muster basierend auf dem <xref:System.Threading.Tasks>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="f6f95-131">Describes the new asynchronous pattern based on the <xref:System.Threading.Tasks> namespace.</span></span> <span data-ttu-id="f6f95-132">Dieses Modell ist der empfohlene Ansatz für die asynchrone Programmierung in .NET Framework 4 und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="f6f95-132">This model is the recommended approach to asynchronous programming in the .NET Framework 4 and later versions.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f6f95-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6f95-133">See also</span></span>

<span data-ttu-id="f6f95-134">[Asynchrone Programmierung in C#](~/docs/csharp/async.md) </span><span class="sxs-lookup"><span data-stu-id="f6f95-134">[Asynchronous programming in C#](~/docs/csharp/async.md) </span></span>  
<span data-ttu-id="f6f95-135">[Asynchrone Programmierung in F#](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md) </span><span class="sxs-lookup"><span data-stu-id="f6f95-135">[Async Programming in F#](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md) </span></span>  
[<span data-ttu-id="f6f95-136">Asynchrone Programmierung mit „Async“ und „Await“ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6f95-136">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/concepts/async/index.md)

