---
title: Leitfaden zur Verwendung von Memory<T> und Span<T>
ms.date: 10/01/2018
helpviewer_keywords:
- Memory&lt;T&gt; and Span&lt;T&gt; best practices
- using Memory&lt;T&gt; and Span&lt;T&gt;
ms.openlocfilehash: b89969f212da6ac90d0fb0d1bf388626e136b92e
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158592"
---
# <a name="memoryt-and-spant-usage-guidelines"></a><span data-ttu-id="0f33f-102">Leitfaden zur Verwendung von Memory\<T> und Span\<T></span><span class="sxs-lookup"><span data-stu-id="0f33f-102">Memory\<T> and Span\<T> usage guidelines</span></span>

<span data-ttu-id="0f33f-103">.NET Core enthält eine Reihe von Typen, die eine beliebige zusammenhängende Speicherregion darstellen.</span><span class="sxs-lookup"><span data-stu-id="0f33f-103">.NET Core includes a number of types that represent an arbitrary contiguous region of memory.</span></span> <span data-ttu-id="0f33f-104">.NET Core 2.0 hat <xref:System.Span%601> und <xref:System.ReadOnlySpan%601> eingeführt. Dabei handelt es sich um einfache Speicherpuffer, die durch verwalteten oder nicht verwalteten Speicher gesichert werden können.</span><span class="sxs-lookup"><span data-stu-id="0f33f-104">.NET Core 2.0 introduced <xref:System.Span%601> and <xref:System.ReadOnlySpan%601>, which are lightweight memory buffers that can be backed by managed or unmanaged memory.</span></span> <span data-ttu-id="0f33f-105">Da diese Typen nur im Stapel gespeichert werden können, sind sie für eine Reihe von Szenarien ungeeignet. Hierzu zählen unter anderem asynchrone Methodenaufrufe.</span><span class="sxs-lookup"><span data-stu-id="0f33f-105">Because these types can only be stored on the stack, they are unsuitable for a number of scenarios, including asynchronous method calls.</span></span> <span data-ttu-id="0f33f-106">.NET Core 2.1 fügt eine Reihe von zusätzlichen Typen hinzu, einschließlich <xref:System.Memory%601>, <xref:System.ReadOnlyMemory%601>, <xref:System.Buffers.IMemoryOwner%601> und <xref:System.Buffers.MemoryPool%601>.</span><span class="sxs-lookup"><span data-stu-id="0f33f-106">.NET Core 2.1 adds a number of additional types, including <xref:System.Memory%601>, <xref:System.ReadOnlyMemory%601>, <xref:System.Buffers.IMemoryOwner%601>, and <xref:System.Buffers.MemoryPool%601>.</span></span> <span data-ttu-id="0f33f-107">Wie <xref:System.Span%601> kann auch <xref:System.Memory%601> und die verwandten Typen durch verwalteten und nicht verwalteten Speicher gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="0f33f-107">Like <xref:System.Span%601>, <xref:System.Memory%601> and its related types can be backed by both managed and unmanaged memory.</span></span> <span data-ttu-id="0f33f-108">Im Gegensatz zu <xref:System.Span%601> kann <xref:System.Memory%601> im verwalteten Heap gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="0f33f-108">Unlike <xref:System.Span%601>, <xref:System.Memory%601> can be stored on the managed heap.</span></span>

<span data-ttu-id="0f33f-109">Sowohl <xref:System.Span%601> als auch <xref:System.Memory%601> sind Puffer von strukturierten Daten, die in Pipelines verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="0f33f-109">Both <xref:System.Span%601> and <xref:System.Memory%601> are buffers of structured data that can be used in pipelines.</span></span> <span data-ttu-id="0f33f-110">Das heißt, sie sind so konzipiert, dass ein Teil oder alle Daten effizient an Komponenten in der Pipeline übergeben werden können, die sie verarbeiten und optional den Puffer modifizieren können.</span><span class="sxs-lookup"><span data-stu-id="0f33f-110">That is, they are designed so that some or all of the data can be efficiently passed to components in the pipeline, which can process them and optionally modify the buffer.</span></span> <span data-ttu-id="0f33f-111">Da <xref:System.Memory%601> und die zugehörigen Typen von mehreren Komponenten oder von mehreren Threads aufgerufen werden können, ist es wichtig, dass Entwickler einige Standardnutzungsrichtlinien befolgen, um robusten Code zu generieren.</span><span class="sxs-lookup"><span data-stu-id="0f33f-111">Because <xref:System.Memory%601> and its related types can be accessed by multiple components or by multiple threads, it's important that developers follow some standard usage guidelines to produce robust code.</span></span>

## <a name="owners-consumers-and-lifetime-management"></a><span data-ttu-id="0f33f-112">Besitzer, Consumer und Verwaltung der Lebensdauer</span><span class="sxs-lookup"><span data-stu-id="0f33f-112">Owners, consumers, and lifetime management</span></span>

<span data-ttu-id="0f33f-113">Da Puffer zwischen APIs ausgetauscht werden können und auf Puffer manchmal über mehrere Threads zugegriffen werden kann, ist es wichtig, die Lebensdauerverwaltung zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="0f33f-113">Since buffers can be passed around between APIs, and since buffers can sometimes be accessed from multiple threads, it's important to consider lifetime management.</span></span> <span data-ttu-id="0f33f-114">Es gibt drei grundlegende Konzepte:</span><span class="sxs-lookup"><span data-stu-id="0f33f-114">There are three core concepts:</span></span>

- <span data-ttu-id="0f33f-115">**Besitz**.</span><span class="sxs-lookup"><span data-stu-id="0f33f-115">**Ownership**.</span></span> <span data-ttu-id="0f33f-116">Der Besitzer einer Pufferinstanz ist für das die Verwaltung der Lebensdauer verantwortlich, einschließlich der Zerstörung des Puffers, wenn er nicht mehr in Gebrauch ist.</span><span class="sxs-lookup"><span data-stu-id="0f33f-116">The owner of a buffer instance is responsible for lifetime management, including destroying the buffer when it's no longer in use.</span></span> <span data-ttu-id="0f33f-117">Alle Puffer haben nur einen einzigen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="0f33f-117">All buffers have a single owner.</span></span> <span data-ttu-id="0f33f-118">Im Allgemeinen ist der Besitzer die Komponente, die den Puffer erstellt hat, oder die den Puffer von einer Factory erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="0f33f-118">Generally the owner is the component that created the buffer or that received the buffer from a factory.</span></span> <span data-ttu-id="0f33f-119">Der Besitz kann auch übertragen werden; **Komponente-A** kann die Kontrolle über den Puffer an **Komponente-B** abgeben, wobei **Komponente-A** den Puffer nicht mehr verwenden darf, und **Komponente-B** wird für die Zerstörung des Puffers verantwortlich, wenn er nicht mehr verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0f33f-119">Ownership can also be transferred; **Component-A** can relinquish control of the buffer to **Component-B**, at which point **Component-A** may no longer use the buffer, and **Component-B** becomes responsible for destroying the buffer when it's no longer in use.</span></span>

- <span data-ttu-id="0f33f-120">**Verbrauch**.</span><span class="sxs-lookup"><span data-stu-id="0f33f-120">**Consumption**.</span></span> <span data-ttu-id="0f33f-121">Der Consumer einer Pufferinstanz darf die Pufferinstanz nutzen, indem er aus ihr liest und eventuell in sie schreibt.</span><span class="sxs-lookup"><span data-stu-id="0f33f-121">The consumer of a buffer instance is allowed to use the buffer instance by reading from it and possibly writing to it.</span></span> <span data-ttu-id="0f33f-122">Puffer können jeweils einen Consumer haben, es sei denn, es ist ein externer Synchronisationsmechanismus vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="0f33f-122">Buffers can have one consumer at a time unless some external synchronization mechanism is provided.</span></span> <span data-ttu-id="0f33f-123">Der aktive Consumer eines Puffers ist nicht unbedingt der Besitzer des Puffers.</span><span class="sxs-lookup"><span data-stu-id="0f33f-123">The active consumer of a buffer isn't necessarily the buffer's owner.</span></span>

- <span data-ttu-id="0f33f-124">**Leasedauer**.</span><span class="sxs-lookup"><span data-stu-id="0f33f-124">**Lease**.</span></span> <span data-ttu-id="0f33f-125">Die Leasedauer ist die Zeitspanne, in der eine bestimmte Komponente als Consumer des Puffers zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="0f33f-125">The lease is the length of time that a particular component is allowed to be the consumer of the buffer.</span></span>

<span data-ttu-id="0f33f-126">Im folgenden Pseudocodebeispiel werden diese drei Konzepte veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0f33f-126">The following pseudo-code example illustrates these three concepts.</span></span> <span data-ttu-id="0f33f-127">Es beinhaltet eine `Main`-Methode, die einen <xref:System.Memory%601>-Puffer vom Typ <xref:System.Char> instanziiert, die `WriteInt32ToBuffer`-Methode aufruft, um die Zeichenfolgendarstellung einer ganzen Zahl in den Puffer zu schreiben, und dann die `DisplayBufferToConsole`-Methode aufruft, um den Wert des Puffers anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0f33f-127">It includes a `Main` method that instantiates a <xref:System.Memory%601> buffer of type <xref:System.Char>, calls the `WriteInt32ToBuffer` method to write the string representation of an integer to the buffer, and then calls the `DisplayBufferToConsole` method to display the value of the buffer.</span></span>

```csharp
using System;

class Program
{
    // Write 'value' as a human-readable string to the output buffer.
    void WriteInt32ToBuffer(int value, Buffer buffer);

    // Display the contents of the buffer to the console.
    void DisplayBufferToConsole(Buffer buffer);

    // Application code
    static void Main()
    {
        var buffer = CreateBuffer();
        try
        {
            int value = Int32.Parse(Console.ReadLine());
            WriteInt32ToBuffer(value, buffer);
            DisplayBufferToConsole(buffer);
        }
        finally
        {
            buffer.Destroy();
        }
    }
}
```

<span data-ttu-id="0f33f-128">Die `Main`-Methode erstellt den Puffer (in diesem Fall eine <xref:System.Span%601>-Instanz) und damit seinen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="0f33f-128">The `Main` method creates the buffer (in this case an <xref:System.Span%601> instance) and so is its owner.</span></span> <span data-ttu-id="0f33f-129">Daher ist `Main` dafür verantwortlich, den Puffer zu zerstören, wenn er nicht mehr verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0f33f-129">Therefore, `Main` is responsible for destroying the buffer when it's no longer in use.</span></span> <span data-ttu-id="0f33f-130">Dies geschieht durch Aufrufen der <xref:System.Span%601.Clear?displayProperty=nameWithType> Methode des Puffers.</span><span class="sxs-lookup"><span data-stu-id="0f33f-130">It does this by calling the buffer's <xref:System.Span%601.Clear?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0f33f-131">(Die <xref:System.Span%601.Clear>-Methode löscht hier tatsächlich den Speicher des Puffers; die <xref:System.Span%601>-Struktur verfügt über keine Methode, die den Puffer zerstört.)</span><span class="sxs-lookup"><span data-stu-id="0f33f-131">(The <xref:System.Span%601.Clear> method here actually clears the buffer's memory; the <xref:System.Span%601> structure doesn't actually have a method that destroys the buffer.)</span></span>

<span data-ttu-id="0f33f-132">Der Puffer hat zwei Consumer: `WriteInt32ToBuffer` und `DisplayBufferToConsole`.</span><span class="sxs-lookup"><span data-stu-id="0f33f-132">The buffer has two consumers, `WriteInt32ToBuffer` and `DisplayBufferToConsole`.</span></span> <span data-ttu-id="0f33f-133">Es gibt immer nur jeweils einen Consumer (zuerst `WriteInt32ToBuffer`, dann `DisplayBufferToConsole`), und keiner der Consumer besitzt den Puffer.</span><span class="sxs-lookup"><span data-stu-id="0f33f-133">There is only one consumer at a time (first `WriteInt32ToBuffer`, then `DisplayBufferToConsole`), and neither of the consumers owns the buffer.</span></span> <span data-ttu-id="0f33f-134">Beachten Sie auch, dass „Consumer“ in diesem Zusammenhang keine schreibgeschützte Ansicht des Puffers impliziert; Consumer können den Inhalt des Puffers ändern, wie `WriteInt32ToBuffer`, wenn sie eine Lese-/Schreibansicht des Puffers erhalten.</span><span class="sxs-lookup"><span data-stu-id="0f33f-134">Note also that "consumer" in this context doesn't imply a read-only view of the buffer; consumers can modify the buffer's contents, as `WriteInt32ToBuffer` does, if given a read/write view of the buffer.</span></span>

<span data-ttu-id="0f33f-135">Die `WriteInt32ToBuffer`-Methode verfügt über eine Leasedauer (kann den Puffer zwischen dem Start des Methodenaufrufs und der Zeit, die die Methode zurückgibt, verbrauchen).</span><span class="sxs-lookup"><span data-stu-id="0f33f-135">The `WriteInt32ToBuffer` method has a lease on (can consume) the buffer between the start of the method call and the time the method returns.</span></span> <span data-ttu-id="0f33f-136">Ebenso hat `DisplayBufferToConsole` eine Leasingdauer für den Puffer, während er ausgeführt wird, und die Leasedauer wird freigegeben, wenn die Methode entladen wird.</span><span class="sxs-lookup"><span data-stu-id="0f33f-136">Similarly, `DisplayBufferToConsole` has a lease on the buffer while it's executing, and the lease is released when the method unwinds.</span></span> <span data-ttu-id="0f33f-137">(Es gibt keine API für die Leaseverwaltung; eine „Leasedauer“ ist nur ein Konzept.)</span><span class="sxs-lookup"><span data-stu-id="0f33f-137">(There is no API for lease management; a "lease" is a conceptual matter.)</span></span>

## <a name="memoryt-and-the-ownerconsumer-model"></a><span data-ttu-id="0f33f-138">Memory\<T > und das Besitzer/Consumer-Modell</span><span class="sxs-lookup"><span data-stu-id="0f33f-138">Memory\<T> and the owner/consumer model</span></span>

<span data-ttu-id="0f33f-139">Wie im Abschnitt [Besitzer, Consumer und Verwaltung der Lebensdauer](#owners-consumers-and-lifetime-management) beschrieben, hat ein Puffer immer einen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="0f33f-139">As the [Owners, consumers, and lifetime management](#owners-consumers-and-lifetime-management) section notes, a buffer always has an owner.</span></span> <span data-ttu-id="0f33f-140">.NET Core unterstützt zwei Besitzmodelle:</span><span class="sxs-lookup"><span data-stu-id="0f33f-140">.NET Core supports two ownership models:</span></span>

- <span data-ttu-id="0f33f-141">Ein Modell, das alleinigen Besitz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0f33f-141">A model that supports single ownership.</span></span> <span data-ttu-id="0f33f-142">Ein Puffer hat einen einzigen Besitzer für seine gesamte Lebensdauer.</span><span class="sxs-lookup"><span data-stu-id="0f33f-142">A buffer has a single owner for its entire lifetime.</span></span>

- <span data-ttu-id="0f33f-143">Ein Modell, das die Besitzübertragung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0f33f-143">A model that supports ownership transfer.</span></span> <span data-ttu-id="0f33f-144">Der Besitz eines Puffers kann von seinem ursprünglichen Besitzer (seinem Ersteller) auf eine andere Komponente übertragen werden, die dann für die Lebensdauerverwaltung des Puffers verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="0f33f-144">Ownership of a buffer can be transferred from its original owner (its creator) to another component, which then becomes responsible for the buffer's lifetime management.</span></span> <span data-ttu-id="0f33f-145">Dieser Besitzer kann seinerseits den Besitz auf eine andere Komponente übertragen, und so weiter.</span><span class="sxs-lookup"><span data-stu-id="0f33f-145">That owner can in turn transfer ownership to another component, and so on.</span></span>

<span data-ttu-id="0f33f-146">Sie verwenden die <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>-Schnittstelle, um den Besitz eines Puffers explizit zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="0f33f-146">You use the <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType> interface to explicitly manage the ownership of a buffer.</span></span> <span data-ttu-id="0f33f-147"><xref:System.Buffers.IMemoryOwner%601> unterstützt beide Besitzmodelle.</span><span class="sxs-lookup"><span data-stu-id="0f33f-147"><xref:System.Buffers.IMemoryOwner%601> supports both ownership models.</span></span> <span data-ttu-id="0f33f-148">Die Komponente, die einen Verweis <xref:System.Buffers.IMemoryOwner%601> hat, besitzt den Puffer.</span><span class="sxs-lookup"><span data-stu-id="0f33f-148">The component that has an <xref:System.Buffers.IMemoryOwner%601> reference owns the buffer.</span></span> <span data-ttu-id="0f33f-149">Das folgende Beispiel verwendet eine <xref:System.Buffers.IMemoryOwner%601?>-Instanz, um den Besitz eines <xref:System.Memory%601>-Puffers anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0f33f-149">The following example uses an <xref:System.Buffers.IMemoryOwner%601?> instance to reflect the ownership of an <xref:System.Memory%601> buffer.</span></span>

[!code-csharp[ownership](~/samples/snippets/standard/buffers/memory-t/owner/owner.cs)]

<span data-ttu-id="0f33f-150">Wir können dieses Beispiel auch mit dem [`using`](../../csharp/language-reference/keywords/using-statement.md) schreiben:</span><span class="sxs-lookup"><span data-stu-id="0f33f-150">We can also write this example with the [`using`](../../csharp/language-reference/keywords/using-statement.md):</span></span>

[!code-csharp[ownership-using](~/samples/snippets/standard/buffers/memory-t/owner-using/owner-using.cs)]

<span data-ttu-id="0f33f-151">In diesem Code:</span><span class="sxs-lookup"><span data-stu-id="0f33f-151">In this code:</span></span>

- <span data-ttu-id="0f33f-152">Die `Main`-Methode enthält den Verweis auf die <xref:System.Buffers.IMemoryOwner%601>-Instanz, sodass die `Main`-Methode der Besitzer des Puffers ist.</span><span class="sxs-lookup"><span data-stu-id="0f33f-152">The `Main` method holds the reference to the <xref:System.Buffers.IMemoryOwner%601> instance, so the `Main` method is the owner of the buffer.</span></span>

- <span data-ttu-id="0f33f-153">Die `WriteInt32ToBuffer`- und `DisplayBufferToConsole`-Methode akzeptieren <xref:System.Memory%601> als öffentliche API.</span><span class="sxs-lookup"><span data-stu-id="0f33f-153">The `WriteInt32ToBuffer` and `DisplayBufferToConsole` methods accept <xref:System.Memory%601> as a public API.</span></span> <span data-ttu-id="0f33f-154">Daher sind sie der Consumer des Puffers.</span><span class="sxs-lookup"><span data-stu-id="0f33f-154">Therefore, they are consumers of the buffer.</span></span> <span data-ttu-id="0f33f-155">Und sie können ihn nur jeweils einzeln verbrauchen.</span><span class="sxs-lookup"><span data-stu-id="0f33f-155">And they only consume it one at a time.</span></span>

<span data-ttu-id="0f33f-156">Obwohl die `WriteInt32ToBuffer`-Methode dazu bestimmt ist, einen Wert in den Puffer zu schreiben, ist die `DisplayBufferToConsole`-Methode dies nicht.</span><span class="sxs-lookup"><span data-stu-id="0f33f-156">Although the `WriteInt32ToBuffer` method is intended to write a value to the buffer, the `DisplayBufferToConsole` method isn't.</span></span> <span data-ttu-id="0f33f-157">Um dies anzugeben, hätte sie ein Argument vom Typ <xref:System.ReadOnlyMemory%601> akzeptieren können.</span><span class="sxs-lookup"><span data-stu-id="0f33f-157">To reflect this, it could have accepted an argument of type <xref:System.ReadOnlyMemory%601>.</span></span> <span data-ttu-id="0f33f-158">Weitere Informationen zu <xref:System.ReadOnlyMemory%601> finden Sie unter [Regel 2: ReadOnlySpan\<T> oder ReadOnlyMemory\<T> verwenden, wenn der Puffer schreibgeschützt sein soll](#rule-2).</span><span class="sxs-lookup"><span data-stu-id="0f33f-158">For more information on <xref:System.ReadOnlyMemory%601>, see [Rule #2: Use ReadOnlySpan\<T> or ReadOnlyMemory\<T> if the buffer should be read-only](#rule-2).</span></span>

### <a name="ownerless-memoryt-instances"></a><span data-ttu-id="0f33f-159">Memory\<T>-Instanzen ohne Besitzer</span><span class="sxs-lookup"><span data-stu-id="0f33f-159">"Ownerless" Memory\<T> instances</span></span>

<span data-ttu-id="0f33f-160">Sie können einen <xref:System.Memory%601>-Instanz ohne die Verwendung von <xref:System.Buffers.IMemoryOwner%601> erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f33f-160">You can create a <xref:System.Memory%601> instance without using <xref:System.Buffers.IMemoryOwner%601>.</span></span> <span data-ttu-id="0f33f-161">In diesem Fall ist der Besitz des Puffers eher implizit als explizit, und es wird nur das Einzelbesitzermodell unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0f33f-161">In this case, ownership of the buffer is implicit rather than explicit, and only the single-owner model is supported.</span></span> <span data-ttu-id="0f33f-162">Gehen Sie dafür so vor:</span><span class="sxs-lookup"><span data-stu-id="0f33f-162">You can do this by:</span></span>

- <span data-ttu-id="0f33f-163">Direkter Aufruf eines der <xref:System.Memory%601>-Konstruktoren, Übergabe eines `T[]`, wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="0f33f-163">Calling one of the  <xref:System.Memory%601> constructors directly, passing in a `T[]`, as the following example does.</span></span>

- <span data-ttu-id="0f33f-164">Aufrufen der [String.AsMemory](xref:System.MemoryExtensions.AsMemory(System.String))-Erweiterungsmethode zur Erstellung einer `ReadOnlyMemory<char>`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="0f33f-164">Calling the [String.AsMemory](xref:System.MemoryExtensions.AsMemory(System.String)) extension method to produce a `ReadOnlyMemory<char>` instance.</span></span>

[!code-csharp[ownerless-memory](~/samples/snippets/standard/buffers/memory-t/ownerless/ownerless.cs)]

<span data-ttu-id="0f33f-165">Die Methode, die die <xref:System.Memory%601>-Instanz initial erstellt, ist der implizite Besitzer des Puffers.</span><span class="sxs-lookup"><span data-stu-id="0f33f-165">The method that initially creates the <xref:System.Memory%601> instance is the implicit owner of the buffer.</span></span> <span data-ttu-id="0f33f-166">Der Besitz kann nicht auf eine andere Komponente übertragen werden, da es keine <xref:System.Buffers.IMemoryOwner%601>-Instanz gibt, die die Übertragung vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="0f33f-166">Ownership cannot be transferred to any other component because there is no <xref:System.Buffers.IMemoryOwner%601> instance to facilitate the transfer.</span></span> <span data-ttu-id="0f33f-167">(Alternativ ist es auch vorstellbar, dass der Garbage Collector der Runtime den Puffer besitzt und alle Methoden nur den Puffer verbrauchen.)</span><span class="sxs-lookup"><span data-stu-id="0f33f-167">(As an alternative, you can also imagine that the runtime's garbage collector owns the buffer, and all methods just consume the buffer.)</span></span>

## <a name="usage-guidelines"></a><span data-ttu-id="0f33f-168">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0f33f-168">Usage guidelines</span></span>

<span data-ttu-id="0f33f-169">Da ein Speicherblock einen Besitzer hat, aber an mehrere Komponenten übergeben werden soll, von denen einige gleichzeitig auf einem bestimmten Speicherblock arbeiten können, ist es wichtig, Richtlinien für die Verwendung von <xref:System.Memory%601> und <xref:System.Span%601> festzulegen.</span><span class="sxs-lookup"><span data-stu-id="0f33f-169">Because a memory block is owned but is intended to be passed to multiple components, some of which may operate upon a particular memory block simultaneously, it is important to establish guidelines for using both <xref:System.Memory%601> and <xref:System.Span%601>.</span></span>  <span data-ttu-id="0f33f-170">Richtlinien sind aus folgendem Grund erforderlich:</span><span class="sxs-lookup"><span data-stu-id="0f33f-170">Guidelines are necessary because:</span></span>

- <span data-ttu-id="0f33f-171">Es ist möglich, dass eine Komponente einen Verweis auf einen Speicherblock behält, nachdem sein Besitzer ihn freigegeben hat.</span><span class="sxs-lookup"><span data-stu-id="0f33f-171">It is possible for a component to retain a reference to a memory block after its owner has released it.</span></span>

- <span data-ttu-id="0f33f-172">Es ist möglich, dass eine Komponente gleichzeitig mit einer anderen Komponente auf einem Puffer arbeitet, wodurch die Daten im Puffer beschädigt werden.</span><span class="sxs-lookup"><span data-stu-id="0f33f-172">It is possible for a component to operate on a buffer at the same time that another component is operating on it, in the process corrupting the data in the buffer.</span></span>

- <span data-ttu-id="0f33f-173">Durch die Stapelzuordnung von <xref:System.Span%601> wird zwar die Leistung optimiert und <xref:System.Span%601> zum bevorzugten Typ für den Betrieb auf einem Speicherblock, aber auch <xref:System.Span%601> einigen bedeutenden Einschränkungen unterworfen.</span><span class="sxs-lookup"><span data-stu-id="0f33f-173">While the stack-allocated nature of <xref:System.Span%601> optimizes performance and makes <xref:System.Span%601> the preferred type for operating on a memory block, it also subjects <xref:System.Span%601> to some major restrictions.</span></span> <span data-ttu-id="0f33f-174">Es ist wichtig zu wissen, wann einen <xref:System.Span%601> und wann <xref:System.Memory%601> verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="0f33f-174">It is important to know when to use a <xref:System.Span%601> and when to use <xref:System.Memory%601>.</span></span>

<span data-ttu-id="0f33f-175">Nachfolgend finden Sie unsere Empfehlungen für den erfolgreichen Einsatz von <xref:System.Memory%601> und den verwandten Typen.</span><span class="sxs-lookup"><span data-stu-id="0f33f-175">The following are our recommendations for successfully using <xref:System.Memory%601> and its related types.</span></span> <span data-ttu-id="0f33f-176">Die Richtlinien, die für <xref:System.Memory%601> und <xref:System.Span%601> gelten, gelten auch für <xref:System.ReadOnlyMemory%601> und <xref:System.ReadOnlySpan%601>, sofern nicht ausdrücklich anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="0f33f-176">Guidance that applies to <xref:System.Memory%601> and <xref:System.Span%601> also applies to <xref:System.ReadOnlyMemory%601> and <xref:System.ReadOnlySpan%601> unless we explicitly note otherwise.</span></span>

<span data-ttu-id="0f33f-177">**Regel 1: Für eine synchrone API Span\<T> anstelle von Memory\<T> als Parameter verwenden, wenn möglich.**</span><span class="sxs-lookup"><span data-stu-id="0f33f-177">**Rule #1: For a synchronous API, use Span\<T> instead of Memory\<T> as a parameter if possible.**</span></span>

<span data-ttu-id="0f33f-178"><xref:System.Span%601> ist vielseitiger als <xref:System.Memory%601> und kann eine größere Anzahl von zusammenhängenden Speicherpuffern darstellen.</span><span class="sxs-lookup"><span data-stu-id="0f33f-178"><xref:System.Span%601> is more versatile than <xref:System.Memory%601> and can represent a wider variety of contiguous memory buffers.</span></span> <span data-ttu-id="0f33f-179"><xref:System.Span%601> bietet außerdem eine bessere Leistung als <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="0f33f-179"><xref:System.Span%601> also offers better performance than <xref:System.Memory%601>.</span></span> <span data-ttu-id="0f33f-180">Schließlich können Sie die <xref:System.Memory%601.Span?displayProperty=nameWithType>-Eigenschaft verwenden, um eine <xref:System.Memory%601>-Instanz in eine <xref:System.Span%601>-Instanz zu konvertieren, obwohl eine Span\<T>-in-Memory\<T>-Konvertierung nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="0f33f-180">Finally, you can use the <xref:System.Memory%601.Span?displayProperty=nameWithType> property to convert a <xref:System.Memory%601> instance to a <xref:System.Span%601>, although Span\<T>-to-Memory\<T> conversion isn't possible.</span></span> <span data-ttu-id="0f33f-181">Wenn Ihre Aufrufer also eine <xref:System.Memory%601>-Instanz haben, können sie Ihre Methoden trotzdem mit <xref:System.Span%601>-Parametern aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0f33f-181">So if your callers happen to have a <xref:System.Memory%601> instance, they'll be able to call your methods with <xref:System.Span%601> parameters anyway.</span></span>

<span data-ttu-id="0f33f-182">Die Verwendung eines Parameters vom Typ <xref:System.Span%601> anstelle von Typ <xref:System.Memory%601> unterstützt Sie auch dabei, eine korrekte Implementierung einer konsumierenden Methode zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="0f33f-182">Using a parameter of type <xref:System.Span%601> instead of type <xref:System.Memory%601> also helps you write a correct consuming method implementation.</span></span> <span data-ttu-id="0f33f-183">Die Kompilierzeit wird automatisch überprüft, um sicherzustellen, dass Sie nicht versuche, nach Ablauf der Leasedauer auf den Puffer zuzugreifen (weitere Informationen dazu im weiteren Verlauf).</span><span class="sxs-lookup"><span data-stu-id="0f33f-183">You'll automatically get compile-time checks to ensure that you're not attempting to access the buffer beyond your method's lease (more on this later).</span></span>

<span data-ttu-id="0f33f-184">Manchmal müssen Sie einen <xref:System.Memory%601>-Parameter anstelle eines <xref:System.Span%601>-Parameters verwenden, auch wenn Sie vollständig synchron sind.</span><span class="sxs-lookup"><span data-stu-id="0f33f-184">Sometimes, you'll have to use a <xref:System.Memory%601> parameter instead of a <xref:System.Span%601> parameter, even if you're fully synchronous.</span></span> <span data-ttu-id="0f33f-185">Vielleicht akzeptiert eine API, von der Sie abhängen, nur <xref:System.Memory%601>-Argumente.</span><span class="sxs-lookup"><span data-stu-id="0f33f-185">Perhaps an API that you depend accepts only <xref:System.Memory%601> arguments.</span></span> <span data-ttu-id="0f33f-186">Dies ist in Ordnung, aber beachten Sie die Vor- und Nachteile, die bei der synchronen Verwendung von <xref:System.Memory%601> auftreten.</span><span class="sxs-lookup"><span data-stu-id="0f33f-186">This is fine, but be aware of the tradeoffs involved when using <xref:System.Memory%601> synchronously.</span></span>

<a name="rule-2" />

<span data-ttu-id="0f33f-187">**Regel 2: ReadOnlySpan\<T> oder ReadOnlyMemory\<T> verwenden, wenn der Puffer schreibgeschützt sein soll.**</span><span class="sxs-lookup"><span data-stu-id="0f33f-187">**Rule #2: Use ReadOnlySpan\<T> or ReadOnlyMemory\<T> if the buffer should be read-only.**</span></span>

<span data-ttu-id="0f33f-188">In den früheren Beispielen liest die `DisplayBufferToConsole`-Methode nur aus dem Puffer und ändert den Inhalt des Puffers nicht.</span><span class="sxs-lookup"><span data-stu-id="0f33f-188">In the earlier examples, the `DisplayBufferToConsole` method only reads from the buffer; it doesn't modify the contents of the buffer.</span></span> <span data-ttu-id="0f33f-189">Die Methodensignatur sollte wie folgt geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0f33f-189">The method signature should be changed to the following.</span></span>

```csharp
void DisplayBufferToConsole(ReadOnlyMemory<char> buffer);
```

<span data-ttu-id="0f33f-190">Wenn wir diese Regel und Regel 1 kombinieren, können wir die Methodensignatur wie folgt umschreiben:</span><span class="sxs-lookup"><span data-stu-id="0f33f-190">In fact, if we combine this rule and Rule #1, we can do even better and rewrite the method signature as follows:</span></span>

```csharp
void DisplayBufferToConsole(ReadOnlySpan<char> buffer);
```

<span data-ttu-id="0f33f-191">Die `DisplayBufferToConsole`-Methode funktioniert nun mit praktisch jedem denkbaren Puffertyp: `T[]`, Speicher, der mit [stackalloc](../../csharp/language-reference/operators/stackalloc.md) zugewiesen wurde, und so weiter.</span><span class="sxs-lookup"><span data-stu-id="0f33f-191">The `DisplayBufferToConsole` method now works with virtually every buffer type imaginable: `T[]`, storage allocated with [stackalloc](../../csharp/language-reference/operators/stackalloc.md), and so on.</span></span> <span data-ttu-id="0f33f-192">Sie können einen <xref:System.String> sogar direkt übergeben!</span><span class="sxs-lookup"><span data-stu-id="0f33f-192">You can even pass a <xref:System.String> directly into it!</span></span>

<span data-ttu-id="0f33f-193">**Regel 3: Wenn Ihre Methode Memory\<T> akzeptiert und `void` zurückgibt, dürfen Sie die Memory\<T>-Instanz nicht verwenden, nachdem Ihre Methode ein Ergebnis zurückgegeben hat.**</span><span class="sxs-lookup"><span data-stu-id="0f33f-193">**Rule #3: If your method accepts Memory\<T> and returns `void`, you must not use the Memory\<T> instance after your method returns.**</span></span>

<span data-ttu-id="0f33f-194">Dies bezieht sich auf das bereits erwähnte Konzept der „Leasedauer“.</span><span class="sxs-lookup"><span data-stu-id="0f33f-194">This relates to the "lease" concept mentioned earlier.</span></span> <span data-ttu-id="0f33f-195">Die Leasedauer für eine Methode auf der <xref:System.Memory%601>-Instanz, die „void“ zurückgibt, beginnt, wenn die Methode aufgerufen wird, und endet, wenn die Methode beendet wird.</span><span class="sxs-lookup"><span data-stu-id="0f33f-195">A void-returning method's lease on the <xref:System.Memory%601> instance begins when the method is entered, and it ends when the method exits.</span></span> <span data-ttu-id="0f33f-196">Schauen Sie sich das folgende Beispiel an, in dem basierend auf der Eingabe von der Konsole ein `Log` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0f33f-196">Consider the following example, which calls `Log` in a loop based on input from the console.</span></span>

[!code-csharp[void-returning](~/samples/snippets/standard/buffers/memory-t/void-returning/void-returning.cs#1)]

<span data-ttu-id="0f33f-197">Wenn `Log` eine vollständig synchrone Methode ist, verhält sich dieser Code wie erwartet, da es zu einem bestimmten Zeitpunkt nur einen aktiven Verbraucher der Speicherinstanz gibt.</span><span class="sxs-lookup"><span data-stu-id="0f33f-197">If `Log` is a fully synchronous method, this code will behave as expected because there is only one active consumer of the memory instance at any given time.</span></span>
<span data-ttu-id="0f33f-198">Aber stellen Sie sich vor, `Log` hat stattdessen diese Implementierung.</span><span class="sxs-lookup"><span data-stu-id="0f33f-198">But imagine instead that `Log` has this implementation.</span></span>

```csharp
// !!! INCORRECT IMPLEMENTATION !!!
static void Log(ReadOnlyMemory<char> message)
{
    // Run in background so that we don't block the main thread while performing IO.
    Task.Run(() =>
    {
        StreamWriter sw = File.AppendText(@".\input-numbers.dat");
        sw.WriteLine(message);
    });
}
```

<span data-ttu-id="0f33f-199">In dieser Implementierung verstößt `Log` gegen die Leasedauer, weil immer noch versucht wird, die <xref:System.Memory%601>-Instanz im Hintergrund zu verwenden, nachdem die ursprüngliche Methode zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="0f33f-199">In this implementation, `Log` violates its lease because it still attempts to use the <xref:System.Memory%601> instance in the background after the original method has returned.</span></span> <span data-ttu-id="0f33f-200">Die `Main`-Methode könnte den Puffer verändern, während `Log` versucht, aus ihm zu lesen. Das könnte zu einer Datenbeschädigung führen.</span><span class="sxs-lookup"><span data-stu-id="0f33f-200">The `Main` method could mutate the buffer while `Log` attempts to read from it, which could result in data corruption.</span></span>

<span data-ttu-id="0f33f-201">Es gibt mehrere Möglichkeiten, dieses Problem zu lösen:</span><span class="sxs-lookup"><span data-stu-id="0f33f-201">There are several ways to resolve this:</span></span>

- <span data-ttu-id="0f33f-202">Die `Log`-Methode kann <xref:System.Threading.Tasks.Task> anstelle von `void` zurückgeben, wie es bei der folgenden Implementierung der `Log`-Methode der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="0f33f-202">The `Log` method can return a <xref:System.Threading.Tasks.Task> instead of `void`, as the following implementation of the `Log` method does.</span></span>

   [!code-csharp[task-returning](~/samples/snippets/standard/buffers/memory-t/task-returning2/task-returning2.cs#1)]

- <span data-ttu-id="0f33f-203">`Log` kann stattdessen wie folgt implementiert werden:</span><span class="sxs-lookup"><span data-stu-id="0f33f-203">`Log` can instead be implemented as follows:</span></span>

   [!code-csharp[defensive-copy](~/samples/snippets/standard/buffers/memory-t/task-returning/task-returning.cs#1)]

<span data-ttu-id="0f33f-204">**Regel 4: Wenn Ihre Methode Memory\<T> akzeptiert und einen Task zurückgibt, dürfen Sie die Memory\<T>-Instanz nicht verwenden, nachdem der Task in einen Endzustand übergeht.**</span><span class="sxs-lookup"><span data-stu-id="0f33f-204">**Rule #4: If your method accepts a Memory\<T> and returns a Task, you must not use the Memory\<T> instance after the Task transitions to a terminal state.**</span></span>

<span data-ttu-id="0f33f-205">Dies ist nur die asynchrone Variante von Regel 3.</span><span class="sxs-lookup"><span data-stu-id="0f33f-205">This is just the async variant of Rule #3.</span></span> <span data-ttu-id="0f33f-206">Die `Log`-Methode aus dem früheren Beispiel kann wie folgt geschrieben werden, um dieser Regel zu entsprechen:</span><span class="sxs-lookup"><span data-stu-id="0f33f-206">The `Log` method from the earlier example can be written as follows to comply with this rule:</span></span>

[!code-csharp[task-returning-async](~/samples/snippets/standard/buffers/memory-t/void-returning-async/void-returning-async.cs#1)]

<span data-ttu-id="0f33f-207">Hier bedeutet „Endzustand“, dass der Task in einen abgeschlossenen, fehlerhaften oder abgebrochenen Zustand übergeht.</span><span class="sxs-lookup"><span data-stu-id="0f33f-207">Here, "terminal state" means that the task transitions to a completed, faulted, or canceled state.</span></span> <span data-ttu-id="0f33f-208">Anders ausgedrückt bedeutet „Endzustand“ „alles, was das Warten auf das Auslösen oder Fortsetzen der Ausführung verursachen würde“.</span><span class="sxs-lookup"><span data-stu-id="0f33f-208">In other words, "terminal state" means "anything that would cause await to throw or to continue execution."</span></span>

<span data-ttu-id="0f33f-209">Diese Anleitung gilt für Methoden, die <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask%601> oder einen ähnlichen Typen zurückgeben würden.</span><span class="sxs-lookup"><span data-stu-id="0f33f-209">This guidance applies to methods that return <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask%601>, or any similar type.</span></span>

<span data-ttu-id="0f33f-210">**Regel 5: Wenn Ihr Konstruktor Memory\<T> als Parameter akzeptiert, werden Instanzmethoden auf dem konstruierten Objekt als Consumer der Memory\<T>-Instanz angenommen.**</span><span class="sxs-lookup"><span data-stu-id="0f33f-210">**Rule #5: If your constructor accepts Memory\<T> as a parameter, instance methods on the constructed object are assumed to be consumers of the Memory\<T> instance.**</span></span>

<span data-ttu-id="0f33f-211">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0f33f-211">Consider the following example:</span></span>

```csharp
class OddValueExtractor
{
    public OddValueExtractor(ReadOnlyMemory<int> input);
    public bool TryReadNextOddValue(out int value);
}

void PrintAllOddValues(ReadOnlyMemory<int> input)
{
    var extractor = new OddValueExtractor(input);
    while (extractor.TryReadNextOddValue(out int value))
    {
      Console.WriteLine(value);
    }
}
```

<span data-ttu-id="0f33f-212">Hier akzeptiert der `OddValueExtractor`-Konstruktor `ReadOnlyMemory<int>` als Konstruktorparameter, sodass der Konstruktor selbst ein Consumer der `ReadOnlyMemory<int>`-Instanz ist, und alle Instanzmethoden auf dem zurückgegebenen Wert sind auch Consumer der ursprünglichen `ReadOnlyMemory<int>`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="0f33f-212">Here, the `OddValueExtractor` constructor accepts a `ReadOnlyMemory<int>` as a constructor parameter, so the constructor itself is a consumer of the `ReadOnlyMemory<int>` instance, and all instance methods on the returned value are also consumers of the original `ReadOnlyMemory<int>` instance.</span></span> <span data-ttu-id="0f33f-213">Das bedeutet, dass `TryReadNextOddValue` die `ReadOnlyMemory<int>`-Instanz verbraucht, obwohl die Instanz nicht direkt an die `TryReadNextOddValue`-Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="0f33f-213">This means that `TryReadNextOddValue` consumes the `ReadOnlyMemory<int>` instance, even though the instance isn't passed directly to the `TryReadNextOddValue` method.</span></span>

<span data-ttu-id="0f33f-214">**Regel 6: Wenn Sie eine einstellbare Memory\<T>-typisierte Eigenschaft (oder eine gleichwertige Instanzmethode) für Ihren Typ haben, werden Instanzmethoden auf diesem Objekt als Consumer der Memory\<T>-Instanz angenommen.**</span><span class="sxs-lookup"><span data-stu-id="0f33f-214">**Rule #6: If you have a settable Memory\<T>-typed property (or an equivalent instance method) on your type, instance methods on that object are assumed to be consumers of the Memory\<T> instance.**</span></span>

<span data-ttu-id="0f33f-215">Dies ist eigentlich nur eine Variante der Regel 5.</span><span class="sxs-lookup"><span data-stu-id="0f33f-215">This is really just a variant of Rule #5.</span></span> <span data-ttu-id="0f33f-216">Diese Regel existiert, weil davon ausgegangen wird, dass Property Setter oder gleichwertige Methoden ihre Eingaben erfassen und beibehalten, sodass Instanzmethoden auf demselben Objekt den erfassten Zustand verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0f33f-216">This rule exists because property setters or equivalent methods are assumed to capture and persist their inputs, so instance methods on the same object may utilize the captured state.</span></span>

<span data-ttu-id="0f33f-217">Das folgende Beispiel löst diese Regel aus:</span><span class="sxs-lookup"><span data-stu-id="0f33f-217">The following example triggers this rule:</span></span>

```csharp
class Person
{
    // Settable property.
    public Memory<char> FirstName { get; set; }

    // alternatively, equivalent "setter" method
    public SetFirstName(Memory<char> value);

    // alternatively, a public settable field
    public Memory<char> FirstName;
}
```

<span data-ttu-id="0f33f-218">**Regel 7: Wenn Sie einen IMemoryOwner\<T> Verweis haben, müssen Sie ihn irgendwann verwerfen oder den Besitz übertragen (aber nicht beides).**</span><span class="sxs-lookup"><span data-stu-id="0f33f-218">**Rule #7: If you have an IMemoryOwner\<T> reference, you must at some point dispose of it or transfer its ownership (but not both).**</span></span>

<span data-ttu-id="0f33f-219">Da eine <xref:System.Memory%601>-Instanz entweder durch verwalteten oder nicht verwalteten Speicher gesichert werden kann, muss der Besitzer <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> aufrufen, wenn die Arbeit an der <xref:System.Memory%601>-Instanz abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="0f33f-219">Since a <xref:System.Memory%601> instance may be backed by either managed or unmanaged memory, the owner must call <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> when work performed on the <xref:System.Memory%601> instance is complete.</span></span> <span data-ttu-id="0f33f-220">Alternativ kann der Besitzer die Besitzrechte an der <xref:System.Buffers.IMemoryOwner%601>-Instanz auf eine andere Komponente übertragen, wobei die erwerbende Komponente dann für den Aufruf von <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> zum gegebenen Zeitpunkt (mehr dazu später) verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="0f33f-220">Alternatively, the owner may transfer ownership of the <xref:System.Buffers.IMemoryOwner%601> instance to a different component, at which point the acquiring component becomes responsible for calling <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> at the appropriate time (more on this later).</span></span>

<span data-ttu-id="0f33f-221">Wenn die <xref:System.Buffers.MemoryPool%601.Dispose%2A>-Methode nicht aufgerufen wird, kann dies zu nicht verwalteten Speicherverlusten oder anderen Leistungseinbußen führen.</span><span class="sxs-lookup"><span data-stu-id="0f33f-221">Failure to call the <xref:System.Buffers.MemoryPool%601.Dispose%2A> method may lead to unmanaged memory leaks or other performance degradation.</span></span>

<span data-ttu-id="0f33f-222">Diese Regel gilt auch für Code, der Factorymethoden wie <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType> aufruft.</span><span class="sxs-lookup"><span data-stu-id="0f33f-222">This rule also applies to code that calls factory methods like <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0f33f-223">Der Aufrufer wird zum Besitzer des zurückgegebenen <xref:System.Buffers.IMemoryOwner%601> und ist verantwortlich für das Verwerfen der Instanz, wenn sie beendet ist.</span><span class="sxs-lookup"><span data-stu-id="0f33f-223">The caller becomes the owner of the returned <xref:System.Buffers.IMemoryOwner%601> and is responsible for disposing of the instance when finished.</span></span>

<span data-ttu-id="0f33f-224">**Regel 8: Wenn Sie einen IMemoryOwner\<T>-Parameter in Ihrer API-Oberfläche haben, akzeptieren Sie den Besitz dieser Instanz.**</span><span class="sxs-lookup"><span data-stu-id="0f33f-224">**Rule #8: If you have an IMemoryOwner\<T> parameter in your API surface, you are accepting ownership of that instance.**</span></span>

<span data-ttu-id="0f33f-225">Die Annahme einer Instanz dieses Typs signalisiert, dass Ihre Komponente beabsichtigt, den Besitz dieser Instanz zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="0f33f-225">Accepting an instance of this type signals that your component intends to take ownership of this instance.</span></span> <span data-ttu-id="0f33f-226">Ihre Komponente ist für das ordnungsgemäße Verwerfen gemäß Regel 7 verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="0f33f-226">Your component becomes responsible for proper disposal according to Rule #7.</span></span>

<span data-ttu-id="0f33f-227">Jede Komponente, die den Besitz der <xref:System.Buffers.IMemoryOwner%601>-Instanz auf eine andere Komponente überträgt, sollte diese Instanz nach Abschluss des Methodenaufrufs nicht mehr verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f33f-227">Any component that transfers ownership of the <xref:System.Buffers.IMemoryOwner%601> instance to a different component should no longer use that instance after the method call completes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f33f-228">Wenn Ihr Konstruktor <xref:System.Buffers.IMemoryOwner%601> als Parameter akzeptiert, sollte sein Typ <xref:System.IDisposable> implementieren, und Ihre <xref:System.IDisposable.Dispose%2A>-Methode sollte <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0f33f-228">If your constructor accepts <xref:System.Buffers.IMemoryOwner%601> as a parameter, its type should implement <xref:System.IDisposable>, and your <xref:System.IDisposable.Dispose%2A> method should call <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="0f33f-229">**Regel 9: Wenn Sie eine synchrone P/Invoke-Methode umschließen, sollte Ihre API Span\<T> als Parameter akzeptieren.**</span><span class="sxs-lookup"><span data-stu-id="0f33f-229">**Rule #9: If you're wrapping a synchronous p/invoke method, your API should accept Span\<T> as a parameter.**</span></span>

<span data-ttu-id="0f33f-230">Gemäß Regel 1 ist <xref:System.Span%601> im Allgemeinen der richtige Typ für synchrone APIs.</span><span class="sxs-lookup"><span data-stu-id="0f33f-230">According to Rule #1, <xref:System.Span%601> is generally the correct type to use for synchronous APIs.</span></span> <span data-ttu-id="0f33f-231">Sie können <xref:System.Span%601>-Instanzen über das Schlüsselwort [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) anheften, wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="0f33f-231">You can pin <xref:System.Span%601> instances via the [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) keyword, as in the following example.</span></span>

```csharp
using System.Runtime.InteropServices;

[DllImport(...)]
private static extern unsafe int ExportedMethod(byte* pbData, int cbData);

public unsafe int ManagedWrapper(Span<byte> data)
{
    fixed (byte* pbData = &MemoryMarshal.GetReference(data))
    {
        int retVal = ExportedMethod(pbData, data.Length);

        /* error checking retVal goes here */

        return retVal;
    }
}
```

<span data-ttu-id="0f33f-232">Im vorherigen Beispiel kann `pbData` Null sein, wenn beispielsweise der Eingangs-Span-Wert leer ist.</span><span class="sxs-lookup"><span data-stu-id="0f33f-232">In the previous example, `pbData` can be null if, for example, the input span is empty.</span></span> <span data-ttu-id="0f33f-233">Wenn die exportierte Methode unbedingt erfordert, dass `pbData` nicht Null ist, auch wenn `cbData` 0 ist, kann die Methode wie folgt implementiert werden:</span><span class="sxs-lookup"><span data-stu-id="0f33f-233">If the exported method absolutely requires that `pbData` be non-null, even if `cbData` is 0, the method can be implemented as follows:</span></span>

```csharp
public unsafe int ManagedWrapper(Span<byte> data)
{
    fixed (byte* pbData = &MemoryMarshal.GetReference(data))
    {
        byte dummy = 0;
        int retVal = ExportedMethod((pbData != null) ? pbData : &dummy, data.Length);

        /* error checking retVal goes here */

        return retVal;
    }
}
```

<span data-ttu-id="0f33f-234">**Regel 10: Wenn Sie eine synchrone P/Invoke-Methode umschließen, sollte Ihre API Memory\<T> als Parameter akzeptieren.**</span><span class="sxs-lookup"><span data-stu-id="0f33f-234">**Rule #10: If you're wrapping an asynchronous p/invoke method, your API should accept Memory\<T> as a parameter.**</span></span>

<span data-ttu-id="0f33f-235">Da Sie das Schlüsselwort [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) nicht über asynchrone Vorgänge hinweg verwenden können, verwenden Sie die <xref:System.Memory%601.Pin%2A?displayProperty=nameWithType>-Methode, um <xref:System.Memory%601>-Instanzen anzuheften, unabhängig von der Art des zusammenhängenden Speichers, den die Instanz repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="0f33f-235">Since you cannot use the [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) keyword across asynchronous operations, you use the <xref:System.Memory%601.Pin%2A?displayProperty=nameWithType> method to pin <xref:System.Memory%601> instances, regardless of the kind of contiguous memory the instance represents.</span></span> <span data-ttu-id="0f33f-236">Das folgende Beispiel zeigt, wie man diese API verwendet, um einen asynchronen P/Invoke-Aufruf durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="0f33f-236">The following example shows how to use this API to perform an asynchronous p/invoke call.</span></span>

```csharp
using System.Runtime.InteropServices;

[UnmanagedFunctionPointer(...)]
private delegate void OnCompletedCallback(IntPtr state, int result);

[DllImport(...)]
private static extern unsafe int ExportedAsyncMethod(byte* pbData, int cbData, IntPtr pState, IntPtr lpfnOnCompletedCallback);

private static readonly IntPtr _callbackPtr = GetCompletionCallbackPointer();

public unsafe Task<int> ManagedWrapperAsync(Memory<byte> data)
{
    // setup
    var tcs = new TaskCompletionSource<int>();
    var state = new MyCompletedCallbackState
    {
        Tcs = tcs
    };
    var pState = (IntPtr)GCHandle.Alloc(state);

    var memoryHandle = data.Pin();
    state.MemoryHandle = memoryHandle;

    // make the call
    int result;
    try
    {
        result = ExportedAsyncMethod((byte*)memoryHandle.Pointer, data.Length, pState, _callbackPtr);
    }
    catch
    {
        ((GCHandle)pState).Free(); // cleanup since callback won't be invoked
        memoryHandle.Dispose();
        throw;
    }

    if (result != PENDING)
    {
        // Operation completed synchronously; invoke callback manually
        // for result processing and cleanup.
        MyCompletedCallbackImplementation(pState, result);
    }

    return tcs.Task;
}

private static void MyCompletedCallbackImplementation(IntPtr state, int result)
{
    GCHandle handle = (GCHandle)state;
    var actualState = (MyCompletedCallbackState)(handle.Target);
    handle.Free();
    actualState.MemoryHandle.Dispose();

    /* error checking result goes here */

    if (error)
    {
        actualState.Tcs.SetException(...);
    }
    else
    {
        actualState.Tcs.SetResult(result);
    }
}

private static IntPtr GetCompletionCallbackPointer()
{
    OnCompletedCallback callback = MyCompletedCallbackImplementation;
    GCHandle.Alloc(callback); // keep alive for lifetime of application
    return Marshal.GetFunctionPointerForDelegate(callback);
}

private class MyCompletedCallbackState
{
    public TaskCompletionSource<int> Tcs;
    public MemoryHandle MemoryHandle;
}
```

## <a name="see-also"></a><span data-ttu-id="0f33f-237">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f33f-237">See also</span></span>

- <xref:System.Memory%601?displayProperty=nameWithType>
- <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>
- <xref:System.Span%601?displayProperty=nameWithType>
