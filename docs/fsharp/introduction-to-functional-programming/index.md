---
title: Einführung in die funktionale Programmierung mit F#
description: Lernen Sie die Grundlagen der funktionalen Programmierung mit F# kennen.
ms.date: 10/29/2018
ms.openlocfilehash: fc2aebe80de16b92942c3557c0e03c198883dde1
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740327"
---
# <a name="introduction-to-functional-programming-in-f"></a><span data-ttu-id="20e58-103">Einführung in die funktionale Programmierung mit F\#</span><span class="sxs-lookup"><span data-stu-id="20e58-103">Introduction to Functional Programming in F\#</span></span>

<span data-ttu-id="20e58-104">Die funktionale Programmierung ist ein Programmierstil, der die Verwendung von Funktionen und unveränderlichen Daten betont.</span><span class="sxs-lookup"><span data-stu-id="20e58-104">Functional programming is a style of programming that emphasizes the use of functions and immutable data.</span></span> <span data-ttu-id="20e58-105">Das Merkmal typisierter funktionaler Programmierung ist, dass die funktionale Programmierung mit statischen Typen kombiniert wird, z. B. F#.</span><span class="sxs-lookup"><span data-stu-id="20e58-105">Typed functional programming is when functional programming is combined with static types, such as with F#.</span></span> <span data-ttu-id="20e58-106">Im Allgemeinen werden die folgenden Konzepte bei der funktionalen Programmierung betont:</span><span class="sxs-lookup"><span data-stu-id="20e58-106">In general, the following concepts are emphasized in functional programming:</span></span>

* <span data-ttu-id="20e58-107">Funktionen als primäre Konstrukte, die Sie verwenden</span><span class="sxs-lookup"><span data-stu-id="20e58-107">Functions as the primary constructs you use</span></span>
* <span data-ttu-id="20e58-108">Ausdrücke anstelle von Anweisungen</span><span class="sxs-lookup"><span data-stu-id="20e58-108">Expressions instead of statements</span></span>
* <span data-ttu-id="20e58-109">Unveränderliche Werte vor Variablen</span><span class="sxs-lookup"><span data-stu-id="20e58-109">Immutable values over variables</span></span>
* <span data-ttu-id="20e58-110">Deklarative Programmierung vor imperativer Programmierung</span><span class="sxs-lookup"><span data-stu-id="20e58-110">Declarative programming over imperative programming</span></span>

<span data-ttu-id="20e58-111">In dieser Reihe lernen Sie Konzepte und Muster der funktionalen Programmierung mit F# kennen.</span><span class="sxs-lookup"><span data-stu-id="20e58-111">Throughout this series, you'll explore concepts and patterns in functional programming using F#.</span></span> <span data-ttu-id="20e58-112">Dabei erfahren Sie auch Einiges über F#.</span><span class="sxs-lookup"><span data-stu-id="20e58-112">Along the way, you'll learn some F# too.</span></span>

## <a name="terminology"></a><span data-ttu-id="20e58-113">Begriff</span><span class="sxs-lookup"><span data-stu-id="20e58-113">Terminology</span></span>

<span data-ttu-id="20e58-114">Wie andere Programmierparadigmen hat die funktionale Programmierung ein Vokabular, das Sie lernen müssen.</span><span class="sxs-lookup"><span data-stu-id="20e58-114">Functional programming, like other programming paradigms, comes with a vocabulary that you will eventually need to learn.</span></span> <span data-ttu-id="20e58-115">Im Folgenden finden Sie einige gängige Begriffe, die Ihnen ständig begegnen werden:</span><span class="sxs-lookup"><span data-stu-id="20e58-115">Here are some common terms you'll see all of the time:</span></span>

* <span data-ttu-id="20e58-116">**Funktion**: Eine Funktion ist ein Konstrukt, das eine Ausgabe erzeugt, wenn es eine Eingabe erhält.</span><span class="sxs-lookup"><span data-stu-id="20e58-116">**Function** - A function is a construct that will produce an output when given an input.</span></span> <span data-ttu-id="20e58-117">Formeller gesagt, _weist_ sie ein Element aus einem Satz einem anderen Satz zu.</span><span class="sxs-lookup"><span data-stu-id="20e58-117">More formally, it _maps_ an item from one set to another set.</span></span> <span data-ttu-id="20e58-118">Dieser Formalismus wird in vielerlei Hinsicht konkret, insbesondere bei der Verwendung von Funktionen, die Datensammlungen verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="20e58-118">This formalism is lifted into the concrete in many ways, especially when using functions that operate on collections of data.</span></span> <span data-ttu-id="20e58-119">Dies ist das grundlegendste (und wichtigste) Konzept der funktionalen Programmierung.</span><span class="sxs-lookup"><span data-stu-id="20e58-119">It is the most basic (and important) concept in functional programming.</span></span>
* <span data-ttu-id="20e58-120">**Ausdruck**: Ein Ausdruck ist ein Konstrukt im Code, das einen Wert erzeugt.</span><span class="sxs-lookup"><span data-stu-id="20e58-120">**Expression** - An expression is a construct in code that produces a value.</span></span> <span data-ttu-id="20e58-121">In F# muss dieser Wert gebunden oder explizit ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="20e58-121">In F#, this value must be bound or explicitly ignored.</span></span> <span data-ttu-id="20e58-122">Ein Ausdruck kann einfach durch einen Funktionsaufruf ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="20e58-122">An expression can be trivially replaced by a function call.</span></span>
* <span data-ttu-id="20e58-123">**Reinheit**: Reinheit als Eigenschaft einer Funktion bedeutet, dass ihr Rückgabewert für dieselben Argumente immer identisch ist und seine Auswertung keine Nebeneffekte hat.</span><span class="sxs-lookup"><span data-stu-id="20e58-123">**Purity** - Purity is a property of a function such that its return value is always the same for the same arguments, and that its evaluation has no side effects.</span></span> <span data-ttu-id="20e58-124">Eine reine Funktion hängt vollständig von ihren Argumenten ab.</span><span class="sxs-lookup"><span data-stu-id="20e58-124">A pure function depends entirely on its arguments.</span></span>
* <span data-ttu-id="20e58-125">**Referenzielle Transparenz**: Referenzielle Transparenz als Eigenschaft einer Funktion bedeutet, dass sie durch ihre Ausgabe ersetzt werden kann, ohne dass das Verhalten eines Programms beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="20e58-125">**Referential Transparency** - Referential Transparency is a property of expressions such that they can be replaced with their output without affecting a program's behavior.</span></span>
* <span data-ttu-id="20e58-126">**Unveränderlichkeit**: Unveränderlichkeit bedeutet, dass ein Wert nicht direkt geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="20e58-126">**Immutability** - Immutability means that a value cannot be changed in-place.</span></span> <span data-ttu-id="20e58-127">Dies steht im Gegensatz zu Variablen, die sich direkt ändern können.</span><span class="sxs-lookup"><span data-stu-id="20e58-127">This is in contrast with variables, which can change in place.</span></span>

## <a name="examples"></a><span data-ttu-id="20e58-128">Beispiele</span><span class="sxs-lookup"><span data-stu-id="20e58-128">Examples</span></span>

<span data-ttu-id="20e58-129">In den folgenden Beispielen werden diese Kernkonzepte veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="20e58-129">The following examples demonstrate these core concepts.</span></span>

### <a name="functions"></a><span data-ttu-id="20e58-130">Functions</span><span class="sxs-lookup"><span data-stu-id="20e58-130">Functions</span></span>

<span data-ttu-id="20e58-131">Das gängigste und grundlegendste Konstrukt der funktionalen Programmierung ist die Funktion.</span><span class="sxs-lookup"><span data-stu-id="20e58-131">The most common and fundamental construct in functional programming is the function.</span></span> <span data-ttu-id="20e58-132">Im Folgenden finden Sie eine einfache Funktion, die einer Ganzzahl den Wert 1 hinzufügt:</span><span class="sxs-lookup"><span data-stu-id="20e58-132">Here's a simple function that adds 1 to an integer:</span></span>

```fsharp
let addOne x = x + 1
```

<span data-ttu-id="20e58-133">Ihre Typsignatur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="20e58-133">Its type signature is as follows:</span></span>

```fsharp
val addOne: x:int -> int
```

<span data-ttu-id="20e58-134">Die Signatur kann als „`addOne` nimmt einen `int`-Wert mit dem Namen `x` entgegen und erzeugt einen `int`-Wert“ gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="20e58-134">The signature can be read as, "`addOne` accepts an `int` named `x` and will produce an `int`".</span></span> <span data-ttu-id="20e58-135">Formeller betrachtet, ist `addOne` die _Zuordnung_ eines Wert aus dem Satz ganzer Zahlen zum Satz ganzer Zahlen.</span><span class="sxs-lookup"><span data-stu-id="20e58-135">More formally, `addOne` is _mapping_ a value from the set of integers to the set of integers.</span></span> <span data-ttu-id="20e58-136">Das `->`-Token bezeichnet diese Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="20e58-136">The `->` token signifies this mapping.</span></span> <span data-ttu-id="20e58-137">In F# können Sie in der Regel anhand der Funktionssignatur erkennen, was sie tut.</span><span class="sxs-lookup"><span data-stu-id="20e58-137">In F#, you can usually look at the function signature to get a sense for what it does.</span></span>

<span data-ttu-id="20e58-138">Warum ist die Signatur denn so wichtig?</span><span class="sxs-lookup"><span data-stu-id="20e58-138">So, why is the signature important?</span></span> <span data-ttu-id="20e58-139">In der typisierten funktionalen Programmierung ist die Implementierung einer Funktion oft weniger wichtig als die eigentliche Typsignatur!</span><span class="sxs-lookup"><span data-stu-id="20e58-139">In typed functional programming, the implementation of a function is often less important than the actual type signature!</span></span> <span data-ttu-id="20e58-140">Die Tatsache, dass `addOne` den Wert 1 zu einer Ganzzahl addiert, ist zur Laufzeit interessant, aber wenn Sie ein Programm erstellen, informiert Sie die Tatsache, dass es einen `int`-Wert annimmt und zurückgibt, darüber, wie Sie diese Funktion tatsächlich verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="20e58-140">The fact that `addOne` adds the value 1 to an integer is interesting at runtime, but when you are constructing a program, the fact that it accepts and returns an `int` is what informs how you will actually use this function.</span></span> <span data-ttu-id="20e58-141">Wenn Sie diese Funktion außerdem ordnungsgemäß (in Bezug auf ihre Typsignatur) verwenden, kann die Diagnose von Problemen nur innerhalb des Texts der `addOne`-Funktion erfolgen.</span><span class="sxs-lookup"><span data-stu-id="20e58-141">Furthermore, once you use this function correctly (with respect to its type signature), diagnosing any problems can be done only within the body of the `addOne` function.</span></span> <span data-ttu-id="20e58-142">Dies ist der Impuls hinter der typisierten funktionalen Programmierung.</span><span class="sxs-lookup"><span data-stu-id="20e58-142">This is the impetus behind typed functional programming.</span></span>

### <a name="expressions"></a><span data-ttu-id="20e58-143">Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="20e58-143">Expressions</span></span>

<span data-ttu-id="20e58-144">Ausdrücke sind Konstrukte, die zu einem Wert ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="20e58-144">Expressions are constructs that evaluate to a value.</span></span> <span data-ttu-id="20e58-145">Im Gegensatz zu Anweisungen, die einfach eine Aktion ausführen, führen Ausdrücke eine Aktion aus, die einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="20e58-145">In contrast to statements, which perform an action, expressions can be thought of performing an action that gives back a value.</span></span> <span data-ttu-id="20e58-146">Ausdrücke werden in der funktionalen Programmierung fast immer Anweisungen vorgezogen.</span><span class="sxs-lookup"><span data-stu-id="20e58-146">Expressions are almost always used in favor of statements in functional programming.</span></span>

<span data-ttu-id="20e58-147">Betrachten Sie die obige Funktion `addOne`.</span><span class="sxs-lookup"><span data-stu-id="20e58-147">Consider the previous function, `addOne`.</span></span> <span data-ttu-id="20e58-148">Der Text von `addOne` ist ein Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="20e58-148">The body of `addOne` is an expression:</span></span>

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

<span data-ttu-id="20e58-149">Das Ergebnis dieses Ausdrucks definiert den Ergebnistyp der `addOne`-Funktion.</span><span class="sxs-lookup"><span data-stu-id="20e58-149">It is the result of this expression that defines the result type of the `addOne` function.</span></span> <span data-ttu-id="20e58-150">Beispielsweise könnte der Ausdruck, der diese Funktion bildet, in einen anderen Typ geändert werden, z. B. einen `string`:</span><span class="sxs-lookup"><span data-stu-id="20e58-150">For example, the expression that makes up this function could be changed to be a different type, such as a `string`:</span></span>

```fsharp
let addOne x = x.ToString() + "1"
```

<span data-ttu-id="20e58-151">Die Signatur der Funktion lautet nun:</span><span class="sxs-lookup"><span data-stu-id="20e58-151">The signature of the function is now:</span></span>

```fsharp
val addOne: x:'a -> string
```

<span data-ttu-id="20e58-152">Da für jeden Typ in F# `ToString()` aufgerufen werden kann, wurde der Typ von `x` verallgemeinert ([automatische Verallgemeinerung](../language-reference/generics/automatic-generalization.md) genannt), und der resultierende Typ ist ein `string`.</span><span class="sxs-lookup"><span data-stu-id="20e58-152">Since any type in F# can have `ToString()` called on it, the type of `x` has been made generic (called [Automatic Generalization](../language-reference/generics/automatic-generalization.md)), and the resultant type is a `string`.</span></span>

<span data-ttu-id="20e58-153">Ausdrücke sind nicht nur die Texte von Funktionen.</span><span class="sxs-lookup"><span data-stu-id="20e58-153">Expressions are not just the bodies of functions.</span></span> <span data-ttu-id="20e58-154">Sie können Ausdrücke verwenden, die einen Wert produzieren, den Sie an anderer Stelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="20e58-154">You can have expressions that produce a value you use elsewhere.</span></span> <span data-ttu-id="20e58-155">`if` ist gängig:</span><span class="sxs-lookup"><span data-stu-id="20e58-155">A common one is `if`:</span></span>

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result
```

<span data-ttu-id="20e58-156">Der `if`-Ausdruck erzeugt einen Wert namens `result`.</span><span class="sxs-lookup"><span data-stu-id="20e58-156">The `if` expression produces a value called `result`.</span></span> <span data-ttu-id="20e58-157">Beachten Sie, dass Sie `result` vollständig weglassen könnten, indem Sie den `if`-Ausdruck zum Text der `addOneIfOdd`-Funktion machen.</span><span class="sxs-lookup"><span data-stu-id="20e58-157">Note that you could omit `result` entirely, making the `if` expression the body of the `addOneIfOdd` function.</span></span> <span data-ttu-id="20e58-158">Das Wichtigste, was Sie sich über Ausdrücke merken sollten, ist, dass sie einen Wert produzieren.</span><span class="sxs-lookup"><span data-stu-id="20e58-158">The key thing to remember about expressions is that they produce a value.</span></span>

<span data-ttu-id="20e58-159">Ein besonderer Typ, `unit`, wird verwendet, wenn nichts zurückgegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="20e58-159">There is a special type, `unit`, that is used when there is nothing to return.</span></span> <span data-ttu-id="20e58-160">Betrachten Sie als Beispiel diese einfache Funktion:</span><span class="sxs-lookup"><span data-stu-id="20e58-160">For example, consider this simple function:</span></span>

```fsharp
let printString (str: string) =
    printfn $"String is: {str}"
```

<span data-ttu-id="20e58-161">Die Signatur sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="20e58-161">The signature looks like this:</span></span>

```fsharp
val printString: str:string -> unit
```

<span data-ttu-id="20e58-162">Der `unit`-Typ gibt an, dass kein tatsächlicher Wert zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="20e58-162">The `unit` type indicates that there is no actual value being returned.</span></span> <span data-ttu-id="20e58-163">Dies ist nützlich, wenn Sie über eine Routine verfügen, die „arbeiten“ muss, obwohl kein Wert vorhanden ist, der als Ergebnis der Arbeit zurückgegeben werden könnte.</span><span class="sxs-lookup"><span data-stu-id="20e58-163">This is useful when you have a routine that must "do work" despite having no value to return as a result of that work.</span></span>

<span data-ttu-id="20e58-164">Dies ist ein scharfer Kontrast zur imperativen Programmierung, bei der das entsprechende `if`-Konstrukt eine-Anweisung ist und das Erstellen von Werten häufig mit der Veränderung von Variablen erfolgt.</span><span class="sxs-lookup"><span data-stu-id="20e58-164">This is in sharp contrast to imperative programming, where the equivalent `if` construct is a statement, and producing values is often done with mutating variables.</span></span> <span data-ttu-id="20e58-165">In C# könnte der Code z. B. wie folgt geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="20e58-165">For example, in C#, the code might be written like this:</span></span>

```csharp
bool IsOdd(int x) => x % 2 != 0;

int AddOneIfOdd(int input)
{
    var result = input;

    if (IsOdd(input))
    {
        result = input + 1;
    }

    return result;
}
```

<span data-ttu-id="20e58-166">Beachten Sie, dass C# und andere Sprachen im C-Stil den [ternären Ausdruck](../../csharp/language-reference/operators/conditional-operator.md) unterstützen, der die ausdrucksbasierte bedingte Programmierung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="20e58-166">It's worth noting that C# and other C-style languages do support the [ternary expression](../../csharp/language-reference/operators/conditional-operator.md), which allows for expression-based conditional programming.</span></span>

<span data-ttu-id="20e58-167">In der funktionalen Programmierung werden Werte selten mit Anweisungen verändert.</span><span class="sxs-lookup"><span data-stu-id="20e58-167">In functional programming, it is rare to mutate values with statements.</span></span> <span data-ttu-id="20e58-168">Einige funktionale Sprachen unterstützen Anweisungen und Veränderungen, aber es ist nicht üblich, diese Konzepte in der funktionalen Programmierung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="20e58-168">Although some functional languages support statements and mutation, it is not common to use these concepts in functional programming.</span></span>

### <a name="pure-functions"></a><span data-ttu-id="20e58-169">Reine Funktionen</span><span class="sxs-lookup"><span data-stu-id="20e58-169">Pure functions</span></span>

<span data-ttu-id="20e58-170">Wie bereits erwähnt, weisen reine Funktionen folgende Merkmale auf:</span><span class="sxs-lookup"><span data-stu-id="20e58-170">As previously mentioned, pure functions are functions that:</span></span>

* <span data-ttu-id="20e58-171">Für dieselbe Eingabe wird immer derselbe Wert ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="20e58-171">Always evaluate to the same value for the same input.</span></span>
* <span data-ttu-id="20e58-172">Sie haben keine Nebeneffekte.</span><span class="sxs-lookup"><span data-stu-id="20e58-172">Have no side effects.</span></span>

<span data-ttu-id="20e58-173">Es ist hilfreich, in diesem Kontext mathematische Funktionen zu betrachten.</span><span class="sxs-lookup"><span data-stu-id="20e58-173">It is helpful to think of mathematical functions in this context.</span></span> <span data-ttu-id="20e58-174">In der Mathematik sind Funktionen nur von ihren Argumenten abhängig und haben keine Nebeneffekte.</span><span class="sxs-lookup"><span data-stu-id="20e58-174">In mathematics, functions depend only on their arguments and do not have any side effects.</span></span> <span data-ttu-id="20e58-175">In der mathematischen Funktion `f(x) = x + 1` hängt der Wert von `f(x)` nur vom Wert von `x` ab.</span><span class="sxs-lookup"><span data-stu-id="20e58-175">In the mathematical function `f(x) = x + 1`, the value of `f(x)` depends only on the value of `x`.</span></span> <span data-ttu-id="20e58-176">Bei reinen Funktionen in der funktionalen Programmierung verhält es sich genauso.</span><span class="sxs-lookup"><span data-stu-id="20e58-176">Pure functions in functional programming are the same way.</span></span>

<span data-ttu-id="20e58-177">Beachten Sie beim Schreiben einer reinen Funktion, dass die Funktion nur von ihren Argumenten abhängig sein und keine Aktionen ausführen darf, die zu einem Nebeneffekt führen.</span><span class="sxs-lookup"><span data-stu-id="20e58-177">When writing a pure function, the function must depend only on its arguments and not perform any action that results in a side effect.</span></span>

<span data-ttu-id="20e58-178">Im Folgenden finden Sie ein Beispiel für eine Funktion, die nicht rein ist, da sie vom globalen, veränderbaren Zustand abhängt:</span><span class="sxs-lookup"><span data-stu-id="20e58-178">Here is an example of a non-pure function because it depends on global, mutable state:</span></span>

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

<span data-ttu-id="20e58-179">Die `addOneToValue`-Funktion ist eindeutig nicht rein, da `value` jederzeit in einen anderen Wert als 1 geändert werden könnte.</span><span class="sxs-lookup"><span data-stu-id="20e58-179">The `addOneToValue` function is clearly impure, because `value` could be changed at any time to have a different value than 1.</span></span> <span data-ttu-id="20e58-180">Dieses Muster der Abhängigkeit von einem globalen Wert muss in der funktionalen Programmierung vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="20e58-180">This pattern of depending on a global value is to be avoided in functional programming.</span></span>

<span data-ttu-id="20e58-181">Hier sehen Sie ein weiteres Beispiel für eine Funktion, die nicht rein ist, da sie einen Nebeneffekt hat:</span><span class="sxs-lookup"><span data-stu-id="20e58-181">Here is another example of a non-pure function, because it performs a side effect:</span></span>

```fsharp
let addOneToValue x =
    printfn $"x is %d{x}"
    x + 1
```

<span data-ttu-id="20e58-182">Obwohl diese Funktion nicht von einem globalen Wert abhängt, schreibt sie den Wert `x` in die Ausgabe des Programms.</span><span class="sxs-lookup"><span data-stu-id="20e58-182">Although this function does not depend on a global value, it writes the value of `x` to the output of the program.</span></span> <span data-ttu-id="20e58-183">Dies ist zwar grundsätzlich nicht falsch, bedeutet aber, dass die Funktion nicht rein ist.</span><span class="sxs-lookup"><span data-stu-id="20e58-183">Although there is nothing inherently wrong with doing this, it does mean that the function is not pure.</span></span> <span data-ttu-id="20e58-184">Wenn ein anderer Teil des Programms von programmexternen Elementen wie z. B. dem Ausgabepuffer abhängt, kann der Aufruf dieser Funktion sich auf diesen anderen Teil des Programms auswirken.</span><span class="sxs-lookup"><span data-stu-id="20e58-184">If another part of your program depends on something external to the program, such as the output buffer, then calling this function can affect that other part of your program.</span></span>

<span data-ttu-id="20e58-185">Durch Entfernen der `printfn`-Anweisung wird die Funktion rein:</span><span class="sxs-lookup"><span data-stu-id="20e58-185">Removing the `printfn` statement makes the function pure:</span></span>

```fsharp
let addOneToValue x = x + 1
```

<span data-ttu-id="20e58-186">Diese Funktion ist zwar nicht grundsätzlich _besser_ als die vorherige Version mit der `printfn`-Anweisung, aber es ist gewährleistet, dass sie nichts anderes tut als einen Wert zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="20e58-186">Although this function is not inherently _better_ than the previous version with the `printfn` statement, it does guarantee that all this function does is return a value.</span></span> <span data-ttu-id="20e58-187">Wenn diese Funktion beliebig oft aufgerufen wird, wird immer das gleiche Ergebnis erzielt: Sie erzeugt lediglich einen Wert.</span><span class="sxs-lookup"><span data-stu-id="20e58-187">Calling this function any number of times produces the same result: it just produces a value.</span></span> <span data-ttu-id="20e58-188">Die durch Reinheit garantierte Vorhersagbarkeit ist etwas, das viele funktionale Programmierer anstreben.</span><span class="sxs-lookup"><span data-stu-id="20e58-188">The predictability given by purity is something many functional programmers strive for.</span></span>

### <a name="immutability"></a><span data-ttu-id="20e58-189">Unveränderlichkeit.</span><span class="sxs-lookup"><span data-stu-id="20e58-189">Immutability</span></span>

<span data-ttu-id="20e58-190">Schließlich ist Unveränderlichkeit eines der grundlegendsten Konzepte der typisierten funktionalen Programmierung.</span><span class="sxs-lookup"><span data-stu-id="20e58-190">Finally, one of the most fundamental concepts of typed functional programming is immutability.</span></span> <span data-ttu-id="20e58-191">In F# sind alle Werte standardmäßig unveränderbar.</span><span class="sxs-lookup"><span data-stu-id="20e58-191">In F#, all values are immutable by default.</span></span> <span data-ttu-id="20e58-192">Dies bedeutet, dass sie nicht direkt bearbeitet werden können, sofern Sie sie nicht explizit als veränderbar markieren.</span><span class="sxs-lookup"><span data-stu-id="20e58-192">That means they cannot be mutated in-place unless you explicitly mark them as mutable.</span></span>

<span data-ttu-id="20e58-193">In der Praxis bedeutet das Arbeiten mit unveränderlichen Werten, dass Sie Ihren Programmierungsansatz von „Ich muss etwas ändern“ in „Ich muss einen neuen Wert erzeugen“ ändern.</span><span class="sxs-lookup"><span data-stu-id="20e58-193">In practice, working with immutable values means that you change your approach to programming from, "I need to change something", to "I need to produce a new value".</span></span>

<span data-ttu-id="20e58-194">Wenn Sie z. B. 1 einem Wert hinzufügen, wird ein neuer Wert erzeugt, nicht der vorhandene Wert geändert:</span><span class="sxs-lookup"><span data-stu-id="20e58-194">For example, adding 1 to a value means producing a new value, not mutating the existing one:</span></span>

```fsharp
let value = 1
let secondValue = value + 1
```

<span data-ttu-id="20e58-195">In F# ändert der folgende Code **nicht** die `value`-Funktion; stattdessen wird eine Gleichheitsüberprüfung durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="20e58-195">In F#, the following code does **not** mutate the `value` function; instead, it performs an equality check:</span></span>

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

<span data-ttu-id="20e58-196">Einige funktionale Programmiersprachen unterstützen die Änderung überhaupt nicht.</span><span class="sxs-lookup"><span data-stu-id="20e58-196">Some functional programming languages do not support mutation at all.</span></span> <span data-ttu-id="20e58-197">In F# wird sie unterstützt, ist aber nicht das Standardverhalten für Werte.</span><span class="sxs-lookup"><span data-stu-id="20e58-197">In F#, it is supported, but it is not the default behavior for values.</span></span>

<span data-ttu-id="20e58-198">Dieses Konzept erstreckt sich sogar noch weiter auf Datenstrukturen.</span><span class="sxs-lookup"><span data-stu-id="20e58-198">This concept extends even further to data structures.</span></span> <span data-ttu-id="20e58-199">In der funktionalen Programmierung weisen unveränderliche Datenstrukturen wie z. B. Sätze (und viele weitere) eine andere Implementierung auf, als Sie vielleicht anfänglich erwarten.</span><span class="sxs-lookup"><span data-stu-id="20e58-199">In functional programming, immutable data structures such as sets (and many more) have a different implementation than you might initially expect.</span></span> <span data-ttu-id="20e58-200">Konzeptionell ändert etwas wie das Hinzufügen eines Elements zu einem Satz den Satz nicht, sondern produziert einen _neuen_ Satz mit dem hinzugefügten Wert.</span><span class="sxs-lookup"><span data-stu-id="20e58-200">Conceptually, something like adding an item to a set does not change the set, it produces a _new_ set with the added value.</span></span> <span data-ttu-id="20e58-201">Im Hintergrund wird dies häufig durch eine andere Datenstruktur erreicht, die eine effiziente Nachverfolgung eines Werts ermöglicht, damit die entsprechende Darstellung der Daten als Ergebnis angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="20e58-201">Under the covers, this is often accomplished by a different data structure that allows for efficiently tracking a value so that the appropriate representation of the data can be given as a result.</span></span>

<span data-ttu-id="20e58-202">Dieser Stil des Arbeitens mit Werten und Datenstrukturen ist äußerst wichtig, da er Sie zwingt, jeden Vorgang, der etwas ändert, so zu behandeln, als schaffe er eine neue Version dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="20e58-202">This style of working with values and data structures is critical, as it forces you to treat any operation that modifies something as if it creates a new version of that thing.</span></span> <span data-ttu-id="20e58-203">Dies ermöglicht die Konsistenz von Aspekten wie Gleichheit und Vergleichbarkeit in Ihren Programmen.</span><span class="sxs-lookup"><span data-stu-id="20e58-203">This allows for things like equality and comparability to be consistent in your programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="20e58-204">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="20e58-204">Next steps</span></span>

<span data-ttu-id="20e58-205">Im nächsten Abschnitt werden Funktionen ausführlich behandelt und verschiedene Möglichkeiten untersucht, wie Sie sie in der funktionalen Programmierung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="20e58-205">The next section will thoroughly cover functions, exploring different ways you can use them in functional programming.</span></span>

<span data-ttu-id="20e58-206">[Funktionen erster Klasse](first-class-functions.md) untersucht Funktionen gründlich und zeigt Ihnen, wie Sie sie in verschiedenen Kontexten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="20e58-206">[First-class functions](first-class-functions.md) explores functions deeply, showing how you can use them in various contexts.</span></span>

## <a name="further-reading"></a><span data-ttu-id="20e58-207">Weitere nützliche Informationen</span><span class="sxs-lookup"><span data-stu-id="20e58-207">Further reading</span></span>

<span data-ttu-id="20e58-208">Die Reihe [Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) (Funktional denken) ist eine weitere großartige Ressource, um mehr über die funktionale Programmierung mit F# zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="20e58-208">The [Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) series is another great resource to learn about functional programming with F#.</span></span> <span data-ttu-id="20e58-209">Sie behandelt die Grundlagen der funktionalen Programmierung auf pragmatische und leicht lesbare Weise, wobei die Konzepte mit F#-Funktionen veranschaulicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="20e58-209">It covers fundamentals of functional programming in a pragmatic and easy-to-read way, using F# features to illustrate the concepts.</span></span>
