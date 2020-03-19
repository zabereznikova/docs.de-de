---
title: Codekonventionen für F#
description: Lernen Sie allgemeine Richtlinien und Idiome beim Schreiben von F-Code.
ms.date: 01/15/2020
ms.openlocfilehash: 7266211e501bdb52564220781e2347d1aceaf296
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401148"
---
# <a name="f-coding-conventions"></a><span data-ttu-id="4971c-103">Codekonventionen für F#</span><span class="sxs-lookup"><span data-stu-id="4971c-103">F# coding conventions</span></span>

<span data-ttu-id="4971c-104">Die folgenden Konventionen basieren auf der Erfahrung in der Arbeit mit großen F-Codebases.</span><span class="sxs-lookup"><span data-stu-id="4971c-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="4971c-105">Die [fünf Prinzipien des guten F-Codes](index.md#five-principles-of-good-f-code) sind die Grundlage jeder Empfehlung.</span><span class="sxs-lookup"><span data-stu-id="4971c-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="4971c-106">Sie beziehen sich auf die Richtlinien für den Entwurf von [F-Komponenten](component-design-guidelines.md), sind jedoch für jeden F-Code anwendbar, nicht nur für Komponenten wie Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="4971c-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="4971c-107">Organisieren von Code</span><span class="sxs-lookup"><span data-stu-id="4971c-107">Organizing code</span></span>

<span data-ttu-id="4971c-108">Es gibt zwei primäre Möglichkeiten, Code zu organisieren: Module und Namespaces.</span><span class="sxs-lookup"><span data-stu-id="4971c-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="4971c-109">Diese sind ähnlich, weisen jedoch die folgenden Unterschiede auf:</span><span class="sxs-lookup"><span data-stu-id="4971c-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="4971c-110">Namespaces werden als .NET-Namespaces kompiliert.</span><span class="sxs-lookup"><span data-stu-id="4971c-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="4971c-111">Module werden als statische Klassen kompiliert.</span><span class="sxs-lookup"><span data-stu-id="4971c-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="4971c-112">Namespaces sind immer oberste Ebene.</span><span class="sxs-lookup"><span data-stu-id="4971c-112">Namespaces are always top level.</span></span> <span data-ttu-id="4971c-113">Module können auf der obersten Ebene sein und in anderen Modulen verschachtelt sein.</span><span class="sxs-lookup"><span data-stu-id="4971c-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="4971c-114">Namespaces können mehrere Dateien umfassen.</span><span class="sxs-lookup"><span data-stu-id="4971c-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="4971c-115">Module können dies nicht.</span><span class="sxs-lookup"><span data-stu-id="4971c-115">Modules cannot.</span></span>
* <span data-ttu-id="4971c-116">Module können mit `[<RequireQualifiedAccess>]` und `[<AutoOpen>]`dekoriert werden.</span><span class="sxs-lookup"><span data-stu-id="4971c-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="4971c-117">Die folgenden Richtlinien helfen Ihnen, diese zum Organisieren des Codes zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4971c-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="4971c-118">Bevorzugen Sie Namespaces auf der obersten Ebene</span><span class="sxs-lookup"><span data-stu-id="4971c-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="4971c-119">Für alle öffentlich-beschaffenen Codes sind Namespaces Modulen auf der obersten Ebene vorziehend.</span><span class="sxs-lookup"><span data-stu-id="4971c-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="4971c-120">Da sie als .NET-Namespaces kompiliert werden, sind sie ohne Probleme aus C-Code verbrauchsfähig.</span><span class="sxs-lookup"><span data-stu-id="4971c-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="4971c-121">Die Verwendung eines Moduls der obersten Ebene scheint möglicherweise nicht anders zu sein, wenn es nur `MyClass` von `MyCode` F-Dateien aufgerufen wird, aber für C-Verbraucher können Anrufer überrascht sein, wenn sie sich für das Modul qualifizieren müssen.</span><span class="sxs-lookup"><span data-stu-id="4971c-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="4971c-122">Sorgfältig anwenden`[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="4971c-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="4971c-123">Das `[<AutoOpen>]` Konstrukt kann den Umfang dessen verschmutzen, was Anrufern zur Verfügung steht, und die Antwort darauf, woher etwas kommt, ist "Magisch".</span><span class="sxs-lookup"><span data-stu-id="4971c-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="4971c-124">Das ist nicht gut.</span><span class="sxs-lookup"><span data-stu-id="4971c-124">This is not a good thing.</span></span> <span data-ttu-id="4971c-125">Eine Ausnahme von dieser Regel ist die F-Core-Bibliothek selbst (obwohl diese Tatsache auch etwas umstritten ist).</span><span class="sxs-lookup"><span data-stu-id="4971c-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="4971c-126">Es ist jedoch eine Bequemlichkeit, wenn Sie über Hilfsfunktionen für eine öffentliche API verfügen, die Sie getrennt von dieser öffentlichen API organisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4971c-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

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

<span data-ttu-id="4971c-127">Auf diese Weise können Sie Implementierungsdetails sauber von der öffentlichen API einer Funktion trennen, ohne einen Helfer bei jedem Aufruf vollständig qualifizieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="4971c-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="4971c-128">Darüber hinaus kann das Aussetzen von Erweiterungsmethoden und Ausdrucksgeneratoren auf Namespaceebene mit ordentlich ausgedrückt `[<AutoOpen>]`werden.</span><span class="sxs-lookup"><span data-stu-id="4971c-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="4971c-129">Verwenden `[<RequireQualifiedAccess>]` Sie immer dann, wenn Namen in Konflikt geraten könnten oder Sie das Gefühl haben, dass dies bei der Lesbarkeit hilft</span><span class="sxs-lookup"><span data-stu-id="4971c-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="4971c-130">Das `[<RequireQualifiedAccess>]` Hinzufügen des Attributs zu einem Modul weist darauf hin, dass das Modul möglicherweise nicht geöffnet wird und dass Verweise auf die Elemente des Moduls einen expliziten qualifizierten Zugriff erfordern.</span><span class="sxs-lookup"><span data-stu-id="4971c-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="4971c-131">Das `Microsoft.FSharp.Collections.List` Modul verfügt beispielsweise über dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="4971c-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="4971c-132">Dies ist nützlich, wenn Funktionen und Werte im Modul Namen haben, die wahrscheinlich mit Namen in anderen Modulen in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="4971c-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="4971c-133">Der Erfordernis eines qualifizierten Zugriffs kann die langfristige Wartbarkeit und Evolvierbarkeit einer Bibliothek erheblich erhöhen.</span><span class="sxs-lookup"><span data-stu-id="4971c-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="4971c-134">Sortieren `open` von Anweisungen topologisch</span><span class="sxs-lookup"><span data-stu-id="4971c-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="4971c-135">In f- ist die Reihenfolge der `open` Erklärungen wichtig, auch mit Erklärungen.</span><span class="sxs-lookup"><span data-stu-id="4971c-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="4971c-136">Dies ist anders als bei `using` `using static` C, wo die Wirkung dieser Anweisungen in einer Datei unabhängig ist und unabhängig ist.</span><span class="sxs-lookup"><span data-stu-id="4971c-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="4971c-137">Elemente, die in einen Bereich geöffnet werden, können andere bereits vorhandene Elemente in F-Bereich überschatten.</span><span class="sxs-lookup"><span data-stu-id="4971c-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="4971c-138">Dies bedeutet, `open` dass das Neuanordnen von Anweisungen die Bedeutung von Code ändern könnte.</span><span class="sxs-lookup"><span data-stu-id="4971c-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="4971c-139">Daher wird keine beliebige Sortierung aller `open` Anweisungen (z. B. alphanumerisch) empfohlen, damit Sie nicht ein anderes Verhalten generieren, das Sie möglicherweise erwarten.</span><span class="sxs-lookup"><span data-stu-id="4971c-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="4971c-140">Stattdessen empfehlen wir, dass Sie sie [topologisch](https://en.wikipedia.org/wiki/Topological_sorting)sortieren; Das heißt, `open` ordnen Sie Ihre Anweisungen in der Reihenfolge an, in der _Ebenen_ Ihres Systems definiert sind.</span><span class="sxs-lookup"><span data-stu-id="4971c-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="4971c-141">Die alphanumerische Sortierung innerhalb verschiedener topologischer Schichten kann ebenfalls in Betracht gezogen werden.</span><span class="sxs-lookup"><span data-stu-id="4971c-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="4971c-142">Hier ist z. B. die topologische Sortierung für die öffentliche API-Datei des F-Compilerdiensts:</span><span class="sxs-lookup"><span data-stu-id="4971c-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

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

<span data-ttu-id="4971c-143">Beachten Sie, dass ein Zeilenumbruch topologische Layer trennt, wobei jede Ebene anschließend alphanumerisch sortiert wird.</span><span class="sxs-lookup"><span data-stu-id="4971c-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="4971c-144">Dadurch wird Code sauber organisiert, ohne versehentlich Werte zu beschatten.</span><span class="sxs-lookup"><span data-stu-id="4971c-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="4971c-145">Verwenden von Klassen zum Enthalten von Werten mit Nebenwirkungen</span><span class="sxs-lookup"><span data-stu-id="4971c-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="4971c-146">Es gibt viele Male, in denen das Initialisieren eines Werts Nebenwirkungen haben kann, z. B. das Instanziieren eines Kontexts in einer Datenbank oder einer anderen Remoteressource.</span><span class="sxs-lookup"><span data-stu-id="4971c-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="4971c-147">Es ist verlockend, solche Dinge in einem Modul zu initialisieren und in nachfolgenden Funktionen zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="4971c-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

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

<span data-ttu-id="4971c-148">Dies ist oft eine schlechte Idee aus einigen Gründen:</span><span class="sxs-lookup"><span data-stu-id="4971c-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="4971c-149">Zuerst wird die Anwendungskonfiguration in `dep1` die `dep2`Codebasis mit und übertragen.</span><span class="sxs-lookup"><span data-stu-id="4971c-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="4971c-150">Dies ist in größeren Codebasen nur schwer zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="4971c-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="4971c-151">Zweitens sollten statisch initialisierte Daten keine Werte enthalten, die nicht threadsicher sind, wenn die Komponente selbst mehrere Threads verwendet.</span><span class="sxs-lookup"><span data-stu-id="4971c-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="4971c-152">Dies wird `dep3`eindeutig durch verletzt.</span><span class="sxs-lookup"><span data-stu-id="4971c-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="4971c-153">Schließlich wird die Modulinitialisierung in einen statischen Konstruktor für die gesamte Kompilierungseinheit kompiliert.</span><span class="sxs-lookup"><span data-stu-id="4971c-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="4971c-154">Wenn in diesem Modul ein Fehler bei der let-bound-Wertinitialisierung auftritt, manifestiert er sich als ein, `TypeInitializationException` der dann für die gesamte Lebensdauer der Anwendung zwischengespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="4971c-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="4971c-155">Dies kann schwierig zu diagnostizieren sein.</span><span class="sxs-lookup"><span data-stu-id="4971c-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="4971c-156">Es gibt in der Regel eine innere Ausnahme, über die Sie versuchen können, zu denken, aber wenn es nicht gibt, dann gibt es keine Aussage darüber, was die Ursache ist.</span><span class="sxs-lookup"><span data-stu-id="4971c-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="4971c-157">Verwenden Sie stattdessen einfach eine einfache Klasse, um Abhängigkeiten zu halten:</span><span class="sxs-lookup"><span data-stu-id="4971c-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="4971c-158">Dies ermöglicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4971c-158">This enables the following:</span></span>

1. <span data-ttu-id="4971c-159">Durch Pushen eines abhängigen Status außerhalb der API selbst.</span><span class="sxs-lookup"><span data-stu-id="4971c-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="4971c-160">Die Konfiguration kann nun außerhalb der API erfolgen.</span><span class="sxs-lookup"><span data-stu-id="4971c-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="4971c-161">Fehler bei der Initialisierung für abhängige `TypeInitializationException`Werte werden sich wahrscheinlich nicht als manifestieren.</span><span class="sxs-lookup"><span data-stu-id="4971c-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="4971c-162">Die API ist jetzt einfacher zu testen.</span><span class="sxs-lookup"><span data-stu-id="4971c-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="4971c-163">Fehlerverwaltung</span><span class="sxs-lookup"><span data-stu-id="4971c-163">Error management</span></span>

<span data-ttu-id="4971c-164">Fehlermanagement in großen Systemen ist ein komplexes und nuanciertes Unterfangen, und es gibt keine silbernen Kugeln, um sicherzustellen, dass Ihre Systeme fehlertolerant sind und sich gut verhalten.</span><span class="sxs-lookup"><span data-stu-id="4971c-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="4971c-165">Die folgenden Richtlinien sollten Anleitungen für die Navigation in diesem schwierigen Bereich bieten.</span><span class="sxs-lookup"><span data-stu-id="4971c-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="4971c-166">Stellen Sie Fehlerfälle und ungültigen Status in Typen dar, die Ihrer Domäne innewohnen</span><span class="sxs-lookup"><span data-stu-id="4971c-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="4971c-167">Mit Diskriminierten Unions können Sie mit ["Diskriminierte Unions"](../language-reference/discriminated-unions.md)einen fehlerhaften Programmstatus in Ihrem Typsystem darstellen.</span><span class="sxs-lookup"><span data-stu-id="4971c-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="4971c-168">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4971c-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="4971c-169">In diesem Fall gibt es drei bekannte Möglichkeiten, wie das Abheben von Geld von einem Bankkonto fehlschlagen kann.</span><span class="sxs-lookup"><span data-stu-id="4971c-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="4971c-170">Jeder Fehlerfall wird im Typ dargestellt und kann somit im gesamten Programm sicher behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="4971c-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="4971c-171">Wenn Sie im Allgemeinen die verschiedenen Möglichkeiten modellieren können, wie etwas in Ihrer Domäne **fehlschlagen** kann, wird Fehlerbehandlungscode nicht mehr als etwas behandelt, mit dem Sie sich zusätzlich zum regulären Programmfluss befassen müssen.</span><span class="sxs-lookup"><span data-stu-id="4971c-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="4971c-172">Es ist einfach ein Teil des normalen Programmflusses und nicht als **außergewöhnlich**betrachtet.</span><span class="sxs-lookup"><span data-stu-id="4971c-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="4971c-173">Dies hat zwei Hauptvorteile:</span><span class="sxs-lookup"><span data-stu-id="4971c-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="4971c-174">Es ist einfacher zu verwalten, wenn sich Ihre Domäne im Laufe der Zeit ändert.</span><span class="sxs-lookup"><span data-stu-id="4971c-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="4971c-175">Fehlerfälle sind einfacher zu einheitstest.</span><span class="sxs-lookup"><span data-stu-id="4971c-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="4971c-176">Ausnahmen verwenden, wenn Fehler nicht mit Typen dargestellt werden können</span><span class="sxs-lookup"><span data-stu-id="4971c-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="4971c-177">Nicht alle Fehler können in einer Problemdomäne dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4971c-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="4971c-178">Diese Art von Fehlern sind *außergewöhnlich,* daher die Fähigkeit, Ausnahmen in F zu erhöhen und zu fangen.</span><span class="sxs-lookup"><span data-stu-id="4971c-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="4971c-179">Zunächst wird empfohlen, die Richtlinien für den [Ausnahmeentwurf](../../standard/design-guidelines/exceptions.md)zu lesen.</span><span class="sxs-lookup"><span data-stu-id="4971c-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="4971c-180">Diese gelten auch für die F-Datei.</span><span class="sxs-lookup"><span data-stu-id="4971c-180">These are also applicable to F#.</span></span>

<span data-ttu-id="4971c-181">Die wichtigsten Konstrukte, die für das Auslösen von Ausnahmen in F-Code verfügbar sind, sollten in der folgenden Reihenfolge der Präferenz betrachtet werden:</span><span class="sxs-lookup"><span data-stu-id="4971c-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="4971c-182">Funktion</span><span class="sxs-lookup"><span data-stu-id="4971c-182">Function</span></span> | <span data-ttu-id="4971c-183">Syntax</span><span class="sxs-lookup"><span data-stu-id="4971c-183">Syntax</span></span> | <span data-ttu-id="4971c-184">Zweck</span><span class="sxs-lookup"><span data-stu-id="4971c-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="4971c-185">Löst `System.ArgumentNullException` a mit dem angegebenen Argumentnamen aus.</span><span class="sxs-lookup"><span data-stu-id="4971c-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="4971c-186">Löst `System.ArgumentException` eine mit einem angegebenen Argumentnamen und einer angegebenen Nachricht aus.</span><span class="sxs-lookup"><span data-stu-id="4971c-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="4971c-187">Löst `System.InvalidOperationException` eine mit der angegebenen Nachricht aus.</span><span class="sxs-lookup"><span data-stu-id="4971c-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="4971c-188">Allzweckmechanismus zum Auslösen von Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="4971c-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="4971c-189">Löst `System.Exception` eine mit der angegebenen Nachricht aus.</span><span class="sxs-lookup"><span data-stu-id="4971c-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="4971c-190">Löst `System.Exception` eine mit einer Nachricht aus, die durch die Formatzeichenfolge und ihre Eingaben bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="4971c-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="4971c-191">Verwenden `nullArg` `invalidArg` Sie `invalidOp` , und `ArgumentNullException`als `ArgumentException` `InvalidOperationException` Mechanismus zum Auslösen von , und ggf..</span><span class="sxs-lookup"><span data-stu-id="4971c-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="4971c-192">Die `failwith` `failwithf` und Funktionen sollten im Allgemeinen vermieden `Exception` werden, da sie den Basistyp und keine bestimmte Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="4971c-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="4971c-193">Gemäß den Richtlinien für den [Ausnahmeentwurf](../../standard/design-guidelines/exceptions.md)möchten Sie, wenn möglich, spezifischere Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="4971c-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="4971c-194">Verwenden der Syntax für die Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="4971c-194">Using exception-handling syntax</span></span>

<span data-ttu-id="4971c-195">Über die `try...with` Syntax unterstützt F- Ausnahmemuster:</span><span class="sxs-lookup"><span data-stu-id="4971c-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="4971c-196">Das Abgleichen der Funktionalität, die angesichts einer Ausnahme mit dem Musterabgleich durchgeführt werden soll, kann etwas schwierig sein, wenn Sie den Code sauber halten möchten.</span><span class="sxs-lookup"><span data-stu-id="4971c-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="4971c-197">Eine möglichkeit, dies zu behandeln, besteht darin, [aktive Muster](../language-reference/active-patterns.md) als Mittel zu verwenden, um Funktionen zu gruppieren, die einen Fehlerfall mit einer Ausnahme selbst umgeben.</span><span class="sxs-lookup"><span data-stu-id="4971c-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="4971c-198">Sie können z. B. eine API verwenden, die beim Auslösen einer Ausnahme wertvolle Informationen in die Ausnahmemetadaten einschließt.</span><span class="sxs-lookup"><span data-stu-id="4971c-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="4971c-199">Das Entpacken eines nützlichen Werts im Körper der erfassten Ausnahme innerhalb des aktiven Musters und das Zurückgeben dieses Werts kann in einigen Situationen hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="4971c-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="4971c-200">Verwenden Sie keine monadische Fehlerbehandlung, um Ausnahmen zu ersetzen</span><span class="sxs-lookup"><span data-stu-id="4971c-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="4971c-201">Ausnahmen werden in der funktionalen Programmierung als etwas tabu angesehen.</span><span class="sxs-lookup"><span data-stu-id="4971c-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="4971c-202">In der Tat, Ausnahmen verletzen Reinheit, so ist es sicher, sie nicht ganz funktionsfähig zu betrachten.</span><span class="sxs-lookup"><span data-stu-id="4971c-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="4971c-203">Dadurch wird jedoch die Realität ignoriert, wo Code ausgeführt werden muss, und dass Laufzeitfehler auftreten können.</span><span class="sxs-lookup"><span data-stu-id="4971c-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="4971c-204">Im Allgemeinen schreiben Sie Code unter der Annahme, dass die meisten Dinge weder rein noch vollständig sind, um unangenehme Überraschungen zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="4971c-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="4971c-205">Es ist wichtig, die folgenden Kernstärken/Aspekte von Ausnahmen in Bezug auf ihre Relevanz und Angemessenheit im .NET-Laufzeit- und sprachübergreifenden Ökosystem als Ganzes zu berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="4971c-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="4971c-206">Sie enthalten detaillierte Diagnoseinformationen, was beim Debuggen eines Problems sehr hilfreich ist.</span><span class="sxs-lookup"><span data-stu-id="4971c-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="4971c-207">Sie werden von der Laufzeit und anderen .NET-Sprachen gut verstanden.</span><span class="sxs-lookup"><span data-stu-id="4971c-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="4971c-208">Sie können im Vergleich zu Code, der aus dem Weg geht, um Ausnahmen zu *vermeiden,* signifikante Bausteine reduzieren, indem sie eine Teilmenge ihrer Semantik ad hoc implementieren.</span><span class="sxs-lookup"><span data-stu-id="4971c-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="4971c-209">Dieser dritte Punkt ist von entscheidender Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="4971c-209">This third point is critical.</span></span> <span data-ttu-id="4971c-210">Bei nicht trivialen komplexen Vorgängen kann die Nichtverwendung von Ausnahmen zu Strukturen wie diesen führen:</span><span class="sxs-lookup"><span data-stu-id="4971c-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="4971c-211">Was leicht zu fragilem Code wie Musterabgleich bei "stringly-typed"-Fehlern führen kann:</span><span class="sxs-lookup"><span data-stu-id="4971c-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="4971c-212">Darüber hinaus kann es verlockend sein, jede Ausnahme in dem Wunsch nach einer "einfachen" Funktion zu schlucken, die einen "niceren" Typ zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="4971c-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="4971c-213">Leider `tryReadAllText` können zahlreiche Ausnahmen auf der Grundlage der unzähligen Dinge, die auf einem Dateisystem passieren können, auslösen, und dieser Code verwirft alle Informationen darüber, was in Ihrer Umgebung tatsächlich schief gehen könnte.</span><span class="sxs-lookup"><span data-stu-id="4971c-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="4971c-214">Wenn Sie diesen Code durch einen Ergebnistyp ersetzen, kehren Sie zur Analyse der Fehlermeldung "stringly-typed" zurück:</span><span class="sxs-lookup"><span data-stu-id="4971c-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

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

<span data-ttu-id="4971c-215">Und das Platzieren des `Error` Ausnahmeobjekts selbst im Konstruktor zwingt Sie nur, den Ausnahmetyp an der Aufrufsite und nicht in der Funktion ordnungsgemäß zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="4971c-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="4971c-216">Dadurch werden effektiv geprüfte Ausnahmen erstellt, die als Aufrufer einer API notorisch unlustig sind.</span><span class="sxs-lookup"><span data-stu-id="4971c-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="4971c-217">Eine gute Alternative zu den obigen Beispielen besteht darin, *bestimmte* Ausnahmen abzufangen und im Kontext dieser Ausnahme einen aussagekräftigen Wert zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="4971c-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="4971c-218">Wenn Sie `tryReadAllText` die Funktion `None` wie folgt ändern, hat mehr Bedeutung:</span><span class="sxs-lookup"><span data-stu-id="4971c-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="4971c-219">Anstatt als Catch-All zu fungieren, wird diese Funktion nun den Fall richtig behandeln, wenn eine Datei nicht gefunden wurde, und diese Bedeutung einer Rückgabe zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4971c-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="4971c-220">Dieser Rückgabewert kann diesem Fehlerfall zugeordnet werden, ohne Kontextinformationen zu verwerfen oder Aufrufer zu zwingen, sich mit einem Fall zu befassen, der an diesem Punkt des Codes möglicherweise nicht relevant ist.</span><span class="sxs-lookup"><span data-stu-id="4971c-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="4971c-221">Typen, `Result<'Success, 'Error>` z. B. eignen sich für grundlegende Vorgänge, bei denen sie nicht geschachtelt sind, und optionale Typen von F- sind perfekt zum Darstellen, wenn etwas *etwas* oder *nichts*zurückgeben könnte.</span><span class="sxs-lookup"><span data-stu-id="4971c-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="4971c-222">Sie ersetzen jedoch keine Ausnahmen und sollten nicht verwendet werden, um Ausnahmen zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="4971c-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="4971c-223">Vielmehr sollten sie mit Bedacht angewendet werden, um bestimmte Aspekte der Ausnahme- und Fehlerverwaltungspolitik gezielt anzugehen.</span><span class="sxs-lookup"><span data-stu-id="4971c-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="4971c-224">Teilanwendung und punktfreie Programmierung</span><span class="sxs-lookup"><span data-stu-id="4971c-224">Partial application and point-free programming</span></span>

<span data-ttu-id="4971c-225">Die Datei unterstützt die partielle Anwendung und damit verschiedene Möglichkeiten, punktfrei zu programmieren.</span><span class="sxs-lookup"><span data-stu-id="4971c-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="4971c-226">Dies kann für die Wiederverwendung von Code innerhalb eines Moduls oder die Implementierung von etwas von Vorteil sein, aber es ist nicht etwas, das öffentlich verfügbar gemacht werden kann.</span><span class="sxs-lookup"><span data-stu-id="4971c-226">This can be beneficial for code reuse within a module or the implementation of something, but it is not something to expose publicly.</span></span> <span data-ttu-id="4971c-227">Im Allgemeinen ist punktfreie Programmierung keine Tugend an sich und kann eine signifikante kognitive Barriere für Menschen hinzufügen, die nicht in den Stil eingetaucht sind.</span><span class="sxs-lookup"><span data-stu-id="4971c-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="4971c-228">Verwenden Sie keine partielle Anwendung und Currying in öffentlichen APIs</span><span class="sxs-lookup"><span data-stu-id="4971c-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="4971c-229">Mit wenig Ausnahme kann die Verwendung von Partizipasten in öffentlichen APIs für Verbraucher verwirrend sein.</span><span class="sxs-lookup"><span data-stu-id="4971c-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="4971c-230">In `let`der Regel sind -gebundene Werte im F-Code **Werte,** keine **Funktionswerte**.</span><span class="sxs-lookup"><span data-stu-id="4971c-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="4971c-231">Das Zusammenführen von Werten und Funktionswerten kann dazu führen, dass eine kleine Anzahl von Codezeilen `>>` im Austausch für einen ziemlich enerbierten kognitiven Overhead gespeichert wird, insbesondere wenn sie mit Operatoren kombiniert werden, die z. B. Funktionen erstellen.</span><span class="sxs-lookup"><span data-stu-id="4971c-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="4971c-232">Berücksichtigen Sie die Auswirkungen auf die Werkzeugerstellung für die punktfreie Programmierung</span><span class="sxs-lookup"><span data-stu-id="4971c-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="4971c-233">Curried-Funktionen kennzeichnen ihre Argumente nicht.</span><span class="sxs-lookup"><span data-stu-id="4971c-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="4971c-234">Dies hat Auswirkungen auf die Werkzeugisierung.</span><span class="sxs-lookup"><span data-stu-id="4971c-234">This has tooling implications.</span></span> <span data-ttu-id="4971c-235">Berücksichtigen Sie die folgenden beiden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="4971c-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="4971c-236">Beide sind gültige `funcWithApplication` Funktionen, sind jedoch eine Curry-Funktion.</span><span class="sxs-lookup"><span data-stu-id="4971c-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="4971c-237">Wenn Sie den Mauszeiger über ihre Typen in einem Editor bewegen, sehen Sie dies:</span><span class="sxs-lookup"><span data-stu-id="4971c-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="4971c-238">Auf der Aufrufsite geben Tooltips in Tools wie Visual Studio keine `string` aussagekräftigen Informationen darüber, was die Eingabetypen `int` tatsächlich darstellen.</span><span class="sxs-lookup"><span data-stu-id="4971c-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="4971c-239">Wenn Sie punktfreien Code `funcWithApplication` wie diesen öffentlich verbrauchsfähig begegnen, wird empfohlen, eine vollständige Erweiterung von ,,,"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""</span><span class="sxs-lookup"><span data-stu-id="4971c-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="4971c-240">Darüber hinaus kann das Debuggen von punktfreiem Code eine Herausforderung, wenn nicht gar unmöglich sein.</span><span class="sxs-lookup"><span data-stu-id="4971c-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="4971c-241">Debugtools basieren auf Werten, die an `let` Namen gebunden sind (z. B. Bindungen), sodass Sie Zwischenwerte während der Ausführung überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="4971c-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="4971c-242">Wenn der Code keine Werte zum Überprüfen hat, gibt es nichts zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="4971c-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="4971c-243">In Zukunft können sich Debugging-Tools weiterentwickeln, um diese Werte basierend auf zuvor ausgeführten Pfaden zu synthetisieren, aber es ist keine gute Idee, Ihre Wetten auf *potenzielle* Debugging-Funktionalität abzusichern.</span><span class="sxs-lookup"><span data-stu-id="4971c-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="4971c-244">Betrachten Sie die partielle Anwendung als eine Technik, um interne Boilerplate zu reduzieren</span><span class="sxs-lookup"><span data-stu-id="4971c-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="4971c-245">Im Gegensatz zum vorherigen Punkt ist die Partielle Anwendung ein wunderbares Werkzeug zur Reduzierung von Boilerplate innerhalb einer Anwendung oder der tieferen Innenräume einer API.</span><span class="sxs-lookup"><span data-stu-id="4971c-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="4971c-246">Es kann hilfreich sein, wenn Komponenten die Implementierung komplizierterer APIs testen, bei denen die Bausteine oft ein Schmerz sind.</span><span class="sxs-lookup"><span data-stu-id="4971c-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="4971c-247">Der folgende Code zeigt beispielsweise, wie Sie das erreichen können, was Ihnen die meisten Mocking-Frameworks bieten, ohne eine externe Abhängigkeit von einem solchen Framework zu übernehmen und eine zugehörige maßgeschneiderte API zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="4971c-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="4971c-248">Betrachten Sie beispielsweise die folgende Lösungstopographie:</span><span class="sxs-lookup"><span data-stu-id="4971c-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="4971c-249">`ImplementationLogic.fsproj`kann Code verfügbar machen, z. B.:</span><span class="sxs-lookup"><span data-stu-id="4971c-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="4971c-250">Komponententests `Transactions.doTransaction` `ImplementationLogic.Tests.fsproj` in sind einfach:</span><span class="sxs-lookup"><span data-stu-id="4971c-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fsproj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="4971c-251">Wenn `doTransaction` Sie teilweise mit einem Mocking-Kontextobjekt angewendet werden, können Sie die Funktion in allen Komponententests aufrufen, ohne jedes Mal einen simulierten Kontext erstellen zu müssen:</span><span class="sxs-lookup"><span data-stu-id="4971c-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member _.TheFirstMember() = ...
        member _.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

<span data-ttu-id="4971c-252">Diese Technik sollte nicht universell auf Ihre gesamte Codebasis angewendet werden, aber es ist eine gute Möglichkeit, Boilerplate für komplizierte Interna und Komponententests dieser Interna zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="4971c-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="4971c-253">Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="4971c-253">Access control</span></span>

<span data-ttu-id="4971c-254">Die Option ["F"](../language-reference/access-control.md)verfügt über mehrere Optionen für die Zugriffssteuerung , die von dem geerbt wurde, was in der .NET-Laufzeit verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="4971c-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="4971c-255">Diese sind nicht nur für Typen nutzbar - Sie können sie auch für Funktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4971c-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="4971c-256">Bevorzugen Sie`public` Nicht-Typen und Member, bis Sie sie öffentlich verbrauchsfähig sein müssen.</span><span class="sxs-lookup"><span data-stu-id="4971c-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="4971c-257">Dies minimiert auch, was Verbraucher paaren.</span><span class="sxs-lookup"><span data-stu-id="4971c-257">This also minimizes what consumers couple to.</span></span>
* <span data-ttu-id="4971c-258">Bemühen Sie sich, `private`alle Helfer-Funktionalität zu behalten .</span><span class="sxs-lookup"><span data-stu-id="4971c-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="4971c-259">Erwägen Sie `[<AutoOpen>]` die Verwendung auf einem privaten Modul von Hilfsfunktionen, wenn sie zahlreich werden.</span><span class="sxs-lookup"><span data-stu-id="4971c-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="4971c-260">Typrückschluss und Generika</span><span class="sxs-lookup"><span data-stu-id="4971c-260">Type inference and generics</span></span>

<span data-ttu-id="4971c-261">Typrückschluss kann Sie vor der Eingabe einer Menge Von Boilerplate sparen.</span><span class="sxs-lookup"><span data-stu-id="4971c-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="4971c-262">Und die automatische Verallgemeinerung im F-Compiler kann Ihnen helfen, mehr generischen Code zu schreiben, ohne dass Sie sich mehr Mühe geben.</span><span class="sxs-lookup"><span data-stu-id="4971c-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="4971c-263">Diese Eigenschaften sind jedoch nicht allgemein gut.</span><span class="sxs-lookup"><span data-stu-id="4971c-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="4971c-264">Erwägen Sie die Beschriftung von Argumentnamen mit expliziten Typen in öffentlichen APIs, und verlassen Sie sich hierzu nicht auf Typrückschluss.</span><span class="sxs-lookup"><span data-stu-id="4971c-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="4971c-265">Der Grund dafür ist, dass **Sie** die Kontrolle über die Form Ihrer API haben sollten, nicht über den Compiler.</span><span class="sxs-lookup"><span data-stu-id="4971c-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="4971c-266">Obwohl der Compiler beim Ableiten von Typen für Sie eine gute Arbeit leisten kann, ist es möglich, die Form der API zu ändern, wenn die internen Typen geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="4971c-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="4971c-267">Das mag Das sein, was Sie wollen, aber es wird mit ziemlicher Sicherheit zu einer bahnbrechenden API-Änderung führen, mit der sich nachgeschaltete Verbraucher dann auseinandersetzen müssen.</span><span class="sxs-lookup"><span data-stu-id="4971c-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="4971c-268">Wenn Sie stattdessen explizit die Form Ihrer öffentlichen API steuern, können Sie diese brechenden Änderungen steuern.</span><span class="sxs-lookup"><span data-stu-id="4971c-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="4971c-269">In DDD-Begriffen kann dies als Anti-Korruptions-Schicht betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="4971c-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="4971c-270">Erwägen Sie, Ihren allgemeinen Argumenten einen aussagekräftigen Namen zu geben.</span><span class="sxs-lookup"><span data-stu-id="4971c-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="4971c-271">Wenn Sie keinen wirklich generischen Code schreiben, der nicht spezifisch für eine bestimmte Domäne ist, kann ein aussagekräftiger Name anderen Programmierern helfen, die Domäne zu verstehen, in der sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="4971c-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="4971c-272">Ein Typparameter, der `'Document` im Kontext der Interaktion mit einer Dokumentdatenbank benannt ist, macht beispielsweise deutlicher, dass generische Dokumenttypen von der Funktion oder dem Member akzeptiert werden können, mit dem Bzw. der Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="4971c-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="4971c-273">Erwägen Sie, generische Typparameter mit PascalCase zu benennen.</span><span class="sxs-lookup"><span data-stu-id="4971c-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="4971c-274">Dies ist die allgemeine Vorgehensweise in .NET, daher wird empfohlen, PascalCase anstelle von snake_case oder camelCase zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4971c-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="4971c-275">Schließlich ist die automatische Verallgemeinerung nicht immer ein Segen für Personen, die neu in der F-Datei oder einer großen Codebasis sind.</span><span class="sxs-lookup"><span data-stu-id="4971c-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="4971c-276">Die Verwendung von generischen Komponenten ist ein kognitiver Overhead.</span><span class="sxs-lookup"><span data-stu-id="4971c-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="4971c-277">Wenn automatisch verallgemeinerte Funktionen nicht mit unterschiedlichen Eingabetypen verwendet werden (geschweige denn, wenn sie als solche verwendet werden sollen), dann besteht kein wirklicher Vorteil dafür, dass sie zu diesem Zeitpunkt generisch sind.</span><span class="sxs-lookup"><span data-stu-id="4971c-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="4971c-278">Berücksichtigen Sie immer, ob der Code, den Sie schreiben, tatsächlich davon profitiert, generisch zu sein.</span><span class="sxs-lookup"><span data-stu-id="4971c-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="4971c-279">Leistung</span><span class="sxs-lookup"><span data-stu-id="4971c-279">Performance</span></span>

### <a name="prefer-structs-for-small-data-types"></a><span data-ttu-id="4971c-280">Bevorzugen von Strukturen für kleine Datentypen</span><span class="sxs-lookup"><span data-stu-id="4971c-280">Prefer structs for small data types</span></span>

<span data-ttu-id="4971c-281">Die Verwendung von Strukturen (auch Als Werttypen bezeichnet) kann häufig zu einer höheren Leistung für einige Codes führen, da die Zuweisung von Objekten in der Regel vermieden wird.</span><span class="sxs-lookup"><span data-stu-id="4971c-281">Using structs (also called Value Types) can often result in higher performance for some code because it typically avoids allocating objects.</span></span> <span data-ttu-id="4971c-282">Strukturen sind jedoch nicht immer eine "Go faster"-Schaltfläche: Wenn die Größe der Daten in einer Struktur 16 Byte überschreitet, kann das Kopieren der Daten oft zu mehr CPU-Zeit führen als mit einem Referenztyp.</span><span class="sxs-lookup"><span data-stu-id="4971c-282">However, structs are not always a "go faster" button: if the size of the data in a struct exceeds 16 bytes, copying the data can often result in more CPU time spend than using a reference type.</span></span>

<span data-ttu-id="4971c-283">Um zu bestimmen, ob Sie eine Struktur verwenden sollten, beachten Sie die folgenden Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="4971c-283">To determine if you should use a struct, consider the following conditions:</span></span>

- <span data-ttu-id="4971c-284">Wenn die Größe Ihrer Daten 16 Byte oder kleiner ist.</span><span class="sxs-lookup"><span data-stu-id="4971c-284">If the size of your data is 16 bytes or smaller.</span></span>
- <span data-ttu-id="4971c-285">Wenn sich wahrscheinlich viele dieser Datentypen in einem laufenden Programm im Arbeitsspeicher befinden.</span><span class="sxs-lookup"><span data-stu-id="4971c-285">If you're likely to have many of these data types resident in memory in a running program.</span></span>

<span data-ttu-id="4971c-286">Wenn die erste Bedingung zutrifft, sollten Sie in der Regel eine Struktur verwenden.</span><span class="sxs-lookup"><span data-stu-id="4971c-286">If the first condition applies, you should generally use a struct.</span></span> <span data-ttu-id="4971c-287">Wenn beides zutrifft, sollten Sie fast immer eine Struktur verwenden.</span><span class="sxs-lookup"><span data-stu-id="4971c-287">If both apply, you should almost always use a struct.</span></span> <span data-ttu-id="4971c-288">Es kann einige Fälle geben, in denen die vorherigen Bedingungen gelten, aber die Verwendung einer Struktur ist nicht besser oder schlechter als die Verwendung eines Referenztyps, aber sie sind wahrscheinlich selten.</span><span class="sxs-lookup"><span data-stu-id="4971c-288">There may be some cases where the previous conditions apply, but using a struct is no better or worse than using a reference type, but they are likely to be rare.</span></span> <span data-ttu-id="4971c-289">Es ist wichtig, immer zu messen, wenn Sie Änderungen wie diese vornehmen, aber nicht auf Annahme oder Intuition zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="4971c-289">It's important to always measure when making changes like this, though, and not operate on assumption or intuition.</span></span>

#### <a name="prefer-struct-tuples-when-grouping-small-value-types"></a><span data-ttu-id="4971c-290">Bevorzugen Sie Struktur-Tuples beim Gruppieren kleiner Werttypen</span><span class="sxs-lookup"><span data-stu-id="4971c-290">Prefer struct tuples when grouping small value types</span></span>

<span data-ttu-id="4971c-291">Berücksichtigen Sie die folgenden beiden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="4971c-291">Consider the following two functions:</span></span>

```fsharp
let rec runWithTuple t offset times =
    let offsetValues x y z offset =
        (x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let (x, y, z) = t
        let r = offsetValues x y z offset
        runWithTuple r offset (times - 1)

let rec runWithStructTuple t offset times =
    let offsetValues x y z offset =
        struct(x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let struct(x, y, z) = t
        let r = offsetValues x y z offset
        runWithStructTuple r offset (times - 1)
```

<span data-ttu-id="4971c-292">Wenn Sie diese Funktionen mit einem statistischen Benchmarking-Tool wie [BenchmarkDotNet](https://benchmarkdotnet.org/)vergleichen, werden Sie feststellen, dass die Funktion, die `runWithStructTuple` Struktur-Tuuples verwendet, 40% schneller läuft und keinen Speicher zuweist.</span><span class="sxs-lookup"><span data-stu-id="4971c-292">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that the `runWithStructTuple` function that uses struct tuples runs 40% faster and allocates no memory.</span></span>

<span data-ttu-id="4971c-293">Diese Ergebnisse sind jedoch nicht immer in Ihrem eigenen Code der Fall.</span><span class="sxs-lookup"><span data-stu-id="4971c-293">However, these results won't always be the case in your own code.</span></span> <span data-ttu-id="4971c-294">Wenn Sie eine `inline`Funktion als markieren, erhält Code, der Referenz-Tupeln verwendet, möglicherweise einige zusätzliche Optimierungen, oder Code, der zugewiesen würde, könnte einfach nicht mehr optimiert werden.</span><span class="sxs-lookup"><span data-stu-id="4971c-294">If you mark a function as `inline`, code that uses reference tuples may get some additional optimizations, or code that would allocate could simply be optimized away.</span></span> <span data-ttu-id="4971c-295">Sie sollten immer Ergebnisse messen, wenn es um Leistung geht, und niemals auf der Grundlage von Annahme oder Intuition arbeiten.</span><span class="sxs-lookup"><span data-stu-id="4971c-295">You should always measure results whenever performance is concerned, and never operate based on assumption or intuition.</span></span>

#### <a name="prefer-struct-records-when-the-data-type-is-small"></a><span data-ttu-id="4971c-296">Bevorzugen von Strukturdatensätzen, wenn der Datentyp klein ist</span><span class="sxs-lookup"><span data-stu-id="4971c-296">Prefer struct records when the data type is small</span></span>

<span data-ttu-id="4971c-297">Die oben beschriebene Faustregel gilt auch für [die Datensatztypen](../language-reference/records.md)von F.</span><span class="sxs-lookup"><span data-stu-id="4971c-297">The rule of thumb described earlier also holds for [F# record types](../language-reference/records.md).</span></span> <span data-ttu-id="4971c-298">Berücksichtigen Sie die folgenden Datentypen und Funktionen, die sie verarbeiten:</span><span class="sxs-lookup"><span data-stu-id="4971c-298">Consider the following data types and functions that process them:</span></span>

```fsharp
type Point = { X: float; Y: float; Z: float }

[<Struct>]
type SPoint = { X: float; Y: float; Z: float }

let rec processPoint (p: Point) offset times =
    let inline offsetValues (p: Point) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processPoint r offset (times - 1)

let rec processStructPoint (p: SPoint) offset times =
    let inline offsetValues (p: SPoint) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processStructPoint r offset (times - 1)
```

<span data-ttu-id="4971c-299">Dies ähnelt dem vorherigen Tupelcode, aber dieses Mal verwendet das Beispiel Datensätze und eine inline innere Funktion.</span><span class="sxs-lookup"><span data-stu-id="4971c-299">This is similar to the previous tuple code, but this time the example uses records and an inlined inner function.</span></span>

<span data-ttu-id="4971c-300">Wenn Sie diese Funktionen mit einem statistischen Benchmarking-Tool wie `processStructPoint` [BenchmarkDotNet](https://benchmarkdotnet.org/)vergleichen, werden Sie feststellen, dass fast 60% schneller läuft und nichts auf dem verwalteten Heap zuordnet.</span><span class="sxs-lookup"><span data-stu-id="4971c-300">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `processStructPoint` runs nearly 60% faster and allocates nothing on the managed heap.</span></span>

#### <a name="prefer-struct-discriminated-unions-when-the-data-type-is-small"></a><span data-ttu-id="4971c-301">Bevorzugen Sie strukturierte diskriminierte Gewerkschaften, wenn der Datentyp klein ist</span><span class="sxs-lookup"><span data-stu-id="4971c-301">Prefer struct discriminated unions when the data type is small</span></span>

<span data-ttu-id="4971c-302">Die bisherigen Beobachtungen zur Leistung mit Strukturtupeln und Aufzeichnungen gilt auch für [die F-Diskriminierten Unions](../language-reference/discriminated-unions.md).</span><span class="sxs-lookup"><span data-stu-id="4971c-302">The previous observations about performance with struct tuples and records also holds for [F# Discriminated Unions](../language-reference/discriminated-unions.md).</span></span> <span data-ttu-id="4971c-303">Betrachten Sie folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="4971c-303">Consider the following code:</span></span>

```fsharp
    type Name = Name of string

    [<Struct>]
    type SName = SName of string

    let reverseName (Name s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> Name

    let structReverseName (SName s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> SName
```

<span data-ttu-id="4971c-304">Es ist üblich, einzelne diskriminierte Unions wie diese für die Domänenmodellierung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="4971c-304">It's common to define single-case Discriminated Unions like this for domain modeling.</span></span> <span data-ttu-id="4971c-305">Wenn Sie diese Funktionen mit einem statistischen Benchmarking-Tool wie [BenchmarkDotNet](https://benchmarkdotnet.org/)vergleichen, werden Sie feststellen, dass das `structReverseName` etwa 25% schneller läuft als `reverseName` bei kleinen Strings.</span><span class="sxs-lookup"><span data-stu-id="4971c-305">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `structReverseName` runs about 25% faster than `reverseName` for small strings.</span></span> <span data-ttu-id="4971c-306">Bei großen Zeichenfolgen führen beide ungefähr gleich aus.</span><span class="sxs-lookup"><span data-stu-id="4971c-306">For large strings, both perform about the same.</span></span> <span data-ttu-id="4971c-307">In diesem Fall ist es also immer vorzuziehen, eine Struktur zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4971c-307">So, in this case, it's always preferable to use a struct.</span></span> <span data-ttu-id="4971c-308">Wie bereits erwähnt, messen und arbeiten sie nicht auf Annahmen oder Intuition.</span><span class="sxs-lookup"><span data-stu-id="4971c-308">As previously mentioned, always measure and do not operate on assumptions or intuition.</span></span>

<span data-ttu-id="4971c-309">Obwohl das vorangegangene Beispiel zeigte, dass eine strukturdiskriminierte Union eine bessere Leistung erbracht hat, ist es üblich, größere diskriminierte Unions zu haben, wenn sie eine Domäne modellieren.</span><span class="sxs-lookup"><span data-stu-id="4971c-309">Although the previous example showed that a struct Discriminated Union yielded better performance, it is common to have larger Discriminated Unions when modeling a domain.</span></span> <span data-ttu-id="4971c-310">Größere Datentypen wie dieser funktionieren möglicherweise nicht so gut, wenn es sich um Strukturen handelt, die von den Vorgängen abhängen, da mehr Kopieren beteiligt sein könnte.</span><span class="sxs-lookup"><span data-stu-id="4971c-310">Larger data types like that may not perform as well if they are structs depending on the operations on them, since more copying could be involved.</span></span>

### <a name="functional-programming-and-mutation"></a><span data-ttu-id="4971c-311">Funktionelle Programmierung und Mutation</span><span class="sxs-lookup"><span data-stu-id="4971c-311">Functional programming and mutation</span></span>

<span data-ttu-id="4971c-312">Die F-Werte sind standardmäßig unveränderlich, sodass Sie bestimmte Klassen von Fehlern vermeiden können (insbesondere solche, die Parallelität und Parallelität betreffen).</span><span class="sxs-lookup"><span data-stu-id="4971c-312">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="4971c-313">In bestimmten Fällen kann jedoch eine Arbeitsspanne am besten mithilfe einer ortsansässigen Mutation des Zustands implementiert werden, um eine optimale (oder sogar angemessene) Effizienz der Ausführungszeit oder speicherzuweisungen zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="4971c-313">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="4971c-314">Dies ist in einer Opt-in-Basis `mutable` mit dem Schlüsselwort F' möglich.</span><span class="sxs-lookup"><span data-stu-id="4971c-314">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="4971c-315">Die `mutable` Verwendung von in F' kann sich im Widerspruch zur funktionellen Reinheit anfühlen.</span><span class="sxs-lookup"><span data-stu-id="4971c-315">Use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="4971c-316">Das ist verständlich, aber funktionale Reinheit kann überall im Widerspruch zu Leistungszielen stehen.</span><span class="sxs-lookup"><span data-stu-id="4971c-316">This is understandable, but functional purity everywhere can be at odds with performance goals.</span></span> <span data-ttu-id="4971c-317">Ein Kompromiss besteht darin, Mutationen so zu kapseln, dass Anrufer sich nicht darum kümmern müssen, was passiert, wenn sie eine Funktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4971c-317">A compromise is to encapsulate mutation such that callers need not care about what happens when they call a function.</span></span> <span data-ttu-id="4971c-318">Auf diese Weise können Sie eine funktionale Schnittstelle über eine mutationsbasierte Implementierung für leistungskritischen Code schreiben.</span><span class="sxs-lookup"><span data-stu-id="4971c-318">This allows you to write a functional interface over a mutation-based implementation for performance-critical code.</span></span>

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="4971c-319">Wrap-veränderlichen Code in unveränderlichen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4971c-319">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="4971c-320">Unter dem Ziel der referenziellen Transparenz ist es wichtig, Code zu schreiben, der den veränderlichen Unterbauch leistungskritischer Funktionen nicht verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="4971c-320">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="4971c-321">Der folgende Code implementiert z. B. die `Array.contains` Funktion in der Kernbibliothek von F.:</span><span class="sxs-lookup"><span data-stu-id="4971c-321">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

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

<span data-ttu-id="4971c-322">Wenn Sie diese Funktion mehrmals aufrufen, wird das zugrunde liegende Array nicht geändert, und Es erfordert auch nicht, dass Sie einen veränderlichen Zustand beibehalten, um es zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4971c-322">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="4971c-323">Es ist referenziell transparent, obwohl fast jede Codezeile darin Mutation verwendet.</span><span class="sxs-lookup"><span data-stu-id="4971c-323">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

#### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="4971c-324">Erwägen Sie das Einkapseln veränderbarer Daten in Klassen</span><span class="sxs-lookup"><span data-stu-id="4971c-324">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="4971c-325">Im vorherigen Beispiel wurde eine einzelne Funktion verwendet, um Vorgänge mithilfe veränderbarer Daten zu kapseln.</span><span class="sxs-lookup"><span data-stu-id="4971c-325">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="4971c-326">Dies reicht nicht immer für komplexere Datensätze aus.</span><span class="sxs-lookup"><span data-stu-id="4971c-326">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="4971c-327">Berücksichtigen Sie die folgenden Funktionssätze:</span><span class="sxs-lookup"><span data-stu-id="4971c-327">Consider the following sets of functions:</span></span>

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

<span data-ttu-id="4971c-328">Dieser Code ist performant, macht jedoch die mutationsbasierte Datenstruktur verfügbar, für deren Wartung Aufrufer verantwortlich sind.</span><span class="sxs-lookup"><span data-stu-id="4971c-328">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="4971c-329">Dies kann innerhalb einer Klasse ohne zugrunde liegende Member eingeschlossen werden, die sich ändern können:</span><span class="sxs-lookup"><span data-stu-id="4971c-329">This can be wrapped inside of a class with no underlying members that can change:</span></span>

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member _.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member _.Count = t.Count

    member _.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

<span data-ttu-id="4971c-330">`Closure1Table`Kapselt die zugrunde liegende mutationsbasierte Datenstruktur, wodurch Aufrufer nicht gezwungen werden, die zugrunde liegende Datenstruktur beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="4971c-330">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="4971c-331">Klassen sind eine leistungsstarke Möglichkeit, Daten und Routinen zu kapseln, die mutationsbasiert sind, ohne die Details Aufrufern offenzulegen.</span><span class="sxs-lookup"><span data-stu-id="4971c-331">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

#### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="4971c-332">Bevorzugen `let mutable` Sie Referenzzellen</span><span class="sxs-lookup"><span data-stu-id="4971c-332">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="4971c-333">Referenzzellen sind eine Möglichkeit, den Verweis auf einen Wert und nicht den Wert selbst darzustellen.</span><span class="sxs-lookup"><span data-stu-id="4971c-333">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="4971c-334">Obwohl sie für leistungskritischen Code verwendet werden können, werden sie nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="4971c-334">Although they can be used for performance-critical code, they are not recommended.</span></span> <span data-ttu-id="4971c-335">Betrachten Sie das folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4971c-335">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="4971c-336">Die Verwendung einer Referenzzelle "verschmutzt" nun den gesamten nachfolgenden Code mit dem Dereferenzieren und erneuten Referenzieren der zugrunde liegenden Daten.</span><span class="sxs-lookup"><span data-stu-id="4971c-336">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="4971c-337">Betrachten Sie `let mutable`stattdessen:</span><span class="sxs-lookup"><span data-stu-id="4971c-337">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="4971c-338">Abgesehen vom einzelnen Mutationspunkt in der Mitte des Lambda-Ausdrucks kann jeder andere Code, der `acc` berührt, `let`dies auf eine Weise tun, die sich nicht von der Verwendung eines normalen unveränderlichen Wertes unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="4971c-338">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="4971c-339">Dies wird es einfacher, im Laufe der Zeit zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4971c-339">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="4971c-340">Objektprogrammierung</span><span class="sxs-lookup"><span data-stu-id="4971c-340">Object programming</span></span>

<span data-ttu-id="4971c-341">Die vollständige Unterstützung von Objekten und objektorientierten Konzepten (OO) ist von F- unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4971c-341">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="4971c-342">Obwohl viele OO-Konzepte leistungsstark und nützlich sind, sind nicht alle ideal zu bedienen.</span><span class="sxs-lookup"><span data-stu-id="4971c-342">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="4971c-343">Die folgenden Listen bieten Anleitungen zu Kategorien von OO-Funktionen auf hoher Ebene.</span><span class="sxs-lookup"><span data-stu-id="4971c-343">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="4971c-344">**Erwägen Sie die Verwendung dieser Funktionen in vielen Situationen:**</span><span class="sxs-lookup"><span data-stu-id="4971c-344">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="4971c-345">Punktnotation`x.Length`( )</span><span class="sxs-lookup"><span data-stu-id="4971c-345">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="4971c-346">Instanzmitglieder</span><span class="sxs-lookup"><span data-stu-id="4971c-346">Instance members</span></span>
* <span data-ttu-id="4971c-347">Implizite Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="4971c-347">Implicit constructors</span></span>
* <span data-ttu-id="4971c-348">Statische Member</span><span class="sxs-lookup"><span data-stu-id="4971c-348">Static members</span></span>
* <span data-ttu-id="4971c-349">Indexernotation`arr.[x]`( )</span><span class="sxs-lookup"><span data-stu-id="4971c-349">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="4971c-350">Benannte und optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="4971c-350">Named and Optional arguments</span></span>
* <span data-ttu-id="4971c-351">Schnittstellen und Schnittstellenimplementierungen</span><span class="sxs-lookup"><span data-stu-id="4971c-351">Interfaces and interface implementations</span></span>

<span data-ttu-id="4971c-352">**Greifen Sie nicht zuerst nach diesen Funktionen, sondern wenden Sie sie mit Bedacht an, wenn sie bequem sind, um ein Problem zu lösen:**</span><span class="sxs-lookup"><span data-stu-id="4971c-352">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="4971c-353">Methodenüberladung</span><span class="sxs-lookup"><span data-stu-id="4971c-353">Method overloading</span></span>
* <span data-ttu-id="4971c-354">Gekapselte veränderbare Daten</span><span class="sxs-lookup"><span data-stu-id="4971c-354">Encapsulated mutable data</span></span>
* <span data-ttu-id="4971c-355">Operatoren für Typen</span><span class="sxs-lookup"><span data-stu-id="4971c-355">Operators on types</span></span>
* <span data-ttu-id="4971c-356">Autoeigenschaften</span><span class="sxs-lookup"><span data-stu-id="4971c-356">Auto properties</span></span>
* <span data-ttu-id="4971c-357">Umsetzung `IDisposable` und`IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="4971c-357">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="4971c-358">Typerweiterungen</span><span class="sxs-lookup"><span data-stu-id="4971c-358">Type extensions</span></span>
* <span data-ttu-id="4971c-359">Events</span><span class="sxs-lookup"><span data-stu-id="4971c-359">Events</span></span>
* <span data-ttu-id="4971c-360">Strukturen</span><span class="sxs-lookup"><span data-stu-id="4971c-360">Structs</span></span>
* <span data-ttu-id="4971c-361">Delegaten</span><span class="sxs-lookup"><span data-stu-id="4971c-361">Delegates</span></span>
* <span data-ttu-id="4971c-362">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="4971c-362">Enums</span></span>

<span data-ttu-id="4971c-363">**Vermeiden Sie diese Funktionen im Allgemeinen, es sei denn, Sie müssen sie verwenden:**</span><span class="sxs-lookup"><span data-stu-id="4971c-363">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="4971c-364">Vererbungsbasierte Typhierarchien und Implementierungsvererbung</span><span class="sxs-lookup"><span data-stu-id="4971c-364">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="4971c-365">Nullen und`Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="4971c-365">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="4971c-366">Komposition vor Vererbung bevorzugen</span><span class="sxs-lookup"><span data-stu-id="4971c-366">Prefer composition over inheritance</span></span>

<span data-ttu-id="4971c-367">[Die Komposition über die Vererbung](https://en.wikipedia.org/wiki/Composition_over_inheritance) ist ein langjähriges Idiom, an das sich guter F-Code halten kann.</span><span class="sxs-lookup"><span data-stu-id="4971c-367">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="4971c-368">Das Grundprinzip besteht darin, dass Sie keine Basisklasse verfügbar machen und Aufrufer zwingen sollten, von dieser Basisklasse zu erben, um Funktionalität zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4971c-368">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="4971c-369">Verwenden von Objektausdrücken zum Implementieren von Schnittstellen, wenn Sie keine Klasse benötigen</span><span class="sxs-lookup"><span data-stu-id="4971c-369">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="4971c-370">[Mit Objektausdrücken](../language-reference/object-expressions.md) können Sie Schnittstellen spontan implementieren und die implementierte Schnittstelle an einen Wert binden, ohne dass dies innerhalb einer Klasse erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="4971c-370">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="4971c-371">Dies ist praktisch, vor allem, wenn Sie _nur_ die Schnittstelle implementieren müssen und keine vollständige Klasse benötigen.</span><span class="sxs-lookup"><span data-stu-id="4971c-371">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="4971c-372">Hier ist z. B. der Code, der in [Ionide](http://ionide.io/) ausgeführt wird, um eine Codefixaktion bereitzustellen, wenn Sie ein Symbol hinzugefügt haben, für das Sie keine `open` Anweisung haben:</span><span class="sxs-lookup"><span data-stu-id="4971c-372">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

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

<span data-ttu-id="4971c-373">Da bei der Interaktion mit der Visual Studio-Code-API keine Klasse erforderlich ist, sind Objektausdrücke ein ideales Tool dafür.</span><span class="sxs-lookup"><span data-stu-id="4971c-373">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="4971c-374">Sie sind auch für Komponententests nützlich, wenn Sie eine Schnittstelle mit Testroutinen ad hoc ausblenden möchten.</span><span class="sxs-lookup"><span data-stu-id="4971c-374">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="consider-type-abbreviations-to-shorten-signatures"></a><span data-ttu-id="4971c-375">Typabkürzungen in Betracht ziehen, um Signaturen zu kürzen</span><span class="sxs-lookup"><span data-stu-id="4971c-375">Consider Type Abbreviations to shorten signatures</span></span>

<span data-ttu-id="4971c-376">[Typabkürzungen](../language-reference/type-abbreviations.md) sind eine bequeme Möglichkeit, eine Bezeichnung einem anderen Typ zuzuweisen, z. B. einer Funktionssignatur oder einem komplexeren Typ.</span><span class="sxs-lookup"><span data-stu-id="4971c-376">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="4971c-377">Der folgende Alias weist z. B. eine Bezeichnung dem zu, was zum Definieren einer Berechnung mit [CNTK](https://docs.microsoft.com/cognitive-toolkit/), einer Deep Learning-Bibliothek, erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="4971c-377">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://docs.microsoft.com/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="4971c-378">Der `Computation` Name ist eine bequeme Möglichkeit, jede Funktion zu bezeichnen, die mit der Signatur übereinstimmt, die mit dem Aliasnamen übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="4971c-378">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="4971c-379">Die Verwendung von Typabkürzungen wie dieser ist praktisch und ermöglicht prägnanteren Code.</span><span class="sxs-lookup"><span data-stu-id="4971c-379">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="4971c-380">Vermeiden Sie die Verwendung von Typabkürzungen zur Darstellung Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="4971c-380">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="4971c-381">Obwohl Typabkürzungen für die Angabe eines Namens für Funktionssignaturen praktisch sind, können sie verwirrend sein, wenn andere Typen abgekürzt werden.</span><span class="sxs-lookup"><span data-stu-id="4971c-381">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="4971c-382">Betrachten Sie diese Abkürzung:</span><span class="sxs-lookup"><span data-stu-id="4971c-382">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="4971c-383">Dies kann auf verschiedene Arten verwirrend sein:</span><span class="sxs-lookup"><span data-stu-id="4971c-383">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="4971c-384">`BufferSize`ist keine Abstraktion; es ist nur ein anderer Name für eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="4971c-384">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="4971c-385">Wenn `BufferSize` sie in einer öffentlichen API verfügbar gemacht wird, `int`kann sie leicht falsch interpretiert werden, um mehr als nur zu bedeuten.</span><span class="sxs-lookup"><span data-stu-id="4971c-385">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="4971c-386">Im Allgemeinen weisen Domänentypen mehrere Attribute auf sich `int`ab und sind keine primitiven Typen wie .</span><span class="sxs-lookup"><span data-stu-id="4971c-386">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="4971c-387">Diese Abkürzung verstößt gegen diese Annahme.</span><span class="sxs-lookup"><span data-stu-id="4971c-387">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="4971c-388">Das Gehäuse `BufferSize` von (PascalCase) impliziert, dass dieser Typ mehr Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="4971c-388">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="4971c-389">Dieser Alias bietet keine größere Klarheit im Vergleich zur Bereitstellung eines benannten Arguments für eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="4971c-389">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="4971c-390">Die Abkürzung manifestiert sich nicht in kompilierter IL; Es ist nur eine ganze Zahl und dieser Alias ist ein Kompilierungszeitkonstrukt.</span><span class="sxs-lookup"><span data-stu-id="4971c-390">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

<span data-ttu-id="4971c-391">Zusammenfassend lässt sich sagen, dass die Falle bei Typabkürzungen darin besteht, dass sie **keine** Abstraktionen über die Typen sind, die sie abkürzen.</span><span class="sxs-lookup"><span data-stu-id="4971c-391">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="4971c-392">Im vorherigen Beispiel `BufferSize` ist `int` nur eine unter den Abdeckungen, ohne zusätzliche Daten, `int` noch irgendwelche Vorteile aus dem Typsystem abgesehen von dem, was bereits hat.</span><span class="sxs-lookup"><span data-stu-id="4971c-392">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>

<span data-ttu-id="4971c-393">Ein alternativer Ansatz zur Verwendung von Typabkürzungen zur Darstellung einer Domäne besteht darin, diskriminierte Unions in einzelfalldurchfällen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4971c-393">An alternative approach to using type abbreviations to represent a domain is to use single-case discriminated unions.</span></span> <span data-ttu-id="4971c-394">Das vorherige Beispiel kann wie folgt modelliert werden:</span><span class="sxs-lookup"><span data-stu-id="4971c-394">The previous sample can be modeled as follows:</span></span>

```fsharp
type BufferSize = BufferSize of int
```

<span data-ttu-id="4971c-395">Wenn Sie Code schreiben, `BufferSize` der in Bezug auf und den zugrunde liegenden Wert arbeitet, müssen Sie einen erstellen, anstatt eine beliebige ganze Zahl zu übergeben:</span><span class="sxs-lookup"><span data-stu-id="4971c-395">If you write code that operates in terms of `BufferSize` and its underlying value, you need to construct one rather than pass in any arbitrary integer:</span></span>

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

<span data-ttu-id="4971c-396">Dies verringert die Wahrscheinlichkeit, dass eine `send` beliebige ganze Zahl versehentlich an `BufferSize` die Funktion übergeben wird, da der Aufrufer einen Typ erstellen muss, um einen Wert umzuschließen, bevor er die Funktion aufruft.</span><span class="sxs-lookup"><span data-stu-id="4971c-396">This reduces the likelihood of mistakenly passing an arbitrary integer into the `send` function, because the caller must construct a `BufferSize` type to wrap a value before calling the function.</span></span>
