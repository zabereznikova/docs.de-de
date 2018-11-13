---
title: Einführung in die funktionale Programmierung mit F#
description: Lernen Sie die Grundlagen der funktionalen Programmierung in F#.
ms.date: 10/29/2018
ms.openlocfilehash: d4a9bb0cd826b41aca96e12e2bcb5aab80c18eb4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "25724477"
---
# <a name="introduction-to-functional-programming-in-f"></a><span data-ttu-id="0d068-103">Einführung in die funktionale Programmierung mit F#</span><span class="sxs-lookup"><span data-stu-id="0d068-103">Introduction to Functional Programming in F#</span></span> #

<span data-ttu-id="0d068-104">Funktionale Programmierung ist eine Art der Programmierung, die die Verwendung von Funktionen und Daten mit unveränderlicher betont.</span><span class="sxs-lookup"><span data-stu-id="0d068-104">Functional programming is a style of programming that emphasizes the use of functions and immutable data.</span></span> <span data-ttu-id="0d068-105">Typisierte funktionaler Programmierung ist funktionaler Programmierung mit statischen Typen, z. B. in Kombination mit ist F#.</span><span class="sxs-lookup"><span data-stu-id="0d068-105">Typed functional programming is when functional programming is combined with static types, such as with F#.</span></span> <span data-ttu-id="0d068-106">Die folgenden Begriffe werden in der Regel bei der funktionalen Programmierung hervorgehoben:</span><span class="sxs-lookup"><span data-stu-id="0d068-106">In general, the following concepts are emphasized in functional programming:</span></span>

* <span data-ttu-id="0d068-107">Funktionen als die primären Konstrukte, die Sie verwenden</span><span class="sxs-lookup"><span data-stu-id="0d068-107">Functions as the primary constructs you use</span></span>
* <span data-ttu-id="0d068-108">Ausdrücke anstelle von Anweisungen</span><span class="sxs-lookup"><span data-stu-id="0d068-108">Expressions instead of statements</span></span>
* <span data-ttu-id="0d068-109">Unveränderliche Werte Variablen</span><span class="sxs-lookup"><span data-stu-id="0d068-109">Immutable values over variables</span></span>
* <span data-ttu-id="0d068-110">Deklarative Programmierung häufiger über imperative Programmierung</span><span class="sxs-lookup"><span data-stu-id="0d068-110">Declarative programming over imperative programming</span></span>

<span data-ttu-id="0d068-111">In der gesamten Reihe, müssen Sie untersuchen, Konzepte und Muster in die funktionale Programmierung mit F#.</span><span class="sxs-lookup"><span data-stu-id="0d068-111">Throughout this series, you'll explore concepts and patterns in functional programming using F#.</span></span> <span data-ttu-id="0d068-112">Dabei erfahren Sie, einige F# zu.</span><span class="sxs-lookup"><span data-stu-id="0d068-112">Along the way, you'll learn some F# too.</span></span>

## <a name="terminology"></a><span data-ttu-id="0d068-113">Terminologie</span><span class="sxs-lookup"><span data-stu-id="0d068-113">Terminology</span></span>

<span data-ttu-id="0d068-114">Funktionale Programmierung, wie die anderen Paradigmen, enthält ein Vokabular, das Sie irgendwann einmal um zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="0d068-114">Functional programming, like other programming paradigms, comes with a vocabulary that you will eventually need to learn.</span></span> <span data-ttu-id="0d068-115">Hier sind einige allgemeine Begriffe, die Sie ständig sehen:</span><span class="sxs-lookup"><span data-stu-id="0d068-115">Here are some common terms you'll see all of the time:</span></span>

* <span data-ttu-id="0d068-116">**Funktion** -Funktion ist ein Konstrukt, das erzeugt eine Ausgabe, wenn eine Eingabe angegeben.</span><span class="sxs-lookup"><span data-stu-id="0d068-116">**Function** - A function is a construct that will produce an output when given an input.</span></span> <span data-ttu-id="0d068-117">Formeller gesehen, es _ordnet_ ein Element aus einem zu einer anderen Gruppe festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0d068-117">More formally, it _maps_ an item from one set to another set.</span></span> <span data-ttu-id="0d068-118">Diese formalismus ist in die konkreten in vielerlei Hinsicht transformiert, vor allem bei Verwendung von Funktionen, die ausgeführt werden Auflistungen von Daten.</span><span class="sxs-lookup"><span data-stu-id="0d068-118">This formalism is lifted into the concrete in many ways, especially when using functions that operate on collections of data.</span></span> <span data-ttu-id="0d068-119">Es ist die grundlegende (und wichtige) Konzept bei der funktionalen Programmierung.</span><span class="sxs-lookup"><span data-stu-id="0d068-119">It is the most basic (and important) concept in functional programming.</span></span> 
* <span data-ttu-id="0d068-120">**Ausdruck** -ein Ausdruck ist ein Konstrukt in Code, der einen Wert erzeugt.</span><span class="sxs-lookup"><span data-stu-id="0d068-120">**Expression** - An expression is a construct in code that produces a value.</span></span> <span data-ttu-id="0d068-121">In F#, muss dieser Wert gebunden oder explizit ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="0d068-121">In F#, this value must be bound or explicitly ignored.</span></span> <span data-ttu-id="0d068-122">Ein Ausdruck kann einfach durch einen Funktionsaufruf ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="0d068-122">An expression can be trivially replaced by a function call.</span></span>
* <span data-ttu-id="0d068-123">**Reinheit** -Reinheit ist eine Eigenschaft einer Funktion, sodass der Rückgabewert immer für den gleichen Argumenten identisch ist und dass seine Bewertung keine Nebeneffekte hat.</span><span class="sxs-lookup"><span data-stu-id="0d068-123">**Purity** - Purity is a property of a function such that its return value is always the same for the same arguments, and that its evaluation has no side effects.</span></span> <span data-ttu-id="0d068-124">Eine reine Funktion hängt gänzlich von den Argumenten.</span><span class="sxs-lookup"><span data-stu-id="0d068-124">A pure function depends entirely on its arguments.</span></span>
* <span data-ttu-id="0d068-125">**Referenzieller Transparenz** -referenzieller Transparenz ist eine Eigenschaft von Ausdrücken aus, sodass sie mit ihrer Ausgabe ersetzt werden können, ohne ein Programmverhalten.</span><span class="sxs-lookup"><span data-stu-id="0d068-125">**Referential Transparency** - Referential Transparency is a property of expressions such that they can be replaced with their output without affecting a program's behavior.</span></span>
* <span data-ttu-id="0d068-126">**Unveränderlichkeit** -Immutabilität bedeutet, dass ein Wert kann nicht direkt geändert.</span><span class="sxs-lookup"><span data-stu-id="0d068-126">**Immutability** - Immutability means that a value cannot be changed in-place.</span></span> <span data-ttu-id="0d068-127">Dies ist im Gegensatz zu Variablen, die direktes ändern können.</span><span class="sxs-lookup"><span data-stu-id="0d068-127">This is in contrast with variables, which can change in place.</span></span>

## <a name="examples"></a><span data-ttu-id="0d068-128">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0d068-128">Examples</span></span>

<span data-ttu-id="0d068-129">Die folgenden Beispiele veranschaulichen diese kernbegriffe.</span><span class="sxs-lookup"><span data-stu-id="0d068-129">The following examples demonstrate these core concepts.</span></span>

### <a name="functions"></a><span data-ttu-id="0d068-130">Funktionen</span><span class="sxs-lookup"><span data-stu-id="0d068-130">Functions</span></span>

<span data-ttu-id="0d068-131">Die meisten allgemeinen und grundlegenden Konstrukt bei der funktionalen Programmierung ist die Funktion.</span><span class="sxs-lookup"><span data-stu-id="0d068-131">The most common and fundamental construct in functional programming is the function.</span></span> <span data-ttu-id="0d068-132">Hier ist eine einfache Funktion, die eine ganze Zahl 1 hinzufügt:</span><span class="sxs-lookup"><span data-stu-id="0d068-132">Here's a simple function that adds 1 to an integer:</span></span>

```fsharp
let addOne x = x + 1
```

<span data-ttu-id="0d068-133">Die Typsignatur lautet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="0d068-133">Its type signature is as follows:</span></span>

```fsharp
val addOne: x:int -> int
```

<span data-ttu-id="0d068-134">Die Signatur gelesen werden kann, wie "`addOne` akzeptiert eine `int` mit dem Namen `x` und erzeugt eine `int`".</span><span class="sxs-lookup"><span data-stu-id="0d068-134">The signature can be read as, "`addOne` accepts an `int` named `x` and will produce an `int`".</span></span> <span data-ttu-id="0d068-135">Formeller gesehen `addOne` ist _Zuordnung_ einen Wert aus dem Satz von ganzen Zahlen auf den Satz von ganzen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="0d068-135">More formally, `addOne` is _mapping_ a value from the set of integers to the set of integers.</span></span> <span data-ttu-id="0d068-136">Die `->` Token gibt an, diese Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="0d068-136">The `->` token signifies this mapping.</span></span> <span data-ttu-id="0d068-137">In F#, in der Regel sehen Sie sich die Signatur für die Sie bekommen eine Vorstellung für welche Aktion er ausführt.</span><span class="sxs-lookup"><span data-stu-id="0d068-137">In F#, you can usually look at the function signature to get a sense for what it does.</span></span>

<span data-ttu-id="0d068-138">Warum also ist die Signatur wichtig?</span><span class="sxs-lookup"><span data-stu-id="0d068-138">So, why is the signature important?</span></span> <span data-ttu-id="0d068-139">In typisierte, funktionale Programmierung, die Implementierung einer Funktion wird häufig weniger wichtiger als die tatsächliche Typsignatur!</span><span class="sxs-lookup"><span data-stu-id="0d068-139">In typed functional programming, the implementation of a function is often less important than the actual type signature!</span></span> <span data-ttu-id="0d068-140">Die Tatsache, `addOne` fügt der Wert 1 in eine ganze Zahl ist interessant, zur Laufzeit jedoch beim Konstruieren Sie ein Programm, die Tatsache, die akzeptiert und gibt eine `int` ist, was darüber informiert, wie Sie diese Funktion tatsächlich verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="0d068-140">The fact that `addOne` adds the value 1 to an integer is interesting at runtime, but when you are constructing a program, the fact that it accepts and returns an `int` is what informs how you will actually use this function.</span></span> <span data-ttu-id="0d068-141">Darüber hinaus sobald Sie diese Funktion ordnungsgemäß (in Bezug auf seine Typsignatur) verwenden, Diagnose von Problemen kann erfolgen nur innerhalb des Texts der `addOne` Funktion.</span><span class="sxs-lookup"><span data-stu-id="0d068-141">Furthermore, once you use this function correctly (with respect to its type signature), diagnosing any problems can be done only within the body of the `addOne` function.</span></span> <span data-ttu-id="0d068-142">Dies ist der Grund hinter typisierte funktionale Programmierung.</span><span class="sxs-lookup"><span data-stu-id="0d068-142">This is the impetus behind typed functional programming.</span></span>

### <a name="expressions"></a><span data-ttu-id="0d068-143">Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="0d068-143">Expressions</span></span>

<span data-ttu-id="0d068-144">Ausdrücke sind Konstrukte, die zu einem Wert ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="0d068-144">Expressions are constructs that evaluate to a value.</span></span> <span data-ttu-id="0d068-145">Im Gegensatz zu Anweisungen, die eine Aktion ausführen zu können, können Ausdrücke betrachtet werden, der eine Aktion, die einen Wert zurück gibt.</span><span class="sxs-lookup"><span data-stu-id="0d068-145">In contrast to statements, which perform an action, expressions can be thought of performing an action that gives back a value.</span></span> <span data-ttu-id="0d068-146">Ausdrücke werden fast immer zugunsten von Anweisungen, die bei der funktionalen Programmierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d068-146">Expressions are almost always used in favor of statements in functional programming.</span></span>

<span data-ttu-id="0d068-147">Betrachten Sie die vorherige Funktion `addOne`.</span><span class="sxs-lookup"><span data-stu-id="0d068-147">Consider the previous function, `addOne`.</span></span> <span data-ttu-id="0d068-148">Der Text der `addOne` ist ein Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="0d068-148">The body of `addOne` is an expression:</span></span>

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

<span data-ttu-id="0d068-149">Es ist das Ergebnis dieses Ausdrucks, das den Ergebnistyp des definiert die `addOne` Funktion.</span><span class="sxs-lookup"><span data-stu-id="0d068-149">It is the result of this expression that defines the result type of the `addOne` function.</span></span> <span data-ttu-id="0d068-150">Beispielsweise konnte der Ausdruck, der diese Funktion bildet geändert werden, um einen anderen Typ, z. B. eine `string`:</span><span class="sxs-lookup"><span data-stu-id="0d068-150">For example, the expression that makes up this function could be changed to be a different type, such as a `string`:</span></span>

```fsharp
let addOne x = x.ToString() + "1"
```

<span data-ttu-id="0d068-151">Die Signatur der Funktion lautet jetzt:</span><span class="sxs-lookup"><span data-stu-id="0d068-151">The signature of the function is now:</span></span>

```fsharp
val addOne: x:'a -> string
```

<span data-ttu-id="0d068-152">Seit jeden Typ im F# können `ToString()` aufgerufen, der Typ des `x` wurde als generisches (namens [automatische Verallgemeinerung](../language-reference/generics/automatic-generalization.md)), und der resultierende Typ ist ein `string`.</span><span class="sxs-lookup"><span data-stu-id="0d068-152">Since any type in F# can have `ToString()` called on it, the type of `x` has been made generic (called [Automatic Generalization](../language-reference/generics/automatic-generalization.md)), and the resultant type is a `string`.</span></span>

<span data-ttu-id="0d068-153">Ausdrücke sind nicht nur die Texte der Funktionen.</span><span class="sxs-lookup"><span data-stu-id="0d068-153">Expressions are not just the bodies of functions.</span></span> <span data-ttu-id="0d068-154">Sie können Ausdrücke verwenden, die einen Wert zu erzeugen, die, den Sie an anderer Stelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="0d068-154">You can have expressions that produce a value you use elsewhere.</span></span> <span data-ttu-id="0d068-155">Eine allgemeine er `if`:</span><span class="sxs-lookup"><span data-stu-id="0d068-155">A common one is `if`:</span></span>

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

<span data-ttu-id="0d068-156">Die `if` -Ausdruck liefert einen Wert mit dem `result`.</span><span class="sxs-lookup"><span data-stu-id="0d068-156">The `if` expression produces a value called `result`.</span></span> <span data-ttu-id="0d068-157">Beachten Sie, die Sie auslassen `result` vollständig, wodurch die `if` Ausdruck den Text von der `addOneIfOdd` Funktion.</span><span class="sxs-lookup"><span data-stu-id="0d068-157">Note that you could omit `result` entirely, making the `if` expression the body of the `addOneIfOdd` function.</span></span> <span data-ttu-id="0d068-158">Das wichtigste über Ausdrücke zu merken ist, dass sie einen Wert erzeugen.</span><span class="sxs-lookup"><span data-stu-id="0d068-158">The key thing to remember about expressions is that they produce a value.</span></span>

<span data-ttu-id="0d068-159">Es ist ein spezieller Typ, `unit`, die verwendet wird, wenn nichts zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0d068-159">There is a special type, `unit`, that is used when there is nothing to return.</span></span> <span data-ttu-id="0d068-160">Betrachten Sie beispielsweise diese einfache Funktion:</span><span class="sxs-lookup"><span data-stu-id="0d068-160">For example, consider this simple function:</span></span>

```fsharp
let printString (str: string) =
    printfn "String is: %s" s
```

<span data-ttu-id="0d068-161">Die Signatur sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="0d068-161">The signature looks like this:</span></span>

```fsharp
val printString: str:string -> unit
```

<span data-ttu-id="0d068-162">Die `unit` Typ gibt an, dass keine tatsächlichen Wert zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0d068-162">The `unit` type indicates that there is no actual value being returned.</span></span> <span data-ttu-id="0d068-163">Dies ist nützlich, wenn Sie eine Routine verfügen, die muss "funktionieren" auch wenn kein Wert als Ergebnis dieser Arbeit zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0d068-163">This is useful when you have a routine that must "do work" despite having no value to return as a result of that work.</span></span>

<span data-ttu-id="0d068-164">Dies ist in den starken Kontrast zu imperativen Programmierung, in denen die entsprechende `if` Konstrukt ist eine Anweisung, und die Werte erzeugen erfolgt häufig mit veränderliche Variablen.</span><span class="sxs-lookup"><span data-stu-id="0d068-164">This is in sharp contrast to imperative programming, where the equivalent `if` construct is a statement, and producing values is often done with mutating variables.</span></span> <span data-ttu-id="0d068-165">Z. B. in C#, der Code wie folgt geschrieben werden kann:</span><span class="sxs-lookup"><span data-stu-id="0d068-165">For example, in C#, the code might be written like this:</span></span>

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

<span data-ttu-id="0d068-166">Es ist erwähnenswert, die C# und anderen c-Sprachen unterstützen die [ternärer Ausdruck](../../csharp/language-reference/operators/conditional-operator.md), wodurch für die bedingte Programmierung auf Ausdrücken beruhende.</span><span class="sxs-lookup"><span data-stu-id="0d068-166">It's worth noting that C# and other C-style languages do support the [ternary expression](../../csharp/language-reference/operators/conditional-operator.md), which allows for expression-based conditional programming.</span></span>

<span data-ttu-id="0d068-167">Bei der funktionalen Programmierung ist es nur selten, dass die Werte mit Anweisungen zu verändern.</span><span class="sxs-lookup"><span data-stu-id="0d068-167">In functional programming, it is rare to mutate values with statements.</span></span> <span data-ttu-id="0d068-168">Obwohl einige funktionalen Sprachen Anweisungen und Mutation unterstützen, ist es nicht üblich, dass diese Konzepte bei der funktionalen Programmierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d068-168">Although some functional languages support statements and mutation, it is not common to use these concepts in functional programming.</span></span>

### <a name="pure-functions"></a><span data-ttu-id="0d068-169">Reine Funktionen</span><span class="sxs-lookup"><span data-stu-id="0d068-169">Pure functions</span></span>

<span data-ttu-id="0d068-170">Wie bereits erwähnte, reine Funktionen sind Funktionen, die:</span><span class="sxs-lookup"><span data-stu-id="0d068-170">As previously mentioned, pure functions are functions that:</span></span>

* <span data-ttu-id="0d068-171">Überprüfen Sie immer auf den gleichen Wert für die gleiche Eingabe.</span><span class="sxs-lookup"><span data-stu-id="0d068-171">Always evaluate to the same value for the same input.</span></span>
* <span data-ttu-id="0d068-172">Haben Sie keine nachteiligen Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="0d068-172">Have no side effects.</span></span>

<span data-ttu-id="0d068-173">Es ist hilfreich, mathematische Funktionen, die in diesem Zusammenhang zu betrachten.</span><span class="sxs-lookup"><span data-stu-id="0d068-173">It is helpful to think of mathematical functions in this context.</span></span> <span data-ttu-id="0d068-174">In der Mathematik Funktionen nur abhängig von ihrer Argumente und müssen keine keine Nebeneffekte.</span><span class="sxs-lookup"><span data-stu-id="0d068-174">In mathematics, functions depend only on their arguments and do not have any side effects.</span></span> <span data-ttu-id="0d068-175">In der mathematischen Funktion `f(x) = x + 1`, den Wert der `f(x)` hängt nur von den Wert der `x`.</span><span class="sxs-lookup"><span data-stu-id="0d068-175">In the mathematical function `f(x) = x + 1`, the value of `f(x)` depends only on the value of `x`.</span></span> <span data-ttu-id="0d068-176">Reine Funktionen bei der funktionalen Programmierung sind die gleiche Weise.</span><span class="sxs-lookup"><span data-stu-id="0d068-176">Pure functions in functional programming are the same way.</span></span>

<span data-ttu-id="0d068-177">Wenn Sie eine reine Funktion schreiben, muss die Funktion nur abhängig von den Argumenten und nicht ausgeführt werden alle Aktionen, die einen Nebeneffekt führt.</span><span class="sxs-lookup"><span data-stu-id="0d068-177">When writing a pure function, the function must depend only on its arguments and not perform any action that results in a side effect.</span></span>

<span data-ttu-id="0d068-178">Hier ist ein Beispiel einer nicht reine Funktion auf, da sie global und änderbaren Zustand abhängt:</span><span class="sxs-lookup"><span data-stu-id="0d068-178">Here is an example of a non-pure function because it depends on global, mutable state:</span></span>

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

<span data-ttu-id="0d068-179">Die `addOneToValue` -Funktion ist deutlich unsauberen, da `value` kann jederzeit auf einen anderen Wert als 1 geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0d068-179">The `addOneToValue` function is clearly impure, because `value` could be changed at any time to have a different value than 1.</span></span> <span data-ttu-id="0d068-180">Dieses Muster der abhängig von einem globalen Wert ist, die bei der funktionalen Programmierung vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="0d068-180">This pattern of depending on a global value is to be avoided in functional programming.</span></span>

<span data-ttu-id="0d068-181">Hier ist ein weiteres Beispiel für eine nicht reine Funktion, da sie einen Nebeneffekt ausführt:</span><span class="sxs-lookup"><span data-stu-id="0d068-181">Here is another example of a non-pure function, because it performs a side effect:</span></span>

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

<span data-ttu-id="0d068-182">Obwohl diese Funktion nicht von einem globalen Wert abhängig ist, schreibt er den Wert der `x` an die Ausgabe des Programms.</span><span class="sxs-lookup"><span data-stu-id="0d068-182">Although this function does not depend on a global value, it writes the value of `x` to the output of the program.</span></span> <span data-ttu-id="0d068-183">Obwohl es nichts wirklich falsch ist, dabei, bedeutet dies, dass diese Funktion keine reine ist.</span><span class="sxs-lookup"><span data-stu-id="0d068-183">Although there is nothing inherently wrong with doing this, it does mean that the function is not pure.</span></span>

<span data-ttu-id="0d068-184">Entfernen der `printfn` Anweisung schließlich ist die Funktion rein:</span><span class="sxs-lookup"><span data-stu-id="0d068-184">Removing the `printfn` statement finally makes the function pure:</span></span>

```fsharp
let addOneToValue x = x + 1
```

<span data-ttu-id="0d068-185">Obwohl diese Funktion nicht grundsätzlich ist _besser_ als die vorherige Version mit der `printfn` -Anweisung, dies garantiert, dass alle mit dieser Funktion ist einen Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0d068-185">Although this function is not inherently _better_ than the previous version with the `printfn` statement, it does guarantee that all this function does is return a value.</span></span> <span data-ttu-id="0d068-186">Aufrufen von dieser Funktion einmal oder 1 Milliarden Mal wird noch Ergebnis in das gleiche: nur einen Wert erzeugt.</span><span class="sxs-lookup"><span data-stu-id="0d068-186">Calling this function once or 1 billion times will still result in the same thing: just producing a value.</span></span> <span data-ttu-id="0d068-187">Diese Vorhersagbarkeit ist hilfreich bei der funktionalen Programmierung, da dies bedeutet, dass reiner Funktion Referenziell transparent ist.</span><span class="sxs-lookup"><span data-stu-id="0d068-187">This predictability is valuable in functional programming, as it means that any pure function is referentially transparent.</span></span>

### <a name="referential-transparency"></a><span data-ttu-id="0d068-188">Referenzieller Transparenz</span><span class="sxs-lookup"><span data-stu-id="0d068-188">Referential Transparency</span></span>

<span data-ttu-id="0d068-189">Referenzieller Transparenz ist eine Eigenschaft der Ausdrücke und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="0d068-189">Referential transparency is a property of expressions and functions.</span></span> <span data-ttu-id="0d068-190">Für einen Ausdruck Referenziell transparent sein müssen sie mit den sich ergebenden Wert ersetzt werden, ohne das Programm Verhalten zu ändern können.</span><span class="sxs-lookup"><span data-stu-id="0d068-190">For an expression to be referentially transparent, it must be able to be replaced with its resulting value without changing the program's behavior.</span></span> <span data-ttu-id="0d068-191">Alle reine Funktionen sind Referenziell transparent.</span><span class="sxs-lookup"><span data-stu-id="0d068-191">All pure functions are referentially transparent.</span></span>

<span data-ttu-id="0d068-192">Wie bei reinen Funktionen kann es hilfreich, referenzieller Transparenz aus mathematischer Sicht vorstellen sein.</span><span class="sxs-lookup"><span data-stu-id="0d068-192">As with pure functions, it can be helpful to think of referential transparency from a mathematical perspective.</span></span> <span data-ttu-id="0d068-193">In der mathematischen Ausdruck `y = f(x)`, `f(x)` kann durch das Ergebnis der Funktion ersetzt werden und sie werden gleich `y`.</span><span class="sxs-lookup"><span data-stu-id="0d068-193">In the mathematical expression `y = f(x)`, `f(x)` can be replaced by the result of the function and it will still be equal to `y`.</span></span> <span data-ttu-id="0d068-194">Dies gilt gleichermaßen für referenzieller Transparenz bei der funktionalen Programmierung.</span><span class="sxs-lookup"><span data-stu-id="0d068-194">This is equally true for referential transparency in functional programming.</span></span>

<span data-ttu-id="0d068-195">Rufen Sie die zuvor definierte `addOneIfOdd` zweimal funktionieren:</span><span class="sxs-lookup"><span data-stu-id="0d068-195">Consider calling the previously defined `addOneIfOdd` function twice:</span></span>

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

let res1 = addOneIffOdd 1 // Produces 2
let res2 = addOneIffOdd 2 // Produces 2
```

<span data-ttu-id="0d068-196">Wir können alle Funktionsaufrufe durch Ersetzen der Hauptteil der Funktion, und Ersetzen Sie dabei das Argument `input` mit einzelnen Werten:</span><span class="sxs-lookup"><span data-stu-id="0d068-196">We can replace each function call with the function body, substituting the argument `input` with each value:</span></span>

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

let res1 =
    let result =
        if isOdd 1 then
            1 + 1
        else
            1

    result
let res2 =
    let result =
        if isOdd 2 then
            2 + 1
        else
            2

    result
```

<span data-ttu-id="0d068-197">Beide `res1` und `res2` denselben Wert haben, als ob die Funktion aufgerufen wurde, gibt an, dass, `addOneIfOdd` Referenziell transparent ist.</span><span class="sxs-lookup"><span data-stu-id="0d068-197">Both `res1` and `res2` have the same value as if the function was called, indicating that `addOneIfOdd` is referentially transparent!</span></span>

<span data-ttu-id="0d068-198">Darüber hinaus muss eine Funktion keine reinen auch Referenziell transparent sein.</span><span class="sxs-lookup"><span data-stu-id="0d068-198">Additionally, a function doesn't have to be pure to also be referentially transparent.</span></span> <span data-ttu-id="0d068-199">Erwägen Sie eine vorherige Definition von `addOneTovalue`:</span><span class="sxs-lookup"><span data-stu-id="0d068-199">Consider a previous definition of  `addOneTovalue`:</span></span>

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

<span data-ttu-id="0d068-200">Jeder Aufruf dieser Funktion kann auch durch Text ersetzt werden, und die Punkte erfolgt jedes Mal:</span><span class="sxs-lookup"><span data-stu-id="0d068-200">Any call to this function can also be replaced by its body and the same things will happen each time:</span></span>

* <span data-ttu-id="0d068-201">Der Wert, bevor Sie hinzugefügt wird, wird an die Ausgabe ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="0d068-201">The value, prior to being added to, is printed to the output</span></span>
* <span data-ttu-id="0d068-202">Der Wert hinzugefügt wird "1" wurde "</span><span class="sxs-lookup"><span data-stu-id="0d068-202">The value has 1 added to it</span></span>

<span data-ttu-id="0d068-203">Beim Programmieren in F#, es ist häufig referenzieller Transparenz, die das Ziel, anstatt Reinheit ist.</span><span class="sxs-lookup"><span data-stu-id="0d068-203">When programming in F#, it is often referential transparency that is the goal, rather than purity.</span></span> <span data-ttu-id="0d068-204">Es ist jedoch weiterhin empfohlen, die reine Funktionen geschrieben werden, wenn möglich.</span><span class="sxs-lookup"><span data-stu-id="0d068-204">However, it is still good practice to write pure functions when you can.</span></span>

### <a name="immutability"></a><span data-ttu-id="0d068-205">Unveränderlichkeit</span><span class="sxs-lookup"><span data-stu-id="0d068-205">Immutability</span></span>

<span data-ttu-id="0d068-206">Schließlich ist einer der wichtigsten Konzepte, typisierte, funktionale Programmierung Unveränderlichkeit.</span><span class="sxs-lookup"><span data-stu-id="0d068-206">Finally, one of the most fundamental concepts of typed functional programming is immutability.</span></span> <span data-ttu-id="0d068-207">In F#, alle Werte sind standardmäßig nicht verändert werden.</span><span class="sxs-lookup"><span data-stu-id="0d068-207">In F#, all values are immutable by default.</span></span> <span data-ttu-id="0d068-208">Das bedeutet, dass sie mutiert werden können, es sei denn, Sie explizit als änderbaren markieren.</span><span class="sxs-lookup"><span data-stu-id="0d068-208">That means they cannot be mutated in-place unless you explicitly mark them as mutable.</span></span>

<span data-ttu-id="0d068-209">In der Praxis bedeutet arbeiten mit unveränderlichen Werten an, dass Sie Ihren Ansatz mit der Programmierung von "muss ich etwas ändern" ändern, auf "Ich möchte einen neuen Wert zu erzeugen.".</span><span class="sxs-lookup"><span data-stu-id="0d068-209">In practice, working with immutable values means that you change your approach to programming from, "I need to change something", to "I need to produce a new value".</span></span>

<span data-ttu-id="0d068-210">Hinzufügen von 1 auf einen Wert bedeutet beispielsweise, erzeugen einen neuen Wert, der nicht mutierende der vorhandenen Dateigruppe:</span><span class="sxs-lookup"><span data-stu-id="0d068-210">For example, adding 1 to a value means producing a new value, not mutating the existing one:</span></span>

```fsharp
let value = 1
let secondValue = value + 1
```

<span data-ttu-id="0d068-211">In F#, der folgende Code macht **nicht** geändert wird, die `value` funktionieren; stattdessen wird eine Überprüfung auf Gleichheit:</span><span class="sxs-lookup"><span data-stu-id="0d068-211">In F#, the following code does **not** mutate the `value` function; instead, it performs an equality check:</span></span>

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

<span data-ttu-id="0d068-212">Einige funktionalen Programmiersprachen unterstützen überhaupt keine Veränderung.</span><span class="sxs-lookup"><span data-stu-id="0d068-212">Some functional programming languages do not support mutation at all.</span></span> <span data-ttu-id="0d068-213">In F#, wird unterstützt, aber es ist nicht das Standardverhalten für Werte.</span><span class="sxs-lookup"><span data-stu-id="0d068-213">In F#, it is supported, but it is not the default behavior for values.</span></span>

<span data-ttu-id="0d068-214">Dieses Konzept wird auch weiter auf Datenstrukturen erweitert.</span><span class="sxs-lookup"><span data-stu-id="0d068-214">This concept extends even further to data structures.</span></span> <span data-ttu-id="0d068-215">Bei der funktionalen Programmierung erwarten wie z. B. Sätze (und viele mehr) haben eine andere Implementierung als Anfangs vielleicht unveränderliche Datenstrukturen.</span><span class="sxs-lookup"><span data-stu-id="0d068-215">In functional programming, immutable data structures such as sets (and many more) have a different implementation than you might initially expect.</span></span> <span data-ttu-id="0d068-216">Konzeptionell etwas Hinzufügen eines Elements zu einer Gruppe die Gruppe nicht geändert wird, erzeugt es ein _neue_ mit den hinzugefügten Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0d068-216">Conceptually, something like adding an item to a set does not change the set, it produces a _new_ set with the added value.</span></span> <span data-ttu-id="0d068-217">Im Hintergrund wird dies häufig durch eine andere Datenstruktur erreicht, die ermöglicht, die zum Nachverfolgen von effizient eines Werts, damit die entsprechende Darstellung der Daten daher angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="0d068-217">Under the covers, this is often accomplished by a different data structure that allows for efficiently tracking a value so that the appropriate representation of the data can be given as a result.</span></span>

<span data-ttu-id="0d068-218">Diese Art der Arbeiten mit Werten und Datenstrukturen ist wichtig, wie sie erzwingt, einen Vorgang behandelt werden, der etwas ändert dass, als ob erstellt eine neue Version des ab.</span><span class="sxs-lookup"><span data-stu-id="0d068-218">This style of working with values and data structures is critical, as it forces you to treat any operation that modifies something as if it creates a new version of that thing.</span></span> <span data-ttu-id="0d068-219">Dies ermöglicht z. B. auf Gleichheit und Vergleichbarkeit in Ihren Programmen konsistent sein.</span><span class="sxs-lookup"><span data-stu-id="0d068-219">This allows for things like equality and comparability to be consistent in your programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0d068-220">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0d068-220">Next steps</span></span>

<span data-ttu-id="0d068-221">Im nächste Abschnitt behandelt gründlich Funktionen, untersuchen verschiedene Möglichkeiten, die Sie sie bei der funktionalen Programmierung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0d068-221">The next section will thoroughly cover functions, exploring different ways you can use them in functional programming.</span></span>

<span data-ttu-id="0d068-222">[Funktionen](first-class-functions.md) tief, untersucht Funktionen zeigt, wie Sie diese in verschiedenen Kontexten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0d068-222">[First-class functions](first-class-functions.md) explores functions deeply, showing how you can use them in various contexts.</span></span>

## <a name="further-reading"></a><span data-ttu-id="0d068-223">Weiterführende Themen</span><span class="sxs-lookup"><span data-stu-id="0d068-223">Further reading</span></span>

<span data-ttu-id="0d068-224">Die [funktional denken](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) -Reihe ist eine weitere hervorragende Ressource funktionale Programmierung mit Informationen F#.</span><span class="sxs-lookup"><span data-stu-id="0d068-224">The [Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) series is another great resource to learn about functional programming with F#.</span></span> <span data-ttu-id="0d068-225">Hierin sind die Grundlagen der funktionalen Programmierung pragmatischen und leicht lesbaren Weise mit F# Features zum Veranschaulichen der Konzepte.</span><span class="sxs-lookup"><span data-stu-id="0d068-225">It covers fundamentals of functional programming in a pragmatic and easy-to-read way, using F# features to illustrate the concepts.</span></span>