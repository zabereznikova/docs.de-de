---
title: Funktionen als erstrangige Werte (F#)
description: "Erfahren Sie, wie Funktionen als erstrangige in der Programmiersprache f# erhöht werden."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 6b76b93b-a141-40f4-976c-7f0c558d6d09
ms.openlocfilehash: bca0e09edbe0aa86f0db746282acd4f4b3237a03
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="functions-as-first-class-values"></a><span data-ttu-id="0ff92-104">Funktionen als erstrangige Werte</span><span class="sxs-lookup"><span data-stu-id="0ff92-104">Functions as First-Class Values</span></span>

<span data-ttu-id="0ff92-105">Eine wichtige Eigenschaft funktionaler Programmiersprachen ist die Behandlung von Funktionen als erstrangige Werte.</span><span class="sxs-lookup"><span data-stu-id="0ff92-105">A defining characteristic of functional programming languages is the elevation of functions to first-class status.</span></span> <span data-ttu-id="0ff92-106">Sie sollten mit einer Funktion ohne Mehraufwand alle Vorgänge ausführen können, die Sie auch mit den Werten der anderen integrierten Typen ausführen können.</span><span class="sxs-lookup"><span data-stu-id="0ff92-106">You should be able to do with a function whatever you can do with values of the other built-in types, and be able to do so with a comparable degree of effort.</span></span>

<span data-ttu-id="0ff92-107">Zur Feststellung der Erstrangigkeit gehören folgende Kriterien:</span><span class="sxs-lookup"><span data-stu-id="0ff92-107">Typical measures of first-class status include the following:</span></span>

- <span data-ttu-id="0ff92-108">Binden Sie können Funktionen auf Bezeichner?</span><span class="sxs-lookup"><span data-stu-id="0ff92-108">Can you bind functions to identifiers?</span></span> <span data-ttu-id="0ff92-109">D. h., können Sie ihnen Namen geben?</span><span class="sxs-lookup"><span data-stu-id="0ff92-109">That is, can you give them names?</span></span>

- <span data-ttu-id="0ff92-110">Können Sie Funktionen in den Datenstrukturen, z. B. in einer Liste speichern?</span><span class="sxs-lookup"><span data-stu-id="0ff92-110">Can you store functions in data structures, such as in a list?</span></span>

- <span data-ttu-id="0ff92-111">Kann eine Funktion in einem Funktionsaufruf als Argument werden übergeben?</span><span class="sxs-lookup"><span data-stu-id="0ff92-111">Can you pass a function as an argument in a function call?</span></span>

- <span data-ttu-id="0ff92-112">Können Sie eine Funktion aus einem Funktionsaufruf zurückgeben?</span><span class="sxs-lookup"><span data-stu-id="0ff92-112">Can you return a function from a function call?</span></span>

<span data-ttu-id="0ff92-113">Die letzten beiden Measures definieren, so genannten *Operationen höherer Ordnung* oder *Funktionen höherer Ordnung*.</span><span class="sxs-lookup"><span data-stu-id="0ff92-113">The last two measures define what are known as *higher-order operations* or *higher-order functions*.</span></span> <span data-ttu-id="0ff92-114">Funktionen höherer Ordnung unterstützen Funktionen als Argumente und geben Funktionen als Werte von Funktionsaufrufen zurück.</span><span class="sxs-lookup"><span data-stu-id="0ff92-114">Higher-order functions accept functions as arguments and return functions as the value of function calls.</span></span> <span data-ttu-id="0ff92-115">Diese Operationen bilden die Grundlage für die Hauptstützen der funktionalen Programmierung, wie z. B. Zuordnungsfunktionen und Funktionszusammensetzung.</span><span class="sxs-lookup"><span data-stu-id="0ff92-115">These operations support such mainstays of functional programming as mapping functions and composition of functions.</span></span>


## <a name="give-the-value-a-name"></a><span data-ttu-id="0ff92-116">Zuweisen eines Namens zu einem Wert</span><span class="sxs-lookup"><span data-stu-id="0ff92-116">Give the Value a Name</span></span>

<span data-ttu-id="0ff92-117">Einem erstrangigen Funktionswert muss wie ganzen Zahlen, Zeichenfolgen und anderen integrierten Typen ein Name zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="0ff92-117">If a function is a first-class value, you must be able to name it, just as you can name integers, strings, and other built-in types.</span></span> <span data-ttu-id="0ff92-118">Bei der funktionalen Programmierung wird dies als Bindung eines Bezeichners an einen Wert ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="0ff92-118">This is referred to in functional programming literature as binding an identifier to a value.</span></span> <span data-ttu-id="0ff92-119">F# verwendet [ `let` Bindungen](../language-reference/functions/let-bindings.md) zum Binden von Namen an Werte: `let <identifier> = <value>`.</span><span class="sxs-lookup"><span data-stu-id="0ff92-119">F# uses [`let` bindings](../language-reference/functions/let-bindings.md) to bind names to values: `let <identifier> = <value>`.</span></span> <span data-ttu-id="0ff92-120">Der folgende Code enthält zwei Beispiele.</span><span class="sxs-lookup"><span data-stu-id="0ff92-120">The following code shows two examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet20.fs)]

<span data-ttu-id="0ff92-121">Das Zuweisen eines Namens zu einer Funktion ist ebenso einfach.</span><span class="sxs-lookup"><span data-stu-id="0ff92-121">You can name a function just as easily.</span></span> <span data-ttu-id="0ff92-122">Das folgende Beispiel definiert eine Funktion namens `squareIt` durch den Bezeichner binden `squareIt` auf die [Lambda-Ausdruck](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`.</span><span class="sxs-lookup"><span data-stu-id="0ff92-122">The following example defines a function named `squareIt` by binding the identifier `squareIt` to the [lambda expression](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`.</span></span> <span data-ttu-id="0ff92-123">Die Funktion `squareIt` verfügt über einen Parameter `n` und gibt das Quadrat dieses Parameters zurück.</span><span class="sxs-lookup"><span data-stu-id="0ff92-123">Function `squareIt` has one parameter, `n`, and it returns the square of that parameter.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

<span data-ttu-id="0ff92-124">Durch die folgende kürzere Syntax in F# erzielen Sie das gleiche Ergebnis mit weniger Aufwand.</span><span class="sxs-lookup"><span data-stu-id="0ff92-124">F# provides the following more concise syntax to achieve the same result with less typing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet22.fs)]

<span data-ttu-id="0ff92-125">In den folgenden Beispielen wird meist das erste Format (`let <function-name> = <lambda-expression>`) verwendet, um die Ähnlichkeiten zwischen der Deklaration von Funktionen und der Deklaration anderer Werttypen hervorzuheben.</span><span class="sxs-lookup"><span data-stu-id="0ff92-125">The examples that follow mostly use the first style, `let <function-name> = <lambda-expression>`, to emphasize the similarities between the declaration of functions and the declaration of other types of values.</span></span> <span data-ttu-id="0ff92-126">Sie können jedoch alle benannten Funktionen mit der kürzeren Syntax schreiben.</span><span class="sxs-lookup"><span data-stu-id="0ff92-126">However, all the named functions can also be written with the concise syntax.</span></span> <span data-ttu-id="0ff92-127">In einigen Beispielen werden beide Formate verwendet.</span><span class="sxs-lookup"><span data-stu-id="0ff92-127">Some of the examples are written in both ways.</span></span>


## <a name="store-the-value-in-a-data-structure"></a><span data-ttu-id="0ff92-128">Speichern des Werts in einer Datenstruktur</span><span class="sxs-lookup"><span data-stu-id="0ff92-128">Store the Value in a Data Structure</span></span>

<span data-ttu-id="0ff92-129">Sie können erstrangige Werte in einer Datenstruktur speichern.</span><span class="sxs-lookup"><span data-stu-id="0ff92-129">A first-class value can be stored in a data structure.</span></span> <span data-ttu-id="0ff92-130">Der folgende Code enthält Beispiele, in denen Werte in Listen und Tupeln gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="0ff92-130">The following code shows examples that store values in lists and in tuples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet23.fs)]

<span data-ttu-id="0ff92-131">Um zu überprüfen, ob ein in einem Tupel gespeicherter Funktionsname tatsächlich eine Funktion ergibt, werden im folgenden Beispiel mit dem `fst`-Operator und dem `snd`-Operator das erste und das zweite Element des Tupels `funAndArgTuple` extrahiert.</span><span class="sxs-lookup"><span data-stu-id="0ff92-131">To verify that a function name stored in a tuple does in fact evaluate to a function, the following example uses the `fst` and `snd` operators to extract the first and second elements from tuple `funAndArgTuple`.</span></span> <span data-ttu-id="0ff92-132">Das erste Element im Tupel ist `squareIt`, das zweite Element ist `num`.</span><span class="sxs-lookup"><span data-stu-id="0ff92-132">The first element in the tuple is `squareIt` and the second element is `num`.</span></span> <span data-ttu-id="0ff92-133">Der Bezeichner `num` wurde in einem vorangehenden Beispiel an die ganze Zahl 10 gebunden, ein gültiges Argument für die `squareIt`-Funktion.</span><span class="sxs-lookup"><span data-stu-id="0ff92-133">Identifier `num` is bound in a previous example to integer 10, a valid argument for the `squareIt` function.</span></span> <span data-ttu-id="0ff92-134">Der zweite Ausdruck wendet das erste Element im Tupel auf das zweite Element im Tupel an: `squareIt num`.</span><span class="sxs-lookup"><span data-stu-id="0ff92-134">The second expression applies the first element in the tuple to the second element in the tuple: `squareIt num`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet24.fs)]

<span data-ttu-id="0ff92-135">Ebenso wie der Bezeichner `num` und die ganze Zahl 10 sind auch der Bezeichner `squareIt` und der lambda-Ausdruck `fun n -> n * n` austauschbar.</span><span class="sxs-lookup"><span data-stu-id="0ff92-135">Similarly, just as identifier `num` and integer 10 can be used interchangeably, so can identifier `squareIt` and lambda expression `fun n -> n * n`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet25.fs)]
    
## <a name="pass-the-value-as-an-argument"></a><span data-ttu-id="0ff92-136">Übergeben des Werts als Argument</span><span class="sxs-lookup"><span data-stu-id="0ff92-136">Pass the Value as an Argument</span></span>

<span data-ttu-id="0ff92-137">Werte mit erstrangigem Status in einer Sprache können als Argumente an eine Funktion übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="0ff92-137">If a value has first-class status in a language, you can pass it as an argument to a function.</span></span> <span data-ttu-id="0ff92-138">So werden z. B. ganze Zahlen und Zeichenfolgen häufig als Argumente übergeben.</span><span class="sxs-lookup"><span data-stu-id="0ff92-138">For example, it is common to pass integers and strings as arguments.</span></span> <span data-ttu-id="0ff92-139">Im folgenden Code werden ganze Zahlen und Zeichenfolgen in F# als Argumente übergeben.</span><span class="sxs-lookup"><span data-stu-id="0ff92-139">The following code shows integers and strings passed as arguments in F#.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet26.fs)]

<span data-ttu-id="0ff92-140">Funktionen mit erstrangigem Status müssen sich ebenso als Argumente übergeben lassen.</span><span class="sxs-lookup"><span data-stu-id="0ff92-140">If functions have first-class status, you must be able to pass them as arguments in the same way.</span></span> <span data-ttu-id="0ff92-141">Hierbei handelt es sich um die erste Eigenschaft von Funktionen höherer Ordnung.</span><span class="sxs-lookup"><span data-stu-id="0ff92-141">Remember that this is the first characteristic of higher-order functions.</span></span>

<span data-ttu-id="0ff92-142">Die Funktion `applyIt` im folgenden Beispiel verfügt über die beiden Parameter `op` und `arg`.</span><span class="sxs-lookup"><span data-stu-id="0ff92-142">In the following example, function `applyIt` has two parameters, `op` and `arg`.</span></span> <span data-ttu-id="0ff92-143">Wenn Sie eine Funktion mit einem Parameter für `op` und ein entsprechendes Funktionsargument für `arg` senden, gibt die Funktion ein Ergebnis zurück, das sich aus der Anwendung von `op` auf `arg` ergibt.</span><span class="sxs-lookup"><span data-stu-id="0ff92-143">If you send in a function that has one parameter for `op` and an appropriate argument for the function to `arg`, the function returns the result of applying `op` to `arg`.</span></span> <span data-ttu-id="0ff92-144">Im folgenden Beispiel wird sowohl zum Senden des Funktionsarguments als auch zum Senden des ganzzahligen Arguments der jeweilige Name verwendet.</span><span class="sxs-lookup"><span data-stu-id="0ff92-144">In the following example, both the function argument and the integer argument are sent in the same way, by using their names.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet27.fs)]

<span data-ttu-id="0ff92-145">Die Fähigkeit, eine Funktion als Argument an eine andere Funktion zu übergeben, unterliegt in funktionalen Programmiersprachen allgemeinen Abstraktionen, wie z. B. Zuordnungs- und Filteroperationen.</span><span class="sxs-lookup"><span data-stu-id="0ff92-145">The ability to send a function as an argument to another function underlies common abstractions in functional programming languages, such as map or filter operations.</span></span> <span data-ttu-id="0ff92-146">Um eine Zuordnungsoperation handelt es sich z. B. bei einer Funktion höherer Ordnung, mit der die Berechnung von Funktionen erfasst wird, die eine Liste durchlaufen, eine bestimmte Aktion für jedes Element ausführen und dann eine Liste mit den Ergebnissen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0ff92-146">A map operation, for example, is a higher-order function that captures the computation shared by functions that step through a list, do something to each element, and then return a list of the results.</span></span> <span data-ttu-id="0ff92-147">Auf diese Weise können Sie z. B. die einzelnen Element in einer Liste mit ganzen Zahlen um einen bestimmten Wert erhöhen oder quadrieren oder die Elemente in einer Liste mit Zeichenfolgen in Großschreibung ändern.</span><span class="sxs-lookup"><span data-stu-id="0ff92-147">You might want to increment each element in a list of integers, or to square each element, or to change each element in a list of strings to uppercase.</span></span> <span data-ttu-id="0ff92-148">Der fehleranfällige Teil dieser Berechnung ist der rekursive Prozess, mit dem die Liste durchlaufen und eine Liste der zurückzugebenden Ergebnisse erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0ff92-148">The error-prone part of the computation is the recursive process that steps through the list and builds a list of the results to return.</span></span> <span data-ttu-id="0ff92-149">Dieser Teil wird von der Zuordnungsfunktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0ff92-149">That part is captured in the mapping function.</span></span> <span data-ttu-id="0ff92-150">Sie müssen für eine bestimmte Anwendung lediglich die Funktion schreiben, die auf jedes einzelne Element in der Liste angewendet werden soll (Addieren, Quadrieren, in Großschreibung ändern).</span><span class="sxs-lookup"><span data-stu-id="0ff92-150">All you have to write for a particular application is the function that you want to apply to each list element individually (adding, squaring, changing case).</span></span> <span data-ttu-id="0ff92-151">Diese Funktion wird als Argument an die Zuordnungsfunktion gesendet, wie im vorangehenden Beispiel, in dem `squareIt` an `applyIt` gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="0ff92-151">That function is sent as an argument to the mapping function, just as `squareIt` is sent to `applyIt` in the previous example.</span></span>

<span data-ttu-id="0ff92-152">F# stellt Zuordnungsmethoden für die meisten Auflistungstypen, einschließlich [listet](../language-reference/lists.md), [Arrays](../language-reference/arrays.md), und [Sequenzen](../language-reference/sequences.md).</span><span class="sxs-lookup"><span data-stu-id="0ff92-152">F# provides map methods for most collection types, including [lists](../language-reference/lists.md), [arrays](../language-reference/arrays.md), and [sequences](../language-reference/sequences.md).</span></span> <span data-ttu-id="0ff92-153">In den folgenden Beispielen werden Listen verwendet.</span><span class="sxs-lookup"><span data-stu-id="0ff92-153">The following examples use lists.</span></span> <span data-ttu-id="0ff92-154">Die Syntax lautet `List.map <the function> <the list>`.</span><span class="sxs-lookup"><span data-stu-id="0ff92-154">The syntax is `List.map <the function> <the list>`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet28.fs)]

<span data-ttu-id="0ff92-155">Weitere Informationen finden Sie unter [listet](../language-reference/lists.md).</span><span class="sxs-lookup"><span data-stu-id="0ff92-155">For more information, see [Lists](../language-reference/lists.md).</span></span>

## <a name="return-the-value-from-a-function-call"></a><span data-ttu-id="0ff92-156">Zurückgeben des Werts aus einem Funktionsaufruf</span><span class="sxs-lookup"><span data-stu-id="0ff92-156">Return the Value from a Function Call</span></span>

<span data-ttu-id="0ff92-157">Schließlich müssen sich Funktion mit erstrangigem Status in einer Sprache als Wert aus einem Funktionsaufruf zurückgeben lassen, ebenso wie andere Typen, z. B. ganze Zahlen oder Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="0ff92-157">Finally, if a function has first-class status in a language, you must be able to return it as the value of a function call, just as you return other types, such as integers and strings.</span></span>

<span data-ttu-id="0ff92-158">Mit den folgenden Funktionsaufrufen werden ganze Zahlen zurückgegeben und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0ff92-158">The following function calls return integers and display them.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet29.fs)]

<span data-ttu-id="0ff92-159">Mit dem folgenden Funktionsaufruf wird eine Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0ff92-159">The following function call returns a string.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet30.fs)]

<span data-ttu-id="0ff92-160">Mit dem folgenden inline deklarierten Funktionsaufruf wird ein boolescher Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0ff92-160">The following function call, declared inline, returns a Boolean value.</span></span> <span data-ttu-id="0ff92-161">Der angezeigte Wert ist `True`.</span><span class="sxs-lookup"><span data-stu-id="0ff92-161">The value displayed is `True`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet31.fs)]

<span data-ttu-id="0ff92-162">Die Fähigkeit, eine Funktion als Wert eines Funktionsaufrufs zurückzugeben, ist die zweite Eigenschaft von Funktionen höherer Ordnung.</span><span class="sxs-lookup"><span data-stu-id="0ff92-162">The ability to return a function as the value of a function call is the second characteristic of higher-order functions.</span></span> <span data-ttu-id="0ff92-163">Im folgenden Beispiel wird `checkFor` als Funktion definiert, die ein Argument erfordert (`item`) und eine neue Funktion als Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0ff92-163">In the following example, `checkFor` is defined to be a function that takes one argument, `item`, and returns a new function as its value.</span></span> <span data-ttu-id="0ff92-164">Die zurückgegebene Funktion erfordert eine Liste als Argument (`lst`) und führt in `item` eine Suche nach `lst` aus.</span><span class="sxs-lookup"><span data-stu-id="0ff92-164">The returned function takes a list as its argument, `lst`, and searches for `item` in `lst`.</span></span> <span data-ttu-id="0ff92-165">Wenn `item` gefunden wird, gibt die Funktion `true` zurück.</span><span class="sxs-lookup"><span data-stu-id="0ff92-165">If `item` is present, the function returns `true`.</span></span> <span data-ttu-id="0ff92-166">Wenn `item` nicht vorhanden ist, wird `false` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0ff92-166">If `item` is not present, the function returns `false`.</span></span> <span data-ttu-id="0ff92-167">Wie im vorherigen Abschnitt, der folgende Code verwendet eine Funktion bereitgestellte Liste [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), um die Liste zu suchen.</span><span class="sxs-lookup"><span data-stu-id="0ff92-167">As in the previous section, the following code uses a provided list function, [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), to search the list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="0ff92-168">Im folgenden Code wird mit `checkFor` eine neue Funktion erstellt, die ein Listenargument erfordert und in der Liste nach der Zahl 7 sucht.</span><span class="sxs-lookup"><span data-stu-id="0ff92-168">The following code uses `checkFor` to create a new function that takes one argument, a list, and searches for 7 in the list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet33.fs)]

<span data-ttu-id="0ff92-169">Im folgenden Beispiel wird der erstrangige Funktionsstatus in F# verwendet, um die Funktion `compose` zu deklarieren, die eine Zusammensetzung von zwei Funktionsargumenten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0ff92-169">The following example uses the first-class status of functions in F# to declare a function, `compose`, that returns a composition of two function arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet34.fs)]
    
>[!NOTE]
<span data-ttu-id="0ff92-170">Eine noch kürzere Version finden Sie im folgenden Abschnitt, "Funktionen mit Currying".</span><span class="sxs-lookup"><span data-stu-id="0ff92-170">For an even shorter version, see the following section, "Curried Functions."</span></span>


<span data-ttu-id="0ff92-171">Mit dem folgenden Code werden zwei Funktionen als Argumente an `compose` gesendet, die beide ein einzelnes Argument desselben Typs erfordern.</span><span class="sxs-lookup"><span data-stu-id="0ff92-171">The following code sends two functions as arguments to `compose`, both of which take a single argument of the same type.</span></span> <span data-ttu-id="0ff92-172">Der Rückgabewert ist eine neue Funktion, bei der es sich um eine Zusammensetzung der beiden Funktionsargumente handelt.</span><span class="sxs-lookup"><span data-stu-id="0ff92-172">The return value is a new function that is a composition of the two function arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet35.fs)]
    
>[!NOTE] 
<span data-ttu-id="0ff92-173">F# bietet zwei Operatoren zum Zusammensetzen von Funktionen: `<<` und `>>`.</span><span class="sxs-lookup"><span data-stu-id="0ff92-173">F# provides two operators, `<<` and `>>`, that compose functions.</span></span> <span data-ttu-id="0ff92-174">`let squareAndDouble2 = doubleIt << squareIt` entspricht im vorangehenden Beispiel `let squareAndDouble = compose doubleIt squareIt`.</span><span class="sxs-lookup"><span data-stu-id="0ff92-174">For example, `let squareAndDouble2 = doubleIt << squareIt` is equivalent to `let squareAndDouble = compose doubleIt squareIt` in the previous example.</span></span>

<span data-ttu-id="0ff92-175">Im folgenden Beispiel zur Rückgabe einer Funktion als Wert eines Funktionsaufrufs wird ein einfaches Ratespiel erstellt.</span><span class="sxs-lookup"><span data-stu-id="0ff92-175">The following example of returning a function as the value of a function call creates a simple guessing game.</span></span> <span data-ttu-id="0ff92-176">Rufen Sie zum Erstellen eines Spiels `makeGame` auf, und senden Sie den Wert, der erraten werden soll, an `target`.</span><span class="sxs-lookup"><span data-stu-id="0ff92-176">To create a game, call `makeGame` with the value that you want someone to guess sent in for `target`.</span></span> <span data-ttu-id="0ff92-177">Der Rückgabewert der Funktion `makeGame` ist eine Funktion, die ein Argument erfordert (den zu erratenden Wert) und zurückgibt, ob richtig geraten wurde.</span><span class="sxs-lookup"><span data-stu-id="0ff92-177">The return value from function `makeGame` is a function that takes one argument (the guess) and reports whether the guess is correct.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet36.fs)]

<span data-ttu-id="0ff92-178">Im folgenden Code wird `makeGame` aufgerufen und der Wert `7` an `target` gesendet.</span><span class="sxs-lookup"><span data-stu-id="0ff92-178">The following code calls `makeGame`, sending the value `7` for `target`.</span></span> <span data-ttu-id="0ff92-179">Der Bezeichner `playGame` wird an den zurückgegebenen Lambda-Ausdruck gebunden.</span><span class="sxs-lookup"><span data-stu-id="0ff92-179">Identifier `playGame` is bound to the returned lambda expression.</span></span> <span data-ttu-id="0ff92-180">Somit ist `playGame` eine Funktion, die den Wert für `guess` als einzelnes Argument erfordert.</span><span class="sxs-lookup"><span data-stu-id="0ff92-180">Therefore, `playGame` is a function that takes as its one argument a value for `guess`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet37.fs)]
    
## <a name="curried-functions"></a><span data-ttu-id="0ff92-181">Funktionen mit Currying</span><span class="sxs-lookup"><span data-stu-id="0ff92-181">Curried Functions</span></span>

<span data-ttu-id="0ff92-182">In vielen der Beispiele im vorherigen Abschnitt geschrieben werden können noch kürzer fassen durch Nutzen der impliziten *currying* in Funktionsdeklarationen in F# erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="0ff92-182">Many of the examples in the previous section can be written more concisely by taking advantage of the implicit *currying* in F# function declarations.</span></span> <span data-ttu-id="0ff92-183">Beim sogenannten Currying wird eine Funktion mit mehreren Parametern in eine Reihe eingebetteter Funktionen mit jeweils einem einzelnen Parameter transformiert.</span><span class="sxs-lookup"><span data-stu-id="0ff92-183">Currying is a process that transforms a function that has more than one parameter into a series of embedded functions, each of which has a single parameter.</span></span> <span data-ttu-id="0ff92-184">In F# wird Currying grundsätzlich auf Funktionen mit mehreren Parametern angewendet.</span><span class="sxs-lookup"><span data-stu-id="0ff92-184">In F#, functions that have more than one parameter are inherently curried.</span></span> <span data-ttu-id="0ff92-185">Beispiel: `compose` aus dem vorherigen Abschnitt kann in dem folgenden kurz gefassten Format mit drei Parametern geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="0ff92-185">For example, `compose` from the previous section can be written as shown in the following concise style, with three parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet38.fs)]

<span data-ttu-id="0ff92-186">Das Ergebnis ist eine Funktion mit einem Parameter, die eine Funktion mit einem Parameter zurückgibt, die wiederum eine Funktion mit einem Parameter zurückgibt (siehe `compose4curried`).</span><span class="sxs-lookup"><span data-stu-id="0ff92-186">However, the result is a function of one parameter that returns a function of one parameter that in turn returns another function of one parameter, as shown in `compose4curried`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet39.fs)]

<span data-ttu-id="0ff92-187">Für den Zugriff auf diese Funktion haben Sie verschiedene Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="0ff92-187">You can access this function in several ways.</span></span> <span data-ttu-id="0ff92-188">In jedem der folgenden Beispiele wird 18 zurückgegeben und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0ff92-188">Each of the following examples returns and displays 18.</span></span> <span data-ttu-id="0ff92-189">Sie können in jedem der Beispiele `compose4` durch `compose4curried` ersetzen.</span><span class="sxs-lookup"><span data-stu-id="0ff92-189">You can replace `compose4` with `compose4curried` in any of the examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet40.fs)]

<span data-ttu-id="0ff92-190">Um zu überprüfen, ob die Funktion wie gehabt funktioniert, verwenden Sie die ursprünglichen Testsituationen erneut.</span><span class="sxs-lookup"><span data-stu-id="0ff92-190">To verify that the function still works as it did before, try the original test cases again.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet41.fs)]
    
>[!NOTE] 
<span data-ttu-id="0ff92-191">Zur Einschränkung von Currying können Sie die Parameter in Tupeln einschließen.</span><span class="sxs-lookup"><span data-stu-id="0ff92-191">You can restrict currying by enclosing parameters in tuples.</span></span> <span data-ttu-id="0ff92-192">Weitere Informationen finden Sie unter "Muster der Parameter" in [Parameter und Argumente](../language-reference/parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="0ff92-192">For more information, see "Parameter Patterns" in [Parameters and Arguments](../language-reference/parameters-and-arguments.md).</span></span>

<span data-ttu-id="0ff92-193">Im folgenden Beispiel wird mit implizitem Currying eine kürzere Version von `makeGame` geschrieben.</span><span class="sxs-lookup"><span data-stu-id="0ff92-193">The following example uses implicit currying to write a shorter version of `makeGame`.</span></span> <span data-ttu-id="0ff92-194">Wie `makeGame` die `game`-Funktion erstellt und zurückgibt, ist in diesem Format weniger explizit, Sie können das Ergebnis aber mit den ursprünglichen Testsituationen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0ff92-194">The details of how `makeGame` constructs and returns the `game` function are less explicit in this format, but you can verify by using the original test cases that the result is the same.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet42.fs)]

<span data-ttu-id="0ff92-195">Weitere Informationen zu currying finden Sie unter "Partielle Anwendung von Argumenten" in [Funktionen](../language-reference/functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="0ff92-195">For more information about currying, see "Partial Application of Arguments" in [Functions](../language-reference/functions/index.md).</span></span>


## <a name="identifier-and-function-definition-are-interchangeable"></a><span data-ttu-id="0ff92-196">Bezeichner und Funktionsdefinition sind austauschbar</span><span class="sxs-lookup"><span data-stu-id="0ff92-196">Identifier and Function Definition Are Interchangeable</span></span>
<span data-ttu-id="0ff92-197">Der Variablenname `num` in den vorherigen Beispielen ergibt die ganze Zahl 10, wenn also `num` gültig ist, hat 10 ebenso Gültigkeit.</span><span class="sxs-lookup"><span data-stu-id="0ff92-197">The variable name `num` in the previous examples evaluates to the integer 10, and it is no surprise that where `num` is valid, 10 is also valid.</span></span> <span data-ttu-id="0ff92-198">Dasselbe gilt für Funktionsbezeichner und ihre Werte: Wenn der Name der Funktion verwendet werden kann, kann auch der daran gebundene lambda-Ausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0ff92-198">The same is true of function identifiers and their values: anywhere the name of the function can be used, the lambda expression to which it is bound can be used.</span></span>

<span data-ttu-id="0ff92-199">Im folgenden Beispiel wird eine `Boolean`-Funktion mit dem Namen `isNegative` definiert. Dann werden Funktionsname und Funktionsdefinition beliebig ausgetauscht.</span><span class="sxs-lookup"><span data-stu-id="0ff92-199">The following example defines a `Boolean` function called `isNegative`, and then uses the name of the function and the definition of the function interchangeably.</span></span> <span data-ttu-id="0ff92-200">In den nächsten drei Beispielen wird immer `False` zurückgegeben und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0ff92-200">The next three examples all return and display `False`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet43.fs)]

<span data-ttu-id="0ff92-201">Gehen Sie noch einen Schritt weiter und ersetzen Sie `applyIt` durch den Wert, an den `applyIt` gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="0ff92-201">To take it one step further, substitute the value that `applyIt` is bound to for `applyIt`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a><span data-ttu-id="0ff92-202">Funktionen in F# sind erstrangige Werte</span><span class="sxs-lookup"><span data-stu-id="0ff92-202">Functions Are First-Class Values in F#</span></span> #

<span data-ttu-id="0ff92-203">Die Beispiele in den vorherigen Abschnitten veranschaulichen, dass die Funktionen in F# die Kriterien für erstrangige Werte in F# erfüllen:</span><span class="sxs-lookup"><span data-stu-id="0ff92-203">The examples in the previous sections demonstrate that functions in F# satisfy the criteria for being first-class values in F#:</span></span>

- <span data-ttu-id="0ff92-204">Sie können einen Bezeichner an eine Funktionsdefinition binden.</span><span class="sxs-lookup"><span data-stu-id="0ff92-204">You can bind an identifier to a function definition.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

- <span data-ttu-id="0ff92-205">Sie können eine Funktion in einer Datenstruktur speichern.</span><span class="sxs-lookup"><span data-stu-id="0ff92-205">You can store a function in a data structure.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet45.fs)]

- <span data-ttu-id="0ff92-206">Sie können eine Funktion als Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="0ff92-206">You can pass a function as an argument.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet46.fs)]

- <span data-ttu-id="0ff92-207">Sie können eine Funktion als Wert eines Funktionsaufrufs zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0ff92-207">You can return a function as the value of a function call.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="0ff92-208">Weitere Informationen zu F# erläutert werden, finden Sie unter der [f#-Sprachreferenz](../language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="0ff92-208">For more information about F#, see the [F# Language Reference](../language-reference/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="0ff92-209">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0ff92-209">Example</span></span>

### <a name="description"></a><span data-ttu-id="0ff92-210">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ff92-210">Description</span></span>

<span data-ttu-id="0ff92-211">Der folgende Code enthält alle Beispiele aus diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="0ff92-211">The following code contains all the examples in this topic.</span></span>

### <a name="code"></a><span data-ttu-id="0ff92-212">Code</span><span class="sxs-lookup"><span data-stu-id="0ff92-212">Code</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet47.fs)]
    
## <a name="see-also"></a><span data-ttu-id="0ff92-213">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ff92-213">See Also</span></span>

[<span data-ttu-id="0ff92-214">Listen</span><span class="sxs-lookup"><span data-stu-id="0ff92-214">Lists</span></span>](../language-reference/lists.md)

[<span data-ttu-id="0ff92-215">Tupel</span><span class="sxs-lookup"><span data-stu-id="0ff92-215">Tuples</span></span>](../language-reference/tuples.md)

[<span data-ttu-id="0ff92-216">Funktionen</span><span class="sxs-lookup"><span data-stu-id="0ff92-216">Functions</span></span>](../language-reference/functions/index.md)

[<span data-ttu-id="0ff92-217">`let`Bindungen</span><span class="sxs-lookup"><span data-stu-id="0ff92-217">`let` Bindings</span></span>](../language-reference/functions/let-bindings.md)

[<span data-ttu-id="0ff92-218">Lambda-Ausdrücke: Das `fun` Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="0ff92-218">Lambda Expressions: The `fun` Keyword</span></span>](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
