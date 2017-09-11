---
title: Finalizer (C#-Programmierhandbuch)
ms.date: 2017-05-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ~ [C#], in finalizers
- C# language, finalizers
- finalizers [C#]
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
caps.latest.revision: 24
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
ms.openlocfilehash: 43bb7e6488da5eda863e7ad70b25c9bf55bebb52
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="finalizers-c-programming-guide"></a><span data-ttu-id="5a8fe-102">Finalizer (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="5a8fe-102">Finalizers (C# Programming Guide)</span></span>
<span data-ttu-id="5a8fe-103">Finalizer werden zur Zerstörung von Klasseninstanzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-103">Finalizers are used to destruct instances of classes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a8fe-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5a8fe-104">Remarks</span></span>  
  
-   <span data-ttu-id="5a8fe-105">Finalizer können nicht in Strukturen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-105">Finalizers cannot be defined in structs.</span></span> <span data-ttu-id="5a8fe-106">Sie werden nur mit Klassen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-106">They are only used with classes.</span></span>  
  
-   <span data-ttu-id="5a8fe-107">Eine Klasse kann nur über einen Finalizer verfügen.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-107">A class can only have one finalizer.</span></span>  
  
-   <span data-ttu-id="5a8fe-108">Finalizer können nicht vererbt oder überladen werden.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-108">Finalizers cannot be inherited or overloaded.</span></span>  
  
-   <span data-ttu-id="5a8fe-109">Finalizer können nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-109">Finalizers cannot be called.</span></span> <span data-ttu-id="5a8fe-110">Sie werden automatisch aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-110">They are invoked automatically.</span></span>  
  
-   <span data-ttu-id="5a8fe-111">Ein Finalizer kann nicht über Modifizierer oder Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-111">A finalizer does not take modifiers or have parameters.</span></span>  
  
 <span data-ttu-id="5a8fe-112">Folgendes ist z.B. eine Deklaration eines Finalizers für die Klasse `Car`:</span><span class="sxs-lookup"><span data-stu-id="5a8fe-112">For example, the following is a declaration of a finalizer for the `Car` class.</span></span>
  
 <span data-ttu-id="5a8fe-113">[!code-cs[csProgGuideObjects#86](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5a8fe-113">[!code-cs[csProgGuideObjects#86](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_1.cs)]</span></span>  

<span data-ttu-id="5a8fe-114">Ein Finalizer kann auch als Ausdruckstextdefinition implementiert werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-114">A finalizer can also be implemented as an expression body definition, as the following example shows.</span></span>

<span data-ttu-id="5a8fe-115">[!code-cs[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="5a8fe-115">[!code-cs[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]</span></span>  
  
 <span data-ttu-id="5a8fe-116">Der Finalizer ruft <xref:System.Object.Finalize%2A> implizit auf der Basisklasse des Objekts auf.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-116">The finalizer implicitly calls <xref:System.Object.Finalize%2A> on the base class of the object.</span></span> <span data-ttu-id="5a8fe-117">Daher wird der Aufruf eines Finalizers implizit in den folgenden Code übersetzt:</span><span class="sxs-lookup"><span data-stu-id="5a8fe-117">Therefore, a call to a finalizer is implicitly translated to the following code:</span></span>  
  
```csharp  
protected override void Finalize()  
{  
    try  
    {  
        // Cleanup statements...  
    }  
    finally  
    {  
        base.Finalize();  
    }  
}  
```  
  
 <span data-ttu-id="5a8fe-118">Dies bedeutet, dass die `Finalize`-Methode für alle Instanzen in der Vererbungskette rekursiv aufgerufen wird, von der am meisten bis zu der am wenigsten abgeleiteten.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-118">This means that the `Finalize` method is called recursively for all instances in the inheritance chain, from the most-derived to the least-derived.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a8fe-119">Leere Finalizer sollten nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-119">Empty finalizers should not be used.</span></span> <span data-ttu-id="5a8fe-120">Wenn eine Klasse einen Finalizer enthält, wird ein Eintrag in der `Finalize`-Warteschlange erstellt.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-120">When a class contains a finalizer, an entry is created in the `Finalize` queue.</span></span> <span data-ttu-id="5a8fe-121">Wenn der Finalizer aufgerufen wird, wird der Garbage Collector aufgerufen, um die Warteschlange zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-121">When the finalizer is called, the garbage collector is invoked to process the queue.</span></span> <span data-ttu-id="5a8fe-122">Ein leerer Finalizer führt nur zu einem unnötigen Leistungsverlust.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-122">An empty finalizer just causes a needless loss of performance.</span></span>  
  
 <span data-ttu-id="5a8fe-123">Der Programmierer hat keine Kontrolle darüber, wann der Finalizer aufgerufen wird, da dies durch den Garbage Collector bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-123">The programmer has no control over when the finalizer is called because this is determined by the garbage collector.</span></span> <span data-ttu-id="5a8fe-124">Der Garbage Collector sucht nach Objekten, die von der Anwendung nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-124">The garbage collector checks for objects that are no longer being used by the application.</span></span> <span data-ttu-id="5a8fe-125">Wenn er ein Objekt als abschließbar angesehen wird, ruft er den Finalizer auf (sofern vorhanden) und fordert den Arbeitsspeicher, der zum Speichern des Objekts verwendet wurde, zurück.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-125">If it considers an object eligible for finalization, it calls the finalizer (if any) and reclaims the memory used to store the object.</span></span> <span data-ttu-id="5a8fe-126">Finalizer werden auch aufgerufen, wenn das Programm beendet wird.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-126">Finalizers are also called when the program exits.</span></span>  
  
 <span data-ttu-id="5a8fe-127">Es ist möglich, die Garbage Collection durch Aufrufen von <xref:System.GC.Collect%2A> zu erzwingen, aber dies sollte meistens vermieden werden, da es Leistungsprobleme hervorrufen kann.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-127">It is possible to force garbage collection by calling <xref:System.GC.Collect%2A>, but most of the time, this should be avoided because it may create performance issues.</span></span>  
  
## <a name="using-finalizers-to-release-resources"></a><span data-ttu-id="5a8fe-128">Verwenden von Finalizern zum Freigeben von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5a8fe-128">Using Finalizers to Release Resources</span></span>  
 <span data-ttu-id="5a8fe-129">Im Allgemeinen erfordert C# nicht so viel Speicherverwaltung wie benötigt wird, wenn Sie mit einer anderen Sprache entwickeln, die nicht auf eine Laufzeit mit der Garbage Collection abzielt.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-129">In general, C# does not require as much memory management as is needed when you develop with a language that does not target a runtime with garbage collection.</span></span> <span data-ttu-id="5a8fe-130">Der Garbage Collector von .NET Framework verwaltet implizit die Belegung und Freigabe von Arbeitsspeicher für Ihre Objekte.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-130">This is because the .NET Framework garbage collector implicitly manages the allocation and release of memory for your objects.</span></span> <span data-ttu-id="5a8fe-131">Wenn Ihre Anwendung nicht verwaltete Ressourcen wie z.B. Fenster, Dateien und Netzwerkverbindungen kapselt, sollten Sie Finalizer verwenden, um die Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-131">However, when your application encapsulates unmanaged resources such as windows, files, and network connections, you should use finalizers to free those resources.</span></span> <span data-ttu-id="5a8fe-132">Wenn das Objekt abgeschlossen werden kann, führt der Garbage Collector die `Finalize`-Methode des Objekts aus.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-132">When the object is eligible for finalization, the garbage collector runs the `Finalize` method of the object.</span></span>  
  
## <a name="explicit-release-of-resources"></a><span data-ttu-id="5a8fe-133">Explizite Freigabe von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5a8fe-133">Explicit Release of Resources</span></span>  
 <span data-ttu-id="5a8fe-134">Wenn Ihre Anwendung eine umfangreiche externe Ressource verwendet, wird außerdem empfohlen, dass Sie eine Möglichkeit bieten, die Ressource explizit freizugeben, bevor der Garbage Collector das Objekt freigibt.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-134">If your application is using an expensive external resource, we also recommend that you provide a way to explicitly release the resource before the garbage collector frees the object.</span></span> <span data-ttu-id="5a8fe-135">Implementieren Sie dazu eine `Dispose`-Methode aus der Schnittstelle <xref:System.IDisposable>, die die erforderliche Bereinigung für das Objekt durchführt.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-135">You do this by implementing a `Dispose` method from the <xref:System.IDisposable> interface that performs the necessary cleanup for the object.</span></span> <span data-ttu-id="5a8fe-136">Dies kann die Leistung der Anwendung erheblich verbessern.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-136">This can considerably improve the performance of the application.</span></span> <span data-ttu-id="5a8fe-137">Trotz dieser expliziten Kontrolle über Ressourcen, wird der Finalizer Ressourcen sicher bereinigen, wenn der Aufruf der `Dispose`-Methode fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-137">Even with this explicit control over resources, the finalizer becomes a safeguard to clean up resources if the call to the `Dispose` method failed.</span></span>  
  
 <span data-ttu-id="5a8fe-138">Weitere Informationen zum Bereinigen von Ressourcen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="5a8fe-138">For more details about cleaning up resources, see the following topics:</span></span>  
  
-   [<span data-ttu-id="5a8fe-139">Bereinigen von nicht verwalteten Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5a8fe-139">Cleaning Up Unmanaged Resources</span></span>](../../../standard/garbage-collection/unmanaged.md)  
  
-   [<span data-ttu-id="5a8fe-140">Implementieren einer Dispose-Methode</span><span class="sxs-lookup"><span data-stu-id="5a8fe-140">Implementing a Dispose Method</span></span>](../../../standard/garbage-collection/implementing-dispose.md)  
  
-   [<span data-ttu-id="5a8fe-141">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5a8fe-141">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)  
  
## <a name="example"></a><span data-ttu-id="5a8fe-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5a8fe-142">Example</span></span>  
 <span data-ttu-id="5a8fe-143">Das folgende Beispiel erstellt drei Klassen, die eine Vererbungskette bilden.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-143">The following example creates three classes that make a chain of inheritance.</span></span> <span data-ttu-id="5a8fe-144">Die Klasse `First` ist die Basisklasse, `Second` wird von `First` abgeleitet, und `Third` wird von `Second` abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-144">The class `First` is the base class, `Second` is derived from `First`, and `Third` is derived from `Second`.</span></span> <span data-ttu-id="5a8fe-145">Alle drei verfügen über Finalizer.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-145">All three have finalizers.</span></span> <span data-ttu-id="5a8fe-146">In `Main` wird eine Instanz der am meisten abgeleiteten Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-146">In `Main`, an instance of the most-derived class is created.</span></span> <span data-ttu-id="5a8fe-147">Wenn das Programm ausgeführt wird, beachten Sie, dass die Finalizer der drei Klassen automatisch und in Reihenfolge von der am meisten bis zu der am wenigsten abgeleiteten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-147">When the program runs, notice that the finalizers for the three classes are called automatically, and in order, from the most-derived to the least-derived.</span></span>  
  
 <span data-ttu-id="5a8fe-148">[!code-cs[csProgGuideObjects#85](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5a8fe-148">[!code-cs[csProgGuideObjects#85](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5a8fe-149">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="5a8fe-149">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5a8fe-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a8fe-150">See Also</span></span>  
 <span data-ttu-id="5a8fe-151"><xref:System.IDisposable></span><span class="sxs-lookup"><span data-stu-id="5a8fe-151"><xref:System.IDisposable></span></span>   
 <span data-ttu-id="5a8fe-152">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5a8fe-152">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5a8fe-153">[Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="5a8fe-153">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 [<span data-ttu-id="5a8fe-154">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="5a8fe-154">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)

