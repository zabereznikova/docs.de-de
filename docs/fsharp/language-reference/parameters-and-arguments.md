---
title: Parameter und Argumente
description: Erfahren Sie mehr über die Sprachunterstützung von F- zum Definieren von Parametern und Übergeben von Argumenten an Funktionen, Methoden und Eigenschaften.
ms.date: 12/04/2019
ms.openlocfilehash: b234ef939128e7cf09d35f9580d4d5010d7dc639
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401052"
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="07494-103">Parameter und Argumente</span><span class="sxs-lookup"><span data-stu-id="07494-103">Parameters and Arguments</span></span>

<span data-ttu-id="07494-104">In diesem Thema wird die Sprachunterstützung zum Definieren von Parametern und Übergeben von Argumenten an Funktionen, Methoden und Eigenschaften beschrieben.</span><span class="sxs-lookup"><span data-stu-id="07494-104">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="07494-105">Sie enthält Informationen zum Übergeben von Verweis und zum Definieren und Verwenden von Methoden, die eine variable Anzahl von Argumenten annehmen können.</span><span class="sxs-lookup"><span data-stu-id="07494-105">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>

## <a name="parameters-and-arguments"></a><span data-ttu-id="07494-106">Parameter und Argumente</span><span class="sxs-lookup"><span data-stu-id="07494-106">Parameters and Arguments</span></span>

<span data-ttu-id="07494-107">Der *Begriffparameter* wird verwendet, um die Namen für Werte zu beschreiben, die voraussichtlich angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="07494-107">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="07494-108">Das *Termargument* wird für die für jeden Parameter bereitgestellten Werte verwendet.</span><span class="sxs-lookup"><span data-stu-id="07494-108">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="07494-109">Parameter können in Tupel- oder Curryform oder in einer Kombination aus beiden angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="07494-109">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="07494-110">Sie können Argumente übergeben, indem Sie einen expliziten Parameternamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="07494-110">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="07494-111">Parameter von Methoden können als optional angegeben und mit einem Standardwert angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="07494-111">Parameters of methods can be specified as optional and given a default value.</span></span>

## <a name="parameter-patterns"></a><span data-ttu-id="07494-112">Parametermuster</span><span class="sxs-lookup"><span data-stu-id="07494-112">Parameter Patterns</span></span>

<span data-ttu-id="07494-113">Parameter, die Funktionen und Methoden zur Verfügung gestellt werden, sind im Allgemeinen Muster, die durch Leerzeichen getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="07494-113">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="07494-114">Dies bedeutet, dass grundsätzlich jedes der in [Match Expressions](match-expressions.md) beschriebenen Muster in einer Parameterliste für eine Funktion oder einen Member verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="07494-114">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="07494-115">Methoden verwenden in der Regel die Tupelform des Übergebens von Argumenten.</span><span class="sxs-lookup"><span data-stu-id="07494-115">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="07494-116">Dies führt zu einem klareren Ergebnis aus der Perspektive anderer .NET-Sprachen, da das Tupelformular mit der Art und Weise übereinstimmt, wie Argumente in .NET-Methoden übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="07494-116">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="07494-117">Das Curry-Formular wird am häufigsten mit `let` Funktionen verwendet, die mithilfe von Bindungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="07494-117">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="07494-118">Der folgende Pseudocode zeigt Beispiele für Tupel- und Curry-Argumente.</span><span class="sxs-lookup"><span data-stu-id="07494-118">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="07494-119">Kombinierte Formulare sind möglich, wenn einige Argumente in Tupeln sind und einige nicht.</span><span class="sxs-lookup"><span data-stu-id="07494-119">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="07494-120">Andere Muster können auch in Parameterlisten verwendet werden, aber wenn das Parametermuster nicht mit allen möglichen Eingaben übereinstimmt, kann es zur Laufzeit zu einer unvollständigen Übereinstimmung führen.</span><span class="sxs-lookup"><span data-stu-id="07494-120">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="07494-121">Die `MatchFailureException` Ausnahme wird generiert, wenn der Wert eines Arguments nicht mit den in der Parameterliste angegebenen Mustern übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="07494-121">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="07494-122">Der Compiler gibt eine Warnung aus, wenn ein Parametermuster unvollständige Übereinstimmungen zulässt.</span><span class="sxs-lookup"><span data-stu-id="07494-122">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="07494-123">Mindestens ein anderes Muster ist häufig für Parameterlisten nützlich, und das ist das Platzhaltermuster.</span><span class="sxs-lookup"><span data-stu-id="07494-123">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="07494-124">Sie verwenden das Platzhaltermuster in einer Parameterliste, wenn Sie einfach alle angegebenen Argumente ignorieren möchten.</span><span class="sxs-lookup"><span data-stu-id="07494-124">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="07494-125">Der folgende Code veranschaulicht die Verwendung des Platzhaltermusters in einer Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="07494-125">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="07494-126">Das Platzhaltermuster kann nützlich sein, wenn Sie die übergebenen Argumente nicht benötigen, z. B. im Haupteinstiegspunkt an ein Programm, wenn Sie nicht an den Befehlszeilenargumenten interessiert sind, die normalerweise als Zeichenfolgenarray bereitgestellt werden, wie im folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="07494-126">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="07494-127">Andere Muster, die manchmal in `as` Argumenten verwendet werden, sind das Muster und Bezeichnermuster, die mit diskriminierten Gewerkschaften und aktiven Mustern verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="07494-127">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="07494-128">Sie können das einzelne diskriminierte Union-Muster wie folgt verwenden.</span><span class="sxs-lookup"><span data-stu-id="07494-128">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="07494-129">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="07494-129">The output is as follows.</span></span>

```console
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="07494-130">Aktive Muster können als Parameter nützlich sein, z. B. beim Transformieren eines Arguments in ein gewünschtes Format, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="07494-130">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="07494-131">Sie können `as` das Muster verwenden, um einen übereinstimmenden Wert als lokalen Wert zu speichern, wie in der folgenden Codezeile dargestellt.</span><span class="sxs-lookup"><span data-stu-id="07494-131">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="07494-132">Ein anderes Muster, das gelegentlich verwendet wird, ist eine Funktion, die das letzte Argument unbenannt lässt, indem als Text der Funktion ein Lambda-Ausdruck bereitstellt, der sofort eine Musterübereinstimmung für das implizite Argument ausführt.</span><span class="sxs-lookup"><span data-stu-id="07494-132">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="07494-133">Ein Beispiel hierfür ist die folgende Codezeile.</span><span class="sxs-lookup"><span data-stu-id="07494-133">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="07494-134">Dieser Code definiert eine Funktion, die `true` eine generische Liste annimmt und zurückgibt, wenn die Liste leer ist, und `false` auf andere Weise.</span><span class="sxs-lookup"><span data-stu-id="07494-134">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="07494-135">Die Verwendung solcher Techniken kann das Lesen von Code erschweren.</span><span class="sxs-lookup"><span data-stu-id="07494-135">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="07494-136">Gelegentlich sind Muster, die unvollständige Übereinstimmungen beinhalten, nützlich, z. B. wenn Sie wissen, dass die Listen in Ihrem Programm nur drei Elemente enthalten, können Sie ein Muster wie das folgende in einer Parameterliste verwenden.</span><span class="sxs-lookup"><span data-stu-id="07494-136">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="07494-137">Die Verwendung von Mustern, die unvollständige Übereinstimmungen aufweisen, ist am besten für schnelles Prototyping und andere temporäre Verwendungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="07494-137">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="07494-138">Der Compiler gibt eine Warnung für diesen Code aus.</span><span class="sxs-lookup"><span data-stu-id="07494-138">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="07494-139">Solche Muster können nicht den allgemeinen Fall aller möglichen Eingänge abdecken und sind daher nicht für Komponenten-APIs geeignet.</span><span class="sxs-lookup"><span data-stu-id="07494-139">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="07494-140">Benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="07494-140">Named Arguments</span></span>

<span data-ttu-id="07494-141">Argumente für Methoden können durch Position in einer durch Kommas getrennten Argumentliste angegeben werden, oder sie können explizit an eine Methode übergeben werden, indem der Name angegeben wird, gefolgt von einem Gleichheitszeichen und dem wert, der übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="07494-141">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="07494-142">Wenn sie durch Angabe des Namens angegeben werden, können sie in einer anderen Reihenfolge als in der Deklaration angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="07494-142">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="07494-143">Benannte Argumente können Code lesbarer und anpassungsfähiger für bestimmte Arten von Änderungen in der API machen, z. B. eine Neuanordnung von Methodenparametern.</span><span class="sxs-lookup"><span data-stu-id="07494-143">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="07494-144">Benannte Argumente sind nur für `let`Methoden zulässig, nicht für -bound-Funktionen, Funktionswerte oder Lambda-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="07494-144">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="07494-145">Im folgenden Codebeispiel wird die Verwendung benannter Argumente veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="07494-145">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="07494-146">In einem Aufruf eines Klassenkonstruktors können Sie die Werte der Eigenschaften der Klasse festlegen, indem Sie eine Syntax verwenden, die der von benannten Argumenten ähnelt.</span><span class="sxs-lookup"><span data-stu-id="07494-146">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="07494-147">Das folgende Beispiel zeigt diese Syntax.</span><span class="sxs-lookup"><span data-stu-id="07494-147">The following example shows this syntax.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="07494-148">Weitere Informationen finden Sie unter [Konstruktoren (F)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span><span class="sxs-lookup"><span data-stu-id="07494-148">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="07494-149">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="07494-149">Optional Parameters</span></span>

<span data-ttu-id="07494-150">Sie können einen optionalen Parameter für eine Methode angeben, indem Sie ein Fragezeichen vor dem Parameternamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="07494-150">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="07494-151">Optionale Parameter werden als Optionstyp "F" interpretiert, sodass Sie sie auf die `match` reguläre `Some` Art `None`und Weise abfragen können, dass Optionstypen abgefragt werden, indem Sie einen Ausdruck mit und verwenden.</span><span class="sxs-lookup"><span data-stu-id="07494-151">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="07494-152">Optionale Parameter sind nur für Member zulässig, nicht für Funktionen, die mithilfe `let` von Bindungen erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="07494-152">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="07494-153">Sie können vorhandene optionale Werte nach Parametername an die Methode übergeben, z. `?arg=None` B. oder `?arg=Some(3)` oder `?arg=arg`.</span><span class="sxs-lookup"><span data-stu-id="07494-153">You can pass existing optional values to method by parameter name, such as `?arg=None` or `?arg=Some(3)` or `?arg=arg`.</span></span> <span data-ttu-id="07494-154">Dies kann nützlich sein, wenn Sie eine Methode erstellen, die optionale Argumente an eine andere Methode übergibt.</span><span class="sxs-lookup"><span data-stu-id="07494-154">This can be useful when building a method that passes optional arguments to another method.</span></span>

<span data-ttu-id="07494-155">Sie können auch `defaultArg`eine Funktion verwenden, die einen Standardwert eines optionalen Arguments festlegt.</span><span class="sxs-lookup"><span data-stu-id="07494-155">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="07494-156">Die `defaultArg` Funktion nimmt den optionalen Parameter als erstes Argument und den Standardwert als zweites.</span><span class="sxs-lookup"><span data-stu-id="07494-156">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="07494-157">Das folgende Beispiel veranschaulicht die Verwendung optionaler Parameter.</span><span class="sxs-lookup"><span data-stu-id="07494-157">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="07494-158">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="07494-158">The output is as follows.</span></span>

```console
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

<span data-ttu-id="07494-159">Für die Zwecke des Interops "C" und `[<Optional; DefaultParameterValue<(...)>]` des Visual Basic-Interops können Sie die Attribute in F- verwenden, sodass Aufrufer ein Argument als optional anzeigen.</span><span class="sxs-lookup"><span data-stu-id="07494-159">For the purposes of C# and Visual Basic interop you can use the attributes `[<Optional; DefaultParameterValue<(...)>]` in F#, so that callers will see an argument as optional.</span></span> <span data-ttu-id="07494-160">Dies entspricht dem Definieren des Arguments als `MyMethod(int i = 3)`optional in C- wie in .</span><span class="sxs-lookup"><span data-stu-id="07494-160">This is equivalent to defining the argument as optional in C# as in `MyMethod(int i = 3)`.</span></span>

```fsharp
open System
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

<span data-ttu-id="07494-161">Sie können auch ein neues Objekt als Standardparameterwert angeben.</span><span class="sxs-lookup"><span data-stu-id="07494-161">You can also specify a new object as a default parameter value.</span></span> <span data-ttu-id="07494-162">Das `Foo` Element kann z. `CancellationToken` B. eine optionale Eingabe als Eingabe haben:</span><span class="sxs-lookup"><span data-stu-id="07494-162">For example, the `Foo` member could have an optional `CancellationToken` as input instead:</span></span>

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

<span data-ttu-id="07494-163">Der Wert, der `DefaultParameterValue` als Argument angegeben wird, muss mit dem Typ des Parameters übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="07494-163">The value given as argument to `DefaultParameterValue` must match the type of the parameter.</span></span> <span data-ttu-id="07494-164">Das Folgende ist z. B. nicht zulässig:</span><span class="sxs-lookup"><span data-stu-id="07494-164">For example, the following is not allowed:</span></span>

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

<span data-ttu-id="07494-165">In diesem Fall generiert der Compiler eine Warnung und ignoriert beide Attribute vollständig.</span><span class="sxs-lookup"><span data-stu-id="07494-165">In this case, the compiler generates a warning and will ignore both attributes altogether.</span></span> <span data-ttu-id="07494-166">Beachten Sie, `null` dass der Standardwert typannotiert werden muss, da der Compiler andernfalls `[<Optional; DefaultParameterValue(null:obj)>] o:obj`den falschen Typ ableitet, d. h. .</span><span class="sxs-lookup"><span data-stu-id="07494-166">Note that the default value `null` needs to be type-annotated, as otherwise the compiler infers the wrong type, i.e. `[<Optional; DefaultParameterValue(null:obj)>] o:obj`.</span></span>

## <a name="passing-by-reference"></a><span data-ttu-id="07494-167">Vorbeianreise durch Referenz</span><span class="sxs-lookup"><span data-stu-id="07494-167">Passing by Reference</span></span>

<span data-ttu-id="07494-168">Das Übergeben eines F-Werts als Verweis umfasst [byrefs](byrefs.md), die verwaltete Zeigertypen sind.</span><span class="sxs-lookup"><span data-stu-id="07494-168">Passing an F# value by reference involves [byrefs](byrefs.md), which are managed pointer types.</span></span> <span data-ttu-id="07494-169">Anleitung für den typ, der verwendet werden soll, lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="07494-169">Guidance for which type to use is as follows:</span></span>

- <span data-ttu-id="07494-170">Verwenden `inref<'T>` Sie diese Datei, wenn Sie nur den Zeiger lesen müssen.</span><span class="sxs-lookup"><span data-stu-id="07494-170">Use `inref<'T>` if you only need to read the pointer.</span></span>
- <span data-ttu-id="07494-171">Verwenden `outref<'T>` Sie diese Datei, wenn Sie nur in den Zeiger schreiben müssen.</span><span class="sxs-lookup"><span data-stu-id="07494-171">Use `outref<'T>` if you only need to write to the pointer.</span></span>
- <span data-ttu-id="07494-172">Verwenden `byref<'T>` Sie diese Verwendung, wenn Sie sowohl aus dem Zeiger lesen als auch in den Zeiger schreiben müssen.</span><span class="sxs-lookup"><span data-stu-id="07494-172">Use `byref<'T>` if you need to both read from and write to the pointer.</span></span>

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
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

<span data-ttu-id="07494-173">Da der Parameter ein Zeiger ist und der Wert veränderbar ist, werden alle Änderungen am Wert nach der Ausführung der Funktion beibehalten.</span><span class="sxs-lookup"><span data-stu-id="07494-173">Because the parameter is a pointer and the value is mutable, any changes to the value are retained after the execution of the function.</span></span>

<span data-ttu-id="07494-174">Sie können ein Tupel als Rückgabewert `out` verwenden, um alle Parameter in .NET-Bibliotheksmethoden zu speichern.</span><span class="sxs-lookup"><span data-stu-id="07494-174">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="07494-175">Alternativ können Sie den `out` Parameter `byref` auch als Parameter behandeln.</span><span class="sxs-lookup"><span data-stu-id="07494-175">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="07494-176">Das folgende Codebeispiel veranschaulicht beide Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="07494-176">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="07494-177">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="07494-177">Parameter Arrays</span></span>

<span data-ttu-id="07494-178">Gelegentlich ist es notwendig, eine Funktion zu definieren, die eine beliebige Anzahl von Parametern heterogenen Typs annimmt.</span><span class="sxs-lookup"><span data-stu-id="07494-178">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="07494-179">Es wäre nicht praktikabel, alle möglichen überladenen Methoden zu erstellen, um alle Typen zu berücksichtigen, die verwendet werden könnten.</span><span class="sxs-lookup"><span data-stu-id="07494-179">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="07494-180">Die .NET-Implementierungen unterstützen solche Methoden über das Parameterarray-Feature.</span><span class="sxs-lookup"><span data-stu-id="07494-180">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="07494-181">Eine Methode, die ein Parameterarray in ihrer Signatur übernimmt, kann mit einer beliebigen Anzahl von Parametern bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="07494-181">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="07494-182">Die Parameter werden in ein Array eingefügt.</span><span class="sxs-lookup"><span data-stu-id="07494-182">The parameters are put into an array.</span></span> <span data-ttu-id="07494-183">Der Typ der Arrayelemente bestimmt die Parametertypen, die an die Funktion übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="07494-183">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="07494-184">Wenn Sie das Parameterarray mit `System.Object` als Elementtyp definieren, kann Clientcode Werte eines beliebigen Typs übergeben.</span><span class="sxs-lookup"><span data-stu-id="07494-184">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="07494-185">Parameterarrays können nur in Methoden definiert werden.</span><span class="sxs-lookup"><span data-stu-id="07494-185">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="07494-186">Sie können nicht in eigenständigen Funktionen oder Funktionen verwendet werden, die in Modulen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="07494-186">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="07494-187">Sie definieren ein Parameterarray `ParamArray` mithilfe des Attributs.</span><span class="sxs-lookup"><span data-stu-id="07494-187">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="07494-188">Das `ParamArray` Attribut kann nur auf den letzten Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="07494-188">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="07494-189">Der folgende Code veranschaulicht sowohl das Aufrufen einer .NET-Methode, die ein Parameterarray verwendet, als auch die Definition eines Typs in F, der über eine Methode verfügt, die ein Parameterarray verwendet.</span><span class="sxs-lookup"><span data-stu-id="07494-189">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="07494-190">Bei Der Ausführung in einem Projekt wird der vorherige Code wie folgt ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="07494-190">When run in a project, the output of the previous code is as follows:</span></span>

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="07494-191">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07494-191">See also</span></span>

- [<span data-ttu-id="07494-192">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="07494-192">Members</span></span>](./members/index.md)
