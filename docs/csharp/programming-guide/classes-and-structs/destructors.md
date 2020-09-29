---
title: Finalizer – C#-Programmierhandbuch
description: Finalizer in C#, die auch als „Destruktoren“ bezeichnet werden, führen alle erforderlichen endgültigen Bereinigungen durch, wenn eine Klasseninstanz vom Garbage Collector gesammelt wird.
ms.date: 10/08/2018
helpviewer_keywords:
- ~ [C#], in finalizers
- C# language, finalizers
- finalizers [C#]
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
ms.openlocfilehash: 61a00e766b0f975691b9f2a7c7561bb4f1d33c02
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174302"
---
# <a name="finalizers-c-programming-guide"></a><span data-ttu-id="1f6d6-103">Finalizer (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="1f6d6-103">Finalizers (C# Programming Guide)</span></span>

<span data-ttu-id="1f6d6-104">Mit Finalizern (die auch als **Destruktoren** bezeichnet werden) werden alle erforderlichen endgültigen Bereinigungen durchgeführt, wenn eine Klasseninstanz vom Garbage Collector gesammelt wird.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-104">Finalizers (which are also called **destructors**) are used to perform any necessary final clean-up when a class instance is being collected by the garbage collector.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f6d6-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1f6d6-105">Remarks</span></span>  
  
- <span data-ttu-id="1f6d6-106">Finalizer können nicht in Strukturen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-106">Finalizers cannot be defined in structs.</span></span> <span data-ttu-id="1f6d6-107">Sie werden nur mit Klassen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-107">They are only used with classes.</span></span>  
  
- <span data-ttu-id="1f6d6-108">Eine Klasse kann nur über einen Finalizer verfügen.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-108">A class can only have one finalizer.</span></span>  
  
- <span data-ttu-id="1f6d6-109">Finalizer können nicht vererbt oder überladen werden.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-109">Finalizers cannot be inherited or overloaded.</span></span>  
  
- <span data-ttu-id="1f6d6-110">Finalizer können nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-110">Finalizers cannot be called.</span></span> <span data-ttu-id="1f6d6-111">Sie werden automatisch aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-111">They are invoked automatically.</span></span>  
  
- <span data-ttu-id="1f6d6-112">Ein Finalizer kann nicht über Modifizierer oder Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-112">A finalizer does not take modifiers or have parameters.</span></span>  
  
 <span data-ttu-id="1f6d6-113">Folgendes ist z.B. eine Deklaration eines Finalizers für die Klasse `Car`:</span><span class="sxs-lookup"><span data-stu-id="1f6d6-113">For example, the following is a declaration of a finalizer for the `Car` class.</span></span>
  
 [!code-csharp[csProgGuideObjects#86](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#86)]  

<span data-ttu-id="1f6d6-114">Ein Finalizer kann auch als Ausdruckstextdefinition implementiert werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-114">A finalizer can also be implemented as an expression body definition, as the following example shows.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  
  
 <span data-ttu-id="1f6d6-115">Der Finalizer ruft <xref:System.Object.Finalize%2A> implizit auf der Basisklasse des Objekts auf.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-115">The finalizer implicitly calls <xref:System.Object.Finalize%2A> on the base class of the object.</span></span> <span data-ttu-id="1f6d6-116">Daher wird der Aufruf eines Finalizers implizit in den folgenden Code übersetzt:</span><span class="sxs-lookup"><span data-stu-id="1f6d6-116">Therefore, a call to a finalizer is implicitly translated to the following code:</span></span>  
  
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
  
 <span data-ttu-id="1f6d6-117">Dies bedeutet, dass die `Finalize`-Methode für alle Instanzen in der Vererbungskette rekursiv aufgerufen wird, von der am meisten bis zu der am wenigsten abgeleiteten.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-117">This design means that the `Finalize` method is called recursively for all instances in the inheritance chain, from the most-derived to the least-derived.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f6d6-118">Leere Finalizer sollten nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-118">Empty finalizers should not be used.</span></span> <span data-ttu-id="1f6d6-119">Wenn eine Klasse einen Finalizer enthält, wird ein Eintrag in der `Finalize`-Warteschlange erstellt.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-119">When a class contains a finalizer, an entry is created in the `Finalize` queue.</span></span> <span data-ttu-id="1f6d6-120">Wenn der Finalizer aufgerufen wird, wird der Garbage Collector aufgerufen, um die Warteschlange zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-120">When the finalizer is called, the garbage collector is invoked to process the queue.</span></span> <span data-ttu-id="1f6d6-121">Ein leerer Finalizer führt nur zu einem unnötigen Leistungsverlust.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-121">An empty finalizer just causes a needless loss of performance.</span></span>  
  
 <span data-ttu-id="1f6d6-122">Der Programmierer hat keine Kontrolle darüber, wann der Finalizer aufgerufen wird, da der Garbage Collector den Zeitpunkt des Aufrufs bestimmt.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-122">The programmer has no control over when the finalizer is called; the garbage collector decides when to call it.</span></span> <span data-ttu-id="1f6d6-123">Der Garbage Collector sucht nach Objekten, die von der Anwendung nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-123">The garbage collector checks for objects that are no longer being used by the application.</span></span> <span data-ttu-id="1f6d6-124">Wenn er ein Objekt als abschließbar angesehen wird, ruft er den Finalizer auf (sofern vorhanden) und fordert den Arbeitsspeicher, der zum Speichern des Objekts verwendet wurde, zurück.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-124">If it considers an object eligible for finalization, it calls the finalizer (if any) and reclaims the memory used to store the object.</span></span>

 <span data-ttu-id="1f6d6-125">In .NET Framework-Anwendungen (aber nicht in .NET Core-Anwendungen) werden auch Finalizer aufgerufen, wenn das Programm beendet wird.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-125">In .NET Framework applications (but not in .NET Core applications), finalizers are also called when the program exits.</span></span>
  
 <span data-ttu-id="1f6d6-126">Es ist möglich, die Garbage Collection durch Aufrufen von <xref:System.GC.Collect%2A> zu erzwingen. Dieser Aufruf sollte jedoch meistens vermieden werden, da er Leistungsprobleme hervorrufen kann.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-126">It's possible to force garbage collection by calling <xref:System.GC.Collect%2A>, but most of the time, this call should be avoided because it may create performance issues.</span></span>  
  
## <a name="using-finalizers-to-release-resources"></a><span data-ttu-id="1f6d6-127">Verwenden von Finalizern zum Freigeben von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1f6d6-127">Using finalizers to release resources</span></span>  

 <span data-ttu-id="1f6d6-128">Im Allgemeinen erfordert C# nicht so viel Speicherverwaltung seitens des Entwicklers wie Sprachen, die mit der Garbage Collection nicht auf eine Laufzeit abzielen.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-128">In general, C# does not require as much memory management on the part of the developer as languages that don't target a runtime with garbage collection.</span></span> <span data-ttu-id="1f6d6-129">Der Garbage Collector von .NET verwaltet implizit die Belegung und Freigabe von Arbeitsspeicher für Ihre Objekte.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-129">This is because the .NET garbage collector implicitly manages the allocation and release of memory for your objects.</span></span> <span data-ttu-id="1f6d6-130">Wenn Ihre Anwendung nicht verwaltete Ressourcen wie z. B. Fenster, Dateien und Netzwerkverbindungen kapselt, sollten Sie Finalizer verwenden, um die Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-130">However, when your application encapsulates unmanaged resources, such as windows, files, and network connections, you should use finalizers to free those resources.</span></span> <span data-ttu-id="1f6d6-131">Wenn das Objekt abgeschlossen werden kann, führt der Garbage Collector die `Finalize`-Methode des Objekts aus.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-131">When the object is eligible for finalization, the garbage collector runs the `Finalize` method of the object.</span></span>
  
## <a name="explicit-release-of-resources"></a><span data-ttu-id="1f6d6-132">Explizite Freigabe von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1f6d6-132">Explicit release of resources</span></span>  

 <span data-ttu-id="1f6d6-133">Wenn Ihre Anwendung eine umfangreiche externe Ressource verwendet, wird außerdem empfohlen, dass Sie eine Möglichkeit bieten, die Ressource explizit freizugeben, bevor der Garbage Collector das Objekt freigibt.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-133">If your application is using an expensive external resource, we also recommend that you provide a way to explicitly release the resource before the garbage collector frees the object.</span></span> <span data-ttu-id="1f6d6-134">Implementieren Sie zum Freigeben der Ressource eine `Dispose`-Methode aus der Schnittstelle <xref:System.IDisposable>, die die erforderliche Bereinigung für das Objekt durchführt.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-134">To release the resource, implement a `Dispose` method from the <xref:System.IDisposable> interface that performs the necessary cleanup for the object.</span></span> <span data-ttu-id="1f6d6-135">Dies kann die Leistung der Anwendung erheblich verbessern.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-135">This can considerably improve the performance of the application.</span></span> <span data-ttu-id="1f6d6-136">Trotz dieser expliziten Kontrolle über Ressourcen wird der Finalizer Ressourcen sicher bereinigen, wenn der Aufruf der `Dispose`-Methode fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-136">Even with this explicit control over resources, the finalizer becomes a safeguard to clean up resources if the call to the `Dispose` method fails.</span></span>  
  
 <span data-ttu-id="1f6d6-137">Weitere Informationen zum Bereinigen von Ressourcen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="1f6d6-137">For more information about cleaning up resources, see the following articles:</span></span>  
  
- [<span data-ttu-id="1f6d6-138">Bereinigen von nicht verwalteten Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1f6d6-138">Cleaning Up Unmanaged Resources</span></span>](../../../standard/garbage-collection/unmanaged.md)  
  
- [<span data-ttu-id="1f6d6-139">Implementieren einer Dispose-Methode</span><span class="sxs-lookup"><span data-stu-id="1f6d6-139">Implementing a Dispose Method</span></span>](../../../standard/garbage-collection/implementing-dispose.md)  
  
- [<span data-ttu-id="1f6d6-140">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1f6d6-140">using Statement</span></span>](../../language-reference/keywords/using-statement.md)  
  
## <a name="example"></a><span data-ttu-id="1f6d6-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1f6d6-141">Example</span></span>  

 <span data-ttu-id="1f6d6-142">Das folgende Beispiel erstellt drei Klassen, die eine Vererbungskette bilden.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-142">The following example creates three classes that make a chain of inheritance.</span></span> <span data-ttu-id="1f6d6-143">Die Klasse `First` ist die Basisklasse, `Second` wird von `First` abgeleitet, und `Third` wird von `Second` abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-143">The class `First` is the base class, `Second` is derived from `First`, and `Third` is derived from `Second`.</span></span> <span data-ttu-id="1f6d6-144">Alle drei verfügen über Finalizer.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-144">All three have finalizers.</span></span> <span data-ttu-id="1f6d6-145">In `Main` wird eine Instanz der am meisten abgeleiteten Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-145">In `Main`, an instance of the most-derived class is created.</span></span> <span data-ttu-id="1f6d6-146">Wenn das Programm ausgeführt wird, beachten Sie, dass die Finalizer der drei Klassen automatisch und in Reihenfolge von der am meisten bis zu der am wenigsten abgeleiteten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1f6d6-146">When the program runs, notice that the finalizers for the three classes are called automatically, and in order, from the most-derived to the least-derived.</span></span>  
  
 [!code-csharp[csProgGuideObjects#85](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#85)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="1f6d6-147">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="1f6d6-147">C# language specification</span></span>  

<span data-ttu-id="1f6d6-148">Weitere Informationen finden Sie im Abschnitt [Destruktoren](~/_csharplang/spec/classes.md#destructors) der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="1f6d6-148">For more information, see the [Destructors](~/_csharplang/spec/classes.md#destructors) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1f6d6-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f6d6-149">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="1f6d6-150">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1f6d6-150">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1f6d6-151">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="1f6d6-151">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="1f6d6-152">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="1f6d6-152">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
