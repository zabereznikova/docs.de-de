---
title: Richtlinien für das Formatieren von F#-Code
description: 'Hier finden Sie Richtlinien zum Formatieren von F #'
ms.date: 08/31/2020
ms.openlocfilehash: 01a5f9ce0c9b5a67bb0c70bce0829ac300032883
ms.sourcegitcommit: c3093e9d106d8ca87cc86eef1f2ae4ecfb392118
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2020
ms.locfileid: "97737189"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="999ef-103">Richtlinien für das Formatieren von F#-Code</span><span class="sxs-lookup"><span data-stu-id="999ef-103">F# code formatting guidelines</span></span>

<span data-ttu-id="999ef-104">Dieser Artikel enthält Richtlinien zum Formatieren von Code, sodass der F #-Code wie folgt lautet:</span><span class="sxs-lookup"><span data-stu-id="999ef-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="999ef-105">Besser lesbar</span><span class="sxs-lookup"><span data-stu-id="999ef-105">More legible</span></span>
* <span data-ttu-id="999ef-106">In Übereinstimmung mit Konventionen, die von Formatierungs Tools in Visual Studio und anderen Editoren angewendet werden</span><span class="sxs-lookup"><span data-stu-id="999ef-106">In accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="999ef-107">Vergleichbar mit anderem Code Online</span><span class="sxs-lookup"><span data-stu-id="999ef-107">Similar to other code online</span></span>

<span data-ttu-id="999ef-108">Diese Richtlinien basieren auf [einer umfassenden Anleitung zu F #-Formatierungs Konventionen](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) durch [Anh-dung Phan](https://github.com/dungpa).</span><span class="sxs-lookup"><span data-stu-id="999ef-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="999ef-109">Allgemeine Regeln für Einzug</span><span class="sxs-lookup"><span data-stu-id="999ef-109">General rules for indentation</span></span>

<span data-ttu-id="999ef-110">In F # wird standardmäßig signifikanter Leerraum verwendet.</span><span class="sxs-lookup"><span data-stu-id="999ef-110">F# uses significant white space by default.</span></span> <span data-ttu-id="999ef-111">Die folgenden Richtlinien dienen als Leitfaden zum vermitteln einiger Herausforderungen, die dies erzwingen kann.</span><span class="sxs-lookup"><span data-stu-id="999ef-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="999ef-112">Verwenden von Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="999ef-112">Using spaces</span></span>

<span data-ttu-id="999ef-113">Wenn Einzug erforderlich ist, müssen Sie Leerzeichen und keine Tabulatoren verwenden.</span><span class="sxs-lookup"><span data-stu-id="999ef-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="999ef-114">Es ist mindestens ein Leerzeichen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="999ef-114">At least one space is required.</span></span> <span data-ttu-id="999ef-115">In Ihrer Organisation können Codierungsstandards erstellt werden, um die Anzahl der für den Einzug zu verwendenden Leerzeichen anzugeben. zwei, drei oder vier Leerzeichen für den Einzug auf jeder Ebene, in der der Einzug auftritt, ist typisch.</span><span class="sxs-lookup"><span data-stu-id="999ef-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three, or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="999ef-116">**Es werden vier Leerzeichen pro Einzug empfohlen.**</span><span class="sxs-lookup"><span data-stu-id="999ef-116">**We recommend four spaces per indentation.**</span></span>

<span data-ttu-id="999ef-117">Dies bedeutet, dass der Einzug von Programmen eine subjektive Angelegenheit ist.</span><span class="sxs-lookup"><span data-stu-id="999ef-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="999ef-118">Variationen sind in Ordnung, aber die erste Regel, die Sie befolgen sollten, ist die *Konsistenz des* Einzugs.</span><span class="sxs-lookup"><span data-stu-id="999ef-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="999ef-119">Wählen Sie eine im allgemeinen akzeptierte Art von Einzug aus, und verwenden Sie sie systematisch in der gesamten Codebasis.</span><span class="sxs-lookup"><span data-stu-id="999ef-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="999ef-120">Formatieren von Leerraum</span><span class="sxs-lookup"><span data-stu-id="999ef-120">Formatting white space</span></span>

<span data-ttu-id="999ef-121">F # ist Leerraum sensibel.</span><span class="sxs-lookup"><span data-stu-id="999ef-121">F# is white space sensitive.</span></span> <span data-ttu-id="999ef-122">Obwohl die meisten Semantik aus Leerraum durch den ordnungsgemäßen Einzug abgedeckt ist, müssen einige andere Punkte berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="999ef-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="999ef-123">Formatierungs Operatoren in arithmetischen Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="999ef-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="999ef-124">Verwenden Sie immer Leerraum um binäre arithmetische Ausdrücke:</span><span class="sxs-lookup"><span data-stu-id="999ef-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="999ef-125">Unäre `-` Operatoren sollten immer direkt auf den Wert folgen, den Sie neinieren:</span><span class="sxs-lookup"><span data-stu-id="999ef-125">Unary `-` operators should always be immediately followed by the value they are negating:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="999ef-126">Wenn ein Leerzeichen nach dem Operator hinzugefügt wird `-` , kann dies zu Verwirrung für andere führen.</span><span class="sxs-lookup"><span data-stu-id="999ef-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="999ef-127">Zusammenfassend ist es wichtig, immer Folgendes zu beachten:</span><span class="sxs-lookup"><span data-stu-id="999ef-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="999ef-128">Binäre Operatoren mit Leerraum umschließen</span><span class="sxs-lookup"><span data-stu-id="999ef-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="999ef-129">Nach einem unären Operator nie nachfolgende Leerzeichen enthalten</span><span class="sxs-lookup"><span data-stu-id="999ef-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="999ef-130">Die Richtlinie für den binären arithmetischen Operator ist besonders wichtig.</span><span class="sxs-lookup"><span data-stu-id="999ef-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="999ef-131">Wenn ein binärer Operator nicht umschließt `-` , in Kombination mit bestimmten Formatierungsoptionen, könnte dies dazu führen, dass er als unäres interpretiert wird `-` .</span><span class="sxs-lookup"><span data-stu-id="999ef-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="999ef-132">Umschließen einer benutzerdefinierten Operator Definition mit Leerraum</span><span class="sxs-lookup"><span data-stu-id="999ef-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="999ef-133">Verwenden Sie immer Leerraum, um eine Operator Definition zu umschließen:</span><span class="sxs-lookup"><span data-stu-id="999ef-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="999ef-134">Für alle benutzerdefinierten Operatoren, die mit beginnen `*` und über mehr als ein Zeichen verfügen, müssen Sie am Anfang der Definition ein Leerzeichen hinzufügen, um eine compilermehrdeutigkeit zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="999ef-134">For any custom operator that starts with `*` and that has more than one character, you need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="999ef-135">Aus diesem Grund wird empfohlen, die Definitionen aller Operatoren einfach mit einem einzelnen Leerzeichen zu umschließen.</span><span class="sxs-lookup"><span data-stu-id="999ef-135">Because of this, we recommend that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="999ef-136">Umschließen von Funktionsparameter Pfeilen mit Leerraum</span><span class="sxs-lookup"><span data-stu-id="999ef-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="999ef-137">Wenn Sie die Signatur einer Funktion definieren, verwenden Sie Leerraum um das `->` Symbol:</span><span class="sxs-lookup"><span data-stu-id="999ef-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a><span data-ttu-id="999ef-138">Umschließen von Funktions Argumenten mit Leerraum</span><span class="sxs-lookup"><span data-stu-id="999ef-138">Surround function arguments with white space</span></span>

<span data-ttu-id="999ef-139">Verwenden Sie beim Definieren einer Funktion Leerzeichen um jedes Argument.</span><span class="sxs-lookup"><span data-stu-id="999ef-139">When defining a function, use white space around each argument.</span></span>

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="avoid-name-sensitive-alignments"></a><span data-ttu-id="999ef-140">Vermeiden von namens sensiblen Ausrichtungen</span><span class="sxs-lookup"><span data-stu-id="999ef-140">Avoid name-sensitive alignments</span></span>

<span data-ttu-id="999ef-141">Im Allgemeinen sollten Sie versuchen, den Einzug und die Ausrichtung zu vermeiden, die von der Benennung abhängig sind:</span><span class="sxs-lookup"><span data-stu-id="999ef-141">In general, seek to avoid indentation and alignment that is sensitive to naming:</span></span>

```fsharp
// OK
let myLongValueName =
    someExpression
    |> anotherExpression


// Bad
let myLongValueName = someExpression
                      |> anotherExpression
```

<span data-ttu-id="999ef-142">Dies wird manchmal als "Vanity Alignment" oder "Vanity Einzug" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="999ef-142">This is sometimes called “vanity alignment” or “vanity indentation”.</span></span> <span data-ttu-id="999ef-143">Die Hauptgründe hierfür sind:</span><span class="sxs-lookup"><span data-stu-id="999ef-143">The primary reasons for avoiding this are:</span></span>

* <span data-ttu-id="999ef-144">Wichtiger Code wird weit nach rechts verschoben.</span><span class="sxs-lookup"><span data-stu-id="999ef-144">Important code is moved far to the right</span></span>
* <span data-ttu-id="999ef-145">Für den eigentlichen Code ist weniger Breite übrig.</span><span class="sxs-lookup"><span data-stu-id="999ef-145">There is less width left for the actual code</span></span>
* <span data-ttu-id="999ef-146">Umbenennen kann die Ausrichtung unterbrechen</span><span class="sxs-lookup"><span data-stu-id="999ef-146">Renaming can break the alignment</span></span>

<span data-ttu-id="999ef-147">Führen Sie die gleichen Schritte für aus `do` / `do!` , um den Einzug konsistent zu halten `let` / `let!` .</span><span class="sxs-lookup"><span data-stu-id="999ef-147">Do the same for `do`/`do!` in order to keep the indentation consistent with `let`/`let!`.</span></span> <span data-ttu-id="999ef-148">Hier ist ein Beispiel für die Verwendung von `do` in einer-Klasse:</span><span class="sxs-lookup"><span data-stu-id="999ef-148">Here is an example using `do` in a class:</span></span>

```fsharp
// OK
type Foo () =
    let foo =
        fooBarBaz
        |> loremIpsumDolorSitAmet
        |> theQuickBrownFoxJumpedOverTheLazyDog
    do
        fooBarBaz
        |> loremIpsumDolorSitAmet
        |> theQuickBrownFoxJumpedOverTheLazyDog

// Bad - notice the "do" expression is indented one space less than the `let` expression
type Foo () =
    let foo =
        fooBarBaz
        |> loremIpsumDolorSitAmet
        |> theQuickBrownFoxJumpedOverTheLazyDog
    do fooBarBaz
       |> loremIpsumDolorSitAmet
       |> theQuickBrownFoxJumpedOverTheLazyDog
```

<span data-ttu-id="999ef-149">Im folgenden finden Sie ein Beispiel für `do!` die Verwendung von zwei Leerzeichen für einzüden (da `do!` es zufällig keinen Unterschied zwischen den Ansätzen gibt, wenn 4 Einschub Zeichen verwendet werden):</span><span class="sxs-lookup"><span data-stu-id="999ef-149">Here is an example with `do!` using 2 spaces of indentation (because with `do!` there is coincidentally no difference between the approaches when using 4 spaces of indentation):</span></span>

```fsharp
// OK
async {
  let! foo =
    fooBarBaz
    |> loremIpsumDolorSitAmet
    |> theQuickBrownFoxJumpedOverTheLazyDog
  do!
    fooBarBaz
    |> loremIpsumDolorSitAmet
    |> theQuickBrownFoxJumpedOverTheLazyDog
}

// Bad - notice the "do!" expression is indented two spaces more than the `let!` expression
async {
  let! foo =
    fooBarBaz
    |> loremIpsumDolorSitAmet
    |> theQuickBrownFoxJumpedOverTheLazyDog
  do! fooBarBaz
      |> loremIpsumDolorSitAmet
      |> theQuickBrownFoxJumpedOverTheLazyDog
}
```

### <a name="place-parameters-on-a-new-line-for-long-definitions"></a><span data-ttu-id="999ef-150">Parameter für lange Definitionen in einer neuen Zeile platzieren</span><span class="sxs-lookup"><span data-stu-id="999ef-150">Place parameters on a new line for long definitions</span></span>

<span data-ttu-id="999ef-151">Wenn Sie über eine lange Funktionsdefinition verfügen, platzieren Sie die Parameter in neuen Zeilen, und fügen Sie Sie so ein, dass Sie der Einzugs Ebene des nachfolgenden Parameters entsprechen.</span><span class="sxs-lookup"><span data-stu-id="999ef-151">If you have a long function definition, place the parameters on new lines and indent them to match the indentation level of the subsequent parameter.</span></span>

```fsharp
module M =
    let longFunctionWithLotsOfParameters
        (aVeryLongParam: AVeryLongTypeThatYouNeedToUse)
        (aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse)
        (aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse)
        =
        // ... the body of the method follows

    let longFunctionWithLotsOfParametersAndReturnType
        (aVeryLongParam: AVeryLongTypeThatYouNeedToUse)
        (aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse)
        (aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse)
        : ReturnType =
        // ... the body of the method follows

    let longFunctionWithLongTupleParameter
        (
            aVeryLongParam: AVeryLongTypeThatYouNeedToUse,
            aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse,
            aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse
        ) =
        // ... the body of the method follows

    let longFunctionWithLongTupleParameterAndReturnType
        (
            aVeryLongParam: AVeryLongTypeThatYouNeedToUse,
            aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse,
            aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse
        ) : ReturnType =
        // ... the body of the method follows
```

<span data-ttu-id="999ef-152">Dies gilt auch für Member, Konstruktoren und Parameter mithilfe von Tupeln:</span><span class="sxs-lookup"><span data-stu-id="999ef-152">This also applies to members, constructors, and parameters using tuples:</span></span>

```fsharp
type TM() =
    member _.LongMethodWithLotsOfParameters
        (
            aVeryLongParam: AVeryLongTypeThatYouNeedToUse,
            aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse,
            aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse
        ) =
        // ... the body of the method

type TC
    (
        aVeryLongCtorParam: AVeryLongTypeThatYouNeedToUse,
        aSecondVeryLongCtorParam: AVeryLongTypeThatYouNeedToUse,
        aThirdVeryLongCtorParam: AVeryLongTypeThatYouNeedToUse
    ) =
    // ... the body of the class follows
```

<span data-ttu-id="999ef-153">Wenn die Parameter klassifiziert werden oder eine explizite Rückgabetyp Anmerkung vorliegt, ist es vorzuziehen, das `=` Zeichen in einer neuen Zeile zu platzieren:</span><span class="sxs-lookup"><span data-stu-id="999ef-153">If the parameters are currified or there's an explicit return type annotation, it is preferable to place the `=` character on a new line:</span></span>

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters
        (
            aVeryLongParam: AVeryLongTypeThatYouNeedToUse,
            aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse,
            aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse
        ) : AReturnType =
        // ... the body of the method
    member _.LongMethodWithLotsOfCurrifiedParams
        (aVeryLongParam: AVeryLongTypeThatYouNeedToUse)
        (aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse)
        (aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse)
        =
        // ... the body of the method
```

<span data-ttu-id="999ef-154">Dies ist eine Methode, um zu lange Zeilen zu vermeiden (für den Fall, dass der Rückgabetyp einen langen Namen aufweisen kann) und weniger Zeilen Schaden beim Hinzufügen von Parametern hat</span><span class="sxs-lookup"><span data-stu-id="999ef-154">This is a way to avoid too long lines (in case return type might have long name) and have less line-damage when adding parameters.</span></span>

### <a name="type-annotations"></a><span data-ttu-id="999ef-155">Typanmerkungen</span><span class="sxs-lookup"><span data-stu-id="999ef-155">Type annotations</span></span>

#### <a name="right-pad-function-argument-type-annotations"></a><span data-ttu-id="999ef-156">Typanmerkungen für Funktionsargumente des Rechts Auffüll Bereichs</span><span class="sxs-lookup"><span data-stu-id="999ef-156">Right-pad function argument type annotations</span></span>

<span data-ttu-id="999ef-157">Wenn Sie Argumente mit Typanmerkungen definieren, verwenden Sie Leerraum nach dem `:` Symbol:</span><span class="sxs-lookup"><span data-stu-id="999ef-157">When defining arguments with type annotations, use white space after the `:` symbol:</span></span>

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a><span data-ttu-id="999ef-158">Umschließende Rückgabetyp Anmerkungen mit Leerraum</span><span class="sxs-lookup"><span data-stu-id="999ef-158">Surround return type annotations with white space</span></span>

<span data-ttu-id="999ef-159">Verwenden Sie in einer Let-gebundenen Funktion oder Werttyp Anmerkung (Rückgabetyp im Fall einer Funktion) Leerraum vor und nach dem `:` Symbol:</span><span class="sxs-lookup"><span data-stu-id="999ef-159">In a let-bound function or value type annotation (return type in the case of a function), use white space before and after the `:` symbol:</span></span>

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="999ef-160">Formatieren von leeren Zeilen</span><span class="sxs-lookup"><span data-stu-id="999ef-160">Formatting blank lines</span></span>

* <span data-ttu-id="999ef-161">Trennen Sie Funktions-und Klassendefinitionen der obersten Ebene mit zwei leeren Zeilen.</span><span class="sxs-lookup"><span data-stu-id="999ef-161">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="999ef-162">Methoden Definitionen innerhalb einer Klasse werden durch eine einzelne Leerzeile getrennt.</span><span class="sxs-lookup"><span data-stu-id="999ef-162">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="999ef-163">Zusätzliche leere Zeilen können (sparsam) zum Trennen von Gruppen verwandter Funktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="999ef-163">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="999ef-164">Leere Zeilen können zwischen einer Reihe verwandter Einzeiler (z. b. einer Gruppe von Pseudo Implementierungen) weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="999ef-164">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="999ef-165">Verwenden Sie in Funktionen, die in den Funktionen sehr sparsam sind, um logische Abschnitte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="999ef-165">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="999ef-166">Formatieren von Kommentaren</span><span class="sxs-lookup"><span data-stu-id="999ef-166">Formatting comments</span></span>

<span data-ttu-id="999ef-167">Bevorzugen Sie im Allgemeinen mehrere Kommentare mit doppelten Schrägstrichen über Block Kommentare im ml-Stil.</span><span class="sxs-lookup"><span data-stu-id="999ef-167">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="999ef-168">Inline Kommentare sollten den ersten Buchstaben ausnutzen.</span><span class="sxs-lookup"><span data-stu-id="999ef-168">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="999ef-169">Benennungskonventionen</span><span class="sxs-lookup"><span data-stu-id="999ef-169">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="999ef-170">Verwenden Sie "CamelCase" für Klassen gebundene, Ausdrucks gebundene und Muster gebundene Werte und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="999ef-170">Use camelCase for class-bound, expression-bound, and pattern-bound values and functions</span></span>

<span data-ttu-id="999ef-171">Es ist üblich, dass im F #-Stil für alle Namen, die als lokale Variablen oder in Muster Übereinstimmungen und Funktionsdefinitionen gebunden sind, "CamelCase" verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="999ef-171">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="999ef-172">Lokal gebundene Funktionen in Klassen sollten auch "CamelCase" verwenden.</span><span class="sxs-lookup"><span data-stu-id="999ef-172">Locally bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="999ef-173">Verwenden von "CamelCase" für Modul gebundene öffentliche Funktionen</span><span class="sxs-lookup"><span data-stu-id="999ef-173">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="999ef-174">Wenn eine Modul gebundene Funktion Teil einer öffentlichen API ist, sollte Sie "CamelCase" verwenden:</span><span class="sxs-lookup"><span data-stu-id="999ef-174">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="999ef-175">Verwenden Sie "CamelCase" für interne und private Modul gebundene Werte und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="999ef-175">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="999ef-176">Verwenden Sie CamelCase für private Modul gebundene Werte, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="999ef-176">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="999ef-177">Ad-hoc-Funktionen in Skripts</span><span class="sxs-lookup"><span data-stu-id="999ef-177">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="999ef-178">Werte, die die interne Implementierung eines Moduls oder Typs bilden</span><span class="sxs-lookup"><span data-stu-id="999ef-178">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="999ef-179">Verwenden Sie "CamelCase" für Parameter.</span><span class="sxs-lookup"><span data-stu-id="999ef-179">Use camelCase for parameters</span></span>

<span data-ttu-id="999ef-180">Alle Parameter sollten in Übereinstimmung mit den .net-Benennungs Konventionen "CamelCase" verwenden.</span><span class="sxs-lookup"><span data-stu-id="999ef-180">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="999ef-181">Verwenden von PascalCase für Module</span><span class="sxs-lookup"><span data-stu-id="999ef-181">Use PascalCase for modules</span></span>

<span data-ttu-id="999ef-182">Alle Module (Top-Level, Internal, private, netsted) sollten PascalCase verwenden.</span><span class="sxs-lookup"><span data-stu-id="999ef-182">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="999ef-183">Verwenden von PascalCase für Typdeklarationen, Elemente und Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="999ef-183">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="999ef-184">Klassen, Schnittstellen, Strukturen, Enumerationen, Delegaten, Datensätze und Unterscheidungs-Unions sollten mit PascalCase benannt werden.</span><span class="sxs-lookup"><span data-stu-id="999ef-184">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="999ef-185">Member innerhalb von Typen und Bezeichnungen für Datensätze und Unterscheidungs-Unions sollten auch PascalCase verwenden.</span><span class="sxs-lookup"><span data-stu-id="999ef-185">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="999ef-186">Verwenden von PascalCase für Konstrukte in .net</span><span class="sxs-lookup"><span data-stu-id="999ef-186">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="999ef-187">Namespaces, Ausnahmen, Ereignisse und Projekt/ `.dll` Namen sollten ebenfalls PascalCase verwenden.</span><span class="sxs-lookup"><span data-stu-id="999ef-187">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="999ef-188">Dies bedeutet nicht nur, dass die Nutzung von anderen .NET-Sprachen für Consumer natürlicher ist, sondern auch mit den .net-Benennungs Konventionen, die wahrscheinlich auftreten.</span><span class="sxs-lookup"><span data-stu-id="999ef-188">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="999ef-189">Unterstriche in Namen vermeiden</span><span class="sxs-lookup"><span data-stu-id="999ef-189">Avoid underscores in names</span></span>

<span data-ttu-id="999ef-190">In der Vergangenheit haben einige F #-Bibliotheken Unterstriche in Namen verwendet.</span><span class="sxs-lookup"><span data-stu-id="999ef-190">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="999ef-191">Dies wird jedoch nicht mehr weitgehend akzeptiert, weil es Konflikte mit .net-Benennungs Konventionen verursacht.</span><span class="sxs-lookup"><span data-stu-id="999ef-191">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="999ef-192">Das heißt, einige F #-Programmierer verwenden Unterstriche stark, teilweise aus historischen Gründen, und Toleranz und Respekt ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="999ef-192">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="999ef-193">Allerdings ist der Stil oft nicht für andere Personen beliebt, die entscheiden können, ob diese verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="999ef-193">However, the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="999ef-194">Eine Ausnahme umfasst die Interoperabilität mit systemeigenen Komponenten, bei denen Unterstriche häufig vorkommen.</span><span class="sxs-lookup"><span data-stu-id="999ef-194">One exception includes interoperating with native components, where underscores are common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="999ef-195">Standard-F #-Operatoren verwenden</span><span class="sxs-lookup"><span data-stu-id="999ef-195">Use standard F# operators</span></span>

<span data-ttu-id="999ef-196">Die folgenden Operatoren sind in der F #-Standardbibliothek definiert und sollten anstelle der Definition von Entsprechungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="999ef-196">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="999ef-197">Die Verwendung dieser Operatoren wird empfohlen, da Sie dazu führt, dass der Code besser lesbar und idiatisch ist.</span><span class="sxs-lookup"><span data-stu-id="999ef-197">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="999ef-198">Entwickler, die einen Hintergrund in ocaml oder einer anderen funktionalen Programmiersprache haben, sind möglicherweise an verschiedene Idiome gewöhnt.</span><span class="sxs-lookup"><span data-stu-id="999ef-198">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="999ef-199">In der folgenden Liste werden die empfohlenen F #-Operatoren zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="999ef-199">The following list summarizes the recommended F# operators.</span></span>

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="999ef-200">Verwenden Sie Präfix Syntax für Generika ( `Foo<T>` ) in bevorzugter postfix Syntax ( `T Foo` ).</span><span class="sxs-lookup"><span data-stu-id="999ef-200">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="999ef-201">F # erbt sowohl den Postfix-ml-Stil der Benennung generischer Typen (z. b. `int list` ) als auch das Präfix .NET-Format (z `list<int>` . b.).</span><span class="sxs-lookup"><span data-stu-id="999ef-201">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="999ef-202">Bevorzugen Sie den .net-Stil mit Ausnahme von fünf spezifischen Typen:</span><span class="sxs-lookup"><span data-stu-id="999ef-202">Prefer the .NET style, except for five specific types:</span></span>

1. <span data-ttu-id="999ef-203">Verwenden Sie für F #-Listen das postfix-Formular: `int list` anstelle von `list<int>` .</span><span class="sxs-lookup"><span data-stu-id="999ef-203">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="999ef-204">Verwenden Sie für F #-Optionen das postfix-Formular: `int option` anstelle von `option<int>` .</span><span class="sxs-lookup"><span data-stu-id="999ef-204">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="999ef-205">Verwenden Sie für F #-Wert Optionen das postfix-Formular: `int voption` anstelle von `voption<int>` .</span><span class="sxs-lookup"><span data-stu-id="999ef-205">For F# Value Options, use the postfix form: `int voption` rather than `voption<int>`.</span></span>
4. <span data-ttu-id="999ef-206">Verwenden Sie für F #-Arrays den syntaktischen Namen `int[]` anstelle von `int array` oder `array<int>` .</span><span class="sxs-lookup"><span data-stu-id="999ef-206">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
5. <span data-ttu-id="999ef-207">Verwenden Sie für Verweis Zellen `int ref` anstelle von `ref<int>` oder `Ref<int>` .</span><span class="sxs-lookup"><span data-stu-id="999ef-207">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="999ef-208">Verwenden Sie für alle anderen Typen das Präfix-Formular.</span><span class="sxs-lookup"><span data-stu-id="999ef-208">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="999ef-209">Formatierung von Tupeln</span><span class="sxs-lookup"><span data-stu-id="999ef-209">Formatting tuples</span></span>

<span data-ttu-id="999ef-210">Eine tupelinstanziierung sollte in Klammern gesetzt werden, und auf die Trennzeichen in diesem muss ein einzelnes Leerzeichen folgen, z. b.: `(1, 2)` , `(x, y, z)` .</span><span class="sxs-lookup"><span data-stu-id="999ef-210">A tuple instantiation should be parenthesized, and the delimiting commas within it should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="999ef-211">Es wird häufig angenommen, Klammern bei der Muster Übereinstimmung von Tupeln auszulassen:</span><span class="sxs-lookup"><span data-stu-id="999ef-211">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

<span data-ttu-id="999ef-212">Es wird auch häufig angenommen, Klammern auszulassen, wenn das Tupel der Rückgabewert einer Funktion ist:</span><span class="sxs-lookup"><span data-stu-id="999ef-212">It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span></span>

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

<span data-ttu-id="999ef-213">Zusammenfassend gilt, dass Tupel-Instanziierungen in Klammern bevorzugen, aber wenn Sie Tupel für den Musterabgleich oder einen Rückgabewert verwenden, wird es als ausreichend erachtet, Klammern zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="999ef-213">In summary, prefer parenthesized tuple instantiations, but when using tuples for pattern matching or a return value, it is considered fine to avoid parentheses.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="999ef-214">Formatierung diskriminierter Union-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="999ef-214">Formatting discriminated union declarations</span></span>

<span data-ttu-id="999ef-215">Einzug `|` in Typdefinition um vier Leerzeichen:</span><span class="sxs-lookup"><span data-stu-id="999ef-215">Indent `|` in type definition by four spaces:</span></span>

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

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="999ef-216">Formatieren diskriminierter Unions</span><span class="sxs-lookup"><span data-stu-id="999ef-216">Formatting discriminated unions</span></span>

<span data-ttu-id="999ef-217">Instanziierte Unterscheidungs-Unions, die auf mehrere Zeilen aufgeteilt werden, sollten enthaltene Daten einen neuen Bereich mit Einzug vermitteln:</span><span class="sxs-lookup"><span data-stu-id="999ef-217">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="999ef-218">Die schließende Klammer kann sich auch in einer neuen Zeile befinden:</span><span class="sxs-lookup"><span data-stu-id="999ef-218">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="999ef-219">Formatieren von Datensätze</span><span class="sxs-lookup"><span data-stu-id="999ef-219">Formatting record declarations</span></span>

<span data-ttu-id="999ef-220">Einzug `{` in die Typdefinition um vier Leerzeichen, und die Feldliste wird in derselben Zeile gestartet:</span><span class="sxs-lookup"><span data-stu-id="999ef-220">Indent `{` in type definition by four spaces and start the field list on the same line:</span></span>

```fsharp
// OK
type PostalAddress =
    { Address: string
      City: string
      Zip: string }
    member x.ZipAndCity = $"{x.Zip} {x.City}"

// Not OK
type PostalAddress =
  { Address: string
    City: string
    Zip: string }
    member x.ZipAndCity = $"{x.Zip} {x.City}"

// Unusual in F#
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
```

<span data-ttu-id="999ef-221">Die Platzierung des öffnenden Tokens in einer neuen Zeile und das schließende Token in einer neuen Zeile ist vorzuziehen, wenn Sie Schnittstellen Implementierungen oder Member im Datensatz deklarieren:</span><span class="sxs-lookup"><span data-stu-id="999ef-221">Placing the opening token on a new line and the closing token on a new line is preferable if you are declaring interface implementations or members on the record:</span></span>

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
    member x.ZipAndCity = $"{x.Zip} {x.City}"

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a><span data-ttu-id="999ef-222">Datensätze formatieren</span><span class="sxs-lookup"><span data-stu-id="999ef-222">Formatting records</span></span>

<span data-ttu-id="999ef-223">Kurze Datensätze können in einer Zeile geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="999ef-223">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="999ef-224">Für Datensätze, die länger sind, sollten neue Zeilen für Bezeichnungen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="999ef-224">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="999ef-225">Wenn Sie das öffnende Token in einer neuen Zeile platzieren, wird der Inhalt in einem Bereich im Registerkarten Format angezeigt, und das schließende Token in einer neuen Zeile ist vorzuziehen, wenn Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="999ef-225">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferable if you are:</span></span>

* <span data-ttu-id="999ef-226">Verschieben von Datensätzen im Code mit unterschiedlichen Einzugs Bereichen</span><span class="sxs-lookup"><span data-stu-id="999ef-226">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="999ef-227">Weiterleiten an eine Funktion</span><span class="sxs-lookup"><span data-stu-id="999ef-227">Piping them into a function</span></span>

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
    |> Option.map
        (fun x ->
            {
                MyField = x
            })
```

<span data-ttu-id="999ef-228">Die gleichen Regeln gelten für Listen-und Array Elemente.</span><span class="sxs-lookup"><span data-stu-id="999ef-228">The same rules apply for list and array elements.</span></span>

## <a name="formatting-copy-and-update-record-expressions"></a><span data-ttu-id="999ef-229">Formatieren von Ausdrücken zum Kopieren und Aktualisieren von Datensätzen</span><span class="sxs-lookup"><span data-stu-id="999ef-229">Formatting copy-and-update record expressions</span></span>

<span data-ttu-id="999ef-230">Ein Kopier-und Update Daten Satz Ausdruck ist immer noch ein Datensatz, daher gelten ähnliche Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="999ef-230">A copy-and-update record expression is still a record, so similar guidelines apply.</span></span>

<span data-ttu-id="999ef-231">Kurze Ausdrücke können in eine Zeile passen:</span><span class="sxs-lookup"><span data-stu-id="999ef-231">Short expressions can fit on one line:</span></span>

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

<span data-ttu-id="999ef-232">Längere Ausdrücke sollten neue Zeilen verwenden:</span><span class="sxs-lookup"><span data-stu-id="999ef-232">Longer expressions should use new lines:</span></span>

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = [ "Zippy"; "George"; "Bungle" ] }
```

<span data-ttu-id="999ef-233">Ebenso wie bei den Daten Satz Anleitungen sollten Sie separate Zeilen für geschweifte Klammern verwenden und einen Bereich mit dem Ausdruck nach rechts einziehen.</span><span class="sxs-lookup"><span data-stu-id="999ef-233">And as with the record guidance, you may want to dedicate separate lines for the braces and indent one scope to the right with the expression.</span></span> <span data-ttu-id="999ef-234">In einigen besonderen Fällen (z. b. beim umschließen eines Werts mit einem optionalen ohne Klammern) müssen Sie möglicherweise eine geschweifter Klammer in einer Zeile aufbewahren:</span><span class="sxs-lookup"><span data-stu-id="999ef-234">In some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:</span></span>

```fsharp
type S = { F1: int; F2: string }
type State = { Foo: S option }

let state = { Foo = Some { F1 = 1; F2 = "Hello" } }
let newState =
    {
        state with
            Foo =
                Some {
                    F1 = 0
                    F2 = ""
                }
    }
```

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="999ef-235">Formatieren von Listen und Arrays</span><span class="sxs-lookup"><span data-stu-id="999ef-235">Formatting lists and arrays</span></span>

<span data-ttu-id="999ef-236">Schreiben Sie `x :: l` mit Leerzeichen um den `::` Operator ( `::` ist ein Infix-Operator, der daher von Leerzeichen umgeben ist).</span><span class="sxs-lookup"><span data-stu-id="999ef-236">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="999ef-237">Listen und Arrays, die in einer einzelnen Zeile deklariert werden, müssen nach der öffnenden eckige Klammer und vor der schließenden Klammer ein Leerzeichen enthalten:</span><span class="sxs-lookup"><span data-stu-id="999ef-237">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="999ef-238">Verwenden Sie immer mindestens ein Leerzeichen zwischen zwei unterschiedlichen geschweifter Klammern ähnlichen Operatoren.</span><span class="sxs-lookup"><span data-stu-id="999ef-238">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="999ef-239">Belassen Sie z. b. ein Leerzeichen zwischen einem `[` und einem `{` .</span><span class="sxs-lookup"><span data-stu-id="999ef-239">For example, leave a space between a `[` and a `{`.</span></span>

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

<span data-ttu-id="999ef-240">Die gleiche Richtlinie gilt für Listen oder Arrays von Tupeln.</span><span class="sxs-lookup"><span data-stu-id="999ef-240">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="999ef-241">Listen und Arrays, die auf mehrere Zeilen aufgeteilt werden, folgen einer ähnlichen Regel wie Datensätze:</span><span class="sxs-lookup"><span data-stu-id="999ef-241">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

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

<span data-ttu-id="999ef-242">Ebenso wie bei Datensätzen wird durch das Deklarieren der öffnenden und schließenden Klammern in der eigenen Zeile das Verschieben von Code und das Weiterleiten in Funktionen vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="999ef-242">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

<span data-ttu-id="999ef-243">Wenn Sie Arrays und Listen Programm gesteuert generieren, bevorzugen Sie, `->` `do ... yield` Wenn ein Wert immer generiert wird:</span><span class="sxs-lookup"><span data-stu-id="999ef-243">When generating arrays and lists programmatically, prefer `->` over `do ... yield` when a value is always generated:</span></span>

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x * x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x * x ]
```

<span data-ttu-id="999ef-244">Ältere Versionen der F #-Sprache erforderten die Angabe von `yield` in Situationen, in denen Daten bedingt generiert werden können, oder es können aufeinanderfolgende Ausdrücke ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="999ef-244">Older versions of the F# language required specifying `yield` in situations where data may be generated conditionally, or there may be consecutive expressions to be evaluated.</span></span> <span data-ttu-id="999ef-245">Sie sollten diese Schlüsselwörter weglassen, `yield` es sei denn, Sie müssen mit einer älteren F #-Sprachversion kompilieren:</span><span class="sxs-lookup"><span data-stu-id="999ef-245">Prefer omitting these `yield` keywords unless you must compile with an older F# language version:</span></span>

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

<span data-ttu-id="999ef-246">In einigen Fällen kann die Lesbarkeit von unter `do...yield` stützen.</span><span class="sxs-lookup"><span data-stu-id="999ef-246">In some cases, `do...yield` may aid in readability.</span></span> <span data-ttu-id="999ef-247">Diese Fälle, aber subjektiv, sollten berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="999ef-247">These cases, though subjective, should be taken into consideration.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="999ef-248">Formatieren von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="999ef-248">Formatting if expressions</span></span>

<span data-ttu-id="999ef-249">Der Einzug von Bedingungen hängt von der Größe und Komplexität der Ausdrücke ab, die Sie bilden.</span><span class="sxs-lookup"><span data-stu-id="999ef-249">Indentation of conditionals depends on the size and complexity of the expressions that make them up.</span></span>
<span data-ttu-id="999ef-250">Schreiben Sie Sie in einer Zeile, wenn:</span><span class="sxs-lookup"><span data-stu-id="999ef-250">Write them on one line when:</span></span>

- <span data-ttu-id="999ef-251">`cond`, `e1` und `e2` sind kurz</span><span class="sxs-lookup"><span data-stu-id="999ef-251">`cond`, `e1`, and `e2` are short</span></span>
- <span data-ttu-id="999ef-252">`e1` und `e2` sind keine `if/then/else` Ausdrücke selbst.</span><span class="sxs-lookup"><span data-stu-id="999ef-252">`e1` and `e2` are not `if/then/else` expressions themselves.</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="999ef-253">Wenn einer der Ausdrücke mehrzeilige oder Ausdrücke ist `if/then/else` .</span><span class="sxs-lookup"><span data-stu-id="999ef-253">If any of the expressions are multi-line or `if/then/else` expressions.</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="999ef-254">Mehrere Bedingungen mit `elif` und `else` werden im gleichen Gültigkeitsbereich wie das `if` eingerückt, wenn Sie den Regeln der einzeiligen `if/then/else` Ausdrücke folgen.</span><span class="sxs-lookup"><span data-stu-id="999ef-254">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if` when they follow the rules of the one line `if/then/else` expressions.</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

<span data-ttu-id="999ef-255">Wenn eine der Bedingungen oder Ausdrücke mehrzeilige Bedingungen hat, ist der gesamte `if/then/else` Ausdruck mehrzeilige Zeilen:</span><span class="sxs-lookup"><span data-stu-id="999ef-255">If any of the conditions or expressions is multi-line, the entire `if/then/else` expression is multi-line:</span></span>

```fsharp
if cond1 then
    e1
elif cond2 then
    e2
elif cond3 then
    e3
else
    e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="999ef-256">Musterabgleichkonstrukte</span><span class="sxs-lookup"><span data-stu-id="999ef-256">Pattern matching constructs</span></span>

<span data-ttu-id="999ef-257">Verwenden Sie eine `|` for each-Klausel einer Entsprechung ohne Einzug.</span><span class="sxs-lookup"><span data-stu-id="999ef-257">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="999ef-258">Wenn der Ausdruck kurz ist, können Sie die Verwendung einer einzelnen Zeile in Erwägung gezogen, wenn jeder Teil Ausdruck ebenfalls einfach ist.</span><span class="sxs-lookup"><span data-stu-id="999ef-258">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

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

<span data-ttu-id="999ef-259">Wenn der Ausdruck auf der rechten Seite des Musters für den Musterabgleich zu groß ist, verschieben Sie ihn in die folgende Zeile, wobei Sie einen Schritt aus der eingezogen haben `match` / `|` .</span><span class="sxs-lookup"><span data-stu-id="999ef-259">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="999ef-260">Der Musterabgleich von anonymen Funktionen, beginnend mit `function` , sollte in der Regel nicht zu weit einziehen.</span><span class="sxs-lookup"><span data-stu-id="999ef-260">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="999ef-261">Beispielsweise ist es in Ordnung, einen Bereich wie folgt einzuschließen:</span><span class="sxs-lookup"><span data-stu-id="999ef-261">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map
    (function
        | Abs(x, body) -> 1 + sizeLambda 0 body
        | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
        | Var v -> 1)
```

<span data-ttu-id="999ef-262">Der Musterabgleich in Funktionen `let` , die von oder definiert `let rec` werden, sollte nach dem Start von vier Leerzeichen eingezogen werden `let` , auch wenn das- `function` Schlüsselwort verwendet wird</span><span class="sxs-lookup"><span data-stu-id="999ef-262">Pattern matching in functions defined by `let` or `let rec` should be indented four spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="999ef-263">Es wird nicht empfohlen, Pfeile auszurichten.</span><span class="sxs-lookup"><span data-stu-id="999ef-263">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="999ef-264">Formatieren von try/with-Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="999ef-264">Formatting try/with expressions</span></span>

<span data-ttu-id="999ef-265">Der Musterabgleich für den Ausnahmetyp sollte auf der gleichen Ebene wie eingerückt werden `with` .</span><span class="sxs-lookup"><span data-stu-id="999ef-265">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

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

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="999ef-266">Formatieren der Funktionsparameter Anwendung</span><span class="sxs-lookup"><span data-stu-id="999ef-266">Formatting function parameter application</span></span>

<span data-ttu-id="999ef-267">Im Allgemeinen werden die meisten Argumente in derselben Zeile bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="999ef-267">In general, most arguments are provided on the same line:</span></span>

```fsharp
let x = sprintf "\t%s - %i\n\r" x.IngredientName x.Quantity

let printListWithOffset a list1 =
    List.iter (fun elem -> printfn $"%d{a + elem}") list1
```

<span data-ttu-id="999ef-268">Wenn Pipelines betroffen sind, ist das gleiche in der Regel auch true, wenn eine Curry-Funktion als Argument in derselben Zeile angewendet wird:</span><span class="sxs-lookup"><span data-stu-id="999ef-268">When pipelines are concerned, the same is typically also true, where a curried function is applied as an argument on the same line:</span></span>

```
let printListWithOffsetPiped a list1 =
    list1
    |> List.iter (fun elem -> printfn $"%d{a + elem}")
```

<span data-ttu-id="999ef-269">Möglicherweise möchten Sie jedoch Argumente an eine Funktion in einer neuen Zeile übergeben, um die Lesbarkeit zu ermöglichen, oder weil die Liste der Argumente oder der Argument Namen zu lang ist.</span><span class="sxs-lookup"><span data-stu-id="999ef-269">However, you may wish to pass arguments to a function on a new line, as a matter of readability or because the list of arguments or the argument names are too long.</span></span> <span data-ttu-id="999ef-270">Einziehen Sie in diesem Fall mit einem Bereich:</span><span class="sxs-lookup"><span data-stu-id="999ef-270">In that case, indent with one scope:</span></span>

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

<span data-ttu-id="999ef-271">Bei Lambda-Ausdrücken sollten Sie auch erwägen, den Text eines Lambda-Ausdrucks in einer neuen Zeile einzuordnen, die um einen Bereich eingezogen ist, wenn er lang genug ist:</span><span class="sxs-lookup"><span data-stu-id="999ef-271">For lambda expressions, you may also want to consider placing the body of a lambda expression on a new line, indented by one scope, if it is long enough:</span></span>

```fsharp
let printListWithOffset a list1 =
    List.iter
        (fun elem ->
            printfn $"%d{a + elem}")
        list1

let printListWithOffsetPiped a list1 =
    list1
    |> List.iter
        (fun elem ->
            printfn $"%d{a + elem}")
```

<span data-ttu-id="999ef-272">Wenn der Text eines Lambda-Ausdrucks mehrere Zeilen lang ist, sollten Sie ihn in eine lokal positionsierte Funktion umgestalten.</span><span class="sxs-lookup"><span data-stu-id="999ef-272">If the body of a lambda expression is multiple lines long, you should consider refactoring it into a locally-scoped function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="999ef-273">Formatieren von Infixoperatoren</span><span class="sxs-lookup"><span data-stu-id="999ef-273">Formatting infix operators</span></span>

<span data-ttu-id="999ef-274">Getrennte Operatoren nach Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="999ef-274">Separate operators by spaces.</span></span> <span data-ttu-id="999ef-275">Offensichtliche Ausnahmen zu dieser Regel sind die `!` `.` Operatoren und.</span><span class="sxs-lookup"><span data-stu-id="999ef-275">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="999ef-276">Infix-Ausdrücke sind in der gleichen Spalte zu finden:</span><span class="sxs-lookup"><span data-stu-id="999ef-276">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators-or-mutable-assignments"></a><span data-ttu-id="999ef-277">Formatieren von Pipeline-Operatoren oder änderbaren Zuweisungen</span><span class="sxs-lookup"><span data-stu-id="999ef-277">Formatting pipeline operators or mutable assignments</span></span>

<span data-ttu-id="999ef-278">Pipeline `|>` Operatoren sollten unterhalb der Ausdrücke liegen, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="999ef-278">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

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

// Not OK either
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
               |> List.ofArray
               |> List.map (fun assm -> assm.GetTypes())
               |> Array.concat
               |> List.ofArray
               |> List.map (fun t -> t.GetMethods())
               |> Array.concat
```

<span data-ttu-id="999ef-279">Dies gilt auch für änderbare Setter:</span><span class="sxs-lookup"><span data-stu-id="999ef-279">This also applies to mutable setters:</span></span>

```fsharp
// Preferred approach
ctx.Response.Headers.[HeaderNames.ContentType] <-
    Constants.jsonApiMediaType |> StringValues
ctx.Response.Headers.[HeaderNames.ContentLength] <-
    bytes.Length |> string |> StringValues

// Not OK
ctx.Response.Headers.[HeaderNames.ContentType] <- Constants.jsonApiMediaType
                                                  |> StringValues
ctx.Response.Headers.[HeaderNames.ContentLength] <- bytes.Length
                                                    |> string
                                                    |> StringValues
```

### <a name="formatting-modules"></a><span data-ttu-id="999ef-280">Formatieren von Modulen</span><span class="sxs-lookup"><span data-stu-id="999ef-280">Formatting modules</span></span>

<span data-ttu-id="999ef-281">Der Code in einem lokalen Modul muss relativ zum Modul eingezogen werden, aber der Code in einem Modul der obersten Ebene sollte nicht eingezogen werden.</span><span class="sxs-lookup"><span data-stu-id="999ef-281">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="999ef-282">Namespace Elemente müssen nicht eingezogen werden.</span><span class="sxs-lookup"><span data-stu-id="999ef-282">Namespace elements do not have to be indented.</span></span>

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a * a + b * b

module A2 =
    let function2 a b = a * a - b * b
```

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="999ef-283">Formatieren von Objekt Ausdrücken und Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="999ef-283">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="999ef-284">Objekt Ausdrücke und Schnittstellen sollten auf die gleiche Weise ausgerichtet werden `member` , wenn Sie nach vier Leerzeichen eingezogen werden.</span><span class="sxs-lookup"><span data-stu-id="999ef-284">Object expressions and interfaces should be aligned in the same way with `member` being indented after four spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="999ef-285">Formatieren von Leerzeichen in Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="999ef-285">Formatting white space in expressions</span></span>

<span data-ttu-id="999ef-286">Vermeiden Sie überflüssige Leerzeichen in F #-Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="999ef-286">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="999ef-287">Benannte Argumente sollten auch keinen Platz enthalten, der das umgibt `=` :</span><span class="sxs-lookup"><span data-stu-id="999ef-287">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

### <a name="formatting-constructors-static-members-and-member-invocations"></a><span data-ttu-id="999ef-288">Formatierungskonstruktoren, statische Member und Element Aufrufe</span><span class="sxs-lookup"><span data-stu-id="999ef-288">Formatting constructors, static members, and member invocations</span></span>

<span data-ttu-id="999ef-289">Wenn der Ausdruck kurz ist, trennen Sie Argumente mit Leerzeichen, und bewahren Sie Sie in einer Zeile auf.</span><span class="sxs-lookup"><span data-stu-id="999ef-289">If the expression is short, separate arguments with spaces and keep it in one line.</span></span>

```fsharp
let person = new Person(a1, a2)

let myRegexMatch = Regex.Match(input, regex)

let untypedRes = checker.ParseFile(file, source, opts)
```

<span data-ttu-id="999ef-290">Wenn der Ausdruck lang ist, verwenden Sie Zeilenumbrüche und einen Bereich, anstatt in die eckige Klammer einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="999ef-290">If the expression is long, use newlines and indent one scope, rather than indenting to the bracket.</span></span>

```fsharp
let person =
    new Person(
        argument1,
        argument2
    )

let myRegexMatch =
    Regex.Match(
        "my longer input string with some interesting content in it",
        "myRegexPattern"
    )

let untypedRes =
    checker.ParseFile(
        fileName,
        sourceText,
        parsingOptionsWithDefines
    )
```

## <a name="formatting-attributes"></a><span data-ttu-id="999ef-291">Formatieren von Attributen</span><span class="sxs-lookup"><span data-stu-id="999ef-291">Formatting attributes</span></span>

<span data-ttu-id="999ef-292">[Attribute](../language-reference/attributes.md) werden über einem Konstrukt platziert:</span><span class="sxs-lookup"><span data-stu-id="999ef-292">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

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

<span data-ttu-id="999ef-293">Sie sollten nach jeder XML-Dokumentation gehen:</span><span class="sxs-lookup"><span data-stu-id="999ef-293">They should go after any XML documentation:</span></span>

```fsharp
/// Module with some things in it.
[<RequireQualifiedAccess>]
module M =
    let f x = x
```

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="999ef-294">Formatieren von Attributen für Parameter</span><span class="sxs-lookup"><span data-stu-id="999ef-294">Formatting attributes on parameters</span></span>

<span data-ttu-id="999ef-295">Attribute können auch in Parameter eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="999ef-295">Attributes can also be placed on parameters.</span></span> <span data-ttu-id="999ef-296">Platzieren Sie in diesem Fall die Zeile in derselben Zeile wie der-Parameter und vor dem Namen:</span><span class="sxs-lookup"><span data-stu-id="999ef-296">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="999ef-297">Formatieren mehrerer Attribute</span><span class="sxs-lookup"><span data-stu-id="999ef-297">Formatting multiple attributes</span></span>

<span data-ttu-id="999ef-298">Wenn mehrere Attribute auf ein Konstrukt angewendet werden, bei dem es sich nicht um einen Parameter handelt, sollten Sie so platziert werden, dass ein Attribut pro Zeile vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="999ef-298">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="999ef-299">Wenn Sie auf einen Parameter angewendet werden, müssen Sie sich in derselben Zeile befinden und durch ein Trennzeichen getrennt werden `;` .</span><span class="sxs-lookup"><span data-stu-id="999ef-299">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="999ef-300">Formatieren von literalen</span><span class="sxs-lookup"><span data-stu-id="999ef-300">Formatting literals</span></span>

<span data-ttu-id="999ef-301">[F #-Literale](../language-reference/literals.md) , die das-Attribut verwenden, `Literal` sollten das-Attribut in einer eigenen Zeile platzieren und die Verwendung von PascalCase verwenden:</span><span class="sxs-lookup"><span data-stu-id="999ef-301">[F# literals](../language-reference/literals.md) using the `Literal` attribute should place the attribute on its own line and use PascalCase naming:</span></span>

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="999ef-302">Vermeiden Sie das Platzieren des Attributs in derselben Zeile wie den Wert.</span><span class="sxs-lookup"><span data-stu-id="999ef-302">Avoid placing the attribute on the same line as the value.</span></span>

## <a name="formatting-computation-expression-operations"></a><span data-ttu-id="999ef-303">Formatieren von Ausdrucks Operationen für Berechnungen</span><span class="sxs-lookup"><span data-stu-id="999ef-303">Formatting computation expression operations</span></span>

<span data-ttu-id="999ef-304">Beim Erstellen von benutzerdefinierten Vorgängen für [Berechnungs Ausdrücke](../language-reference/computation-expressions.md)empfiehlt es sich, die Namensgebung in CamelCase zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="999ef-304">When creating custom operations for [computation expressions](../language-reference/computation-expressions.md), it is recommended to use camelCase naming:</span></span>

```fsharp
type MathBuilder () =
    member _.Yield _ = 0

    [<CustomOperation("addOne")>]
    member _.AddOne (state: int) =
        state + 1

    [<CustomOperation("subtractOne")>]
    member _.SubtractOne (state: int) =
        state - 1

    [<CustomOperation("divideBy")>]
    member _.DivideBy (state: int, divisor: int) =
        state / divisor

    [<CustomOperation("multiplyBy")>]
    member _.MultiplyBy (state: int, factor: int) =
        state * factor

let math = MathBuilder()

// 10
let myNumber =
    math {
        addOne
        addOne
        addOne

        subtractOne

        divideBy 2

        multiplyBy 10
    }
```

<span data-ttu-id="999ef-305">Die zu modellierende Domäne sollte letztendlich die Benennungs Konvention steuern.</span><span class="sxs-lookup"><span data-stu-id="999ef-305">The domain that's being modeled should ultimately drive the naming convention.</span></span>
<span data-ttu-id="999ef-306">Wenn es idiomatisch ist, eine andere Konvention zu verwenden, sollte diese Konvention stattdessen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="999ef-306">If it is idiomatic to use a different convention, that convention should be used instead.</span></span>
