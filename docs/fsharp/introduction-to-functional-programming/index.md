---
title: Einführung in die funktionale Programmierung mit F#
description: Lernen Sie die Grundlagen der funktionalen F#Programmierung in kennen.
ms.date: 10/29/2018
ms.openlocfilehash: e1a0edc61dbe13012c48e166d490e22ebc70d6a0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424709"
---
# <a name="introduction-to-functional-programming-in-f"></a><span data-ttu-id="84707-103">Einführung in die funktionale Programmierung in F\#</span><span class="sxs-lookup"><span data-stu-id="84707-103">Introduction to Functional Programming in F\#</span></span>

<span data-ttu-id="84707-104">Die funktionale Programmierung ist ein Programmierstil, der die Verwendung von Funktionen und unveränderlichen Daten betont.</span><span class="sxs-lookup"><span data-stu-id="84707-104">Functional programming is a style of programming that emphasizes the use of functions and immutable data.</span></span> <span data-ttu-id="84707-105">Die typisierte funktionale Programmierung ist, wenn die funktionale Programmierung mit statischen Typen kombiniert wird F#, z. b. mit.</span><span class="sxs-lookup"><span data-stu-id="84707-105">Typed functional programming is when functional programming is combined with static types, such as with F#.</span></span> <span data-ttu-id="84707-106">Im Allgemeinen werden die folgenden Konzepte bei der funktionalen Programmierung hervorgehoben:</span><span class="sxs-lookup"><span data-stu-id="84707-106">In general, the following concepts are emphasized in functional programming:</span></span>

* <span data-ttu-id="84707-107">Funktionen als primäre Konstrukte, die Sie verwenden</span><span class="sxs-lookup"><span data-stu-id="84707-107">Functions as the primary constructs you use</span></span>
* <span data-ttu-id="84707-108">Ausdrücke anstelle von Anweisungen</span><span class="sxs-lookup"><span data-stu-id="84707-108">Expressions instead of statements</span></span>
* <span data-ttu-id="84707-109">Unveränderliche Werte für Variablen</span><span class="sxs-lookup"><span data-stu-id="84707-109">Immutable values over variables</span></span>
* <span data-ttu-id="84707-110">Deklarative Programmierung über imperative Programmierung</span><span class="sxs-lookup"><span data-stu-id="84707-110">Declarative programming over imperative programming</span></span>

<span data-ttu-id="84707-111">In dieser Reihe werden Konzepte und Muster der funktionalen Programmierung mithilfe F#von untersucht.</span><span class="sxs-lookup"><span data-stu-id="84707-111">Throughout this series, you'll explore concepts and patterns in functional programming using F#.</span></span> <span data-ttu-id="84707-112">Dabei lernen Sie auch etwas F# kennen.</span><span class="sxs-lookup"><span data-stu-id="84707-112">Along the way, you'll learn some F# too.</span></span>

## <a name="terminology"></a><span data-ttu-id="84707-113">Terminologie</span><span class="sxs-lookup"><span data-stu-id="84707-113">Terminology</span></span>

<span data-ttu-id="84707-114">Die funktionale Programmierung, wie andere Programmierparadigmen, enthält ein Vokabular, das Sie schließlich erlernen müssen.</span><span class="sxs-lookup"><span data-stu-id="84707-114">Functional programming, like other programming paradigms, comes with a vocabulary that you will eventually need to learn.</span></span> <span data-ttu-id="84707-115">Im folgenden finden Sie einige gängige Begriffe, die Sie in der gesamten Zeit sehen werden:</span><span class="sxs-lookup"><span data-stu-id="84707-115">Here are some common terms you'll see all of the time:</span></span>

* <span data-ttu-id="84707-116">**Function** : eine Funktion ist ein Konstrukt, das eine Ausgabe erzeugt, wenn eine Eingabe angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="84707-116">**Function** - A function is a construct that will produce an output when given an input.</span></span> <span data-ttu-id="84707-117">Formal wird ein Element aus einem _Satz einem anderen_ Satz zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="84707-117">More formally, it _maps_ an item from one set to another set.</span></span> <span data-ttu-id="84707-118">Diese Formalität wird in vielerlei Hinsicht auf den konkreten angehoben, insbesondere bei der Verwendung von Funktionen, die auf Daten Auflistungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="84707-118">This formalism is lifted into the concrete in many ways, especially when using functions that operate on collections of data.</span></span> <span data-ttu-id="84707-119">Es ist das grundlegendste (und wichtigste) Konzept bei der funktionalen Programmierung.</span><span class="sxs-lookup"><span data-stu-id="84707-119">It is the most basic (and important) concept in functional programming.</span></span>
* <span data-ttu-id="84707-120">**Ausdruck** : ein Ausdruck ist ein Konstrukt in Code, der einen Wert erzeugt.</span><span class="sxs-lookup"><span data-stu-id="84707-120">**Expression** - An expression is a construct in code that produces a value.</span></span> <span data-ttu-id="84707-121">In F#muss dieser Wert gebunden oder explizit ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="84707-121">In F#, this value must be bound or explicitly ignored.</span></span> <span data-ttu-id="84707-122">Ein Ausdruck kann trivial durch einen Funktions aufzurufen ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="84707-122">An expression can be trivially replaced by a function call.</span></span>
* <span data-ttu-id="84707-123">**Purity** -Purity ist eine Eigenschaft einer Funktion, sodass Ihr Rückgabewert für dieselben Argumente immer identisch ist und die Auswertung keine Nebeneffekte hat.</span><span class="sxs-lookup"><span data-stu-id="84707-123">**Purity** - Purity is a property of a function such that its return value is always the same for the same arguments, and that its evaluation has no side effects.</span></span> <span data-ttu-id="84707-124">Eine reine Funktion hängt vollständig von ihren Argumenten ab.</span><span class="sxs-lookup"><span data-stu-id="84707-124">A pure function depends entirely on its arguments.</span></span>
* <span data-ttu-id="84707-125">**Referenzielle Transparenz** : referentielle Transparenz ist eine Eigenschaft von Ausdrücken, die Sie durch ihre Ausgabe ersetzen können, ohne das Verhalten eines Programms zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="84707-125">**Referential Transparency** - Referential Transparency is a property of expressions such that they can be replaced with their output without affecting a program's behavior.</span></span>
* <span data-ttu-id="84707-126">**Unveränderlichkeit** : Unveränderlichkeit bedeutet, dass ein Wert nicht direkt geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="84707-126">**Immutability** - Immutability means that a value cannot be changed in-place.</span></span> <span data-ttu-id="84707-127">Dies steht im Gegensatz zu Variablen, die sich direkt ändern können.</span><span class="sxs-lookup"><span data-stu-id="84707-127">This is in contrast with variables, which can change in place.</span></span>

## <a name="examples"></a><span data-ttu-id="84707-128">Beispiele</span><span class="sxs-lookup"><span data-stu-id="84707-128">Examples</span></span>

<span data-ttu-id="84707-129">Die folgenden Beispiele veranschaulichen diese grundlegenden Konzepte.</span><span class="sxs-lookup"><span data-stu-id="84707-129">The following examples demonstrate these core concepts.</span></span>

### <a name="functions"></a><span data-ttu-id="84707-130">Funktionen</span><span class="sxs-lookup"><span data-stu-id="84707-130">Functions</span></span>

<span data-ttu-id="84707-131">Das gängigste und grundlegendste Konstrukt bei der funktionalen Programmierung ist die-Funktion.</span><span class="sxs-lookup"><span data-stu-id="84707-131">The most common and fundamental construct in functional programming is the function.</span></span> <span data-ttu-id="84707-132">Im folgenden finden Sie eine einfache Funktion, die einer Ganzzahl 1 hinzufügt:</span><span class="sxs-lookup"><span data-stu-id="84707-132">Here's a simple function that adds 1 to an integer:</span></span>

```fsharp
let addOne x = x + 1
```

<span data-ttu-id="84707-133">Die Typsignatur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="84707-133">Its type signature is as follows:</span></span>

```fsharp
val addOne: x:int -> int
```

<span data-ttu-id="84707-134">Die Signatur kann mit dem Namen "`addOne` akzeptiert eine `int` mit dem Namen `x` und erzeugt eine `int`".</span><span class="sxs-lookup"><span data-stu-id="84707-134">The signature can be read as, "`addOne` accepts an `int` named `x` and will produce an `int`".</span></span> <span data-ttu-id="84707-135">Formal wird _`addOne` einen Wert_ aus dem Satz von ganzen Zahlen dem Satz von ganzen Zahlen zuordnet.</span><span class="sxs-lookup"><span data-stu-id="84707-135">More formally, `addOne` is _mapping_ a value from the set of integers to the set of integers.</span></span> <span data-ttu-id="84707-136">Das `->` Token bezeichnet diese Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="84707-136">The `->` token signifies this mapping.</span></span> <span data-ttu-id="84707-137">In F#können Sie in der Regel die Funktions Signatur überprüfen, um einen Eindruck davon zu erhalten, was Sie tut.</span><span class="sxs-lookup"><span data-stu-id="84707-137">In F#, you can usually look at the function signature to get a sense for what it does.</span></span>

<span data-ttu-id="84707-138">Warum ist die Signatur also wichtig?</span><span class="sxs-lookup"><span data-stu-id="84707-138">So, why is the signature important?</span></span> <span data-ttu-id="84707-139">Bei der typisierten funktionalen Programmierung ist die Implementierung einer Funktion oft weniger wichtig als die tatsächliche Typsignatur.</span><span class="sxs-lookup"><span data-stu-id="84707-139">In typed functional programming, the implementation of a function is often less important than the actual type signature!</span></span> <span data-ttu-id="84707-140">Die Tatsache, dass `addOne` den Wert 1 zu einer Ganzzahl addiert, ist zur Laufzeit interessant, aber wenn Sie ein Programm erstellen, ist die Tatsache, dass es eine `int` akzeptiert und zurückgibt, so informiert, wie Sie diese Funktion tatsächlich verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="84707-140">The fact that `addOne` adds the value 1 to an integer is interesting at runtime, but when you are constructing a program, the fact that it accepts and returns an `int` is what informs how you will actually use this function.</span></span> <span data-ttu-id="84707-141">Wenn Sie diese Funktion außerdem ordnungsgemäß (in Bezug auf Ihre Typsignatur) verwenden, kann die Diagnose von Problemen nur innerhalb des Texts der `addOne` Funktion erfolgen.</span><span class="sxs-lookup"><span data-stu-id="84707-141">Furthermore, once you use this function correctly (with respect to its type signature), diagnosing any problems can be done only within the body of the `addOne` function.</span></span> <span data-ttu-id="84707-142">Dies ist der Impuls hinter der typisierten funktionalen Programmierung.</span><span class="sxs-lookup"><span data-stu-id="84707-142">This is the impetus behind typed functional programming.</span></span>

### <a name="expressions"></a><span data-ttu-id="84707-143">Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="84707-143">Expressions</span></span>

<span data-ttu-id="84707-144">Ausdrücke sind Konstrukte, die zu einem Wert ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="84707-144">Expressions are constructs that evaluate to a value.</span></span> <span data-ttu-id="84707-145">Im Gegensatz zu-Anweisungen, die eine Aktion ausführen, können Ausdrücke eine Aktion durchführen, die einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="84707-145">In contrast to statements, which perform an action, expressions can be thought of performing an action that gives back a value.</span></span> <span data-ttu-id="84707-146">Ausdrücke werden fast immer anstelle von-Anweisungen in der funktionalen Programmierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="84707-146">Expressions are almost always used in favor of statements in functional programming.</span></span>

<span data-ttu-id="84707-147">Sehen Sie sich die vorherige Funktion an, `addOne`.</span><span class="sxs-lookup"><span data-stu-id="84707-147">Consider the previous function, `addOne`.</span></span> <span data-ttu-id="84707-148">Der Text des `addOne` ist ein Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="84707-148">The body of `addOne` is an expression:</span></span>

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

<span data-ttu-id="84707-149">Dies ist das Ergebnis dieses Ausdrucks, der den Ergebnistyp der `addOne` Funktion definiert.</span><span class="sxs-lookup"><span data-stu-id="84707-149">It is the result of this expression that defines the result type of the `addOne` function.</span></span> <span data-ttu-id="84707-150">Beispielsweise könnte der Ausdruck, der diese Funktion bildet, in einen anderen Typ geändert werden, z. b. ein `string`:</span><span class="sxs-lookup"><span data-stu-id="84707-150">For example, the expression that makes up this function could be changed to be a different type, such as a `string`:</span></span>

```fsharp
let addOne x = x.ToString() + "1"
```

<span data-ttu-id="84707-151">Die Signatur der Funktion ist jetzt:</span><span class="sxs-lookup"><span data-stu-id="84707-151">The signature of the function is now:</span></span>

```fsharp
val addOne: x:'a -> string
```

<span data-ttu-id="84707-152">Da für jeden Typ F# in `ToString()` aufgerufen werden kann, wurde der Typ des `x` generisch (sogenannte [Automatische Generalisierung](../language-reference/generics/automatic-generalization.md)), und der resultierende Typ ist eine `string`.</span><span class="sxs-lookup"><span data-stu-id="84707-152">Since any type in F# can have `ToString()` called on it, the type of `x` has been made generic (called [Automatic Generalization](../language-reference/generics/automatic-generalization.md)), and the resultant type is a `string`.</span></span>

<span data-ttu-id="84707-153">Ausdrücke sind nicht nur die Funktions Texte.</span><span class="sxs-lookup"><span data-stu-id="84707-153">Expressions are not just the bodies of functions.</span></span> <span data-ttu-id="84707-154">Sie können Ausdrücke verwenden, die einen Wert verursachen, den Sie an anderer Stelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="84707-154">You can have expressions that produce a value you use elsewhere.</span></span> <span data-ttu-id="84707-155">Eine gängige `if`ist:</span><span class="sxs-lookup"><span data-stu-id="84707-155">A common one is `if`:</span></span>

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

<span data-ttu-id="84707-156">Der `if` Ausdruck erzeugt einen Wert mit dem Namen `result`.</span><span class="sxs-lookup"><span data-stu-id="84707-156">The `if` expression produces a value called `result`.</span></span> <span data-ttu-id="84707-157">Beachten Sie, dass Sie `result` vollständig weglassen können, indem Sie den `if` Ausdruck zum Text der `addOneIfOdd`-Funktion führen.</span><span class="sxs-lookup"><span data-stu-id="84707-157">Note that you could omit `result` entirely, making the `if` expression the body of the `addOneIfOdd` function.</span></span> <span data-ttu-id="84707-158">Der wichtigste Punkt, den Sie sich an Ausdrücken merken müssen, ist, dass Sie einen Wert ergeben.</span><span class="sxs-lookup"><span data-stu-id="84707-158">The key thing to remember about expressions is that they produce a value.</span></span>

<span data-ttu-id="84707-159">Es gibt einen besonderen Typ, `unit`, der verwendet wird, wenn nichts zurückgegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="84707-159">There is a special type, `unit`, that is used when there is nothing to return.</span></span> <span data-ttu-id="84707-160">Sehen Sie sich beispielsweise diese einfache Funktion an:</span><span class="sxs-lookup"><span data-stu-id="84707-160">For example, consider this simple function:</span></span>

```fsharp
let printString (str: string) =
    printfn "String is: %s" str
```

<span data-ttu-id="84707-161">Die Signatur sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="84707-161">The signature looks like this:</span></span>

```fsharp
val printString: str:string -> unit
```

<span data-ttu-id="84707-162">Der `unit`-Typ gibt an, dass kein tatsächlicher Wert zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="84707-162">The `unit` type indicates that there is no actual value being returned.</span></span> <span data-ttu-id="84707-163">Dies ist nützlich, wenn Sie über eine Routine verfügen, die "arbeiten" muss, obwohl kein Wert vorhanden ist, der als Ergebnis der Arbeit zurückgegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="84707-163">This is useful when you have a routine that must "do work" despite having no value to return as a result of that work.</span></span>

<span data-ttu-id="84707-164">Dies ist ein starker Kontrast zur imperativen Programmierung, bei der das entsprechende `if` Konstrukt eine-Anweisung ist, und das Erstellen von Werten wird häufig mit veränderenden Variablen erreicht.</span><span class="sxs-lookup"><span data-stu-id="84707-164">This is in sharp contrast to imperative programming, where the equivalent `if` construct is a statement, and producing values is often done with mutating variables.</span></span> <span data-ttu-id="84707-165">In C#könnte der Code z. b. wie folgt geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="84707-165">For example, in C#, the code might be written like this:</span></span>

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

<span data-ttu-id="84707-166">Beachten Sie, dass C# und andere Sprachen im C-Stil den [ternären Ausdruck](../../csharp/language-reference/operators/conditional-operator.md)unterstützen, der die Ausdrucks basierte bedingte Programmierung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="84707-166">It's worth noting that C# and other C-style languages do support the [ternary expression](../../csharp/language-reference/operators/conditional-operator.md), which allows for expression-based conditional programming.</span></span>

<span data-ttu-id="84707-167">Bei der funktionalen Programmierung ist es selten, Werte mit-Anweisungen zu mutieren.</span><span class="sxs-lookup"><span data-stu-id="84707-167">In functional programming, it is rare to mutate values with statements.</span></span> <span data-ttu-id="84707-168">Obwohl einige funktionale Sprachen Anweisungen und mutations unterstützen, ist es nicht üblich, diese Konzepte bei der funktionalen Programmierung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="84707-168">Although some functional languages support statements and mutation, it is not common to use these concepts in functional programming.</span></span>

### <a name="pure-functions"></a><span data-ttu-id="84707-169">Reine Funktionen</span><span class="sxs-lookup"><span data-stu-id="84707-169">Pure functions</span></span>

<span data-ttu-id="84707-170">Wie bereits erwähnt, sind reine Funktionen Funktionen, die:</span><span class="sxs-lookup"><span data-stu-id="84707-170">As previously mentioned, pure functions are functions that:</span></span>

* <span data-ttu-id="84707-171">Wertet immer denselben Wert für dieselbe Eingabe aus.</span><span class="sxs-lookup"><span data-stu-id="84707-171">Always evaluate to the same value for the same input.</span></span>
* <span data-ttu-id="84707-172">Hat keine Nebenwirkungen.</span><span class="sxs-lookup"><span data-stu-id="84707-172">Have no side effects.</span></span>

<span data-ttu-id="84707-173">Es ist hilfreich, mathematische Funktionen in diesem Kontext zu betrachten.</span><span class="sxs-lookup"><span data-stu-id="84707-173">It is helpful to think of mathematical functions in this context.</span></span> <span data-ttu-id="84707-174">In der Mathematik sind Funktionen nur von ihren Argumenten abhängig und haben keine Nebeneffekte.</span><span class="sxs-lookup"><span data-stu-id="84707-174">In mathematics, functions depend only on their arguments and do not have any side effects.</span></span> <span data-ttu-id="84707-175">In der mathematischen Funktions `f(x) = x + 1`hängt der Wert von `f(x)` nur vom Wert von `x`ab.</span><span class="sxs-lookup"><span data-stu-id="84707-175">In the mathematical function `f(x) = x + 1`, the value of `f(x)` depends only on the value of `x`.</span></span> <span data-ttu-id="84707-176">Reine Funktionen bei der funktionalen Programmierung sind auf dieselbe Weise.</span><span class="sxs-lookup"><span data-stu-id="84707-176">Pure functions in functional programming are the same way.</span></span>

<span data-ttu-id="84707-177">Beim Schreiben einer reinen Funktion muss die Funktion nur von ihren Argumenten abhängen und keine Aktionen ausführen, die zu einem Nebeneffekt führen.</span><span class="sxs-lookup"><span data-stu-id="84707-177">When writing a pure function, the function must depend only on its arguments and not perform any action that results in a side effect.</span></span>

<span data-ttu-id="84707-178">Im folgenden finden Sie ein Beispiel für eine nicht reine Funktion, da Sie vom globalen, veränderbaren Zustand abhängt:</span><span class="sxs-lookup"><span data-stu-id="84707-178">Here is an example of a non-pure function because it depends on global, mutable state:</span></span>

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

<span data-ttu-id="84707-179">Die `addOneToValue` Funktion ist eindeutig, da `value` jederzeit geändert werden kann, um einen anderen Wert als 1 zu haben.</span><span class="sxs-lookup"><span data-stu-id="84707-179">The `addOneToValue` function is clearly impure, because `value` could be changed at any time to have a different value than 1.</span></span> <span data-ttu-id="84707-180">Dieses Muster von, abhängig von einem globalen Wert, muss bei der funktionalen Programmierung vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="84707-180">This pattern of depending on a global value is to be avoided in functional programming.</span></span>

<span data-ttu-id="84707-181">Im folgenden finden Sie ein weiteres Beispiel für eine nicht reine Funktion, da Sie einen Nebeneffekt durchführt:</span><span class="sxs-lookup"><span data-stu-id="84707-181">Here is another example of a non-pure function, because it performs a side effect:</span></span>

```fsharp
let addOneToValue x =
    printfn "x is %d" x
    x + 1
```

<span data-ttu-id="84707-182">Obwohl diese Funktion nicht von einem globalen Wert abhängt, schreibt Sie den Wert `x` in die Ausgabe des Programms.</span><span class="sxs-lookup"><span data-stu-id="84707-182">Although this function does not depend on a global value, it writes the value of `x` to the output of the program.</span></span> <span data-ttu-id="84707-183">Obwohl es in der Tat nichts falsches gibt, bedeutet dies, dass die Funktion nicht rein ist.</span><span class="sxs-lookup"><span data-stu-id="84707-183">Although there is nothing inherently wrong with doing this, it does mean that the function is not pure.</span></span> <span data-ttu-id="84707-184">Wenn ein anderer Teil des Programms von einem externen Programm, z. b. dem Ausgabepuffer, abhängt, kann sich das Aufrufen dieser Funktion auf diesen anderen Teil des Programms auswirken.</span><span class="sxs-lookup"><span data-stu-id="84707-184">If another part of your program depends on something external to the program, such as the output buffer, then calling this function can affect that other part of your program.</span></span>

<span data-ttu-id="84707-185">Wenn Sie die `printfn`-Anweisung entfernen, wird die-Funktion rein:</span><span class="sxs-lookup"><span data-stu-id="84707-185">Removing the `printfn` statement makes the function pure:</span></span>

```fsharp
let addOneToValue x = x + 1
```

<span data-ttu-id="84707-186">Obwohl diese Funktion nicht grundsätzlich _besser_ als die vorherige Version mit der `printfn`-Anweisung ist, gewährleistet Sie, dass all diese Funktion einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="84707-186">Although this function is not inherently _better_ than the previous version with the `printfn` statement, it does guarantee that all this function does is return a value.</span></span> <span data-ttu-id="84707-187">Wenn diese Funktion beliebig oft aufgerufen wird, wird das gleiche Ergebnis erzielt: Sie erzeugt lediglich einen Wert.</span><span class="sxs-lookup"><span data-stu-id="84707-187">Calling this function any number of times produces the same result: it just produces a value.</span></span> <span data-ttu-id="84707-188">Die von der Reinheit gegebene Vorhersagbarkeit ist etwas, das viele funktionale Programmierer anstreben.</span><span class="sxs-lookup"><span data-stu-id="84707-188">The predictability given by purity is something many functional programmers strive for.</span></span>

### <a name="immutability"></a><span data-ttu-id="84707-189">Unveränderlichkeit</span><span class="sxs-lookup"><span data-stu-id="84707-189">Immutability</span></span>

<span data-ttu-id="84707-190">Und schließlich ist eines der grundlegendsten Konzepte der typisierten funktionalen Programmierung Unveränderlichkeit.</span><span class="sxs-lookup"><span data-stu-id="84707-190">Finally, one of the most fundamental concepts of typed functional programming is immutability.</span></span> <span data-ttu-id="84707-191">In F#sind alle Werte standardmäßig unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="84707-191">In F#, all values are immutable by default.</span></span> <span data-ttu-id="84707-192">Dies bedeutet, dass Sie nicht direkt bearbeitet werden können, es sei denn, Sie markieren Sie explizit als änderbar.</span><span class="sxs-lookup"><span data-stu-id="84707-192">That means they cannot be mutated in-place unless you explicitly mark them as mutable.</span></span>

<span data-ttu-id="84707-193">In der Praxis bedeutet das Arbeiten mit unveränderlichen Werten, dass Sie Ihren Ansatz für die Programmierung von "Ich muss etwas ändern", in "Ich muss einen neuen Wert entwickeln" ändern.</span><span class="sxs-lookup"><span data-stu-id="84707-193">In practice, working with immutable values means that you change your approach to programming from, "I need to change something", to "I need to produce a new value".</span></span>

<span data-ttu-id="84707-194">Wenn Sie z. b. 1 zu einem Wert hinzufügen, wird ein neuer Wert erzeugt, der die vorhandene nicht muziiert:</span><span class="sxs-lookup"><span data-stu-id="84707-194">For example, adding 1 to a value means producing a new value, not mutating the existing one:</span></span>

```fsharp
let value = 1
let secondValue = value + 1
```

<span data-ttu-id="84707-195">In F#mutiert der folgende Code die `value`-Funktion **nicht** . Stattdessen wird eine Gleichheits Überprüfung durchführt:</span><span class="sxs-lookup"><span data-stu-id="84707-195">In F#, the following code does **not** mutate the `value` function; instead, it performs an equality check:</span></span>

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

<span data-ttu-id="84707-196">Einige funktionale Programmiersprachen unterstützen überhaupt keine Mutation.</span><span class="sxs-lookup"><span data-stu-id="84707-196">Some functional programming languages do not support mutation at all.</span></span> <span data-ttu-id="84707-197">In F#wird es unterstützt, aber es ist nicht das Standardverhalten für-Werte.</span><span class="sxs-lookup"><span data-stu-id="84707-197">In F#, it is supported, but it is not the default behavior for values.</span></span>

<span data-ttu-id="84707-198">Dieses Konzept erstreckt sich noch weiter auf Datenstrukturen.</span><span class="sxs-lookup"><span data-stu-id="84707-198">This concept extends even further to data structures.</span></span> <span data-ttu-id="84707-199">Bei der funktionalen Programmierung weisen unveränderliche Datenstrukturen, wie z. b. Mengen (und viele weitere), eine andere Implementierung auf als Sie anfänglich erwarten.</span><span class="sxs-lookup"><span data-stu-id="84707-199">In functional programming, immutable data structures such as sets (and many more) have a different implementation than you might initially expect.</span></span> <span data-ttu-id="84707-200">Konzeptionell bedeutet das Hinzufügen eines Elements zu einem Satz nicht, dass der Satz geändert wird, sondern es wird eine _neue_ Menge mit dem hinzugefügten Wert erstellt.</span><span class="sxs-lookup"><span data-stu-id="84707-200">Conceptually, something like adding an item to a set does not change the set, it produces a _new_ set with the added value.</span></span> <span data-ttu-id="84707-201">Im Unterschied wird dies häufig durch eine andere Datenstruktur erreicht, die eine effiziente Nachverfolgung eines Werts ermöglicht, damit die entsprechende Darstellung der Daten als Ergebnis angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="84707-201">Under the covers, this is often accomplished by a different data structure that allows for efficiently tracking a value so that the appropriate representation of the data can be given as a result.</span></span>

<span data-ttu-id="84707-202">Diese Art der Arbeit mit Werten und Datenstrukturen ist äußerst wichtig, da Sie zwingt, jeden Vorgang zu behandeln, der etwas so ändert, als ob eine neue Version der Aufgabe erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="84707-202">This style of working with values and data structures is critical, as it forces you to treat any operation that modifies something as if it creates a new version of that thing.</span></span> <span data-ttu-id="84707-203">Dies ermöglicht es, dass Dinge wie Gleichheit und Vergleichbarkeit in ihren Programmen einheitlich sind.</span><span class="sxs-lookup"><span data-stu-id="84707-203">This allows for things like equality and comparability to be consistent in your programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="84707-204">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="84707-204">Next steps</span></span>

<span data-ttu-id="84707-205">Im nächsten Abschnitt werden Funktionen ausführlich behandelt und verschiedene Möglichkeiten erläutert, wie Sie Sie bei der funktionalen Programmierung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="84707-205">The next section will thoroughly cover functions, exploring different ways you can use them in functional programming.</span></span>

<span data-ttu-id="84707-206">[Erstklassige Funktionen](first-class-functions.md) untersucht Funktionen tief und zeigt, wie Sie Sie in verschiedenen Kontexten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="84707-206">[First-class functions](first-class-functions.md) explores functions deeply, showing how you can use them in various contexts.</span></span>

## <a name="further-reading"></a><span data-ttu-id="84707-207">Weiterführende Themen</span><span class="sxs-lookup"><span data-stu-id="84707-207">Further reading</span></span>

<span data-ttu-id="84707-208">Die [denkende funktionale](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) Reihe ist eine weitere großartige Ressource, um mehr F#über die funktionale Programmierung mit zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="84707-208">The [Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) series is another great resource to learn about functional programming with F#.</span></span> <span data-ttu-id="84707-209">Sie behandelt die Grundlagen der funktionalen Programmierung auf eine pragmatische und leicht lesbare Weise, indem F# Sie Funktionen zum Veranschaulichen der Konzepte verwendet.</span><span class="sxs-lookup"><span data-stu-id="84707-209">It covers fundamentals of functional programming in a pragmatic and easy-to-read way, using F# features to illustrate the concepts.</span></span>
