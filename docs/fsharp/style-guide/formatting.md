---
title: F#-Code Formatieren von Richtlinien
description: Erfahren Sie, Richtlinien zur Formatierung von F#-Code.
ms.date: 05/14/2018
ms.openlocfilehash: 0d7d2d1771710db55bf990f3a06079b2aec48fd7
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "43858004"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="e2ea0-103">F#-Code Formatieren von Richtlinien</span><span class="sxs-lookup"><span data-stu-id="e2ea0-103">F# code formatting guidelines</span></span>

<span data-ttu-id="e2ea0-104">Dieser Artikel bietet Richtlinien zum Code zu formatieren, damit Ihre F#-Code ist:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="e2ea0-105">In der Regel als besser lesbar angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="e2ea0-106">In Übereinstimmung mit Konventionen formatiert-Tools in Visual Studio und andere Editoren angewendet wird</span><span class="sxs-lookup"><span data-stu-id="e2ea0-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="e2ea0-107">Ähnlich wie bei anderen Code online</span><span class="sxs-lookup"><span data-stu-id="e2ea0-107">Similar to other code online</span></span>

<span data-ttu-id="e2ea0-108">Diese Leitlinien basieren auf [ein umfassendes Handbuch zum F#-Formatierungskonventionen](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) von [Anh-Dung Phan](https://github.com/dungpa).</span><span class="sxs-lookup"><span data-stu-id="e2ea0-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="e2ea0-109">Allgemeine Regeln für den Einzug</span><span class="sxs-lookup"><span data-stu-id="e2ea0-109">General rules for indentation</span></span>

<span data-ttu-id="e2ea0-110">F#-signifikanten Leerraum wird standardmäßig verwendet.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-110">F# uses significant white space by default.</span></span> <span data-ttu-id="e2ea0-111">Die folgenden Richtlinien dienen bieten eine Anleitung, wie einige Herausforderungen unter einen Hut bringen, die diese darstellen kann.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="e2ea0-112">Mithilfe von Speicherplätzen</span><span class="sxs-lookup"><span data-stu-id="e2ea0-112">Using spaces</span></span>

<span data-ttu-id="e2ea0-113">Wenn der Einzug erforderlich ist, müssen Sie Leerzeichen nicht Registerkarten verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="e2ea0-114">Mindestens ein Leerzeichen ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-114">At least one space is required.</span></span> <span data-ttu-id="e2ea0-115">Ihre Organisation kann zum Angeben der Anzahl der Leerzeichen für Einzüge zu verwendende Codierungsstandards erstellen; zwei, drei oder vier Leerzeichen des Einzugs am jede Einzugsebene ist typisch.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="e2ea0-116">**Es wird empfohlen, 4 Leerzeichen pro Einzug.**</span><span class="sxs-lookup"><span data-stu-id="e2ea0-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="e2ea0-117">Dies bedeutet, dass der Einzug der Programme eine subjektive Angelegenheit ist.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="e2ea0-118">Variationen sind in Ordnung, aber die erste Regel, die Sie befolgen sollten ist *Konsistenz des Einzugs*.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="e2ea0-119">Wählen Sie ein allgemein anerkannten Format des Einzugs und systematisch in Ihrer gesamten Codebasis verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-blank-lines"></a><span data-ttu-id="e2ea0-120">Formatieren von Leerzeilen</span><span class="sxs-lookup"><span data-stu-id="e2ea0-120">Formatting blank lines</span></span>

* <span data-ttu-id="e2ea0-121">Separate auf oberster Ebene-Funktion und der Klassendefinition mit zwei Leerzeilen.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-121">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="e2ea0-122">Methodendefinitionen, die innerhalb einer Klasse werden durch eine einzelne leere Zeile getrennt.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-122">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="e2ea0-123">Zusätzliche Leerzeilen einfügen können (selten) verwendet werden, um Gruppen von verwandten Funktionen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-123">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="e2ea0-124">Leere Zeilen können zwischen einer Reihe von verwandten Einzeiler (z. B. ein Satz von platzhalterimplementierungen) weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-124">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="e2ea0-125">Verwenden Sie Leerzeilen sparsam und nur dann in Funktionen, um logische Abschnitte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-125">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="e2ea0-126">Formatieren von Kommentaren</span><span class="sxs-lookup"><span data-stu-id="e2ea0-126">Formatting comments</span></span>

<span data-ttu-id="e2ea0-127">Ziehen Sie in der Regel mehrere Kommentaren mit doppelten Schrägstrichen blockskommentaren ML-Format vor.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-127">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="e2ea0-128">Inlinekommentare sollte der erste Buchstabe groß geschrieben.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-128">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="e2ea0-129">Namenskonventionen </span><span class="sxs-lookup"><span data-stu-id="e2ea0-129">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="e2ea0-130">Verwenden Sie CamelCase für die Klasse, ausdrucksgebundenen als auch Muster – gebunden Werte und Funktionen</span><span class="sxs-lookup"><span data-stu-id="e2ea0-130">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="e2ea0-131">Es ist üblich und akzeptierte F#-Stil verwenden Sie CamelCase für alle Namen gebunden, als lokale Variablen oder in musterübereinstimmungen und Funktionsdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-131">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="e2ea0-132">Lokale gebundene Funktionen in Klassen sollten auch CamelCase verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-132">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="e2ea0-133">Verwenden Sie CamelCase für Öffentliche Modul-Bound-Funktionen</span><span class="sxs-lookup"><span data-stu-id="e2ea0-133">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="e2ea0-134">Wenn eine Modul-Bound-Funktion eine öffentliche API gehört, sollten sie CamelCase verwenden:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-134">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="e2ea0-135">Verwenden Sie CamelCase für interne und private Modul-Bound-Werte und Funktionen</span><span class="sxs-lookup"><span data-stu-id="e2ea0-135">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="e2ea0-136">Verwenden Sie CamelCase für private Modul-Bound-Werte, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-136">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="e2ea0-137">Ad-hoc-Funktionen in Skripts</span><span class="sxs-lookup"><span data-stu-id="e2ea0-137">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="e2ea0-138">Werte, aus denen die interne Implementierung der ein Modul oder Typ</span><span class="sxs-lookup"><span data-stu-id="e2ea0-138">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="e2ea0-139">Verwenden Sie CamelCase für Parameter</span><span class="sxs-lookup"><span data-stu-id="e2ea0-139">Use camelCase for parameters</span></span>

<span data-ttu-id="e2ea0-140">Alle Parameter sollten CamelCase gemäß den Konventionen zur Namensgebung von .NET verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-140">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="e2ea0-141">Verwenden Sie PascalCase für Module.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-141">Use PascalCase for modules</span></span>

<span data-ttu-id="e2ea0-142">Alle Module (der obersten Ebene, interne, private, geschachtelte) sollten PascalCase verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-142">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="e2ea0-143">Verwenden von PascalCase für Deklarationen von Typen, Member und Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="e2ea0-143">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="e2ea0-144">Klassen, Schnittstellen, Strukturen, Enumerationen, Delegaten, Datensätze und Unterscheidungs-Unions sollten alle mit PascalCase benannt werden.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-144">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="e2ea0-145">Außerdem sollten die Elemente innerhalb der Typen und Bezeichnungen für Datensätze und Unterscheidungs-Unions PascalCase verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-145">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="e2ea0-146">Verwendung von PascalCase für Konstrukte auf .NET systeminterne</span><span class="sxs-lookup"><span data-stu-id="e2ea0-146">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="e2ea0-147">Namespaces, Ausnahmen, Ereignisse und Projekt /`.dll` Namen sollten auch PascalCase verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-147">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="e2ea0-148">Nicht nur macht dies Verbrauch von anderen .NET-Sprachen können Sie erwarten, dass Kunden, es ist auch mit .NET Benennungskonventionen, die Sie wahrscheinlich konfrontiert sind konsistent.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-148">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="e2ea0-149">Vermeiden Sie die Unterstriche im Namen</span><span class="sxs-lookup"><span data-stu-id="e2ea0-149">Avoid underscores in names</span></span>

<span data-ttu-id="e2ea0-150">In der Vergangenheit haben einige F#-Bibliotheken Unterstriche im Namen verwendet.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-150">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="e2ea0-151">Allerdings wird dies häufig nicht mehr akzeptiert, teilweise daran, dass sie mit .NET Benennungskonventionen verursacht einen Konflikt.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-151">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="e2ea0-152">Allerdings einige F#-Programmierer verwenden Unterstriche stark, teilweise historisch bedingt und Fehlertoleranz und Respekt ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-152">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="e2ea0-153">Bedenken Sie jedoch, dass der Stil häufig von anderen gefällt mir nicht ist, die eine Wahl darüber, ob sie verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-153">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="e2ea0-154">Einige Ausnahmen umfasst die Interaktion mit nativen Komponenten, in denen Unterstriche sind sehr häufig.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-154">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="e2ea0-155">Verwenden Sie die standardmäßige F#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="e2ea0-155">Use standard F# operators</span></span>

<span data-ttu-id="e2ea0-156">Die folgenden Operatoren werden in der F#-Standardbibliothek definiert und sollte verwendet werden, anstatt Entsprechungen.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-156">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="e2ea0-157">Mit diesen Operatoren wird empfohlen, wie sie Code besser lesbar und idiomatische machen ist.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-157">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="e2ea0-158">Entwickler mit einem Hintergrund mit OCaml oder andere funktionale Programmiersprache ggf. daran gewöhnt, Idiome zu sein.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-158">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="e2ea0-159">Die folgende Liste enthält die empfohlenen F#-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-159">The following list summarizes the recommended F# operators.</span></span>

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="e2ea0-160">Verwenden Sie Generika Präfix-Syntax (`Foo<T>`) statt Postfix-Syntax (`T Foo`)</span><span class="sxs-lookup"><span data-stu-id="e2ea0-160">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="e2ea0-161">F#-erbt sowohl den Postfix ML Stil für die Benennung von generischer Typen (z. B. `int list`) sowie das Präfix .NET Stil (z. B. `list<int>`).</span><span class="sxs-lookup"><span data-stu-id="e2ea0-161">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="e2ea0-162">Bevorzugen Sie das .NET-Format, mit Ausnahme von vier bestimmte Typen:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-162">Prefer the .NET style, except for four specific types:</span></span>

1. <span data-ttu-id="e2ea0-163">Für F#-Listen, verwenden Sie die Postfix-Form: `int list` statt `list<int>`.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-163">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="e2ea0-164">Für die F#-Optionen verwenden Sie die Postfix-Form: `int option` statt `option<int>`.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-164">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="e2ea0-165">Verwenden Sie für F#-Arrays, die syntaktischen Namen `int[]` statt `int array` oder `array<int>`.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-165">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
4. <span data-ttu-id="e2ea0-166">Verwenden Sie für Referenzzellen, `int ref` statt `ref<int>` oder `Ref<int>`.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-166">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="e2ea0-167">Verwenden Sie für alle anderen Dateitypen die Präfix-Form.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-167">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="e2ea0-168">Formatieren von Tupeln</span><span class="sxs-lookup"><span data-stu-id="e2ea0-168">Formatting tuples</span></span>

<span data-ttu-id="e2ea0-169">Eine Instanziierung Tupel muss in Klammern ein, und die begrenzenden Kommas innerhalb von sollte z. B. durch ein Leerzeichen, gefolgt werden: `(1, 2)`, `(x, y, z)`.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-169">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="e2ea0-170">Es wird häufig zum Auslassen von Klammern in Musterabgleich von Tupeln akzeptiert:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-170">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="e2ea0-171">Formatieren von Unterscheidungs-union-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="e2ea0-171">Formatting discriminated union declarations</span></span>

<span data-ttu-id="e2ea0-172">Einzug `|` in der Definition des Typs von 4 Leerzeichen:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-172">Indent `|` in type definition by 4 spaces:</span></span>

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

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="e2ea0-173">Formatieren von Unterscheidungs-unions</span><span class="sxs-lookup"><span data-stu-id="e2ea0-173">Formatting discriminated unions</span></span>

<span data-ttu-id="e2ea0-174">Instanziierte Unterscheidungs-Unions, die über mehrere Zeilen aufgeteilt sollte enthaltenen Daten einen neuen Bereich mit Einzug bieten:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-174">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="e2ea0-175">Die schließende Klammer kann auch in einer neuen Zeile werden:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-175">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="e2ea0-176">Formatieren von Datensatz-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="e2ea0-176">Formatting record declarations</span></span>

<span data-ttu-id="e2ea0-177">Einzug `{` Geben Sie in die Definition von 4 Leerzeichen und die Feldliste in der gleichen Zeile beginnen:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-177">Indent `{` in type definition by 4 spaces and start the field list on the same line:</span></span>

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

<span data-ttu-id="e2ea0-178">Das öffnendes-Token auf der gleichen Zeile und dem schließenden-Token in einer neuen Zeile platziert ist ebenfalls in Ordnung, aber beachten Sie, dass Sie benötigen die [ausführliche Syntax](../language-reference/verbose-syntax.md) um Elemente zu definieren (die `with` Schlüsselwort):</span><span class="sxs-lookup"><span data-stu-id="e2ea0-178">Placing the opening token on the same line and the closing token on a new line is also fine, but be aware that you need to use the [verbose syntax](../language-reference/verbose-syntax.md) to define members (the `with` keyword):</span></span>

```fsharp
//  OK, but verbose syntax required
type PostalAddress = { 
    Address: string
    City: string
    Zip: string
} with
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City
```

## <a name="formatting-records"></a><span data-ttu-id="e2ea0-179">Formatieren von Datensätzen</span><span class="sxs-lookup"><span data-stu-id="e2ea0-179">Formatting records</span></span>

<span data-ttu-id="e2ea0-180">Kurze Datensätze können in einer Zeile geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-180">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="e2ea0-181">Datensätze, die länger sind, sollten neue Zeilen für Bezeichnungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-181">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="e2ea0-182">Es ist auch in Ordnung, das öffnendes-Token auf der gleichen Zeile und dem schließenden-Token in einer neuen Zeile platziert:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-182">Placing the opening token on the same line and the closing token on a new line is also fine:</span></span>

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

<span data-ttu-id="e2ea0-183">Die gleichen Regeln gelten für Listen- und Elemente.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-183">The same rules apply for list and array elements.</span></span>

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="e2ea0-184">Formatieren von Listen und arrays</span><span class="sxs-lookup"><span data-stu-id="e2ea0-184">Formatting lists and arrays</span></span>

<span data-ttu-id="e2ea0-185">Schreiben von `x :: l` mit Leerzeichen vor und hinter der `::` Operator (`::` ist ein Infix-Operator, daher Leerzeichen enthaltender) und `[1; 2; 3]` (`;` ein Trennzeichen, daher gefolgt von einem Leerzeichen).</span><span class="sxs-lookup"><span data-stu-id="e2ea0-185">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces) and `[1; 2; 3]` (`;` is a delimiter, hence followed by a space).</span></span>

<span data-ttu-id="e2ea0-186">Verwenden Sie immer mindestens ein Leerzeichen zwischen zwei unterschiedlichen geschweifte Klammer-Like-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-186">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="e2ea0-187">Lassen Sie beispielsweise einem Leerzeichen zwischen einem `[` und `{`.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-187">For example, leave a space between a `[` and a `{`.</span></span>

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

<span data-ttu-id="e2ea0-188">Listen und Arrays, die über mehrere Zeilen aufgeteilt. Führen Sie eine ähnliche Regel, wie Datensätze:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-188">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

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

## <a name="formatting-if-expressions"></a><span data-ttu-id="e2ea0-189">Formatierung-If-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="e2ea0-189">Formatting if expressions</span></span>

<span data-ttu-id="e2ea0-190">Einzug von Bedingungen hängt von der Größe der Ausdrücke, die sie sich machen ab.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-190">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="e2ea0-191">Wenn `cond`, `e1` und `e2` sind kurze, Schreiben Sie sie einfach auf eine Zeile:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-191">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="e2ea0-192">Wenn entweder `cond`, `e1` oder `e2` sind länger, aber nicht mit mehreren Zeilen:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-192">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="e2ea0-193">Wenn einer der Ausdrücke mit mehreren Zeilen sind:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-193">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="e2ea0-194">Mehrere Bedingungen mit `elif` und `else` werden eingerückt unter dem gleichen Bereich wie die `if`:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-194">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="e2ea0-195">Übereinstimmende Muster-Konstrukte</span><span class="sxs-lookup"><span data-stu-id="e2ea0-195">Pattern matching constructs</span></span>

<span data-ttu-id="e2ea0-196">Verwenden einer `|` für jede Klausel einer Übereinstimmung mit ohne Einzug.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-196">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="e2ea0-197">Wenn der Ausdruck kurz ist, können Sie erwägen, eine einzelne Zeile verwenden, wenn jede Teilausdruck auch einfach ist.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-197">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

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

<span data-ttu-id="e2ea0-198">Wenn der Ausdruck auf der rechten Seite der Musterabgleich Pfeil zu groß ist, verschieben Sie sie auf der folgenden Zeile eingezogen einen Schritt aus dem `match` / `|`.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-198">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="e2ea0-199">Mustervergleich von anonymen Funktionen, die gestartet wird, indem `function`, sollte im Allgemeinen nicht einrücken zu weit.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-199">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="e2ea0-200">Beispielsweise reicht Einzug einen Bereich wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-200">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="e2ea0-201">Mustervergleiche in Funktionen, die von definiert `let` oder `let rec` muss eingezogene 4 Leerzeichen nach dem Starten des `let`, auch wenn `function` -Schlüsselwort wird verwendet:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-201">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="e2ea0-202">Wir empfehlen nicht, Pfeile ausrichten.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-202">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="e2ea0-203">Formatierung Try / with-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="e2ea0-203">Formatting try/with expressions</span></span>

<span data-ttu-id="e2ea0-204">Musterabgleich für den Typ der Ausnahme sollte eingezogen werden, auf der gleichen Ebene wie `with`.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-204">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

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

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="e2ea0-205">Formatieren von funktionsanwendung-parameter</span><span class="sxs-lookup"><span data-stu-id="e2ea0-205">Formatting function parameter application</span></span>

<span data-ttu-id="e2ea0-206">Die meisten funktionsanwendung-Parameter wird in der Regel in der gleichen Zeile durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-206">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="e2ea0-207">Wenn Sie, um Parameter an eine Funktion in einer neuen Zeile anzuwenden möchten, Rücken Sie diese durch einen Bereich.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-207">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

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

<span data-ttu-id="e2ea0-208">Die gleichen Richtlinien gelten für Lambda-Ausdrücke als Argumente der Funktion.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-208">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="e2ea0-209">Wenn der Text eines Lambda-Ausdrucks, der Text einer anderen Zeile eingerückt wird, indem Sie einen Bereich enthalten kann</span><span class="sxs-lookup"><span data-stu-id="e2ea0-209">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

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

<span data-ttu-id="e2ea0-210">Allerdings ist der Text eines Lambdaausdrucks mehrere Zeilen, sollten Sie ihn in eine separate Funktion Finanzierung anstelle einer mehrzeiligen-Konstrukt, das als einzelnes Argument an eine Funktion angewendet.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-210">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="e2ea0-211">Formatieren von Infixoperatoren</span><span class="sxs-lookup"><span data-stu-id="e2ea0-211">Formatting infix operators</span></span>

<span data-ttu-id="e2ea0-212">Separate Operatoren durch Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-212">Separate operators by spaces.</span></span> <span data-ttu-id="e2ea0-213">Offensichtliche Ausnahmen von dieser Regel werden die `!` und `.` Operatoren.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-213">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="e2ea0-214">Infix-Ausdrücke sind in Ordnung LineUp auf dieselbe Spalte:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-214">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="e2ea0-215">Formatieren von Pipeline-Operatoren</span><span class="sxs-lookup"><span data-stu-id="e2ea0-215">Formatting pipeline operators</span></span>

<span data-ttu-id="e2ea0-216">Pipeline `|>` Operatoren gesendet werden sollen, darunter die Ausdrücke, die sie verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-216">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

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

### <a name="formatting-modules"></a><span data-ttu-id="e2ea0-217">Formatieren von Modulen</span><span class="sxs-lookup"><span data-stu-id="e2ea0-217">Formatting modules</span></span>

<span data-ttu-id="e2ea0-218">Code in einem lokalen Modul muss sich auf das Modul eingezogen werden, jedoch Code in einem Modul auf oberster Ebene sollten nicht eingerückt werden.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-218">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="e2ea0-219">Namespace-Elemente müssen nicht mit Einzug dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-219">Namespace elements do not have to be indented.</span></span>

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

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="e2ea0-220">Formatieren von Object-Ausdrücke und Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e2ea0-220">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="e2ea0-221">Object-Ausdrücke und Schnittstellen sollten auf die gleiche Weise mit ausgerichtet werden `member` nach 4 Leerzeichen eingerückt wird.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-221">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="e2ea0-222">Formatieren von Leerzeichen in Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="e2ea0-222">Formatting white space in expressions</span></span>

<span data-ttu-id="e2ea0-223">Vermeiden Sie die überflüssigen Leerzeichen in F#-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="e2ea0-223">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="e2ea0-224">Benannte Argumente dürfen auch keine Leerzeichen, umgibt die `=`:</span><span class="sxs-lookup"><span data-stu-id="e2ea0-224">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```
