---
title: Richtlinien für das Formatieren von F#-Code
description: Erfahren Sie mehr über Richtlinien zum Formatieren von F-Code.
ms.date: 11/04/2019
ms.openlocfilehash: 2086b515b8ec9b69a44e2e65ca06fb320670dff2
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2020
ms.locfileid: "81278937"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="a9084-103">Richtlinien für das Formatieren von F#-Code</span><span class="sxs-lookup"><span data-stu-id="a9084-103">F# code formatting guidelines</span></span>

<span data-ttu-id="a9084-104">Dieser Artikel enthält Richtlinien zum Formatieren des Codes, sodass der F-Code:</span><span class="sxs-lookup"><span data-stu-id="a9084-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="a9084-105">Allgemein als lesbarer angesehen</span><span class="sxs-lookup"><span data-stu-id="a9084-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="a9084-106">Entspricht den Konventionen, die von Formatierungstools in Visual Studio und anderen Editoren angewendet werden</span><span class="sxs-lookup"><span data-stu-id="a9084-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="a9084-107">Ähnlich wie bei anderen Online-Code</span><span class="sxs-lookup"><span data-stu-id="a9084-107">Similar to other code online</span></span>

<span data-ttu-id="a9084-108">Diese Richtlinien basieren auf [einem umfassenden Leitfaden zu den Richtlinien](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) von [Anh-Dung Phan](https://github.com/dungpa).</span><span class="sxs-lookup"><span data-stu-id="a9084-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="a9084-109">Allgemeine Regeln für den Einzug</span><span class="sxs-lookup"><span data-stu-id="a9084-109">General rules for indentation</span></span>

<span data-ttu-id="a9084-110">Standardmäßig wird ein erheblicher Leerraum verwendet.</span><span class="sxs-lookup"><span data-stu-id="a9084-110">F# uses significant white space by default.</span></span> <span data-ttu-id="a9084-111">Die folgenden Richtlinien sollen Anleitungen geben, wie man mit einigen Herausforderungen jonglieren kann, die dies mit sich bringen kann.</span><span class="sxs-lookup"><span data-stu-id="a9084-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="a9084-112">Verwenden von Räumen</span><span class="sxs-lookup"><span data-stu-id="a9084-112">Using spaces</span></span>

<span data-ttu-id="a9084-113">Wenn einEinzug erforderlich ist, müssen Sie Leerzeichen und keine Registerkarten verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9084-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="a9084-114">Mindestens ein Leerzeichen ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a9084-114">At least one space is required.</span></span> <span data-ttu-id="a9084-115">Ihre Organisation kann Codierungsstandards erstellen, um die Anzahl der Leerzeichen anzugeben, die für den Einzug verwendet werden sollen. zwei, drei oder vier Einrückungsräume auf jeder Ebene, auf der der Einzug stattfindet, sind typisch.</span><span class="sxs-lookup"><span data-stu-id="a9084-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="a9084-116">**Wir empfehlen 4 Leerzeichen pro Einzug.**</span><span class="sxs-lookup"><span data-stu-id="a9084-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="a9084-117">Das heißt, die Einrückung von Programmen ist eine subjektive Angelegenheit.</span><span class="sxs-lookup"><span data-stu-id="a9084-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="a9084-118">Variationen sind in Ordnung, aber die erste Regel, der Sie folgen sollten, ist *die Konsistenz der Einrückung*.</span><span class="sxs-lookup"><span data-stu-id="a9084-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="a9084-119">Wählen Sie einen allgemein akzeptierten Einzugsstil und verwenden Sie ihn systematisch in der gesamten Codebasis.</span><span class="sxs-lookup"><span data-stu-id="a9084-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="a9084-120">Formatieren von Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="a9084-120">Formatting white space</span></span>

<span data-ttu-id="a9084-121">Der Leerraum ist leer.</span><span class="sxs-lookup"><span data-stu-id="a9084-121">F# is white space sensitive.</span></span> <span data-ttu-id="a9084-122">Obwohl die meisten Semantik aus dem weißen Raum durch richtige Einzug abgedeckt sind, gibt es einige andere Dinge zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="a9084-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="a9084-123">Formatieren von Operatoren in arithmetischen Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="a9084-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="a9084-124">Verwenden Sie immer Leerraum um binäre arithmetische Ausdrücke:</span><span class="sxs-lookup"><span data-stu-id="a9084-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="a9084-125">Unäre `-` Operatoren sollten immer den Wert haben, den sie negieren, sofort folgen:</span><span class="sxs-lookup"><span data-stu-id="a9084-125">Unary `-` operators should always have the value they are negating immediately follow:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="a9084-126">Das Hinzufügen eines Leerzeichens nach dem `-` Operator kann zu Verwechslungen für andere führen.</span><span class="sxs-lookup"><span data-stu-id="a9084-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="a9084-127">Zusammenfassend ist es wichtig, immer:</span><span class="sxs-lookup"><span data-stu-id="a9084-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="a9084-128">Umgeben von binären Operatoren mit Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="a9084-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="a9084-129">Niemals nach einem unären Operator nachgelassenen Leerraum haben</span><span class="sxs-lookup"><span data-stu-id="a9084-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="a9084-130">Die binäre arithmetische Operator-Richtlinie ist besonders wichtig.</span><span class="sxs-lookup"><span data-stu-id="a9084-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="a9084-131">Wenn ein binärer `-` Operator nicht mit bestimmten Formatierungsoptionen verbunden ist, `-`kann dies dazu führen, dass er als unär interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="a9084-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="a9084-132">Umgeben einer benutzerdefinierten Operatordefinition mit Leerraum</span><span class="sxs-lookup"><span data-stu-id="a9084-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="a9084-133">Verwenden Sie immer Leerraum, um eine Operatordefinition zu umgeben:</span><span class="sxs-lookup"><span data-stu-id="a9084-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="a9084-134">Für jeden benutzerdefinierten `*` Operator, der mit mehr als einem Zeichen beginnt und mehr als ein Zeichen enthält, müssen Sie am Anfang der Definition ein Leerzeichen hinzufügen, um eine Compilermehrdeutigkeit zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="a9084-134">For any custom operator that starts with `*` and that has more than one character, you need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="a9084-135">Aus diesem Grund empfehlen wir, dass Sie einfach die Definitionen aller Operatoren mit einem einzelnen Leerzeichen umgeben.</span><span class="sxs-lookup"><span data-stu-id="a9084-135">Because of this, we recommend that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="a9084-136">Surround-Funktionsparameterpfeile mit Leerraum</span><span class="sxs-lookup"><span data-stu-id="a9084-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="a9084-137">Verwenden Sie beim Definieren der Signatur einer `->` Funktion Leerzeichen um das Symbol:</span><span class="sxs-lookup"><span data-stu-id="a9084-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a><span data-ttu-id="a9084-138">Surround-Funktionsargumente mit Leerraum</span><span class="sxs-lookup"><span data-stu-id="a9084-138">Surround function arguments with white space</span></span>

<span data-ttu-id="a9084-139">Verwenden Sie beim Definieren einer Funktion Leerraum um jedes Argument.</span><span class="sxs-lookup"><span data-stu-id="a9084-139">When defining a function, use white space around each argument.</span></span>

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-very-long-member-definitions"></a><span data-ttu-id="a9084-140">Platzieren von Parametern in einer neuen Zeile für sehr lange Elementdefinitionen</span><span class="sxs-lookup"><span data-stu-id="a9084-140">Place parameters on a new line for very long member definitions</span></span>

<span data-ttu-id="a9084-141">Wenn Sie über eine sehr lange Elementdefinition verfügen, platzieren Sie die Parameter in neuen Zeilen, und ziehen Sie sie in einen Bereich ein.</span><span class="sxs-lookup"><span data-stu-id="a9084-141">If you have a very long member definition, place the parameters on new lines and indent them one scope.</span></span>

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(
        aVeryLongType: AVeryLongTypeThatYouNeedToUse
        aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
        aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method follows
```

<span data-ttu-id="a9084-142">Dies gilt auch für Konstruktoren:</span><span class="sxs-lookup"><span data-stu-id="a9084-142">This also applies to constructors:</span></span>

```fsharp
type C(
    aVeryLongType: AVeryLongTypeThatYouNeedToUse
    aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
    aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

### <a name="type-annotations"></a><span data-ttu-id="a9084-143">Typanmerkungen</span><span class="sxs-lookup"><span data-stu-id="a9084-143">Type annotations</span></span>

#### <a name="right-pad-function-argument-type-annotations"></a><span data-ttu-id="a9084-144">Rechts-Pad-Funktionsargumenttyp-Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="a9084-144">Right-pad function argument type annotations</span></span>

<span data-ttu-id="a9084-145">Verwenden Sie beim Definieren von Argumenten mit `:` Typanmerkungen Leerzeichen nach dem Symbol:</span><span class="sxs-lookup"><span data-stu-id="a9084-145">When defining arguments with type annotations, use white space after the `:` symbol:</span></span>

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a><span data-ttu-id="a9084-146">Surround-Rückgabetyp-Anmerkungen mit Leerraum</span><span class="sxs-lookup"><span data-stu-id="a9084-146">Surround return type annotations with white space</span></span>

<span data-ttu-id="a9084-147">Verwenden Sie in einer let-bound-Funktion oder Werttypanmerkung (Rückgabetyp im Fall `:` einer Funktion) Leerzeichen vor und nach dem Symbol:</span><span class="sxs-lookup"><span data-stu-id="a9084-147">In a let-bound function or value type annotation (return type in the case of a function), use white space before and after the `:` symbol:</span></span>

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="a9084-148">Formatieren leerer Zeilen</span><span class="sxs-lookup"><span data-stu-id="a9084-148">Formatting blank lines</span></span>

* <span data-ttu-id="a9084-149">Trennen Sie Funktions- und Klassendefinitionen der obersten Ebene mit zwei leeren Zeilen.</span><span class="sxs-lookup"><span data-stu-id="a9084-149">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="a9084-150">Methodendefinitionen innerhalb einer Klasse werden durch eine einzelne leere Zeile getrennt.</span><span class="sxs-lookup"><span data-stu-id="a9084-150">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="a9084-151">Zusätzliche leere Zeilen können (sparsam) verwendet werden, um Gruppen verwandter Funktionen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="a9084-151">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="a9084-152">Leere Linien können zwischen einer Reihe verwandter Einzeiler weggelassen werden (z. B. eine Reihe von Dummy-Implementierungen).</span><span class="sxs-lookup"><span data-stu-id="a9084-152">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="a9084-153">Verwenden Sie leere Zeilen in Funktionen sparsam, um logische Abschnitte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a9084-153">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="a9084-154">Formatieren von Kommentaren</span><span class="sxs-lookup"><span data-stu-id="a9084-154">Formatting comments</span></span>

<span data-ttu-id="a9084-155">Im Allgemeinen bevorzugen Sie mehrere Doppelschrägstrich-Kommentare gegenüber Blockkommentaren im ML-Stil.</span><span class="sxs-lookup"><span data-stu-id="a9084-155">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="a9084-156">Inlinekommentare sollten den ersten Buchstaben großschreiben.</span><span class="sxs-lookup"><span data-stu-id="a9084-156">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="a9084-157">Namenskonventionen</span><span class="sxs-lookup"><span data-stu-id="a9084-157">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="a9084-158">Verwenden von camelCase für klassengebundene, ausdrucks- und mustergebundene Werte und Funktionen</span><span class="sxs-lookup"><span data-stu-id="a9084-158">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="a9084-159">Es ist üblich und akzeptiert Erdstil, camelCase für alle Namen zu verwenden, die als lokale Variablen oder in Musterübereinstimmungen und Funktionsdefinitionen gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="a9084-159">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="a9084-160">Lokal gebundene Funktionen in Klassen sollten auch camelCase verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9084-160">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="a9084-161">Verwenden von camelCase für modulgebundene öffentliche Funktionen</span><span class="sxs-lookup"><span data-stu-id="a9084-161">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="a9084-162">Wenn eine modulgebundene Funktion Teil einer öffentlichen API ist, sollte sie camelCase verwenden:</span><span class="sxs-lookup"><span data-stu-id="a9084-162">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="a9084-163">Verwenden von camelCase für interne und private modulgebundene Werte und Funktionen</span><span class="sxs-lookup"><span data-stu-id="a9084-163">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="a9084-164">Verwenden Sie camelCase für private Modul-gebundene Werte, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="a9084-164">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="a9084-165">Ad-hoc-Funktionen in Skripten</span><span class="sxs-lookup"><span data-stu-id="a9084-165">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="a9084-166">Werte, aus der die interne Implementierung eines Moduls oder Typs besteht</span><span class="sxs-lookup"><span data-stu-id="a9084-166">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="a9084-167">CamelCase für Parameter verwenden</span><span class="sxs-lookup"><span data-stu-id="a9084-167">Use camelCase for parameters</span></span>

<span data-ttu-id="a9084-168">Alle Parameter sollten camelCase gemäß .NET-Namenskonventionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9084-168">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="a9084-169">PascalCase für Module verwenden</span><span class="sxs-lookup"><span data-stu-id="a9084-169">Use PascalCase for modules</span></span>

<span data-ttu-id="a9084-170">Alle Module (top-level, internal, private, nested) sollten PascalCase verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9084-170">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="a9084-171">PascalCase für Typdeklarationen, Member und Beschriftungen verwenden</span><span class="sxs-lookup"><span data-stu-id="a9084-171">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="a9084-172">Klassen, Schnittstellen, Strukturen, Enumerationen, Delegaten, Datensätze und diskriminierte Unions sollten alle mit PascalCase benannt werden.</span><span class="sxs-lookup"><span data-stu-id="a9084-172">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="a9084-173">Member innerhalb von Typen und Bezeichnungen für Datensätze und diskriminierte Gewerkschaften sollten auch PascalCase verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9084-173">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="a9084-174">PascalCase für Konstrukte verwenden, die .NET intrinsisch sind</span><span class="sxs-lookup"><span data-stu-id="a9084-174">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="a9084-175">Namespaces, Ausnahmen, Ereignisse und`.dll` Projektnamen sollten auch PascalCase verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9084-175">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="a9084-176">Dadurch fühlt sich der Verbrauch aus anderen .NET-Sprachen für Verbraucher nicht nur natürlicher an, sondern steht auch im Einklang mit .NET-Namenskonventionen, auf die Sie wahrscheinlich stoßen werden.</span><span class="sxs-lookup"><span data-stu-id="a9084-176">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="a9084-177">Unterstriche in Namen vermeiden</span><span class="sxs-lookup"><span data-stu-id="a9084-177">Avoid underscores in names</span></span>

<span data-ttu-id="a9084-178">In der Vergangenheit haben einige F-Bibliotheken Unterstriche in Namen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a9084-178">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="a9084-179">Dies wird jedoch nicht mehr allgemein akzeptiert, auch weil es mit .NET-Namenskonventionen kollidiert.</span><span class="sxs-lookup"><span data-stu-id="a9084-179">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="a9084-180">Das heißt, einige F-Programmierer verwenden unterstrichen stark, teilweise aus historischen Gründen, und Toleranz und Respekt ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="a9084-180">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="a9084-181">Beachten Sie jedoch, dass der Stil von anderen, die eine Wahl haben, ob sie ihn verwenden möchten, oft nicht gemocht wird.</span><span class="sxs-lookup"><span data-stu-id="a9084-181">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="a9084-182">Einige Ausnahmen umfassen die Zusammenarbeit mit systemeigenen Komponenten, bei denen Unterstriche sehr häufig auftreten.</span><span class="sxs-lookup"><span data-stu-id="a9084-182">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="a9084-183">Verwenden von Standard-Operatoren für Die Verwendung von F-Operatoren</span><span class="sxs-lookup"><span data-stu-id="a9084-183">Use standard F# operators</span></span>

<span data-ttu-id="a9084-184">Die folgenden Operatoren sind in der F-Standardbibliothek definiert und sollten verwendet werden, anstatt Äquivalente zu definieren.</span><span class="sxs-lookup"><span data-stu-id="a9084-184">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="a9084-185">Die Verwendung dieser Operatoren wird empfohlen, da Code tendenziell lesbarer und idiomatischer wird.</span><span class="sxs-lookup"><span data-stu-id="a9084-185">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="a9084-186">Entwickler mit einem Hintergrund in OCaml oder einer anderen funktionalen Programmiersprache können an verschiedene Idiome gewöhnt sein.</span><span class="sxs-lookup"><span data-stu-id="a9084-186">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="a9084-187">In der folgenden Liste werden die empfohlenen F-Operatoren zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="a9084-187">The following list summarizes the recommended F# operators.</span></span>

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="a9084-188">Präfixsyntax für Generika`Foo<T>`verwenden ( ) vorgeben der Postfixsyntax (`T Foo`)</span><span class="sxs-lookup"><span data-stu-id="a9084-188">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="a9084-189">F- erbt sowohl den postfix-ML-Stil des `int list`Namens generischer Typen (z. B. `list<int>`) als auch das Präfix .NET-Stil (z. B. ).</span><span class="sxs-lookup"><span data-stu-id="a9084-189">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="a9084-190">Bevorzugen Sie den .NET-Stil, mit Ausnahme von fünf bestimmten Typen:</span><span class="sxs-lookup"><span data-stu-id="a9084-190">Prefer the .NET style, except for five specific types:</span></span>

1. <span data-ttu-id="a9084-191">Verwenden Sie für F-Listen das `int list` postfix-Formular: anstelle von `list<int>`.</span><span class="sxs-lookup"><span data-stu-id="a9084-191">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="a9084-192">Verwenden Sie für Die Optionen das `int option` postfix-Formular: anstelle von `option<int>`.</span><span class="sxs-lookup"><span data-stu-id="a9084-192">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="a9084-193">Verwenden Sie für die Wertoptionen von `int voption` F- Wert das postfix-Formular: anstelle von `voption<int>`.</span><span class="sxs-lookup"><span data-stu-id="a9084-193">For F# Value Options, use the postfix form: `int voption` rather than `voption<int>`.</span></span>
4. <span data-ttu-id="a9084-194">Verwenden Sie für Die Arrays `int[]` den `int array` syntaktischen Namen anstelle von oder `array<int>`.</span><span class="sxs-lookup"><span data-stu-id="a9084-194">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
5. <span data-ttu-id="a9084-195">Verwenden Sie `int ref` für Referenzzellen anstelle von `ref<int>` oder `Ref<int>`.</span><span class="sxs-lookup"><span data-stu-id="a9084-195">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="a9084-196">Verwenden Sie für alle anderen Typen das Präfixformular.</span><span class="sxs-lookup"><span data-stu-id="a9084-196">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="a9084-197">Formatieren von Tupeln</span><span class="sxs-lookup"><span data-stu-id="a9084-197">Formatting tuples</span></span>

<span data-ttu-id="a9084-198">Eine Tupelinstanziierung sollte in Klammern sein, und auf die begrenzenden Kommas innerhalb `(1, 2)` `(x, y, z)`sollte ein einzelnes Leerzeichen folgen, z. B.: .</span><span class="sxs-lookup"><span data-stu-id="a9084-198">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="a9084-199">Es ist allgemein akzeptiert, Klammern in Muster-Matching von Tupeln wegzulassen:</span><span class="sxs-lookup"><span data-stu-id="a9084-199">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

<span data-ttu-id="a9084-200">Es ist auch allgemein akzeptiert, Klammern wegzulassen, wenn das Tupel der Rückgabewert einer Funktion ist:</span><span class="sxs-lookup"><span data-stu-id="a9084-200">It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span></span>

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

<span data-ttu-id="a9084-201">Zusammenfassend ist, dass die Parenthesized Tupelinstanziationen bevorzugt werden, aber wenn Sie Tupel für Musterabgleich oder einen Rückgabewert verwenden, gilt es als fein, Klammern zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="a9084-201">In summary, prefer parenthesized tuple instantiations, but when using tuples for pattern matching or a return value, it is considered fine to avoid parentheses.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="a9084-202">Formatieren diskriminierter Gewerkschaftserklärungen</span><span class="sxs-lookup"><span data-stu-id="a9084-202">Formatting discriminated union declarations</span></span>

<span data-ttu-id="a9084-203">Einzug `|` in Typdefinition durch 4 Leerzeichen:</span><span class="sxs-lookup"><span data-stu-id="a9084-203">Indent `|` in type definition by 4 spaces:</span></span>

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

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="a9084-204">Formatieren diskriminierter Gewerkschaften</span><span class="sxs-lookup"><span data-stu-id="a9084-204">Formatting discriminated unions</span></span>

<span data-ttu-id="a9084-205">Instanziierte diskriminierte Unions, die sich über mehrere Zeilen verteilen, sollten enthaltenen Daten einen neuen Bereich mit Einzug geben:</span><span class="sxs-lookup"><span data-stu-id="a9084-205">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="a9084-206">Die schließende Klammer kann sich auch auf einer neuen Linie befinden:</span><span class="sxs-lookup"><span data-stu-id="a9084-206">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="a9084-207">Formatieren von Datensatzdeklarationen</span><span class="sxs-lookup"><span data-stu-id="a9084-207">Formatting record declarations</span></span>

<span data-ttu-id="a9084-208">Einzug `{` in Typdefinition um 4 Leerzeichen und Starten der Feldliste in derselben Zeile:</span><span class="sxs-lookup"><span data-stu-id="a9084-208">Indent `{` in type definition by 4 spaces and start the field list on the same line:</span></span>

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

<span data-ttu-id="a9084-209">Das Platzieren des öffnenden Tokens in einer neuen Zeile und des schließenden Tokens in einer neuen Zeile ist vorzuziehen, wenn Sie Schnittstellenimplementierungen oder Member im Datensatz deklarieren:</span><span class="sxs-lookup"><span data-stu-id="a9084-209">Placing the opening token on a new line and the closing token on a new line is preferable if you are declaring interface implementations or members on the record:</span></span>

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a><span data-ttu-id="a9084-210">Formatieren von Datensätzen</span><span class="sxs-lookup"><span data-stu-id="a9084-210">Formatting records</span></span>

<span data-ttu-id="a9084-211">Kurze Datensätze können in einer Zeile geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="a9084-211">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="a9084-212">Datensätze, die länger sind, sollten neue Zeilen für Beschriftungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="a9084-212">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="a9084-213">Das Platzieren des Öffnenstokens in einer neuen Zeile, das Tabbed des Inhalts über einen Bereich und das schließende Token in einer neuen Zeile ist vorzuziehen, wenn Sie:</span><span class="sxs-lookup"><span data-stu-id="a9084-213">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferable if you are:</span></span>

* <span data-ttu-id="a9084-214">Verschieben von Datensätzen im Code mit unterschiedlichen Einzugsbereichen</span><span class="sxs-lookup"><span data-stu-id="a9084-214">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="a9084-215">Sie in eine Funktion einzupfeifen</span><span class="sxs-lookup"><span data-stu-id="a9084-215">Piping them into a function</span></span>

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

<span data-ttu-id="a9084-216">Für Listen- und Arrayelemente gelten die gleichen Regeln.</span><span class="sxs-lookup"><span data-stu-id="a9084-216">The same rules apply for list and array elements.</span></span>

## <a name="formatting-copy-and-update-record-expressions"></a><span data-ttu-id="a9084-217">Formatieren von Kopier- und Aktualisierungsdatensatzausdrücken</span><span class="sxs-lookup"><span data-stu-id="a9084-217">Formatting copy-and-update record expressions</span></span>

<span data-ttu-id="a9084-218">Ein Copy-and-Update-Datensatzausdruck ist immer noch ein Datensatz, daher gelten ähnliche Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="a9084-218">A copy-and-update record expression is still a record, so similar guidelines apply.</span></span>

<span data-ttu-id="a9084-219">Kurze Ausdrücke können in eine Zeile passen:</span><span class="sxs-lookup"><span data-stu-id="a9084-219">Short expressions can fit on one line:</span></span>

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

<span data-ttu-id="a9084-220">Längere Ausdrücke sollten neue Zeilen verwenden:</span><span class="sxs-lookup"><span data-stu-id="a9084-220">Longer expressions should use new lines:</span></span>

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="a9084-221">Wie bei der Datensatzanleitung können Sie separate Zeilen für die geschweiften Klammern und einEinzug eines Bereichs nach rechts mit dem Ausdruck widmen.</span><span class="sxs-lookup"><span data-stu-id="a9084-221">And as with the record guidance, you may want to dedicate separate lines for the braces and indent one scope to the right with the expression.</span></span> <span data-ttu-id="a9084-222">Beachten Sie, dass Sie in einigen speziellen Fällen, z. B. das Umschließen eines Werts mit einem optionalen Wert ohne Klammern, möglicherweise eine geschweifte Klammer in einer Zeile beibehalten müssen:</span><span class="sxs-lookup"><span data-stu-id="a9084-222">Note that in some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:</span></span>

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

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="a9084-223">Formatieren von Listen und Arrays</span><span class="sxs-lookup"><span data-stu-id="a9084-223">Formatting lists and arrays</span></span>

<span data-ttu-id="a9084-224">Schreiben `x :: l` Sie mit `::` Leerzeichen um den Operator (ist`::` ein Infixoperator, daher von Leerzeichen umgeben).</span><span class="sxs-lookup"><span data-stu-id="a9084-224">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="a9084-225">Liste und Arrays, die in einer einzelnen Zeile deklariert sind, sollten ein Leerzeichen nach der öffnenden Klammer und vor der schließenden Klammer haben:</span><span class="sxs-lookup"><span data-stu-id="a9084-225">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="a9084-226">Verwenden Sie immer mindestens ein Leerzeichen zwischen zwei unterschiedlichen, koredagen Operatoren.</span><span class="sxs-lookup"><span data-stu-id="a9084-226">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="a9084-227">Lassen Sie z. B. ein Leerzeichen zwischen a `[` und a. `{`</span><span class="sxs-lookup"><span data-stu-id="a9084-227">For example, leave a space between a `[` and a `{`.</span></span>

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

<span data-ttu-id="a9084-228">Die gleiche Richtlinie gilt für Listen oder Arrays von Tupeln.</span><span class="sxs-lookup"><span data-stu-id="a9084-228">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="a9084-229">Listen und Arrays, die über mehrere Zeilen aufgeteilt sind, folgen einer ähnlichen Regel wie Datensätze:</span><span class="sxs-lookup"><span data-stu-id="a9084-229">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

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

<span data-ttu-id="a9084-230">Und wie bei Datensätzen erleichtert das Deklarieren der öffnenden und schließenden Klammern in ihrer eigenen Zeile das Verschieben von Code und das Einleiten in Funktionen.</span><span class="sxs-lookup"><span data-stu-id="a9084-230">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

<span data-ttu-id="a9084-231">Wenn Arrays und Listen programmgesteuert `->` generiert `do ... yield` werden, bevorzugen Sie, wenn immer ein Wert generiert wird:</span><span class="sxs-lookup"><span data-stu-id="a9084-231">When generating arrays and lists programmatically, prefer `->` over `do ... yield` when a value is always generated:</span></span>

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x*x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x*x ]
```

<span data-ttu-id="a9084-232">In Situationen, `yield` in denen Daten bedingt generiert werden können oder aufeinander folgende Ausdrücke ausgewertet werden müssen, sind ältere Versionen der Sprache "F" erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a9084-232">Older versions of the F# language required specifying `yield` in situations where data may be generated conditionally, or there may be consecutive expressions to be evaluated.</span></span> <span data-ttu-id="a9084-233">Bevorzugen Sie das `yield` Weglassen dieser Schlüsselwörter, es sei denn, Sie müssen mit einer älteren Version der F-Sprache kompilieren:</span><span class="sxs-lookup"><span data-stu-id="a9084-233">Prefer omitting these `yield` keywords unless you must compile with an older F# language version:</span></span>

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

<span data-ttu-id="a9084-234">In einigen `do...yield` Fällen kann dies zur Lesbarkeit beiderbarkeit s.</span><span class="sxs-lookup"><span data-stu-id="a9084-234">In some cases, `do...yield` may aid in readability.</span></span> <span data-ttu-id="a9084-235">Diese Fälle sind zwar subjektiv, sollten aber berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="a9084-235">These cases, though subjective, should be taken into consideration.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="a9084-236">Formatieren von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="a9084-236">Formatting if expressions</span></span>

<span data-ttu-id="a9084-237">Der Einzug von Conditionals hängt von der Größe der Ausdrücke ab, aus denen sie besteht.</span><span class="sxs-lookup"><span data-stu-id="a9084-237">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="a9084-238">Wenn `cond` `e1` , `e2` und kurz sind, schreiben Sie sie einfach in einer Zeile:</span><span class="sxs-lookup"><span data-stu-id="a9084-238">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="a9084-239">Wenn `cond`entweder `e1` `e2` , oder länger, aber nicht mehrzeilig:</span><span class="sxs-lookup"><span data-stu-id="a9084-239">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="a9084-240">Wenn einer der Ausdrücke mehrzeilige Ausdrücke ist:</span><span class="sxs-lookup"><span data-stu-id="a9084-240">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="a9084-241">Mehrere Conditionals `elif` `else` mit und werden im gleichen `if`Bereich wie die eingerückt:</span><span class="sxs-lookup"><span data-stu-id="a9084-241">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="a9084-242">Musterübereinstimmungskonstrukte</span><span class="sxs-lookup"><span data-stu-id="a9084-242">Pattern matching constructs</span></span>

<span data-ttu-id="a9084-243">Verwenden `|` Sie für jede Klausel einer Übereinstimmung ohne Einzug eine.</span><span class="sxs-lookup"><span data-stu-id="a9084-243">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="a9084-244">Wenn der Ausdruck kurz ist, können Sie eine einzelne Zeile verwenden, wenn jeder Unterausdruck ebenfalls einfach ist.</span><span class="sxs-lookup"><span data-stu-id="a9084-244">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

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

<span data-ttu-id="a9084-245">Wenn der Ausdruck auf der rechten Seite des Musterübereinstimmungspfeils zu groß ist, `match` / `|`verschieben Sie ihn in die folgende Zeile, die einen Schritt von der eingerückt wird.</span><span class="sxs-lookup"><span data-stu-id="a9084-245">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="a9084-246">Der Musterabgleich anonymer `function`Funktionen, beginnend mit , sollte in der Regel nicht zu weit einrücken.</span><span class="sxs-lookup"><span data-stu-id="a9084-246">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="a9084-247">Beispielsweise ist es in Ordnung, einen Bereich wie folgt einzuablehnen:</span><span class="sxs-lookup"><span data-stu-id="a9084-247">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="a9084-248">Musterabgleich in `let` Funktionen, die von 4 Leerzeichen definiert sind oder `let rec` nach dem Start von `let`eingerückt werden sollen, auch wenn `function` das Schlüsselwort verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="a9084-248">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="a9084-249">Es wird nicht empfohlen, die Pfeile auszurichten.</span><span class="sxs-lookup"><span data-stu-id="a9084-249">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="a9084-250">Formatieren try/with-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="a9084-250">Formatting try/with expressions</span></span>

<span data-ttu-id="a9084-251">Der Musterabgleich für den Ausnahmetyp sollte auf `with`derselben Ebene wie eingerückt werden.</span><span class="sxs-lookup"><span data-stu-id="a9084-251">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

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

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="a9084-252">Formatierungsfunktion ParameterAnwendung</span><span class="sxs-lookup"><span data-stu-id="a9084-252">Formatting function parameter application</span></span>

<span data-ttu-id="a9084-253">Im Allgemeinen wird die Anwendung der meisten Funktionsparameter in derselben Zeile durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="a9084-253">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="a9084-254">Wenn Sie Parameter auf eine Funktion in einer neuen Zeile anwenden möchten, ziehen Sie sie um einen Bereich ein.</span><span class="sxs-lookup"><span data-stu-id="a9084-254">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

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

<span data-ttu-id="a9084-255">Dieselben Richtlinien gelten für Lambda-Ausdrücke als Funktionsargumente.</span><span class="sxs-lookup"><span data-stu-id="a9084-255">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="a9084-256">Wenn der Körper eines Lambda-Ausdrucks, kann der Körper eine andere Linie haben, eingerückt durch einen Bereich</span><span class="sxs-lookup"><span data-stu-id="a9084-256">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

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

<span data-ttu-id="a9084-257">Wenn der Text eines Lambdaausdrucks jedoch mehr als eine Zeile ist, sollten Sie ihn in eine separate Funktion einteilen, anstatt ein mehrzeiliges Konstrukt als einzelnes Argument auf eine Funktion anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="a9084-257">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="a9084-258">Formatieren von Infixoperatoren</span><span class="sxs-lookup"><span data-stu-id="a9084-258">Formatting infix operators</span></span>

<span data-ttu-id="a9084-259">Trennen Sie Operatoren nach Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="a9084-259">Separate operators by spaces.</span></span> <span data-ttu-id="a9084-260">Offensichtliche Ausnahmen von dieser `!` Regel `.` sind die und Operatoren.</span><span class="sxs-lookup"><span data-stu-id="a9084-260">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="a9084-261">Infix-Ausdrücke sind INfix-Auflisten in derselben Spalte:</span><span class="sxs-lookup"><span data-stu-id="a9084-261">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="a9084-262">Formatieren von Pipelineoperatoren</span><span class="sxs-lookup"><span data-stu-id="a9084-262">Formatting pipeline operators</span></span>

<span data-ttu-id="a9084-263">Pipeline-Operatoren `|>` sollten sich unter die Ausdrücke befolgen, auf denen sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="a9084-263">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

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

### <a name="formatting-modules"></a><span data-ttu-id="a9084-264">Formatieren von Modulen</span><span class="sxs-lookup"><span data-stu-id="a9084-264">Formatting modules</span></span>

<span data-ttu-id="a9084-265">Code in einem lokalen Modul muss relativ zum Modul eingerückt werden, code in einem Modul der obersten Ebene sollte jedoch nicht eingerückt werden.</span><span class="sxs-lookup"><span data-stu-id="a9084-265">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="a9084-266">Namespaceelemente müssen nicht eingerückt werden.</span><span class="sxs-lookup"><span data-stu-id="a9084-266">Namespace elements do not have to be indented.</span></span>

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

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="a9084-267">Formatieren von Objektausdrücken und -schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a9084-267">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="a9084-268">Objektausdrücke und -schnittstellen sollten auf die `member` gleiche Weise ausgerichtet werden, wenn sie nach 4 Leerzeichen eingerückt werden.</span><span class="sxs-lookup"><span data-stu-id="a9084-268">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="a9084-269">Formatieren von Leerraum in Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="a9084-269">Formatting white space in expressions</span></span>

<span data-ttu-id="a9084-270">Vermeiden Sie überflüssige Leerzeichen in F-Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="a9084-270">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="a9084-271">Benannte Argumente sollten auch `=`keinen Platz für die folgenden Argumente haben:</span><span class="sxs-lookup"><span data-stu-id="a9084-271">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a><span data-ttu-id="a9084-272">Formatieren von Attributen</span><span class="sxs-lookup"><span data-stu-id="a9084-272">Formatting attributes</span></span>

<span data-ttu-id="a9084-273">[Attribute](../language-reference/attributes.md) werden über einem Konstrukt platziert:</span><span class="sxs-lookup"><span data-stu-id="a9084-273">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

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

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="a9084-274">Formatieren von Attributen für Parameter</span><span class="sxs-lookup"><span data-stu-id="a9084-274">Formatting attributes on parameters</span></span>

<span data-ttu-id="a9084-275">Attribute können auch Orte auf Parametern sein.</span><span class="sxs-lookup"><span data-stu-id="a9084-275">Attributes can also be places on parameters.</span></span> <span data-ttu-id="a9084-276">Platzieren Sie in diesem Fall dann dieselbe Zeile wie der Parameter und vor dem Namen:</span><span class="sxs-lookup"><span data-stu-id="a9084-276">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="a9084-277">Formatieren mehrerer Attribute</span><span class="sxs-lookup"><span data-stu-id="a9084-277">Formatting multiple attributes</span></span>

<span data-ttu-id="a9084-278">Wenn mehrere Attribute auf ein Konstrukt angewendet werden, das kein Parameter ist, sollten sie so platziert werden, dass es ein Attribut pro Zeile gibt:</span><span class="sxs-lookup"><span data-stu-id="a9084-278">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="a9084-279">Wenn sie auf einen Parameter angewendet werden, müssen `;` sie sich in derselben Zeile und durch ein Trennzeichen getrennt haben.</span><span class="sxs-lookup"><span data-stu-id="a9084-279">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="a9084-280">Formatieren von Literalen</span><span class="sxs-lookup"><span data-stu-id="a9084-280">Formatting literals</span></span>

<span data-ttu-id="a9084-281">[Die Definitionen,](../language-reference/literals.md) `Literal` die das Attribut verwenden, sollten das Attribut in einer eigenen Zeile platzieren und die PascalCase-Benennung verwenden:</span><span class="sxs-lookup"><span data-stu-id="a9084-281">[F# literals](../language-reference/literals.md) using the `Literal` attribute should place the attribute on its own line and use PascalCase naming:</span></span>

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="a9084-282">Vermeiden Sie es, das Attribut in derselben Zeile wie der Wert zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="a9084-282">Avoid placing the attribute on the same line as the value.</span></span>
