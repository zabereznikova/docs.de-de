---
title: F#-Code, die Formatierung von Richtlinien
description: Erfahren Sie Richtlinien zur Formatierung von F#-Code ein.
ms.date: 05/14/2018
ms.openlocfilehash: 6c8e4059fd4bf1e7450118a6df02609217c4f4db
ms.sourcegitcommit: 2ad7d06f4f469b5d8a5280ac0e0289a81867fc8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2018
ms.locfileid: "35231505"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="5e8a6-103">F#-Code, die Formatierung von Richtlinien</span><span class="sxs-lookup"><span data-stu-id="5e8a6-103">F# code formatting guidelines</span></span>

<span data-ttu-id="5e8a6-104">Dieser Artikel bietet Richtlinien zum Code formatieren, sodass der f#-Code ist:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="5e8a6-105">Im Allgemeinen als besser lesbar angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="5e8a6-106">In Übereinstimmung mit den Konventionen, die durch die Tools in Visual Studio und andere Editoren Formatierung angewendet wird</span><span class="sxs-lookup"><span data-stu-id="5e8a6-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="5e8a6-107">Ähnlich wie bei anderen Code online</span><span class="sxs-lookup"><span data-stu-id="5e8a6-107">Similar to other code online</span></span>

<span data-ttu-id="5e8a6-108">Diese Richtlinien basieren auf [eine umfassende Anleitung zum F#-Formatierung Konventionen](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) von [Anh Mist Phan](https://github.com/dungpa).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="5e8a6-109">Allgemeine Regeln für den Einzug</span><span class="sxs-lookup"><span data-stu-id="5e8a6-109">General rules for indentation</span></span>

<span data-ttu-id="5e8a6-110">F#-signifikanten Leerräume wird standardmäßig verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-110">F# uses significant whitespace by default.</span></span> <span data-ttu-id="5e8a6-111">Die folgenden Richtlinien sollen bieten eine Anleitung, wie einige Herausforderungen Grenzen gesetzt sind, die kann dies zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="5e8a6-112">Durch Leerzeichen getrennt werden</span><span class="sxs-lookup"><span data-stu-id="5e8a6-112">Using spaces</span></span>

<span data-ttu-id="5e8a6-113">Wenn Einzug erforderlich ist, müssen Sie Leerzeichen, nicht-Registerkarten verwenden.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="5e8a6-114">Mindestens eine Leerstelle ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-114">At least one space is required.</span></span> <span data-ttu-id="5e8a6-115">Ihre Organisation kann Codierungsstandards zum Angeben der Anzahl von Leerzeichen zum einrücken verwendet erstellen; zwei, drei oder vier Speicherplätzen Einzugsebene an jede Einzugsebene entspricht den Erwartungen.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="5e8a6-116">**Es wird empfohlen, 4 Leerzeichen pro Einzug.**</span><span class="sxs-lookup"><span data-stu-id="5e8a6-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="5e8a6-117">Dies bedeutet, dass der Einzug der Programme eine subjektive Angelegenheit ist.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="5e8a6-118">Varianten sind in Ordnung, jedoch ist die erste Regel, die Sie befolgen sollten *Konsistenz des Einzugs*.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="5e8a6-119">Wählen Sie ein allgemein anerkannten Format des Einzugs und systematisch in der gesamten Codebasis verwenden.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-blank-lines"></a><span data-ttu-id="5e8a6-120">Formatieren von Leerzeilen</span><span class="sxs-lookup"><span data-stu-id="5e8a6-120">Formatting blank lines</span></span>

* <span data-ttu-id="5e8a6-121">Separate auf oberster Ebene Funktion und der Klassendefinition mit zwei leere Zeilen.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-121">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="5e8a6-122">Methodendefinitionen innerhalb einer Klasse werden durch eine einzelne Leerzeile getrennt.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-122">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="5e8a6-123">Zusätzliche leere Zeilen können (nur selten) in separate Gruppen verwandter Funktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-123">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="5e8a6-124">Leerzeilen können zwischen einer Reihe von verwandten Einzeiler (z. B. ein Satz von dummy-Implementierungen) ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-124">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="5e8a6-125">Verwenden Sie leere Zeilen nur selten, in Funktionen, um logische Abschnitte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-125">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="5e8a6-126">Formatieren von Kommentaren</span><span class="sxs-lookup"><span data-stu-id="5e8a6-126">Formatting comments</span></span>

<span data-ttu-id="5e8a6-127">Ziehen Sie in der Regel mehrere doppelten Schrägstrich Kommentare ML-Stil Blocks-Kommentaren.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-127">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="5e8a6-128">Inline-Kommentare, sollte der erste Buchstabe groß geschrieben.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-128">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="5e8a6-129">Namenskonventionen </span><span class="sxs-lookup"><span data-stu-id="5e8a6-129">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="5e8a6-130">Verwenden Sie camelCase ändern möchten, für gebundene Klasse, Ausdruck auch Muster gebunden Werte und Funktionen</span><span class="sxs-lookup"><span data-stu-id="5e8a6-130">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="5e8a6-131">Es kommt häufig vor und akzeptierte F#-Format, das camelCase ändern möchten nach allen Namen gebunden, als lokale Variablen oder Muster Matches "und" Funktionsdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-131">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="5e8a6-132">Lokalen gebundenen Funktionen in Klassen verwenden zudem camelCase ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-132">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="5e8a6-133">Verwenden Sie für öffentliche Funktionen Modul datengebundenen camelCase ändern möchten</span><span class="sxs-lookup"><span data-stu-id="5e8a6-133">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="5e8a6-134">Wenn ein Modul-gebundenen Funktionen eine öffentliche API gehört, sollten sie camelCase ändern möchten verwenden:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-134">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="5e8a6-135">Verwenden Sie camelCase ändern möchten, für die interne und private Modul gebundenen Werte und Funktionen</span><span class="sxs-lookup"><span data-stu-id="5e8a6-135">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="5e8a6-136">Verwenden Sie camelCase ändern möchten, für die private Modul gebundenen Werte, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-136">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="5e8a6-137">Ad-hoc-Funktionen in Skripts</span><span class="sxs-lookup"><span data-stu-id="5e8a6-137">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="5e8a6-138">Werte, aus denen die interne Implementierung der ein Modul oder einen Typ</span><span class="sxs-lookup"><span data-stu-id="5e8a6-138">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="5e8a6-139">Verwenden Sie camelCase ändern möchten, für Parameter</span><span class="sxs-lookup"><span data-stu-id="5e8a6-139">Use camelCase for parameters</span></span>

<span data-ttu-id="5e8a6-140">Alle Parameter sollten camelCase ändern möchten, in Übereinstimmung mit den Konventionen zur Namensgebung von .NET verwenden.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-140">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="5e8a6-141">Verwenden Sie "PascalCase" für Module</span><span class="sxs-lookup"><span data-stu-id="5e8a6-141">Use PascalCase for modules</span></span>

<span data-ttu-id="5e8a6-142">Alle Module (auf der obersten Ebene, interne, private, geschachtelte) sollten "PascalCase" verwenden.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-142">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="5e8a6-143">Verwenden Sie "PascalCase" für Deklarationen von Typen, Member und Beschriftungen</span><span class="sxs-lookup"><span data-stu-id="5e8a6-143">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="5e8a6-144">Klassen, Schnittstellen, Strukturen, Enumerationen, Delegaten, Datensätze und Unterscheidungs-Unions sollten alle mit "PascalCase" benannt werden.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-144">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="5e8a6-145">Außerdem sollten die Elemente innerhalb der Typen und Bezeichnungen für Datensätze und Unterscheidungs-Unions "PascalCase" verwenden.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-145">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="5e8a6-146">Verwenden Sie "PascalCase" Konstrukte für .NET</span><span class="sxs-lookup"><span data-stu-id="5e8a6-146">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="5e8a6-147">Namespaces, Ausnahmen, Ereignisse und Projekt /`.dll` Namen sollte auch "PascalCase" verwenden.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-147">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="5e8a6-148">Nicht nur dadurch, Verbrauch aus anderen .NET-Sprachen natürlicher für Consumer können, ist auch konsistent mit dem .NET Benennungskonventionen, die Sie stoßen können.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-148">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="5e8a6-149">Vermeiden Sie Unterstriche im Namen</span><span class="sxs-lookup"><span data-stu-id="5e8a6-149">Avoid underscores in names</span></span>

<span data-ttu-id="5e8a6-150">In der Vergangenheit haben einige f#-Bibliotheken Unterstriche im Namen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-150">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="5e8a6-151">Allerdings wird dies häufig nicht mehr akzeptiert, da mit den Benennungskonventionen für .NET Konflikt.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-151">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="5e8a6-152">Dies bedeutet, dass einige f#-Programmierer verwenden Sie Unterstriche stark, teilweise aus Verlaufsgründen und Fehlertoleranz zu gewährleisten und Hinsicht ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-152">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="5e8a6-153">Denken Sie jedoch, dass die Formatvorlage häufig von anderen disliked ist, die Wahl, ob Sie, ob es verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-153">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="5e8a6-154">Einige Ausnahmen enthält Interoperabilität mit systemeigenen Komponenten, in denen Unterstriche üblich sind.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-154">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="5e8a6-155">Verwenden Sie die standard-Operatoren [F#]</span><span class="sxs-lookup"><span data-stu-id="5e8a6-155">Use standard F# operators</span></span>

<span data-ttu-id="5e8a6-156">Die folgenden Operatoren werden in der f#-Standardbibliothek definiert und sollte verwendet werden, statt zu Entsprechungen definieren.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-156">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="5e8a6-157">Mithilfe dieser Operatoren wird empfohlen, wie sie Code besser lesbar und idiomatische ist ist.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-157">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="5e8a6-158">Entwickler mit einem Hintergrund mit OCaml oder anderen funktionalen Programmierung Sprache möglicherweise mit anderen Idiome vertraut sein.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-158">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="5e8a6-159">Die folgende Liste fasst die empfohlene F#-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-159">The following list summarizes the recommended F# operators.</span></span>

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="5e8a6-160">Verwenden Sie die Präfix-Syntax für Generika (`Foo<T>`) aufrufanweisung Postfix-Syntax (`T Foo`)</span><span class="sxs-lookup"><span data-stu-id="5e8a6-160">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="5e8a6-161">F#-erbt sowohl den Postfix ML Stil für die Benennung von generischer Typen (z. B. `int list`) sowie das Präfix .NET Stil (z. B. `list<int>`).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-161">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="5e8a6-162">Bevorzugen Sie .NET Formatvorlage, mit Ausnahme von vier bestimmte Typen:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-162">Prefer the .NET style, except for four specific types:</span></span>

1. <span data-ttu-id="5e8a6-163">Verwenden Sie für f#-Listen, die Postfix-Form: `int list` statt `list<int>`.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-163">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="5e8a6-164">Verwenden Sie für f#-Optionen, die Postfix-Form: `int option` statt `option<int>`.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-164">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="5e8a6-165">Verwenden Sie für f#-Arrays, die syntaktischen Namen `int[]` statt `int array` oder `array<int>`.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-165">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
4. <span data-ttu-id="5e8a6-166">Verwenden Sie Referenzzellen, `int ref` statt `ref<int>` oder `Ref<int>`.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-166">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="5e8a6-167">Verwenden Sie für alle anderen Datentypen die Präfix-Form.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-167">For all other types, use the prefix form.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="5e8a6-168">Formatieren von Unterscheidungs-union-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="5e8a6-168">Formatting discriminated union declarations</span></span>

<span data-ttu-id="5e8a6-169">Ziehen Sie ein `|` in Typdefinition durch 4 Leerzeichen:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-169">Indent `|` in type definition by 4 spaces:</span></span>

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

<span data-ttu-id="5e8a6-170">Instanziierte Unterscheidungs-Unions, die auf mehrere Zeilen aufgeteilt sollte enthaltenen Daten einen neuen Bereich mit Einzügen vermitteln:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-170">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="5e8a6-171">Die schließende Klammer in einer neuen Zeile ist auch möglich:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-171">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-tuples"></a><span data-ttu-id="5e8a6-172">Formatieren von Tupeln</span><span class="sxs-lookup"><span data-stu-id="5e8a6-172">Formatting tuples</span></span>

<span data-ttu-id="5e8a6-173">Eine Instanziierung der Tupel in Klammern werden sollte und der begrenzenden Kommas innerhalb sollte darauf folgen durch ein Leerzeichen, z. B.: `(1, 2)`, `(x, y, z)`.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-173">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="5e8a6-174">Eine häufig akzeptierte Ausnahme besteht darin, Klammern in einem Mustervergleich von Tupeln auszuschließen:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-174">A commonly accepted exception is to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring

match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-records"></a><span data-ttu-id="5e8a6-175">Formatieren von Datensätzen</span><span class="sxs-lookup"><span data-stu-id="5e8a6-175">Formatting records</span></span>

<span data-ttu-id="5e8a6-176">Kurze Datensätze können in einer Zeile geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-176">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="5e8a6-177">Datensätze, die länger sind, sollten neue Zeilen für Bezeichnungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-177">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="5e8a6-178">Das öffnende-Token auf der gleichen Zeile und das schließende-Token in einer neuen Zeile platziert wird auch keine Probleme:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-178">Placing the opening token on the same line and the closing token on a new line is also fine:</span></span>

```fsharp
let rainbow = {
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
```

<span data-ttu-id="5e8a6-179">Es gelten die gleichen Regeln für Liste und Array-Elemente.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-179">The same rules apply for list and array elements.</span></span>

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="5e8a6-180">Formatieren von Listen und arrays</span><span class="sxs-lookup"><span data-stu-id="5e8a6-180">Formatting lists and arrays</span></span>

<span data-ttu-id="5e8a6-181">Schreiben von `x :: l` mit Leerzeichen der `::` Operator (`::` ist ein Infix-Operator, daher Leerzeichen enthaltender) und `[1; 2; 3]` (`;` ist ein Trennzeichen, daher gefolgt von einem Leerzeichen).</span><span class="sxs-lookup"><span data-stu-id="5e8a6-181">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces) and `[1; 2; 3]` (`;` is a delimiter, hence followed by a space).</span></span>

<span data-ttu-id="5e8a6-182">Verwenden Sie immer mindestens ein Leerzeichen zwischen zwei unterschiedlichen geschweifte Klammer-ähnliche Operatoren ein.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-182">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="5e8a6-183">Lassen Sie z. B. ein Leerzeichen zwischen einem `[` und ein `{`.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-183">For example, leave a space between a `[` and a `{`.</span></span>

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

<span data-ttu-id="5e8a6-184">Listen und Arrays, die auf mehrere Zeilen aufgeteilt führen Sie eine ähnliche Regel, wie Datensätze:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-184">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

```fsharp
let pascalsTriangle = [|
    [|1|]
    [|1; 1|]
    [|1; 2; 1|]
    [|1; 3; 3; 1|]
    [|1; 4; 6; 4; 1|]
    [|1; 5; 10; 10; 5; 1|]
    [|1; 6; 15; 20; 15; 6; 1|]
    [|1; 7; 21; 35; 35; 21; 7; 1|]
    [|1; 8; 28; 56; 70; 56; 28; 8; 1|]
|]
```

## <a name="formatting-if-expressions"></a><span data-ttu-id="5e8a6-185">Formatierung If Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="5e8a6-185">Formatting if expressions</span></span>

<span data-ttu-id="5e8a6-186">Einzug des Konditionelle Abschnitte hängt die Größen von Ausdrücken, die sie bilden.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-186">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="5e8a6-187">Wenn `cond`, `e1` und `e2` "klein", werden sie einfach auf eine Zeile zu schreiben:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-187">If `cond`, `e1` and `e2` are small, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="5e8a6-188">Wenn `e1` und `cond` "klein", sind aber `e2` groß ist:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-188">If `e1` and `cond` are small, but `e2` is large:</span></span>

```fsharp
if cond then e1
else
    e2
```

<span data-ttu-id="5e8a6-189">Wenn `e1` und `cond` Groß und `e2` ist klein:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-189">If `e1` and `cond` are large and `e2` is small:</span></span>

```fsharp
if cond then
    e1
else e2
```

<span data-ttu-id="5e8a6-190">Wenn alle Ausdrücke groß sind:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-190">If all the expressions are large:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="5e8a6-191">Mehrere Bedingungen mit `elif` und `else` eingezogen im gleichen Bereich wie die `if`:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-191">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="5e8a6-192">Übereinstimmende Muster-Konstrukte</span><span class="sxs-lookup"><span data-stu-id="5e8a6-192">Pattern matching constructs</span></span>

<span data-ttu-id="5e8a6-193">Verwenden einer `|` für jede Klausel einer Übereinstimmung ohne Einzug.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-193">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="5e8a6-194">Wenn der Ausdruck kurz ist, können Sie erwägen, eine einzelne Zeile verwenden, wenn jede Teilausdruck auch einfach ist.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-194">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> _
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> _
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

<span data-ttu-id="5e8a6-195">Wenn der Ausdruck auf der rechten Seite der Musterabgleich Pfeil zu groß ist, verschieben Sie sie auf der folgenden Zeile eingezogen einen Schritt aus der `match` / `|`.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-195">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="5e8a6-196">Anonyme Funktionen, die gestartet wird, indem den Mustervergleich `function`, sollte im Allgemeinen nicht Einzug zu weit.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-196">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="5e8a6-197">Beispielsweise ist das Festlegen von Einzügen für einen Bereich wie folgt Ordnung:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-197">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="5e8a6-198">Mustervergleich in Funktionen, die definiert, indem `let` oder `let rec` muss eingezogene 4 Leerzeichen nach dem Starten der `let`, selbst wenn `function` -Schlüsselwort wird verwendet:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-198">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="5e8a6-199">Wir empfehlen nicht Pfeile ausrichten.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-199">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="5e8a6-200">Formatierung Try / mit-Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="5e8a6-200">Formatting try/with expressions</span></span>

<span data-ttu-id="5e8a6-201">Einen Mustervergleich für den Ausnahmetyp sollte auf der gleichen Ebene wie eingezogen werden `with`.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-201">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

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

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="5e8a6-202">Formatieren von funktionsanwendung-parameter</span><span class="sxs-lookup"><span data-stu-id="5e8a6-202">Formatting function parameter application</span></span>

<span data-ttu-id="5e8a6-203">Im Allgemeinen erfolgt die meisten funktionsanwendung Parameter in derselben Zeile.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-203">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="5e8a6-204">Wenn Sie Parameter an eine Funktion in einer neuen Zeile anwenden möchten, Rücken Sie diese durch einen Bereich.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-204">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

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

<span data-ttu-id="5e8a6-205">Dieselben Richtlinien werden für Lambda-Ausdrücke als Funktionsargumente angewendet.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-205">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="5e8a6-206">Wenn der Text eines Lambda-Ausdrucks, der Text einer anderen Zeile, die durch einen Bereich mit Einzug dargestellt werden kann</span><span class="sxs-lookup"><span data-stu-id="5e8a6-206">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

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

<span data-ttu-id="5e8a6-207">Allerdings ist der Text eines Lambda-Ausdrucks auf mehr als eine Zeile, sollten Sie ihn in eine separate Funktion factoring anstatt eine mehrzeilige-Konstrukt, das als einzelnes Argument für eine Funktion übernommen.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-207">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="5e8a6-208">Formatieren von Infixoperatoren</span><span class="sxs-lookup"><span data-stu-id="5e8a6-208">Formatting infix operators</span></span>

<span data-ttu-id="5e8a6-209">Separate Operatoren durch Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-209">Separate operators by spaces.</span></span> <span data-ttu-id="5e8a6-210">Offensichtliche Ausnahmen von dieser Regel werden die `!` und `.` Operatoren.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-210">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="5e8a6-211">Infix-Ausdrücke sind in Ordnung LineUp für dieselbe Spalte:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-211">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="5e8a6-212">Formatieren von Pipeline-Operatoren</span><span class="sxs-lookup"><span data-stu-id="5e8a6-212">Formatting pipeline operators</span></span>

<span data-ttu-id="5e8a6-213">Pipeline `|>` Operatoren verwendende unterhalb der Ausdrücke, die sie verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-213">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

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

### <a name="formatting-modules"></a><span data-ttu-id="5e8a6-214">Formatieren von Modulen</span><span class="sxs-lookup"><span data-stu-id="5e8a6-214">Formatting modules</span></span>

<span data-ttu-id="5e8a6-215">Code in einem lokalen Modul muss relativ zum Modul eingezogen werden, jedoch Code in einem Modul der obersten Ebene nicht eingezogen werden soll.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-215">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="5e8a6-216">Namespace-Elemente müssen nicht mit Einzug dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-216">Namespace elements do not have to be indented.</span></span>

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

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="5e8a6-217">Formatieren von Objektausdrücke und Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5e8a6-217">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="5e8a6-218">Objektausdrücke und Schnittstellen auf die gleiche Weise mit ausgerichtet sein `member` wird nach 4 Leerzeichen eingezogen.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-218">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-whitespace-in-expressions"></a><span data-ttu-id="5e8a6-219">Formatieren von Leerzeichen in Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="5e8a6-219">Formatting whitespace in expressions</span></span>

<span data-ttu-id="5e8a6-220">Vermeiden Sie unnötige Leerstellen in f#-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="5e8a6-220">Avoid extraneous whitespace in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="5e8a6-221">Benannte Argumente sollten auch keinen Speicherplatz umgebenden der `=`:</span><span class="sxs-lookup"><span data-stu-id="5e8a6-221">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```
