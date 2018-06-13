---
title: Codekonventionen [F#]
description: Erfahren Sie allgemeine Richtlinien und Idiome beim Schreiben von F#-Code.
ms.date: 05/14/2018
ms.openlocfilehash: f3d16f735ddc1901aeaa5ebb39e2fa2b70a3d836
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457981"
---
# <a name="f-coding-conventions"></a><span data-ttu-id="51e22-103">Codekonventionen [F#]</span><span class="sxs-lookup"><span data-stu-id="51e22-103">F# coding conventions</span></span>

<span data-ttu-id="51e22-104">Die folgenden Konventionen werden aus Erfahrung mit großen f# formuliert Codebasen.</span><span class="sxs-lookup"><span data-stu-id="51e22-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="51e22-105">Die [fünf Prinzipien der gute f#-Code](index.md#five-principles-of-good-f-code) sind die Grundlage für jede Empfehlung.</span><span class="sxs-lookup"><span data-stu-id="51e22-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="51e22-106">Sie beziehen sich auf die [f# Komponente Entwurfsrichtlinien](component-design-guidelines.md), jedoch gelten für alle f#-Code, nicht nur Komponenten wie Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="51e22-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="51e22-107">Organisieren von code</span><span class="sxs-lookup"><span data-stu-id="51e22-107">Organizing code</span></span>

<span data-ttu-id="51e22-108">F# bietet zwei Hauptmethoden zum Organisieren von Code: Module und Namespaces.</span><span class="sxs-lookup"><span data-stu-id="51e22-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="51e22-109">Diese sind ähnlich, aber Sie müssen die folgenden Unterschiede:</span><span class="sxs-lookup"><span data-stu-id="51e22-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="51e22-110">Namespaces werden als .NET Namespaces kompiliert.</span><span class="sxs-lookup"><span data-stu-id="51e22-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="51e22-111">Module werden als statische Klassen kompiliert.</span><span class="sxs-lookup"><span data-stu-id="51e22-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="51e22-112">Namespaces sind immer der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="51e22-112">Namespaces are always top level.</span></span> <span data-ttu-id="51e22-113">Module können auf der obersten Ebene und in anderen Modulen geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="51e22-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="51e22-114">Namespaces können mehrere Dateien umfassen.</span><span class="sxs-lookup"><span data-stu-id="51e22-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="51e22-115">Module können nicht.</span><span class="sxs-lookup"><span data-stu-id="51e22-115">Modules cannot.</span></span>
* <span data-ttu-id="51e22-116">Module können mit ergänzt werden `[<RequireQualifiedAccess>]` und `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="51e22-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="51e22-117">Die folgenden Richtlinien können Sie diese verwenden, um Ihren Code zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="51e22-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="51e22-118">Bevorzugen Sie Namespaces auf der obersten Ebene</span><span class="sxs-lookup"><span data-stu-id="51e22-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="51e22-119">Für jeden öffentlich nutzbar Code sind Namespaces bietet, Module, die auf der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="51e22-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="51e22-120">Da sie als .NET Namespaces kompiliert werden, sind sie kann von c# mit kein Problem.</span><span class="sxs-lookup"><span data-stu-id="51e22-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="51e22-121">Mithilfe der obersten Ebene treten möglicherweise anders aus, wenn Sie nur vom F#-aufgerufen, aber für C#-Consumern, können Aufrufer Katastrophenfall qualifizieren überrascht werden `MyClass` mit der `MyCode` Modul.</span><span class="sxs-lookup"><span data-stu-id="51e22-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="51e22-122">Sorgfältig anwenden `[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="51e22-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="51e22-123">Die `[<AutoOpen>]` Konstrukt kann dadurch den Rahmen, was für Aufrufer verfügbar ist, und die Antwort auf etwas Ursprung ist "magische".</span><span class="sxs-lookup"><span data-stu-id="51e22-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="51e22-124">Dies ist im Allgemeinen nicht empfehlenswert.</span><span class="sxs-lookup"><span data-stu-id="51e22-124">This is generally not a good thing.</span></span> <span data-ttu-id="51e22-125">Eine Ausnahme von dieser Regel wird die F#-Kernbibliothek selbst (obwohl dies auch etwas kontroverse ist).</span><span class="sxs-lookup"><span data-stu-id="51e22-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="51e22-126">Es ist jedoch zur Vereinfachung, wenn Sie Hilfsfunktionen für eine öffentliche API verfügen, die Sie separat von diesem öffentliche API organisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="51e22-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

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

<span data-ttu-id="51e22-127">Dadurch können Sie von der öffentlichen API einer Funktion ordnungsgemäß separate Implementierungsdetails ohne vollständig eine Hilfsprogramm jedes Mal zu qualifizieren Sie ihn aufrufen.</span><span class="sxs-lookup"><span data-stu-id="51e22-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="51e22-128">Darüber hinaus Verfügbarmachen von Erweiterungsmethoden und Ausdrucks-Generatoren auf Namespaceebene ausgedrückt werden kann problemlos mit `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="51e22-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="51e22-129">Verwendung `[<RequireQualifiedAccess>]` sichern können einen Konflikt mit Namen, und es unterstützt die Lesbarkeit der Meinung</span><span class="sxs-lookup"><span data-stu-id="51e22-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="51e22-130">Hinzufügen der `[<RequireQualifiedAccess>]` Attribut auf ein Modul gibt an, dass das Modul kann nicht geöffnet werden, dass Verweise auf die Elemente des Moduls explizite benötigen Zugriff qualifiziert.</span><span class="sxs-lookup"><span data-stu-id="51e22-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="51e22-131">Z. B. die `Microsoft.FSharp.Collections.List` -Modul ist dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="51e22-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="51e22-132">Dies ist hilfreich, wenn Funktionen und Werte im Modul Namen haben, die wahrscheinlich einen Konflikt mit Namen in anderen Modulen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="51e22-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="51e22-133">Einen qualifizierten Zugriff erfordern, kann erheblich die langfristige Verwaltbarkeit und die Evolvability einer Bibliothek erhöhen.</span><span class="sxs-lookup"><span data-stu-id="51e22-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="51e22-134">Sortieren `open` Anweisungen topologisch</span><span class="sxs-lookup"><span data-stu-id="51e22-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="51e22-135">In F# erläutert werden, die Reihenfolge der Deklarationen ist von Belang, einschließlich mit `open` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="51e22-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="51e22-136">Dies ist anders als bei c#, wobei die Auswirkung der `using` und `using static` ist unabhängig von der Reihenfolge der diese Anweisungen in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="51e22-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="51e22-137">In F# erläutert werden können Elemente, die in den Gültigkeitsbereich einer geöffnet Shadowing für andere bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="51e22-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="51e22-138">Dies bedeutet, dass dieser neuanordnung `open` alter-Anweisungen konnte die Bedeutung des Codes.</span><span class="sxs-lookup"><span data-stu-id="51e22-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="51e22-139">Als Ergebnis jeder beliebige Sortierung aller `open` Anweisungen (z. B. alphanumerisch) ist im Allgemeinen nicht empfohlen werden, müssen Sie sich im Verhalten etwas generieren, die Sie möglicherweise erwarten.</span><span class="sxs-lookup"><span data-stu-id="51e22-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is generally not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="51e22-140">Stattdessen empfehlen wir, dass sie zu sortieren [topologisch](https://en.wikipedia.org/wiki/Topological_sorting); d. h. sortieren Ihre `open` Anweisungen in der Reihenfolge, in der _Ebenen_ Ihres Systems definiert sind.</span><span class="sxs-lookup"><span data-stu-id="51e22-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="51e22-141">Auf diese Weise alphanumerische Sortierung in verschiedene topologische Ebenen kann ebenfalls berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="51e22-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="51e22-142">Als Beispiel sieht die topologische Sortierung für die F#-Compiler öffentliche API-Datei:</span><span class="sxs-lookup"><span data-stu-id="51e22-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

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

<span data-ttu-id="51e22-143">Beachten Sie, dass ein Zeilenumbruch topologische Ebenen mit jeder Ebene, die zu sortierenden alphanumerisch anschließend trennt.</span><span class="sxs-lookup"><span data-stu-id="51e22-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="51e22-144">Diese werden ordnungsgemäß Code ohne versehentlich shadowing Werte organisiert.</span><span class="sxs-lookup"><span data-stu-id="51e22-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="51e22-145">Verwenden Sie Klassen, um die Werte enthalten, die Nebeneffekte haben</span><span class="sxs-lookup"><span data-stu-id="51e22-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="51e22-146">Es gibt viele Male Wenn Nebeneffekte, wie einen Kontext auf eine Datenbank oder andere Remoteressource instanziieren initialisieren einen Wert aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="51e22-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="51e22-147">Es ist verlockend, u. a. in einem Modul zu initialisieren und in nachfolgenden Funktionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="51e22-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

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

<span data-ttu-id="51e22-148">Dies ist häufig nicht sinnvoll, Gründen:</span><span class="sxs-lookup"><span data-stu-id="51e22-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="51e22-149">Zunächst Anwendungskonfiguration abgelegt wird, in die Codebase mit `dep1` und `dep2`.</span><span class="sxs-lookup"><span data-stu-id="51e22-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="51e22-150">Dies ist schwer zu größeren Codebasen in verwalten.</span><span class="sxs-lookup"><span data-stu-id="51e22-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="51e22-151">Zweitens statisch initialisierte Daten sollten keine Werte enthalten, die nicht threadsicher sind, wenn die Komponente selbst mehrere Threads verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="51e22-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="51e22-152">Dies ist eindeutig durch verletzt `dep3`.</span><span class="sxs-lookup"><span data-stu-id="51e22-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="51e22-153">Schließlich wird Initialisierung des Moduls in einem statischen Konstruktor für die gesamte Kompilationseinheit kompiliert.</span><span class="sxs-lookup"><span data-stu-id="51e22-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="51e22-154">Wenn ein Fehler bei der Initialisierung der Let-Grenzwert in diesem Modul auftritt, Manifeste als eine `TypeInitializationException` , klicken Sie dann für die gesamte Lebensdauer der Anwendung zwischengespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="51e22-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="51e22-155">Dies kann nur schwer zu diagnostizieren sein.</span><span class="sxs-lookup"><span data-stu-id="51e22-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="51e22-156">In der Regel eine innere Ausnahme, der Sie versuchen, zu dem Grund besteht, aber wenn keine vorhanden ist, besteht keine mitteilen, was die Ursache ist.</span><span class="sxs-lookup"><span data-stu-id="51e22-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="51e22-157">Verwenden Sie eine einfache Klasse stattdessen nur zum Speichern von Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="51e22-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member __.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member __.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="51e22-158">Dies ermöglicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="51e22-158">This enables the following:</span></span>

1. <span data-ttu-id="51e22-159">Betätigen alle abhängigen Status außerhalb der API selbst.</span><span class="sxs-lookup"><span data-stu-id="51e22-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="51e22-160">Konfiguration kann nun außerhalb der API erfolgen.</span><span class="sxs-lookup"><span data-stu-id="51e22-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="51e22-161">Fehler bei der Initialisierung für abhängige Werte können nicht als manifest wahrscheinlich eine `TypeInitializationException`.</span><span class="sxs-lookup"><span data-stu-id="51e22-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="51e22-162">Die API ist jetzt einfacher zu testen.</span><span class="sxs-lookup"><span data-stu-id="51e22-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="51e22-163">Fehlerverwaltung</span><span class="sxs-lookup"><span data-stu-id="51e22-163">Error management</span></span>

<span data-ttu-id="51e22-164">Fehlerverwaltung in großen Systemen ist ein komplexer und vor-Unterfangen, und es sind keine Silber Nummerierung in Ihr System sichergestellt werden fehlertolerante und Verhalten sich auch.</span><span class="sxs-lookup"><span data-stu-id="51e22-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="51e22-165">Die folgenden Richtlinien bieten Anleitungen zum Navigieren in dieser schwierig Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="51e22-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="51e22-166">Darstellen Sie Sonderfälle und ungültigen Status in Ihrer Domäne systeminterne Typen</span><span class="sxs-lookup"><span data-stu-id="51e22-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="51e22-167">Mit [Unterscheidungs-Unions](../language-reference/discriminated-unions.md), f# bietet Ihnen die Möglichkeit, fehlerhafte Programmstatus in Ihrem Typsystem darstellen.</span><span class="sxs-lookup"><span data-stu-id="51e22-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="51e22-168">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="51e22-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="51e22-169">In diesem Fall stehen drei bekannte Methoden, die das Abbuchen von Geld von einem Bankkonto ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="51e22-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="51e22-170">Jeder Fehlerfall des Typs dargestellt wird und daher behandelt werden kann sicher in der gesamten Anwendung.</span><span class="sxs-lookup"><span data-stu-id="51e22-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="51e22-171">Im Allgemeinen, wenn Sie die verschiedenen Möglichkeiten modellieren können, dass etwas kann **fehlschlagen** in Ihrer Domäne, klicken Sie dann Fehlerbehandlungscode ist nicht mehr als behandelt etwas müssen Sie zusätzlich zum normalen Programmablauf behandeln.</span><span class="sxs-lookup"><span data-stu-id="51e22-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="51e22-172">Es ist einfach ein Bestandteil der normalen Programmablauf und nicht als **herausragende**.</span><span class="sxs-lookup"><span data-stu-id="51e22-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="51e22-173">Es gibt zwei Hauptvorteile dieser:</span><span class="sxs-lookup"><span data-stu-id="51e22-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="51e22-174">Es ist einfacher zu verwalten, während Ihre Domäne im Zeitverlauf ändert.</span><span class="sxs-lookup"><span data-stu-id="51e22-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="51e22-175">Für diesen Fehler sind einfacher zu Komponententest.</span><span class="sxs-lookup"><span data-stu-id="51e22-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="51e22-176">Verwenden Sie Ausnahmen aus, wenn der Fehler mit Typen dargestellt werden kann</span><span class="sxs-lookup"><span data-stu-id="51e22-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="51e22-177">Nicht alle Fehler können in einer Problemdomäne dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="51e22-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="51e22-178">Diese Art von Fehlern werden *herausragende* Natur, daher die Möglichkeit, auslösen und Abfangen von Ausnahmen in F# erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="51e22-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="51e22-179">Zunächst wird empfohlen, dass Sie Lesen der [Ausnahme Entwurfsrichtlinien](../../standard/design-guidelines/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="51e22-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="51e22-180">Diese gelten auch für f#.</span><span class="sxs-lookup"><span data-stu-id="51e22-180">These are also applicable to F#.</span></span>

<span data-ttu-id="51e22-181">In f# verfügbar im Rahmen der Auslösen von Ausnahmen mit die wichtigen Konstrukten sollten in der folgenden Reihenfolge der Priorität berücksichtigt werden:</span><span class="sxs-lookup"><span data-stu-id="51e22-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="51e22-182">Funktion</span><span class="sxs-lookup"><span data-stu-id="51e22-182">Function</span></span> | <span data-ttu-id="51e22-183">Syntax</span><span class="sxs-lookup"><span data-stu-id="51e22-183">Syntax</span></span> | <span data-ttu-id="51e22-184">Zweck</span><span class="sxs-lookup"><span data-stu-id="51e22-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="51e22-185">Löst ein `System.ArgumentNullException` mit dem angegebenen Argumentnamen.</span><span class="sxs-lookup"><span data-stu-id="51e22-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="51e22-186">Löst ein `System.ArgumentException` mit einem angegebenen Argumentnamen und die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="51e22-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="51e22-187">Löst ein `System.InvalidOperationException` mit der angegebenen Meldung.</span><span class="sxs-lookup"><span data-stu-id="51e22-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="51e22-188">Allgemeine Mechanismus zum Auslösen von Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="51e22-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="51e22-189">Löst ein `System.Exception` mit der angegebenen Meldung.</span><span class="sxs-lookup"><span data-stu-id="51e22-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="51e22-190">Löst ein `System.Exception` mit einer Meldung durch die Formatzeichenfolge und ihre Eingaben bestimmt.</span><span class="sxs-lookup"><span data-stu-id="51e22-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="51e22-191">Verwendung `nullArg`, `invalidArg` und `invalidOp` als Mechanismus zum lösen `ArgumentNullException`, `ArgumentException` und `InvalidOperationException` gegebenenfalls.</span><span class="sxs-lookup"><span data-stu-id="51e22-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="51e22-192">Die `failwith` und `failwithf` Funktionen sollten im Allgemeinen vermieden werden, da sie die Basis auslösen `Exception` eingeben, nicht für eine bestimmte Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="51e22-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="51e22-193">Gemäß der [Ausnahme Entwurfsrichtlinien](../../standard/design-guidelines/exceptions.md), finden Sie spezifischere Ausnahmen auslösen, sofern möglich werden sollen.</span><span class="sxs-lookup"><span data-stu-id="51e22-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="51e22-194">Mithilfe der Ausnahmebehandlung-syntax</span><span class="sxs-lookup"><span data-stu-id="51e22-194">Using exception-handling syntax</span></span>

<span data-ttu-id="51e22-195">F# unterstützt Ausnahme Muster über die `try...with` Syntax:</span><span class="sxs-lookup"><span data-stu-id="51e22-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="51e22-196">Abstimmen von Funktionen zur Ausführung eine Ausnahme mit dem Mustervergleich ausführen werden etwas komplizierter, wenn Sie den Code bereinigen aufbewahren möchten.</span><span class="sxs-lookup"><span data-stu-id="51e22-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="51e22-197">Eine solche Möglichkeit in diesem Fall ist die Verwendung [mit aktiven Mustern](../language-reference/active-patterns.md) als Mittel zum Funktion für den Fehlerfall eines mit einer Ausnahme selbst umgebenden.</span><span class="sxs-lookup"><span data-stu-id="51e22-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="51e22-198">Beispielsweise können Sie eine API nutzen, die, wenn er eine Ausnahme auslöst, wertvollen Informationen in den Ausnahmemetadaten umschließt.</span><span class="sxs-lookup"><span data-stu-id="51e22-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="51e22-199">Entpacken einen nützlichsten Wert im Text der Ausnahme aufgezeichnete in das aktive Muster und zurückgeben, dass der Wert in einigen Situationen hilfreich sein kann.</span><span class="sxs-lookup"><span data-stu-id="51e22-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="51e22-200">Verwenden Sie keine monadische Fehlerbehandlung um Ausnahmen zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="51e22-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="51e22-201">Ausnahmen werden als etwas Taboo bei der funktionalen Programmierung betrachtet.</span><span class="sxs-lookup"><span data-stu-id="51e22-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="51e22-202">In der Tat verletzen Ausnahmen Reinheit, sodass sie nicht ganz funktionale berücksichtigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="51e22-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="51e22-203">Allerdings wird dadurch die Realität, in dem Code ausgeführt werden muss, und dieser Fehler können auftreten, Laufzeit ignoriert.</span><span class="sxs-lookup"><span data-stu-id="51e22-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="51e22-204">Schreiben Sie Code in der Regel auf der Annahme, dass die meisten Dinge reinen weder total minimieren, unerfreuliche überraschungen sind.</span><span class="sxs-lookup"><span data-stu-id="51e22-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="51e22-205">Es ist wichtig, die folgenden Core Stärken/Aspekte von Ausnahmen im Hinblick auf ihre Relevanz und Eignung in der .NET Common Language Runtime und das sprachübergreifende Ökosystem als Ganzes zu berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="51e22-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="51e22-206">Sie enthalten detaillierte Diagnoseinformationen, die sehr hilfreich ist, wenn ein Problem debuggen.</span><span class="sxs-lookup"><span data-stu-id="51e22-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="51e22-207">Durch die Common Language Runtime und anderen gut verständlich sind.</span><span class="sxs-lookup"><span data-stu-id="51e22-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="51e22-208">Reduzierung der erhebliche Textbaustein im Vergleich zu Code, der eine Methode zum verlässt *vermeiden* Ausnahmen durch die Implementierung einer Teilmenge der ihre Semantik auf Ad-hoc-Basis.</span><span class="sxs-lookup"><span data-stu-id="51e22-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="51e22-209">Diese dritte Punkt ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="51e22-209">This third point is critical.</span></span> <span data-ttu-id="51e22-210">Für nicht trivialen komplexe Operationen ausführen kann wegen eines Fehlers beim Verwenden von Ausnahmen beim Umgang mit Datenstrukturen, z. B. Dies führen:</span><span class="sxs-lookup"><span data-stu-id="51e22-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="51e22-211">Dies kann problemlos zu instabilen Code wie einen Mustervergleich für "stringly typisierte" Fehler führen:</span><span class="sxs-lookup"><span data-stu-id="51e22-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="51e22-212">Darüber hinaus kann es sein verlockend, jede Ausnahme in der Wunsch nach einer Funktion "einfache" behalten, die ein "nützlicher" zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="51e22-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="51e22-213">Leider `tryReadAllText` kann zahlreiche basierte auf einer Vielzahl von Vorgängen, die in einem Dateisystem durchgeführt kann Ausnahmen auslösen, und dieser Code verwirft sofort jegliche Informationen, was tatsächlich in Ihrer Umgebung falschen passiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="51e22-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="51e22-214">Wenn Sie diesen Code mit einem Ergebnistyp ersetzen, können Sie zurück zur Analyse des "stringly typisierte" Fehler:</span><span class="sxs-lookup"><span data-stu-id="51e22-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

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

<span data-ttu-id="51e22-215">Und platziert das Ausnahmeobjekt selbst in die `Error` Konstruktor nur erzwingt, dass Sie den Ausnahmetyp an der Aufrufsite anstatt in die Funktion ordnungsgemäß behandeln.</span><span class="sxs-lookup"><span data-stu-id="51e22-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="51e22-216">Dadurch effektiv erstellt überprüfte Ausnahmen, die für den Umgang mit als Aufrufer einer API offenkundig unfun sind.</span><span class="sxs-lookup"><span data-stu-id="51e22-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="51e22-217">Eine gute Alternative zur in den Beispielen oben wird zum Abfangen von *bestimmte* Ausnahmen und der Rückgabewert keinen sinnvollen Wert im Kontext der diese Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="51e22-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="51e22-218">Wenn Sie ändern die `tryReadAllText` -Funktion wie folgt `None` hat mehr Bedeutung:</span><span class="sxs-lookup"><span data-stu-id="51e22-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="51e22-219">Anstelle von funktioniert wie eine sammelfehlermeldung, ausführt diese Funktion jetzt ordnungsgemäß die Groß-/Kleinschreibung, wenn eine Datei wurde nicht gefunden, und weisen Sie diesem Bedeutung eine Rückgabe.</span><span class="sxs-lookup"><span data-stu-id="51e22-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="51e22-220">Dieser Rückgabewert kann diese auftretender Fehler beim Zuordnen nicht verwerfen alle Kontextinformationen oder Erzwingen der Aufrufer für den Umgang mit einem Fall, die möglicherweise nicht relevant ist an diesem Punkt im Code.</span><span class="sxs-lookup"><span data-stu-id="51e22-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="51e22-221">Typen wie `Result<'Success, 'Error>` eignen sich für Standardvorgänge, in dem sie geschachtelt sind nicht, und optionale f#-Typen sind ideal für die Darstellung etwas entweder möglich *etwas* oder *nichts*.</span><span class="sxs-lookup"><span data-stu-id="51e22-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="51e22-222">Sie sind kein Ersatz für Ausnahmen, jedoch und sollte nicht in einem Versuch zum Ersetzen von Ausnahmen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="51e22-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="51e22-223">Stattdessen sollten sie Umsicht Adresse bestimmte Aspekte der Ausnahme und die Richtlinie für die Verwaltung targeted angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="51e22-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="51e22-224">Teilweise Anwendung und frei von Punkt-Programmierung</span><span class="sxs-lookup"><span data-stu-id="51e22-224">Partial application and point-free programming</span></span>

<span data-ttu-id="51e22-225">F# unterstützt teilweise Anwendung, und somit auf verschiedene Arten der Programmierung in einem Format mit Punkt freizugeben.</span><span class="sxs-lookup"><span data-stu-id="51e22-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="51e22-226">Dies kann für die Wiederverwendung von Code in einem Modul oder die Implementierung von etwas von Vorteil sein, allerdings handelt es sich im Allgemeinen nicht etwas, um die öffentlich verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="51e22-226">This can be beneficial for code reuse within a module or the implementation of something, but it is generally not something to expose publicly.</span></span> <span data-ttu-id="51e22-227">Im Allgemeinen Punkt frei Programmierung ist ein Vorteil, dass es in und von sich selbst und kann ein großes cognitive Hindernis für Personen, die im entsprechenden Stil nicht mehr über sind hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="51e22-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="51e22-228">Verwenden Sie keine teilweise Anwendung und in öffentlichen APIs currying</span><span class="sxs-lookup"><span data-stu-id="51e22-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="51e22-229">Mit wenig Ausnahme kann die Verwendung der partiellen Anwendung von öffentlichen APIs für den Consumer verwirrend sein.</span><span class="sxs-lookup"><span data-stu-id="51e22-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="51e22-230">In der Regel `let`-gebundenen Werte in f#-Code sind **Werte**, nicht **Funktion Werte**.</span><span class="sxs-lookup"><span data-stu-id="51e22-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="51e22-231">Vermischen von Werten und Funktionswerten kann dazu führen, speichern eine kleine Anzahl von Codezeilen für relativ viel cognitive Mehraufwand, insbesondere dann, wenn Sie z. B. mit Operatoren kombiniert `>>` um Funktionen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="51e22-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="51e22-232">Betrachten Sie die Auswirkungen auf die Tools für die Programmierung Punkt frei</span><span class="sxs-lookup"><span data-stu-id="51e22-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="51e22-233">Funktionen mit Currying ihre Argumente nicht beschriftet.</span><span class="sxs-lookup"><span data-stu-id="51e22-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="51e22-234">Dies hat Auswirkungen auf die Tools.</span><span class="sxs-lookup"><span data-stu-id="51e22-234">This has tooling implications.</span></span> <span data-ttu-id="51e22-235">Betrachten Sie die folgenden zwei Funktionen:</span><span class="sxs-lookup"><span data-stu-id="51e22-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="51e22-236">Beide sind gültige Funktionen jedoch `funcWithApplication` ist eine Funktion, mit Currying.</span><span class="sxs-lookup"><span data-stu-id="51e22-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="51e22-237">Wenn Sie ihre Typen in einem Editor zeigen, wird Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="51e22-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="51e22-238">An der Aufrufsite QuickInfos in Tools wie Visual Studio nicht erhalten Sie aussagekräftige Informationen, was die `string` und `int` Eingabetypen tatsächlich darstellen.</span><span class="sxs-lookup"><span data-stu-id="51e22-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="51e22-239">Treten Punkt frei Code wie `funcWithApplication` öffentlich nutzbar ist, es wird empfohlen, einen vollständigen η-Erweiterung vornehmen, sodass Tools wählen Sie aussagekräftige Namen für die Argumente an bis kann.</span><span class="sxs-lookup"><span data-stu-id="51e22-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="51e22-240">Darüber hinaus kann Debugcode Punkt frei, wenn nicht sogar unmöglich schwierig sein.</span><span class="sxs-lookup"><span data-stu-id="51e22-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="51e22-241">Tools zum Debuggen basieren auf Werte, die an den Namen gebunden (z. B. `let` Bindungen), um Sie in der Mitte Zwischenwerte durch die Ausführung überprüfen.</span><span class="sxs-lookup"><span data-stu-id="51e22-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="51e22-242">Wenn der Code keine Werte überprüfen aufweist, wird nichts zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="51e22-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="51e22-243">In der Zukunft Debugtools weiterentwickelt kann, um diese Werte basierend auf der zuvor ausgeführten Pfade zu synthetisieren, aber es ist nicht ratsam, Ihre Suchergebnisse auf hedge *potenzielle* Funktionalität Debuggen.</span><span class="sxs-lookup"><span data-stu-id="51e22-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="51e22-244">Betrachten Sie teilweise Anwendung als eine Technik zum Reduzieren der internen Textbaustein</span><span class="sxs-lookup"><span data-stu-id="51e22-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="51e22-245">Im Gegensatz zu vorherigen Punkt ist teilweise Anwendung ein traumhaftes Tool zur Reduzierung der Textbaustein innerhalb einer Anwendung oder die tieferen Besonderheiten der API.</span><span class="sxs-lookup"><span data-stu-id="51e22-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="51e22-246">Es kann für die Implementierung der etwas komplizierteren APIs, wobei Textbaustein häufig einen Bereich mit den für den Umgang mit ist für die Komponententests hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="51e22-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="51e22-247">Z. B. der folgende Code zeigt, wie Sie erreichen können, welche die meisten Mockframeworks Ihnen ohne externe Abhängigkeit solches Framework und einer verknüpften erfahren, dass die API Werk.</span><span class="sxs-lookup"><span data-stu-id="51e22-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="51e22-248">Betrachten Sie beispielsweise die folgende Lösung Topografie aus:</span><span class="sxs-lookup"><span data-stu-id="51e22-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="51e22-249">`ImplementationLogic.fsproj` Code kann z. B. verfügbar machen:</span><span class="sxs-lookup"><span data-stu-id="51e22-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member __.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="51e22-250">UnitTests `Transactions.doTransaction` in `ImplementationLogic.Tests.fspoj` ist einfach:</span><span class="sxs-lookup"><span data-stu-id="51e22-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fspoj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="51e22-251">Anwenden von teilweise `doTransaction` Objekt mit einem mocking Kontext können Sie die Funktion in allen Komponententests aufrufen, ohne einen mocked Kontext jedes Mal erstellen:</span><span class="sxs-lookup"><span data-stu-id="51e22-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

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

<span data-ttu-id="51e22-252">Dieses Verfahren sollten auf die gesamte Codebase nicht universell angewendet, aber es ist eine gute Möglichkeit, Textbausteine für komplizierte Besonderheiten und diese Mechanismen für die Komponententests zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="51e22-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="51e22-253">Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="51e22-253">Access control</span></span>

<span data-ttu-id="51e22-254">F#-verfügt über mehrere Optionen für [Zugriffssteuerung](../language-reference/access-control.md), geerbt vom was in der .NET Common Language Runtime verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="51e22-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="51e22-255">Diese sind nicht nur für Typen verwendet werden – verwenden sie für Funktionen zu.</span><span class="sxs-lookup"><span data-stu-id="51e22-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="51e22-256">Bevorzugen nicht-`public` Typen und Member, bis Sie öffentlich werden benötigt.</span><span class="sxs-lookup"><span data-stu-id="51e22-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="51e22-257">Dadurch wird minimiert auch, welche Consumer-Paar an</span><span class="sxs-lookup"><span data-stu-id="51e22-257">This also minimizes what consumers couple to</span></span>
* <span data-ttu-id="51e22-258">Bemühen, behalten Sie alle Hilfsfunktionen `private`.</span><span class="sxs-lookup"><span data-stu-id="51e22-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="51e22-259">Betrachten Sie die Verwendung von `[<AutoOpen>]` auf eine private Hilfsfunktionen, wenn zahlreiche versetzten-Modul.</span><span class="sxs-lookup"><span data-stu-id="51e22-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="51e22-260">Typrückschluss und Generika</span><span class="sxs-lookup"><span data-stu-id="51e22-260">Type inference and generics</span></span>

<span data-ttu-id="51e22-261">Typrückschluss sparen Sie viel Textbaustein eingeben.</span><span class="sxs-lookup"><span data-stu-id="51e22-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="51e22-262">Und automatische Verallgemeinerung in f#-Compiler können Sie allgemeineren Code mit fast keine zusätzlichen Aufwand ihrerseits zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="51e22-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="51e22-263">Diese Funktionen sind jedoch nicht universell gut.</span><span class="sxs-lookup"><span data-stu-id="51e22-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="51e22-264">Betrachten Sie beschriften Argumentnamen mit expliziten Typen in öffentlichen APIs und verlassen Sie sich nicht auf den Typrückschluss für diesen.</span><span class="sxs-lookup"><span data-stu-id="51e22-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="51e22-265">Der Grund dafür ist, dass **Sie** Kontrolle über die Form von Ihrer API, die nicht vom Compiler werden sollte.</span><span class="sxs-lookup"><span data-stu-id="51e22-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="51e22-266">Obwohl der Compiler sehr gut an Ableiten von Typen für Sie ausführen kann, ist es möglich, dass die Form der API ändern, wenn die Mechanismen, die auf basiert Typen geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="51e22-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="51e22-267">Dies kann sein, was Sie möchten, aber Befehlsbeispiel führt zu einer Änderung der wichtige-API, für die downstreamconsumer dann für den Umgang mit.</span><span class="sxs-lookup"><span data-stu-id="51e22-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="51e22-268">Stattdessen, wenn Sie die Form des Ihre öffentliche API explizit steuern, dann können Sie diese Änderungen steuern.</span><span class="sxs-lookup"><span data-stu-id="51e22-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="51e22-269">DDD ausgedrückt kann dies als eine Schicht Anti-Beschädigung betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="51e22-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="51e22-270">Nennen Sie einen aussagekräftigen Namen zu Ihrer generischen Argumenten.</span><span class="sxs-lookup"><span data-stu-id="51e22-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="51e22-271">Es sei denn, Sie tatsächlich generischen Code, der nicht spezifisch für eine bestimmte Domäne ist schreiben, können ein aussagekräftigen Namen andere Programmierer verstehen die Domäne, in dem sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="51e22-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="51e22-272">Beispielsweise einen Typparameter mit dem Namen `'Document` im Kontext der Interaktion mit einem Dokument Datenbank erleichtert klarer, dass generische Dokumenttypen können, von der Funktion oder einen Member akzeptiert werden mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="51e22-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="51e22-273">Erwägen Sie die Benennung der generische Typparameter mit "PascalCase".</span><span class="sxs-lookup"><span data-stu-id="51e22-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="51e22-274">Dies ist die allgemeine Möglichkeit, die Aktionen in .NET, daher wird empfohlen, dass die Verwendung von "PascalCase" anstatt Snake_case oder camelCase ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="51e22-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="51e22-275">Schließlich ist automatische Verallgemeinerung nicht immer ein Segen für Personen, die F#- oder einer großen Codebasis nicht vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="51e22-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="51e22-276">Bei der Verwendung von Komponenten, die generisch sind ist cognitive Aufwand.</span><span class="sxs-lookup"><span data-stu-id="51e22-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="51e22-277">Wenn automatisch darüber hinaus die generalisierte Funktionen werden nicht mit verschiedenen Eingabetypen (Let allein, wenn sie z. B. verwendet werden soll) verwendet, wird keine echte Vorteil diese generischen zu diesem Zeitpunkt wird.</span><span class="sxs-lookup"><span data-stu-id="51e22-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="51e22-278">In Betracht gezogen Sie, wenn der Code, den Sie schreiben tatsächlich nicht generischen profitieren.</span><span class="sxs-lookup"><span data-stu-id="51e22-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="51e22-279">Leistung</span><span class="sxs-lookup"><span data-stu-id="51e22-279">Performance</span></span>

<span data-ttu-id="51e22-280">F#-Werte sind unveränderlich ist, wird standardmäßig die Ihnen ermöglicht, bestimmte Klassen von Fehlern (insbesondere die im Zusammenhang mit Parallelität und Parallelität) zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="51e22-280">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="51e22-281">Allerdings kann in bestimmten Fällen um eine optimale (oder sogar sinnvoll) Effizienz Ausführungszeit oder speicherbelegungen zu erzielen eine Spanne der Arbeit am besten implementiert werden mithilfe von direkten Mutation des Status.</span><span class="sxs-lookup"><span data-stu-id="51e22-281">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="51e22-282">Dies ist möglich, in ein Opt-in-Basis mit f# mit dem `mutable` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="51e22-282">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="51e22-283">Allerdings verwenden der `mutable` in f# entwurfsseitig funktionale Reinheit fühlen.</span><span class="sxs-lookup"><span data-stu-id="51e22-283">However, use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="51e22-284">Dies ist in Ordnung, wenn Sie Erwartungen aus Reinheit zum Anpassen [referenzielle Transparenz](https://en.wikipedia.org/wiki/Referential_transparency).</span><span class="sxs-lookup"><span data-stu-id="51e22-284">This is fine, if you adjust expectations from purity to [referential transparency](https://en.wikipedia.org/wiki/Referential_transparency).</span></span> <span data-ttu-id="51e22-285">Referenzielle Transparenz - nicht Reinheit - ist Endziel es beim Schreiben von f#-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="51e22-285">Referential transparency - not purity - is the end goal when writing F# functions.</span></span> <span data-ttu-id="51e22-286">Dadurch können Sie eine funktionsfähige Schnittstelle über einer Mutation-basierten Implementierung für Leistung wichtigen Code zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="51e22-286">This allows you to write a functional interface over a mutation-based implementation for performance critical code.</span></span>

### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="51e22-287">Umschließen Sie änderbare Code unveränderlichen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="51e22-287">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="51e22-288">Mit referenziellen Transparenz als Ziel ist es wichtig, Code zu schreiben, die nicht die änderbare Tiefen leistungskritischen Funktionen zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="51e22-288">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="51e22-289">Z. B. der folgende code implementiert die `Array.contains` -Funktion in der f#-Kernbibliothek:</span><span class="sxs-lookup"><span data-stu-id="51e22-289">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

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

<span data-ttu-id="51e22-290">Das Aufrufen dieser Funktion mehrmals ändert sich nicht auf das zugrunde liegende Array, noch ist es erforderlich, alle änderbaren Zustand in Ihre Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="51e22-290">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="51e22-291">Es ist Referenziell transparent, obwohl fast jede Codezeile darin Mutation verwendet.</span><span class="sxs-lookup"><span data-stu-id="51e22-291">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="51e22-292">Betrachten Sie änderbare Daten in Klassen kapseln</span><span class="sxs-lookup"><span data-stu-id="51e22-292">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="51e22-293">Im vorherige Beispiel verwendet eine einzelne Funktion, um Vorgänge mithilfe änderbare Daten kapseln.</span><span class="sxs-lookup"><span data-stu-id="51e22-293">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="51e22-294">Dies ist nicht immer ausreichend für komplexe Datenmengen.</span><span class="sxs-lookup"><span data-stu-id="51e22-294">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="51e22-295">Betrachten Sie die folgenden Sätze von Funktionen aus:</span><span class="sxs-lookup"><span data-stu-id="51e22-295">Consider the following sets of functions:</span></span>

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

<span data-ttu-id="51e22-296">Dieser Code ist leistungsfähiger, aber macht die Mutation basierende Datenstruktur, dass Aufrufer für die Verwaltung zuständig sind.</span><span class="sxs-lookup"><span data-stu-id="51e22-296">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="51e22-297">Dies kann innerhalb einer Klasse ohne zugrunde liegende Member umbrochen werden, die geändert werden kann:</span><span class="sxs-lookup"><span data-stu-id="51e22-297">This can be wrapped inside of a class with no underlying members that can change:</span></span>

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

<span data-ttu-id="51e22-298">`Closure1Table` Kapselt die zugrunde liegende Mutation kennwortbasierten Datenschutzdienst-Struktur, nicht erzwingen Aufrufer auf die zugrunde liegende Datenstruktur zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="51e22-298">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="51e22-299">Klassen sind eine leistungsfähige Möglichkeit zum Kapseln von Daten und Routinen, die Mutation-basiert sind, ohne die Details für Aufrufer verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="51e22-299">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="51e22-300">Bevorzugen `let mutable` zu Referenzzellen</span><span class="sxs-lookup"><span data-stu-id="51e22-300">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="51e22-301">Referenzzellen sind eine Möglichkeit, den Verweis auf einen Wert anstatt den Wert selbst darstellen.</span><span class="sxs-lookup"><span data-stu-id="51e22-301">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="51e22-302">Obwohl sie für leistungskritische Code verwendet werden können, werden sie im Allgemeinen nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="51e22-302">Although they can be used for performance-critical code, they are generally not recommended.</span></span> <span data-ttu-id="51e22-303">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="51e22-303">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="51e22-304">Die Verwendung von einer Referenzzelle Täuschung"" alle nachfolgenden Code zu dereferenzieren und verweisen auf die zugrunde liegenden Daten erneut.</span><span class="sxs-lookup"><span data-stu-id="51e22-304">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="51e22-305">Erwägen Sie stattdessen `let mutable`:</span><span class="sxs-lookup"><span data-stu-id="51e22-305">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="51e22-306">Abgesehen von den einzelnen Fehlerpunkt Mutation in der Mitte der Lambda-Ausdruck, alle anderen Code, der berührt `acc` können dies in einer Weise, die nicht für die Verwendung einer normalen unterscheidet tun `let`-unveränderlichen Wert gebunden.</span><span class="sxs-lookup"><span data-stu-id="51e22-306">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="51e22-307">Dies wird im Laufe der Zeit ändern vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="51e22-307">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="51e22-308">Objekt-Programmierung</span><span class="sxs-lookup"><span data-stu-id="51e22-308">Object programming</span></span>

<span data-ttu-id="51e22-309">F# bietet vollständige Unterstützung für Objekte und Konzepte für objektorientierte (OO).</span><span class="sxs-lookup"><span data-stu-id="51e22-309">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="51e22-310">Obwohl viele OO Konzepte leistungsstarke und nützlich sind, sind nicht alle von ihnen sich perfekt für verwenden.</span><span class="sxs-lookup"><span data-stu-id="51e22-310">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="51e22-311">Die folgenden Listen bieten Anleitungen zu den Kategorien von OO Funktionen auf hoher Ebene.</span><span class="sxs-lookup"><span data-stu-id="51e22-311">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="51e22-312">**Sollten Sie diese Funktionen in vielen Situationen verwenden:**</span><span class="sxs-lookup"><span data-stu-id="51e22-312">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="51e22-313">Punktnotation (`x.Length`)</span><span class="sxs-lookup"><span data-stu-id="51e22-313">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="51e22-314">Instanzmember</span><span class="sxs-lookup"><span data-stu-id="51e22-314">Instance members</span></span>
* <span data-ttu-id="51e22-315">Implizite Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="51e22-315">Implicit constructors</span></span>
* <span data-ttu-id="51e22-316">Statische Member</span><span class="sxs-lookup"><span data-stu-id="51e22-316">Static members</span></span>
* <span data-ttu-id="51e22-317">Indexer-Notation (`arr.[x]`)</span><span class="sxs-lookup"><span data-stu-id="51e22-317">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="51e22-318">Benannte und optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="51e22-318">Named and Optional arguments</span></span>
* <span data-ttu-id="51e22-319">Schnittstellen und schnittstellenimplementierungen</span><span class="sxs-lookup"><span data-stu-id="51e22-319">Interfaces and interface implementations</span></span>

<span data-ttu-id="51e22-320">**Erreichen Sie nicht zuerst für diese Funktionen, aber Umsicht anzuwenden Sie, wenn sie zur Lösung eines Problems sind:**</span><span class="sxs-lookup"><span data-stu-id="51e22-320">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="51e22-321">Methodenüberladung</span><span class="sxs-lookup"><span data-stu-id="51e22-321">Method overloading</span></span>
* <span data-ttu-id="51e22-322">Gekapselten änderbaren Daten</span><span class="sxs-lookup"><span data-stu-id="51e22-322">Encapsulated mutable data</span></span>
* <span data-ttu-id="51e22-323">Operatoren auf Typen</span><span class="sxs-lookup"><span data-stu-id="51e22-323">Operators on types</span></span>
* <span data-ttu-id="51e22-324">Auto-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="51e22-324">Auto properties</span></span>
* <span data-ttu-id="51e22-325">Implementieren von `IDisposable` und `IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="51e22-325">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="51e22-326">Typerweiterungen</span><span class="sxs-lookup"><span data-stu-id="51e22-326">Type extensions</span></span>
* <span data-ttu-id="51e22-327">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="51e22-327">Events</span></span>
* <span data-ttu-id="51e22-328">Strukturen</span><span class="sxs-lookup"><span data-stu-id="51e22-328">Structs</span></span>
* <span data-ttu-id="51e22-329">Delegaten</span><span class="sxs-lookup"><span data-stu-id="51e22-329">Delegates</span></span>
* <span data-ttu-id="51e22-330">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="51e22-330">Enums</span></span>

<span data-ttu-id="51e22-331">**Vermeiden Sie diese Funktionen in der Regel, sofern Sie sie verwenden müssen:**</span><span class="sxs-lookup"><span data-stu-id="51e22-331">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="51e22-332">Vererbung basierende Typenhierarchien und implementierungsvererbung</span><span class="sxs-lookup"><span data-stu-id="51e22-332">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="51e22-333">NULL-Werte und `Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="51e22-333">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="51e22-334">Ziehen Sie Komposition Vererbung</span><span class="sxs-lookup"><span data-stu-id="51e22-334">Prefer composition over inheritance</span></span>

<span data-ttu-id="51e22-335">[Komposition über Vererbung](https://en.wikipedia.org/wiki/Composition_over_inheritance) ist ein langjähriges-Idiom, die gute f#-Code entsprechen kann.</span><span class="sxs-lookup"><span data-stu-id="51e22-335">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="51e22-336">Fundamentales Prinzip ist, sollten nicht verfügbar eine Basisklasse machen und zum Erzwingen von Aufrufern das erben von dieser Basisklasse, Funktionalität zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="51e22-336">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="51e22-337">Verwenden Sie Objektausdrücke, um Schnittstellen zu implementieren, wenn Sie eine Klasse benötigen</span><span class="sxs-lookup"><span data-stu-id="51e22-337">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="51e22-338">[Objektausdrücke](../language-reference/object-expressions.md) ermöglichen es Ihnen, im Handumdrehen Schnittstellen implementieren die implementierte Schnittstelle auf einen Wert binden, ohne dass dazu innerhalb einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="51e22-338">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="51e22-339">Dies ist zweckmäßig, insbesondere dann, wenn Sie _nur_ müssen die Schnittstelle implementieren und keine Notwendigkeit für eine vollständige-Klasse.</span><span class="sxs-lookup"><span data-stu-id="51e22-339">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="51e22-340">Hier ist z. B. der Code, der ausgeführt wird, in [Ionide](http://ionide.io/) eine Update-Codeaktion bereitstellen, wenn Sie ein Symbol hinzugefügt haben, die Sie besitzen eine `open` -Anweisung:</span><span class="sxs-lookup"><span data-stu-id="51e22-340">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

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

<span data-ttu-id="51e22-341">Da bei der Interaktion mit den Visual Studio Code-API, keine Notwendigkeit für eine Klasse besteht, sind Objektausdrücke ein ideales Tool dafür.</span><span class="sxs-lookup"><span data-stu-id="51e22-341">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="51e22-342">Sie sind auch nützlich für Komponententests bereit, wenn Sie, eine Schnittstelle mit Test-Routinen in einer ad-hoc-Weise stub möchten.</span><span class="sxs-lookup"><span data-stu-id="51e22-342">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="type-abbreviations"></a><span data-ttu-id="51e22-343">Typabkürzungen</span><span class="sxs-lookup"><span data-stu-id="51e22-343">Type Abbreviations</span></span>

<span data-ttu-id="51e22-344">[Typabkürzungen](../language-reference/type-abbreviations.md) sind eine einfache Möglichkeit, einen anderen Typ, z. B. einer Funktionssignatur oder ein komplexer Typ eine Bezeichnung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="51e22-344">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="51e22-345">Beispielsweise weist der folgende Alias eine Bezeichnung, was erforderlich ist, um eine Berechnung mit definieren [CNTK](https://www.microsoft.com/cognitive-toolkit/), eine umfassende learning-Bibliothek:</span><span class="sxs-lookup"><span data-stu-id="51e22-345">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://www.microsoft.com/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="51e22-346">Die `Computation` Name ist eine einfache Möglichkeit, eine beliebige Funktion anzumerken, die der Signatur entspricht, es handelt sich um Aliasing.</span><span class="sxs-lookup"><span data-stu-id="51e22-346">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="51e22-347">Typabkürzungen wie folgt mit ist sehr nützlich und kompaktere Code ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="51e22-347">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="51e22-348">Vermeiden Sie die Verwendung von Typabkürzungen zur Darstellung Ihrer Domänenstatus</span><span class="sxs-lookup"><span data-stu-id="51e22-348">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="51e22-349">Obwohl Typabkürzungen praktisch für die Vergabe eines Namens für die Funktionssignaturen sind, können sie verwirrend sein, wenn abkürzen von anderen Typen von.</span><span class="sxs-lookup"><span data-stu-id="51e22-349">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="51e22-350">Betrachten Sie diese Abkürzung aus:</span><span class="sxs-lookup"><span data-stu-id="51e22-350">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="51e22-351">Dies kann auf verschiedene Weise verwirrend sein:</span><span class="sxs-lookup"><span data-stu-id="51e22-351">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="51e22-352">`BufferSize` ist nicht abstrakt. Es ist einfach einen anderen Namen für eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="51e22-352">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="51e22-353">Wenn `BufferSize` verfügbar gemacht wird in eine öffentliche API es kann problemlos falsch interpretiert werden, um mehr als nur bedeuten, dass `int`.</span><span class="sxs-lookup"><span data-stu-id="51e22-353">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="51e22-354">Im Allgemeinen Domänentypen haben Sie mehrere Attribute werden und sind nicht primitive Typen wie `int`.</span><span class="sxs-lookup"><span data-stu-id="51e22-354">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="51e22-355">Diese Abkürzung verstößt gegen diese Annahme.</span><span class="sxs-lookup"><span data-stu-id="51e22-355">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="51e22-356">Die Groß-/Kleinschreibung von `BufferSize` ("PascalCase") gibt an, dass dieser Typ mehr Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="51e22-356">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="51e22-357">Dieser Alias bietet höhere Klarheit im Vergleich mit dem Ziel eines benannten Arguments an eine Funktion nicht.</span><span class="sxs-lookup"><span data-stu-id="51e22-357">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="51e22-358">Die Abkürzung wird nicht in die kompilierte IL manifest; Es ist nur eine ganze Zahl, und dieser Alias ist ein Konstrukt Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="51e22-358">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) =
        ...
```

<span data-ttu-id="51e22-359">Im Grunde ist der Dateneingabe mit Typabkürzungen sind **nicht** Abstraktionen über die Typen, die sie sind abkürzen von.</span><span class="sxs-lookup"><span data-stu-id="51e22-359">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="51e22-360">Im vorherigen Beispiel `BufferSize` lediglich ein `int` mit keine zusätzlichen Daten noch keine Vorteile aus dem Typsystem neben dem, was im Hintergrund `int` bereits hat.</span><span class="sxs-lookup"><span data-stu-id="51e22-360">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>
