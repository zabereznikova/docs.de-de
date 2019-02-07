---
title: Neuerungen in .NET Core 3.0
description: Informationen zu den neuen Features in .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/31/2018
ms.openlocfilehash: baaa2676865c475e331ec889e7b10ae326b552fa
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675087"
---
# <a name="whats-new-in-net-core-30-preview-2"></a><span data-ttu-id="dab78-103">Neuerungen in .NET Core 3.0 (Vorschauversion 2)</span><span class="sxs-lookup"><span data-stu-id="dab78-103">What's new in .NET Core 3.0 (Preview 2)</span></span>

<span data-ttu-id="dab78-104">In diesem Artikel werden Neuerungen in .NET Core 3.0 (Vorschauversion 2) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dab78-104">This article describes what is new in .NET Core 3.0 (preview 2).</span></span> <span data-ttu-id="dab78-105">Eine der wichtigsten Verbesserungen ist die Unterstützung für Windows-Desktopanwendungen (nur Windows).</span><span class="sxs-lookup"><span data-stu-id="dab78-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="dab78-106">Mit der .NET Core 3.0 SDK-Komponente Windows Desktop können Sie Ihre Windows Forms- und WPF-Anwendungen (Windows Presentation Foundation) portieren.</span><span class="sxs-lookup"><span data-stu-id="dab78-106">By utilizing a .NET Core 3.0 SDK component called Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="dab78-107">Die Windows Desktop-Komponente wird ausdrücklich nur für Windows unterstützt und ist nur unter Windows enthalten.</span><span class="sxs-lookup"><span data-stu-id="dab78-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="dab78-108">Weitere Informationen finden Sie unten im Abschnitt [Windows Desktop](#windows-desktop).</span><span class="sxs-lookup"><span data-stu-id="dab78-108">For more information, see the section [Windows desktop](#windows-desktop) below.</span></span>

<span data-ttu-id="dab78-109">.NET Core 3.0 bietet Unterstützung für C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="dab78-109">.NET Core 3.0 adds support for C# 8.0.</span></span>

<span data-ttu-id="dab78-110">[Sie können die Vorschauversion 2 von .NET Core 3.0 jetzt für Windows, Mac und Linux herunterladen und sofort starten.](https://aka.ms/netcore3download)</span><span class="sxs-lookup"><span data-stu-id="dab78-110">[Download and get started with .NET Core 3 Preview 2](https://aka.ms/netcore3download) right now on Windows, Mac and Linux.</span></span> <span data-ttu-id="dab78-111">Alle Details zu diesem Release finden Sie in den [Versionshinweisen zur Vorschauversion 2 von .NET Core 3.0](https://aka.ms/netcore3releasenotes).</span><span class="sxs-lookup"><span data-stu-id="dab78-111">You can see complete details of the release in the [.NET Core 3 Preview 2 release notes](https://aka.ms/netcore3releasenotes).</span></span>

<span data-ttu-id="dab78-112">Weitere Informationen zu Neuerungen, die in Vorschauversion 1 eingeführt wurden, finden Sie in der [Ankündigung der Vorschauversion 1 von .NET Core 3.0](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/).</span><span class="sxs-lookup"><span data-stu-id="dab78-112">For more information about what was released with Preview 1, see the [.NET Core 3.0 Preview 1 announcement](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/).</span></span>

<span data-ttu-id="dab78-113">Weitere Informationen zu Neuerungen, die in Vorschauversion 2 eingeführt wurden, finden Sie in der [Ankündigung der Vorschauversion 2 von .NET Core 3.0]().</span><span class="sxs-lookup"><span data-stu-id="dab78-113">For more information about what was released with Preview 2, see the [.NET Core 3.0 Preview 1 announcement]().</span></span>

## <a name="c-8"></a><span data-ttu-id="dab78-114">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="dab78-114">C# 8</span></span>

<span data-ttu-id="dab78-115">.NET Core 3.0 unterstützt C# 8.0. Ab der Vorschauversion 2 von NET Core 3.0 werden neue Features unterstützt, die weiter unten aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="dab78-115">.NET Core 3.0 supports C# 8, and as of .NET Core 3.0 Preview 2, supports these new features.</span></span> <span data-ttu-id="dab78-116">Weitere Informationen zu Features von C# 8.0 finden Sie in den folgenden Blogbeiträgen:</span><span class="sxs-lookup"><span data-stu-id="dab78-116">For more information about C# 8.0 features, see the following blog posts:</span></span>

- [<span data-ttu-id="dab78-117">Do more with patterns in C# 8.0 (Effektivere Verwendung von Mustern in C# 8.0)</span><span class="sxs-lookup"><span data-stu-id="dab78-117">Do more with patterns in C# 8.0</span></span>](https://blogs.msdn.microsoft.com/dotnet/2019/01/24/do-more-with-patterns-in-c-8-0/)
- [<span data-ttu-id="dab78-118">Take C# 8.0 for a spin (Neuerungen in C# 8.0)</span><span class="sxs-lookup"><span data-stu-id="dab78-118">Take C# 8.0 for a spin</span></span>](https://blogs.msdn.microsoft.com/dotnet/2018/12/05/take-c-8-0-for-a-spin/)
- [<span data-ttu-id="dab78-119">Building C# 8.0 (Neue Features in C# 8.0)</span><span class="sxs-lookup"><span data-stu-id="dab78-119">Building C# 8.0</span></span>](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/)


### <a name="ranges-and-indices"></a><span data-ttu-id="dab78-120">Bereiche und Indizes</span><span class="sxs-lookup"><span data-stu-id="dab78-120">Ranges and indices</span></span>

<span data-ttu-id="dab78-121">Der neue `Index`-Typ kann für die Indizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dab78-121">The new `Index` type can be used for indexing.</span></span> <span data-ttu-id="dab78-122">Sie können einen aus einem `int` erstellen, der vom Anfang aus zählt, oder mit einem Präfix-`^`-Operator (C#), der vom Ende aus zählt:</span><span class="sxs-lookup"><span data-stu-id="dab78-122">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="dab78-123">Es gibt auch einen `Range`-Typ, der aus zwei `Index`-Werten besteht, einen für den Anfang und einen für das Ende, und mit einem `x..y`-Bereichsausdruck (C#) geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="dab78-123">There is also a `Range` type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="dab78-124">Sie können dann mit einem `Range` indizieren, um einen Slice zu erzeugen:</span><span class="sxs-lookup"><span data-stu-id="dab78-124">You can then index with a `Range` in order to produce a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

### <a name="async-streams"></a><span data-ttu-id="dab78-125">Asynchrone Datenströme</span><span class="sxs-lookup"><span data-stu-id="dab78-125">Async streams</span></span>

<span data-ttu-id="dab78-126">Die `IAsyncEnumerable<T>`-Typ ist eine neue asynchrone Version von `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="dab78-126">The `IAsyncEnumerable<T>` type is a new asynchronous version of `IEnumerable<T>`.</span></span> <span data-ttu-id="dab78-127">In C# 8.0 können Sie `await foreach` zur Verarbeitung der `IAsyncEnumerable<T>`-Elemente nutzen und anschließend `yield return` zum Erstellen von Elementen verwenden.</span><span class="sxs-lookup"><span data-stu-id="dab78-127">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="dab78-128">Das folgende Beispiel zeigt sowohl die Produktion als auch die Nutzung von asynchronen Datenströmen.</span><span class="sxs-lookup"><span data-stu-id="dab78-128">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="dab78-129">Die `foreach`-Anweisung ist asynchron und verwendet `yield return`, um einen asynchronen Datenstrom für Anrufer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dab78-129">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="dab78-130">Dieses Muster (mit `yield return`) ist das empfohlene Modell zum Erstellen von asynchronen Datenströmen.</span><span class="sxs-lookup"><span data-stu-id="dab78-130">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

<span data-ttu-id="dab78-131">Zusätzlich zu `await foreach` können Sie auch asynchrone Iteratoren erstellen, z.B. einen Iterator, der `IAsyncEnumerable/IAsyncEnumerator` zurückgibt, in den Sie sowohl `await` als auch `yield` einfügen können.</span><span class="sxs-lookup"><span data-stu-id="dab78-131">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="dab78-132">Für Objekte, die gelöscht werden müssen, können Sie `IAsyncDisposable` verwenden, das von verschiedenen BCL-Typen implementiert wird, wie beispielsweise `Stream` und `Timer`.</span><span class="sxs-lookup"><span data-stu-id="dab78-132">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

>[!NOTE]
><span data-ttu-id="dab78-133">Sie benötigen zur Nutzung asynchroner Datenströme die Vorschauversion 2 von .NET Core 3.0, wenn Sie mit der Vorschauversion 2 von Visual Studio 2019 oder mit der aktuellen Vorschauversion der [C#-Erweiterung für Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/releases/tag/v1.18.0-beta5) entwickeln möchten.</span><span class="sxs-lookup"><span data-stu-id="dab78-133">You need .NET Core 3.0 Preview 2 to use async streams if you want to develop with either Visual Studio 2019 Preview 2 or the latest preview of the [C# extension for Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/releases/tag/v1.18.0-beta5).</span></span> <span data-ttu-id="dab78-134">Wenn Sie die Vorschauversion 2 von .NET Core 3.0 über die Befehlszeile nutzen, entstehen keine Probleme.</span><span class="sxs-lookup"><span data-stu-id="dab78-134">If you are using .NET Core 3.0 Preview 2 at the command line, then everything will work as expected.</span></span>

### <a name="using-declarations"></a><span data-ttu-id="dab78-135">using-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="dab78-135">Using Declarations</span></span>

<span data-ttu-id="dab78-136">*using-Deklarationen* sind ein neues Feature, mit dem sichergestellt werden kann, dass ein Objekt wie erwartet verworfen wird.</span><span class="sxs-lookup"><span data-stu-id="dab78-136">*Using declarations* are a new way to ensure your object is properly disposed.</span></span> <span data-ttu-id="dab78-137">Mit einer *using-Deklaration* wird für das Objekt Speicher belegt, solange es sich im Geltungsbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="dab78-137">A *using declaration* keeps the object alive while it is still in scope.</span></span> <span data-ttu-id="dab78-138">Verlässt das Objekt diesen Bereich, wird es automatisch verworfen.</span><span class="sxs-lookup"><span data-stu-id="dab78-138">Once the object becomes out of scope, it is automatically disposed.</span></span> <span data-ttu-id="dab78-139">Dadurch müssen weniger geschachtelte *using-Anweisungen* verwendet werden, was zu übersichtlicherem Code führt.</span><span class="sxs-lookup"><span data-stu-id="dab78-139">This will reduce nested *using statements* and make your code cleaner.</span></span>

```csharp
static void Main(string[] args)
{
    using var options = Parse(args);
    if (options["verbose"]) { WriteLine("Logging..."); }

} // options disposed here
```

### <a name="switch-expressions"></a><span data-ttu-id="dab78-140">switch-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="dab78-140">Switch Expressions</span></span>

<span data-ttu-id="dab78-141">*switch-Ausdrücke* stellen eine übersichtlichere Variante von *switch-Anweisungen* dar. Da es sich aber um Ausdrücke handelt, wird ein Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dab78-141">*Switch expressions* are a cleaner way of doing a *switch statement* but, since it's an expression, returns a value.</span></span> <span data-ttu-id="dab78-142">*switch-Ausdrücke* lassen sich außerdem uneingeschränkt mit Musterabgleichen verwenden und nutzen das Ausschussmuster `_` zur Darstellung des `default`-Werts.</span><span class="sxs-lookup"><span data-stu-id="dab78-142">*Switch expressions* are also fully integrated with pattern matching, and use the discard pattern, `_`, to represent the `default` value.</span></span>

<span data-ttu-id="dab78-143">Die Syntax von *switch-Ausdrücken* wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="dab78-143">You can see the syntax for *switch expressions* in the following example:</span></span>

```csharp
static string Display(object o) => o switch
{
    Point { X: 0, Y: 0 }         => "origin",
    Point { X: var x, Y: var y } => $"({x}, {y})",
    _                            => "unknown"
};
```

<span data-ttu-id="dab78-144">In diesem Beispiel werden zwei Muster verwendet.</span><span class="sxs-lookup"><span data-stu-id="dab78-144">There are two patterns at play in this example.</span></span> <span data-ttu-id="dab78-145">`o` wird für `Point` zuerst mit dem *Typmuster* und anschließend mit dem *Eigenschaftenmuster* innerhalb der *{geschweiften Klammern}* abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="dab78-145">`o` first matches with the `Point` *type pattern* and then with the *property pattern* inside the *{curly braces}*.</span></span> <span data-ttu-id="dab78-146">`_` beschreibt das `discard pattern`, das mit `default` für *switch-Anweisungen* identisch ist.</span><span class="sxs-lookup"><span data-stu-id="dab78-146">The `_` describes the `discard pattern`, which is the same as `default` for *switch statements*.</span></span>

<span data-ttu-id="dab78-147">Mit Mustern können Sie anstelle von prozeduralem Code, in dem Tests für eine Absicht implementiert werden, deklarativen Code schreiben, der diese Absicht direkt erfasst.</span><span class="sxs-lookup"><span data-stu-id="dab78-147">Patterns enable you to write declarative code that captures your intent instead of procedural code that implements tests for it.</span></span> <span data-ttu-id="dab78-148">Die Verantwortung zur Implementierung des prozeduralen Codes wird so dem Compiler übertragen, der diese Aufgabe immer fehlerfrei ausführt.</span><span class="sxs-lookup"><span data-stu-id="dab78-148">The compiler becomes responsible for implementing that boring procedural code and is guaranteed to always do it correctly.</span></span>

<span data-ttu-id="dab78-149">Es gibt dennoch Fälle, in denen *switch-Anweisungen* weiterhin besser geeignet sind als *switch-Ausdrücke*, und Muster können mit beiden Syntaxstilen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dab78-149">There will still be cases where *switch statements* will be a better choice than *switch expressions* and patterns can be used with both syntax styles.</span></span>

<span data-ttu-id="dab78-150">Weitere Informationen finden Sie unter [Do more with patterns in C# 8.0 (Effektivere Verwendung von Mustern in C# 8.0)](https://blogs.msdn.microsoft.com/dotnet/2019/01/24/do-more-with-patterns-in-c-8-0/).</span><span class="sxs-lookup"><span data-stu-id="dab78-150">For more information, see [Do more with patterns in C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2019/01/24/do-more-with-patterns-in-c-8-0/).</span></span>

## <a name="ieee-floating-point-improvements"></a><span data-ttu-id="dab78-151">Verbesserungen bei Gleitkommazahlen gemäß IEEE-Spezifikation</span><span class="sxs-lookup"><span data-stu-id="dab78-151">IEEE Floating-point improvements</span></span>

<span data-ttu-id="dab78-152">APIs für Gleitkommazahlen werden aktuell an die [Revision des Standards IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision) angepasst.</span><span class="sxs-lookup"><span data-stu-id="dab78-152">Floating point APIs are in the process of being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="dab78-153">Ziel dieser Änderungen ist es, alle „erforderlichen“ Operationen verfügbar zu machen und sicherzustellen, dass sie mit dem in der IEEE-Spezifikation beschriebenen Verhalten kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="dab78-153">The goal of these changes is to expose all "required" operations and ensure that they are behaviorally compliant with the IEEE spec.</span></span>

<span data-ttu-id="dab78-154">Korrekturen bei der Analyse und Formatierung:</span><span class="sxs-lookup"><span data-stu-id="dab78-154">Parsing and formatting fixes:</span></span>

* <span data-ttu-id="dab78-155">Eingaben mit beliebiger Länge werden richtig analysiert und gerundet.</span><span class="sxs-lookup"><span data-stu-id="dab78-155">Correctly parse and round inputs of any length.</span></span>
* <span data-ttu-id="dab78-156">Die negative Null wird richtig analysiert und formatiert.</span><span class="sxs-lookup"><span data-stu-id="dab78-156">Correctly parse and format negative zero.</span></span>
* <span data-ttu-id="dab78-157">Unendlichkeits- und NaN-Werte werden mithilfe einer Überprüfung, bei der nicht zwischen Groß-/Kleinbuchstaben unterschieden wird, richtig analysiert. Außerdem ist, falls erforderlich, optional das vorangestellte `+`-Zeichen zulässig.</span><span class="sxs-lookup"><span data-stu-id="dab78-157">Correctly parse Infinity and NaN by performing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="dab78-158">In den neuen Mathematik-APIs sind folgende Operationen enthalten:</span><span class="sxs-lookup"><span data-stu-id="dab78-158">New Math APIs have:</span></span>

* `BitIncrement/BitDecrement`\
<span data-ttu-id="dab78-159">entspricht den IEEE-Operationen `nextUp` und `nextDown`.</span><span class="sxs-lookup"><span data-stu-id="dab78-159">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="dab78-160">Diese geben jeweils die kleinste Gleitkommazahl zurück, die größer oder kleiner als der Eingabewert ist.</span><span class="sxs-lookup"><span data-stu-id="dab78-160">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="dab78-161">`Math.BitIncrement(0.0)` gibt beispielsweise `double.Epsilon` zurück.</span><span class="sxs-lookup"><span data-stu-id="dab78-161">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

* `MaxMagnitude/MinMagnitude`\
<span data-ttu-id="dab78-162">entspricht den IEEE-Operationen `maxNumMag` und `minNumMag`. Diese geben für zwei Eingabewerte jeweils den Wert zurück, für den ein größerer oder kleinerer Absolutbetrag ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="dab78-162">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="dab78-163">`Math.MaxMagnitude(2.0, -3.0)` gibt beispielsweise `-3.0` zurück.</span><span class="sxs-lookup"><span data-stu-id="dab78-163">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

* `ILogB`\
<span data-ttu-id="dab78-164">entspricht der IEEE-Operation `logB`, die einen integralen Wert zurückgibt. Der Rückgabewert ist der integrale Wert des Logarithmus zur Basis 2 des Eingabeparameters.</span><span class="sxs-lookup"><span data-stu-id="dab78-164">Corresponds to the `logB` IEEE operation which returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="dab78-165">Diese Operation entspricht im Wesentlichen `floor(log2(x))`, jedoch ist der Rundungsfehler minimal.</span><span class="sxs-lookup"><span data-stu-id="dab78-165">This is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

* `ScaleB`\
<span data-ttu-id="dab78-166">entspricht der IEEE-Operation `scaleB`, der ein integraler Wert übergeben wird. Zurückgegeben wird im Wesentlichen `x * pow(2, n)`, jedoch ist der Rundungsfehler minimal.</span><span class="sxs-lookup"><span data-stu-id="dab78-166">Corresponds to the `scaleB` IEEE operation which takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

* `Log2`\
<span data-ttu-id="dab78-167">entspricht der IEEE-Operation `log2`, die den Logarithmus zur Basis 2 zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="dab78-167">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="dab78-168">Diese Operation minimiert den Rundungsfehler.</span><span class="sxs-lookup"><span data-stu-id="dab78-168">It minimizes rounding error.</span></span>

* `FusedMultiplyAdd`\
<span data-ttu-id="dab78-169">entspricht der IEEE-Operation `fma`, die eine Fused-Multiply-Add-Operation durchführt.</span><span class="sxs-lookup"><span data-stu-id="dab78-169">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="dab78-170">Dabei wird `(x * y) + z` als einzelne Operation ausgeführt, wodurch der Rundungsfehler minimiert wird.</span><span class="sxs-lookup"><span data-stu-id="dab78-170">That is, it does `(x * y) + z` as a single operation, there-by minimizing the rounding error.</span></span> <span data-ttu-id="dab78-171">`FusedMultiplyAdd(1e308, 2.0, -1e308)` gibt beispielsweise `1e308` zurück.</span><span class="sxs-lookup"><span data-stu-id="dab78-171">An example would be `FusedMultiplyAdd(1e308, 2.0, -1e308)` which returns `1e308`.</span></span> <span data-ttu-id="dab78-172">Die reguläre Operation `(1e308 * 2.0) - 1e308` gibt `double.PositiveInfinity` zurück.</span><span class="sxs-lookup"><span data-stu-id="dab78-172">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

* `CopySign`\
<span data-ttu-id="dab78-173">entspricht der IEEE-Operation `copySign`. Diese gibt den Wert von `x` mit dem Vorzeichen von `y` zurück.</span><span class="sxs-lookup"><span data-stu-id="dab78-173">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

## <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="dab78-174">Intrinsische .NET-plattformabhängige Funktionen</span><span class="sxs-lookup"><span data-stu-id="dab78-174">.NET Platform Dependent Intrinsics</span></span>

<span data-ttu-id="dab78-175">Mit neuen APIs kann auf bestimmte leistungsorientierte CPU-Anweisungen wie **SIMD** oder **Bit Manipulation Instruction Sets** zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="dab78-175">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="dab78-176">Diese Anweisungen können in bestimmten Szenarios wie der effizienten parallelen Datenverarbeitung zu deutlichen Leistungssteigerungen führen.</span><span class="sxs-lookup"><span data-stu-id="dab78-176">These instructions can help achieve big performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span> <span data-ttu-id="dab78-177">Diese API-Operationen können nicht nur in eigenen Programmen verwendet werden, sondern werden nun auch von .NET-Bibliotheken zur Leistungssteigerung eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="dab78-177">In addition to exposing the APIs for your programs to use, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="dab78-178">In den folgenden CoreCLR-PRs werden einige intrinsische Funktionen und deren Implementierung oder Verwendung vorgestellt:</span><span class="sxs-lookup"><span data-stu-id="dab78-178">The following CoreCLR PRs demonstrate a few of the intrinsics, either via implementation or use:</span></span>

* [<span data-ttu-id="dab78-179">Implement simple SSE2 hardware intrinsics (Implementieren einfacher intrinsischer SSE2-Hardwarefunktionen)</span><span class="sxs-lookup"><span data-stu-id="dab78-179">Implement simple SSE2 hardware intrinsics</span></span>](https://github.com/dotnet/coreclr/pull/15585)
* [<span data-ttu-id="dab78-180">Implement the SSE hardware intrinsics (Implementieren intrinsischer SSE2-Hardwarefunktionen)</span><span class="sxs-lookup"><span data-stu-id="dab78-180">Implement the SSE hardware intrinsics</span></span>](https://github.com/dotnet/coreclr/pull/15538)
* [<span data-ttu-id="dab78-181">Arm64 Base HW Intrinsics (Intrinsische Base-Hardwarefunktionen für ARM64)</span><span class="sxs-lookup"><span data-stu-id="dab78-181">Arm64 Base HW Intrinsics</span></span>](https://github.com/dotnet/coreclr/pull/16822)
* [<span data-ttu-id="dab78-182">Use TZCNT and LZCNT for Locate{First|Last}Found{Byte|Char} (Verwenden von TZCNT und LZCNT für Locate{First|Last}Found{Byte|Char})</span><span class="sxs-lookup"><span data-stu-id="dab78-182">Use TZCNT and LZCNT for Locate{First|Last}Found{Byte|Char}</span></span>](https://github.com/dotnet/coreclr/pull/21073)

<span data-ttu-id="dab78-183">Weitere Informationen finden Sie unter [.NET Platform Dependent Intrinsics (Intrinsische .NET-plattformabhängige Funktionen)](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md). In diesem Artikel wird eine Strategie zum Definieren von intrinsischen Funktionen für eine bestimmte Hardwareinfrastruktur vorgestellt. Dadurch können Microsoft, Chiphersteller oder andere Unternehmen oder Personen Hardware- bzw. Chip-APIs entwerfen, die in .NET-Code verfügbar gemacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="dab78-183">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md), which defines an approach for defining this hardware infrastructure, allowing Microsoft, chip vendors, or any other company or individual to define hardware/chip APIs that should be exposed to .NET code.</span></span>

## <a name="default-executables"></a><span data-ttu-id="dab78-184">Standardmäßig ausführbare Dateien</span><span class="sxs-lookup"><span data-stu-id="dab78-184">Default executables</span></span>

<span data-ttu-id="dab78-185">.NET Core erstellt die [frameworkabhängigen ausführbaren Dateien](../deploying/index.md#framework-dependent-executables-fde) jetzt standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="dab78-185">.NET Core will now build [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="dab78-186">Dies ist neu für Anwendungen, die eine global installierte Version von .NET Core verwenden.</span><span class="sxs-lookup"><span data-stu-id="dab78-186">This is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="dab78-187">Bis jetzt produzierten nur [eigenständige Bereitstellungen](../deploying/index.md#self-contained-deployments-scd) eine ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="dab78-187">Until now, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="dab78-188">Während `dotnet build` oder `dotnet publish` wird eine ausführbare Datei erstellt, die der Umgebung und Plattform des von Ihnen verwendeten SDKs entspricht.</span><span class="sxs-lookup"><span data-stu-id="dab78-188">During `dotnet build` or `dotnet publish`, an executable is created provided that matches the environment and platform of the SDK you are using.</span></span> <span data-ttu-id="dab78-189">Diese ausführbaren Dateien bieten Ihnen die gleichen Möglichkeiten wie andere native ausführbare Dateien, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="dab78-189">You can expect the same things with these executables as you would other native executables, such as:</span></span>

* <span data-ttu-id="dab78-190">Sie können die ausführbare Datei doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="dab78-190">You can double-click on the executable.</span></span>
* <span data-ttu-id="dab78-191">Sie können die Anwendung direkt aus einer Eingabeaufforderung starten, z.B. `myapp.exe` unter Windows und `./myapp` unter Linux und MacOS.</span><span class="sxs-lookup"><span data-stu-id="dab78-191">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="build-copies-dependencies"></a><span data-ttu-id="dab78-192">Build kopiert Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="dab78-192">Build copies dependencies</span></span>

<span data-ttu-id="dab78-193">`dotnet build` kopiert jetzt NuGet-Abhängigkeiten für Ihre Anwendung aus dem NuGet-Cache in den Buildausgabeordner.</span><span class="sxs-lookup"><span data-stu-id="dab78-193">`dotnet build` now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="dab78-194">Bisher wurde Abhängigkeiten nur als Teil von `dotnet publish` kopiert.</span><span class="sxs-lookup"><span data-stu-id="dab78-194">Previously, dependencies were only copied as part of `dotnet publish`.</span></span> 

<span data-ttu-id="dab78-195">Es gibt einige Vorgänge, wie das Verlinken und das Veröffentlichen von Razor-Seiten, die noch veröffentlicht werden müssen.</span><span class="sxs-lookup"><span data-stu-id="dab78-195">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>


## <a name="local-dotnet-tools"></a><span data-ttu-id="dab78-196">Lokale dotnet-Tools</span><span class="sxs-lookup"><span data-stu-id="dab78-196">Local dotnet tools</span></span>

>[!WARNING]
><span data-ttu-id="dab78-197">Nach der Vorschauversion 1 von .NET Core 3.0 wurde in Vorschauversion 2 eine Änderung an den lokalen .NET Core-Tools vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="dab78-197">There was a change in .NET Core Local Tools between .NET Core 3.0 Preview 1 and .NET Core 3.0 Preview 2.</span></span>  <span data-ttu-id="dab78-198">Wenn Sie die lokalen Tools in Vorschauversion 1 mit einem Befehl wie `dotnet tool restore` oder `dotnet tool install` verwenden haben, müssen Sie den Cacheordner für die lokalen Tools löschen, da diese andernfalls in Vorschauversion 2 nicht funktionieren.</span><span class="sxs-lookup"><span data-stu-id="dab78-198">If you tried out local tools in Preview 1 by running a command like `dotnet tool restore` or `dotnet tool install`, you need to delete your local tools cache folder before local tools will work correctly in Preview 2.</span></span> <span data-ttu-id="dab78-199">Je nach Betriebssystem werden die Ordnerpfade wie folgt gelöscht:</span><span class="sxs-lookup"><span data-stu-id="dab78-199">This folder is located at:</span></span>
>
><span data-ttu-id="dab78-200">Mac und Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="dab78-200">On mac, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
><span data-ttu-id="dab78-201">Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="dab78-201">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>
>
><span data-ttu-id="dab78-202">Wenn Sie diesen Ordner nicht löschen, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dab78-202">If you do not delete this folder, you will receive an error.</span></span>

<span data-ttu-id="dab78-203">.NET Core 2.1 unterstützt globale Tools, .NET Core 3.0 verfügt jetzt über lokale Tools.</span><span class="sxs-lookup"><span data-stu-id="dab78-203">While .NET Core 2.1 supported global tools, .NET Core 3.0 now has local tools.</span></span> <span data-ttu-id="dab78-204">Lokale Tools ähneln globalen Tools, sind aber mit einem bestimmten Speicherort auf dem Datenträger verknüpft.</span><span class="sxs-lookup"><span data-stu-id="dab78-204">Local tools are similar to global tools but are associated with a particular location on disk.</span></span> <span data-ttu-id="dab78-205">Dies ermöglicht die Bereitstellung von Tools für einzelne Projekte und Repositorys.</span><span class="sxs-lookup"><span data-stu-id="dab78-205">This enables per-project and per-repository tooling.</span></span> <span data-ttu-id="dab78-206">Jedes lokal installierte Tool ist nicht global verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dab78-206">Any tool installed locally isn't available globally.</span></span> <span data-ttu-id="dab78-207">Tools werden als NuGet-Pakete verteilt.</span><span class="sxs-lookup"><span data-stu-id="dab78-207">Tools are distributed as NuGet packages.</span></span>

<span data-ttu-id="dab78-208">Lokale Tools basieren auf einer Manifestdatei `dotnet-tools.json` in Ihrem aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="dab78-208">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="dab78-209">In dieser Manifestdatei werden die Tools festgelegt, die im Verzeichnis und in den Unterverzeichnissen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="dab78-209">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="dab78-210">Durch die Erstellung dieser Manifestdatei im Stammverzeichnis Ihres Repositorys stellen Sie sicher, dass jeder, der Ihren Code klont, die Tools wiederherstellen und verwenden kann, die für eine erfolgreiche Arbeit mit Ihrem Code erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="dab78-210">By creating this manifest file at the root of your repository, you ensure anyone cloning your code can restore and use the tools that are needed to successfully work with your code.</span></span>

<span data-ttu-id="dab78-211">Mit dem folgenden Befehl können Sie eine `dotnet-tools.json`-Manifestdatei erstellen:</span><span class="sxs-lookup"><span data-stu-id="dab78-211">To create a `dotnet-tools.json` manifest file, use:</span></span>

```console
dotnet new tool-manifest
```

<span data-ttu-id="dab78-212">Wenn Sie dem lokalen Manifest ein neues Tool hinzufügen möchten, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="dab78-212">Add a new tool to the local manifest with:</span></span>

```console
dotnet tool install <packageId>
```

<span data-ttu-id="dab78-213">Mit dem folgenden Befehl können Sie außerdem die Tools im lokalen Manifest auflisten:</span><span class="sxs-lookup"><span data-stu-id="dab78-213">You can also list the tools in the local manifest with:</span></span>

```console
dotnet tool list
```

<span data-ttu-id="dab78-214">Wenn Sie die global installierten Tools anzeigen möchten, verwenden Sie folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="dab78-214">To see what tools are installed globally, use:</span></span>

```console
dotnet tool list -g
```

<span data-ttu-id="dab78-215">Wenn die Manifestdatei für die lokalen Tools verfügbar ist, die im Manifest festgelegten Tools jedoch nicht installiert wurden, verwenden Sie den folgenden Befehl, um sie automatisch herunterzuladen und zu installieren:</span><span class="sxs-lookup"><span data-stu-id="dab78-215">When the local tools manifest file is available, but the tools defined in the manifest have not been installed, use the following command to automatically download and install those tools:</span></span>

```console
dotnet tool restore
```

<span data-ttu-id="dab78-216">Führen Sie ein lokales Tool mit dem folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="dab78-216">Run a local tool with the following command:</span></span>

```console
dotnet tool run <tool-command-name>
```

<span data-ttu-id="dab78-217">Wenn ein lokales Tool ausgeführt wird, sucht dotnet nach einer Manifestdatei in der aktuellen Verzeichnisstruktur.</span><span class="sxs-lookup"><span data-stu-id="dab78-217">When a local tool is run, dotnet searches for a manifest up the current directory structure.</span></span> <span data-ttu-id="dab78-218">Wenn eine Manifestdatei für das Tool gefunden wurde, wird diese nach dem erforderlichen Tool durchsucht.</span><span class="sxs-lookup"><span data-stu-id="dab78-218">When a tool manifest file is found, it is searched for the requested tool.</span></span> <span data-ttu-id="dab78-219">Wenn das Tool im Manifest, aber nicht im Cache gefunden wird, wird dem Benutzer eine Fehlermeldung angezeigt. Dieser muss dann `dotnet tool restore` ausführen.</span><span class="sxs-lookup"><span data-stu-id="dab78-219">If the tool is found in the manifest, but not the cache, the user receives an error and needs to run `dotnet tool restore`.</span></span>

<span data-ttu-id="dab78-220">Wenn Sie ein Tool aus der Manifestdatei für die lokalen Tools entfernen möchten, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="dab78-220">To remove a tool from the local tool manifest file, run the following command:</span></span>

```console
dotnet tool uninstall <packageId>
```

<span data-ttu-id="dab78-221">Die Manifestdatei des Tools ist so konzipiert, dass sie eine manuelle Bearbeitung ermöglicht. Sie müssen die Datei bearbeiten, um die erforderliche Version für die Arbeit mit dem Repository zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="dab78-221">The tool manifest file is designed to allow hand editing – which you might do to update the required version for working with the repository.</span></span> <span data-ttu-id="dab78-222">Hier ist ein Beispiel für eine `dotnet-tools.json`-Datei:</span><span class="sxs-lookup"><span data-stu-id="dab78-222">Here is an example `dotnet-tools.json` file:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "dotnetsay": {
      "version": "2.1.4",
      "commands": [
        "dotnetsay"
      ]
    },
    "t-rex": {
      "version": "1.0.103",
      "commands": [
        "t-rex"
      ]
    }
  }
}
```

<span data-ttu-id="dab78-223">Für sowohl globale als auch lokale Tools ist eine kompatible Version der Runtime erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dab78-223">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="dab78-224">Die meisten Tools führen derzeit NuGet.org target .NET Core Runtime 2.1 aus.</span><span class="sxs-lookup"><span data-stu-id="dab78-224">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="dab78-225">Um diese global oder lokal zu installieren, müssten Sie weiterhin die [NET Core 2.1-Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1) installieren.</span><span class="sxs-lookup"><span data-stu-id="dab78-225">To install those globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="dab78-226">Windows-Desktop</span><span class="sxs-lookup"><span data-stu-id="dab78-226">Windows desktop</span></span>

<span data-ttu-id="dab78-227">Ab .NET Core 3.0 Vorschauversion 1 können Sie Windows Desktop-Anwendungen mit WPF und Windows Forms erstellen.</span><span class="sxs-lookup"><span data-stu-id="dab78-227">Starting with .NET Core 3.0 Preview 1, you can build Windows desktop applications using WPF and Windows Forms.</span></span> <span data-ttu-id="dab78-228">Diese Frameworks unterstützt auch die Verwendung moderner Steuerelemente und des Fluent-Stils aus der Windows-UI-XAML-Bibliothek (WinUI) über [XAML-Inseln](/windows/uwp/xaml-platform/xaml-host-controls).</span><span class="sxs-lookup"><span data-stu-id="dab78-228">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="dab78-229">Die Windows Desktop-Komponente ist Teil des Windows .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="dab78-229">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="dab78-230">Mit dem folgenden `dotnet`-Befehl können Sie eine neue WPF- oder Windows Forms-Anwendung erstellen:</span><span class="sxs-lookup"><span data-stu-id="dab78-230">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="dab78-231">Neu in Vorschauversion 2 von Visual Studio 2019 sind Vorlagen für die Option **Neues Projekt** für Windows Forms und WPF in .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="dab78-231">Visual Studio 2019 Preview 2 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span> <span data-ttu-id="dab78-232">Designer werden nach wie vor noch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dab78-232">Designers are still not yet supported.</span></span> <span data-ttu-id="dab78-233">Sie können die Projekte in Visual Studio 2019 öffnen, starten und debuggen.</span><span class="sxs-lookup"><span data-stu-id="dab78-233">And you can open, launch, and debug these projects in Visual Studio 2019.</span></span>

<span data-ttu-id="dab78-234">Ab Visual Studio 2017 15.9 ist es möglich, [.NET Core-Vorschauversionen zu aktivieren](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/). Dieses Feature müssen Sie jedoch erst aktivieren, und es handelt sich dabei nicht um ein unterstütztes Szenario.</span><span class="sxs-lookup"><span data-stu-id="dab78-234">Visual Studio 2017 15.9 adds the ability to [enable .NET Core previews](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/), but you need to turn that feature on, and it's not a supported scenario.</span></span>

<span data-ttu-id="dab78-235">Die neuen Projekte sind die gleichen wie die bestehenden.NET Core Projekte, mit ein paar Ergänzungen.</span><span class="sxs-lookup"><span data-stu-id="dab78-235">The new projects are the same as existing .NET Core projects, with a couple additions.</span></span> <span data-ttu-id="dab78-236">Hier ist der Vergleich eines einfachen .NET Core-Konsolenprojekts mit einem einfachen Windows Forms- und WPF-Projekt.</span><span class="sxs-lookup"><span data-stu-id="dab78-236">Here is the comparison of the basic .NET Core console project and a basic Windows Forms and WPF project.</span></span>

<span data-ttu-id="dab78-237">In einem .NET Core-Konsolenprojekt verwendet das Projekt das `Microsoft.NET.Sdk` SDK und deklariert eine Abhängigkeit von .NET Core 3.0 über das `netcoreapp3.0`-Zielframework.</span><span class="sxs-lookup"><span data-stu-id="dab78-237">In a .NET Core console project, the project uses the `Microsoft.NET.Sdk` SDK and declares a dependency on .NET Core 3.0 via the `netcoreapp3.0` target framework.</span></span> <span data-ttu-id="dab78-238">Um eine Windows Desktop-Anwendung zu erstellen, verwenden Sie das `Microsoft.NET.Sdk.WindowsDesktop` SDK und wählen Sie das zu verwendende UI-Framework:</span><span class="sxs-lookup"><span data-stu-id="dab78-238">To create a Windows Desktop app, use the `Microsoft.NET.Sdk.WindowsDesktop` SDK and choose which UI framework to use:</span></span>

```diff
-<Project Sdk="Microsoft.NET.Sdk">
+<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
+   <UseWPF>true</UseWPF>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="dab78-239">Um Windows Forms und nicht WPF zu wählen, legen Sie `UseWindowsForms` anstelle von `UseWPF` fest:</span><span class="sxs-lookup"><span data-stu-id="dab78-239">To choose Windows Forms over WPF, set `UseWindowsForms` instead of `UseWPF`:</span></span>

```diff
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
-   <UseWPF>true</UseWPF>
+   <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="dab78-240">Sowohl `UseWPF` als auch `UseWindowsForms` können auf `true` festgelegt werden, wenn die Anwendung beide Frameworks verwendet, z.B. wenn ein Windows Forms-Dialogfeld ein WPF-Steuerelement bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="dab78-240">Both `UseWPF` and `UseWindowsForms` can be set to `true` if the app uses both frameworks, for example when a Windows Forms dialog is hosting a WPF control.</span></span>

<span data-ttu-id="dab78-241">Ihr Feedback in den [dotnet/winforms](https://github.com/dotnet/winforms/issues)-, [dotnet/wpf](https://github.com/dotnet/wpf/issues)- und [dotnet/core](https://github.com/dotnet/core/issues)-Repositorys ist jederzeit willkommen.</span><span class="sxs-lookup"><span data-stu-id="dab78-241">Please share your feedback on the [dotnet/winforms](https://github.com/dotnet/winforms/issues),  [dotnet/wpf](https://github.com/dotnet/wpf/issues) and [dotnet/core](https://github.com/dotnet/core/issues) repos.</span></span>

## <a name="msix-deployment-for-windows-desktop"></a><span data-ttu-id="dab78-242">MSIX-Bereitstellung für Windows Desktop</span><span class="sxs-lookup"><span data-stu-id="dab78-242">MSIX Deployment for Windows Desktop</span></span>

<span data-ttu-id="dab78-243">[MSIX](https://docs.microsoft.com/windows/msix/) ist ein neues Windows-App-Paketformat.</span><span class="sxs-lookup"><span data-stu-id="dab78-243">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows app package format.</span></span> <span data-ttu-id="dab78-244">Es kann zum Bereitstellen von .NET Core 3.0-Desktopanwendungen auf Windows 10 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dab78-244">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="dab78-245">Ab der Vorschauversion 2 von Visual Studio 2019 können mit dem enthaltenen [Paketerstellungsprojekt für Windows-Anwendungen](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net) MSIX-Pakete mit [eigenständigen](../deploying/#self-contained-deployments-scd) .NET Core-Anwendungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="dab78-245">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019 Preview 2, allows you to create MSIX packages with [self-contained](../deploying/#self-contained-deployments-scd) .NET Core applications.</span></span>

><span data-ttu-id="dab78-246">Hinweis: Die unterstützten Laufzeiten müssen in der `<RuntimeIdentifiers>`-Eigenschaft der .NET Core-Projektdatei angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="dab78-246">Note: The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>
```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="fast-built-in-json-support"></a><span data-ttu-id="dab78-247">Schneller integrierter JSON-Support</span><span class="sxs-lookup"><span data-stu-id="dab78-247">Fast built-in JSON support</span></span>

<span data-ttu-id="dab78-248">Das .NET-Ökosystem basiert auf [**Json.NET**](https://www.newtonsoft.com/json) und anderen beliebten JSON-Bibliotheken, die weiterhin eine gute Wahl sind.</span><span class="sxs-lookup"><span data-stu-id="dab78-248">The .NET ecosystem has relied on [**Json.NET**](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="dab78-249">**Json.NET** verwendet als Basisdatentyp .NET-Zeichenfolgen, die intern in UTF-16 codiert sind.</span><span class="sxs-lookup"><span data-stu-id="dab78-249">**Json.NET** uses .NET strings as its base datatype, which are UTF-16 under the hood.</span></span>

<span data-ttu-id="dab78-250">Die neue integrierte JSON-Unterstützung ist überaus leistungsfähig und basiert auf `Span<byte>`. Außerdem wird damit nur wenig Speicher belegt.</span><span class="sxs-lookup"><span data-stu-id="dab78-250">The new built-in JSON support is high-performance, low allocation, and based on `Span<byte>`.</span></span> <span data-ttu-id="dab78-251">In .NET Core 3.0 wurden dem Namespace `System.Text.Json` drei neue JSON-bezogene Typen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dab78-251">Three new main JSON-related types have been added to .NET Core 3.0 the `System.Text.Json` namespace.</span></span>

### <a name="utf8jsonreader"></a><span data-ttu-id="dab78-252">Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="dab78-252">Utf8JsonReader</span></span>

<span data-ttu-id="dab78-253">`System.Text.Json.Utf8JsonReader` ist ein leistungsstarker, reiner Vorwärtsleser mit geringer Zuordnung für UTF-8-kodierten JSON-Text, der von einem `ReadOnlySpan<byte>` gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="dab78-253">`System.Text.Json.Utf8JsonReader` is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="dab78-254">Der `Utf8JsonReader` ist ein grundlegender, Low-Level-Typ, der zum Erstellen von benutzerdefinierten Parsern und Fehler beim Erstellen des Deserialisierungsprogramms genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="dab78-254">The `Utf8JsonReader` is a foundational, low-level type, that can be leveraged to build custom parsers and deserializers.</span></span> <span data-ttu-id="dab78-255">Das Durchlesen einer JSON-Nutzlast mit dem neuen `Utf8JsonReader` ist 2x schneller als mit dem Leser von **Json.NET**.</span><span class="sxs-lookup"><span data-stu-id="dab78-255">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from **Json.NET**.</span></span> <span data-ttu-id="dab78-256">Es wird erst dann zugewiesen, wenn Sie JSON-Token als (UTF-16)-Zeichenfolgen aktualisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="dab78-256">It does not allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="dab78-257">Diese neue API umfasst die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="dab78-257">This new API will include the following components:</span></span>

* <span data-ttu-id="dab78-258">In Vorschauversion 1: JSON-Reader (sequenzieller Zugriff)</span><span class="sxs-lookup"><span data-stu-id="dab78-258">In Preview 1: JSON reader (sequential access)</span></span>
* <span data-ttu-id="dab78-259">Geplant: JSON-Writer, DOM (wahlfreier Zugriff), POCO-Serialisierungsprogramm, POCO-Deserialisierungsprogramm</span><span class="sxs-lookup"><span data-stu-id="dab78-259">Coming next: JSON writer, DOM (random access), poco serializer, poco deserializer</span></span>

<span data-ttu-id="dab78-260">Hier ist eine einfache Leserschleife für den `Utf8JsonReader`, die als Startpunkt verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="dab78-260">Here is the basic reader loop for the `Utf8JsonReader` that can be used as a starting point:</span></span>

```csharp
using System.Text.Json;

public static void Utf8JsonReaderLoop(ReadOnlySpan<byte> dataUtf8)
{
    var json = new Utf8JsonReader(dataUtf8, isFinalBlock: true, state: default);

    while (json.Read())
    {
        JsonTokenType tokenType = json.TokenType;
        ReadOnlySpan<byte> valueSpan = json.ValueSpan;
        switch (tokenType)
        {
            case JsonTokenType.StartObject:
            case JsonTokenType.EndObject:
                break;
            case JsonTokenType.StartArray:
            case JsonTokenType.EndArray:
                break;
            case JsonTokenType.PropertyName:
                break;
            case JsonTokenType.String:
                string valueString = json.GetStringValue();
                break;
            case JsonTokenType.Number:
                if (!json.TryGetInt32Value(out int valueInteger))
                {
                    throw new FormatException();
                }
                break;
            case JsonTokenType.True:
            case JsonTokenType.False:
                bool valueBool = json.GetBooleanValue();
                break;
            case JsonTokenType.Null:
                break;
            default:
                throw new ArgumentException();
        }
    }

    dataUtf8 = dataUtf8.Slice((int)json.BytesConsumed);
    JsonReaderState state = json.CurrentState;
}
```

### <a name="utf8jsonwriter"></a><span data-ttu-id="dab78-261">Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="dab78-261">Utf8JsonWriter</span></span>

<span data-ttu-id="dab78-262">Mit `System.Text.Json.Utf8JsonWriter` lassen sich in UTF-8 codierte JSON-Texte aus gängigen .NET-Typen wie `String`, `Int32` und `DateTime` schnell, vorwärtsgerichtet und ohne Zwischenspeichern schreiben.</span><span class="sxs-lookup"><span data-stu-id="dab78-262">`System.Text.Json.Utf8JsonWriter` provides a high-performance, non-cached, forward-only way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="dab78-263">Der Writer ist ebenso wie der Reader ein grundlegender Low-Level-Typ, der zum Erstellen von benutzerdefinierten Serialisierungsmodulen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="dab78-263">Like the reader, the writer is a foundational, low-level type, that can be leveraged to build custom serializers.</span></span> <span data-ttu-id="dab78-264">Mit der neuen `Utf8JsonWriter`-Klasse werden JSON-Nutzlasten 30 bis 80 % schnell geschrieben als mit dem **Json.NET**-Writer. Außerdem findet keine Speicherbelegung statt.</span><span class="sxs-lookup"><span data-stu-id="dab78-264">Writing a JSON payload using the new `Utf8JsonWriter` is 30-80% faster than using the writer from **Json.NET** and does not allocate.</span></span>

<span data-ttu-id="dab78-265">Das folgende Beispiel enthält für `Utf8JsonWriter` ein Anwendungsszenario, das als Ausgangspunkt verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="dab78-265">Here is a sample usage of the `Utf8JsonWriter` that can be used as a starting point:</span></span>

```csharp
static int WriteJson(IBufferWriter<byte> output, long[] extraData)
{
    var json = new Utf8JsonWriter(output, state: default);

    json.WriteStartObject();

    json.WriteNumber("age", 15, escape: false);
    json.WriteString("date", DateTime.Now);
    json.WriteString("first", "John");
    json.WriteString("last", "Smith");

    json.WriteStartArray("phoneNumbers", escape: false);
    json.WriteStringValue("425-000-1212", escape: false);
    json.WriteStringValue("425-000-1213");
    json.WriteEndArray();

    json.WriteStartObject("address");
    json.WriteString("street", "1 Microsoft Way");
    json.WriteString("city", "Redmond");
    json.WriteNumber("zip", 98052);
    json.WriteEndObject();

    json.WriteStartArray("ExtraArray");
    for (var i = 0; i < extraData.Length; i++)
    {
        json.WriteNumberValue(extraData[i]);
    }
    json.WriteEndArray();

    json.WriteEndObject();

    json.Flush(isFinalBlock: true);

    return (int)json.BytesWritten;
}
```

<span data-ttu-id="dab78-266">`Utf8JsonWriter` nimmt `IBufferWriter<byte>` als Ausgabespeicherort entgegen, in den die JSON-Daten geschrieben werden. In der aufrufenden Funktion muss eine konkrete Implementierung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="dab78-266">The `Utf8JsonWriter` accepts `IBufferWriter<byte>` as the output location to synchronously write the json data into, and you as the caller need to provide a concrete implementation.</span></span> <span data-ttu-id="dab78-267">Die Plattform umfasst zurzeit keine Implementierung dieser Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="dab78-267">The platform does not currently include an implementation of this interface.</span></span> <span data-ttu-id="dab78-268">Ein Beispiel zu `IBufferWriter<byte>` finden Sie unter [https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35](https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35).</span><span class="sxs-lookup"><span data-stu-id="dab78-268">For an example of `IBufferWriter<byte>`, see [https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35](https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35)</span></span>

### <a name="jsondocument"></a><span data-ttu-id="dab78-269">JsonDocument</span><span class="sxs-lookup"><span data-stu-id="dab78-269">JsonDocument</span></span>

<span data-ttu-id="dab78-270">`System.Text.Json.JsonDocument` basiert auf `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="dab78-270">`System.Text.Json.JsonDocument` is built on top of the `Utf8JsonReader`.</span></span> <span data-ttu-id="dab78-271">Mit `JsonDocument` können JSON-Daten analysiert werden. Zusätzlich kann damit ein schreibgeschütztes Dokumentobjektmodell (DOM) erstellt werden, das zur Unterstützung von zufälligen Zugriffen und Enumerationen abgefragt werden kann.</span><span class="sxs-lookup"><span data-stu-id="dab78-271">The `JsonDocument` provides the ability to parse JSON data and build a read-only Document Object Model (DOM) that can be queried to support random access and enumeration.</span></span> <span data-ttu-id="dab78-272">Auf die JSON-Elemente, aus denen sich die Daten zusammensetzen, kann über den Typ `JsonElement` zugegriffen werden, der von `JsonDocument` als `RootElement`-Eigenschaft verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="dab78-272">The JSON elements that compose the data can be accessed via the `JsonElement` type which is exposed by the `JsonDocument` as a property called `RootElement`.</span></span> <span data-ttu-id="dab78-273">`JsonElement` enthält das JSON-Array und Objektenumeratoren sowie APIs zum Konvertieren von JSON-Text in gängige .NET-Typen.</span><span class="sxs-lookup"><span data-stu-id="dab78-273">The `JsonElement` contains the JSON array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="dab78-274">Die Analyse einer typischen JSON-Nutzlast und der Zugriff auf alle zugehörigen Member mithilfe von `JsonDocument` wird zwei- bis dreimal so schnell durchgeführt wie mit **Json.NET**. Dabei wird für eine überschaubare Datengröße (< 1 MB) nur wenig Speicher belegt.</span><span class="sxs-lookup"><span data-stu-id="dab78-274">Parsing a typical JSON payload and accessing all its members using the `JsonDocument` is 2-3x faster than **Json.NET** with very little allocations for data that is reasonably sized (i.e. < 1 MB).</span></span>

<span data-ttu-id="dab78-275">Das folgende Beispiel enthält für `JsonDocument` und `JsonElement` ein Anwendungsszenario, das als Ausgangspunkt verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="dab78-275">Here is a sample usage of the `JsonDocument` and `JsonElement` that can be used as a starting point:</span></span>

```csharp
static double ParseJson()
{
    const string json = " [ { \"name\": \"John\" }, [ \"425-000-1212\", 15 ], { \"grades\": [ 90, 80, 100, 75 ] } ]";

    double average = -1;

    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        JsonElement root = doc.RootElement;
        JsonElement info = root[1];

        string phoneNumber = info[0].GetString();
        int age = info[1].GetInt32();

        JsonElement grades = root[2].GetProperty("grades");

        double sum = 0;
        foreach (JsonElement grade in grades.EnumerateArray())
        {
            sum += grade.GetInt32();
        }

        int numberOfCourses = grades.GetArrayLength();
        average = sum / numberOfCourses;
    }

    return average;
}
```

## <a name="assembly-unloadability"></a><span data-ttu-id="dab78-276">Assemblyentladbarkeit</span><span class="sxs-lookup"><span data-stu-id="dab78-276">Assembly Unloadability</span></span>

<span data-ttu-id="dab78-277">Assemblyentladbarkeit ist eine neue Funktion von `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="dab78-277">Assembly unloadability is a new capability of `AssemblyLoadContext`.</span></span> <span data-ttu-id="dab78-278">Dieses neue Feature bringt nur wenige neue APIs mit sich und ist daher aus der API-Perspektive gut überschaubar.</span><span class="sxs-lookup"><span data-stu-id="dab78-278">This new feature is largely transparent from an API perspective, exposed with just a few new APIs.</span></span> <span data-ttu-id="dab78-279">Mithilfe der Assemblyentladbarkeit kann der Ladeprogrammkontext entladen werden, wodurch sämtlicher Speicher für instanziierte Typen, statische Felder und für die Assembly selbst freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="dab78-279">It enables a loader context to be unloaded, releasing all memory for instantiated types, static fields and for the assembly itself.</span></span> <span data-ttu-id="dab78-280">Eine Anwendung sollte mit diesem Mechanismus unbegrenzt lange Assemblys laden und entladen können, ohne dass ein Arbeitsspeicherverlust auftritt.</span><span class="sxs-lookup"><span data-stu-id="dab78-280">An application should be able to load and unload assemblies via this mechanism forever without experiencing a memory leak.</span></span>

<span data-ttu-id="dab78-281">Diese neue Funktion kann für Szenarios wie die folgenden verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="dab78-281">This new capability can be used for scenarios similar to:</span></span>

* <span data-ttu-id="dab78-282">Plug-In-Szenarios, in denen ein dynamisches Laden und Entladen von Plug-Ins erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="dab78-282">Plugin scenarios where dynamic plugin loading and unloading is required.</span></span> 
* <span data-ttu-id="dab78-283">Dynamisches Kompilieren und Ausführen von Code sowie Leeren des zugehörigen Speichers.</span><span class="sxs-lookup"><span data-stu-id="dab78-283">Dynamically compiling, running and then flushing code.</span></span> <span data-ttu-id="dab78-284">Dies ist beispielsweise für Websites und Skript-Engines nützlich.</span><span class="sxs-lookup"><span data-stu-id="dab78-284">Useful for web sites, scripting engines, etc.</span></span>
* <span data-ttu-id="dab78-285">Laden von Assemblys für eine Selbstprüfung (ähnlich wie bei ReflectionOnlyLoad). In vielen Fällen ist [MetadataLoadContext](#type-metadataloadcontext) (veröffentlicht in Vorschauversion 1) jedoch die bessere Wahl.</span><span class="sxs-lookup"><span data-stu-id="dab78-285">Loading assemblies for introspection (like ReflectionOnlyLoad), although [MetadataLoadContext](#type-metadataloadcontext) (released in Preview 1) will be a better choice in many cases.</span></span>

<span data-ttu-id="dab78-286">Weitere Informationen finden Sie unter [Verwenden von Entladbarkeit](https://github.com/dotnet/coreclr/pull/22221).</span><span class="sxs-lookup"><span data-stu-id="dab78-286">For more information, see the [Using Unloadability](https://github.com/dotnet/coreclr/pull/22221) document.</span></span>

<span data-ttu-id="dab78-287">Beim Entladen von Assemblys muss unbedingt darauf geachtet werden, dass alle außerhalb des Ladeprogrammkontexts vorhandenen Verweise auf verwaltete Objekte nachvollzogen und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="dab78-287">Assembly unloading requires significant care to ensure that all references to managed objects from outside a loader context are understood and managed.</span></span> <span data-ttu-id="dab78-288">Wenn der Ladeprogrammkontext zum Entladen aufgefordert wird, müssen alle externen Verweise bereits aufgehoben sein, damit der Ladeprogrammkontext ausschließlich mit sich selbst konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="dab78-288">When the loader context is requested to be unloaded, any outside references need to have been unreferenced so that the loader context is self-consistent only to itself.</span></span>

<span data-ttu-id="dab78-289">Assemblyentladbarkeit wurde im .NET Framework durch Anwendungsdomänen (AppDomains) bereitgestellt, die in .NET Core nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="dab78-289">Assembly unloadability was provided in the .NET Framework by Application Domains (AppDomains), which are not supported with .NET Core.</span></span> <span data-ttu-id="dab78-290">AppDomains hatten verglichen mit diesem neuen Modell sowohl Vor- als auch Nachteile.</span><span class="sxs-lookup"><span data-stu-id="dab78-290">AppDomains had both benefits and limitations compared to this new model.</span></span> <span data-ttu-id="dab78-291">Das neue Ladeprogrammmodell kann im Vergleich zu AppDomains als flexibler und leistungsfähiger betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="dab78-291">Consider this new loader model to be more flexible and higher performant when compared to AppDomains.</span></span>

## <a name="windows-native-interop"></a><span data-ttu-id="dab78-292">Native Windows-Interop-API</span><span class="sxs-lookup"><span data-stu-id="dab78-292">Windows Native Interop</span></span>

<span data-ttu-id="dab78-293">Windows stellt eine umfassende native API mit grundlegenden C-APIs (ohne C++-Features), COM und WinRT bereit.</span><span class="sxs-lookup"><span data-stu-id="dab78-293">Windows offers a rich native API, in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="dab78-294">Seit .NET Core 1.0 wird **P/Invoke** unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dab78-294">Since .NET Core 1.0, **P/Invoke** has been supported.</span></span> <span data-ttu-id="dab78-295">In .NET Core 3.0 besteht nun die Möglichkeit, **mit CoCreate COM-APIs zu erstellen** und **WinRT-APIs zu aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="dab78-295">Now with .NET Core 3.0, support for the ability to **CoCreate COM APIs** and **Activate WinRT APIs** has been added.</span></span>

<span data-ttu-id="dab78-296">Ein Beispiel zur Verwendung von COM finden Sie im [Quellcode der Excel-Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span><span class="sxs-lookup"><span data-stu-id="dab78-296">You can see an example of using COM with the [Excel Demo source code](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>


## <a name="type-sequencereader"></a><span data-ttu-id="dab78-297">Typ: SequenceReader</span><span class="sxs-lookup"><span data-stu-id="dab78-297">Type: SequenceReader</span></span>

<span data-ttu-id="dab78-298">In .NET Core 3.0 wurde `System.Buffers.SequenceReader` hinzugefügt, der als Leser für `ReadOnlySequence<T>` verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="dab78-298">In .NET Core 3.0, `System.Buffers.SequenceReader` has been added which can be used as a reader for `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="dab78-299">Dies ermöglicht eine einfache, leistungsstarke Zuteilungsanalyse mit geringer Priorität von `System.IO.Pipelines`-Daten, die mehrere Hintergrundpuffer überwinden können.</span><span class="sxs-lookup"><span data-stu-id="dab78-299">This allows easy, high performance, low allocation parsing of `System.IO.Pipelines` data that can cross multiple backing buffers.</span></span> 

<span data-ttu-id="dab78-300">Das folgende Beispiel bricht eine Eingabe-`Sequence` in gültige, durch Trennzeichen getrennte `CR/LF`-Zeilen auf:</span><span class="sxs-lookup"><span data-stu-id="dab78-300">The following example breaks an input `Sequence` into valid `CR/LF` delimited lines:</span></span>

```csharp
private static ReadOnlySpan<byte> CRLF => new byte[] { (byte)'\r', (byte)'\n' };

public static void ReadLines(ReadOnlySequence<byte> sequence)
{
    SequenceReader<byte> reader = new SequenceReader<byte>(sequence);

    while (!reader.End)
    {
        if (!reader.TryReadToAny(out ReadOnlySpan<byte> line, CRLF, advancePastDelimiter:false))
        {
            // Couldn't find another delimiter
            // ...
        }

        if (!reader.IsNext(CRLF, advancePast: true))
        {
            // Not a good CR/LF pair
            // ...
        }

        // line is valid, process
        ProcessLine(line);
    }
}
```

## <a name="type-metadataloadcontext"></a><span data-ttu-id="dab78-301">Typ: MetadataLoadContext</span><span class="sxs-lookup"><span data-stu-id="dab78-301">Type: MetadataLoadContext</span></span>

<span data-ttu-id="dab78-302">Der `MetadataLoadContext`-Typ wurde hinzugefügt, der das Lesen von Assemblymetadaten ermöglicht, ohne die Anwendungsdomäne des Anrufers zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="dab78-302">The `MetadataLoadContext` type has been added that enables reading assembly metadata without affecting the caller’s application domain.</span></span> <span data-ttu-id="dab78-303">Assemblys werden als Daten gelesen, einschließlich Assemblys, die für andere Architekturen und Plattformen als die aktuelle Runtimeumgebung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="dab78-303">Assemblies are read as data, including assemblies built for different architectures and platforms than the current runtime environment.</span></span> <span data-ttu-id="dab78-304">`MetadataLoadContext` überschneidet sich mit <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, das nur in .NET Framework verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="dab78-304">`MetadataLoadContext` overlaps with the <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, which is only available in the .NET Framework.</span></span>

<span data-ttu-id="dab78-305">`MetdataLoadContext` ist im [System.Reflection.MetadataLoadContext-Paket](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dab78-305">`MetdataLoadContext` is available in the [System.Reflection.MetadataLoadContext package](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext).</span></span> <span data-ttu-id="dab78-306">Es ist ein .NET Standard 2.0-Paket.</span><span class="sxs-lookup"><span data-stu-id="dab78-306">It is a .NET Standard 2.0 package.</span></span>

<span data-ttu-id="dab78-307">Der `MetadataLoadContext` stellt APIs ähnlich dem Typ <xref:System.Runtime.Loader.AssemblyLoadContext> zur Verfügung, basiert aber nicht auf diesem Typ.</span><span class="sxs-lookup"><span data-stu-id="dab78-307">The `MetadataLoadContext` exposes APIs similar to the <xref:System.Runtime.Loader.AssemblyLoadContext> type, but is not based on that type.</span></span> <span data-ttu-id="dab78-308">Ähnlich wie <xref:System.Runtime.Loader.AssemblyLoadContext> ermöglicht der `MetadataLoadContext` das Laden von Assemblys innerhalb einer isolierten Umgebung zum Laden von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="dab78-308">Much like <xref:System.Runtime.Loader.AssemblyLoadContext>, the `MetadataLoadContext` enables loading assemblies within an isolated assembly loading universe.</span></span> <span data-ttu-id="dab78-309">`MetdataLoadContext`-APIs geben <xref:System.Reflection.Assembly>-Objekte zurück, sodass bekannte Reflektions-APIs verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="dab78-309">`MetdataLoadContext` APIs return <xref:System.Reflection.Assembly> objects, enabling the use of familiar reflection APIs.</span></span> <span data-ttu-id="dab78-310">Ausführungsorientierte APIs, wie [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127) sind nicht zulässig, und geben „InvalidOperationException“ zurück.</span><span class="sxs-lookup"><span data-stu-id="dab78-310">Execution-oriented APIs, such as [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), are not allowed and will throw InvalidOperationException.</span></span>

<span data-ttu-id="dab78-311">Das folgende Beispiel zeigt, wie Sie den richtigen Typen in einer Assembly findet, die eine bestimmte Schnittstelle implementiert:</span><span class="sxs-lookup"><span data-stu-id="dab78-311">The following sample demonstrates how to find concrete types in an assembly that implements a given interface:</span></span>

```csharp
var paths = new string[] {@"C:\myapp\mscorlib.dll", @"C:\myapp\myapp.dll"};
var resolver = new PathAssemblyResolver(paths);
using (var lc = new MetadataLoadContext(resolver))
{
    Assembly a = lc.LoadFromAssemblyName("myapp");
    Type myInterface = a.GetType("MyApp.IPluginInterface");
    foreach (Type t in a.GetTypes())
    {
        if (t.IsClass && myInterface.IsAssignableFrom(t))
            Console.WriteLine($"Class {t.FullName} implements IPluginInterface");
    }
}
```

<span data-ttu-id="dab78-312">Szenarien für `MetadataLoadContext` beinhalten Entwurfszeitfeatures, Buildzeit-Tools und Runtime-Light-Up-Features, die eine Reihe von Assemblys als Daten überprüfen müssen und alle Dateisperren und Speicher freigeben, nachdem die Überprüfung durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="dab78-312">Scenarios for `MetadataLoadContext` include design-time features, build-time tooling, and runtime light-up features that need to inspect a set of assemblies as data and have all file locks and memory freed after inspection is performed.</span></span>

<span data-ttu-id="dab78-313">Der `MetadataLoadContext` hat eine Resolverklasse, die an dessen Konstruktor übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="dab78-313">The `MetadataLoadContext` has a resolver class passed to its constructor.</span></span> <span data-ttu-id="dab78-314">Die Auftrag des Resolvers ist es, eine `Assembly` zu laden, wenn der `AssemblyName` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="dab78-314">The resolver's job is to load an `Assembly` given its `AssemblyName`.</span></span> <span data-ttu-id="dab78-315">Die Resolverklasse wird aus der abstrakten `MetadataAssemblyResolver`-Klasse abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="dab78-315">The resolver class derives from the abstract `MetadataAssemblyResolver` class.</span></span> <span data-ttu-id="dab78-316">Die Implementierung des Resolvers für pfadbasierte Szenarien ist durch `PathAssemblyResolver` möglich.</span><span class="sxs-lookup"><span data-stu-id="dab78-316">An implementation of the resolver for path-based scenarios is provided with `PathAssemblyResolver`.</span></span>

<span data-ttu-id="dab78-317">Die [MetadataLoadContext-Tests](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) zeigen viele Anwendungsfälle.</span><span class="sxs-lookup"><span data-stu-id="dab78-317">The [MetadataLoadContext tests](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) demonstrate many use cases.</span></span> <span data-ttu-id="dab78-318">Die [Assemblytests](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) sind ein guter Ausgangspunkt.</span><span class="sxs-lookup"><span data-stu-id="dab78-318">The [Assembly tests](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) are a good place to start.</span></span>

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="dab78-319">TLS 1.3 & OpenSSL 1.1.1 auf Linux</span><span class="sxs-lookup"><span data-stu-id="dab78-319">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="dab78-320">.NET Core nutzt nun die Unterstützung von [TLS 1.3 in OpenSSL 1.1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), wenn es in einer bestimmten Umgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="dab78-320">.NET Core will now take advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it is available in a given environment.</span></span> <span data-ttu-id="dab78-321">Gemäß dem [OpenSSL-Team](https://www.openssl.org/blog/blog/2018/09/11/release111/) hat TLS 1.3 viele Vorteile:</span><span class="sxs-lookup"><span data-stu-id="dab78-321">There are multiple benefits of TLS 1.3, per the [OpenSSL team](https://www.openssl.org/blog/blog/2018/09/11/release111/):</span></span>

* <span data-ttu-id="dab78-322">Verbesserte Verbindungszeiten aufgrund einer Reduzierung der erforderlich Roundtrips zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="dab78-322">Improved connection times due to a reduction in the number of round trips required between the client and server.</span></span>

* <span data-ttu-id="dab78-323">Höhere Sicherheit durch das Entfernen verschiedener veralteter und unsicher Kryptografiealgorithmen und die Verschlüsselung von mehr des Verbindungshandshake.</span><span class="sxs-lookup"><span data-stu-id="dab78-323">Improved security due to the removal of various obsolete and insecure cryptographic algorithms and encryption of more of the connection handshake.</span></span>

<span data-ttu-id="dab78-324">.NET Core 3.0 Vorschauversion 1 kann **OpenSSL 1.1.1**, **OpenSSL 1.1.0** oder **OpenSSL 1.0.2** (was auch immer die geeignete Lösung ist) auf einem Linux-System verwenden.</span><span class="sxs-lookup"><span data-stu-id="dab78-324">.NET Core 3.0 Preview 1 is capable of utilizing **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** (whatever the best version found is, on a Linux system).</span></span>  <span data-ttu-id="dab78-325">Wenn **OpenSSL 1.1.1** verfügbar ist, verwenden „SslStream“- und „HttpClient“-Typen **TLS 1.3** bei der Nutzung von `SslProtocols.None` (systemseitige Standardprotokolle), sofern sowohl der Client als auch der Server **TLS 1.3** unterstützen.</span><span class="sxs-lookup"><span data-stu-id="dab78-325">When **OpenSSL 1.1.1** is available the SslStream and HttpClient types will use **TLS 1.3** when using `SslProtocols.None` (system default protocols), assuming both the client and server support **TLS 1.3**.</span></span>

<span data-ttu-id="dab78-326">Das folgende Beispiel veranschaulicht .NET Core 3.0 Vorschauversion 1 auf Ubuntu 18.10 beim Verbinden mit <https://www.cloudflare.com>:</span><span class="sxs-lookup"><span data-stu-id="dab78-326">The following sample demonstrates .NET Core 3.0 Preview 1 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

```csharp
using System;
using System.Net.Security;
using System.Net.Sockets;
using System.Threading.Tasks;

namespace tlstest
{
    class Program
    {
        static async Task Main()
        {
            using (TcpClient tcpClient = new TcpClient())
            {
                string targetHost = "www.cloudflare.com";

                await tcpClient.ConnectAsync(targetHost, 443);

                using (SslStream sslStream = new SslStream(tcpClient.GetStream()))
                {
                    await sslStream.AuthenticateAsClientAsync(targetHost);
                    await Console.Out.WriteLineAsync($"Connected to {targetHost} with {sslStream.SslProtocol}");
                }
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/tlstest$ dotnet run
Connected to www.cloudflare.com with Tls13
user@comp-ubuntu1810:~/tlstest$ openssl version
OpenSSL 1.1.1  11 Sep 2018
```

>[!IMPORTANT]
><span data-ttu-id="dab78-327">Windows und macOS unterstützen **TLS 1.3** noch nicht.</span><span class="sxs-lookup"><span data-stu-id="dab78-327">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="dab78-328">.NET Core 3.0 unterstützt **TLS 1.3** auf diesen Betriebssystemen, wenn entsprechender Support verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="dab78-328">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

## <a name="cryptography"></a><span data-ttu-id="dab78-329">Kryptografie</span><span class="sxs-lookup"><span data-stu-id="dab78-329">Cryptography</span></span>

<span data-ttu-id="dab78-330">Unterstützung für **AES-GCM**- und **AES-CCM**-Verschlüsselungen wurde hinzugefügt, implementiert über `System.Security.Cryptography.AesGcm` und `System.Security.Cryptography.AesCcm`.</span><span class="sxs-lookup"><span data-stu-id="dab78-330">Support has been added for **AES-GCM** and **AES-CCM** ciphers, implemented via `System.Security.Cryptography.AesGcm` and `System.Security.Cryptography.AesCcm`.</span></span> <span data-ttu-id="dab78-331">Diese Algorithmen sind beide [Authenticated Encryption with Association Data (AEAD)-Algorithmen](https://en.wikipedia.org/wiki/Authenticated_encryption) und die ersten Authenticated Encryption (AE)-Algorithmen, die zu .NET Core hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="dab78-331">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption), and the first Authenticated Encryption (AE) algorithms added to .NET Core.</span></span>

<span data-ttu-id="dab78-332">Der folgende Code veranschaulicht die Verwendung der **AesGcm**-Verschlüsselung zum Verschlüsseln und Entschlüsseln von Zufallsdaten.</span><span class="sxs-lookup"><span data-stu-id="dab78-332">The following code demonstrates using **AesGcm** cipher to encrypt and decrypt random data.</span></span>

<span data-ttu-id="dab78-333">Der Code für **AesCcm** würde fast identisch aussehen (nur der Variablenname der Klasse wäre anders).</span><span class="sxs-lookup"><span data-stu-id="dab78-333">The code for **AesCcm** would look almost identical (only the class variable names would be different).</span></span>

```csharp
// key should be: pre-known, derived, or transported via another channel, such as RSA encryption
byte[] key = new byte[16];
RandomNumberGenerator.Fill(key);

byte[] nonce = new byte[12];
RandomNumberGenerator.Fill(nonce);

// normally this would be your data
byte[] dataToEncrypt = new byte[1234];
byte[] associatedData = new byte[333];
RandomNumberGenerator.Fill(dataToEncrypt);
RandomNumberGenerator.Fill(associatedData);

// these will be filled during the encryption
byte[] tag = new byte[16];
byte[] ciphertext = new byte[dataToEncrypt.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Encrypt(nonce, dataToEncrypt, ciphertext, tag, associatedData);
}

// tag, nonce, ciphertext, associatedData should be sent to the other part

byte[] decryptedData = new byte[ciphertext.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Decrypt(nonce, ciphertext, tag, decryptedData, associatedData);
}

// do something with the data
// this should always print that data is the same
Console.WriteLine($"AES-GCM: Decrypted data is{(dataToEncrypt.SequenceEqual(decryptedData) ? "the same as" : "different than")} original data.");
```

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="dab78-334">Importieren/Exportieren kryptografischer Schlüssel</span><span class="sxs-lookup"><span data-stu-id="dab78-334">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="dab78-335">.NET Core 3.0 Vorschauversion 1 unterstützt das Importieren und Exportieren der asymmetrischen öffentliche und private Schlüssel aus den Standardformaten, ohne dass ein x. 509-Zertifikat verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="dab78-335">.NET Core 3.0 Preview 1 supports the import and export of asymmetric public and private keys from standard formats, without needing to use an X.509 certificate.</span></span>

<span data-ttu-id="dab78-336">Alle Schlüsseltypen (RSA, DSA, ECDsa, ECDiffieHellman) unterstützten das Format **X.509 SubjectPublicKeyInfo** für öffentliche Schlüssel und die Formate **PKCS#8 PrivateKeyInfo** und **PKCS#8 EncryptedPrivateKeyInfo** für private Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="dab78-336">All key types (RSA, DSA, ECDsa, ECDiffieHellman) support the **X.509 SubjectPublicKeyInfo** format for public keys, and the **PKCS#8 PrivateKeyInfo** and **PKCS#8 EncryptedPrivateKeyInfo** formats for private keys.</span></span> <span data-ttu-id="dab78-337">RSA unterstützt zudem **PKCS#1 RSAPublicKey** und **PKCS#1 RSAPrivateKey**.</span><span class="sxs-lookup"><span data-stu-id="dab78-337">RSA additionally supports **PKCS#1 RSAPublicKey** and **PKCS#1 RSAPrivateKey**.</span></span> <span data-ttu-id="dab78-338">Die Exportmethoden erstellen alle DER-kodierte Binärdaten, und die Importmethoden erwarten dasselbe.</span><span class="sxs-lookup"><span data-stu-id="dab78-338">The export methods all produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="dab78-339">Wenn ein Schlüssel im textfreundlichen PEM-Format gespeichert ist, muss der Anrufer den Inhalt base64-dekodieren, bevor er eine Importmethode aufruft.</span><span class="sxs-lookup"><span data-stu-id="dab78-339">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

namespace rsakeyprint
{
    class Program
    {
        static void Main(string[] args)
        {
            using (RSA rsa = RSA.Create())
            {
                byte[] keyBytes = File.ReadAllBytes(args[0]);
                rsa.ImportRSAPrivateKey(keyBytes, out int bytesRead);
 
                Console.WriteLine($"Read {bytesRead} bytes, {keyBytes.Length-bytesRead} extra byte(s) in file.");
                RSAParameters rsaParameters = rsa.ExportParameters(true);
                Console.WriteLine(BitConverter.ToString(rsaParameters.D));
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/rsakeyprint$ echo Making a small key to save on screen space.
Making a small key to save on screen space.
user@comp-ubuntu1810:~/rsakeyprint$ openssl genrsa 768 | openssl rsa -outform der -out rsa.key
Generating RSA private key, 768 bit long modulus (2 primes)
..+++++++
........+++++++
e is 65537 (0x010001)
writing RSA key
user@comp-ubuntu1810:~/rsakeyprint$ dotnet run rsa.key
Read 461 bytes, 0 extra byte(s) in file.
0F-D0-82-34-F8-13-38-4A-7F-C7-52-4A-F6-93-F8-FB-6D-98-7A-6A-04-3B-BC-35-8C-7D-AC-A5-A3-6E-AD-C1-66-30-81-2C-2A-DE-DA-60-03-6A-2C-D9-76-15-7F-61-97-57-
79-E1-6E-45-62-C3-83-04-97-CB-32-EF-C5-17-5F-99-60-92-AE-B6-34-6F-30-06-03-AC-BF-15-24-43-84-EB-83-60-EF-4D-3B-BD-D9-5D-56-26-F0-51-CE-F1
user@comp-ubuntu1810:~/rsakeyprint$ openssl rsa -in rsa.key -inform der -text -noout | grep -A7 private
privateExponent:
    0f:d0:82:34:f8:13:38:4a:7f:c7:52:4a:f6:93:f8:
    fb:6d:98:7a:6a:04:3b:bc:35:8c:7d:ac:a5:a3:6e:
    ad:c1:66:30:81:2c:2a:de:da:60:03:6a:2c:d9:76:
    15:7f:61:97:57:79:e1:6e:45:62:c3:83:04:97:cb:
    32:ef:c5:17:5f:99:60:92:ae:b6:34:6f:30:06:03:
    ac:bf:15:24:43:84:eb:83:60:ef:4d:3b:bd:d9:5d:
    56:26:f0:51:ce:f1
```

<span data-ttu-id="dab78-340">PKCS #8-Dateien können mit der `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo`-Klasse überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="dab78-340">PKCS#8 files can be inspected with the `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo` class.</span></span>

<span data-ttu-id="dab78-341">PFX/PKCS#12-Dateien können mit `System.Security.Cryptography.Pkcs.Pkcs12Info` oder `System.Security.Cryptography.Pkcs.Pkcs12Builder` überprüft und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="dab78-341">PFX/PKCS#12 files can be inspected and manipulated with `System.Security.Cryptography.Pkcs.Pkcs12Info` and `System.Security.Cryptography.Pkcs.Pkcs12Builder`, respectively.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="dab78-342">SerialPort für Linux</span><span class="sxs-lookup"><span data-stu-id="dab78-342">SerialPort for Linux</span></span>

<span data-ttu-id="dab78-343">.NET Core 3.0 unterstützt jetzt <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> auf Linux.</span><span class="sxs-lookup"><span data-stu-id="dab78-343">.NET Core 3.0 now supports <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="dab78-344">Bisher unterstützte .NET Core nur die Verwendung des `SerialPort`-Typs auf Windows.</span><span class="sxs-lookup"><span data-stu-id="dab78-344">Previously, .NET Core only supported using the `SerialPort` type on Windows.</span></span>

## <a name="more-bcl-improvements"></a><span data-ttu-id="dab78-345">Weitere BCL-Verbesserungen</span><span class="sxs-lookup"><span data-stu-id="dab78-345">More BCL Improvements</span></span>

<span data-ttu-id="dab78-346">Die Typen `Span<T>`, `Memory<T>` und verwandte Typen, die in .NET Core 2.1 eingeführt wurden, wurden in .NET Core 3.0 optimiert.</span><span class="sxs-lookup"><span data-stu-id="dab78-346">The `Span<T>`, `Memory<T>`, and related types that were introduced in .NET Core 2.1, have been optimized in .NET Core 3.0.</span></span> <span data-ttu-id="dab78-347">Allgemeine Vorgänge, wie die Bereichserstellung, Slicing, Analyse und Formatierung werden jetzt besser ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dab78-347">Common operations such as span construction, slicing, parsing, and formatting now perform better.</span></span> 

<span data-ttu-id="dab78-348">Darüber hinaus haben Typen wie `String` indirekte Verbesserungen, um sie effizienter zu machen, wenn sie als Schlüssel mit `Dictionary<TKey, TValue>` und anderen Sammlungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dab78-348">Additionally, types like `String` have seen under-the-cover improvements to make them more efficient when used as keys with `Dictionary<TKey, TValue>` and other collections.</span></span> <span data-ttu-id="dab78-349">Um von diesen Verbesserungen zu profitieren, sind keine Codeänderungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dab78-349">No code changes are required to benefit from these improvements.</span></span>

<span data-ttu-id="dab78-350">NET Core 3 Vorschauversion 1 enthält außerdem die folgenden Verbesserungen:</span><span class="sxs-lookup"><span data-stu-id="dab78-350">The following improvements are also new in .NET Core 3 Preview 1:</span></span>

* <span data-ttu-id="dab78-351">In HttpClient integrierte Brotli-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="dab78-351">Brotli support built in to HttpClient</span></span>
* <span data-ttu-id="dab78-352">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span><span class="sxs-lookup"><span data-stu-id="dab78-352">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span></span>
* <span data-ttu-id="dab78-353">Unsafe.Unbox</span><span class="sxs-lookup"><span data-stu-id="dab78-353">Unsafe.Unbox</span></span>
* <span data-ttu-id="dab78-354">CancellationToken.Unregister</span><span class="sxs-lookup"><span data-stu-id="dab78-354">CancellationToken.Unregister</span></span>
* <span data-ttu-id="dab78-355">Komplexe arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="dab78-355">Complex arithmetic operators</span></span>
* <span data-ttu-id="dab78-356">Socket-APIs für TCP-Keep-Alive</span><span class="sxs-lookup"><span data-stu-id="dab78-356">Socket APIs for TCP keep alive</span></span>
* <span data-ttu-id="dab78-357">StringBuilder.GetChunks</span><span class="sxs-lookup"><span data-stu-id="dab78-357">StringBuilder.GetChunks</span></span>
* <span data-ttu-id="dab78-358">IPEndPoint-Analyse</span><span class="sxs-lookup"><span data-stu-id="dab78-358">IPEndPoint parsing</span></span>
* <span data-ttu-id="dab78-359">RandomNumberGenerator.GetInt32</span><span class="sxs-lookup"><span data-stu-id="dab78-359">RandomNumberGenerator.GetInt32</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="dab78-360">Mehrstufig Kompilierung</span><span class="sxs-lookup"><span data-stu-id="dab78-360">Tiered compilation</span></span>

<span data-ttu-id="dab78-361">Die [mehrstufig Kompilierung](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) ist bei .NET Core 3.0 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="dab78-361">[Tiered compilation](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="dab78-362">Es ist ein Feature, das es der Runtime ermöglicht, den Just-In-Time (JIT)-Compiler adaptiver zu nutzen, um eine bessere Leistung zu erzielen, sowohl beim Start als auch zur Maximierung des Durchsatzes.</span><span class="sxs-lookup"><span data-stu-id="dab78-362">It is a feature that enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance, both at startup and to maximize throughput.</span></span>

<span data-ttu-id="dab78-363">Dieses Feature wurde als abonnierbares Feature für [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) hinzugefügt, und anschließend standardmäßig in der [.NET Core 2.2 Vorschauversion 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="dab78-363">This feature was added as an opt-in feature in [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) and then was enabled by default in [.NET Core 2.2 Preview 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/).</span></span> <span data-ttu-id="dab78-364">Anschließend wurde es wieder zurückgesetzt, und ist mit dem Release von .NET Core 2.2 wieder abonnierbar.</span><span class="sxs-lookup"><span data-stu-id="dab78-364">Subsequently, it has been reverted back to opt in with the .NET Core 2.2 release.</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="dab78-365">ARM64-Linux-Support</span><span class="sxs-lookup"><span data-stu-id="dab78-365">ARM64 Linux support</span></span>

<span data-ttu-id="dab78-366">ARM64 für Linux wird nun unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dab78-366">Support has been added for ARM64 for Linux.</span></span> <span data-ttu-id="dab78-367">Der primäre Anwendungsfall für ARM64 sind derzeit IoT-Szenarien.</span><span class="sxs-lookup"><span data-stu-id="dab78-367">The primary use case for ARM64 is currently with IoT scenarios.</span></span>

<span data-ttu-id="dab78-368">Alpine-, Debian- und Ubuntu-[-Dockerimages sind für .NET Core für ARM64 verfügbar](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="dab78-368">Alpine, Debian and Ubuntu [Docker images are available for .NET Core for ARM64](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

<span data-ttu-id="dab78-369">Bitte lesen Sie für weitere Informationen [.NET Core-ARM64-Status](https://github.com/dotnet/announcements/issues/82)</span><span class="sxs-lookup"><span data-stu-id="dab78-369">Please check [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82) for more information.</span></span>

>[!NOTE]
> <span data-ttu-id="dab78-370">**ARM64** wird von Windows noch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dab78-370">**ARM64** Windows support isn't yet available.</span></span>

## <a name="install-net-core-30-previews-on-linux-with-snap"></a><span data-ttu-id="dab78-371">Installieren von .NET Core 3.0-Vorschauversionen unter Linux mit Snap</span><span class="sxs-lookup"><span data-stu-id="dab78-371">Install .NET Core 3.0 Previews on Linux with Snap</span></span>

<span data-ttu-id="dab78-372">Snap ist die bevorzugte Methode zum Installieren und Testen von .NET Core-Vorschauversionen unter [Linux-Distributionen, die Snap unterstützen](https://docs.snapcraft.io/installing-snapd/6735).</span><span class="sxs-lookup"><span data-stu-id="dab78-372">Snap is the preferred way to install and try .NET Core previews on [Linux distributions that support Snap](https://docs.snapcraft.io/installing-snapd/6735).</span></span>

<span data-ttu-id="dab78-373">Führen Sie nach dem Konfigurieren von Snap auf Ihrem System den folgenden Befehl aus, um das [.NET Core SDK 3.0 für die Vorschauversion](https://snapcraft.io/dotnet-sdk) zu installieren.</span><span class="sxs-lookup"><span data-stu-id="dab78-373">After configuring Snap on your system, run the following command to install the [.NET Core SDK 3.0 Preview SDK](https://snapcraft.io/dotnet-sdk).</span></span>

```console
sudo snap install dotnet-sdk --beta --classic
```
 
<span data-ttu-id="dab78-374">Wenn .NET Core mit dem Snap-Paket installiert wird, lautet der Standardbefehl für .NET Core `dotnet-sdk.dotnet` und nicht nur `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="dab78-374">When .NET Core in installed using the Snap package, the default .NET Core command is `dotnet-sdk.dotnet`, as opposed to just `dotnet`.</span></span> <span data-ttu-id="dab78-375">Der Vorteil des Befehls mit dem Namespace besteht darin, dass keine Konflikte mit möglicherweise global installierten .NET Core-Versionen auftreten.</span><span class="sxs-lookup"><span data-stu-id="dab78-375">The benefit of the namespaced command is that it will not conflict with a globally installed .NET Core version you may have.</span></span> <span data-ttu-id="dab78-376">Für diesen Befehl kann der Alias `dotnet` wie folgt erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="dab78-376">This command can be aliased to `dotnet` with:</span></span>

```console
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="dab78-377">Bei einigen Distributionen ist ein zusätzlicher Schritt zum Aktivieren des Zugriffs auf das SSL-Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dab78-377">Some distros require an additional step to enable access to the SSL certificate.</span></span> <span data-ttu-id="dab78-378">Details finden Sie im Artikel zur [Einrichtung von Linux](https://github.com/dotnet/core/blob/master/Documentation/linux-setup.md).</span><span class="sxs-lookup"><span data-stu-id="dab78-378">See our [Linux Setup](https://github.com/dotnet/core/blob/master/Documentation/linux-setup.md) for details.</span></span>

## <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="dab78-379">GPIO-Unterstützung für Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="dab78-379">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="dab78-380">Über NuGet können nun zwei neue Pakete für die GPIO-Programmierung bezogen werden:</span><span class="sxs-lookup"><span data-stu-id="dab78-380">Two new packages have been released to NuGet that you can use for GPIO programming.</span></span>

* [<span data-ttu-id="dab78-381">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="dab78-381">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio/0.1.0-prerelease.19078.2)
* [<span data-ttu-id="dab78-382">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="dab78-382">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings/0.1.0-prerelease.19078.2)

<span data-ttu-id="dab78-383">Die GPIO-Pakete enthalten APIs für GPIO-, SPI-, I2C- und PWM-Geräte.</span><span class="sxs-lookup"><span data-stu-id="dab78-383">The GPIO Packages includes APIs for GPIO, SPI, I2C and PWM devices.</span></span> <span data-ttu-id="dab78-384">Das IoT-Bindungspaket enthält [Gerätebindungen](https://github.com/dotnet/iot/blob/master/src/devices/README.md) für verschiedene Chips und Sensoren. Dabei handelt es sich um die gleichen Bindungen, die unter [dotnet/iot – src/devices](https://github.com/dotnet/iot/tree/master/src/devices) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="dab78-384">The IoT bindings package includes [device bindings](https://github.com/dotnet/iot/blob/master/src/devices/README.md) for various chips and sensors, the same ones available at [dotnet/iot - src/devices](https://github.com/dotnet/iot/tree/master/src/devices).</span></span>

<span data-ttu-id="dab78-385">Die aktualisierten APIs für serielle Anschlüsse, die zusammen mit der Vorschauversion 1 von .NET Core 3.0 angekündigt wurden, sind nicht in diesen Paketen enthalten, stehen jedoch als Teil der .NET Core-Plattform zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="dab78-385">The updated serial port APIs that were announced as part of .NET Core 3.0 Preview 1 are not part of these packages but are available as part of the .NET Core platform.</span></span>


## <a name="platform-support"></a><span data-ttu-id="dab78-386">Plattformunterstützung</span><span class="sxs-lookup"><span data-stu-id="dab78-386">Platform Support</span></span>

<span data-ttu-id="dab78-387">.NET Core 3.0 wird auf den folgenden Betriebssystemen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="dab78-387">.NET Core 3 will be supported on the following operating systems:</span></span>

* <span data-ttu-id="dab78-388">Windows-Client: 7, 8.1, 10 (1607 und höher)</span><span class="sxs-lookup"><span data-stu-id="dab78-388">Windows Client: 7, 8.1, 10 (1607+)</span></span>
* <span data-ttu-id="dab78-389">Windows Server: 20012 R2 SP1 und höher</span><span class="sxs-lookup"><span data-stu-id="dab78-389">Windows Server: 20012 R2 SP1+</span></span>
* <span data-ttu-id="dab78-390">macOS: 10.12 und höher</span><span class="sxs-lookup"><span data-stu-id="dab78-390">macOS: 10.12+</span></span>
* <span data-ttu-id="dab78-391">RHEL: 6 und höher</span><span class="sxs-lookup"><span data-stu-id="dab78-391">RHEL: 6+</span></span>
* <span data-ttu-id="dab78-392">Fedora: 26 und höher</span><span class="sxs-lookup"><span data-stu-id="dab78-392">Fedora: 26+</span></span>
* <span data-ttu-id="dab78-393">Ubuntu: 16.04 und höher</span><span class="sxs-lookup"><span data-stu-id="dab78-393">Ubuntu: 16.04+</span></span>
* <span data-ttu-id="dab78-394">Debian: 9 und höher</span><span class="sxs-lookup"><span data-stu-id="dab78-394">Debian: 9+</span></span>
* <span data-ttu-id="dab78-395">SLES: 12 und höher</span><span class="sxs-lookup"><span data-stu-id="dab78-395">SLES: 12+</span></span>
* <span data-ttu-id="dab78-396">openSUSE: 42.3+</span><span class="sxs-lookup"><span data-stu-id="dab78-396">openSUSE: 42.3+</span></span>
* <span data-ttu-id="dab78-397">Alpine: 3.8+</span><span class="sxs-lookup"><span data-stu-id="dab78-397">Alpine: 3.8+</span></span>

<span data-ttu-id="dab78-398">Außerdem werden folgende Chiparchitekturen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="dab78-398">Chip support follows:</span></span>

* <span data-ttu-id="dab78-399">x64 unter Windows, macOS und Linux</span><span class="sxs-lookup"><span data-stu-id="dab78-399">x64 on Windows, macOS, and Linux</span></span>
* <span data-ttu-id="dab78-400">x86 unter Windows</span><span class="sxs-lookup"><span data-stu-id="dab78-400">x86 on Windows</span></span>
* <span data-ttu-id="dab78-401">ARM32 unter Windows und Linux</span><span class="sxs-lookup"><span data-stu-id="dab78-401">ARM32 on Windows and Linux</span></span>
* <span data-ttu-id="dab78-402">ARM64 unter Linux</span><span class="sxs-lookup"><span data-stu-id="dab78-402">ARM64 on Linux</span></span>

<span data-ttu-id="dab78-403">Für Linux wird ARM32 unter Debian 9 und höher und Ubuntu 16.04 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dab78-403">For Linux, ARM32 is supported on Debian 9+ and Ubuntu 16.04+.</span></span> <span data-ttu-id="dab78-404">Für ARM64 gilt das Gleiche wie für ARM32, jedoch wird zusätzlich Alpine 3.8 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dab78-404">For ARM64, it is the same as ARM32 with the addition of Alpine 3.8.</span></span> <span data-ttu-id="dab78-405">Es handelt sich um die gleichen Versionen der Distributionen, die auch für x64 unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="dab78-405">These are the same versions of those distros as is supported for X64.</span></span>

<span data-ttu-id="dab78-406">Docker-Images für .NET Core 3.0 sind unter [microsoft/dotnet im Docker-Hub](https://hub.docker.com/r/microsoft/dotnet/) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dab78-406">Docker images for .NET Core 3.0 are available at [microsoft/dotnet on Docker Hub](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="dab78-407">Microsoft arbeitet aktuell an der Einführung der [Microsoft Container Registry (MCR)](https://cloudblogs.microsoft.com/opensource/2019/01/17/improved-discovery-experience-microsoft-containers-docker-hub/). Die finalen .NET Core 3.0-Images werden voraussichtlich nur dort veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="dab78-407">Microsoft is currently in the process of adopting [Microsoft Container Registry (MCR)](https://cloudblogs.microsoft.com/opensource/2019/01/17/improved-discovery-experience-microsoft-containers-docker-hub/) and it is expected that the final .NET Core 3.0 images will only be published to MCR.</span></span>
