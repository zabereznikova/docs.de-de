---
title: Parameter und Argumente
description: Erfahren Sie mehr über F# sprachunterstützung zum Definieren von Parametern und übergeben von Argumenten an Funktionen, Methoden und Eigenschaften.
ms.date: 05/16/2016
ms.openlocfilehash: 65e3b4f8ffb03e81104c963c5e2da7aba2e2b220
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2019
ms.locfileid: "56583497"
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="07f86-103">Parameter und Argumente</span><span class="sxs-lookup"><span data-stu-id="07f86-103">Parameters and Arguments</span></span>

<span data-ttu-id="07f86-104">Dieses Thema beschreibt die sprachunterstützung zum Definieren von Parametern und übergeben von Argumenten an Funktionen, Methoden und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="07f86-104">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="07f86-105">Sie enthält Informationen zur Übergabe als Verweis, und wie Sie definieren und Verwenden von Methoden, die eine Variable Anzahl von Argumenten akzeptieren können.</span><span class="sxs-lookup"><span data-stu-id="07f86-105">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>

## <a name="parameters-and-arguments"></a><span data-ttu-id="07f86-106">Parameter und Argumente</span><span class="sxs-lookup"><span data-stu-id="07f86-106">Parameters and Arguments</span></span>

<span data-ttu-id="07f86-107">Der Begriff *Parameter* wird verwendet, um die Namen für Werte beschreiben, die bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="07f86-107">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="07f86-108">Der Begriff *Argument* wird verwendet, für die Werte für jeden Parameter bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="07f86-108">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="07f86-109">Parameter können in Tupel oder Curry-Form oder in eine Kombination aus den beiden angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="07f86-109">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="07f86-110">Sie können mithilfe eines expliziten Parameternamens Argumente übergeben.</span><span class="sxs-lookup"><span data-stu-id="07f86-110">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="07f86-111">Parameter der Methoden können als optional festgelegt und einen Standardwert angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="07f86-111">Parameters of methods can be specified as optional and given a default value.</span></span>

## <a name="parameter-patterns"></a><span data-ttu-id="07f86-112">Parametermuster</span><span class="sxs-lookup"><span data-stu-id="07f86-112">Parameter Patterns</span></span>

<span data-ttu-id="07f86-113">Parameter, Funktionen und Methoden bereitgestellt sind, im allgemeinen Mustern, die durch Leerzeichen getrennt.</span><span class="sxs-lookup"><span data-stu-id="07f86-113">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="07f86-114">Dies bedeutet, dass im Prinzip die Muster in beschrieben [Vergleichsausdrücke](match-expressions.md) in einer Parameterliste für eine Funktion oder Member verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="07f86-114">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="07f86-115">In der Regel verwenden Sie Methoden Tupelform übergeben von Argumenten.</span><span class="sxs-lookup"><span data-stu-id="07f86-115">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="07f86-116">Dies wird ein besseres Ergebnis aus der Perspektive der anderen erreicht, da die Tupelform wie übereinstimmt, die Argumente in .NET Methoden übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="07f86-116">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="07f86-117">Die Curry-Form wird meistens verwendet, mit Funktionen, die mithilfe von erstellt `let` Bindungen.</span><span class="sxs-lookup"><span data-stu-id="07f86-117">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="07f86-118">Der folgende Pseudocode zeigt Beispiele für Tupel und Curry-Argumente.</span><span class="sxs-lookup"><span data-stu-id="07f86-118">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="07f86-119">Kombinierte Formen sind möglich, wenn einige Argumente im Tupel sind und einige nicht.</span><span class="sxs-lookup"><span data-stu-id="07f86-119">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="07f86-120">Andere Muster können auch verwendet werden, in der Parameterliste, aber wenn das Muster der Parameter nicht alle Mögliche Eingaben übereinstimmt, gibt es möglicherweise eine unvollständige Übereinstimmung zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="07f86-120">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="07f86-121">Die Ausnahme `MatchFailureException` wird generiert, wenn der Wert eines Arguments nicht die in der Parameterliste angegebenen Mustern übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="07f86-121">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="07f86-122">Der Compiler gibt eine Warnung, wenn ein Muster für die Parameter nach unvollständigen Übereinstimmungen zulässt.</span><span class="sxs-lookup"><span data-stu-id="07f86-122">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="07f86-123">Mindestens eine andere Muster ist häufig nützlich für Parameterlisten, und das ist das Platzhaltermuster.</span><span class="sxs-lookup"><span data-stu-id="07f86-123">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="07f86-124">Sie verwenden das Platzhaltermuster in einer Parameterliste, wenn Sie möchten einfach alle Argumente ignorieren, die bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="07f86-124">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="07f86-125">Der folgende Code veranschaulicht die Verwendung des Platzhaltermusters in einer Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="07f86-125">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="07f86-126">Das Platzhaltermuster kann sein, hilfreich, wenn Sie nicht, die übergebenen Argumenten benötigen, z. B. den Haupteinstiegspunkt für ein Programm, wenn Sie nicht die Befehlszeilenargumente interessiert sind, die normalerweise als Zeichenfolgenarray, wie im folgenden Code bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="07f86-126">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="07f86-127">Sind andere Muster, die in-Argumente verwendet werden die `as` Muster und Bezeichnermuster Unterscheidungs-Unions und aktive Muster zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="07f86-127">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="07f86-128">Sie können wie folgt die Einzelfall-Unterscheidungs-union-Muster verwenden.</span><span class="sxs-lookup"><span data-stu-id="07f86-128">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="07f86-129">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="07f86-129">The output is as follows.</span></span>

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="07f86-130">Mit aktiven Mustern können als Parameter, z. B. nützlich bei der Transformation ein Argument in einem gewünschten Format wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="07f86-130">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="07f86-131">Sie können die `as` Muster, um einen übereinstimmenden Wert als ein lokaler Wert zu speichern, wie in der folgenden Zeile des Codes angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="07f86-131">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="07f86-132">Ein weiteres Muster, das gelegentlich verwendet werden, ist eine Funktion, die das letzte Argument bereitstellen, als Text der Funktion unbenannte verlässt, ein Lambda-Ausdruck, der die implizite Argument sofort eine Musterübereinstimmung ausführt.</span><span class="sxs-lookup"><span data-stu-id="07f86-132">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="07f86-133">Ein Beispiel hierfür ist die folgende Codezeile.</span><span class="sxs-lookup"><span data-stu-id="07f86-133">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="07f86-134">Dieser Code definiert eine Funktion, die eine generische Liste annimmt und zurückgibt `true` ist die Liste leer ist, und `false` andernfalls.</span><span class="sxs-lookup"><span data-stu-id="07f86-134">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="07f86-135">Die Verwendung solcher Techniken betrachtet möglich Code schwieriger zu lesen.</span><span class="sxs-lookup"><span data-stu-id="07f86-135">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="07f86-136">In einigen Fällen Muster, bei denen unvollständige Übereinstimmungen sind nützlich, z. B. Wenn Sie wissen, dass die Listen in Ihrem Programm nur drei Elemente verfügen, können ein Muster wie folgt in einer Parameterliste.</span><span class="sxs-lookup"><span data-stu-id="07f86-136">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="07f86-137">Die Verwendung von Mustern, die unvollständige Übereinstimmungen ist am besten für die schnelle Erstellung von Prototypen und andere temporäre Zwecke reserviert.</span><span class="sxs-lookup"><span data-stu-id="07f86-137">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="07f86-138">Der Compiler gibt eine Warnung für diese Art von Code.</span><span class="sxs-lookup"><span data-stu-id="07f86-138">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="07f86-139">Solche Muster nicht grundsätzlich alle möglichen Eingaben abdecken und sind daher nicht für die Komponenten-APIs geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="07f86-139">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="07f86-140">Benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="07f86-140">Named Arguments</span></span>

<span data-ttu-id="07f86-141">Argumente für Methoden Position in einer Argumentliste von durch Trennzeichen getrennte angegeben werden können, oder sie können übergeben werden an eine Methode explizit durch Eingabe des Namens, gefolgt von einem Gleichheitszeichen und dem Wert übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="07f86-141">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="07f86-142">Wenn angegeben, indem Sie den Namen angeben, können sie in einer anderen Reihenfolge aus, die verwendet werden, in der Deklaration angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="07f86-142">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="07f86-143">Benannte Argumente können Code besser lesbar und besser anpassen auf bestimmte Arten von Änderungen in der API, z. B. eine neuanordnung der Parameter der Methode zu machen.</span><span class="sxs-lookup"><span data-stu-id="07f86-143">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="07f86-144">Benannte Argumente dürfen nur für Methoden, nicht für `let`-gebunden, Funktionen, Werte von Funktionen oder Lambda-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="07f86-144">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="07f86-145">Das folgende Codebeispiel veranschaulicht die Verwendung von benannten Argumente.</span><span class="sxs-lookup"><span data-stu-id="07f86-145">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="07f86-146">In einem Aufruf für einen Klassenkonstruktor können Sie die Werte der Eigenschaften der Klasse mit einer Syntax wie mit der benannten Argumente festlegen.</span><span class="sxs-lookup"><span data-stu-id="07f86-146">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="07f86-147">Das folgende Beispiel zeigt diese Syntax.</span><span class="sxs-lookup"><span data-stu-id="07f86-147">The following example shows this syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="07f86-148">Weitere Informationen finden Sie unter [Konstruktoren (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span><span class="sxs-lookup"><span data-stu-id="07f86-148">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="07f86-149">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="07f86-149">Optional Parameters</span></span>

<span data-ttu-id="07f86-150">Sie können einen optionalen Parameter für eine Methode mit einem Fragezeichen angegeben vor den Parameternamen angeben.</span><span class="sxs-lookup"><span data-stu-id="07f86-150">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="07f86-151">Optionale Parameter werden als interpretiert die F# Typ option, damit Sie auf die übliche Weise abgefragt werden können, dass Optionstypen, mithilfe abgefragt werden einer `match` Ausdruck mit `Some` und `None`.</span><span class="sxs-lookup"><span data-stu-id="07f86-151">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="07f86-152">Optionale Parameter sind zulässig, nur für Elemente, die nicht auf Funktionen, die mithilfe von erstellt `let` Bindungen.</span><span class="sxs-lookup"><span data-stu-id="07f86-152">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="07f86-153">Sie können vorhandene optional Werte übergeben-Methode von Parameternamen, wie z. B. `?arg=None` oder `?arg=Some(3)` oder `?arg=arg`.</span><span class="sxs-lookup"><span data-stu-id="07f86-153">You can pass existing optional values to method by parameter name, such as `?arg=None` or `?arg=Some(3)` or `?arg=arg`.</span></span> <span data-ttu-id="07f86-154">Dies kann nützlich sein, wenn optionale Argumente Erstellen einer Methode, die an eine andere Methode übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="07f86-154">This can be useful when building a method that passes optional arguments to another method.</span></span>

<span data-ttu-id="07f86-155">Sie können auch eine Funktion `defaultArg`, wodurch einen Standardwert eines optionalen Arguments festgelegt.</span><span class="sxs-lookup"><span data-stu-id="07f86-155">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="07f86-156">Die `defaultArg` Funktion akzeptiert den optionalen Parameter als erstes Argument und der Standardwert als das zweite.</span><span class="sxs-lookup"><span data-stu-id="07f86-156">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="07f86-157">Das folgende Beispiel veranschaulicht die Verwendung der optionalen Parameter.</span><span class="sxs-lookup"><span data-stu-id="07f86-157">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="07f86-158">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="07f86-158">The output is as follows.</span></span>

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

<span data-ttu-id="07f86-159">Zum Zweck der C# und Visual Basic-Interop können Sie die Attribute `[<Optional; DefaultParameterValue<(...)>]` in F#, sodass Aufrufer ein Argument als optional angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="07f86-159">For the purposes of C# and Visual Basic interop you can use the attributes `[<Optional; DefaultParameterValue<(...)>]` in F#, so that callers will see an argument as optional.</span></span> <span data-ttu-id="07f86-160">Dies entspricht dem Argument in als optional definiert C# in `MyMethod(int i = 3)`.</span><span class="sxs-lookup"><span data-stu-id="07f86-160">This is equivalent to defining the argument as optional in C# as in `MyMethod(int i = 3)`.</span></span>

```fsharp
open System
open System.Runtime.InteropServices
type C = 
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

<span data-ttu-id="07f86-161">Sie können auch ein neues Objekt als ein standardmäßiger Parameterwert angeben.</span><span class="sxs-lookup"><span data-stu-id="07f86-161">You can also specify a new object as a default parameter value.</span></span> <span data-ttu-id="07f86-162">Z. B. die `Foo` Member ist möglicherweise eine optionale `CanceallationToken` stattdessen als Eingabe:</span><span class="sxs-lookup"><span data-stu-id="07f86-162">For example, the `Foo` member could have an optional `CanceallationToken` as input instead:</span></span>

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C = 
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

<span data-ttu-id="07f86-163">Der Wert, der als Argument für `DefaultParameterValue` muss dem Typ des Parameters entsprechen.</span><span class="sxs-lookup"><span data-stu-id="07f86-163">The value given as argument to `DefaultParameterValue` must match the type of the parameter.</span></span> <span data-ttu-id="07f86-164">Beispielsweise ist Folgendes nicht zulässig:</span><span class="sxs-lookup"><span data-stu-id="07f86-164">For example, the following is not allowed:</span></span>

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

<span data-ttu-id="07f86-165">In diesem Fall wird der Compiler eine Warnung generiert, und beide Attribute vollständig ignoriert.</span><span class="sxs-lookup"><span data-stu-id="07f86-165">In this case, the compiler generates a warning and will ignore both attributes altogether.</span></span> <span data-ttu-id="07f86-166">Beachten Sie, dass der Standardwert `null` muss sein Typ kommentiert, anders leitet der Compiler den falschen Typ, d. h. `[<Optional; DefaultParameterValue(null:obj)>] o:obj`.</span><span class="sxs-lookup"><span data-stu-id="07f86-166">Note that the default value `null` needs to be type-annotated, as otherwise the compiler infers the wrong type, i.e. `[<Optional; DefaultParameterValue(null:obj)>] o:obj`.</span></span>

## <a name="passing-by-reference"></a><span data-ttu-id="07f86-167">Übergeben als Verweis</span><span class="sxs-lookup"><span data-stu-id="07f86-167">Passing by Reference</span></span>

<span data-ttu-id="07f86-168">Übergeben einer F# Wert nach Verweis umfasst [Byrefs](byrefs.md), die verwaltete Zeigertypen sind.</span><span class="sxs-lookup"><span data-stu-id="07f86-168">Passing an F# value by reference involves [byrefs](byrefs.md), which are managed pointer types.</span></span> <span data-ttu-id="07f86-169">Anleitung für die zu verwendende Typ wie folgt lautet:</span><span class="sxs-lookup"><span data-stu-id="07f86-169">Guidance for which type to use is as follows:</span></span>

* <span data-ttu-id="07f86-170">Verwendung `inref<'T>` , wenn Sie nur den Zeiger lesen müssen.</span><span class="sxs-lookup"><span data-stu-id="07f86-170">Use `inref<'T>` if you only need to read the pointer.</span></span>
* <span data-ttu-id="07f86-171">Verwendung `outref<'T>` , wenn Sie nur auf den Zeiger schreiben müssen.</span><span class="sxs-lookup"><span data-stu-id="07f86-171">Use `outref<'T>` if you only need to write to the pointer.</span></span>
* <span data-ttu-id="07f86-172">Verwendung `byref<'T>` Wenn müssen Sie sowohl auslesen und Schreiben in den Zeiger.</span><span class="sxs-lookup"><span data-stu-id="07f86-172">Use `byref<'T>` if you need to both read from and write to the pointer.</span></span>

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

// No need to make it mutable, since it's read-only
let x = 1
example1 &x

// Needs to be mutable, since we write to it
let mutable y = 2
example2 &y
example3 &y // Now 'y' is 3
```

<span data-ttu-id="07f86-173">Da der Parameter ein Zeiger ist, und der Wert kann geändert werden, werden alle Änderungen an den Wert nach der Ausführung der Funktion beibehalten.</span><span class="sxs-lookup"><span data-stu-id="07f86-173">Because the parameter is a pointer and the value is mutable, any changes to the value are retained after the execution of the function.</span></span>

<span data-ttu-id="07f86-174">Sie können ein Tupel als Rückgabewert einer speichern `out` Parameter in .NET-Methoden-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="07f86-174">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="07f86-175">Alternativ können Sie behandeln die `out` Parameter als ein `byref` Parameter.</span><span class="sxs-lookup"><span data-stu-id="07f86-175">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="07f86-176">Im folgenden Codebeispiel wird veranschaulicht, in beide Richtungen.</span><span class="sxs-lookup"><span data-stu-id="07f86-176">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="07f86-177">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="07f86-177">Parameter Arrays</span></span>

<span data-ttu-id="07f86-178">Gelegentlich ist es erforderlich, eine Funktion zu definieren, die eine beliebige Anzahl von Parametern heterogenen Typs akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="07f86-178">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="07f86-179">Es wäre nicht sehr praktisch, erstellen alle möglichen überladenen Methoden um für alle Typen zu berücksichtigen, die verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="07f86-179">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="07f86-180">Die .NET Implementierungen bieten Unterstützung für solche Methoden über die Parameter-Array-Funktion.</span><span class="sxs-lookup"><span data-stu-id="07f86-180">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="07f86-181">Eine Methode, die ein Parameterarray in der Signatur verwendet, werden, kann mit einer beliebigen Anzahl von Parametern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="07f86-181">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="07f86-182">Die Parameter werden in ein Array eingefügt.</span><span class="sxs-lookup"><span data-stu-id="07f86-182">The parameters are put into an array.</span></span> <span data-ttu-id="07f86-183">Der Typ der Elemente des Arrays bestimmt die Parametertypen, die an die Funktion übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="07f86-183">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="07f86-184">Wenn Sie das Parameterarray mit definieren `System.Object` als Typ des Elements, klicken Sie dann Clientcode kann Werte übergeben eines beliebigen Typs.</span><span class="sxs-lookup"><span data-stu-id="07f86-184">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="07f86-185">In F# können Parameterarrays nur in Methoden definiert werden.</span><span class="sxs-lookup"><span data-stu-id="07f86-185">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="07f86-186">Sie können nicht verwendet werden, in der eigenständigen oder Funktionen, die in Modulen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="07f86-186">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="07f86-187">Sie definieren ein Parameterarray mithilfe der `ParamArray` Attribut.</span><span class="sxs-lookup"><span data-stu-id="07f86-187">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="07f86-188">Die `ParamArray` Attribut kann nur auf den letzten Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="07f86-188">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="07f86-189">Der folgende Code veranschaulicht beide eine .NET-Methode übergeben wird, die ein Parameterarray und die Definition eines Typs in F# verwendet wird, die eine Methode, die akzeptiert ein Parameterarray aufrufen.</span><span class="sxs-lookup"><span data-stu-id="07f86-189">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="07f86-190">Wenn in einem Projekt ausführen, lautet die Ausgabe des obigen Codes wie folgt:</span><span class="sxs-lookup"><span data-stu-id="07f86-190">When run in a project, the output of the previous code is as follows:</span></span>

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="07f86-191">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07f86-191">See also</span></span>

- [<span data-ttu-id="07f86-192">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="07f86-192">Members</span></span>](members/index.md)
