---
title: Parameter und Argumente (F#)
description: Informationen Sie zu F#-sprachunterstützung für das Definieren von Parametern und übergeben von Argumenten zu Funktionen, Methoden und Eigenschaften.
ms.date: 05/16/2016
ms.openlocfilehash: 319cf0e7346d498ce34e41a9993fe0160038461a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566219"
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="1fafa-103">Parameter und Argumente</span><span class="sxs-lookup"><span data-stu-id="1fafa-103">Parameters and Arguments</span></span>

<span data-ttu-id="1fafa-104">Dieses Thema beschreibt die sprachunterstützung für das Definieren von Parametern und übergeben von Argumenten zu Funktionen, Methoden und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="1fafa-104">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="1fafa-105">Es enthält Informationen über das als Verweis übergeben und das Definieren und Verwenden von Methoden, die eine Variable Anzahl von Argumenten akzeptieren können.</span><span class="sxs-lookup"><span data-stu-id="1fafa-105">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>


## <a name="parameters-and-arguments"></a><span data-ttu-id="1fafa-106">Parameter und Argumente</span><span class="sxs-lookup"><span data-stu-id="1fafa-106">Parameters and Arguments</span></span>
<span data-ttu-id="1fafa-107">Der Begriff *Parameter* wird verwendet, um die Namen für die Werte zu beschreiben, die bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1fafa-107">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="1fafa-108">Der Begriff *Argument* wird verwendet, für die Werte für jeden Parameter bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1fafa-108">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="1fafa-109">Parameter können in Tupel oder Curry-Form oder in einer Kombination von beiden angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1fafa-109">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="1fafa-110">Sie können Argumente übergeben, indem Sie eine explizite Parameternamen.</span><span class="sxs-lookup"><span data-stu-id="1fafa-110">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="1fafa-111">Parameter der Methoden können als optional angegeben und einen Standardwert angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1fafa-111">Parameters of methods can be specified as optional and given a default value.</span></span>


## <a name="parameter-patterns"></a><span data-ttu-id="1fafa-112">Parametermuster</span><span class="sxs-lookup"><span data-stu-id="1fafa-112">Parameter Patterns</span></span>
<span data-ttu-id="1fafa-113">Funktionen und Methoden eingegebenen Parameter sind im allgemeinen Mustern, die durch Leerzeichen getrennt an.</span><span class="sxs-lookup"><span data-stu-id="1fafa-113">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="1fafa-114">Dies bedeutet, dass im Prinzip die Muster beschrieben [Übereinstimmungsausdrücken](match-expressions.md) für eine Funktion oder ein Element in einer Parameterliste verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1fafa-114">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="1fafa-115">In der Regel verwenden Sie Methoden Tupelform übergeben von Argumenten.</span><span class="sxs-lookup"><span data-stu-id="1fafa-115">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="1fafa-116">Dadurch wird ein besseres Ergebnis aus der Perspektive eines anderen erreicht, da die Tupelform wie übereinstimmt, die in .NET-Methoden Argumente übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="1fafa-116">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="1fafa-117">Die Curry-Form werden am häufigsten verwendet, mit Funktionen, die mithilfe von erstellt `let` Bindungen.</span><span class="sxs-lookup"><span data-stu-id="1fafa-117">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="1fafa-118">Der folgende Pseudocode zeigt Beispiele für Tupel und Curry-Argumente.</span><span class="sxs-lookup"><span data-stu-id="1fafa-118">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="1fafa-119">Kombinierte Formen sind möglich, wenn einige Argumente in Tupeln sind und einige nicht.</span><span class="sxs-lookup"><span data-stu-id="1fafa-119">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="1fafa-120">Andere Muster können auch in Parameterlisten verwendet werden, aber wenn das Muster der Parameter nicht alle Mögliche Eingaben übereinstimmt, gibt es möglicherweise eine unvollständige Übereinstimmung zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="1fafa-120">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="1fafa-121">Die Ausnahme `MatchFailureException` wird generiert, wenn der Wert eines Arguments nicht die in der Parameterliste angegebenen Mustern übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="1fafa-121">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="1fafa-122">Der Compiler einer Warnung, wenn ein Muster für die Parameter für unvollständige Übereinstimmungen zulässt.</span><span class="sxs-lookup"><span data-stu-id="1fafa-122">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="1fafa-123">Mindestens eine andere Muster ist häufig hilfreich für Parameterlisten und, die das Platzhaltermuster wird.</span><span class="sxs-lookup"><span data-stu-id="1fafa-123">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="1fafa-124">Sie verwenden das Platzhaltermuster in einer Parameterliste, wenn einfach ignorieren keine Argumente, die bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1fafa-124">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="1fafa-125">Der folgende Code veranschaulicht die Verwendung des Platzhaltermusters in einer Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="1fafa-125">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="1fafa-126">Das Platzhaltermuster kann hilfreich, wenn Sie die übergebenen Argumente nicht benötigen, z. B. den Haupteinstiegspunkt für ein Programm sein, wenn Sie nicht die Befehlszeilenargumente interessiert sind, die normalerweise als ein Array von Zeichenfolgen, wie im folgenden Code angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1fafa-126">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="1fafa-127">Sind andere Muster, die in-Argumente verwendet werden die `as` Muster und Bezeichnermuster Unterscheidungs-Unions und aktive Muster zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1fafa-127">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="1fafa-128">Sie können die einzelnen Fall Unterscheidungs-union-Muster wie folgt verwenden.</span><span class="sxs-lookup"><span data-stu-id="1fafa-128">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="1fafa-129">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="1fafa-129">The output is as follows.</span></span>

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="1fafa-130">Aktive Muster können als Parameter, z. B. hilfreich sein, die bei der Transformation ein Argument in einem gewünschten Format, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1fafa-130">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="1fafa-131">Sie können die `as` Muster, um einen übereinstimmenden Wert als einen lokalen Wert zu speichern, wie in der folgenden Zeile des Codes dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1fafa-131">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="1fafa-132">Ein anderes Muster, das gelegentlich verwendet wird, ist eine Funktion, die bewirkt, das letzte Argument unbenannte dass bereitstellen, wie der Text der Funktion, ein Lambda-Ausdruck, der sofort einen Mustervergleich für das implizite Argument ausführt.</span><span class="sxs-lookup"><span data-stu-id="1fafa-132">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="1fafa-133">Ein Beispiel hierfür ist die folgende Codezeile.</span><span class="sxs-lookup"><span data-stu-id="1fafa-133">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="1fafa-134">Dieser Code definiert eine Funktion, die eine generische Liste akzeptiert und gibt `true` Wenn die Liste leer ist und `false` andernfalls.</span><span class="sxs-lookup"><span data-stu-id="1fafa-134">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="1fafa-135">Die Verwendung solcher Techniken vererbungsoptionen Code schwieriger zu lesen.</span><span class="sxs-lookup"><span data-stu-id="1fafa-135">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="1fafa-136">In einigen Fällen eignen sich Muster, die unvollständige Übereinstimmungen einschließen, z. B. Wenn Sie wissen, dass die Listen in Ihrem Programm nur drei Elemente verfügen, können ein Muster wie folgt in einer Parameterliste.</span><span class="sxs-lookup"><span data-stu-id="1fafa-136">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="1fafa-137">Die Verwendung von Mustern, die unvollständig übereinstimmenden ist am besten für schnellen Prototyping und andere temporäre Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="1fafa-137">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="1fafa-138">Der Compiler wird einer Warnung für diesen Code.</span><span class="sxs-lookup"><span data-stu-id="1fafa-138">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="1fafa-139">Muster dieser Art können nicht im allgemeinen Fall alle möglichen Eingaben behandelt und sind daher nicht für die Komponente APIs geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="1fafa-139">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="1fafa-140">Benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="1fafa-140">Named Arguments</span></span>
<span data-ttu-id="1fafa-141">Argumente für Methoden können anhand der Position in einer durch Trennzeichen getrennte Argumentliste angegeben werden, oder sie können übergeben werden an eine Methode explizit durch Eingabe des Namens, gefolgt von einem Gleichheitszeichen und dem Wert übergeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="1fafa-141">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="1fafa-142">Wenn angegeben, indem Sie den Namen angeben, können sie in einer anderen Reihenfolge aus, die in der Deklaration verwendet angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1fafa-142">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="1fafa-143">Benannte Argumente können Code besser lesbar und mehr anwendbare bestimmter Arten von Änderungen in der API, z. B. eine neuanordnung der Parameter der Methode vornehmen.</span><span class="sxs-lookup"><span data-stu-id="1fafa-143">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="1fafa-144">Benannte Argumente dürfen nur für Methoden, nicht für `let`-Funktionen, Funktionswerte oder Lambda-Ausdrücke gebunden.</span><span class="sxs-lookup"><span data-stu-id="1fafa-144">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="1fafa-145">Das folgende Codebeispiel veranschaulicht die Verwendung von benannten Argumenten.</span><span class="sxs-lookup"><span data-stu-id="1fafa-145">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="1fafa-146">In einem Aufruf für einen Klassenkonstruktor können Sie die Werte der Eigenschaften der Klasse mit einer Syntax ähnelt der von benannten Argumenten festlegen.</span><span class="sxs-lookup"><span data-stu-id="1fafa-146">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="1fafa-147">Das folgende Beispiel zeigt diese Syntax.</span><span class="sxs-lookup"><span data-stu-id="1fafa-147">The following example shows this syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="1fafa-148">Weitere Informationen finden Sie unter [Konstruktoren (f#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span><span class="sxs-lookup"><span data-stu-id="1fafa-148">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="1fafa-149">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="1fafa-149">Optional Parameters</span></span>
<span data-ttu-id="1fafa-150">Sie können einen optionalen Parameter für eine Methode mit einem Fragezeichen vor den Namen des Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="1fafa-150">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="1fafa-151">Optionale Parameter als F#-Optionstyp interpretiert werden, damit Sie auf die übliche Weise abgefragt werden können, dass Optionstypen, mithilfe abgefragt werden einer `match` Ausdruck mit `Some` und `None`.</span><span class="sxs-lookup"><span data-stu-id="1fafa-151">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="1fafa-152">Optionale Parameter dürfen nur für Elemente, nicht auf Funktionen, die mithilfe von erstellt `let` Bindungen.</span><span class="sxs-lookup"><span data-stu-id="1fafa-152">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="1fafa-153">Sie können auch eine Funktion `defaultArg`, der einen Standardwert eines optionalen Arguments festlegt.</span><span class="sxs-lookup"><span data-stu-id="1fafa-153">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="1fafa-154">Die `defaultArg` Funktion nimmt den optionalen Parameter als erstes Argument und der Standardwert als das zweite.</span><span class="sxs-lookup"><span data-stu-id="1fafa-154">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="1fafa-155">Das folgende Beispiel veranschaulicht die Verwendung von optionalen Parametern.</span><span class="sxs-lookup"><span data-stu-id="1fafa-155">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="1fafa-156">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="1fafa-156">The output is as follows.</span></span>

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
```

## <a name="passing-by-reference"></a><span data-ttu-id="1fafa-157">Übergeben als Verweis</span><span class="sxs-lookup"><span data-stu-id="1fafa-157">Passing by Reference</span></span>
<span data-ttu-id="1fafa-158">F# unterstützt die `byref` Schlüsselwort, das angibt, dass ein Parameter als Verweis übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="1fafa-158">F# supports the `byref` keyword, which specifies that a parameter is passed by reference.</span></span> <span data-ttu-id="1fafa-159">Dies bedeutet, dass alle Änderungen an den Wert nach der Ausführung der Funktion beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="1fafa-159">This means that any changes to the value are retained after the execution of the function.</span></span> <span data-ttu-id="1fafa-160">Werte bereitgestellt, um eine `byref` Parameter muss geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1fafa-160">Values provided to a `byref` parameter must be mutable.</span></span> <span data-ttu-id="1fafa-161">Alternativ können Sie Referenzzellen des entsprechenden Typs übergeben.</span><span class="sxs-lookup"><span data-stu-id="1fafa-161">Alternatively, you can pass reference cells of the appropriate type.</span></span>

<span data-ttu-id="1fafa-162">Übergeben als Verweis in .NET-Sprachen hat sich als eine Möglichkeit, mehr als einen Wert aus einer Funktion zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="1fafa-162">Passing by reference in .NET languages evolved as a way to return more than one value from a function.</span></span> <span data-ttu-id="1fafa-163">In F# erläutert werden können Sie zu diesem Zweck ein Tupel zurückgeben oder eine änderbare Referenzzelle als Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="1fafa-163">In F#, you can return a tuple for this purpose, or use a mutable reference cell as a parameter.</span></span> <span data-ttu-id="1fafa-164">Die `byref` Parameter wird hauptsächlich für die Interoperabilität mit.</span><span class="sxs-lookup"><span data-stu-id="1fafa-164">The `byref` parameter is mainly provided for interoperability with .NET libraries.</span></span>

<span data-ttu-id="1fafa-165">Die folgenden Beispiele veranschaulichen die Verwendung der `byref` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="1fafa-165">The following examples illustrate the use of the `byref` keyword.</span></span> <span data-ttu-id="1fafa-166">Beachten Sie, wenn Sie eine Referenzzelle als Parameter verwenden, muss eine Referenzzelle als einen benannten Wert erstellen und zu verwenden, die als Parameter nicht nur hinzufügen der `ref` Operator wie im ersten Aufruf von gezeigt `Increment` in den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="1fafa-166">Note that when you use a reference cell as a parameter, you must create a reference cell as a named value and use that as the parameter, not just add the `ref` operator as shown in the first call to `Increment` in the following code.</span></span> <span data-ttu-id="1fafa-167">Da eine Kopie des zugrunde liegenden Werts erstellen eine Referenzzelle erstellt wird, erhöht der erste Aufruf nur einen temporären Wert.</span><span class="sxs-lookup"><span data-stu-id="1fafa-167">Because creating a reference cell creates a copy of the underlying value, the first call just increments a temporary value.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3809.fs)]

<span data-ttu-id="1fafa-168">Sie können ein Tupel als Rückgabewert einer speichern `out` Parameter in .NET-Methoden-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="1fafa-168">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="1fafa-169">Alternativ können Sie behandeln die `out` Parameter als ein `byref` Parameter.</span><span class="sxs-lookup"><span data-stu-id="1fafa-169">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="1fafa-170">Im folgenden Codebeispiel wird veranschaulicht beide Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="1fafa-170">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="1fafa-171">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="1fafa-171">Parameter Arrays</span></span>
<span data-ttu-id="1fafa-172">Gelegentlich ist es erforderlich, um eine Funktion definieren, die eine beliebige Anzahl von Parametern heterogenen Typs akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="1fafa-172">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="1fafa-173">Es wäre nicht praktikabel ist, erstellen alle möglichen überladenen Methoden um für alle Typen zu berücksichtigen, die verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1fafa-173">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="1fafa-174">Die .NET Implementierungen bieten Unterstützung für solche Methoden über die Parameter-Array-Funktion.</span><span class="sxs-lookup"><span data-stu-id="1fafa-174">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="1fafa-175">Eine Methode, die in der Signatur ein Parameterarray akzeptiert, kann mit einer beliebigen Anzahl von Parametern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1fafa-175">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="1fafa-176">Die Parameter werden in ein Array eingefügt.</span><span class="sxs-lookup"><span data-stu-id="1fafa-176">The parameters are put into an array.</span></span> <span data-ttu-id="1fafa-177">Der Typ der Arrayelemente bestimmt die Parametertypen, die an die Funktion übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="1fafa-177">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="1fafa-178">Wenn Sie das Parameterarray mit definieren `System.Object` als Elementtyps Clientcode kann Werte dann übergeben eines beliebigen Typs.</span><span class="sxs-lookup"><span data-stu-id="1fafa-178">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="1fafa-179">In f# können Parameterarrays nur in Methoden definiert werden.</span><span class="sxs-lookup"><span data-stu-id="1fafa-179">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="1fafa-180">Sie können nicht verwendet werden, in der eigenständigen Funktionen oder Funktionen, die in Modulen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="1fafa-180">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="1fafa-181">Definieren Sie ein Parameterarray mithilfe der `ParamArray` Attribut.</span><span class="sxs-lookup"><span data-stu-id="1fafa-181">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="1fafa-182">Die `ParamArray` Attribut kann nur auf den letzten Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1fafa-182">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="1fafa-183">Das folgende Codebeispiel veranschaulicht eine .NET-Methode übergeben wird, die ein Parameterarray und die Definition eines Typs in f# verwendet, die eine Methode verfügt, die ein Parameterarray akzeptiert beide aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1fafa-183">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="1fafa-184">Wenn in einem Projekt ausführen, lautet die Ausgabe des vorherigen Codes wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1fafa-184">When run in a project, the output of the previous code is as follows:</span></span>

```
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="1fafa-185">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1fafa-185">See Also</span></span>
[<span data-ttu-id="1fafa-186">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="1fafa-186">Members</span></span>](members/index.md)
