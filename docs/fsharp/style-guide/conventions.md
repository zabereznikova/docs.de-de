---
title: F#-Programmierung Konventionen
description: Erfahren Sie, allgemeine Richtlinien und Idiome, beim Schreiben von F#-Code.
ms.date: 05/14/2018
ms.openlocfilehash: b9afd1fbfbd9d8e04d9bfaa07615de045b7e05fe
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2018
ms.locfileid: "47237399"
---
# <a name="f-coding-conventions"></a><span data-ttu-id="44c6a-103">F#-Programmierung Konventionen</span><span class="sxs-lookup"><span data-stu-id="44c6a-103">F# coding conventions</span></span>

<span data-ttu-id="44c6a-104">Die folgenden Konventionen aus Erfahrung, die Arbeit mit großen f# formuliert werden Codebasen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="44c6a-105">Die [fünf Prinzipien guten F#-Code](index.md#five-principles-of-good-f-code) bilden die Grundlage jeder Empfehlung.</span><span class="sxs-lookup"><span data-stu-id="44c6a-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="44c6a-106">Sie beziehen sich auf die [Entwurfsrichtlinien für F#-Komponente](component-design-guidelines.md), jedoch gelten für alle F#-Code, nicht nur Komponenten wie Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="44c6a-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="44c6a-107">Organisieren von code</span><span class="sxs-lookup"><span data-stu-id="44c6a-107">Organizing code</span></span>

<span data-ttu-id="44c6a-108">F# bietet zwei bevorzugte Möglichkeiten, Code zu organisieren: Modulen und Namespaces.</span><span class="sxs-lookup"><span data-stu-id="44c6a-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="44c6a-109">Diese sind ähnlich, aber Sie müssen die folgenden Unterschiede:</span><span class="sxs-lookup"><span data-stu-id="44c6a-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="44c6a-110">Namespaces werden als .NET Namespaces kompiliert.</span><span class="sxs-lookup"><span data-stu-id="44c6a-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="44c6a-111">Module werden als statische Klassen kompiliert.</span><span class="sxs-lookup"><span data-stu-id="44c6a-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="44c6a-112">Namespaces sind immer oberste Ebene.</span><span class="sxs-lookup"><span data-stu-id="44c6a-112">Namespaces are always top level.</span></span> <span data-ttu-id="44c6a-113">Module können der obersten Ebene und in anderen Modulen geschachtelt sein.</span><span class="sxs-lookup"><span data-stu-id="44c6a-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="44c6a-114">Namespaces können mehrere Dateien umfassen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="44c6a-115">Standardmodule nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="44c6a-115">Modules cannot.</span></span>
* <span data-ttu-id="44c6a-116">Module können mit ergänzt werden `[<RequireQualifiedAccess>]` und `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="44c6a-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="44c6a-117">Die folgenden Richtlinien können Sie diese verwenden, um Ihren Code zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="44c6a-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="44c6a-118">Bevorzugen Sie Namespaces auf der obersten Ebene</span><span class="sxs-lookup"><span data-stu-id="44c6a-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="44c6a-119">Für jeden öffentlich nutzbar Code werden Namespaces Zugriffscode Modulen auf der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="44c6a-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="44c6a-120">Da sie als .NET Namespaces kompiliert werden, sind sie in c# genutzt, kein Problem.</span><span class="sxs-lookup"><span data-stu-id="44c6a-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="44c6a-121">Mit einem Modul auf oberster Ebene möglicherweise nicht angezeigt, unterschiedliche, wenn Sie nur von F#-aufgerufen, aber für C#-Verbraucher Aufrufer Ergebnissen möglicherweise überrascht sein, dass Sie zu qualifizieren `MyClass` mit der `MyCode` Modul.</span><span class="sxs-lookup"><span data-stu-id="44c6a-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="44c6a-122">Sorgfältig anwenden. `[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="44c6a-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="44c6a-123">Die `[<AutoOpen>]` Konstrukt kann den Bereich der verfügbaren Aufrufern verunreinigen, und die Antwort auf einen Ursprung ist "magische".</span><span class="sxs-lookup"><span data-stu-id="44c6a-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="44c6a-124">Dies ist in der Regel nicht gut.</span><span class="sxs-lookup"><span data-stu-id="44c6a-124">This is generally not a good thing.</span></span> <span data-ttu-id="44c6a-125">Eine Ausnahme von dieser Regel ist die F#-Kernbibliothek selbst (obwohl dies auch etwas umstrittenen ist).</span><span class="sxs-lookup"><span data-stu-id="44c6a-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="44c6a-126">Es ist jedoch aus Gründen der benutzerfreundlichkeit, wenn Sie über Hilfsfunktionen für eine öffentliche API verfügen, die Sie zum Organisieren von separat über der öffentliche API möchten.</span><span class="sxs-lookup"><span data-stu-id="44c6a-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

```fsharp
module MyAPI =
    [<AutoOpen>]
    module private Helpers =
        let helper1 x y z =
            ...


    let myFunction1 x =
        let y = ...
        let z = ...

        helper1 x y z
```

<span data-ttu-id="44c6a-127">Dadurch können Sie sauber separate Implementierungsdetails aus der öffentlichen API einer Funktion ohne vollständig eine Hilfsprogramm jedes Mal zu qualifizieren Sie ihn aufrufen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="44c6a-128">Darüber hinaus verfügbar gemacht, Erweiterungsmethoden und Ausdrucks-Generatoren auf Namespaceebene sauber ausgedrückt werden mit `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="44c6a-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="44c6a-129">Verwendung `[<RequireQualifiedAccess>]` jedes Mal, wenn Namen in Konflikt stehen können, oder Sie der Meinung sind, helfen Ihnen Lesbarkeit</span><span class="sxs-lookup"><span data-stu-id="44c6a-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="44c6a-130">Hinzufügen der `[<RequireQualifiedAccess>]` Attribut auf ein Modul gibt an, dass das Modul kann nicht geöffnet werden, dass Verweise auf die Elemente des Moduls explizite benötigen Zugriff qualifizierten.</span><span class="sxs-lookup"><span data-stu-id="44c6a-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="44c6a-131">Z. B. die `Microsoft.FSharp.Collections.List` Modul verfügt über dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="44c6a-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="44c6a-132">Dies ist nützlich, wenn Funktionen und Werte im Modul Namen haben, die einen Konflikt mit den Namen in anderen Modulen wahrscheinlich sind.</span><span class="sxs-lookup"><span data-stu-id="44c6a-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="44c6a-133">Qualifizierten Zugriff erfordern, kann erheblich die langfristige wartbarkeit und Evolvability einer Bibliothek erhöhen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="44c6a-134">Sortierung `open` Anweisungen topologisch</span><span class="sxs-lookup"><span data-stu-id="44c6a-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="44c6a-135">In f# wird die Reihenfolge der Deklarationen von Bedeutung ist, einschließlich mit `open` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="44c6a-136">Dies ist anders als bei c#, wobei die Auswirkungen der `using` und `using static` ist unabhängig von der Reihenfolge dieser Anweisungen in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="44c6a-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="44c6a-137">In f# können Elemente in einem Bereich geöffnet Shadowing für andere bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="44c6a-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="44c6a-138">Dies bedeutet, dass diese Neuordnung `open` Anweisungen können die Bedeutung des Codes ändern.</span><span class="sxs-lookup"><span data-stu-id="44c6a-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="44c6a-139">Als Ergebnis jeden beliebigen aller sortieren `open` Anweisungen (z. B. alphanumerisch) wird im Allgemeinen nicht empfohlen, damit ein anderes Verhalten zu generieren, die Sie möglicherweise erwarten.</span><span class="sxs-lookup"><span data-stu-id="44c6a-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is generally not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="44c6a-140">Stattdessen empfehlen wir, dass Sie diese sortieren [topologisch](https://en.wikipedia.org/wiki/Topological_sorting); sortieren, also Ihr `open` Anweisungen in der Reihenfolge, in der _Ebenen_ des Systems definiert sind.</span><span class="sxs-lookup"><span data-stu-id="44c6a-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="44c6a-141">Alphanumerische in Schichten topologische Sortierung durchführen kann ebenfalls berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="44c6a-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="44c6a-142">Als Beispiel ist hier die topologische Sortierung für die F#-Compiler öffentliche API-Datei:</span><span class="sxs-lookup"><span data-stu-id="44c6a-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

```fsharp
namespace Microsoft.FSharp.Compiler.SourceCodeServices

open System
open System.Collections.Generic
open System.Collections.Concurrent
open System.Diagnostics
open System.IO
open System.Reflection
open System.Text

open Microsoft.FSharp.Compiler
open Microsoft.FSharp.Compiler.AbstractIL
open Microsoft.FSharp.Compiler.AbstractIL.Diagnostics
open Microsoft.FSharp.Compiler.AbstractIL.IL
open Microsoft.FSharp.Compiler.AbstractIL.ILBinaryReader
open Microsoft.FSharp.Compiler.AbstractIL.Internal
open Microsoft.FSharp.Compiler.AbstractIL.Internal.Library

open Microsoft.FSharp.Compiler.AccessibilityLogic
open Microsoft.FSharp.Compiler.Ast
open Microsoft.FSharp.Compiler.CompileOps
open Microsoft.FSharp.Compiler.CompileOptions
open Microsoft.FSharp.Compiler.Driver
open Microsoft.FSharp.Compiler.ErrorLogger
open Microsoft.FSharp.Compiler.Infos
open Microsoft.FSharp.Compiler.InfoReader
open Microsoft.FSharp.Compiler.Lexhelp
open Microsoft.FSharp.Compiler.Layout
open Microsoft.FSharp.Compiler.Lib
open Microsoft.FSharp.Compiler.NameResolution
open Microsoft.FSharp.Compiler.PrettyNaming
open Microsoft.FSharp.Compiler.Parser
open Microsoft.FSharp.Compiler.Range
open Microsoft.FSharp.Compiler.Tast
open Microsoft.FSharp.Compiler.Tastops
open Microsoft.FSharp.Compiler.TcGlobals
open Microsoft.FSharp.Compiler.TypeChecker
open Microsoft.FSharp.Compiler.SourceCodeServices.SymbolHelpers

open Internal.Utilities
open Internal.Utilities.Collections
```

<span data-ttu-id="44c6a-143">Beachten Sie, ein Zeilenumbruch topologische Ebenen, wobei jede Ebene danach alphanumerisch sortiert wird getrennt.</span><span class="sxs-lookup"><span data-stu-id="44c6a-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="44c6a-144">Dieser organisiert Code ordnungsgemäß ohne shadowing versehentlich Werte.</span><span class="sxs-lookup"><span data-stu-id="44c6a-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="44c6a-145">Verwenden Sie Klassen, um die Werte enthalten, die Nebeneffekte haben</span><span class="sxs-lookup"><span data-stu-id="44c6a-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="44c6a-146">Es gibt viele Male, wenn Nebeneffekte, wie Sie einen Kontext für eine Datenbank oder andere Remoteressource instanziieren initialisieren einen Wert haben kann.</span><span class="sxs-lookup"><span data-stu-id="44c6a-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="44c6a-147">Es ist verlockend, beispielsweise in einem Modul zu initialisieren, und in nachfolgenden Funktionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="44c6a-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

```fsharp
// This is bad!
module MyApi =
    let dep1 = File.ReadAllText "/Users/{your name}/connectionstring.txt"
    let dep2 = Environment.GetEnvironmentVariable "DEP_2"

    let private r = Random()
    let dep3() = r.Next() // Problematic if multiple threads use this

    let function1 arg = doStuffWith dep1 dep2 dep3 arg
    let function2 arg = doSutffWith dep1 dep2 dep3 arg
```

<span data-ttu-id="44c6a-148">Dies ist häufig keine gute Idee für verschiedene Gründe haben:</span><span class="sxs-lookup"><span data-stu-id="44c6a-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="44c6a-149">Zunächst wird die Anwendungskonfiguration in der Codebasis mit abgelegt `dep1` und `dep2`.</span><span class="sxs-lookup"><span data-stu-id="44c6a-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="44c6a-150">Dies ist schwer in verwalten, dass die größeren Codebasen befindet.</span><span class="sxs-lookup"><span data-stu-id="44c6a-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="44c6a-151">Zweitens werden statisch initialisierte Daten darf keine Werte enthalten, die nicht threadsicher sind, wenn die Komponente selbst mehrere Threads verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="44c6a-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="44c6a-152">Dies wird eindeutig durch verletzt `dep3`.</span><span class="sxs-lookup"><span data-stu-id="44c6a-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="44c6a-153">Schließlich werden Initialisierung des Moduls in einem statischen Konstruktor für die gesamte Kompilationseinheit kompiliert.</span><span class="sxs-lookup"><span data-stu-id="44c6a-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="44c6a-154">Wenn ein Fehler bei der wertinitialisierung von Let gebundenen in diesem Modul auftritt, manifestiert es als ein `TypeInitializationException` , die dann für die gesamte Lebensdauer der Anwendung zwischengespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="44c6a-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="44c6a-155">Dies kann nur schwer zu diagnostizieren sein.</span><span class="sxs-lookup"><span data-stu-id="44c6a-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="44c6a-156">Es ist in der Regel eine innere Ausnahme, der Sie versuchen können, verständlich, aber wenn keine vorhanden ist, besteht keine Information darüber was die Ursache ist.</span><span class="sxs-lookup"><span data-stu-id="44c6a-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="44c6a-157">Stattdessen verwenden Sie eine einfache Klasse einfach, die Abhängigkeiten enthalten soll:</span><span class="sxs-lookup"><span data-stu-id="44c6a-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member __.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member __.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="44c6a-158">Dies ermöglicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="44c6a-158">This enables the following:</span></span>

1. <span data-ttu-id="44c6a-159">Überträgt alle abhängigen Zustand die API selbst.</span><span class="sxs-lookup"><span data-stu-id="44c6a-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="44c6a-160">Konfiguration kann nun außerhalb der API erfolgen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="44c6a-161">Fehler bei der Initialisierung für abhängige Werte können nicht als manifest wahrscheinlich eine `TypeInitializationException`.</span><span class="sxs-lookup"><span data-stu-id="44c6a-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="44c6a-162">Die API ist jetzt einfacher zu testen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="44c6a-163">Fehlerverwaltung</span><span class="sxs-lookup"><span data-stu-id="44c6a-163">Error management</span></span>

<span data-ttu-id="44c6a-164">Fehlerverwaltung in großen Systemen ist ein komplexer und facettenreichen Unterfangen, und es sind keine Silver Aufzählungszeichen Ihrer Systeme zu gewährleisten, sind fehlertolerant und Verhalten sich auch.</span><span class="sxs-lookup"><span data-stu-id="44c6a-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="44c6a-165">Die folgenden Richtlinien sollten bei der Navigation von dieser schwierig Speicherplatz hilfreich.</span><span class="sxs-lookup"><span data-stu-id="44c6a-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="44c6a-166">Darstellen Sie Fehlerfälle und ungültigen Status in Ihrer Domäne systeminterne Typen</span><span class="sxs-lookup"><span data-stu-id="44c6a-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="44c6a-167">Mit [Unterscheidungs-Unions](../language-reference/discriminated-unions.md), f# gibt Ihnen die Möglichkeit, fehlerhafte Programmstatus in Ihrem Typsystem darstellen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="44c6a-168">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="44c6a-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="44c6a-169">In diesem Fall stehen drei bekannte Methoden, die bucht Geld von einem Bankkonto ausfallen können.</span><span class="sxs-lookup"><span data-stu-id="44c6a-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="44c6a-170">Jeder Fehlerfall des Typs dargestellt wird und daher behandelt werden kann sicher in der gesamten Anwendung.</span><span class="sxs-lookup"><span data-stu-id="44c6a-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="44c6a-171">Im Allgemeinen, wenn Sie die verschiedenen Möglichkeiten modellieren können, dass etwas kann **fehlschlagen** in Ihrer Domäne, klicken Sie dann Fehlerbehandlungscode ist nicht mehr als behandelt etwas müssen Sie zusätzlich zum normalen Programmablauf behandeln.</span><span class="sxs-lookup"><span data-stu-id="44c6a-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="44c6a-172">Es ist einfach ein Bestandteil der normalen Programmablauf und nicht als **außergewöhnliche**.</span><span class="sxs-lookup"><span data-stu-id="44c6a-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="44c6a-173">Es gibt zwei Hauptvorteile sprechen für diese:</span><span class="sxs-lookup"><span data-stu-id="44c6a-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="44c6a-174">Es ist einfacher zu verwalten wie Ihre Domäne im Laufe der Zeit ändert.</span><span class="sxs-lookup"><span data-stu-id="44c6a-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="44c6a-175">Fehler werden einfacher Komponententests unterziehen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="44c6a-176">Verwenden Sie Ausnahmen aus, wenn der Fehler nicht mit Typen dargestellt werden kann</span><span class="sxs-lookup"><span data-stu-id="44c6a-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="44c6a-177">Nicht alle Fehler können in einer Problemdomäne dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="44c6a-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="44c6a-178">Diese Art von Fehlern werden *außergewöhnliche* Natur, daher die Möglichkeit, auslösen und Abfangen von Ausnahmen in f#.</span><span class="sxs-lookup"><span data-stu-id="44c6a-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="44c6a-179">Zunächst wird empfohlen, Sie lesen die [Ausnahme Entwurfsrichtlinien](../../standard/design-guidelines/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="44c6a-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="44c6a-180">Diese gelten auch für f#.</span><span class="sxs-lookup"><span data-stu-id="44c6a-180">These are also applicable to F#.</span></span>

<span data-ttu-id="44c6a-181">Im Rahmen der Auslösen von Ausnahmen in f# verfügbar mit die wichtigen Konstrukten sollten in der folgenden Reihenfolge ihrer Priorität berücksichtigt werden:</span><span class="sxs-lookup"><span data-stu-id="44c6a-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="44c6a-182">Funktion</span><span class="sxs-lookup"><span data-stu-id="44c6a-182">Function</span></span> | <span data-ttu-id="44c6a-183">Syntax</span><span class="sxs-lookup"><span data-stu-id="44c6a-183">Syntax</span></span> | <span data-ttu-id="44c6a-184">Zweck</span><span class="sxs-lookup"><span data-stu-id="44c6a-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="44c6a-185">Löst eine `System.ArgumentNullException` mit dem angegebenen Argumentnamen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="44c6a-186">Löst eine `System.ArgumentException` mit einem angegebenen Argumentnamen und Nachricht.</span><span class="sxs-lookup"><span data-stu-id="44c6a-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="44c6a-187">Löst eine `System.InvalidOperationException` mit der angegebenen Meldung.</span><span class="sxs-lookup"><span data-stu-id="44c6a-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="44c6a-188">Allgemeinen Mechanismus zum Auslösen von Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="44c6a-189">Löst eine `System.Exception` mit der angegebenen Meldung.</span><span class="sxs-lookup"><span data-stu-id="44c6a-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="44c6a-190">Löst eine `System.Exception` mit der Meldung hängt von der Formatzeichenfolge und ihre Eingaben.</span><span class="sxs-lookup"><span data-stu-id="44c6a-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="44c6a-191">Verwendung `nullArg`, `invalidArg` und `invalidOp` als Mechanismus zum Auslösen `ArgumentNullException`, `ArgumentException` und `InvalidOperationException` bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="44c6a-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="44c6a-192">Die `failwith` und `failwithf` Funktionen sollten im Allgemeinen vermieden werden, da sie auf die Basis lösen `Exception` eingeben, nicht für eine bestimmte Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="44c6a-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="44c6a-193">Gemäß der [Ausnahme Entwurfsrichtlinien](../../standard/design-guidelines/exceptions.md), spezifischere Ausnahmen auslösen, wenn möglich werden sollen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="44c6a-194">Mithilfe der Syntax der Behandlung von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="44c6a-194">Using exception-handling syntax</span></span>

<span data-ttu-id="44c6a-195">F# unterstützt Muster für die Ausnahme über die `try...with` Syntax:</span><span class="sxs-lookup"><span data-stu-id="44c6a-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="44c6a-196">Abgleichen von Funktionen bei einer Ausnahme mit dem Mustervergleich ausführen werden etwas schwieriger, wenn Sie den Code für eine übersichtlichere möchten.</span><span class="sxs-lookup"><span data-stu-id="44c6a-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="44c6a-197">Eine solche Möglichkeit hierzu ist die Verwendung [mit aktiven Mustern](../language-reference/active-patterns.md) als Mittel zur Funktion für ein Fehler bei einer Ausnahme selbst um.</span><span class="sxs-lookup"><span data-stu-id="44c6a-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="44c6a-198">Beispielsweise können Sie eine API nutzen, die, wenn es eine Ausnahme auslöst, wertvollen Informationen in die Ausnahmemetadaten einschließt.</span><span class="sxs-lookup"><span data-stu-id="44c6a-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="44c6a-199">Das Aufheben dieses Zustands eines nützlicher Wert im Text die abgefangene Ausnahme in das aktive Muster und zurückgeben, dass der Wert in einigen Situationen hilfreich sein kann.</span><span class="sxs-lookup"><span data-stu-id="44c6a-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="44c6a-200">Verwenden Sie keine monadische Fehlerbehandlung um Ausnahmen zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="44c6a-201">Ausnahmen werden als etwas Taboo bei der funktionalen Programmierung betrachtet.</span><span class="sxs-lookup"><span data-stu-id="44c6a-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="44c6a-202">In der Tat verletzen Ausnahmen Reinheit, daher ist es sicher ist, die sie nicht-ziemlich funktionale berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="44c6a-203">Dies ignoriert jedoch die Realität, in dem Code ausgeführt werden muss, und dieser Laufzeit, Fehler auftreten können.</span><span class="sxs-lookup"><span data-stu-id="44c6a-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="44c6a-204">Schreiben Sie Code in der Regel auf der Annahme, dass die meisten Informationen weder reine noch insgesamt, sodass unliebsame überraschungen Ausbleiben minimiert werden.</span><span class="sxs-lookup"><span data-stu-id="44c6a-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="44c6a-205">Es ist wichtig, die folgenden Stärken/Kernaspekte von Ausnahmen in Bezug auf die Relevanz und die Eignung in der .NET Common Language Runtime und sprachübergreifende-Ökosystem als Ganzes zu berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="44c6a-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="44c6a-206">Sie enthalten ausführliche Diagnoseinformationen, die sehr hilfreich ist, wenn ein Problem zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="44c6a-207">Sie sind durch die Common Language Runtime und anderen .NET-Sprachen gut verstanden.</span><span class="sxs-lookup"><span data-stu-id="44c6a-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="44c6a-208">Sie können zu verringern erheblich im Vergleich mit Code, der eine Methode zum verlässt *vermeiden* Ausnahmen durch die Implementierung einer Teilmenge der ihre Semantik auf Ad-hoc-Basis.</span><span class="sxs-lookup"><span data-stu-id="44c6a-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="44c6a-209">Dieser dritte Punkt ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="44c6a-209">This third point is critical.</span></span> <span data-ttu-id="44c6a-210">Fehler beim Verwenden von Ausnahmen kann beim Umgang mit Strukturen wie folgt bei nicht trivialen komplexe Operationen ausführen führen:</span><span class="sxs-lookup"><span data-stu-id="44c6a-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="44c6a-211">Dies kann problemlos zu instabilem Code z. B. einen Musterabgleich für "stringly typisierte" Fehler führen:</span><span class="sxs-lookup"><span data-stu-id="44c6a-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="44c6a-212">Darüber hinaus kann es verlockend sein, eine Ausnahme aus, in dem Wunsch nach einer "einfachen"-Funktion zu behalten, die ein "nützlicher" zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="44c6a-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="44c6a-213">Leider `tryReadAllText` können zahlreiche basierte auf einer Vielzahl von Aufgaben, die in einem Dateisystem auftreten können Ausnahmen auslösen, und dieser Code verwirft sofort jegliche Informationen darüber, was tatsächlich in Ihrer Umgebung nicht in Ordnung sein kann.</span><span class="sxs-lookup"><span data-stu-id="44c6a-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="44c6a-214">Wenn Sie diesen Code mit einem Ergebnistyp ersetzen, sind Sie an der Analyse des "stringly typisierte" Fehler:</span><span class="sxs-lookup"><span data-stu-id="44c6a-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Ok
    with e -> Error e.Message

let r = tryReadAllText "path-to-file"
match r with
| Ok text -> ...
| Error e ->
    if e.Contains "uh oh, here we go again..." then ...
    else ...
```

<span data-ttu-id="44c6a-215">Und das Ausnahmeobjekt selbst in die `Error` Konstruktor nur erzwingt, dass Sie den Typ der Ausnahme an der Aufrufsite und nicht in der Funktion ordnungsgemäß behandeln.</span><span class="sxs-lookup"><span data-stu-id="44c6a-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="44c6a-216">Dadurch effektiv erstellt geprüften Ausnahmen, die bekanntermaßen für den Umgang mit als einer API-Aufrufer unfun sind.</span><span class="sxs-lookup"><span data-stu-id="44c6a-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="44c6a-217">Eine gute Alternative zu den obigen Beispielen ist zum Abfangen von *bestimmte* Ausnahmen und Return keinen sinnvollen Wert im Kontext dieser Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="44c6a-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="44c6a-218">Wenn Sie ändern die `tryReadAllText` funktioniert wie folgt `None` hat mehr Bedeutung:</span><span class="sxs-lookup"><span data-stu-id="44c6a-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="44c6a-219">Statt als ein Catch-All funktioniert, wird diese Funktion jetzt ordnungsgemäß den Fall handhaben, eine Datei wurde nicht gefunden und eine Rückgabe, Bedeutung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="44c6a-220">Dieser Rückgabewert kann zu diesem Fehlerfall bei der nicht verwerfen alle Kontextinformationen oder erzwingen Aufrufe an einen Fall verarbeiten, die möglicherweise nicht relevant ist an diesem Punkt im Code zuordnen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="44c6a-221">Typen wie `Result<'Success, 'Error>` eignen sich für grundlegende Vorgänge, in dem sie geschachtelt sind nicht und optionale f#-Typen sind ideal für darstellen, wenn etwas entweder zurückgeben könnte *etwas* oder *nichts*.</span><span class="sxs-lookup"><span data-stu-id="44c6a-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="44c6a-222">Sie sind kein Ersatz für Ausnahmen, allerdings und sollte nicht versuchen, Ersetzen von Ausnahmen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="44c6a-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="44c6a-223">Stattdessen sollten sie mit Bedacht auf Aspekte der Adresse der Ausnahme und die Richtlinie für die Verwaltung in die entsprechenden Methoden angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="44c6a-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="44c6a-224">Teilweise Anwendung "und" Punkt-free-Programmierung</span><span class="sxs-lookup"><span data-stu-id="44c6a-224">Partial application and point-free programming</span></span>

<span data-ttu-id="44c6a-225">F# unterstützt partielle Anwendung, und daher verschiedene Arten der Programmierung in einem Punkt-free-Stil.</span><span class="sxs-lookup"><span data-stu-id="44c6a-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="44c6a-226">Dies kann für die Wiederverwendung von Code in einem Modul oder die Implementierung von etwas von Vorteil sein, aber es wird in der Regel nicht öffentlich verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-226">This can be beneficial for code reuse within a module or the implementation of something, but it is generally not something to expose publicly.</span></span> <span data-ttu-id="44c6a-227">Im Allgemeinen kann Point-free-Programmierung keine Tugend an und für sich selbst, und eine erhebliche Hürde für cognitive für Personen, die nicht in der Formatvorlage befinden werden.</span><span class="sxs-lookup"><span data-stu-id="44c6a-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="44c6a-228">Verwenden Sie teilweise Anwendung und in öffentlichen APIs currying nicht</span><span class="sxs-lookup"><span data-stu-id="44c6a-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="44c6a-229">Mit kleinen Ausnahme kann die Verwendung von teilweise Anwendung von öffentlichen APIs für Benutzer verwirrend sein.</span><span class="sxs-lookup"><span data-stu-id="44c6a-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="44c6a-230">In der Regel `let`-gebundenen Werte in F#-Code sind **Werte**, nicht **Funktionswerte**.</span><span class="sxs-lookup"><span data-stu-id="44c6a-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="44c6a-231">Miteinander kombinieren, Werte und Werte von Funktionen kann dazu führen, speichern eine kleine Anzahl von Codezeilen im Austausch gegen einiges an cognitive Mehraufwand, insbesondere dann, wenn Sie z. B. mit Operatoren kombiniert `>>` um Funktionen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="44c6a-232">Betrachten Sie die Auswirkungen auf die Tools für Punkt-free-Programmierung</span><span class="sxs-lookup"><span data-stu-id="44c6a-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="44c6a-233">Funktionen mit Currying ihre Argumente nicht beschriftet.</span><span class="sxs-lookup"><span data-stu-id="44c6a-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="44c6a-234">Dies hat Auswirkungen auf die Tools.</span><span class="sxs-lookup"><span data-stu-id="44c6a-234">This has tooling implications.</span></span> <span data-ttu-id="44c6a-235">Beachten Sie die folgenden zwei Funktionen:</span><span class="sxs-lookup"><span data-stu-id="44c6a-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="44c6a-236">Beide sind gültige Funktionen, aber `funcWithApplication` ist eine Funktion, mit Currying.</span><span class="sxs-lookup"><span data-stu-id="44c6a-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="44c6a-237">Wenn Sie über ihre Typen in einem Editor bewegen, wird Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="44c6a-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="44c6a-238">An der Aufrufsite QuickInfos in Tools wie Visual Studio nicht erhalten Sie aussagekräftige Informationen, welche die `string` und `int` Eingabetypen tatsächlich darstellen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="44c6a-239">Punkt-free-Code wie auftreten `funcWithApplication` , die öffentlich nutzbar ist, es wird empfohlen, eine vollständige η-Erweiterung, damit Tools wählen Sie aussagekräftige Namen für die Argumente an bis kann.</span><span class="sxs-lookup"><span data-stu-id="44c6a-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="44c6a-240">Darüber hinaus kann Punkt fehlerfreien Code zu debuggen, wenn nicht sogar unmöglich schwierig sein.</span><span class="sxs-lookup"><span data-stu-id="44c6a-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="44c6a-241">Tools zum Debuggen communitywerte nutzen, um Namen gebunden (z. B. `let` Bindungen), damit Sie während der Ausführung Zwischenwerte Ausführung überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="44c6a-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="44c6a-242">Wenn im Code keine Werte, um zu überprüfen, aber es gibt noch nichts zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="44c6a-243">In Zukunft weiterentwickeln kann debugging-Tools, um diese Werte, die anhand der zuvor ausgeführten Pfade zu synthetisieren, aber es ist nicht ratsam, Ihre Suchergebnisse auf allerhöchstem *potenzielle* Debugfunktionen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="44c6a-244">Betrachten Sie teilweise Anwendung als Verfahren, um interne Codebausteine zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="44c6a-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="44c6a-245">Im Gegensatz zum vorherigen Punkt handelt ist teilweise Anwendung ein hervorragendes Tool zum Reduzieren der Codebaustein in einer Anwendung oder die umfassendere Interna einer API.</span><span class="sxs-lookup"><span data-stu-id="44c6a-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="44c6a-246">Es kann für Komponententests, die die Implementierung komplizierter-APIs, in denen Codebausteine zu handhaben ist häufig hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="44c6a-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="44c6a-247">Beispielsweise der folgende Code zeigt, wie Sie erreichen können, welche die meisten verfügbaren Mockframeworks erhalten Sie ohne eine externe Abhängigkeit auf solch einem Framework, und einen zugehörigen erfahren, dass Individual-API.</span><span class="sxs-lookup"><span data-stu-id="44c6a-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="44c6a-248">Betrachten Sie beispielsweise die folgende Lösung Topografie aus:</span><span class="sxs-lookup"><span data-stu-id="44c6a-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="44c6a-249">`ImplementationLogic.fsproj` Code kann z. B. verfügbar machen:</span><span class="sxs-lookup"><span data-stu-id="44c6a-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member __.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="44c6a-250">Komponententests `Transactions.doTransaction` in `ImplementationLogic.Tests.fspoj` ist einfach:</span><span class="sxs-lookup"><span data-stu-id="44c6a-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fspoj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="44c6a-251">Teilweise Anwendung `doTransaction` Objekt mit einem mocking Kontext können Sie die Funktion in allen Komponententests aufrufen, ohne jedes Mal einen simulierte Kontext zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="44c6a-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member __.TheFirstMember() = ...
        member __.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

<span data-ttu-id="44c6a-252">Dieses Verfahren sollten nicht universell angewendet werden, Ihre gesamte Codebasis, aber es ist eine gute Möglichkeit zur Reduzierung von Codebausteine für komplizierte-Interna und Komponententests, die die Interna.</span><span class="sxs-lookup"><span data-stu-id="44c6a-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="44c6a-253">Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="44c6a-253">Access control</span></span>

<span data-ttu-id="44c6a-254">F# weist mehrere Optionen für [Zugriffssteuerung](../language-reference/access-control.md), geerbt vom, was in der .NET Runtime verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="44c6a-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="44c6a-255">Diese sind nicht nur für Typen verwendet werden – Sie können sie für Funktionen zu.</span><span class="sxs-lookup"><span data-stu-id="44c6a-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="44c6a-256">Lieber nicht`public` Typen und Member, bis Sie sie öffentlich nutzbar sein benötigen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="44c6a-257">Dies minimiert ebenfalls, welche Consumer-Paar</span><span class="sxs-lookup"><span data-stu-id="44c6a-257">This also minimizes what consumers couple to</span></span>
* <span data-ttu-id="44c6a-258">Sich bemühen, behalten Sie alle Hilfsfunktionen `private`.</span><span class="sxs-lookup"><span data-stu-id="44c6a-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="44c6a-259">Betrachten Sie die Verwendung von `[<AutoOpen>]` für ein Modul private Hilfsfunktionen, wenn sie zahlreiche sind.</span><span class="sxs-lookup"><span data-stu-id="44c6a-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="44c6a-260">Typrückschluss und Generika</span><span class="sxs-lookup"><span data-stu-id="44c6a-260">Type inference and generics</span></span>

<span data-ttu-id="44c6a-261">Typrückschluss können Sie über die Eingabe viele häufig speichern.</span><span class="sxs-lookup"><span data-stu-id="44c6a-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="44c6a-262">Und automatische Verallgemeinerung in f#-Compiler können Sie generischen Code mit fast kein zusätzlicher Aufwand ihrerseits zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="44c6a-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="44c6a-263">Diese Funktionen sind jedoch nicht universell gut.</span><span class="sxs-lookup"><span data-stu-id="44c6a-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="44c6a-264">Betrachten Sie die Argumentnamen mit expliziter Typen in öffentlichen APIs, die Bezeichnung, und verlassen Sie sich nicht auf den Typrückschluss für diese.</span><span class="sxs-lookup"><span data-stu-id="44c6a-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="44c6a-265">Der Grund dafür ist, dass **Sie** muss in der Form Ihrer API, die nicht der Compiler-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="44c6a-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="44c6a-266">Obwohl der Compiler sehr gut an das Ableiten von Typen für Sie tun kann, ist es möglich, dass die Form Ihrer API-Änderung, wenn die standardbibliotheksinternen Elementen, denen in diesem Fall verwendet die Typen geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="44c6a-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="44c6a-267">Dies ist möglicherweise erwünscht, aber in eine grundlegende Änderung der API, die downstreamconsumer klicken Sie dann für den Umgang mit fast absoluter Sicherheit führt.</span><span class="sxs-lookup"><span data-stu-id="44c6a-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="44c6a-268">Stattdessen, wenn Sie explizit die Form der öffentlichen API steuern, dann können Sie diese Änderungen steuern.</span><span class="sxs-lookup"><span data-stu-id="44c6a-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="44c6a-269">In DDD-Terminologie kann dies als eine Anti-Corruption-Ebene aufgefasst werden.</span><span class="sxs-lookup"><span data-stu-id="44c6a-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="44c6a-270">Beachten Sie, sodass einen aussagekräftigen Namen zu Ihrer generischen Argumente.</span><span class="sxs-lookup"><span data-stu-id="44c6a-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="44c6a-271">Es sei denn, Sie tatsächlich generischen Code, der nicht spezifisch für eine bestimmte Domäne ist schreiben, können ein aussagekräftigen Namen andere Programmierer verstehen der Domäne, die sie gerade arbeiten.</span><span class="sxs-lookup"><span data-stu-id="44c6a-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="44c6a-272">Beispielsweise einen Typparameter, die mit dem Namen `'Document` in den Kontext für die Interaktion mit einem Dokument Datenbank ist es klarer, dass generische Dokumenttypen können, von der Funktion oder ein Element akzeptiert werden mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="44c6a-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="44c6a-273">Erwägen Sie die Benennung von generischen Typparametern mit PascalCase.</span><span class="sxs-lookup"><span data-stu-id="44c6a-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="44c6a-274">Dies ist die allgemeine Vorgehensweise Dinge in .NET ist die Verwendung von PascalCase anstelle von Snake_case oder CamelCase empfohlen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="44c6a-275">Schließlich ist automatische Verallgemeinerung nicht immer ein Segen für Personen gedacht, die f#- oder einer großen Codebasis.</span><span class="sxs-lookup"><span data-stu-id="44c6a-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="44c6a-276">Mithilfe von Komponenten, die generisch sind ist cognitive Aufwand.</span><span class="sxs-lookup"><span data-stu-id="44c6a-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="44c6a-277">Wenn automatisch darüber hinaus die generalisierte Funktionen werden nicht verwendet, mit verschiedenen Eingabetypen (Let nur, wenn sie z. B. verwendet werden sollen), dann keinen echten Vorteil, sie generisch zu diesem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="44c6a-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="44c6a-278">Berücksichtigen Sie immer, wenn der Code, den Sie schreiben tatsächlich profitieren von der generischen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="44c6a-279">Leistung</span><span class="sxs-lookup"><span data-stu-id="44c6a-279">Performance</span></span>

<span data-ttu-id="44c6a-280">F#-Werte sind unveränderlich, standardmäßig die Ihnen ermöglicht, bestimmte Klassen von Fehlern (insbesondere die im Zusammenhang mit Parallelität und Konkurrenz) zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="44c6a-280">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="44c6a-281">Allerdings kann in bestimmten Fällen um eine optimale (oder sogar sinnvoll) Effizienz Ausführungszeit oder speicherbelegungen, eine Spanne der Arbeit am besten implementiert werden mithilfe des direktes Veränderung des Zustands.</span><span class="sxs-lookup"><span data-stu-id="44c6a-281">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="44c6a-282">Dies ist möglich, in einer Basis Opt-in mit f# mit der `mutable` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="44c6a-282">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="44c6a-283">Allerdings verwenden der `mutable` in f# echtzeiteinschränkungen funktionale Reinheit fühlen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-283">However, use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="44c6a-284">Dies ist in Ordnung, wenn Sie anpassen, dass die Erwartungen Reinheit zu [referenzieller Transparenz](https://en.wikipedia.org/wiki/Referential_transparency).</span><span class="sxs-lookup"><span data-stu-id="44c6a-284">This is fine, if you adjust expectations from purity to [referential transparency](https://en.wikipedia.org/wiki/Referential_transparency).</span></span> <span data-ttu-id="44c6a-285">Referenzieller Transparenz - nicht Reinheit – ist das Ziel beim Schreiben von f#-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-285">Referential transparency - not purity - is the end goal when writing F# functions.</span></span> <span data-ttu-id="44c6a-286">Dadurch können Sie eine funktionsfähige-Schnittstelle über eine Mutation-basierte Implementierung für die Leistung kritischen Code zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="44c6a-286">This allows you to write a functional interface over a mutation-based implementation for performance critical code.</span></span>

### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="44c6a-287">Umschließen Sie änderbare Code in der unveränderlichen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="44c6a-287">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="44c6a-288">Mit referenzieller Transparenz als Ziel ist es wichtig, Code schreiben, der nicht die änderbare Tiefen des leistungskritischen Funktionen verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="44c6a-288">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="44c6a-289">Das folgende Codebeispiel implementiert die `Array.contains` Funktion in der F#-Kernbibliothek:</span><span class="sxs-lookup"><span data-stu-id="44c6a-289">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

```fsharp
[<CompiledName("Contains")>]
let inline contains value (array:'T[]) =
    checkNonNull "array" array
    let mutable state = false
    let mutable i = 0
    while not state && i < array.Length do
        state <- value = array.[i]
        i <- i + 1
    state
```

<span data-ttu-id="44c6a-290">Das Aufrufen dieser Funktion mehrmals ändert sich nicht auf das zugrunde liegende Array, noch ist es erforderlich, veränderlichen Zustand in Ihre Verwendung zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="44c6a-290">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="44c6a-291">Es ist Referenziell transparent, obwohl nahezu jede Codezeile darin Mutation verwendet.</span><span class="sxs-lookup"><span data-stu-id="44c6a-291">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="44c6a-292">Beachten Sie, änderbare Daten in Klassen kapseln</span><span class="sxs-lookup"><span data-stu-id="44c6a-292">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="44c6a-293">Im vorherige Beispiel verwendet eine einzelne Funktion, um Vorgänge mit änderbare Daten zu kapseln.</span><span class="sxs-lookup"><span data-stu-id="44c6a-293">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="44c6a-294">Dies ist nicht immer ausreichend für komplexere Sätze von Daten.</span><span class="sxs-lookup"><span data-stu-id="44c6a-294">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="44c6a-295">Beachten Sie die folgenden Sätze von Funktionen aus:</span><span class="sxs-lookup"><span data-stu-id="44c6a-295">Consider the following sets of functions:</span></span>

```fsharp
open System.Collections.Generic

let addToClosureTable (key, value) (t: Dictionary<_,_>) =
    if not (t.ContainsKey(key)) then
        t.Add(key, value)
    else
        t.[key] <- value

let closureTableCount (t: Dictionary<_,_>) = t.Count

let closureTableContains (key, value) (t: Dictionary<_, HashSet<_>>) =
    match t.TryGetValue(key) with
    | (true, v) -> v.Equals(value)
    | (false, _) -> false
```

<span data-ttu-id="44c6a-296">Macht die Mutation basierende Datenstruktur, dass Aufrufer für die Verwaltung zuständig sind, aber dieser Code ist leistungsfähig.</span><span class="sxs-lookup"><span data-stu-id="44c6a-296">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="44c6a-297">Dies kann innerhalb einer Klasse ohne zugrunde liegende Member umbrochen werden, die geändert werden können:</span><span class="sxs-lookup"><span data-stu-id="44c6a-297">This can be wrapped inside of a class with no underlying members that can change:</span></span>

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member __.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member __.Count = t.Count

    member __.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

<span data-ttu-id="44c6a-298">`Closure1Table` Kapselt die zugrunde liegende Mutation basierende Data-Struktur, wodurch nicht erzwungen, Aufrufe an die zugrunde liegende Datenstruktur zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="44c6a-298">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="44c6a-299">Klassen sind eine leistungsstarke Möglichkeit zum Kapseln von Daten und Routinen, die Mutation-basiert sind, ohne die Details für Aufrufer verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-299">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="44c6a-300">Bevorzugen `let mutable` zu Referenzzellen</span><span class="sxs-lookup"><span data-stu-id="44c6a-300">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="44c6a-301">Referenzzellen sind eine Möglichkeit, den Verweis auf einen Wert anstatt den Wert selbst darstellen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-301">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="44c6a-302">Obwohl sie für leistungskritische Code verwendet werden können, werden sie in der Regel nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-302">Although they can be used for performance-critical code, they are generally not recommended.</span></span> <span data-ttu-id="44c6a-303">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="44c6a-303">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="44c6a-304">Die Verwendung von einer Referenzzelle jetzt Täuschung"" alle nachfolgenden Code zu von dereferenziert und erneut auf die zugrunde liegenden Daten verweisen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-304">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="44c6a-305">Erwägen Sie stattdessen `let mutable`:</span><span class="sxs-lookup"><span data-stu-id="44c6a-305">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="44c6a-306">Abgesehen von der einzige Punkt der Veränderung in der Mitte der Lambda-Ausdruck, alle anderen Code, der berührt `acc` dazu in einer Weise, die nicht für die Verwendung einer normalen unterscheidet `let`-unveränderlichen Wert gebunden.</span><span class="sxs-lookup"><span data-stu-id="44c6a-306">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="44c6a-307">Dies wird im Laufe der Zeit ändern erleichtern.</span><span class="sxs-lookup"><span data-stu-id="44c6a-307">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="44c6a-308">Objektprogrammierung</span><span class="sxs-lookup"><span data-stu-id="44c6a-308">Object programming</span></span>

<span data-ttu-id="44c6a-309">F# bietet vollständige Unterstützung für Objekte und Konzepte für objektorientierte (OO).</span><span class="sxs-lookup"><span data-stu-id="44c6a-309">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="44c6a-310">Obwohl viele OO-Konzepte leistungsfähig und nützlich sind, sind nicht alle von ihnen erzielen Sie, wenn verwenden.</span><span class="sxs-lookup"><span data-stu-id="44c6a-310">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="44c6a-311">Die folgenden Listen bieten Anleitungen für die Kategorien von OO-Funktionen auf hoher Ebene.</span><span class="sxs-lookup"><span data-stu-id="44c6a-311">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="44c6a-312">**Sollten Sie diese Funktionen in vielen Situationen verwenden:**</span><span class="sxs-lookup"><span data-stu-id="44c6a-312">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="44c6a-313">Punktierte Schreibweise (`x.Length`)</span><span class="sxs-lookup"><span data-stu-id="44c6a-313">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="44c6a-314">Instanzmember</span><span class="sxs-lookup"><span data-stu-id="44c6a-314">Instance members</span></span>
* <span data-ttu-id="44c6a-315">Implizite Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="44c6a-315">Implicit constructors</span></span>
* <span data-ttu-id="44c6a-316">Statische Member</span><span class="sxs-lookup"><span data-stu-id="44c6a-316">Static members</span></span>
* <span data-ttu-id="44c6a-317">Indexers (`arr.[x]`)</span><span class="sxs-lookup"><span data-stu-id="44c6a-317">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="44c6a-318">Benannte und optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="44c6a-318">Named and Optional arguments</span></span>
* <span data-ttu-id="44c6a-319">Schnittstellen und schnittstellenimplementierungen</span><span class="sxs-lookup"><span data-stu-id="44c6a-319">Interfaces and interface implementations</span></span>

<span data-ttu-id="44c6a-320">**Greifen Sie nicht zuerst für diese Funktionen zu, jedoch mit Umsicht anzuwenden Sie, wenn sie zur Lösung eines Problems sind:**</span><span class="sxs-lookup"><span data-stu-id="44c6a-320">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="44c6a-321">Methodenüberladung</span><span class="sxs-lookup"><span data-stu-id="44c6a-321">Method overloading</span></span>
* <span data-ttu-id="44c6a-322">Gekapselten änderbaren Daten</span><span class="sxs-lookup"><span data-stu-id="44c6a-322">Encapsulated mutable data</span></span>
* <span data-ttu-id="44c6a-323">Operatoren für Typen</span><span class="sxs-lookup"><span data-stu-id="44c6a-323">Operators on types</span></span>
* <span data-ttu-id="44c6a-324">Auto-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="44c6a-324">Auto properties</span></span>
* <span data-ttu-id="44c6a-325">Implementieren von `IDisposable` und `IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="44c6a-325">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="44c6a-326">Erweiterungen des Typs</span><span class="sxs-lookup"><span data-stu-id="44c6a-326">Type extensions</span></span>
* <span data-ttu-id="44c6a-327">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="44c6a-327">Events</span></span>
* <span data-ttu-id="44c6a-328">Strukturen</span><span class="sxs-lookup"><span data-stu-id="44c6a-328">Structs</span></span>
* <span data-ttu-id="44c6a-329">Delegaten</span><span class="sxs-lookup"><span data-stu-id="44c6a-329">Delegates</span></span>
* <span data-ttu-id="44c6a-330">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="44c6a-330">Enums</span></span>

<span data-ttu-id="44c6a-331">**Vermeiden Sie diese Funktionen in der Regel, es sei denn, Sie sie verwenden müssen:**</span><span class="sxs-lookup"><span data-stu-id="44c6a-331">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="44c6a-332">Vererbung basierende Typenhierarchien und von implementierungsvererbung</span><span class="sxs-lookup"><span data-stu-id="44c6a-332">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="44c6a-333">NULL-Werte und `Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="44c6a-333">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="44c6a-334">Vererbung Komposition vorziehen</span><span class="sxs-lookup"><span data-stu-id="44c6a-334">Prefer composition over inheritance</span></span>

<span data-ttu-id="44c6a-335">[Aufbau im Laufe der Vererbung](https://en.wikipedia.org/wiki/Composition_over_inheritance) ist eine langfristige Vorgehensweise, die guter F#-Code entsprechen kann.</span><span class="sxs-lookup"><span data-stu-id="44c6a-335">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="44c6a-336">Das grundlegende Prinzip ist, dass Sie nicht verfügbar eine Basisklasse machen und Erzwingen von Aufrufern das erben von dieser Basisklasse um Funktionen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="44c6a-336">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="44c6a-337">Verwenden Sie Object-Ausdrücke, um Schnittstellen zu implementieren, wenn Sie eine Klasse nicht</span><span class="sxs-lookup"><span data-stu-id="44c6a-337">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="44c6a-338">[Objektausdrücke](../language-reference/object-expressions.md) die implementierte Schnittstelle können Sie zum Implementieren von Schnittstellen dynamisch an einen Wert ohne dafür innerhalb einer Klasse gebunden.</span><span class="sxs-lookup"><span data-stu-id="44c6a-338">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="44c6a-339">Dies ist praktisch, insbesondere dann, wenn Sie _nur_ müssen die Schnittstelle implementieren und müssen nicht für eine vollständige Klasse.</span><span class="sxs-lookup"><span data-stu-id="44c6a-339">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="44c6a-340">Beispielsweise sieht der Code, der ausgeführt wird, in [Ionide](http://ionide.io/) eine Korrektur Codeaktion bereitstellen, wenn Sie ein Symbol hinzugefügt haben, die Sie besitzen eine `open` -Anweisung für:</span><span class="sxs-lookup"><span data-stu-id="44c6a-340">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

```fsharp
    let private createProvider () =
        { new CodeActionProvider with
            member this.provideCodeActions(doc, range, context, ct) =
                let diagnostics = context.diagnostics
                let diagnostic = diagnostics |> Seq.tryFind (fun d -> d.message.Contains "Unused open statement")
                let res =
                    match diagnostic with
                    | None -> [||]
                    | Some d ->
                        let line = doc.lineAt d.range.start.line
                        let cmd = createEmpty<Command>
                        cmd.title <- "Remove unused open"
                        cmd.command <- "fsharp.unusedOpenFix"
                        cmd.arguments <- Some ([| doc |> unbox; line.range |> unbox; |] |> ResizeArray)
                        [|cmd |]
                res
                |> ResizeArray
                |> U2.Case1
        }
```

<span data-ttu-id="44c6a-341">Da bei der Interaktion mit der Visual Studio Code-API, keine Notwendigkeit für eine Klasse besteht, sind Object-Ausdrücke ein ideales Tool dafür.</span><span class="sxs-lookup"><span data-stu-id="44c6a-341">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="44c6a-342">Sie sind auch nützlich für Komponententests bereit, wenn Sie eine Schnittstelle mit Test-Routinen in einer ad-hoc-Weise stub werden sollen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-342">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="type-abbreviations"></a><span data-ttu-id="44c6a-343">Typabkürzungen</span><span class="sxs-lookup"><span data-stu-id="44c6a-343">Type Abbreviations</span></span>

<span data-ttu-id="44c6a-344">[Typabkürzungen](../language-reference/type-abbreviations.md) sind eine einfache Möglichkeit zum Zuweisen einer Bezeichnung in einen anderen Typ, z. B. einer Funktionssignatur oder einen komplexen Typ.</span><span class="sxs-lookup"><span data-stu-id="44c6a-344">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="44c6a-345">Der folgende Alias weist z. B. eine Bezeichnung, was erforderlich ist, definieren Sie eine Berechnung mit [CNTK](https://www.microsoft.com/en-us/cognitive-toolkit/), ein Deep learning-Bibliothek:</span><span class="sxs-lookup"><span data-stu-id="44c6a-345">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://www.microsoft.com/en-us/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="44c6a-346">Die `Computation` Name ist eine bequeme Möglichkeit, eine Funktion anzugeben, die der Signatur entspricht, es ist Aliasing.</span><span class="sxs-lookup"><span data-stu-id="44c6a-346">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="44c6a-347">Typabkürzungen wie folgt verwenden, ist praktisch und kompaktere Code ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="44c6a-347">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="44c6a-348">Vermeiden Sie die Verwendung von Typabkürzungen zur Darstellung von Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="44c6a-348">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="44c6a-349">Obwohl Typabkürzungen praktisch für das Festlegen einer Bezeichnung für Funktionssignaturen sind, können sie verwirrend sein, wenn abkürzen, von anderen Typen.</span><span class="sxs-lookup"><span data-stu-id="44c6a-349">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="44c6a-350">Betrachten Sie diese Abkürzung aus:</span><span class="sxs-lookup"><span data-stu-id="44c6a-350">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="44c6a-351">Dies kann auf verschiedene Weise verwirrend sein:</span><span class="sxs-lookup"><span data-stu-id="44c6a-351">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="44c6a-352">`BufferSize` ist keine Abstraktion. Es ist nur ein anderer Name für eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="44c6a-352">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="44c6a-353">Wenn `BufferSize` verfügbar gemacht wird in eine öffentliche API nutzen, es kann leicht falsch interpretiert werden, um mehr als nur bedeutet, dass `int`.</span><span class="sxs-lookup"><span data-stu-id="44c6a-353">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="44c6a-354">Im Allgemeinen Domänentypen mehrere Attribute werden und nicht primitive Typen wie `int`.</span><span class="sxs-lookup"><span data-stu-id="44c6a-354">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="44c6a-355">Diese Abkürzung verstößt gegen diese Annahme.</span><span class="sxs-lookup"><span data-stu-id="44c6a-355">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="44c6a-356">Die Schreibweise von `BufferSize` (PascalCase) bedeutet, dass es sich bei diesem Typ mehr Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="44c6a-356">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="44c6a-357">Dieser Alias bietet keine Verwaltungsaufgabe, die im Vergleich mit der Bereitstellung eines benannten Arguments an eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="44c6a-357">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="44c6a-358">Die Abkürzung wird nicht in die kompilierte IL-manifest; Es ist nur eine ganze Zahl ein, und dieser Alias ist ein Konstrukt während der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="44c6a-358">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) =
        ...
```

<span data-ttu-id="44c6a-359">Zusammenfassung der Fehlers mit Typabkürzungen ist, dass sie **nicht** Abstraktionen, die Typen, die sie mit der sind abkürzen von.</span><span class="sxs-lookup"><span data-stu-id="44c6a-359">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="44c6a-360">Im vorherigen Beispiel `BufferSize` ist einfach ein `int` mit keine zusätzlichen Daten, und alle Vorteile aus das Typensystem neben dem, was im Hintergrund `int` bereits verfügt.</span><span class="sxs-lookup"><span data-stu-id="44c6a-360">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>
