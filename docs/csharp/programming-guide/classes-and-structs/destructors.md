---
title: Finalizer – C#-Programmierhandbuch
ms.date: 10/08/2018
helpviewer_keywords:
- ~ [C#], in finalizers
- C# language, finalizers
- finalizers [C#]
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
ms.openlocfilehash: c8ad738baa3ff76cf9ae8367f2fd2a1fb44a79d6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170298"
---
# <a name="finalizers-c-programming-guide"></a><span data-ttu-id="f6ea9-102">Finalizer (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="f6ea9-102">Finalizers (C# Programming Guide)</span></span>
<span data-ttu-id="f6ea9-103">Mit Finalizern (die auch als **Destruktoren** bezeichnet werden) werden alle erforderlichen endgültigen Bereinigungen durchgeführt, wenn eine Klasseninstanz vom Garbage Collector gesammelt wird.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-103">Finalizers (which are also called **destructors**) are used to perform any necessary final clean-up when a class instance is being collected by the garbage collector.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6ea9-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f6ea9-104">Remarks</span></span>  
  
- <span data-ttu-id="f6ea9-105">Finalizer können nicht in Strukturen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-105">Finalizers cannot be defined in structs.</span></span> <span data-ttu-id="f6ea9-106">Sie werden nur mit Klassen verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-106">They are only used with classes.</span></span>  
  
- <span data-ttu-id="f6ea9-107">Eine Klasse kann nur über einen Finalizer verfügen.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-107">A class can only have one finalizer.</span></span>  
  
- <span data-ttu-id="f6ea9-108">Finalizer können nicht vererbt oder überladen werden.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-108">Finalizers cannot be inherited or overloaded.</span></span>  
  
- <span data-ttu-id="f6ea9-109">Finalizer können nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-109">Finalizers cannot be called.</span></span> <span data-ttu-id="f6ea9-110">Sie werden automatisch aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-110">They are invoked automatically.</span></span>  
  
- <span data-ttu-id="f6ea9-111">Ein Finalizer kann nicht über Modifizierer oder Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-111">A finalizer does not take modifiers or have parameters.</span></span>  
  
 <span data-ttu-id="f6ea9-112">Folgendes ist z.B. eine Deklaration eines Finalizers für die Klasse `Car`:</span><span class="sxs-lookup"><span data-stu-id="f6ea9-112">For example, the following is a declaration of a finalizer for the `Car` class.</span></span>
  
 [!code-csharp[csProgGuideObjects#86](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#86)]  

<span data-ttu-id="f6ea9-113">Ein Finalizer kann auch als Ausdruckstextdefinition implementiert werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-113">A finalizer can also be implemented as an expression body definition, as the following example shows.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  
  
 <span data-ttu-id="f6ea9-114">Der Finalizer ruft <xref:System.Object.Finalize%2A> implizit auf der Basisklasse des Objekts auf.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-114">The finalizer implicitly calls <xref:System.Object.Finalize%2A> on the base class of the object.</span></span> <span data-ttu-id="f6ea9-115">Daher wird der Aufruf eines Finalizers implizit in den folgenden Code übersetzt:</span><span class="sxs-lookup"><span data-stu-id="f6ea9-115">Therefore, a call to a finalizer is implicitly translated to the following code:</span></span>  
  
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
  
 <span data-ttu-id="f6ea9-116">Dies bedeutet, dass die `Finalize`-Methode für alle Instanzen in der Vererbungskette rekursiv aufgerufen wird, von der am meisten bis zu der am wenigsten abgeleiteten.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-116">This means that the `Finalize` method is called recursively for all instances in the inheritance chain, from the most-derived to the least-derived.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f6ea9-117">Leere Finalizer sollten nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-117">Empty finalizers should not be used.</span></span> <span data-ttu-id="f6ea9-118">Wenn eine Klasse einen Finalizer enthält, wird ein Eintrag in der `Finalize`-Warteschlange erstellt.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-118">When a class contains a finalizer, an entry is created in the `Finalize` queue.</span></span> <span data-ttu-id="f6ea9-119">Wenn der Finalizer aufgerufen wird, wird der Garbage Collector aufgerufen, um die Warteschlange zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-119">When the finalizer is called, the garbage collector is invoked to process the queue.</span></span> <span data-ttu-id="f6ea9-120">Ein leerer Finalizer führt nur zu einem unnötigen Leistungsverlust.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-120">An empty finalizer just causes a needless loss of performance.</span></span>  
  
 <span data-ttu-id="f6ea9-121">Der Programmierer hat keine Kontrolle darüber, wann der Finalizer aufgerufen wird, da dies durch den Garbage Collector bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-121">The programmer has no control over when the finalizer is called because this is determined by the garbage collector.</span></span> <span data-ttu-id="f6ea9-122">Der Garbage Collector sucht nach Objekten, die von der Anwendung nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-122">The garbage collector checks for objects that are no longer being used by the application.</span></span> <span data-ttu-id="f6ea9-123">Wenn er ein Objekt als abschließbar angesehen wird, ruft er den Finalizer auf (sofern vorhanden) und fordert den Arbeitsspeicher, der zum Speichern des Objekts verwendet wurde, zurück.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-123">If it considers an object eligible for finalization, it calls the finalizer (if any) and reclaims the memory used to store the object.</span></span>

 <span data-ttu-id="f6ea9-124">In .NET Framework-Anwendungen (aber nicht in .NET Core-Anwendungen) werden auch Finalizer aufgerufen, wenn das Programm beendet wird.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-124">In .NET Framework applications (but not in .NET Core applications), finalizers are also called when the program exits.</span></span>
  
 <span data-ttu-id="f6ea9-125">Es ist möglich, die Garbage Collection durch Aufrufen von <xref:System.GC.Collect%2A> zu erzwingen, aber dies sollte meistens vermieden werden, da es Leistungsprobleme hervorrufen kann.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-125">It is possible to force garbage collection by calling <xref:System.GC.Collect%2A>, but most of the time, this should be avoided because it may create performance issues.</span></span>  
  
## <a name="using-finalizers-to-release-resources"></a><span data-ttu-id="f6ea9-126">Verwenden von Finalizern zum Freigeben von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f6ea9-126">Using finalizers to release resources</span></span>  
 <span data-ttu-id="f6ea9-127">Im Allgemeinen erfordert C# nicht so viel Speicherverwaltung wie benötigt wird, wenn Sie mit einer anderen Sprache entwickeln, die nicht auf eine Laufzeit mit der Garbage Collection abzielt.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-127">In general, C# does not require as much memory management as is needed when you develop with a language that does not target a runtime with garbage collection.</span></span> <span data-ttu-id="f6ea9-128">Der Garbage Collector von .NET Framework verwaltet implizit die Belegung und Freigabe von Arbeitsspeicher für Ihre Objekte.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-128">This is because the .NET Framework garbage collector implicitly manages the allocation and release of memory for your objects.</span></span> <span data-ttu-id="f6ea9-129">Wenn Ihre Anwendung nicht verwaltete Ressourcen wie z.B. Fenster, Dateien und Netzwerkverbindungen kapselt, sollten Sie Finalizer verwenden, um die Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-129">However, when your application encapsulates unmanaged resources such as windows, files, and network connections, you should use finalizers to free those resources.</span></span> <span data-ttu-id="f6ea9-130">Wenn das Objekt abgeschlossen werden kann, führt der Garbage Collector die `Finalize`-Methode des Objekts aus.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-130">When the object is eligible for finalization, the garbage collector runs the `Finalize` method of the object.</span></span>  
  
## <a name="explicit-release-of-resources"></a><span data-ttu-id="f6ea9-131">Explizite Freigabe von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f6ea9-131">Explicit release of resources</span></span>  
 <span data-ttu-id="f6ea9-132">Wenn Ihre Anwendung eine umfangreiche externe Ressource verwendet, wird außerdem empfohlen, dass Sie eine Möglichkeit bieten, die Ressource explizit freizugeben, bevor der Garbage Collector das Objekt freigibt.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-132">If your application is using an expensive external resource, we also recommend that you provide a way to explicitly release the resource before the garbage collector frees the object.</span></span> <span data-ttu-id="f6ea9-133">Implementieren Sie dazu eine `Dispose`-Methode aus der Schnittstelle <xref:System.IDisposable>, die die erforderliche Bereinigung für das Objekt durchführt.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-133">You do this by implementing a `Dispose` method from the <xref:System.IDisposable> interface that performs the necessary cleanup for the object.</span></span> <span data-ttu-id="f6ea9-134">Dies kann die Leistung der Anwendung erheblich verbessern.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-134">This can considerably improve the performance of the application.</span></span> <span data-ttu-id="f6ea9-135">Trotz dieser expliziten Kontrolle über Ressourcen, wird der Finalizer Ressourcen sicher bereinigen, wenn der Aufruf der `Dispose`-Methode fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-135">Even with this explicit control over resources, the finalizer becomes a safeguard to clean up resources if the call to the `Dispose` method failed.</span></span>  
  
 <span data-ttu-id="f6ea9-136">Weitere Informationen zum Bereinigen von Ressourcen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="f6ea9-136">For more details about cleaning up resources, see the following topics:</span></span>  
  
- [<span data-ttu-id="f6ea9-137">Bereinigen von nicht verwalteten Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f6ea9-137">Cleaning Up Unmanaged Resources</span></span>](../../../standard/garbage-collection/unmanaged.md)  
  
- [<span data-ttu-id="f6ea9-138">Implementieren einer Dispose-Methode</span><span class="sxs-lookup"><span data-stu-id="f6ea9-138">Implementing a Dispose Method</span></span>](../../../standard/garbage-collection/implementing-dispose.md)  
  
- [<span data-ttu-id="f6ea9-139">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f6ea9-139">using Statement</span></span>](../../language-reference/keywords/using-statement.md)  
  
## <a name="example"></a><span data-ttu-id="f6ea9-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f6ea9-140">Example</span></span>  
 <span data-ttu-id="f6ea9-141">Das folgende Beispiel erstellt drei Klassen, die eine Vererbungskette bilden.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-141">The following example creates three classes that make a chain of inheritance.</span></span> <span data-ttu-id="f6ea9-142">Die Klasse `First` ist die Basisklasse, `Second` wird von `First` abgeleitet, und `Third` wird von `Second` abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-142">The class `First` is the base class, `Second` is derived from `First`, and `Third` is derived from `Second`.</span></span> <span data-ttu-id="f6ea9-143">Alle drei verfügen über Finalizer.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-143">All three have finalizers.</span></span> <span data-ttu-id="f6ea9-144">In `Main` wird eine Instanz der am meisten abgeleiteten Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-144">In `Main`, an instance of the most-derived class is created.</span></span> <span data-ttu-id="f6ea9-145">Wenn das Programm ausgeführt wird, beachten Sie, dass die Finalizer der drei Klassen automatisch und in Reihenfolge von der am meisten bis zu der am wenigsten abgeleiteten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f6ea9-145">When the program runs, notice that the finalizers for the three classes are called automatically, and in order, from the most-derived to the least-derived.</span></span>  
  
 [!code-csharp[csProgGuideObjects#85](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#85)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="f6ea9-146">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="f6ea9-146">C# language specification</span></span>  

<span data-ttu-id="f6ea9-147">Weitere Informationen finden Sie im Abschnitt [Destruktoren](~/_csharplang/spec/classes.md#destructors) der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="f6ea9-147">For more information, see the [Destructors](~/_csharplang/spec/classes.md#destructors) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f6ea9-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f6ea9-148">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="f6ea9-149">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f6ea9-149">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f6ea9-150">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="f6ea9-150">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="f6ea9-151">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="f6ea9-151">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
