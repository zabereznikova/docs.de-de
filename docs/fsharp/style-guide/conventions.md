---
title: Codekonventionen für F#
description: Hier finden Sie allgemeine Richtlinien und Idiome beim Schreiben F# von Code.
ms.date: 10/22/2019
ms.openlocfilehash: 6700f64aa61308cbfc0b7a38724d69a281a088db
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799099"
---
# <a name="f-coding-conventions"></a><span data-ttu-id="359e2-103">Codekonventionen für F#</span><span class="sxs-lookup"><span data-stu-id="359e2-103">F# coding conventions</span></span>

<span data-ttu-id="359e2-104">Die folgenden Konventionen sind von der Erfahrung beim Arbeiten mit F# großen Codebasen formuliert.</span><span class="sxs-lookup"><span data-stu-id="359e2-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="359e2-105">Die [fünf Prinzipien von gutem F# Code](index.md#five-principles-of-good-f-code) sind die Grundlage für jede Empfehlung.</span><span class="sxs-lookup"><span data-stu-id="359e2-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="359e2-106">Sie sind mit den [ F# Richtlinien zum Entwerfen von Komponenten](component-design-guidelines.md)verknüpft, gelten jedoch F# für jeden beliebigen Code, nicht nur für Komponenten wie Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="359e2-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="359e2-107">Organisieren von Code</span><span class="sxs-lookup"><span data-stu-id="359e2-107">Organizing code</span></span>

<span data-ttu-id="359e2-108">F#bietet zwei Hauptmethoden zum Organisieren von Code: Module und Namespaces.</span><span class="sxs-lookup"><span data-stu-id="359e2-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="359e2-109">Diese sind ähnlich, haben jedoch die folgenden Unterschiede:</span><span class="sxs-lookup"><span data-stu-id="359e2-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="359e2-110">Namespaces werden als .NET-Namespaces kompiliert.</span><span class="sxs-lookup"><span data-stu-id="359e2-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="359e2-111">Module werden als statische Klassen kompiliert.</span><span class="sxs-lookup"><span data-stu-id="359e2-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="359e2-112">Namespaces sind immer die oberste Ebene.</span><span class="sxs-lookup"><span data-stu-id="359e2-112">Namespaces are always top level.</span></span> <span data-ttu-id="359e2-113">Module können auf oberster Ebene und in anderen Modulen geschachtelt sein.</span><span class="sxs-lookup"><span data-stu-id="359e2-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="359e2-114">Namespaces können mehrere Dateien umfassen.</span><span class="sxs-lookup"><span data-stu-id="359e2-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="359e2-115">Module können nicht.</span><span class="sxs-lookup"><span data-stu-id="359e2-115">Modules cannot.</span></span>
* <span data-ttu-id="359e2-116">Module können mit `[<RequireQualifiedAccess>]` und `[<AutoOpen>]`versehen werden.</span><span class="sxs-lookup"><span data-stu-id="359e2-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="359e2-117">Die folgenden Richtlinien helfen Ihnen, diese zum Organisieren Ihres Codes zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="359e2-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="359e2-118">Namespaces auf oberster Ebene bevorzugen</span><span class="sxs-lookup"><span data-stu-id="359e2-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="359e2-119">Für jeden öffentlich verwendbaren Code werden Namespaces für Module auf der obersten Ebene bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="359e2-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="359e2-120">Da Sie als .NET-Namespaces kompiliert werden, können Sie von C# ohne Probleme genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="359e2-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="359e2-121">Die Verwendung eines Moduls der obersten Ebene ist möglicherweise nicht anders, wenn F#Sie nur von C# aufgerufen wird, aber für Consumer werden Aufrufer möglicherweise überrascht, wenn Sie`MyClass`mit dem`MyCode`Modul qualifizieren müssen.</span><span class="sxs-lookup"><span data-stu-id="359e2-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="359e2-122">`[<AutoOpen>]` sorgfältig anwenden</span><span class="sxs-lookup"><span data-stu-id="359e2-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="359e2-123">Das `[<AutoOpen>]` Konstrukt kann den Umfang der für Aufrufer verfügbaren Elemente verschmutzen, und die Antwort auf den Ort, an dem sich etwas ergibt, ist "Magic".</span><span class="sxs-lookup"><span data-stu-id="359e2-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="359e2-124">Dies ist in der Regel kein gutes Problem.</span><span class="sxs-lookup"><span data-stu-id="359e2-124">This is generally not a good thing.</span></span> <span data-ttu-id="359e2-125">Eine Ausnahme von dieser Regel ist die F# Kernbibliothek selbst (obwohl diese Tatsache auch etwas strittig ist).</span><span class="sxs-lookup"><span data-stu-id="359e2-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="359e2-126">Es ist jedoch eine bequeme Methode, wenn Sie über Hilfsfunktionen für eine öffentliche API verfügen, die Sie separat von der öffentlichen API organisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="359e2-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

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

<span data-ttu-id="359e2-127">Auf diese Weise können Sie Implementierungsdetails von der öffentlichen API einer Funktion vollständig trennen, ohne dass Sie jedes Mal, wenn Sie Sie aufrufen, ein Hilfsobjekt vollständig qualifizieren müssen.</span><span class="sxs-lookup"><span data-stu-id="359e2-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="359e2-128">Außerdem kann das verfügbar machen von Erweiterungs Methoden und Ausdrucks-Generatoren auf Namespace Ebene mit `[<AutoOpen>]`sauber ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="359e2-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="359e2-129">Verwenden Sie `[<RequireQualifiedAccess>]`, wenn Namen Konflikte verursachen könnten, oder wenn Sie sich für die Lesbarkeit sorgen.</span><span class="sxs-lookup"><span data-stu-id="359e2-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="359e2-130">Das Hinzufügen des `[<RequireQualifiedAccess>]` Attributs zu einem Modul gibt an, dass das Modul möglicherweise nicht geöffnet wird und dass Verweise auf die Elemente des Moduls einen expliziten qualifizierten Zugriff erfordern.</span><span class="sxs-lookup"><span data-stu-id="359e2-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="359e2-131">Das `Microsoft.FSharp.Collections.List`-Modul verfügt beispielsweise über dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="359e2-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="359e2-132">Dies ist nützlich, wenn Funktionen und Werte im Modulnamen haben, die mit den Namen in anderen Modulen wahrscheinlich in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="359e2-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="359e2-133">Wenn qualifizierter Zugriff erforderlich ist, kann die langfristige Wartbarkeit und die Entwicklung einer Bibliothek erheblich gesteigert werden.</span><span class="sxs-lookup"><span data-stu-id="359e2-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="359e2-134">Sortieren von `open`-Anweisungen topologisch</span><span class="sxs-lookup"><span data-stu-id="359e2-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="359e2-135">In F#ist die Reihenfolge der Deklarationen, einschließlich der `open`-Anweisungen, wichtig.</span><span class="sxs-lookup"><span data-stu-id="359e2-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="359e2-136">Dies unterscheidet C#sich von, wenn die Auswirkung von`using`und`using static`unabhängig von der Reihenfolge dieser Anweisungen in einer Datei ist.</span><span class="sxs-lookup"><span data-stu-id="359e2-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="359e2-137">In F#können Elemente, die in einem Bereich geöffnet werden, andere als Schatten darstellen.</span><span class="sxs-lookup"><span data-stu-id="359e2-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="359e2-138">Dies bedeutet, dass das Neuordnen `open`-Anweisungen die Bedeutung von Code ändern könnte.</span><span class="sxs-lookup"><span data-stu-id="359e2-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="359e2-139">Folglich wird eine beliebige Sortierung aller `open` Anweisungen (z. b. alphanumerisch) in der Regel nicht empfohlen, sodass Sie kein anderes Verhalten generieren, das Sie möglicherweise erwarten.</span><span class="sxs-lookup"><span data-stu-id="359e2-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is generally not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="359e2-140">Stattdessen wird empfohlen, dass Sie Sie [topologisch](https://en.wikipedia.org/wiki/Topological_sorting)sortieren. Ordnen Sie also Ihre `open` Anweisungen in der Reihenfolge an, in der die _Ebenen_ Ihres Systems definiert sind.</span><span class="sxs-lookup"><span data-stu-id="359e2-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="359e2-141">Eine alphanumerische Sortierung innerhalb verschiedener topologischer Ebenen kann auch berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="359e2-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="359e2-142">Im folgenden finden Sie ein Beispiel für die topologische Sortierung der F# öffentlichen API-Datei des compilerdienstanbieter:</span><span class="sxs-lookup"><span data-stu-id="359e2-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

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

<span data-ttu-id="359e2-143">Beachten Sie, dass ein Zeilenumbruch topologische Ebenen trennt, wobei jede Ebene später alphanumerisch sortiert wird.</span><span class="sxs-lookup"><span data-stu-id="359e2-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="359e2-144">Dadurch wird Code ordnungsgemäß organisiert, ohne versehentlich Werte zu shadoauen.</span><span class="sxs-lookup"><span data-stu-id="359e2-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="359e2-145">Verwenden von Klassen zum enthalten von Werten mit Nebeneffekten</span><span class="sxs-lookup"><span data-stu-id="359e2-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="359e2-146">Es gibt viele Male, wenn ein Wert initialisiert werden kann, z. b. beim Instanziieren eines Kontexts in einer Datenbank oder einer anderen Remote Ressource.</span><span class="sxs-lookup"><span data-stu-id="359e2-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="359e2-147">Es ist verlockend, solche Dinge in einem Modul zu initialisieren und in nachfolgenden Funktionen zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="359e2-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

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

<span data-ttu-id="359e2-148">Dies ist aus einigen Gründen häufig eine gute Idee:</span><span class="sxs-lookup"><span data-stu-id="359e2-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="359e2-149">Zuerst wird die Anwendungskonfiguration mit `dep1` und `dep2`in die Codebasis übermittelt.</span><span class="sxs-lookup"><span data-stu-id="359e2-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="359e2-150">Dies ist in größeren Codebasen schwierig zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="359e2-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="359e2-151">Zweitens sollten statisch initialisierte Daten keine Werte enthalten, die nicht Thread sicher sind, wenn die Komponente selbst mehrere Threads verwendet.</span><span class="sxs-lookup"><span data-stu-id="359e2-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="359e2-152">Dies wird durch `dep3`eindeutig verletzt.</span><span class="sxs-lookup"><span data-stu-id="359e2-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="359e2-153">Schließlich wird die Modul Initialisierung in einen statischen Konstruktor für die gesamte Kompilierungseinheit kompiliert.</span><span class="sxs-lookup"><span data-stu-id="359e2-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="359e2-154">Wenn ein Fehler bei der Initialisierung von Let-gebundenen Werten in diesem Modul auftritt, stellt er eine `TypeInitializationException` dar, die für die gesamte Lebensdauer der Anwendung zwischengespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="359e2-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="359e2-155">Dies kann schwierig zu diagnostizieren sein.</span><span class="sxs-lookup"><span data-stu-id="359e2-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="359e2-156">Es gibt in der Regel eine innere Ausnahme, die Sie zu einem bestimmten Zweck haben können. wenn dies nicht der Fall ist, gibt es nicht, was die Grundursache ist.</span><span class="sxs-lookup"><span data-stu-id="359e2-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="359e2-157">Verwenden Sie stattdessen einfach eine einfache Klasse zum Speichern von Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="359e2-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member __.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member __.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="359e2-158">Dies ermöglicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="359e2-158">This enables the following:</span></span>

1. <span data-ttu-id="359e2-159">Verschieben eines beliebigen abhängigen Zustands außerhalb der API selbst.</span><span class="sxs-lookup"><span data-stu-id="359e2-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="359e2-160">Die Konfiguration kann nun außerhalb der API durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="359e2-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="359e2-161">Fehler bei der Initialisierung der abhängigen Werte werden wahrscheinlich nicht als `TypeInitializationException`angezeigt.</span><span class="sxs-lookup"><span data-stu-id="359e2-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="359e2-162">Die API ist jetzt einfacher zu testen.</span><span class="sxs-lookup"><span data-stu-id="359e2-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="359e2-163">Fehler Verwaltung</span><span class="sxs-lookup"><span data-stu-id="359e2-163">Error management</span></span>

<span data-ttu-id="359e2-164">Die Fehler Verwaltung in großen Systemen ist ein komplexes und differenziertes Verhalten, und es gibt keine Silber Aufzählungen, um sicherzustellen, dass Ihre Systeme fehlertolerant sind und sich gut Verhalten.</span><span class="sxs-lookup"><span data-stu-id="359e2-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="359e2-165">Die folgenden Richtlinien sollten Anleitungen zum Navigieren in diesem schwierigen Bereich bieten.</span><span class="sxs-lookup"><span data-stu-id="359e2-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="359e2-166">Darstellen von Fehler Fällen und ungültigen Zuständen in Typen, die in Ihrer Domäne intrinsisch sind</span><span class="sxs-lookup"><span data-stu-id="359e2-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="359e2-167">Mit [Unterscheidungs](../language-reference/discriminated-unions.md)- F# Unions haben Sie die Möglichkeit, einen fehlerhaften Programmzustand in Ihrem Typsystem darzustellen.</span><span class="sxs-lookup"><span data-stu-id="359e2-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="359e2-168">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="359e2-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="359e2-169">In diesem Fall gibt es drei bekannte Möglichkeiten, dass das Zurückziehen von Geld aus einem Bankkonto fehlschlagen kann.</span><span class="sxs-lookup"><span data-stu-id="359e2-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="359e2-170">Jeder Fehlerfall wird im-Typ dargestellt und kann daher sicher im gesamten Programm behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="359e2-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="359e2-171">Wenn Sie die verschiedenen Methoden modellieren können, mit denen in Ihrer Domäne ein Fehler **auftreten kann,** wird der Fehler Behandlungs Code nicht mehr als etwas behandelt, mit dem Sie zusätzlich zum regulären Programmablauf arbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="359e2-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="359e2-172">Es ist einfach ein Teil des normalen Programmflusses und wird nicht als **außergewöhnlich**angesehen.</span><span class="sxs-lookup"><span data-stu-id="359e2-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="359e2-173">Dies hat zwei wesentliche Vorteile:</span><span class="sxs-lookup"><span data-stu-id="359e2-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="359e2-174">Sie ist einfacher zu verwalten, wenn sich Ihre Domäne im Laufe der Zeit ändert.</span><span class="sxs-lookup"><span data-stu-id="359e2-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="359e2-175">Fehlerfälle sind einfacher für Komponententests.</span><span class="sxs-lookup"><span data-stu-id="359e2-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="359e2-176">Verwenden Sie Ausnahmen, wenn Fehler nicht mit Typen dargestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="359e2-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="359e2-177">Nicht alle Fehler können in einer Problemdomäne dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="359e2-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="359e2-178">Diese Arten von Fehlern sind *außergewöhnlich* , sodass Ausnahmen in F#ausgelöst und abgefangen werden können.</span><span class="sxs-lookup"><span data-stu-id="359e2-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="359e2-179">Zuerst wird empfohlen, dass Sie die [Richtlinien für den Ausnahme Entwurf](../../standard/design-guidelines/exceptions.md)lesen.</span><span class="sxs-lookup"><span data-stu-id="359e2-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="359e2-180">Diese sind auch auf F#anwendbar.</span><span class="sxs-lookup"><span data-stu-id="359e2-180">These are also applicable to F#.</span></span>

<span data-ttu-id="359e2-181">Die in F# verfügbaren Hauptkonstrukte für das Auslassen von Ausnahmen sollten in der folgenden Reihenfolge berücksichtigt werden:</span><span class="sxs-lookup"><span data-stu-id="359e2-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="359e2-182">Funktion</span><span class="sxs-lookup"><span data-stu-id="359e2-182">Function</span></span> | <span data-ttu-id="359e2-183">Syntax</span><span class="sxs-lookup"><span data-stu-id="359e2-183">Syntax</span></span> | <span data-ttu-id="359e2-184">Zweck</span><span class="sxs-lookup"><span data-stu-id="359e2-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="359e2-185">Löst eine `System.ArgumentNullException` mit dem angegebenen Argument Namen aus.</span><span class="sxs-lookup"><span data-stu-id="359e2-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="359e2-186">Löst eine `System.ArgumentException` mit einem angegebenen Argument Namen und einer angegebenen Meldung aus.</span><span class="sxs-lookup"><span data-stu-id="359e2-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="359e2-187">Löst eine `System.InvalidOperationException` mit der angegebenen Meldung aus.</span><span class="sxs-lookup"><span data-stu-id="359e2-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="359e2-188">Allgemeiner Mechanismus zum Auslösen von Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="359e2-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="359e2-189">Löst eine `System.Exception` mit der angegebenen Meldung aus.</span><span class="sxs-lookup"><span data-stu-id="359e2-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="359e2-190">Löst eine `System.Exception` mit einer Meldung aus, die von der Format Zeichenfolge und den zugehörigen Eingaben bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="359e2-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="359e2-191">Verwenden Sie `nullArg`, `invalidArg` und `invalidOp` als Mechanismus, um bei Bedarf `ArgumentNullException`, `ArgumentException` und `InvalidOperationException` auszulösen.</span><span class="sxs-lookup"><span data-stu-id="359e2-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="359e2-192">Die Funktionen `failwith` und `failwithf` sollten im allgemeinen vermieden werden, da Sie den Basis `Exception` Typ und nicht eine bestimmte Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="359e2-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="359e2-193">Gemäß den [Richtlinien für den Ausnahme Entwurf](../../standard/design-guidelines/exceptions.md)sollten Sie spezifischere Ausnahmen auslöst, wenn dies möglich ist.</span><span class="sxs-lookup"><span data-stu-id="359e2-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="359e2-194">Verwenden der Syntax für die Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="359e2-194">Using exception-handling syntax</span></span>

<span data-ttu-id="359e2-195">F#unterstützt Ausnahme Muster über die`try...with`-Syntax:</span><span class="sxs-lookup"><span data-stu-id="359e2-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="359e2-196">Die Abstimmung von Funktionen, die im Falle einer Ausnahme mit Musterabgleich durchgeführt werden sollen, kann etwas kompliziert sein, wenn Sie den Code bereinigen möchten.</span><span class="sxs-lookup"><span data-stu-id="359e2-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="359e2-197">Eine solche Vorgehensweise ist die Verwendung [aktiver Muster](../language-reference/active-patterns.md) als Mittel zum Gruppieren von Funktionen in Bezug auf einen Fehlerfall mit einer Ausnahme selbst.</span><span class="sxs-lookup"><span data-stu-id="359e2-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="359e2-198">Beispielsweise können Sie eine API nutzen, die beim Auslösen einer Ausnahme wertvolle Informationen in die Ausnahme Metadaten einschließt.</span><span class="sxs-lookup"><span data-stu-id="359e2-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="359e2-199">In einigen Situationen kann es hilfreich sein, einen nützlichen Wert im Text der erfassten Ausnahme innerhalb des aktiven Musters zu entpacken und diesen Wert zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="359e2-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="359e2-200">Verwenden Sie keine monadische-Fehlerbehandlung zum Ersetzen von Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="359e2-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="359e2-201">Ausnahmen werden bei der funktionalen Programmierung als etwas Tabu betrachtet.</span><span class="sxs-lookup"><span data-stu-id="359e2-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="359e2-202">Tatsächlich verstoßen Ausnahmen gegen Reinheit, daher ist es sicher, dass Sie nicht Recht funktional betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="359e2-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="359e2-203">Dies ignoriert jedoch die Realität, in der der Code ausgeführt werden muss, und dass Laufzeitfehler auftreten können.</span><span class="sxs-lookup"><span data-stu-id="359e2-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="359e2-204">Schreiben Sie im allgemeinen Code in der Annahme, dass die meisten Dinge weder rein noch Gesamt sind, um unangenehme Überraschungen zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="359e2-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="359e2-205">Es ist wichtig, die folgenden Hauptstärken/Aspekte von Ausnahmen hinsichtlich ihrer Relevanz und Eignung in der .NET-Laufzeit und im sprachübergreifenden Ökosystem als Ganzes zu berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="359e2-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="359e2-206">Sie enthalten ausführliche Diagnoseinformationen, die beim Debuggen eines Problems sehr hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="359e2-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="359e2-207">Sie werden von der Laufzeit und anderen .NET-Sprachen gut verstanden.</span><span class="sxs-lookup"><span data-stu-id="359e2-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="359e2-208">Sie können im Vergleich zu Code, der aus seiner Methode entfernt *wird, signifikante* Bausteine verringern, indem eine Teilmenge ihrer Semantik auf Ad-hoc-Basis implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="359e2-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="359e2-209">Dieser dritte Punkt ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="359e2-209">This third point is critical.</span></span> <span data-ttu-id="359e2-210">Bei nicht trivialen komplexen Vorgängen kann das Verwenden von Ausnahmen zum Umgang mit Strukturen wie diesem führen:</span><span class="sxs-lookup"><span data-stu-id="359e2-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="359e2-211">Dies kann problemlos zu zerbrechlichem Code wie Muster Übereinstimmungen bei "getyptypisierten" Fehlern führen:</span><span class="sxs-lookup"><span data-stu-id="359e2-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="359e2-212">Außerdem kann es verlockend sein, jede Ausnahme im Wunsch nach einer "einfachen" Funktion zu verschlucken, die einen "schöneren" Typ zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="359e2-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="359e2-213">Leider können `tryReadAllText` basierend auf den unzähligen Dingen, die auf einem Dateisystem auftreten können, zahlreiche Ausnahmen auslösen, und dieser Code verwirft alle Informationen über das, was in Ihrer Umgebung tatsächlich schief geht.</span><span class="sxs-lookup"><span data-stu-id="359e2-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="359e2-214">Wenn Sie diesen Code durch einen Ergebnistyp ersetzen, werden Sie wieder zur "erstaunlich typisierten" Fehlermeldungs-Verarbeitung zurückkehren:</span><span class="sxs-lookup"><span data-stu-id="359e2-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

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

<span data-ttu-id="359e2-215">Wenn Sie das Ausnahme Objekt selbst in den `Error`-Konstruktor platzieren, erzwingen Sie lediglich, dass Sie den Ausnahmetyp an der aufrufssite und nicht in der Funktion ordnungsgemäß behandeln.</span><span class="sxs-lookup"><span data-stu-id="359e2-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="359e2-216">Auf diese Weise werden überprüfte Ausnahmen erstellt, die bekanntermaßen als Aufrufer einer API behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="359e2-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="359e2-217">Eine gute Alternative zu den obigen Beispielen besteht darin, *bestimmte* Ausnahmen abzufangen und einen sinnvollen Wert im Kontext dieser Ausnahme zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="359e2-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="359e2-218">Wenn Sie die `tryReadAllText` Funktion wie folgt ändern, hat `None` mehr Bedeutung:</span><span class="sxs-lookup"><span data-stu-id="359e2-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="359e2-219">Anstatt als Catch-all zu funktionieren, verarbeitet diese Funktion nun ordnungsgemäß den Fall, dass eine Datei nicht gefunden wurde, und weist diese Bedeutung einer Rückgabe zu.</span><span class="sxs-lookup"><span data-stu-id="359e2-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="359e2-220">Dieser Rückgabewert kann diesem Fehlerfall zugeordnet werden, während keine Kontextinformationen verworfen werden oder Aufrufer gezwungen werden, einen Fall zu behandeln, der an diesem Punkt im Code möglicherweise nicht relevant ist.</span><span class="sxs-lookup"><span data-stu-id="359e2-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="359e2-221">Typen wie `Result<'Success, 'Error>` eignen sich für grundlegende Vorgänge, bei denen Sie nicht eingebettet sind F# , und optionale Typen eignen sich perfekt für die Darstellung, wenn *etwas oder* *nichts*zurückgegeben werden könnte.</span><span class="sxs-lookup"><span data-stu-id="359e2-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="359e2-222">Sie sind jedoch kein Ersatz für Ausnahmen und sollten nicht in einem Versuch verwendet werden, Ausnahmen zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="359e2-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="359e2-223">Vielmehr sollten Sie umsichtig angewendet werden, um bestimmte Aspekte der Ausnahme-und Fehler Verwaltungs Richtlinie in gezielter Weise zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="359e2-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="359e2-224">Partielle Anwendungs-und punktfreie Programmierung</span><span class="sxs-lookup"><span data-stu-id="359e2-224">Partial application and point-free programming</span></span>

<span data-ttu-id="359e2-225">F#unterstützt die partielle Anwendung und somit verschiedene Methoden zum Programmieren in einem Point-Free-Stil.</span><span class="sxs-lookup"><span data-stu-id="359e2-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="359e2-226">Dies kann für die Wiederverwendung von Code in einem Modul oder die Implementierung von etwas von Vorteil sein, aber es ist in der Regel nicht öffentlich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="359e2-226">This can be beneficial for code reuse within a module or the implementation of something, but it is generally not something to expose publicly.</span></span> <span data-ttu-id="359e2-227">Im Allgemeinen ist die Point-Free-Programmierung keine Grundlage für sich selbst und kann eine bedeutende kognitive Barriere für Personen hinzufügen, die nicht in den Stil eintauchen.</span><span class="sxs-lookup"><span data-stu-id="359e2-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="359e2-228">Verwenden Sie keine partielle Anwendung und Currying in öffentlichen APIs.</span><span class="sxs-lookup"><span data-stu-id="359e2-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="359e2-229">Mit wenigen Ausnahmen kann die Verwendung einer partiellen Anwendung in öffentlichen APIs für Consumer verwirrend sein.</span><span class="sxs-lookup"><span data-stu-id="359e2-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="359e2-230">In der Regel sind `let`gebundene Werte F# im Code **Werte**und keine **Funktions Werte**.</span><span class="sxs-lookup"><span data-stu-id="359e2-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="359e2-231">Das Kombinieren von Werten und Funktionswerten kann dazu führen, dass eine kleine Anzahl von Codezeilen in Exchange für einen sehr viel kognitiven mehr Aufwand gespeichert wird. Dies gilt insbesondere, wenn Sie mit Operatoren wie `>>` kombiniert werden, um Funktionen zu verfassen.</span><span class="sxs-lookup"><span data-stu-id="359e2-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="359e2-232">Sehen Sie sich die Auswirkungen auf die Tools für die punktfreie Programmierung an</span><span class="sxs-lookup"><span data-stu-id="359e2-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="359e2-233">Geschweiften Funktionen bezeichnen ihre Argumente nicht.</span><span class="sxs-lookup"><span data-stu-id="359e2-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="359e2-234">Dies hat Auswirkungen auf das Tool.</span><span class="sxs-lookup"><span data-stu-id="359e2-234">This has tooling implications.</span></span> <span data-ttu-id="359e2-235">Beachten Sie die folgenden zwei Funktionen:</span><span class="sxs-lookup"><span data-stu-id="359e2-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="359e2-236">Beide sind gültige Funktionen, `funcWithApplication` aber eine Curry-Funktion ist.</span><span class="sxs-lookup"><span data-stu-id="359e2-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="359e2-237">Wenn Sie mit dem Mauszeiger auf die Typen in einem Editor zeigen, sehen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="359e2-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="359e2-238">In Tools wie Visual Studio erhalten Sie auf der Website des Aufrufes keine aussagekräftigen Informationen darüber, was die `string`-und `int` Eingabetypen tatsächlich darstellen.</span><span class="sxs-lookup"><span data-stu-id="359e2-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="359e2-239">Wenn Sie auf einen Punkt freien Code wie `funcWithApplication` stoßen, der öffentlich genutzt werden kann, empfiehlt es sich, eine vollständige weiterung-Erweiterung durchzuführen, damit die Tools für Argumente aussagekräftige Namen erhalten.</span><span class="sxs-lookup"><span data-stu-id="359e2-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="359e2-240">Außerdem kann das Debuggen von Punkt freiem Code eine Herausforderung darstellen, wenn dies nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="359e2-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="359e2-241">Debugtools basieren auf Werten, die an Namen gebunden sind (z. b. `let` Bindungen), sodass Sie Zwischenwerte in der Mitte der Ausführung überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="359e2-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="359e2-242">Wenn Ihr Code keine zu überprüfenden Werte aufweist, müssen Sie nichts Debuggen.</span><span class="sxs-lookup"><span data-stu-id="359e2-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="359e2-243">In Zukunft werden Debuggingtools möglicherweise so weiterentwickelt, dass diese Werte auf der Grundlage zuvor ausgeführter Pfade synthetisieren werden, aber es ist keine gute Idee, Ihre Wetten auf *potenzielle* Debuggingfunktionen zu</span><span class="sxs-lookup"><span data-stu-id="359e2-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="359e2-244">Als Verfahren zum reduzieren interner Bausteine sollten Sie eine partielle Anwendung als Technik in Erwägung gezogen</span><span class="sxs-lookup"><span data-stu-id="359e2-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="359e2-245">Im Gegensatz zum vorherigen Punkt ist die partielle Anwendung ein wunderbares Tool zum Reduzieren von Code Steinen innerhalb einer Anwendung oder der tieferen internale einer API.</span><span class="sxs-lookup"><span data-stu-id="359e2-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="359e2-246">Dies kann hilfreich für Komponententests bei der Implementierung komplizierterer APIs sein, bei denen Code Bausteine häufig ein Problem ist.</span><span class="sxs-lookup"><span data-stu-id="359e2-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="359e2-247">Der folgende Code zeigt beispielsweise, wie Sie die meisten optimalen Frameworks durchführen können, ohne eine externe Abhängigkeit von einem solchen Framework zu treffen und eine Verwandte, maßgeschneiderte API erlernen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="359e2-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="359e2-248">Sehen Sie sich beispielsweise die folgende Lösungs Topografie an:</span><span class="sxs-lookup"><span data-stu-id="359e2-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="359e2-249">`ImplementationLogic.fsproj` können Code wie z. b. verfügbar machen:</span><span class="sxs-lookup"><span data-stu-id="359e2-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member __.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="359e2-250">Das `Transactions.doTransaction` von Unittests in `ImplementationLogic.Tests.fsproj` ist einfach:</span><span class="sxs-lookup"><span data-stu-id="359e2-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fsproj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="359e2-251">Durch das partielle Anwenden von `doTransaction` mit einem Kontext Objekt können Sie die Funktion in allen Komponententests aufzurufen, ohne jedes Mal einen simulierte Kontext erstellen zu müssen:</span><span class="sxs-lookup"><span data-stu-id="359e2-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

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

<span data-ttu-id="359e2-252">Diese Technik sollte nicht universell auf die gesamte CodeBase angewendet werden, aber Sie ist eine gute Möglichkeit, die Bausteine für komplizierte internale und Unittests zu verringern.</span><span class="sxs-lookup"><span data-stu-id="359e2-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="359e2-253">Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="359e2-253">Access control</span></span>

<span data-ttu-id="359e2-254">F#verfügt über mehrere Optionen für die [Zugriffs Steuerung](../language-reference/access-control.md), die von den in der .NET-Laufzeit verfügbaren Funktionen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="359e2-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="359e2-255">Diese können nicht nur für Typen verwendet werden. Sie können Sie auch für Funktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="359e2-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="359e2-256">Bevorzugen Sie nicht`public` Typen und Member, bis Sie öffentlich nutzbar sein müssen.</span><span class="sxs-lookup"><span data-stu-id="359e2-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="359e2-257">Dadurch wird auch das Paar der Consumer minimiert.</span><span class="sxs-lookup"><span data-stu-id="359e2-257">This also minimizes what consumers couple to.</span></span>
* <span data-ttu-id="359e2-258">Sorgen Sie dafür, dass alle Hilfsfunktionen `private`werden.</span><span class="sxs-lookup"><span data-stu-id="359e2-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="359e2-259">Beachten Sie die Verwendung von `[<AutoOpen>]` in einem privaten Modul von Hilfsfunktionen, wenn Sie zahlreich werden.</span><span class="sxs-lookup"><span data-stu-id="359e2-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="359e2-260">Typrückschluss und Generika</span><span class="sxs-lookup"><span data-stu-id="359e2-260">Type inference and generics</span></span>

<span data-ttu-id="359e2-261">Mithilfe des Typrückschlusses können Sie viele Bausteine speichern.</span><span class="sxs-lookup"><span data-stu-id="359e2-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="359e2-262">Und die F# automatische Generalisierung im Compiler können Sie dabei unterstützen, allgemeineren Code zu schreiben, bei dem Sie fast keinen zusätzlichen Aufwand benötigen.</span><span class="sxs-lookup"><span data-stu-id="359e2-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="359e2-263">Diese Features sind jedoch nicht universell geeignet.</span><span class="sxs-lookup"><span data-stu-id="359e2-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="359e2-264">Sie sollten Argument Namen mit expliziten Typen in öffentlichen APIs bezeichnen und sind hierfür nicht auf den Typrückschluss angewiesen.</span><span class="sxs-lookup"><span data-stu-id="359e2-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="359e2-265">Der Grund hierfür ist, dass **Sie** die Form ihrer API steuern müssen, nicht den Compiler.</span><span class="sxs-lookup"><span data-stu-id="359e2-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="359e2-266">Obwohl der Compiler eine gute Aufgabe beim Ableiten von Typen für Sie erledigen kann, ist es möglich, dass sich die Form der API ändert, wenn sich die internale, auf die Sie sich verlassen, geändert haben.</span><span class="sxs-lookup"><span data-stu-id="359e2-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="359e2-267">Das ist möglicherweise das, was Sie möchten, aber es führt fast sicherlich zu einer wichtigen API-Änderung, die Downstreamconsumer dann behandeln müssen.</span><span class="sxs-lookup"><span data-stu-id="359e2-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="359e2-268">Wenn Sie die Form ihrer öffentlichen API explizit steuern, können Sie stattdessen diese wichtigen Änderungen steuern.</span><span class="sxs-lookup"><span data-stu-id="359e2-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="359e2-269">In DDD-Begriffen kann dies als antibeschädigungs Schicht angesehen werden.</span><span class="sxs-lookup"><span data-stu-id="359e2-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="359e2-270">Sie sollten den generischen Argumenten einen aussagekräftigen Namen geben.</span><span class="sxs-lookup"><span data-stu-id="359e2-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="359e2-271">Wenn Sie nicht wirklich generischen Code schreiben, der nicht spezifisch für eine bestimmte Domäne ist, kann ein aussagekräftiger Name anderen Programmierern helfen, die Domäne, in der Sie arbeiten, zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="359e2-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="359e2-272">Ein Typparameter mit dem Namen `'Document` im Kontext der Interaktion mit einer dokumentdatenbank macht es z. b. klarer, dass generische Dokumenttypen von der Funktion oder dem Member akzeptiert werden können, mit der Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="359e2-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="359e2-273">Es empfiehlt sich, generische Typparameter mit PascalCase zu benennen.</span><span class="sxs-lookup"><span data-stu-id="359e2-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="359e2-274">Dies ist die allgemeine Art und Weise, wie es in .net der Fall ist. es wird empfohlen, anstelle von snake_case oder CamelCase den Wert PascalCase zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="359e2-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="359e2-275">Zum Schluss ist die automatische Generalisierung nicht immer ein Segen für Personen, die F# noch keine neue oder große CodeBase haben.</span><span class="sxs-lookup"><span data-stu-id="359e2-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="359e2-276">Es gibt einen kognitiven Aufwand bei der Verwendung generischer Komponenten.</span><span class="sxs-lookup"><span data-stu-id="359e2-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="359e2-277">Wenn außerdem automatisch verallgemeinerte Funktionen nicht mit unterschiedlichen Eingabetypen verwendet werden (selbst wenn Sie als solche verwendet werden sollen), gibt es keinen echten Vorteil, wenn Sie zu diesem Zeitpunkt generisch sind.</span><span class="sxs-lookup"><span data-stu-id="359e2-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="359e2-278">Denken Sie immer daran, ob der Code, den Sie schreiben, tatsächlich von generischen Vorteilen profitiert.</span><span class="sxs-lookup"><span data-stu-id="359e2-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="359e2-279">Leistung</span><span class="sxs-lookup"><span data-stu-id="359e2-279">Performance</span></span>

<span data-ttu-id="359e2-280">F#Werte sind standardmäßig unveränderlich, sodass Sie bestimmte Klassen von Fehlern vermeiden können (insbesondere solche, die Parallelität und Parallelität betreffen).</span><span class="sxs-lookup"><span data-stu-id="359e2-280">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="359e2-281">In bestimmten Fällen, um eine optimale (oder sogar sinnvolle) Effizienz der Ausführungszeit oder Speicher Belegungen zu erzielen, kann jedoch eine bestimmte arbeitsspanne am besten mithilfe einer direkten Mutation des Zustands implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="359e2-281">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="359e2-282">Dies ist in einer Opt-in-Basis F# mit dem`mutable`-Schlüsselwort möglich.</span><span class="sxs-lookup"><span data-stu-id="359e2-282">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="359e2-283">Die Verwendung von `mutable` in F# kann sich jedoch mit der funktionalen Reinheit widersprechen.</span><span class="sxs-lookup"><span data-stu-id="359e2-283">However, use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="359e2-284">Dies ist in Ordnung, wenn Sie die Erwartungen von der Reinheit an die [referenzielle Transparenz](https://en.wikipedia.org/wiki/Referential_transparency)anpassen.</span><span class="sxs-lookup"><span data-stu-id="359e2-284">This is fine, if you adjust expectations from purity to [referential transparency](https://en.wikipedia.org/wiki/Referential_transparency).</span></span> <span data-ttu-id="359e2-285">Referenzielle Transparenz (nicht Reinheit) ist das Endziel beim Schreiben F# von Funktionen.</span><span class="sxs-lookup"><span data-stu-id="359e2-285">Referential transparency - not purity - is the end goal when writing F# functions.</span></span> <span data-ttu-id="359e2-286">Dies ermöglicht es Ihnen, eine funktionale Schnittstelle über eine mutations basierte Implementierung für Leistungs kritischen Code zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="359e2-286">This allows you to write a functional interface over a mutation-based implementation for performance critical code.</span></span>

### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="359e2-287">Umbruch von änderbaren Code in unveränderlichen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="359e2-287">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="359e2-288">Mit referenzieller Transparenz als Ziel ist es wichtig, Code zu schreiben, der den änderbaren Unterbauch von Leistungs kritischen Funktionen nicht verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="359e2-288">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="359e2-289">Der folgende Code implementiert beispielsweise die `Array.contains`-Funktion in der F# Kernbibliothek:</span><span class="sxs-lookup"><span data-stu-id="359e2-289">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

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

<span data-ttu-id="359e2-290">Wenn Sie diese Funktion mehrmals aufrufen, wird das zugrunde liegende Array nicht geändert, und es ist nicht erforderlich, dass Sie einen änderbaren Zustand bei der Nutzung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="359e2-290">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="359e2-291">Sie ist referenziell transparent, obwohl fast jede Codezeile darin eine Mutation verwendet.</span><span class="sxs-lookup"><span data-stu-id="359e2-291">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="359e2-292">Sie sollten änderbare Daten in Klassen kapseln.</span><span class="sxs-lookup"><span data-stu-id="359e2-292">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="359e2-293">Im vorherigen Beispiel wurde eine einzelne Funktion verwendet, um Vorgänge mit veränderbaren Daten zu kapseln.</span><span class="sxs-lookup"><span data-stu-id="359e2-293">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="359e2-294">Dies ist für komplexere Datensätze nicht immer ausreichend.</span><span class="sxs-lookup"><span data-stu-id="359e2-294">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="359e2-295">Beachten Sie die folgenden Funktions Sätze:</span><span class="sxs-lookup"><span data-stu-id="359e2-295">Consider the following sets of functions:</span></span>

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

<span data-ttu-id="359e2-296">Dieser Code ist leistungsfähig, macht aber die mutations basierte Datenstruktur verfügbar, die Aufrufer für die Wartung verantwortlich sind.</span><span class="sxs-lookup"><span data-stu-id="359e2-296">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="359e2-297">Dies kann in einer Klasse ohne zugrunde liegende Member umschließt werden, die sich ändern können:</span><span class="sxs-lookup"><span data-stu-id="359e2-297">This can be wrapped inside of a class with no underlying members that can change:</span></span>

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

<span data-ttu-id="359e2-298">`Closure1Table` kapselt die zugrunde liegende mutations basierte Datenstruktur und erzwingt dadurch keine Aufrufer, die zugrunde liegende Datenstruktur beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="359e2-298">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="359e2-299">Klassen sind eine leistungsstarke Möglichkeit, Daten und Routinen zu kapseln, die mutations basiert sind, ohne die Details für Aufrufer verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="359e2-299">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="359e2-300">`let mutable` für den Verweis auf Zellen bevorzugen</span><span class="sxs-lookup"><span data-stu-id="359e2-300">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="359e2-301">Verweis Zellen können anstelle des Werts selbst den Verweis auf einen Wert darstellen.</span><span class="sxs-lookup"><span data-stu-id="359e2-301">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="359e2-302">Obwohl Sie für Leistungs kritischen Code verwendet werden können, werden Sie im Allgemeinen nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="359e2-302">Although they can be used for performance-critical code, they are generally not recommended.</span></span> <span data-ttu-id="359e2-303">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="359e2-303">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="359e2-304">Durch die Verwendung einer Referenzzelle wird nun der gesamte nachfolgende Code "verschmutzt", wobei die zugrunde liegenden Daten dereferenziert und neu referenziert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="359e2-304">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="359e2-305">Beachten Sie stattdessen `let mutable`:</span><span class="sxs-lookup"><span data-stu-id="359e2-305">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="359e2-306">Abgesehen von der einzelnen Stelle der Mutation in der Mitte des Lambda-Ausdrucks kann der gesamte Code, der `acc` berührt, so vorgehen, dass er sich nicht von der Verwendung eines normalen `let`gebundenen unveränderlichen Werts unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="359e2-306">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="359e2-307">Dadurch wird es einfacher, sich im Laufe der Zeit zu ändern.</span><span class="sxs-lookup"><span data-stu-id="359e2-307">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="359e2-308">Objekt Programmierung</span><span class="sxs-lookup"><span data-stu-id="359e2-308">Object programming</span></span>

<span data-ttu-id="359e2-309">F#bietet vollständige Unterstützung für Objekte und objektorientierte Konzepte (OO).</span><span class="sxs-lookup"><span data-stu-id="359e2-309">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="359e2-310">Obwohl viele OO-Konzepte leistungsstark und nützlich sind, sind nicht alle davon ideal zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="359e2-310">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="359e2-311">Die folgenden Listen bieten Anleitungen zu den Kategorien von OO-Features auf hoher Ebene.</span><span class="sxs-lookup"><span data-stu-id="359e2-311">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="359e2-312">**In vielen Situationen sollten Sie diese Features verwenden:**</span><span class="sxs-lookup"><span data-stu-id="359e2-312">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="359e2-313">Punkt Notation (`x.Length`)</span><span class="sxs-lookup"><span data-stu-id="359e2-313">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="359e2-314">Instanzmember</span><span class="sxs-lookup"><span data-stu-id="359e2-314">Instance members</span></span>
* <span data-ttu-id="359e2-315">Implizite Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="359e2-315">Implicit constructors</span></span>
* <span data-ttu-id="359e2-316">Statische Member</span><span class="sxs-lookup"><span data-stu-id="359e2-316">Static members</span></span>
* <span data-ttu-id="359e2-317">Indexer-Notation (`arr.[x]`)</span><span class="sxs-lookup"><span data-stu-id="359e2-317">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="359e2-318">Benannte und optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="359e2-318">Named and Optional arguments</span></span>
* <span data-ttu-id="359e2-319">Schnittstellen und Schnittstellen Implementierungen</span><span class="sxs-lookup"><span data-stu-id="359e2-319">Interfaces and interface implementations</span></span>

<span data-ttu-id="359e2-320">**Erreichen Sie diese Features nicht zuerst, aber wenden Sie Sie mit Bedacht an, wenn Sie ein Problem lösen können:**</span><span class="sxs-lookup"><span data-stu-id="359e2-320">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="359e2-321">Methodenüberladung</span><span class="sxs-lookup"><span data-stu-id="359e2-321">Method overloading</span></span>
* <span data-ttu-id="359e2-322">Gekapselte änderbare Daten</span><span class="sxs-lookup"><span data-stu-id="359e2-322">Encapsulated mutable data</span></span>
* <span data-ttu-id="359e2-323">Operatoren für Typen</span><span class="sxs-lookup"><span data-stu-id="359e2-323">Operators on types</span></span>
* <span data-ttu-id="359e2-324">Auto-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="359e2-324">Auto properties</span></span>
* <span data-ttu-id="359e2-325">Implementieren von `IDisposable` und `IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="359e2-325">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="359e2-326">Typerweiterungen</span><span class="sxs-lookup"><span data-stu-id="359e2-326">Type extensions</span></span>
* <span data-ttu-id="359e2-327">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="359e2-327">Events</span></span>
* <span data-ttu-id="359e2-328">Strukturen</span><span class="sxs-lookup"><span data-stu-id="359e2-328">Structs</span></span>
* <span data-ttu-id="359e2-329">Delegaten</span><span class="sxs-lookup"><span data-stu-id="359e2-329">Delegates</span></span>
* <span data-ttu-id="359e2-330">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="359e2-330">Enums</span></span>

<span data-ttu-id="359e2-331">**Vermeiden Sie diese Features im Allgemeinen, wenn Sie Sie nicht verwenden müssen:**</span><span class="sxs-lookup"><span data-stu-id="359e2-331">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="359e2-332">Vererbungs basierte Typhierarchien und Implementierungs Vererbung</span><span class="sxs-lookup"><span data-stu-id="359e2-332">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="359e2-333">Nullen und `Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="359e2-333">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="359e2-334">Komposition vor Vererbung bevorzugen</span><span class="sxs-lookup"><span data-stu-id="359e2-334">Prefer composition over inheritance</span></span>

<span data-ttu-id="359e2-335">Die [Komposition über Vererbung](https://en.wikipedia.org/wiki/Composition_over_inheritance) ist eine lange Ausdrucksweise, F# der guter Code entsprechen kann.</span><span class="sxs-lookup"><span data-stu-id="359e2-335">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="359e2-336">Das Grundprinzip ist, dass Sie keine Basisklasse verfügbar machen und Aufrufer zwingen, von dieser Basisklasse zu erben, um die Funktionalität zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="359e2-336">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="359e2-337">Verwenden von Objekt Ausdrücken zum Implementieren von Schnittstellen, wenn Sie keine Klasse benötigen</span><span class="sxs-lookup"><span data-stu-id="359e2-337">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="359e2-338">[Objekt Ausdrücke](../language-reference/object-expressions.md) ermöglichen es Ihnen, Schnittstellen im laufenden Betrieb zu implementieren, wobei die implementierte Schnittstelle an einen Wert gebunden wird, ohne dass dies innerhalb einer Klasse erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="359e2-338">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="359e2-339">Dies ist praktisch, wenn Sie _nur_ die-Schnittstelle implementieren müssen und keine vollständige Klasse benötigen.</span><span class="sxs-lookup"><span data-stu-id="359e2-339">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="359e2-340">Hier ist beispielsweise der Code, der in [ionide](http://ionide.io/) ausgeführt wird, um eine Code Korrektur Aktion bereitzustellen, wenn Sie ein Symbol hinzugefügt haben, für das Sie keine `open`-Anweisung haben:</span><span class="sxs-lookup"><span data-stu-id="359e2-340">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

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

<span data-ttu-id="359e2-341">Da eine Klasse bei der Interaktion mit der Visual Studio Code-API nicht benötigt wird, sind Objekt Ausdrücke hierfür ein ideales Tool.</span><span class="sxs-lookup"><span data-stu-id="359e2-341">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="359e2-342">Sie sind auch für Komponententests nützlich, wenn Sie eine Schnittstelle mit Testroutinen auf Ad-hoc-Weise auslagern möchten.</span><span class="sxs-lookup"><span data-stu-id="359e2-342">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="consider-type-abbreviations-to-shorten-signatures"></a><span data-ttu-id="359e2-343">Typabkürzungen zum Verkürzen von Signaturen in Erwägung gezogen</span><span class="sxs-lookup"><span data-stu-id="359e2-343">Consider Type Abbreviations to shorten signatures</span></span>

<span data-ttu-id="359e2-344">[Typabkürzungen](../language-reference/type-abbreviations.md) sind eine bequeme Möglichkeit, einem anderen Typ eine Bezeichnung zuzuweisen, z. b. eine Funktions Signatur oder einen komplexeren Typ.</span><span class="sxs-lookup"><span data-stu-id="359e2-344">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="359e2-345">Der folgende Alias weist z. b. eine Bezeichnung zu, die zum Definieren einer Berechnung mit [cntk](https://docs.microsoft.com/cognitive-toolkit/), einer Deep Learning-Bibliothek, benötigt wird:</span><span class="sxs-lookup"><span data-stu-id="359e2-345">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://docs.microsoft.com/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="359e2-346">Der `Computation` Name ist eine bequeme Möglichkeit, jede Funktion anzugeben, die mit der Signatur übereinstimmt, die Sie Aliasing.</span><span class="sxs-lookup"><span data-stu-id="359e2-346">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="359e2-347">Die Verwendung von typabkürzungen wie diesem ist praktisch und ermöglicht einen kompakteren Code.</span><span class="sxs-lookup"><span data-stu-id="359e2-347">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="359e2-348">Vermeiden Sie die Verwendung von typabkürzungen zur Darstellung Ihrer Domäne.</span><span class="sxs-lookup"><span data-stu-id="359e2-348">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="359e2-349">Obwohl typabkürzungen für die Angabe eines Namens an Funktions Signaturen geeignet sind, können Sie beim abkürzen anderer Typen verwirrend sein.</span><span class="sxs-lookup"><span data-stu-id="359e2-349">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="359e2-350">Beachten Sie diese Abkürzung:</span><span class="sxs-lookup"><span data-stu-id="359e2-350">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="359e2-351">Dies kann auf verschiedene Arten verwirrend sein:</span><span class="sxs-lookup"><span data-stu-id="359e2-351">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="359e2-352">`BufferSize` ist keine Abstraktion. Es ist nur ein anderer Name für eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="359e2-352">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="359e2-353">Wenn `BufferSize` in einer öffentlichen API verfügbar gemacht wird, kann es leicht interpretiert werden, um mehr als nur `int`zu bedeuten.</span><span class="sxs-lookup"><span data-stu-id="359e2-353">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="359e2-354">Im allgemeinen weisen Domänen Typen mehrere Attribute auf und sind keine primitiven Typen wie `int`.</span><span class="sxs-lookup"><span data-stu-id="359e2-354">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="359e2-355">Diese Abkürzung verstößt gegen diese Annahme.</span><span class="sxs-lookup"><span data-stu-id="359e2-355">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="359e2-356">Die Schreibweise von `BufferSize` (PascalCase) impliziert, dass dieser Typ mehr Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="359e2-356">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="359e2-357">Dieser Alias bietet im Vergleich zur Bereitstellung eines benannten Arguments für eine Funktion keine bessere Übersichtlichkeit.</span><span class="sxs-lookup"><span data-stu-id="359e2-357">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="359e2-358">Die Abkürzung wird in der kompilierten Il nicht angezeigt. Es handelt sich lediglich um eine ganze Zahl, und dieser Alias ist ein Kompilierzeit Konstrukt.</span><span class="sxs-lookup"><span data-stu-id="359e2-358">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

<span data-ttu-id="359e2-359">Zusammenfassend ist der Fall, dass es sich bei den typabkürzungen um **keine** Abstraktionen für die Typen handelt, die Sie abkürzen.</span><span class="sxs-lookup"><span data-stu-id="359e2-359">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="359e2-360">Im vorherigen Beispiel ist `BufferSize` nur eine `int`, die keine zusätzlichen Daten enthält, ebenso wie keine Vorteile des Typsystems neben den bereits vorhandenen `int`.</span><span class="sxs-lookup"><span data-stu-id="359e2-360">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>

<span data-ttu-id="359e2-361">Ein alternativer Ansatz für die Verwendung von typabkürzungen zur Darstellung einer Domäne ist die Verwendung von unitunterscheidungs-Unions.</span><span class="sxs-lookup"><span data-stu-id="359e2-361">An alternative approach to using type abbreviations to represent a domain is to use single-case discriminated unions.</span></span> <span data-ttu-id="359e2-362">Das vorherige Beispiel kann wie folgt modelliert werden:</span><span class="sxs-lookup"><span data-stu-id="359e2-362">The previous sample can be modeled as follows:</span></span>

```fsharp
type BufferSize = BufferSize of int
```

<span data-ttu-id="359e2-363">Wenn Sie Code schreiben, der in Bezug auf `BufferSize` und den zugrunde liegenden Wert funktioniert, müssen Sie einen erstellen, anstatt eine beliebige ganze Zahl zu übergeben:</span><span class="sxs-lookup"><span data-stu-id="359e2-363">If you write code that operates in terms of `BufferSize` and its underlying value, you need to construct one rather than pass in any arbitrary integer:</span></span>

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

<span data-ttu-id="359e2-364">Dadurch wird die Wahrscheinlichkeit verringert, dass versehentlich eine beliebige Ganzzahl an die `send`-Funktion übergeben wird, da der Aufrufer einen `BufferSize`-Typ erstellen muss, um einen Wert vor dem Aufrufen der Funktion einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="359e2-364">This reduces the likelihood of mistakenly passing an arbitrary integer into the `send` function, because the caller must construct a `BufferSize` type to wrap a value before calling the function.</span></span>
