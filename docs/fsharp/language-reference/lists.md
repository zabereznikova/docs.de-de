---
title: Listen
description: 'Erfahren Sie mehr über F #-Listen, eine geordnete, unveränderliche Reihe von Elementen desselben Typs.'
ms.date: 08/13/2020
ms.openlocfilehash: 16d7195039d25cf63630f5cc3be6563b1bf45c44
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559166"
---
# <a name="lists"></a><span data-ttu-id="ac451-103">Listen</span><span class="sxs-lookup"><span data-stu-id="ac451-103">Lists</span></span>

<span data-ttu-id="ac451-104">Eine Liste in F# stellt eine geordnete, unveränderliche Reihe von Elementen desselben Typs dar.</span><span class="sxs-lookup"><span data-stu-id="ac451-104">A list in F# is an ordered, immutable series of elements of the same type.</span></span> <span data-ttu-id="ac451-105">Verwenden Sie die Funktionen im [Listen Modul](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html), um grundlegende Vorgänge für Listen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ac451-105">To perform basic operations on lists, use the functions in the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span>

## <a name="creating-and-initializing-lists"></a><span data-ttu-id="ac451-106">Erstellen und Initialisieren von Listen</span><span class="sxs-lookup"><span data-stu-id="ac451-106">Creating and Initializing Lists</span></span>

<span data-ttu-id="ac451-107">Sie können eine Liste definieren, indem Sie die durch Semikolon getrennten und in eckige Klammern eingeschlossenen Elemente explizit auflisten, wie in folgender Codezeile veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ac451-107">You can define a list by explicitly listing out the elements, separated by semicolons and enclosed in square brackets, as shown in the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

<span data-ttu-id="ac451-108">Sie können Elemente auch durch Zeilenumbrüche trennen, wobei die Semikolons dann optional sind.</span><span class="sxs-lookup"><span data-stu-id="ac451-108">You can also put line breaks between elements, in which case the semicolons are optional.</span></span> <span data-ttu-id="ac451-109">Letztere Syntax kann den Code übersichtlicher gestalten, wenn die Ausdrücke zur Elementinitialisierung umfangreicher ausfallen oder Sie für jedes Element einen Kommentar einbeziehen möchten.</span><span class="sxs-lookup"><span data-stu-id="ac451-109">The latter syntax can result in more readable code when the element initialization expressions are longer, or when you want to include a comment for each element.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

<span data-ttu-id="ac451-110">Im Allgemeinen müssen alle Listenelemente denselben Typ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ac451-110">Normally, all list elements must be the same type.</span></span> <span data-ttu-id="ac451-111">Eine Ausnahme ist, dass eine Liste, in der für Elemente ein Basistyp angegeben wird, Elemente enthalten darf, die abgeleiteten Typen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ac451-111">An exception is that a list in which the elements are specified to be a base type can have elements that are derived types.</span></span> <span data-ttu-id="ac451-112">Somit ist Folgendes zulässig, da sowohl `Button` und `CheckBox` von `Control` abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ac451-112">Thus the following is acceptable, because both `Button` and `CheckBox` derive from `Control`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

<span data-ttu-id="ac451-113">Sie können Listenelemente auch durch Verwendung eines Bereichs definieren, der durch ganze Zahlen angegeben wird, die durch den Bereichsoperator (`..`) getrennt sind, wie im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ac451-113">You can also define list elements by using a range indicated by integers separated by the range operator (`..`), as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

<span data-ttu-id="ac451-114">Eine leere Liste wird durch ein Paar eckige Klammern angegeben, die nichts einschließen.</span><span class="sxs-lookup"><span data-stu-id="ac451-114">An empty list is specified by a pair of square brackets with nothing in between them.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

<span data-ttu-id="ac451-115">Sie können eine Liste auch mithilfe von Sequenzausdrücken erstellen.</span><span class="sxs-lookup"><span data-stu-id="ac451-115">You can also use a sequence expression to create a list.</span></span> <span data-ttu-id="ac451-116">Weitere Informationen finden Sie unter [Sequence Expressions](sequences.md#sequence-expressions) .</span><span class="sxs-lookup"><span data-stu-id="ac451-116">See [Sequence Expressions](sequences.md#sequence-expressions) for more information.</span></span> <span data-ttu-id="ac451-117">Der folgende Code erstellt z. B. eine Liste mit den Quadratzahlen der ganzen Zahlen von 1 bis 10.</span><span class="sxs-lookup"><span data-stu-id="ac451-117">For example, the following code creates a list of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a><span data-ttu-id="ac451-118">Operatoren für die Arbeit mit Listen</span><span class="sxs-lookup"><span data-stu-id="ac451-118">Operators for Working with Lists</span></span>

<span data-ttu-id="ac451-119">Sie können Elemente mithilfe des Operators `::` (Cons) zu einer Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ac451-119">You can attach elements to a list by using the `::` (cons) operator.</span></span> <span data-ttu-id="ac451-120">Wenn `list1` den Werten `[2; 3; 4]` entspricht, erstellt der folgende Code für `list2` die Werte `[100; 2; 3; 4]`.</span><span class="sxs-lookup"><span data-stu-id="ac451-120">If `list1` is `[2; 3; 4]`, the following code creates `list2` as `[100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

<span data-ttu-id="ac451-121">Sie können Listen, die kompatible Typen aufweisen, wie im folgenden Code mithilfe des Operators `@` verketten.</span><span class="sxs-lookup"><span data-stu-id="ac451-121">You can concatenate lists that have compatible types by using the `@` operator, as in the following code.</span></span> <span data-ttu-id="ac451-122">Wenn `list1` den Werten `[2; 3; 4]` und `list2` den Werten `[100; 2; 3; 4]` entspricht, erstellt dieser Code für `list3` die Werte `[2; 3; 4; 100; 2; 3; 4]`.</span><span class="sxs-lookup"><span data-stu-id="ac451-122">If `list1` is `[2; 3; 4]` and `list2` is `[100; 2; 3; 4]`, this code creates `list3` as `[2; 3; 4; 100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

<span data-ttu-id="ac451-123">Funktionen zum Ausführen von Vorgängen für Listen sind im [Listen Modul](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ac451-123">Functions for performing operations on lists are available in the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span>

<span data-ttu-id="ac451-124">Da Listen in F# unveränderlich sind, erstellen alle modifizierenden Operationen neue Listen, anstatt die vorhandenen Listen zu verändern.</span><span class="sxs-lookup"><span data-stu-id="ac451-124">Because lists in F# are immutable, any modifying operations generate new lists instead of modifying existing lists.</span></span>

<span data-ttu-id="ac451-125">Listen in F # werden als einzeln verknüpfte Listen implementiert. Dies bedeutet, dass Vorgänge, die nur auf den Anfang der Liste zugreifen, o (1) sind und der Element Zugriff o (*n*) ist.</span><span class="sxs-lookup"><span data-stu-id="ac451-125">Lists in F# are implemented as singly linked lists, which means that operations that access only the head of the list are O(1), and element access is O(*n*).</span></span>

## <a name="properties"></a><span data-ttu-id="ac451-126">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ac451-126">Properties</span></span>

<span data-ttu-id="ac451-127">Der Listentyp unterstützt die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ac451-127">The list type supports the following properties:</span></span>

|<span data-ttu-id="ac451-128">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ac451-128">Property</span></span>|<span data-ttu-id="ac451-129">type</span><span class="sxs-lookup"><span data-stu-id="ac451-129">Type</span></span>|<span data-ttu-id="ac451-130">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ac451-130">Description</span></span>|
|--------|----|-----------|
|[<span data-ttu-id="ac451-131">Stadt</span><span class="sxs-lookup"><span data-stu-id="ac451-131">Head</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head)|`'T`|<span data-ttu-id="ac451-132">Das erste Element.</span><span class="sxs-lookup"><span data-stu-id="ac451-132">The first element.</span></span>|
|[<span data-ttu-id="ac451-133">Leer</span><span class="sxs-lookup"><span data-stu-id="ac451-133">Empty</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Empty)|`'T list`|<span data-ttu-id="ac451-134">Eine statische Eigenschaft, die eine leere Liste des entsprechenden Typs zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ac451-134">A static property that returns an empty list of the appropriate type.</span></span>|
|[<span data-ttu-id="ac451-135">IsEmpty</span><span class="sxs-lookup"><span data-stu-id="ac451-135">IsEmpty</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#IsEmpty)|`bool`|<span data-ttu-id="ac451-136">Ergibt `true`, wenn die Liste keine Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="ac451-136">`true` if the list has no elements.</span></span>|
|[<span data-ttu-id="ac451-137">Element</span><span class="sxs-lookup"><span data-stu-id="ac451-137">Item</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Item)|`'T`|<span data-ttu-id="ac451-138">Das Element am angegebenen (nullbasierten) Index.</span><span class="sxs-lookup"><span data-stu-id="ac451-138">The element at the specified index (zero-based).</span></span>|
|[<span data-ttu-id="ac451-139">Länge</span><span class="sxs-lookup"><span data-stu-id="ac451-139">Length</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Length)|`int`|<span data-ttu-id="ac451-140">Die Anzahl der Elemente.</span><span class="sxs-lookup"><span data-stu-id="ac451-140">The number of elements.</span></span>|
|[<span data-ttu-id="ac451-141">Tail</span><span class="sxs-lookup"><span data-stu-id="ac451-141">Tail</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail)|`'T list`|<span data-ttu-id="ac451-142">Die Liste ohne das erste Element.</span><span class="sxs-lookup"><span data-stu-id="ac451-142">The list without the first element.</span></span>|

<span data-ttu-id="ac451-143">Nachfolgend sind einige Beispiele zur Verwendung dieser Eigenschaften aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ac451-143">Following are some examples of using these properties.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]

## <a name="using-lists"></a><span data-ttu-id="ac451-144">Verwenden von Listen</span><span class="sxs-lookup"><span data-stu-id="ac451-144">Using Lists</span></span>

<span data-ttu-id="ac451-145">Durch die Programmierung mit Listen können Sie mit wenig Code komplexe Operationen durchführen.</span><span class="sxs-lookup"><span data-stu-id="ac451-145">Programming with lists enables you to perform complex operations with a small amount of code.</span></span> <span data-ttu-id="ac451-146">In diesem Abschnitt werden die allgemeinen Operationen für Listen beschrieben, die für die funktionale Programmierung von Bedeutung sind.</span><span class="sxs-lookup"><span data-stu-id="ac451-146">This section describes common operations on lists that are important to functional programming.</span></span>

### <a name="recursion-with-lists"></a><span data-ttu-id="ac451-147">Rekursion mit Listen</span><span class="sxs-lookup"><span data-stu-id="ac451-147">Recursion with Lists</span></span>

<span data-ttu-id="ac451-148">Listen sind beispiellos für rekursive Programmierverfahren geeignet.</span><span class="sxs-lookup"><span data-stu-id="ac451-148">Lists are uniquely suited to recursive programming techniques.</span></span> <span data-ttu-id="ac451-149">Betrachten Sie eine Operation, die für jedes Element einer Liste ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="ac451-149">Consider an operation that must be performed on every element of a list.</span></span> <span data-ttu-id="ac451-150">Sie können dazu rekursiv vorgehen, indem Sie den Listenanfang verarbeiten und dann den Rest der Liste, bei dem es sich um eine kleinere Liste handelt, die aus der ursprünglichen Liste ohne das erste Element besteht, zurück an die nächste Rekursionsstufe übergeben.</span><span class="sxs-lookup"><span data-stu-id="ac451-150">You can do this recursively by operating on the head of the list and then passing the tail of the list, which is a smaller list that consists of the original list without the first element, back again to the next level of recursion.</span></span>

<span data-ttu-id="ac451-151">Sie verwenden zum Schreiben einer derartigen rekursiven Funktion den Cons-Operator (`::`) für den Mustervergleich, der es Ihnen ermöglicht, den Listenanfang vom Rest zu trennen.</span><span class="sxs-lookup"><span data-stu-id="ac451-151">To write such a recursive function, you use the cons operator (`::`) in pattern matching, which enables you to separate the head of a list from the tail.</span></span>

<span data-ttu-id="ac451-152">Das folgende Codebeispiel zeigt, wie eine rekursive Funktion mithilfe des Musterabgleichs implementiert wird, die Operationen mit einer Liste ausführt.</span><span class="sxs-lookup"><span data-stu-id="ac451-152">The following code example shows how to use pattern matching to implement a recursive function that performs operations on a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

<span data-ttu-id="ac451-153">Der vorherige Code ist für kleine Listen geeignet, aber bei größeren Listen könnten Stapelüberläufe auftreten.</span><span class="sxs-lookup"><span data-stu-id="ac451-153">The previous code works well for small lists, but for larger lists, it could overflow the stack.</span></span> <span data-ttu-id="ac451-154">Der folgende Code verwendet ein Akkumulatorargument, ein Standardverfahren für die Arbeit mit rekursiven Funktionen, um den vorherigen Code zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="ac451-154">The following code improves on this code by using an accumulator argument, a standard technique for working with recursive functions.</span></span> <span data-ttu-id="ac451-155">Durch die Verwendung des Akkumulatorarguments wird die Funktion zur endrekursiven Funktion, wodurch Stapelspeicher gespart wird.</span><span class="sxs-lookup"><span data-stu-id="ac451-155">The use of the accumulator argument makes the function tail recursive, which saves stack space.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

<span data-ttu-id="ac451-156">Die Funktion `RemoveAllMultiples` ist eine rekursive Funktion, die zwei Listen übernimmt.</span><span class="sxs-lookup"><span data-stu-id="ac451-156">The function `RemoveAllMultiples` is a recursive function that takes two lists.</span></span> <span data-ttu-id="ac451-157">Die erste Liste enthält die Zahlen, deren Vielfaches entfernt wird. Die zweite Liste ist die Liste, aus der die Zahlen entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="ac451-157">The first list contains the numbers whose multiples will be removed, and the second list is the list from which to remove the numbers.</span></span> <span data-ttu-id="ac451-158">Der Code im folgenden Beispiel verwendet diese rekursive Funktion, um alle Nichtprimzahlen aus der Liste zu entfernen, sodass als Ergebnis eine Liste der Primzahlen verbleibt.</span><span class="sxs-lookup"><span data-stu-id="ac451-158">The code in the following example uses this recursive function to eliminate all the non-prime numbers from a list, leaving a list of prime numbers as the result.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

<span data-ttu-id="ac451-159">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-159">The output is as follows:</span></span>

```console
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a><span data-ttu-id="ac451-160">Modulfunktionen</span><span class="sxs-lookup"><span data-stu-id="ac451-160">Module Functions</span></span>

<span data-ttu-id="ac451-161">Das [List-Modul](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html) stellt Funktionen bereit, die auf die Elemente einer Liste zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ac451-161">The [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html) provides functions that access the elements of a list.</span></span> <span data-ttu-id="ac451-162">Auf das Anfangselement kann am schnellsten und einfachsten zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="ac451-162">The head element is the fastest and easiest to access.</span></span> <span data-ttu-id="ac451-163">Verwenden Sie die Eigenschafts [Kopfzeile](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head) oder die Modul Funktion [List. Head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#head).</span><span class="sxs-lookup"><span data-stu-id="ac451-163">Use the property [Head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head) or the module function [List.head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#head).</span></span> <span data-ttu-id="ac451-164">Sie können mit der [Tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail) -Eigenschaft oder der [List. tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tail) -Funktion auf das Ende einer Liste zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ac451-164">You can access the tail of a list by using the [Tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail) property or the [List.tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tail) function.</span></span> <span data-ttu-id="ac451-165">Um nach einem Element anhand des Indexes zu suchen, verwenden Sie die [List. Nth](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#nth) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="ac451-165">To find an element by index, use the [List.nth](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#nth) function.</span></span> <span data-ttu-id="ac451-166">Mithilfe von `List.nth` wird die Liste durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="ac451-166">`List.nth` traverses the list.</span></span> <span data-ttu-id="ac451-167">Daher ist es O (*n*).</span><span class="sxs-lookup"><span data-stu-id="ac451-167">Therefore, it is O(*n*).</span></span> <span data-ttu-id="ac451-168">Wenn in Ihrem Code häufig `List.nth` verwendet wird, können Sie erwägen, ob Sie anstelle der Liste ein Array verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ac451-168">If your code uses `List.nth` frequently, you might want to consider using an array instead of a list.</span></span> <span data-ttu-id="ac451-169">Der Elementzugriff in Arrays entspricht "O(1)".</span><span class="sxs-lookup"><span data-stu-id="ac451-169">Element access in arrays is O(1).</span></span>

### <a name="boolean-operations-on-lists"></a><span data-ttu-id="ac451-170">Boolesche Operationen für Listen</span><span class="sxs-lookup"><span data-stu-id="ac451-170">Boolean Operations on Lists</span></span>

<span data-ttu-id="ac451-171">Die [List. IsEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#isEmpty) -Funktion bestimmt, ob eine Liste über Elemente verfügt.</span><span class="sxs-lookup"><span data-stu-id="ac451-171">The [List.isEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#isEmpty) function determines whether a list has any elements.</span></span>

<span data-ttu-id="ac451-172">Die [List.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists) ist-Funktion wendet einen booleschen Test auf Elemente einer Liste an und gibt zurück, `true` Wenn ein beliebiges Element den Test erfüllt.</span><span class="sxs-lookup"><span data-stu-id="ac451-172">The [List.exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists) function applies a Boolean test to elements of a list and returns `true` if any element satisfies the test.</span></span> <span data-ttu-id="ac451-173">[List. exists2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists2) ist ähnlich, funktioniert aber aufeinander folgende Paare von Elementen in zwei Listen.</span><span class="sxs-lookup"><span data-stu-id="ac451-173">[List.exists2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists2) is similar but operates on successive pairs of elements in two lists.</span></span>

<span data-ttu-id="ac451-174">Das folgende Codebeispiel veranschaulicht die Verwendung von `List.exists`.</span><span class="sxs-lookup"><span data-stu-id="ac451-174">The following code demonstrates the use of `List.exists`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet1.fs)]

<span data-ttu-id="ac451-175">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-175">The output is as follows:</span></span>

```console
For list [0; 1; 2; 3], contains zero is true
```

<span data-ttu-id="ac451-176">Das folgende Beispiel veranschaulicht die Verwendung von `List.exists2`.</span><span class="sxs-lookup"><span data-stu-id="ac451-176">The following example demonstrates the use of `List.exists2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet2.fs)]

<span data-ttu-id="ac451-177">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-177">The output is as follows:</span></span>

```console
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

<span data-ttu-id="ac451-178">Sie können [List. ForAll](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall) verwenden, wenn Sie testen möchten, ob alle Elemente einer Liste eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ac451-178">You can use [List.forall](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall) if you want to test whether all the elements of a list meet a condition.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet3.fs)]

<span data-ttu-id="ac451-179">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-179">The output is as follows:</span></span>

```console
true
false
```

<span data-ttu-id="ac451-180">Auf ähnliche Weise bestimmt [List. forall2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall2) , ob alle Elemente in den entsprechenden Positionen in zwei Listen einen booleschen Ausdruck erfüllen, der jedes Paar von Elementen einschließt.</span><span class="sxs-lookup"><span data-stu-id="ac451-180">Similarly, [List.forall2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall2) determines whether all elements in the corresponding positions in two lists satisfy a Boolean expression that involves each pair of elements.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet4.fs)]

<span data-ttu-id="ac451-181">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-181">The output is as follows:</span></span>

```console
true
false
```

### <a name="sort-operations-on-lists"></a><span data-ttu-id="ac451-182">Sortieroperationen für Listen</span><span class="sxs-lookup"><span data-stu-id="ac451-182">Sort Operations on Lists</span></span>

<span data-ttu-id="ac451-183">Die Listen. [Sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sort)-, [List. SortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortBy)-und [List. sortWith](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortWith) -Funktionen Sortieren Listen.</span><span class="sxs-lookup"><span data-stu-id="ac451-183">The [List.sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sort), [List.sortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortBy), and [List.sortWith](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortWith) functions sort lists.</span></span> <span data-ttu-id="ac451-184">Die Sortierfunktion bestimmt, welche dieser drei Funktionen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ac451-184">The sorting function determines which of these three functions to use.</span></span> <span data-ttu-id="ac451-185">`List.sort` verwendet einen generischen Standardvergleich.</span><span class="sxs-lookup"><span data-stu-id="ac451-185">`List.sort` uses default generic comparison.</span></span> <span data-ttu-id="ac451-186">Beim generischen Vergleich werden globale Operatoren, die auf der allgemeinen Vergleichsfunktion basieren, zum Vergleichen von Werten verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac451-186">Generic comparison uses global operators based on the generic compare function to compare values.</span></span> <span data-ttu-id="ac451-187">Der generische Vergleich funktioniert mit einer Vielzahl von Elementtypen sehr effizient, z. B. mit einfachen numerischen Typen, Tupeln, Datensätzen, diskriminierten Unions, Listen, Arrays und allen anderen Typen, die `System.IComparable` implementieren.</span><span class="sxs-lookup"><span data-stu-id="ac451-187">It works efficiently with a wide variety of element types, such as simple numeric types, tuples, records, discriminated unions, lists, arrays, and any type that implements `System.IComparable`.</span></span> <span data-ttu-id="ac451-188">Für Typen, die `System.IComparable` implementieren, wird für den generischen Vergleich die Funktion `System.IComparable.CompareTo()` verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac451-188">For types that implement `System.IComparable`, generic comparison uses the `System.IComparable.CompareTo()` function.</span></span> <span data-ttu-id="ac451-189">Der generische Vergleich funktioniert auch mit Zeichenfolgen, wobei jedoch eine kulturunabhängige Sortierreihenfolge verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ac451-189">Generic comparison also works with strings, but uses a culture-independent sorting order.</span></span> <span data-ttu-id="ac451-190">Der generische Vergleich sollte nicht für Typen verwendet werden, die nicht unterstützt werden, z. B. für Funktionstypen.</span><span class="sxs-lookup"><span data-stu-id="ac451-190">Generic comparison should not be used on unsupported types, such as function types.</span></span> <span data-ttu-id="ac451-191">Die optimale Leistung erzielt der generische Standardvergleich außerdem für kleine strukturierte Typen. Für größere strukturierte Typen, die häufig verglichen und sortiert werden müssen, sollten Sie die Implementierung von `System.IComparable` erwägen und eine effiziente Implementierung der Methode `System.IComparable.CompareTo()` bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ac451-191">Also, the performance of the default generic comparison is best for small structured types; for larger structured types that need to be compared and sorted frequently, consider implementing `System.IComparable` and providing an efficient implementation of the `System.IComparable.CompareTo()` method.</span></span>

<span data-ttu-id="ac451-192">`List.sortBy` übernimmt eine Funktion, die einen Wert zurückgibt, der als Sortierkriterium verwendet wird, während `List.sortWith` eine Vergleichsfunktion als Argument übernimmt.</span><span class="sxs-lookup"><span data-stu-id="ac451-192">`List.sortBy` takes a function that returns a value that is used as the sort criterion, and `List.sortWith` takes a comparison function as an argument.</span></span> <span data-ttu-id="ac451-193">Die letzten beiden Funktionen sind hilfreich, wenn Sie mit Typen arbeiten, die keinen Vergleich unterstützen bzw. wenn der Vergleich eine komplexere Vergleichssemantik als bei kulturfähige Zeichenfolgen erfordert.</span><span class="sxs-lookup"><span data-stu-id="ac451-193">These latter two functions are useful when you are working with types that do not support comparison, or when the comparison requires more complex comparison semantics, as in the case of culture-aware strings.</span></span>

<span data-ttu-id="ac451-194">Das folgende Beispiel veranschaulicht die Verwendung von `List.sort`.</span><span class="sxs-lookup"><span data-stu-id="ac451-194">The following example demonstrates the use of `List.sort`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet5.fs)]

<span data-ttu-id="ac451-195">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-195">The output is as follows:</span></span>

```console
[-2; 1; 4; 5; 8]
```

<span data-ttu-id="ac451-196">Das folgende Beispiel veranschaulicht die Verwendung von `List.sortBy`.</span><span class="sxs-lookup"><span data-stu-id="ac451-196">The following example demonstrates the use of `List.sortBy`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet6.fs)]

<span data-ttu-id="ac451-197">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-197">The output is as follows:</span></span>

```console
[1; -2; 4; 5; 8]
```

<span data-ttu-id="ac451-198">Das nächste Beispiel veranschaulicht die Verwendung von `List.sortWith`.</span><span class="sxs-lookup"><span data-stu-id="ac451-198">The next example demonstrates the use of `List.sortWith`.</span></span> <span data-ttu-id="ac451-199">In diesem Beispiel wird die benutzerdefinierte Vergleichsfunktion `compareWidgets` zunächst dazu verwendet, um ein Feld mit benutzerdefiniertem Typ zu vergleichen. Anschließend wird ein weiteres Feld verglichen, wenn die Werte des ersten Felds gleich sind.</span><span class="sxs-lookup"><span data-stu-id="ac451-199">In this example, the custom comparison function `compareWidgets` is used to first compare one field of a custom type, and then another when the values of the first field are equal.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet7.fs)]

<span data-ttu-id="ac451-200">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-200">The output is as follows:</span></span>

```console
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a><span data-ttu-id="ac451-201">Suchoperationen für Listen</span><span class="sxs-lookup"><span data-stu-id="ac451-201">Search Operations on Lists</span></span>

<span data-ttu-id="ac451-202">Für Listen werden zahlreiche Suchoperationen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac451-202">Numerous search operations are supported for lists.</span></span> <span data-ttu-id="ac451-203">Das einfachste [List. Find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#find)-Element ermöglicht es Ihnen, das erste Element zu finden, das mit einer bestimmten Bedingung übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="ac451-203">The simplest, [List.find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#find), enables you to find the first element that matches a given condition.</span></span>

<span data-ttu-id="ac451-204">Das folgende Codebeispiel veranschaulicht die Verwendung von `List.find` anhand der Suche nach der ersten Zahl in einer Liste, die durch fünf geteilt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ac451-204">The following code example demonstrates the use of `List.find` to find the first number that is divisible by 5 in a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet8.fs)]

<span data-ttu-id="ac451-205">The result is 5.</span><span class="sxs-lookup"><span data-stu-id="ac451-205">The result is 5.</span></span>

<span data-ttu-id="ac451-206">Wenn die Elemente zuerst transformiert werden müssen, nennen Sie [List. Pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#pick), das eine Funktion annimmt, die eine Option zurückgibt, und sucht nach dem ersten Optionswert, der ist `Some(x)` .</span><span class="sxs-lookup"><span data-stu-id="ac451-206">If the elements must be transformed first, call [List.pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#pick), which takes a function that returns an option, and looks for the first option value that is `Some(x)`.</span></span> <span data-ttu-id="ac451-207">Anstatt ein Element zurückzugeben, gibt `List.pick` das Ergebnis `x` zurück.</span><span class="sxs-lookup"><span data-stu-id="ac451-207">Instead of returning the element, `List.pick` returns the result `x`.</span></span> <span data-ttu-id="ac451-208">Wenn kein übereinstimmendes Element gefunden wird, löst `List.pick` die Ausnahme `System.Collections.Generic.KeyNotFoundException` aus.</span><span class="sxs-lookup"><span data-stu-id="ac451-208">If no matching element is found, `List.pick` throws `System.Collections.Generic.KeyNotFoundException`.</span></span> <span data-ttu-id="ac451-209">Im folgenden Code wird die Verwendung von `List.pick` veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ac451-209">The following code shows the use of `List.pick`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet9.fs)]

<span data-ttu-id="ac451-210">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-210">The output is as follows:</span></span>

```console
"b"
```

<span data-ttu-id="ac451-211">Eine andere Gruppe von Such Vorgängen, [List. tryFind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFind) und verwandte Funktionen, gibt einen Optionswert zurück.</span><span class="sxs-lookup"><span data-stu-id="ac451-211">Another group of search operations, [List.tryFind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFind) and related functions, return an option value.</span></span> <span data-ttu-id="ac451-212">Die `List.tryFind`-Funktion gibt das erste Element einer Liste zurück, das eine Bedingung erfüllt, sofern dieses Element vorhanden ist. Wenn dies nicht der Fall ist, wird der Optionswert `None` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ac451-212">The `List.tryFind` function returns the first element of a list that satisfies a condition if such an element exists, but the option value `None` if not.</span></span> <span data-ttu-id="ac451-213">Die Variations [Liste. tryFindIndex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFindIndex) gibt den Index des Elements zurück, sofern gefunden, und nicht das Element selbst.</span><span class="sxs-lookup"><span data-stu-id="ac451-213">The variation [List.tryFindIndex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFindIndex) returns the index of the element, if one is found, rather than the element itself.</span></span> <span data-ttu-id="ac451-214">Diese Funktionen werden im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ac451-214">These functions are illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet10.fs)]

<span data-ttu-id="ac451-215">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-215">The output is as follows:</span></span>

```console
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a><span data-ttu-id="ac451-216">Arithmetische Operationen für Listen</span><span class="sxs-lookup"><span data-stu-id="ac451-216">Arithmetic Operations on Lists</span></span>

<span data-ttu-id="ac451-217">Allgemeine arithmetische Operationen, wie z. b. Sum und Average, werden in das [Listen Modul](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)integriert.</span><span class="sxs-lookup"><span data-stu-id="ac451-217">Common arithmetic operations such as sum and average are built into the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span> <span data-ttu-id="ac451-218">Um mit [List. Sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sum)arbeiten zu können, muss der List-Elementtyp den `+` -Operator unterstützen und den Wert NULL aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ac451-218">To work with [List.sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sum), the list element type must support the `+` operator and have a zero value.</span></span> <span data-ttu-id="ac451-219">Alle integrierten arithmetischen Typen erfüllen diese Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="ac451-219">All built-in arithmetic types satisfy these conditions.</span></span> <span data-ttu-id="ac451-220">Um mit [List. Average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#average)arbeiten zu können, muss der Elementtyp die Division ohne Rest unterstützen, die ganzzahlige Typen ausschließt, aber Gleit Komma Typen zulässt.</span><span class="sxs-lookup"><span data-stu-id="ac451-220">To work with [List.average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#average), the element type must support division without a remainder, which excludes integral types but allows for floating point types.</span></span> <span data-ttu-id="ac451-221">Die Funktionen [List. sumBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sumBy) und [List. averageBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#averageBy) akzeptieren eine Funktion als Parameter, und die Ergebnisse dieser Funktion werden verwendet, um die Werte für die Summe oder den Durchschnitt zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="ac451-221">The [List.sumBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sumBy) and [List.averageBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#averageBy) functions take a function as a parameter, and this function's results are used to calculate the values for the sum or average.</span></span>

<span data-ttu-id="ac451-222">Das folgende Codebeispiel veranschaulicht die Verwendung von `List.sum`, `List.sumBy` und `List.average`.</span><span class="sxs-lookup"><span data-stu-id="ac451-222">The following code demonstrates the use of `List.sum`, `List.sumBy`, and `List.average`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet11.fs)]

<span data-ttu-id="ac451-223">Die Ausgabe lautet `1.000000`.</span><span class="sxs-lookup"><span data-stu-id="ac451-223">The output is `1.000000`.</span></span>

<span data-ttu-id="ac451-224">Im folgenden Code wird die Verwendung von `List.averageBy` veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ac451-224">The following code shows the use of `List.averageBy`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet12.fs)]

<span data-ttu-id="ac451-225">Die Ausgabe lautet `5.5`.</span><span class="sxs-lookup"><span data-stu-id="ac451-225">The output is `5.5`.</span></span>

### <a name="lists-and-tuples"></a><span data-ttu-id="ac451-226">Listen und Tupel</span><span class="sxs-lookup"><span data-stu-id="ac451-226">Lists and Tuples</span></span>

<span data-ttu-id="ac451-227">Listen, die Tupel enthalten, können mithilfe von Funktionen zum Zippen und Entzippen verändert werden.</span><span class="sxs-lookup"><span data-stu-id="ac451-227">Lists that contain tuples can be manipulated by zip and unzip functions.</span></span> <span data-ttu-id="ac451-228">Diese Funktionen vereinen zwei Listen mit einzelnen Werten zu einer Liste von Tupeln oder unterteilen eine Liste von Tupeln in zwei Listen mit einzelnen Werten.</span><span class="sxs-lookup"><span data-stu-id="ac451-228">These functions combine two lists of single values into one list of tuples or separate one list of tuples into two lists of single values.</span></span> <span data-ttu-id="ac451-229">Die einfachste [List.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip) Funktion übernimmt zwei Listen mit einzelnen Elementen und erzeugt eine einzelne Liste von tupelpaaren.</span><span class="sxs-lookup"><span data-stu-id="ac451-229">The simplest [List.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip) function takes two lists of single elements and produces a single list of tuple pairs.</span></span> <span data-ttu-id="ac451-230">Eine andere Version, [List.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip3), erfordert drei Listen mit einzelnen Elementen und erzeugt eine einzelne Liste von Tupeln, die drei Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="ac451-230">Another version, [List.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip3), takes three lists of single elements and produces a single list of tuples that have three elements.</span></span> <span data-ttu-id="ac451-231">Das folgende Codebeispiel veranschaulicht die Verwendung von `List.zip`.</span><span class="sxs-lookup"><span data-stu-id="ac451-231">The following code example demonstrates the use of `List.zip`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet13.fs)]

<span data-ttu-id="ac451-232">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-232">The output is as follows:</span></span>

```console
[(1, -1); (2, -2); (3; -3)]
```

<span data-ttu-id="ac451-233">Das folgende Codebeispiel veranschaulicht die Verwendung von `List.zip3`.</span><span class="sxs-lookup"><span data-stu-id="ac451-233">The following code example demonstrates the use of `List.zip3`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet14.fs)]

<span data-ttu-id="ac451-234">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-234">The output is as follows:</span></span>

```console
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

<span data-ttu-id="ac451-235">Die entsprechenden Entzippen Sie-Versionen [List. Entzippen Sie](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip) und [List. unzip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3)enthalten Listen von Tupeln und Rückgabe Listen in einem Tupel, wobei die erste Liste alle Elemente enthält, die zuerst in jedem Tupel enthalten waren, und die zweite Liste das zweite Element jedes Tupels usw. enthält.</span><span class="sxs-lookup"><span data-stu-id="ac451-235">The corresponding unzip versions, [List.unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip) and [List.unzip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3), take lists of tuples and return lists in a tuple, where the first list contains all the elements that were first in each tuple, and the second list contains the second element of each tuple, and so on.</span></span>

<span data-ttu-id="ac451-236">Im folgenden Codebeispiel wird die Verwendung von [List. unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21)veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ac451-236">The following code example demonstrates the use of [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet15.fs)]

<span data-ttu-id="ac451-237">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-237">The output is as follows:</span></span>

```console
([1; 3], [2; 4])
[1; 3] [2; 4]
```

<span data-ttu-id="ac451-238">Im folgenden Codebeispiel wird die Verwendung von [List. unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4)veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ac451-238">The following code example demonstrates the use of [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet16.fs)]

<span data-ttu-id="ac451-239">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-239">The output is as follows:</span></span>

```console
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a><span data-ttu-id="ac451-240">Arbeiten mit Listenelementen</span><span class="sxs-lookup"><span data-stu-id="ac451-240">Operating on List Elements</span></span>

<span data-ttu-id="ac451-241">F# unterstützt eine Vielzahl von Operationen mit Listenelementen.</span><span class="sxs-lookup"><span data-stu-id="ac451-241">F# supports a variety of operations on list elements.</span></span> <span data-ttu-id="ac451-242">Das einfachste ist [List. ITER](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter), das es Ihnen ermöglicht, eine Funktion für jedes Element einer Liste aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="ac451-242">The simplest is [List.iter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter), which enables you to call a function on every element of a list.</span></span> <span data-ttu-id="ac451-243">Zu den Variationen zählen [List. iter2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter2), mit denen Sie einen Vorgang für Elemente von zwei Listen ausführen können, z [. b. List. iteri](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri), `List.iter` mit dem Unterschied, dass der Index der einzelnen Elemente als Argument an die Funktion, die für jedes Element aufgerufen wird, und [List. iteri2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri2), die eine Kombination aus der Funktionalität von und ist, weitergeleitet wird `List.iter2` `List.iteri` .</span><span class="sxs-lookup"><span data-stu-id="ac451-243">Variations include [List.iter2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter2), which enables you to perform an operation on elements of two lists, [List.iteri](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri), which is like `List.iter` except that the index of each element is passed as an argument to the function that is called for each element, and [List.iteri2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri2), which is a combination of the functionality of `List.iter2` and `List.iteri`.</span></span> <span data-ttu-id="ac451-244">Diese Funktionen werden im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ac451-244">The following code example illustrates these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet17.fs)]

<span data-ttu-id="ac451-245">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-245">The output is as follows:</span></span>

```console
List.iter: element is 1
List.iter: element is 2
List.iter: element is 3
List.iteri: element 0 is 1
List.iteri: element 1 is 2
List.iteri: element 2 is 3
List.iter2: elements are 1 4
List.iter2: elements are 2 5
List.iter2: elements are 3 6
List.iteri2: element 0 of list1 is 1; element 0 of list2 is 4
List.iteri2: element 1 of list1 is 2; element 1 of list2 is 5
List.iteri2: element 2 of list1 is 3; element 2 of list2 is 6
```

<span data-ttu-id="ac451-246">Eine weitere häufig verwendete Funktion zum Transformieren von Listenelementen ist [List. map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map), mit der Sie eine Funktion auf jedes Element einer Liste anwenden und alle Ergebnisse in eine neue Liste einfügen können.</span><span class="sxs-lookup"><span data-stu-id="ac451-246">Another frequently used function that transforms list elements is [List.map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map), which enables you to apply a function to each element of a list and put all the results into a new list.</span></span> <span data-ttu-id="ac451-247">[List. map2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map2) und [List. map3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map3) sind Variationen, die mehrere Listen annehmen.</span><span class="sxs-lookup"><span data-stu-id="ac451-247">[List.map2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map2) and [List.map3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map3) are variations that take multiple lists.</span></span> <span data-ttu-id="ac451-248">Sie können auch [List. MAPI](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi) und [List. mapi2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi2)verwenden, wenn die Funktion zusätzlich zum-Element den Index der einzelnen Elemente an die Funktion übermittelt werden muss.</span><span class="sxs-lookup"><span data-stu-id="ac451-248">You can also use [List.mapi](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi) and [List.mapi2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi2), if, in addition to the element, the function needs to be passed the index of each element.</span></span> <span data-ttu-id="ac451-249">Der einzige Unterschied zwischen `List.mapi2` und `List.mapi` besteht darin, dass `List.mapi2` mit zwei Listen arbeitet.</span><span class="sxs-lookup"><span data-stu-id="ac451-249">The only difference between `List.mapi2` and `List.mapi` is that `List.mapi2` works with two lists.</span></span> <span data-ttu-id="ac451-250">Das folgende Beispiel veranschaulicht [List. map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map).</span><span class="sxs-lookup"><span data-stu-id="ac451-250">The following example illustrates [List.map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet18.fs)]

<span data-ttu-id="ac451-251">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-251">The output is as follows:</span></span>

```console
[2; 3; 4]
```

<span data-ttu-id="ac451-252">Im folgenden Beispiel wird die Verwendung von `List.map2` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ac451-252">The following example shows the use of `List.map2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet19.fs)]

<span data-ttu-id="ac451-253">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-253">The output is as follows:</span></span>

```console
[5; 7; 9]
```

<span data-ttu-id="ac451-254">Im folgenden Beispiel wird die Verwendung von `List.map3` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ac451-254">The following example shows the use of `List.map3`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet20.fs)]

<span data-ttu-id="ac451-255">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-255">The output is as follows:</span></span>

```console
[7; 10; 13]
```

<span data-ttu-id="ac451-256">Im folgenden Beispiel wird die Verwendung von `List.mapi` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ac451-256">The following example shows the use of `List.mapi`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet21.fs)]

<span data-ttu-id="ac451-257">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-257">The output is as follows:</span></span>

```console
[1; 3; 5]
```

<span data-ttu-id="ac451-258">Im folgenden Beispiel wird die Verwendung von `List.mapi2` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ac451-258">The following example shows the use of `List.mapi2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet22.fs)]

<span data-ttu-id="ac451-259">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-259">The output is as follows:</span></span>

```console
[0; 7; 18]
```

<span data-ttu-id="ac451-260">[List. Collect](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#collect) ist ähnlich `List.map` , mit der Ausnahme, dass jedes Element eine Liste erzeugt und alle diese Listen in einer endgültigen Liste verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="ac451-260">[List.collect](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#collect) is like `List.map`, except that each element produces a list and all these lists are concatenated into a final list.</span></span> <span data-ttu-id="ac451-261">Im folgenden Code generiert jedes Element der Liste drei Zahlen.</span><span class="sxs-lookup"><span data-stu-id="ac451-261">In the following code, each element of the list generates three numbers.</span></span> <span data-ttu-id="ac451-262">Diese werden alle in einer Liste erfasst.</span><span class="sxs-lookup"><span data-stu-id="ac451-262">These are all collected into one list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet23.fs)]

<span data-ttu-id="ac451-263">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-263">The output is as follows:</span></span>

```console
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

<span data-ttu-id="ac451-264">Sie können auch [List. Filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#filter)verwenden, das eine boolesche Bedingung annimmt und eine neue Liste erstellt, die nur aus Elementen besteht, die die angegebene Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ac451-264">You can also use [List.filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#filter), which takes a Boolean condition and produces a new list that consists only of elements that satisfy the given condition.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet24.fs)]

<span data-ttu-id="ac451-265">Die Ergebnisliste lautet `[2; 4; 6]`.</span><span class="sxs-lookup"><span data-stu-id="ac451-265">The resulting list is `[2; 4; 6]`.</span></span>

<span data-ttu-id="ac451-266">Eine Kombination aus Map und Filter, [List. Choose](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#choose) ermöglicht Ihnen, Elemente gleichzeitig zu transformieren und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ac451-266">A combination of map and filter, [List.choose](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#choose) enables you to transform and select elements at the same time.</span></span> <span data-ttu-id="ac451-267">`List.choose` wendet eine Funktion an, die eine Option zu den einzelnen Elementen einer Liste zurückgibt, und gibt eine neue Liste der Ergebnisse für Elemente zurück, wenn die Funktion den Optionswert `Some` liefert.</span><span class="sxs-lookup"><span data-stu-id="ac451-267">`List.choose` applies a function that returns an option to each element of a list, and returns a new list of the results for elements when the function returns the option value `Some`.</span></span>

<span data-ttu-id="ac451-268">Der folgende Code veranschaulicht die Verwendung von `List.choose`, um Wörter in Großbuchstaben aus einer Wörterliste auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ac451-268">The following code demonstrates the use of `List.choose` to select capitalized words out of a list of words.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet25.fs)]

<span data-ttu-id="ac451-269">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ac451-269">The output is as follows:</span></span>

```console
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a><span data-ttu-id="ac451-270">Arbeiten mit mehreren Listen</span><span class="sxs-lookup"><span data-stu-id="ac451-270">Operating on Multiple Lists</span></span>

<span data-ttu-id="ac451-271">Listen können verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="ac451-271">Lists can be joined together.</span></span> <span data-ttu-id="ac451-272">Verwenden Sie [List. Append](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#append), um zwei Listen zu einer zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="ac451-272">To join two lists into one, use [List.append](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#append).</span></span> <span data-ttu-id="ac451-273">Verwenden Sie [List. Concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#concat), um mehr als zwei Listen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="ac451-273">To join more than two lists, use [List.concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#concat).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet26.fs)]

### <a name="fold-and-scan-operations"></a><span data-ttu-id="ac451-274">Falt- und Suchoperationen</span><span class="sxs-lookup"><span data-stu-id="ac451-274">Fold and Scan Operations</span></span>

<span data-ttu-id="ac451-275">Einige Listenoperationen umfassen gegenseitige Abhängigkeiten zwischen allen Listenelementen.</span><span class="sxs-lookup"><span data-stu-id="ac451-275">Some list operations involve interdependencies between all of the list elements.</span></span> <span data-ttu-id="ac451-276">Die Fold-und Scanvorgänge lauten wie `List.iter` und `List.map` darin, dass Sie für jedes Element eine Funktion aufrufen. diese Vorgänge stellen jedoch einen zusätzlichen Parameter namens *Akkumulator* bereit, der Informationen über die Berechnung enthält.</span><span class="sxs-lookup"><span data-stu-id="ac451-276">The fold and scan operations are like `List.iter` and `List.map` in that you invoke a function on each element, but these operations provide an additional parameter called the *accumulator* that carries information through the computation.</span></span>

<span data-ttu-id="ac451-277">Verwenden Sie `List.fold`, um eine Berechnung für eine Liste durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="ac451-277">Use `List.fold` to perform a calculation on a list.</span></span>

<span data-ttu-id="ac451-278">Im folgenden Codebeispiel wird die Verwendung von [List. Fold](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold) zum Durchführen verschiedener Vorgänge veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ac451-278">The following code example demonstrates the use of [List.fold](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold) to perform various operations.</span></span>

<span data-ttu-id="ac451-279">Die Liste wird durchlaufen. Der Akkumulator `acc` ist ein Wert, der mit voranschreitender Berechnung weitergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ac451-279">The list is traversed; the accumulator `acc` is a value that is passed along as the calculation proceeds.</span></span> <span data-ttu-id="ac451-280">Das erste Argument übernimmt den Akkumulator sowie das Listenelement und gibt das Zwischenergebnis der Berechnung für dieses Listenelement zurück.</span><span class="sxs-lookup"><span data-stu-id="ac451-280">The first argument takes the accumulator and the list element, and returns the interim result of the calculation for that list element.</span></span> <span data-ttu-id="ac451-281">Das zweite Argument ist der Ausgangswert des Akkumulators.</span><span class="sxs-lookup"><span data-stu-id="ac451-281">The second argument is the initial value of the accumulator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet27.fs)]

<span data-ttu-id="ac451-282">Die Versionen dieser Funktionen, die eine Ziffer im Funktionsnamen enthalten, arbeiten mit mehreren Listen.</span><span class="sxs-lookup"><span data-stu-id="ac451-282">The versions of these functions that have a digit in the function name operate on more than one list.</span></span> <span data-ttu-id="ac451-283">[List. fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) führt z. b. Berechnungen für zwei Listen aus.</span><span class="sxs-lookup"><span data-stu-id="ac451-283">For example, [List.fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) performs computations on two lists.</span></span>

<span data-ttu-id="ac451-284">Das folgende Beispiel veranschaulicht die Verwendung von `List.fold2`.</span><span class="sxs-lookup"><span data-stu-id="ac451-284">The following example demonstrates the use of `List.fold2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet28.fs)]

<span data-ttu-id="ac451-285">`List.fold` und [List. Scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#scan) unterscheiden sich in, das `List.fold` den Endwert des zusätzlichen Parameters zurückgibt, jedoch `List.scan` die Liste der Zwischenwerte (zusammen mit dem endgültigen Wert) des zusätzlichen Parameters zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ac451-285">`List.fold` and [List.scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#scan) differ in that `List.fold` returns the final value of the extra parameter, but `List.scan` returns the list of the intermediate values (along with the final value) of the extra parameter.</span></span>

<span data-ttu-id="ac451-286">Jede dieser Funktionen enthält eine umgekehrte Variation, z. b [. List. foldBack](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack), die sich in der Reihenfolge unterscheidet, in der die Liste durchlaufen wird, und in der Reihenfolge der Argumente.</span><span class="sxs-lookup"><span data-stu-id="ac451-286">Each of these functions includes a reverse variation, for example, [List.foldBack](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack), which differs in the order in which the list is traversed and the order of the arguments.</span></span> <span data-ttu-id="ac451-287">Außerdem `List.fold` haben und `List.foldBack` Variationen, [List. fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) und [List. foldBack2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack2), die zwei Listen gleicher Länge annehmen.</span><span class="sxs-lookup"><span data-stu-id="ac451-287">Also, `List.fold` and `List.foldBack` have variations, [List.fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) and [List.foldBack2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack2), that take two lists of equal length.</span></span> <span data-ttu-id="ac451-288">Die Funktion, die für die einzelnen Elemente ausgeführt wird, kann entsprechende Elemente beider Listen verwenden, um Aktionen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="ac451-288">The function that executes on each element can use corresponding elements of both lists to perform some action.</span></span> <span data-ttu-id="ac451-289">Die Elementtypen beider Listen können wie im folgenden Beispiel unterschiedlich sein, in dem eine Liste Transaktionsbeträge für ein Bankkonto und die andere Liste den Typ der Transaktion enthält: Einzahlung oder Auszahlung.</span><span class="sxs-lookup"><span data-stu-id="ac451-289">The element types of the two lists can be different, as in the following example, in which one list contains transaction amounts for a bank account, and the other list contains the type of transaction: deposit or withdrawal.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet29.fs)]

<span data-ttu-id="ac451-290">Für eine Berechnung wie bei der Addition weisen `List.fold` und `List.foldBack` denselben Effekt auf, da das Ergebnis nicht von der Reihenfolge des Durchlaufs abhängt.</span><span class="sxs-lookup"><span data-stu-id="ac451-290">For a calculation like summation, `List.fold` and `List.foldBack` have the same effect because the result does not depend on the order of traversal.</span></span> <span data-ttu-id="ac451-291">Im folgenden Beispiel wird `List.foldBack` zum Hinzufügen der Elemente zu einer Liste verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac451-291">In the following example, `List.foldBack` is used to add the elements in a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet30.fs)]

<span data-ttu-id="ac451-292">Das folgende Beispiel kehrt zum Bankkontobeispiel zurück.</span><span class="sxs-lookup"><span data-stu-id="ac451-292">The following example returns to the bank account example.</span></span> <span data-ttu-id="ac451-293">Dieses Mal wird ein neuer Transaktionstyp hinzugefügt: Zinsberechnung.</span><span class="sxs-lookup"><span data-stu-id="ac451-293">This time a new transaction type is added: an interest calculation.</span></span> <span data-ttu-id="ac451-294">Der Endsaldo hängt jetzt von der Reihenfolge der Transaktionen ab.</span><span class="sxs-lookup"><span data-stu-id="ac451-294">The ending balance now depends on the order of transactions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet34.fs)]

<span data-ttu-id="ac451-295">Die Funktions [Liste ". Reduce](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#reduce) " ähnelt `List.fold` `List.scan` in gewisser Weise und, mit der Ausnahme, dass anstelle eines separaten Akkumulators `List.reduce` eine Funktion, die zwei Argumente des Elementtyps annimmt, anstelle eines solchen Arguments ist, und eines dieser Argumente als Akkumulator fungiert, was bedeutet, dass das Zwischenergebnis der Berechnung gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="ac451-295">The function [List.reduce](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#reduce) is somewhat like `List.fold` and `List.scan`, except that instead of passing around a separate accumulator, `List.reduce` takes a function that takes two arguments of the element type instead of just one, and one of those arguments acts as the accumulator, meaning that it stores the intermediate result of the computation.</span></span> <span data-ttu-id="ac451-296">`List.reduce` beginnt mit der Bearbeitung der ersten beiden Listenelemente und verwendet dann das Ergebnis der Operation zusammen mit dem nächsten Element.</span><span class="sxs-lookup"><span data-stu-id="ac451-296">`List.reduce` starts by operating on the first two list elements, and then uses the result of the operation along with the next element.</span></span> <span data-ttu-id="ac451-297">Da kein separater Akkumulator mit eigenem Typ vorhanden ist, kann `List.reduce` nur anstelle von `List.fold` verwendet werden, wenn Akkumulator und Elementtyp denselben Typ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ac451-297">Because there is not a separate accumulator that has its own type, `List.reduce` can be used in place of `List.fold` only when the accumulator and the element type have the same type.</span></span> <span data-ttu-id="ac451-298">Das folgende Codebeispiel veranschaulicht die Verwendung von `List.reduce`.</span><span class="sxs-lookup"><span data-stu-id="ac451-298">The following code demonstrates the use of `List.reduce`.</span></span> <span data-ttu-id="ac451-299">`List.reduce` löst eine Ausnahme aus, wenn die bereitgestellte Liste keine Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="ac451-299">`List.reduce` throws an exception if the list provided has no elements.</span></span>

<span data-ttu-id="ac451-300">Im folgenden Code erhält der Lambdaausdruck die Argumente „2“ und „4“ und gibt „6“ zurück. Der nächste Aufruf erhält die Argumente „6“ und „10“, daher ist das Ergebnis „16“.</span><span class="sxs-lookup"><span data-stu-id="ac451-300">In the following code, the first call to the lambda expression is given the arguments 2 and 4, and returns 6, and the next call is given the arguments 6 and 10, so the result is 16.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet33.fs)]

### <a name="converting-between-lists-and-other-collection-types"></a><span data-ttu-id="ac451-301">Konvertieren zwischen Listen und anderen Auflistungstypen</span><span class="sxs-lookup"><span data-stu-id="ac451-301">Converting Between Lists and Other Collection Types</span></span>

<span data-ttu-id="ac451-302">Das `List`-Modul stellt Funktionen zum Konvertieren von Sequenzen in Arrays und umgekehrt bereit.</span><span class="sxs-lookup"><span data-stu-id="ac451-302">The `List` module provides functions for converting to and from both sequences and arrays.</span></span> <span data-ttu-id="ac451-303">Um in eine oder aus einer Sequenz zu konvertieren, verwenden Sie [List. desetq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toSeq) oder [List. of-q](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofSeq).</span><span class="sxs-lookup"><span data-stu-id="ac451-303">To convert to or from a sequence, use [List.toSeq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toSeq) or [List.ofSeq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofSeq).</span></span> <span data-ttu-id="ac451-304">Wenn Sie in ein oder aus einem Array konvertieren möchten, verwenden Sie [List.-Array](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toArray) oder [List. ofArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofArray).</span><span class="sxs-lookup"><span data-stu-id="ac451-304">To convert to or from an array, use [List.toArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toArray) or [List.ofArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofArray).</span></span>

### <a name="additional-operations"></a><span data-ttu-id="ac451-305">Weitere Operationen</span><span class="sxs-lookup"><span data-stu-id="ac451-305">Additional Operations</span></span>

<span data-ttu-id="ac451-306">Weitere Informationen zu weiteren Vorgängen in Listen finden Sie im Bibliotheks Referenz Thema [List Module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span><span class="sxs-lookup"><span data-stu-id="ac451-306">For information about additional operations on lists, see the library reference topic [List Module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span>

## <a name="see-also"></a><span data-ttu-id="ac451-307">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ac451-307">See also</span></span>

- [<span data-ttu-id="ac451-308">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="ac451-308">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="ac451-309">F#-Typen</span><span class="sxs-lookup"><span data-stu-id="ac451-309">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="ac451-310">Sequenzen</span><span class="sxs-lookup"><span data-stu-id="ac451-310">Sequences</span></span>](sequences.md)
- [<span data-ttu-id="ac451-311">Arrays</span><span class="sxs-lookup"><span data-stu-id="ac451-311">Arrays</span></span>](arrays.md)
- [<span data-ttu-id="ac451-312">Optionen</span><span class="sxs-lookup"><span data-stu-id="ac451-312">Options</span></span>](options.md)
