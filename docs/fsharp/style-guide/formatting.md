---
title: Richtlinien für das Formatieren von F#-Code
description: Hier finden Sie Richt F# Linien zum Formatieren von Code
ms.date: 11/04/2019
ms.openlocfilehash: 895c8211731b47bd4c59d762d5806cfc1bfe232d
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089315"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="5bef5-103">Richtlinien für das Formatieren von F#-Code</span><span class="sxs-lookup"><span data-stu-id="5bef5-103">F# code formatting guidelines</span></span>

<span data-ttu-id="5bef5-104">Dieser Artikel enthält Richtlinien zum Formatieren von Code, sodass der F# Code wie folgt lautet:</span><span class="sxs-lookup"><span data-stu-id="5bef5-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="5bef5-105">Allgemein als besser lesbar angesehen</span><span class="sxs-lookup"><span data-stu-id="5bef5-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="5bef5-106">Entspricht den Konventionen, die von den Formatierungs Tools in Visual Studio und anderen Editoren angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="5bef5-107">Vergleichbar mit anderem Code Online</span><span class="sxs-lookup"><span data-stu-id="5bef5-107">Similar to other code online</span></span>

<span data-ttu-id="5bef5-108">Diese Richtlinien basieren auf [einer umfassenden Anleitung zum F# Formatieren von Konventionen](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) nach [Anh-Mist Phan](https://github.com/dungpa).</span><span class="sxs-lookup"><span data-stu-id="5bef5-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="5bef5-109">Allgemeine Regeln für Einzug</span><span class="sxs-lookup"><span data-stu-id="5bef5-109">General rules for indentation</span></span>

<span data-ttu-id="5bef5-110">F#verwendet standardmäßig signifikanter Leerraum.</span><span class="sxs-lookup"><span data-stu-id="5bef5-110">F# uses significant white space by default.</span></span> <span data-ttu-id="5bef5-111">Die folgenden Richtlinien dienen als Leitfaden zum vermitteln einiger Herausforderungen, die dies erzwingen kann.</span><span class="sxs-lookup"><span data-stu-id="5bef5-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="5bef5-112">Verwenden von Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="5bef5-112">Using spaces</span></span>

<span data-ttu-id="5bef5-113">Wenn Einzug erforderlich ist, müssen Sie Leerzeichen und keine Tabulatoren verwenden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="5bef5-114">Es ist mindestens ein Leerzeichen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5bef5-114">At least one space is required.</span></span> <span data-ttu-id="5bef5-115">In Ihrer Organisation können Codierungsstandards erstellt werden, um die Anzahl der für den Einzug zu verwendenden Leerzeichen anzugeben. zwei, drei oder vier Leerzeichen für den Einzug auf jeder Ebene, auf der der Einzug auftritt, ist typisch.</span><span class="sxs-lookup"><span data-stu-id="5bef5-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="5bef5-116">**Es werden 4 Leerzeichen pro Einzug empfohlen.**</span><span class="sxs-lookup"><span data-stu-id="5bef5-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="5bef5-117">Dies bedeutet, dass der Einzug von Programmen eine subjektive Angelegenheit ist.</span><span class="sxs-lookup"><span data-stu-id="5bef5-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="5bef5-118">Variationen sind in Ordnung, aber die erste Regel, die Sie befolgen sollten, ist die *Konsistenz des*Einzugs.</span><span class="sxs-lookup"><span data-stu-id="5bef5-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="5bef5-119">Wählen Sie eine im allgemeinen akzeptierte Art von Einzug aus, und verwenden Sie sie systematisch in der gesamten Codebasis.</span><span class="sxs-lookup"><span data-stu-id="5bef5-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="5bef5-120">Formatieren von Leerraum</span><span class="sxs-lookup"><span data-stu-id="5bef5-120">Formatting white space</span></span>

<span data-ttu-id="5bef5-121">F#ist Leerraum sensibel.</span><span class="sxs-lookup"><span data-stu-id="5bef5-121">F# is white space sensitive.</span></span> <span data-ttu-id="5bef5-122">Obwohl die meisten Semantik aus Leerraum durch den ordnungsgemäßen Einzug abgedeckt ist, müssen einige andere Punkte berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="5bef5-123">Formatierungs Operatoren in arithmetischen Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="5bef5-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="5bef5-124">Verwenden Sie immer Leerraum um binäre arithmetische Ausdrücke:</span><span class="sxs-lookup"><span data-stu-id="5bef5-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="5bef5-125">Unäre `-`-Operatoren sollten immer den Wert aufweisen, den Sie nachvollziehen können:</span><span class="sxs-lookup"><span data-stu-id="5bef5-125">Unary `-` operators should always have the value they are negating immediately follow:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="5bef5-126">Wenn ein Leerzeichen nach dem `-`-Operator hinzugefügt wird, kann dies zu Verwirrung für andere führen.</span><span class="sxs-lookup"><span data-stu-id="5bef5-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="5bef5-127">Zusammenfassend ist es wichtig, immer Folgendes zu beachten:</span><span class="sxs-lookup"><span data-stu-id="5bef5-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="5bef5-128">Binäre Operatoren mit Leerraum umschließen</span><span class="sxs-lookup"><span data-stu-id="5bef5-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="5bef5-129">Nach einem unären Operator nie nachfolgende Leerzeichen enthalten</span><span class="sxs-lookup"><span data-stu-id="5bef5-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="5bef5-130">Die Richtlinie für den binären arithmetischen Operator ist besonders wichtig.</span><span class="sxs-lookup"><span data-stu-id="5bef5-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="5bef5-131">Wenn ein binärer `-` Operator nicht umschließt, in Kombination mit bestimmten Formatierungsoptionen, könnte dies dazu führen, dass er als unäres `-`interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="5bef5-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="5bef5-132">Umschließen einer benutzerdefinierten Operator Definition mit Leerraum</span><span class="sxs-lookup"><span data-stu-id="5bef5-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="5bef5-133">Verwenden Sie immer Leerraum, um eine Operator Definition zu umschließen:</span><span class="sxs-lookup"><span data-stu-id="5bef5-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="5bef5-134">Für alle benutzerdefinierten Operatoren, die mit `*` beginnen und über mehr als ein Zeichen verfügen, müssen Sie am Anfang der Definition ein Leerzeichen hinzufügen, um eine compilermehrdeutigkeit zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-134">For any custom operator that starts with `*` and that has more than one character, you need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="5bef5-135">Aus diesem Grund wird empfohlen, die Definitionen aller Operatoren einfach mit einem einzelnen Leerzeichen zu umschließen.</span><span class="sxs-lookup"><span data-stu-id="5bef5-135">Because of this, we recommend that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="5bef5-136">Umschließen von Funktionsparameter Pfeilen mit Leerraum</span><span class="sxs-lookup"><span data-stu-id="5bef5-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="5bef5-137">Wenn Sie die Signatur einer Funktion definieren, verwenden Sie Leerraum um das `->` Symbol:</span><span class="sxs-lookup"><span data-stu-id="5bef5-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a><span data-ttu-id="5bef5-138">Umschließen von Funktions Argumenten mit Leerraum</span><span class="sxs-lookup"><span data-stu-id="5bef5-138">Surround function arguments with white space</span></span>

<span data-ttu-id="5bef5-139">Verwenden Sie beim Definieren einer Funktion Leerzeichen um jedes Argument.</span><span class="sxs-lookup"><span data-stu-id="5bef5-139">When defining a function, use white space around each argument.</span></span>

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-very-long-member-definitions"></a><span data-ttu-id="5bef5-140">Parameter für sehr lange Element Definitionen in einer neuen Zeile platzieren</span><span class="sxs-lookup"><span data-stu-id="5bef5-140">Place parameters on a new line for very long member definitions</span></span>

<span data-ttu-id="5bef5-141">Wenn Sie über eine sehr lange Element Definition verfügen, platzieren Sie die Parameter in neuen Zeilen, und fügen Sie Sie in einen Bereich ein.</span><span class="sxs-lookup"><span data-stu-id="5bef5-141">If you have a very long member definition, place the parameters on new lines and indent them one scope.</span></span>

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(
        aVeryLongType: AVeryLongTypeThatYouNeedToUse
        aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
        aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method follows
```

<span data-ttu-id="5bef5-142">Dies gilt auch für Konstruktoren:</span><span class="sxs-lookup"><span data-stu-id="5bef5-142">This also applies to constructors:</span></span>

```fsharp
type C(
    aVeryLongType: AVeryLongTypeThatYouNeedToUse
    aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
    aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

### <a name="type-annotations"></a><span data-ttu-id="5bef5-143">Typanmerkungen</span><span class="sxs-lookup"><span data-stu-id="5bef5-143">Type annotations</span></span>

#### <a name="right-pad-function-argument-type-annotations"></a><span data-ttu-id="5bef5-144">Typanmerkungen für Funktionsargumente des Rechts Auffüll Bereichs</span><span class="sxs-lookup"><span data-stu-id="5bef5-144">Right-pad function argument type annotations</span></span>

<span data-ttu-id="5bef5-145">Wenn Sie Argumente mit Typanmerkungen definieren, verwenden Sie Leerraum nach dem `:`-Symbol:</span><span class="sxs-lookup"><span data-stu-id="5bef5-145">When defining arguments with type annotations, use white space after the `:` symbol:</span></span>

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a><span data-ttu-id="5bef5-146">Umschließende Rückgabetyp Anmerkungen mit Leerraum</span><span class="sxs-lookup"><span data-stu-id="5bef5-146">Surround return type annotations with white space</span></span>

<span data-ttu-id="5bef5-147">Verwenden Sie in einer Let-gebundenen Funktion oder Werttyp Anmerkung (Rückgabetyp im Fall einer Funktion) Leerraum vor und nach dem `:` Symbol:</span><span class="sxs-lookup"><span data-stu-id="5bef5-147">In a let-bound function or value type annotation (return type in the case of a function), use white space before and after the `:` symbol:</span></span>

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="5bef5-148">Formatieren von leeren Zeilen</span><span class="sxs-lookup"><span data-stu-id="5bef5-148">Formatting blank lines</span></span>

* <span data-ttu-id="5bef5-149">Trennen Sie Funktions-und Klassendefinitionen der obersten Ebene mit zwei leeren Zeilen.</span><span class="sxs-lookup"><span data-stu-id="5bef5-149">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="5bef5-150">Methoden Definitionen innerhalb einer Klasse werden durch eine einzelne Leerzeile getrennt.</span><span class="sxs-lookup"><span data-stu-id="5bef5-150">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="5bef5-151">Zusätzliche leere Zeilen können (sparsam) zum Trennen von Gruppen verwandter Funktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-151">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="5bef5-152">Leere Zeilen können zwischen einer Reihe verwandter Einzeiler (z. b. einer Gruppe von Pseudo Implementierungen) weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-152">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="5bef5-153">Verwenden Sie in Funktionen, die in den Funktionen sehr sparsam sind, um logische Abschnitte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5bef5-153">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="5bef5-154">Formatieren von Kommentaren</span><span class="sxs-lookup"><span data-stu-id="5bef5-154">Formatting comments</span></span>

<span data-ttu-id="5bef5-155">Bevorzugen Sie im Allgemeinen mehrere Kommentare mit doppelten Schrägstrichen über Block Kommentare im ml-Stil.</span><span class="sxs-lookup"><span data-stu-id="5bef5-155">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="5bef5-156">Inline Kommentare sollten den ersten Buchstaben ausnutzen.</span><span class="sxs-lookup"><span data-stu-id="5bef5-156">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="5bef5-157">Namenskonventionen</span><span class="sxs-lookup"><span data-stu-id="5bef5-157">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="5bef5-158">Verwenden Sie "CamelCase" für Klassen gebundene, Ausdrucks gebundene und Muster gebundene Werte und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="5bef5-158">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="5bef5-159">Es ist ein gängiges F# und akzeptierter Stil, bei dem für alle Namen, die als lokale Variablen oder in Muster Übereinstimmungen und Funktionsdefinitionen gebunden sind, die Verwendung von</span><span class="sxs-lookup"><span data-stu-id="5bef5-159">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="5bef5-160">Lokal gebundene Funktionen in Klassen sollten auch "CamelCase" verwenden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-160">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="5bef5-161">Verwenden von "CamelCase" für Modul gebundene öffentliche Funktionen</span><span class="sxs-lookup"><span data-stu-id="5bef5-161">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="5bef5-162">Wenn eine Modul gebundene Funktion Teil einer öffentlichen API ist, sollte Sie "CamelCase" verwenden:</span><span class="sxs-lookup"><span data-stu-id="5bef5-162">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="5bef5-163">Verwenden Sie "CamelCase" für interne und private Modul gebundene Werte und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="5bef5-163">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="5bef5-164">Verwenden Sie CamelCase für private Modul gebundene Werte, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="5bef5-164">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="5bef5-165">Ad-hoc-Funktionen in Skripts</span><span class="sxs-lookup"><span data-stu-id="5bef5-165">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="5bef5-166">Werte, die die interne Implementierung eines Moduls oder Typs bilden</span><span class="sxs-lookup"><span data-stu-id="5bef5-166">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="5bef5-167">Verwenden Sie "CamelCase" für Parameter.</span><span class="sxs-lookup"><span data-stu-id="5bef5-167">Use camelCase for parameters</span></span>

<span data-ttu-id="5bef5-168">Alle Parameter sollten in Übereinstimmung mit den .net-Benennungs Konventionen "CamelCase" verwenden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-168">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="5bef5-169">Verwenden von PascalCase für Module</span><span class="sxs-lookup"><span data-stu-id="5bef5-169">Use PascalCase for modules</span></span>

<span data-ttu-id="5bef5-170">Alle Module (Top-Level, Internal, private, netsted) sollten PascalCase verwenden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-170">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="5bef5-171">Verwenden von PascalCase für Typdeklarationen, Elemente und Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="5bef5-171">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="5bef5-172">Klassen, Schnittstellen, Strukturen, Enumerationen, Delegaten, Datensätze und Unterscheidungs-Unions sollten mit PascalCase benannt werden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-172">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="5bef5-173">Member innerhalb von Typen und Bezeichnungen für Datensätze und Unterscheidungs-Unions sollten auch PascalCase verwenden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-173">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

```fsharp
type IMyInterface =
    abstract Something: int

type MyClass() =
    member this.MyMethod(x, y) = x + y

type MyRecord = { IntVal: int; StringVal: string }

type SchoolPerson =
    | Professor
    | Student
    | Advisor
    | Administrator
```

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="5bef5-174">Verwenden von PascalCase für Konstrukte in .net</span><span class="sxs-lookup"><span data-stu-id="5bef5-174">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="5bef5-175">Namespaces, Ausnahmen, Ereignisse und Projekt-/`.dll` Namen sollten ebenfalls PascalCase verwenden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-175">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="5bef5-176">Dies bedeutet nicht nur, dass die Nutzung von anderen .NET-Sprachen für Consumer natürlicher ist, sondern auch mit den .net-Benennungs Konventionen, die wahrscheinlich auftreten.</span><span class="sxs-lookup"><span data-stu-id="5bef5-176">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="5bef5-177">Unterstriche in Namen vermeiden</span><span class="sxs-lookup"><span data-stu-id="5bef5-177">Avoid underscores in names</span></span>

<span data-ttu-id="5bef5-178">In der Vergangenheit F# haben einige Bibliotheken Unterstriche in Namen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5bef5-178">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="5bef5-179">Dies wird jedoch nicht mehr weitgehend akzeptiert, weil es Konflikte mit .net-Benennungs Konventionen verursacht.</span><span class="sxs-lookup"><span data-stu-id="5bef5-179">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="5bef5-180">Dies bedeutet, dass F# einige Programmierer stark Unterstriche verwenden, teilweise aus historischen Gründen, und Toleranz und Respekt ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="5bef5-180">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="5bef5-181">Beachten Sie jedoch, dass der Stil oft von anderen Benutzern nicht gefällt, die entscheiden können, ob diese verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5bef5-181">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="5bef5-182">Einige Ausnahmen umfassen die Interoperabilität mit nativen Komponenten, bei denen Unterstriche sehr häufig vorkommen.</span><span class="sxs-lookup"><span data-stu-id="5bef5-182">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="5bef5-183">Standard F# Operatoren verwenden</span><span class="sxs-lookup"><span data-stu-id="5bef5-183">Use standard F# operators</span></span>

<span data-ttu-id="5bef5-184">Die folgenden Operatoren sind in der F# Standardbibliothek definiert und sollten anstelle der Definition von Entsprechungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-184">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="5bef5-185">Die Verwendung dieser Operatoren wird empfohlen, da Sie dazu führt, dass der Code besser lesbar und idiatisch ist.</span><span class="sxs-lookup"><span data-stu-id="5bef5-185">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="5bef5-186">Entwickler, die einen Hintergrund in ocaml oder einer anderen funktionalen Programmiersprache haben, sind möglicherweise an verschiedene Idiome gewöhnt.</span><span class="sxs-lookup"><span data-stu-id="5bef5-186">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="5bef5-187">In der folgenden Liste sind die F# empfohlenen Operatoren zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="5bef5-187">The following list summarizes the recommended F# operators.</span></span>

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Discard away a value
x + y // Overloaded addition (including string concatenation)
x - y // Overloaded subtraction
x * y // Overloaded multiplication
x / y // Overloaded division
x % y // Overloaded modulus
x && y // Lazy/short-cut "and"
x || y // Lazy/short-cut "or"
x <<< y // Bitwise left shift
x >>> y // Bitwise right shift
x ||| y // Bitwise or, also for working with “flags” enumeration
x &&& y // Bitwise and, also for working with “flags” enumeration
x ^^^ y // Bitwise xor, also for working with “flags” enumeration
```

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="5bef5-188">Verwenden Sie Präfix Syntax für Generika (`Foo<T>`) in bevorzugter postfix Syntax (`T Foo`).</span><span class="sxs-lookup"><span data-stu-id="5bef5-188">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="5bef5-189">F#erbt sowohl den Postfix-ml-Stil der Benennung generischer Typen (z. b. `int list`) als auch das Präfix .NET-Format (z. b. `list<int>`).</span><span class="sxs-lookup"><span data-stu-id="5bef5-189">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="5bef5-190">Bevorzugen Sie den .net-Stil mit Ausnahme von fünf spezifischen Typen:</span><span class="sxs-lookup"><span data-stu-id="5bef5-190">Prefer the .NET style, except for five specific types:</span></span>

1. <span data-ttu-id="5bef5-191">Verwenden F# Sie für Listen das postfix-Formular: `int list` statt `list<int>`.</span><span class="sxs-lookup"><span data-stu-id="5bef5-191">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="5bef5-192">Verwenden F# Sie für Optionen das postfix-Formular: `int option` statt `option<int>`.</span><span class="sxs-lookup"><span data-stu-id="5bef5-192">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="5bef5-193">Verwenden F# Sie für Wert Optionen das postfix-Formular: `int voption` statt `voption<int>`.</span><span class="sxs-lookup"><span data-stu-id="5bef5-193">For F# Value Options, use the postfix form: `int voption` rather than `voption<int>`.</span></span>
4. <span data-ttu-id="5bef5-194">Verwenden F# Sie für Arrays den syntaktischen Namen `int[]` anstatt `int array` oder `array<int>`.</span><span class="sxs-lookup"><span data-stu-id="5bef5-194">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
5. <span data-ttu-id="5bef5-195">Verwenden Sie für Verweis Zellen `int ref` anstelle von `ref<int>` oder `Ref<int>`.</span><span class="sxs-lookup"><span data-stu-id="5bef5-195">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="5bef5-196">Verwenden Sie für alle anderen Typen das Präfix-Formular.</span><span class="sxs-lookup"><span data-stu-id="5bef5-196">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="5bef5-197">Formatierung von Tupeln</span><span class="sxs-lookup"><span data-stu-id="5bef5-197">Formatting tuples</span></span>

<span data-ttu-id="5bef5-198">Eine tupelinstanziierung sollte in Klammern gesetzt werden, und auf die Trennzeichen in sollte ein einzelnes Leerzeichen folgen, z. b. `(1, 2)``(x, y, z)`.</span><span class="sxs-lookup"><span data-stu-id="5bef5-198">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="5bef5-199">Es wird häufig angenommen, Klammern bei der Muster Übereinstimmung von Tupeln auszulassen:</span><span class="sxs-lookup"><span data-stu-id="5bef5-199">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

<span data-ttu-id="5bef5-200">Es wird auch häufig angenommen, Klammern auszulassen, wenn das Tupel der Rückgabewert einer Funktion ist:</span><span class="sxs-lookup"><span data-stu-id="5bef5-200">It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span></span>

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

<span data-ttu-id="5bef5-201">Zusammenfassend gilt, dass Tupel-Instanziierungen in Klammern bevorzugen, aber wenn Sie Tupel für den Musterabgleich oder einen Rückgabewert verwenden, wird es als ausreichend erachtet, Klammern zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-201">In summary, prefer parenthesized tuple instantiations, but when using tuples for pattern matching or a return value, it is considered fine to avoid parentheses.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="5bef5-202">Formatierung diskriminierter Union-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="5bef5-202">Formatting discriminated union declarations</span></span>

<span data-ttu-id="5bef5-203">Einzug `|` in der Typdefinition um 4 Leerzeichen:</span><span class="sxs-lookup"><span data-stu-id="5bef5-203">Indent `|` in type definition by 4 spaces:</span></span>

```fsharp
// OK
type Volume =
    | Liter of float
    | FluidOunce of float
    | ImperialPint of float

// Not OK
type Volume =
| Liter of float
| USPint of float
| ImperialPint of float
```

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="5bef5-204">Formatieren diskriminierter Unions</span><span class="sxs-lookup"><span data-stu-id="5bef5-204">Formatting discriminated unions</span></span>

<span data-ttu-id="5bef5-205">Instanziierte Unterscheidungs-Unions, die auf mehrere Zeilen aufgeteilt werden, sollten enthaltene Daten einen neuen Bereich mit Einzug vermitteln:</span><span class="sxs-lookup"><span data-stu-id="5bef5-205">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="5bef5-206">Die schließende Klammer kann sich auch in einer neuen Zeile befinden:</span><span class="sxs-lookup"><span data-stu-id="5bef5-206">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="5bef5-207">Formatieren von Datensätze</span><span class="sxs-lookup"><span data-stu-id="5bef5-207">Formatting record declarations</span></span>

<span data-ttu-id="5bef5-208">Einzug `{` in der Typdefinition um 4 Leerzeichen, und die Feldliste wird in derselben Zeile gestartet:</span><span class="sxs-lookup"><span data-stu-id="5bef5-208">Indent `{` in type definition by 4 spaces and start the field list on the same line:</span></span>

```fsharp
// OK
type PostalAddress =
    { Address: string
      City: string
      Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Not OK
type PostalAddress =
  { Address: string
    City: string
    Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Unusual in F#
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
```

<span data-ttu-id="5bef5-209">Die Platzierung des öffnenden Tokens in einer neuen Zeile und das schließende Token in einer neuen Zeile ist vorzuziehen, wenn Sie Schnittstellen Implementierungen oder Member im Datensatz deklarieren:</span><span class="sxs-lookup"><span data-stu-id="5bef5-209">Placing the opening token on a new line and the closing token on a new line is preferable if you are declaring interface implementations or members on the record:</span></span>

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    } with
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a><span data-ttu-id="5bef5-210">Datensätze formatieren</span><span class="sxs-lookup"><span data-stu-id="5bef5-210">Formatting records</span></span>

<span data-ttu-id="5bef5-211">Kurze Datensätze können in einer Zeile geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="5bef5-211">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="5bef5-212">Für Datensätze, die länger sind, sollten neue Zeilen für Bezeichnungen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="5bef5-212">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="5bef5-213">Wenn Sie das öffnende Token in einer neuen Zeile platzieren, wird der Inhalt in einem Bereich im Registerkarten Format angezeigt, und das schließende Token in einer neuen Zeile ist vorzuziehen, wenn Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="5bef5-213">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferable if you are:</span></span>

* <span data-ttu-id="5bef5-214">Verschieben von Datensätzen im Code mit unterschiedlichen Einzugs Bereichen</span><span class="sxs-lookup"><span data-stu-id="5bef5-214">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="5bef5-215">Weiterleiten an eine Funktion</span><span class="sxs-lookup"><span data-stu-id="5bef5-215">Piping them into a function</span></span>

```fsharp
let rainbow =
    {
        Boss1 = "Jeffrey"
        Boss2 = "Jeffrey"
        Boss3 = "Jeffrey"
        Boss4 = "Jeffrey"
        Boss5 = "Jeffrey"
        Boss6 = "Jeffrey"
        Boss7 = "Jeffrey"
        Boss8 = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"]
    }

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface

let foo a =
    a
    |> Option.map (fun x ->
        {
            MyField = x
        })
```

<span data-ttu-id="5bef5-216">Die gleichen Regeln gelten für Listen-und Array Elemente.</span><span class="sxs-lookup"><span data-stu-id="5bef5-216">The same rules apply for list and array elements.</span></span>

## <a name="formatting-copy-and-update-record-expressions"></a><span data-ttu-id="5bef5-217">Formatieren von Ausdrücken zum Kopieren und Aktualisieren von Datensätzen</span><span class="sxs-lookup"><span data-stu-id="5bef5-217">Formatting copy-and-update record expressions</span></span>

<span data-ttu-id="5bef5-218">Ein Kopier-und Update Daten Satz Ausdruck ist immer noch ein Datensatz, daher gelten ähnliche Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="5bef5-218">A copy-and-update record expression is still a record, so similar guidelines apply.</span></span>

<span data-ttu-id="5bef5-219">Kurze Ausdrücke können in eine Zeile passen:</span><span class="sxs-lookup"><span data-stu-id="5bef5-219">Short expressions can fit on one line:</span></span>

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

<span data-ttu-id="5bef5-220">Längere Ausdrücke sollten neue Zeilen verwenden:</span><span class="sxs-lookup"><span data-stu-id="5bef5-220">Longer expressions should use new lines:</span></span>

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="5bef5-221">Ebenso wie bei den Daten Satz Anleitungen sollten Sie separate Zeilen für geschweifte Klammern verwenden und einen Bereich mit dem Ausdruck nach rechts einziehen.</span><span class="sxs-lookup"><span data-stu-id="5bef5-221">And as with the record guidance, you may want to dedicate separate lines for the braces and indent one scope to the right with the expression.</span></span> <span data-ttu-id="5bef5-222">Beachten Sie, dass Sie in einigen Sonderfällen, z. b. beim umschließen eines Werts mit einem optionalen ohne Klammern, eine geschweifter Klammer in einer Zeile aufbewahren müssen:</span><span class="sxs-lookup"><span data-stu-id="5bef5-222">Note that in some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:</span></span>

```fsharp
type S = { F1: int; F2: string }
type State = { F:  S option }

let state = { F = Some { F1 = 1; F2 = "Hello" } }
let newState =
    {
        state with
            F = Some {
                    F1 = 0
                    F2 = ""
                }
    }
```

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="5bef5-223">Formatieren von Listen und Arrays</span><span class="sxs-lookup"><span data-stu-id="5bef5-223">Formatting lists and arrays</span></span>

<span data-ttu-id="5bef5-224">Schreiben Sie `x :: l` mit Leerzeichen um den `::` Operator (`::` ist ein Infix-Operator, der daher von Leerzeichen umgeben ist).</span><span class="sxs-lookup"><span data-stu-id="5bef5-224">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="5bef5-225">Listen und Arrays, die in einer einzelnen Zeile deklariert werden, müssen nach der öffnenden eckige Klammer und vor der schließenden Klammer ein Leerzeichen enthalten:</span><span class="sxs-lookup"><span data-stu-id="5bef5-225">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="5bef5-226">Verwenden Sie immer mindestens ein Leerzeichen zwischen zwei unterschiedlichen geschweifter Klammern ähnlichen Operatoren.</span><span class="sxs-lookup"><span data-stu-id="5bef5-226">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="5bef5-227">Belassen Sie z. b. ein Leerzeichen zwischen einem `[` und einem `{`.</span><span class="sxs-lookup"><span data-stu-id="5bef5-227">For example, leave a space between a `[` and a `{`.</span></span>

```fsharp
// OK
[ { IngredientName = "Green beans"; Quantity = 250 }
  { IngredientName = "Pine nuts"; Quantity = 250 }
  { IngredientName = "Feta cheese"; Quantity = 250 }
  { IngredientName = "Olive oil"; Quantity = 10 }
  { IngredientName = "Lemon"; Quantity = 1 } ]

// Not OK
[{ IngredientName = "Green beans"; Quantity = 250 }
 { IngredientName = "Pine nuts"; Quantity = 250 }
 { IngredientName = "Feta cheese"; Quantity = 250 }
 { IngredientName = "Olive oil"; Quantity = 10 }
 { IngredientName = "Lemon"; Quantity = 1 }]
```

<span data-ttu-id="5bef5-228">Die gleiche Richtlinie gilt für Listen oder Arrays von Tupeln.</span><span class="sxs-lookup"><span data-stu-id="5bef5-228">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="5bef5-229">Listen und Arrays, die auf mehrere Zeilen aufgeteilt werden, folgen einer ähnlichen Regel wie Datensätze:</span><span class="sxs-lookup"><span data-stu-id="5bef5-229">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

```fsharp
let pascalsTriangle =
    [|
        [| 1 |]
        [| 1; 1 |]
        [| 1; 2; 1 |]
        [| 1; 3; 3; 1 |]
        [| 1; 4; 6; 4; 1 |]
        [| 1; 5; 10; 10; 5; 1 |]
        [| 1; 6; 15; 20; 15; 6; 1 |]
        [| 1; 7; 21; 35; 35; 21; 7; 1 |]
        [| 1; 8; 28; 56; 70; 56; 28; 8; 1 |]
    |]
```

<span data-ttu-id="5bef5-230">Ebenso wie bei Datensätzen wird durch das Deklarieren der öffnenden und schließenden Klammern in der eigenen Zeile das Verschieben von Code und das Weiterleiten in Funktionen vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="5bef5-230">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

<span data-ttu-id="5bef5-231">Beim programmgesteuerten Generieren von Arrays und Listen sollten Sie `->` über `do ... yield` bevorzugen, wenn immer ein Wert generiert wird:</span><span class="sxs-lookup"><span data-stu-id="5bef5-231">When generating arrays and lists programmatically, prefer `->` over `do ... yield` when a value is always generated:</span></span>

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x*x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x*x ]
```

<span data-ttu-id="5bef5-232">Ältere Versionen der Sprache F# erforderten die Angabe von `yield` in Situationen, in denen Daten bedingt generiert werden können, oder es können aufeinander folgende Ausdrücke ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-232">Older versions of the F# language required specifying `yield` in situations where data may be generated conditionally, or there may be consecutive expressions to be evaluated.</span></span> <span data-ttu-id="5bef5-233">Sie sollten diese `yield` Schlüsselwörter weglassen, es sei denn F# , Sie müssen mit einer älteren Sprachversion kompilieren:</span><span class="sxs-lookup"><span data-stu-id="5bef5-233">Prefer omitting these `yield` keywords unless you must compile with an older F# language version:</span></span>

```fsharp
// Preferred
let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]

// Not preferred
let daysOfWeek' includeWeekend =
    [
        yield "Monday"
        yield "Tuesday"
        yield "Wednesday"
        yield "Thursday"
        yield "Friday"
        if includeWeekend then
            yield "Saturday"
            yield "Sunday"
    ]
```

<span data-ttu-id="5bef5-234">In einigen Fällen können `do...yield` zur besseren Lesbarkeit beitragen.</span><span class="sxs-lookup"><span data-stu-id="5bef5-234">In some cases, `do...yield` may aid in readability.</span></span> <span data-ttu-id="5bef5-235">Diese Fälle, aber subjektiv, sollten berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-235">These cases, though subjective, should be taken into consideration.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="5bef5-236">Formatieren von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="5bef5-236">Formatting if expressions</span></span>

<span data-ttu-id="5bef5-237">Der Einzug von Bedingungen hängt von den Größen der Ausdrücke ab, die Sie bilden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-237">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="5bef5-238">Wenn `cond`, `e1` und `e2` kurz sind, schreiben Sie Sie einfach in einer Zeile:</span><span class="sxs-lookup"><span data-stu-id="5bef5-238">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="5bef5-239">Wenn `cond`, `e1` oder `e2` länger, aber nicht mehrzeilige Zeilen:</span><span class="sxs-lookup"><span data-stu-id="5bef5-239">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="5bef5-240">Wenn einer der Ausdrücke mehrzeilige Ausdrücke ist:</span><span class="sxs-lookup"><span data-stu-id="5bef5-240">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="5bef5-241">Mehrere Bedingungen mit `elif` und `else` werden im gleichen Bereich wie die `if`eingezogen:</span><span class="sxs-lookup"><span data-stu-id="5bef5-241">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="5bef5-242">Musterabgleichkonstrukte</span><span class="sxs-lookup"><span data-stu-id="5bef5-242">Pattern matching constructs</span></span>

<span data-ttu-id="5bef5-243">Verwenden Sie eine `|` für jede Klausel einer Entsprechung ohne Einzug.</span><span class="sxs-lookup"><span data-stu-id="5bef5-243">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="5bef5-244">Wenn der Ausdruck kurz ist, können Sie die Verwendung einer einzelnen Zeile in Erwägung gezogen, wenn jeder Teil Ausdruck ebenfalls einfach ist.</span><span class="sxs-lookup"><span data-stu-id="5bef5-244">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> x
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> x
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

<span data-ttu-id="5bef5-245">Wenn der Ausdruck auf der rechten Seite des Musters für den Musterabgleich zu groß ist, verschieben Sie ihn in die folgende Zeile, wobei Sie einen Schritt aus der `match`/`|`eingezogen haben.</span><span class="sxs-lookup"><span data-stu-id="5bef5-245">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="5bef5-246">Der Musterabgleich von anonymen Funktionen, beginnend mit `function`, sollte in der Regel nicht zu weit einziehen.</span><span class="sxs-lookup"><span data-stu-id="5bef5-246">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="5bef5-247">Beispielsweise ist es in Ordnung, einen Bereich wie folgt einzuschließen:</span><span class="sxs-lookup"><span data-stu-id="5bef5-247">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="5bef5-248">Der Musterabgleich in Funktionen, die durch `let` oder `let rec` definiert werden, sollte 4 Leerzeichen nach dem Start von `let`eingerückt werden, auch wenn `function` Schlüsselwort verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="5bef5-248">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="5bef5-249">Es wird nicht empfohlen, Pfeile auszurichten.</span><span class="sxs-lookup"><span data-stu-id="5bef5-249">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="5bef5-250">Formatieren von try/with-Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="5bef5-250">Formatting try/with expressions</span></span>

<span data-ttu-id="5bef5-251">Der Musterabgleich für den Ausnahmetyp sollte auf der gleichen Ebene wie `with`eingezogen werden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-251">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

```fsharp
try
    if System.DateTime.Now.Second % 3 = 0 then
        raise (new System.Exception())
    else
        raise (new System.ApplicationException())
with
| :? System.ApplicationException ->
    printfn "A second that was not a multiple of 3"
| _ ->
    printfn "A second that was a multiple of 3"
```

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="5bef5-252">Formatieren der Funktionsparameter Anwendung</span><span class="sxs-lookup"><span data-stu-id="5bef5-252">Formatting function parameter application</span></span>

<span data-ttu-id="5bef5-253">Im Allgemeinen werden die meisten Funktionsparameter Anwendungen in derselben Zeile ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5bef5-253">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="5bef5-254">Wenn Sie Parameter auf eine Funktion in einer neuen Zeile anwenden möchten, müssen Sie Sie um einen Bereich einziehen.</span><span class="sxs-lookup"><span data-stu-id="5bef5-254">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

```fsharp
// OK
sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
sprintf
     "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
let printVolumes x =
    printf "Volume in liters = %f, in us pints = %f, in imperial = %f"
        (convertVolumeToLiter x)
        (convertVolumeUSPint x)
        (convertVolumeImperialPint x)
```

<span data-ttu-id="5bef5-255">Die gleichen Richtlinien gelten auch für Lambda-Ausdrücke als Funktionsargumente.</span><span class="sxs-lookup"><span data-stu-id="5bef5-255">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="5bef5-256">Wenn der Text eines Lambda Ausdrucks ist, kann der Text eine andere Zeile enthalten, die von einem Bereich eingezogen wird.</span><span class="sxs-lookup"><span data-stu-id="5bef5-256">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

```fsharp
let printListWithOffset a list1 =
    List.iter
        (fun elem -> printfn "%d" (a + elem))
        list1

// OK if lambda body is long enough
let printListWithOffset a list1 =
    List.iter
        (fun elem ->
            printfn "%d" (a + elem))
        list1
```

<span data-ttu-id="5bef5-257">Wenn der Text eines Lambda-Ausdrucks jedoch mehr als eine Zeile ist, sollten Sie ihn in eine separate Funktion einbeziehen, anstatt ein mehr zeitiges Konstrukt als einzelnes Argument für eine Funktion anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-257">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="5bef5-258">Formatieren von Infixoperatoren</span><span class="sxs-lookup"><span data-stu-id="5bef5-258">Formatting infix operators</span></span>

<span data-ttu-id="5bef5-259">Getrennte Operatoren nach Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="5bef5-259">Separate operators by spaces.</span></span> <span data-ttu-id="5bef5-260">Offensichtliche Ausnahmen für diese Regel sind die `!`-und `.`-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="5bef5-260">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="5bef5-261">Infix-Ausdrücke sind in der gleichen Spalte zu finden:</span><span class="sxs-lookup"><span data-stu-id="5bef5-261">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="5bef5-262">Formatierungs Pipeline Operatoren</span><span class="sxs-lookup"><span data-stu-id="5bef5-262">Formatting pipeline operators</span></span>

<span data-ttu-id="5bef5-263">Pipeline `|>`-Operatoren sollten unterhalb der Ausdrücke liegen, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-263">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

```fsharp
// Preferred approach
let methods2 =
    System.AppDomain.CurrentDomain.GetAssemblies()
    |> List.ofArray
    |> List.map (fun assm -> assm.GetTypes())
    |> Array.concat
    |> List.ofArray
    |> List.map (fun t -> t.GetMethods())
    |> Array.concat

// Not OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
            |> List.ofArray
            |> List.map (fun assm -> assm.GetTypes())
            |> Array.concat
            |> List.ofArray
            |> List.map (fun t -> t.GetMethods())
            |> Array.concat
```

### <a name="formatting-modules"></a><span data-ttu-id="5bef5-264">Formatieren von Modulen</span><span class="sxs-lookup"><span data-stu-id="5bef5-264">Formatting modules</span></span>

<span data-ttu-id="5bef5-265">Der Code in einem lokalen Modul muss relativ zum Modul eingezogen werden, aber der Code in einem Modul der obersten Ebene sollte nicht eingezogen werden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-265">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="5bef5-266">Namespace Elemente müssen nicht eingezogen werden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-266">Namespace elements do not have to be indented.</span></span>

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a*a + b*b

module A2 =
    let function2 a b = a*a - b*b
```

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="5bef5-267">Formatieren von Objekt Ausdrücken und Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5bef5-267">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="5bef5-268">Objekt Ausdrücke und Schnittstellen sollten auf die gleiche Weise ausgerichtet werden, wenn `member` nach 4 Leerzeichen eingezogen werden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-268">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="5bef5-269">Formatieren von Leerzeichen in Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="5bef5-269">Formatting white space in expressions</span></span>

<span data-ttu-id="5bef5-270">Vermeiden Sie überflüssige Leerzeichen in F# Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="5bef5-270">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="5bef5-271">Benannte Argumente sollten auch keinen Leerraum für die `=`aufweisen:</span><span class="sxs-lookup"><span data-stu-id="5bef5-271">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a><span data-ttu-id="5bef5-272">Formatieren von Attributen</span><span class="sxs-lookup"><span data-stu-id="5bef5-272">Formatting attributes</span></span>

<span data-ttu-id="5bef5-273">[Attribute](../language-reference/attributes.md) werden über einem Konstrukt platziert:</span><span class="sxs-lookup"><span data-stu-id="5bef5-273">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

```fsharp
[<SomeAttribute>]
type MyClass() = ...

[<RequireQualifiedAccess>]
module M =
    let f x = x

[<Struct>]
type MyRecord =
    { Label1: int
      Label2: string }
```

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="5bef5-274">Formatieren von Attributen für Parameter</span><span class="sxs-lookup"><span data-stu-id="5bef5-274">Formatting attributes on parameters</span></span>

<span data-ttu-id="5bef5-275">Attribute können auch stellen für Parameter sein.</span><span class="sxs-lookup"><span data-stu-id="5bef5-275">Attributes can also be places on parameters.</span></span> <span data-ttu-id="5bef5-276">Platzieren Sie in diesem Fall die Zeile in derselben Zeile wie der-Parameter und vor dem Namen:</span><span class="sxs-lookup"><span data-stu-id="5bef5-276">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="5bef5-277">Formatieren mehrerer Attribute</span><span class="sxs-lookup"><span data-stu-id="5bef5-277">Formatting multiple attributes</span></span>

<span data-ttu-id="5bef5-278">Wenn mehrere Attribute auf ein Konstrukt angewendet werden, bei dem es sich nicht um einen Parameter handelt, sollten Sie so platziert werden, dass ein Attribut pro Zeile vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="5bef5-278">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="5bef5-279">Wenn Sie auf einen Parameter angewendet werden, müssen Sie sich in derselben Zeile befinden und durch ein `;` Trennzeichen getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="5bef5-279">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="5bef5-280">Formatieren von literalen</span><span class="sxs-lookup"><span data-stu-id="5bef5-280">Formatting literals</span></span>

<span data-ttu-id="5bef5-281">Literale, die das `Literal`-Attribut verwenden, sollten das Attribut in einer eigenen Zeile platzieren und die Verwendung von PascalCase verwenden: [ F# ](../language-reference/literals.md)</span><span class="sxs-lookup"><span data-stu-id="5bef5-281">[F# literals](../language-reference/literals.md) using the `Literal` attribute should place the attribute on its own line and use PascalCase naming:</span></span>

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="5bef5-282">Vermeiden Sie das Platzieren des Attributs in derselben Zeile wie den Wert.</span><span class="sxs-lookup"><span data-stu-id="5bef5-282">Avoid placing the attribute on the same line as the value.</span></span>
