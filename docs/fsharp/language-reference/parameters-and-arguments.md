---
title: Parameter und Argumente
description: 'Erfahren Sie mehr über die F #-Sprachunterstützung zum Definieren von Parametern und zum Übergeben von Argumenten an Funktionen, Methoden und Eigenschaften.'
ms.date: 08/15/2020
ms.openlocfilehash: 3c391ca37a1cf3bd150316943e5b06efa532b317
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740288"
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="2ec2c-103">Parameter und Argumente</span><span class="sxs-lookup"><span data-stu-id="2ec2c-103">Parameters and Arguments</span></span>

<span data-ttu-id="2ec2c-104">In diesem Thema wird die Sprachunterstützung für das Definieren von Parametern und das Übergeben von Argumenten an Funktionen, Methoden und Eigenschaften beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-104">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="2ec2c-105">Sie enthält Informationen zum übergeben als Verweis und zum Definieren und Verwenden von Methoden, die eine Variable Anzahl von Argumenten annehmen können.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-105">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>

## <a name="parameters-and-arguments"></a><span data-ttu-id="2ec2c-106">Parameter und Argumente</span><span class="sxs-lookup"><span data-stu-id="2ec2c-106">Parameters and Arguments</span></span>

<span data-ttu-id="2ec2c-107">Der Term- *Parameter* wird verwendet, um die Namen für Werte zu beschreiben, die bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-107">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="2ec2c-108">Das Begriffs *Argument* wird für die Werte verwendet, die für jeden Parameter bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-108">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="2ec2c-109">Parameter können in einem Tupel-oder Curry-Formular oder in einer Kombination der beiden Werte angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-109">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="2ec2c-110">Sie können Argumente übergeben, indem Sie einen expliziten Parameternamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-110">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="2ec2c-111">Parameter von Methoden können als optional und mit einem Standardwert angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-111">Parameters of methods can be specified as optional and given a default value.</span></span>

## <a name="parameter-patterns"></a><span data-ttu-id="2ec2c-112">Parameter Muster</span><span class="sxs-lookup"><span data-stu-id="2ec2c-112">Parameter Patterns</span></span>

<span data-ttu-id="2ec2c-113">Parameter, die für Funktionen und Methoden bereitgestellt werden, sind im Allgemeinen durch Leerzeichen getrennte Muster.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-113">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="2ec2c-114">Dies bedeutet, dass im Prinzip jedes der in [Match Expressions](match-expressions.md) beschriebenen Muster in einer Parameterliste für eine Funktion oder ein Member verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-114">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="2ec2c-115">Methoden verwenden normalerweise die tupelform der Übergabe von Argumenten.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-115">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="2ec2c-116">Dadurch wird ein deutlicheres Ergebnis aus der Perspektive anderer .NET-Sprachen erzielt, da das tupelformular mit der Art und Weise übereinstimmt, in der die Argumente in .NET-Methoden</span><span class="sxs-lookup"><span data-stu-id="2ec2c-116">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="2ec2c-117">Das Curry-Formular wird am häufigsten mit Funktionen verwendet, die mithilfe von Bindungen erstellt wurden `let` .</span><span class="sxs-lookup"><span data-stu-id="2ec2c-117">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="2ec2c-118">Der folgende Pseudo Code zeigt Beispiele für Tupel-und Curry-Argumente.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-118">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="2ec2c-119">Kombinierte Formulare sind möglich, wenn sich einige Argumente in Tupeln befinden und andere nicht.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-119">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="2ec2c-120">Andere Muster können auch in Parameterlisten verwendet werden, aber wenn das Parameter Muster nicht allen möglichen Eingaben entspricht, gibt es möglicherweise eine unvollständige Entsprechung zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-120">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="2ec2c-121">Die-Ausnahme `MatchFailureException` wird generiert, wenn der Wert eines Arguments nicht mit den in der Parameterliste angegebenen Mustern identisch ist.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-121">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="2ec2c-122">Der Compiler gibt eine Warnung aus, wenn ein Parameter Muster unvollständige Übereinstimmungen zulässt.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-122">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="2ec2c-123">Mindestens ein anderes Muster ist häufig für Parameterlisten nützlich, und das ist das Platzhalter Muster.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-123">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="2ec2c-124">Sie verwenden das Platzhalter Muster in einer Parameterliste, wenn Sie einfach alle angegebenen Argumente ignorieren möchten.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-124">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="2ec2c-125">Der folgende Code veranschaulicht die Verwendung des Platzhalter Musters in einer Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-125">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="2ec2c-126">Das Platzhalter Muster kann nützlich sein, wenn Sie die übergebenen Argumente nicht benötigen, z. b. im Haupteinstiegspunkt an ein Programm, wenn Sie nicht an den Befehlszeilen Argumenten interessiert sind, die normalerweise als Zeichen folgen Array bereitgestellt werden, wie im folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-126">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="2ec2c-127">Andere Muster, die manchmal in Argumenten verwendet werden, sind das `as` Muster und die bezeichnermuster, die mit Unterscheidungs-Unions und aktiven Mustern verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-127">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="2ec2c-128">Sie können das Union-Muster mit einem einzelnen Fall wie folgt verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-128">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="2ec2c-129">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-129">The output is as follows.</span></span>

```console
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="2ec2c-130">Aktive Muster können als Parameter nützlich sein, z. b. beim Transformieren eines Arguments in ein gewünschtes Format, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="2ec2c-130">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="2ec2c-131">Sie können das `as` Muster verwenden, um einen übereinstimmenden Wert als lokalen Wert zu speichern, wie in der folgenden Codezeile dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-131">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="2ec2c-132">Ein anderes Muster, das gelegentlich verwendet wird, ist eine Funktion, die das Letzte unbenannte Argument verlässt, indem als Text der Funktion ein Lambda-Ausdruck bereitgestellt wird, der sofort eine Muster Übereinstimmung für das implizite Argument ausführt.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-132">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="2ec2c-133">Ein Beispiel hierfür ist die folgende Codezeile.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-133">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="2ec2c-134">Dieser Code definiert eine Funktion, die eine generische Liste annimmt und zurückgibt `true` , wenn die Liste leer ist, und `false` andernfalls.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-134">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="2ec2c-135">Die Verwendung solcher Techniken kann das Lesen des Codes erschweren.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-135">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="2ec2c-136">Gelegentlich sind Muster mit unvollständigen Übereinstimmungen nützlich, wenn Sie z. b. wissen, dass die Listen im Programm nur drei Elemente enthalten, können Sie ein Muster wie das folgende in einer Parameterliste verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-136">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="2ec2c-137">Die Verwendung von Mustern mit unvollständigen Übereinstimmungen ist am besten für die schnelle Prototyperstellung und andere temporäre Verwendungszwecke reserviert.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-137">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="2ec2c-138">Der Compiler gibt eine Warnung für diesen Code aus.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-138">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="2ec2c-139">Solche Muster können nicht den allgemeinen Fall aller möglichen Eingaben abdecken und sind daher nicht für Komponenten-APIs geeignet.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-139">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="2ec2c-140">Benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="2ec2c-140">Named Arguments</span></span>

<span data-ttu-id="2ec2c-141">Argumente für Methoden können durch die Position in einer durch Trennzeichen getrennten Argumentliste angegeben werden, oder Sie können explizit an eine Methode durch Angabe des Namens, gefolgt von einem Gleichheitszeichen und dem zu über gebenden Wert weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-141">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="2ec2c-142">Wenn Sie durch Angabe des Namens angegeben werden, können Sie in einer anderen Reihenfolge als der in der Deklaration verwendeten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-142">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="2ec2c-143">Benannte Argumente können den Code besser lesbar machen und besser an bestimmte Typen von Änderungen in der API angepasst werden, z. b. eine Neuanordnung von Methoden Parametern.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-143">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="2ec2c-144">Benannte Argumente sind nur für Methoden, nicht für `let` gebundene Funktionen, Funktions Werte oder Lambda Ausdrücke zulässig.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-144">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="2ec2c-145">Im folgenden Codebeispiel wird die Verwendung von benannten Argumenten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-145">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="2ec2c-146">In einem-Klassenkonstruktor können Sie die Werte der Eigenschaften der-Klasse festlegen, indem Sie eine Syntax verwenden, die dem von benannten Argumenten ähnelt.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-146">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="2ec2c-147">Das folgende Beispiel zeigt diese Syntax.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-147">The following example shows this syntax.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="2ec2c-148">Weitere Informationen finden Sie unter [Konstruktoren (F #)](members/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="2ec2c-148">For more information, see [Constructors (F#)](members/constructors.md).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="2ec2c-149">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="2ec2c-149">Optional Parameters</span></span>

<span data-ttu-id="2ec2c-150">Sie können einen optionalen Parameter für eine Methode angeben, indem Sie ein Fragezeichen vor dem Parameternamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-150">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="2ec2c-151">Optionale Parameter werden als F #-Optionstyp interpretiert, sodass Sie Sie in regulärer Weise Abfragen können, indem Sie einen `match` -Ausdruck mit `Some` und verwenden `None` .</span><span class="sxs-lookup"><span data-stu-id="2ec2c-151">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="2ec2c-152">Optionale Parameter sind nur für Member zulässig, nicht für Funktionen, die mithilfe von Bindungen erstellt wurden `let` .</span><span class="sxs-lookup"><span data-stu-id="2ec2c-152">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="2ec2c-153">Sie können vorhandene optionale Werte an die-Methode über den Parameternamen übergeben, z `?arg=None` `?arg=Some(3)` . b. oder `?arg=arg` .</span><span class="sxs-lookup"><span data-stu-id="2ec2c-153">You can pass existing optional values to method by parameter name, such as `?arg=None` or `?arg=Some(3)` or `?arg=arg`.</span></span> <span data-ttu-id="2ec2c-154">Dies kann bei der Erstellung einer Methode nützlich sein, die optionale Argumente an eine andere Methode übergibt.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-154">This can be useful when building a method that passes optional arguments to another method.</span></span>

<span data-ttu-id="2ec2c-155">Sie können auch eine Funktion verwenden `defaultArg` , mit der ein Standardwert eines optionalen Arguments festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-155">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="2ec2c-156">Die `defaultArg` -Funktion übernimmt den optionalen-Parameter als erstes Argument und den Standardwert als zweiten.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-156">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="2ec2c-157">Das folgende Beispiel veranschaulicht die Verwendung optionaler Parameter.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-157">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="2ec2c-158">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-158">The output is as follows.</span></span>

```console
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

<span data-ttu-id="2ec2c-159">Für c#-und Visual Basic Interop können Sie die Attribute `[<Optional; DefaultParameterValue<(...)>]` in F # verwenden, sodass Aufrufern ein Argument als optional angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-159">For the purposes of C# and Visual Basic interop you can use the attributes `[<Optional; DefaultParameterValue<(...)>]` in F#, so that callers will see an argument as optional.</span></span> <span data-ttu-id="2ec2c-160">Dies entspricht der Definition des Arguments in c# wie in `MyMethod(int i = 3)` .</span><span class="sxs-lookup"><span data-stu-id="2ec2c-160">This is equivalent to defining the argument as optional in C# as in `MyMethod(int i = 3)`.</span></span>

```fsharp
open System
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn $"{message}"
```

<span data-ttu-id="2ec2c-161">Sie können auch ein neues-Objekt als Standardparameter Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-161">You can also specify a new object as a default parameter value.</span></span> <span data-ttu-id="2ec2c-162">Der `Foo` Member könnte beispielsweise optional `CancellationToken` als Eingabe enthalten:</span><span class="sxs-lookup"><span data-stu-id="2ec2c-162">For example, the `Foo` member could have an optional `CancellationToken` as input instead:</span></span>

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn $"{ct}"
```

<span data-ttu-id="2ec2c-163">Der als Argument angegebene Wert `DefaultParameterValue` muss mit dem Typ des Parameters identisch sein.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-163">The value given as argument to `DefaultParameterValue` must match the type of the parameter.</span></span> <span data-ttu-id="2ec2c-164">Beispielsweise ist Folgendes nicht zulässig:</span><span class="sxs-lookup"><span data-stu-id="2ec2c-164">For example, the following is not allowed:</span></span>

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

<span data-ttu-id="2ec2c-165">In diesem Fall generiert der Compiler eine Warnung und ignoriert beide Attribute vollständig.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-165">In this case, the compiler generates a warning and will ignore both attributes altogether.</span></span> <span data-ttu-id="2ec2c-166">Beachten Sie, dass der Standardwert `null` typkommentiert werden muss, da der Compiler andernfalls den falschen Typ, d. h., anleitet `[<Optional; DefaultParameterValue(null:obj)>] o:obj` .</span><span class="sxs-lookup"><span data-stu-id="2ec2c-166">Note that the default value `null` needs to be type-annotated, as otherwise the compiler infers the wrong type, i.e. `[<Optional; DefaultParameterValue(null:obj)>] o:obj`.</span></span>

## <a name="passing-by-reference"></a><span data-ttu-id="2ec2c-167">Übergeben als Verweis</span><span class="sxs-lookup"><span data-stu-id="2ec2c-167">Passing by Reference</span></span>

<span data-ttu-id="2ec2c-168">Das Übergeben eines F #-Werts als Verweis umfasst [ByRefs](byrefs.md), bei denen es sich um verwaltete Zeiger Typen handelt.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-168">Passing an F# value by reference involves [byrefs](byrefs.md), which are managed pointer types.</span></span> <span data-ttu-id="2ec2c-169">Der zu verwendende Typ lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2ec2c-169">Guidance for which type to use is as follows:</span></span>

- <span data-ttu-id="2ec2c-170">Verwenden `inref<'T>` Sie, wenn Sie nur den Zeiger lesen müssen.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-170">Use `inref<'T>` if you only need to read the pointer.</span></span>
- <span data-ttu-id="2ec2c-171">Verwenden `outref<'T>` Sie, wenn Sie nur in den Zeiger schreiben müssen.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-171">Use `outref<'T>` if you only need to write to the pointer.</span></span>
- <span data-ttu-id="2ec2c-172">Verwenden `byref<'T>` Sie, wenn Sie sowohl Lese-als auch Schreibzugriff auf den Zeiger benötigen.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-172">Use `byref<'T>` if you need to both read from and write to the pointer.</span></span>

```fsharp
let example1 (x: inref<int>) = printfn $"It's %d{x}"

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn $"It's %d{x}"
    x <- x + 1

let test () =
    // No need to make it mutable, since it's read-only
    let x = 1
    example1 &x

    // Needs to be mutable, since we write to it
    let mutable y = 2
    example2 &y
    example3 &y // Now 'y' is 3
```

<span data-ttu-id="2ec2c-173">Da der-Parameter ein Zeiger ist und der Wert änderbar ist, werden alle Änderungen am Wert nach der Ausführung der Funktion beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-173">Because the parameter is a pointer and the value is mutable, any changes to the value are retained after the execution of the function.</span></span>

<span data-ttu-id="2ec2c-174">Sie können ein Tupel als Rückgabewert verwenden, um `out` Parameter in .net-Bibliotheks Methoden zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-174">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="2ec2c-175">Alternativ können Sie den `out` Parameter als `byref` Parameter behandeln.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-175">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="2ec2c-176">Im folgenden Codebeispiel werden beide Methoden veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-176">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="2ec2c-177">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="2ec2c-177">Parameter Arrays</span></span>

<span data-ttu-id="2ec2c-178">Gelegentlich ist es erforderlich, eine Funktion zu definieren, die eine beliebige Anzahl von Parametern des heterogenen Typs annimmt.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-178">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="2ec2c-179">Es wäre nicht praktikabel, alle möglichen überladenen Methoden zu erstellen, um alle Typen zu berücksichtigen, die verwendet werden könnten.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-179">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="2ec2c-180">Die .net-Implementierungen unterstützen solche Methoden durch das Parameter Array Feature.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-180">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="2ec2c-181">Eine Methode, die ein Parameter Array in der Signatur annimmt, kann mit einer beliebigen Anzahl von Parametern bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-181">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="2ec2c-182">Die Parameter werden in einem Array abgelegt.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-182">The parameters are put into an array.</span></span> <span data-ttu-id="2ec2c-183">Der Typ der Array Elemente bestimmt die Parametertypen, die an die Funktion übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-183">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="2ec2c-184">Wenn Sie das Parameter Array mit `System.Object` als Elementtyp definieren, kann der Client Code Werte eines beliebigen Typs übergeben.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-184">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="2ec2c-185">In F # können Parameter Arrays nur in Methoden definiert werden.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-185">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="2ec2c-186">Sie können nicht in eigenständigen Funktionen oder Funktionen verwendet werden, die in Modulen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-186">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="2ec2c-187">Ein Parameter Array wird mithilfe des- `ParamArray` Attributs definiert.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-187">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="2ec2c-188">Das- `ParamArray` Attribut kann nur auf den letzten Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-188">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="2ec2c-189">Der folgende Code veranschaulicht, wie Sie eine .NET-Methode aufrufen, die ein Parameter Array annimmt, und die Definition eines Typs in F #, der über eine-Methode verfügt, die ein Parameter Array annimmt.</span><span class="sxs-lookup"><span data-stu-id="2ec2c-189">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="2ec2c-190">Wenn Sie in einem Projekt ausführen, lautet die Ausgabe des vorherigen Codes wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2ec2c-190">When run in a project, the output of the previous code is as follows:</span></span>

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="2ec2c-191">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2ec2c-191">See also</span></span>

- [<span data-ttu-id="2ec2c-192">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="2ec2c-192">Members</span></span>](./members/index.md)
