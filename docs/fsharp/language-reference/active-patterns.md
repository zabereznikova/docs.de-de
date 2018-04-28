---
title: Aktive Muster (F#)
description: Erfahren Sie, wie mit aktiven Mustern verwenden, um benannte Partitionen definieren, die Eingabedaten in der Programmiersprache f# zu unterteilen.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 66e1e39c4822ec7262642d301ceb1deea17fcb8c
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="active-patterns"></a><span data-ttu-id="d53b4-103">Aktive Muster</span><span class="sxs-lookup"><span data-stu-id="d53b4-103">Active Patterns</span></span>

<span data-ttu-id="d53b4-104">*Aktive Muster* ermöglichen es Ihnen, definieren benannte Partitionen, die Eingabedaten zu unterteilen, damit Sie diese Namen in einem Mustervergleichsausdruck wie für eine Unterscheidungs-Union verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d53b4-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="d53b4-105">Mit aktiven Mustern können Sie Daten benutzerdefiniert für jede Partition zerlegen.</span><span class="sxs-lookup"><span data-stu-id="d53b4-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>


## <a name="syntax"></a><span data-ttu-id="d53b4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d53b4-106">Syntax</span></span>

```fsharp
// Complete active pattern definition.
let (|identifer1|identifier2|...|) [ arguments ] = expression
// Partial active pattern definition.
let (|identifier|_|) [ arguments ] = expression
```

## <a name="remarks"></a><span data-ttu-id="d53b4-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d53b4-107">Remarks</span></span>
<span data-ttu-id="d53b4-108">In der vorherigen Syntax sind die Bezeichner Namen für Partitionen der Eingabedaten, die von dargestellte *Argumente*, oder in anderen Worten: die Namen für Teilmengen der Menge aller Werte der Argumente.</span><span class="sxs-lookup"><span data-stu-id="d53b4-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="d53b4-109">Es kann bis zu sieben Partitionen in der Definition eines aktiven Musters vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="d53b4-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="d53b4-110">Die *Ausdruck* beschreibt die Form, in der die Daten zerlegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d53b4-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="d53b4-111">Definition eines aktiven Musters können Sie definieren die Regeln zum bestimmen, welche benannten Partitionen die Werte, die als Argumente zu gehören.</span><span class="sxs-lookup"><span data-stu-id="d53b4-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="d53b4-112">Der (| und |) Symbole werden als bezeichnet *Bananenklammern* und die Funktion erstellt, die von diesem Typ der Let-Bindung wird ein *aktive Erkennung*.</span><span class="sxs-lookup"><span data-stu-id="d53b4-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="d53b4-113">Beispielsweise sollten Sie die folgenden aktive Muster mit einem Argument.</span><span class="sxs-lookup"><span data-stu-id="d53b4-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="d53b4-114">Sie können das aktive Muster in einem Mustervergleichsausdruck wie im folgenden Beispiel gezeigt verwenden.</span><span class="sxs-lookup"><span data-stu-id="d53b4-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="d53b4-115">Die Ausgabe dieses Programms lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d53b4-115">The output of this program is as follows:</span></span>

```
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="d53b4-116">Eine weitere Verwendungsmöglichkeit der aktive Muster ist zum Zerlegen von Datentypen auf verschiedene Weise, wie z. B. wenn die gleichen zugrunde liegenden Daten verschiedene mögliche Darstellungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="d53b4-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="d53b4-117">Angenommen, ein `Color` Objekt konnte in eine RGB-Darstellung oder eine HSB-Darstellung zerlegt werden.</span><span class="sxs-lookup"><span data-stu-id="d53b4-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="d53b4-118">Die Ausgabe des oben genannten Programms lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d53b4-118">The output of the above program is as follows:</span></span>

```
Red
 Red: 255 Green: 0 Blue: 0
 Hue: 360.000000 Saturation: 1.000000 Brightness: 0.500000
Black
 Red: 0 Green: 0 Blue: 0
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.000000
White
 Red: 255 Green: 255 Blue: 255
 Hue: 0.000000 Saturation: 0.000000 Brightness: 1.000000
Gray
 Red: 128 Green: 128 Blue: 128
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.501961
BlanchedAlmond
 Red: 255 Green: 235 Blue: 205
 Hue: 36.000000 Saturation: 1.000000 Brightness: 0.901961
```

<span data-ttu-id="d53b4-119">In Kombination diese beiden Methoden mit aktiven Mustern ermöglichen Ihnen eine Partition Daten in der entsprechenden Format zerlegen und führen Sie die entsprechenden Berechnungen auf die entsprechenden Daten in der für die Berechnung am einfachsten Form.</span><span class="sxs-lookup"><span data-stu-id="d53b4-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="d53b4-120">Die resultierende Muster übereinstimmende Ausdrücke aktivieren Daten auf einfache Weise geschrieben werden, die schwer lesbar, erheblich vereinfachen potenziell komplexen Verzweigen und Datencode für die Analyse ist.</span><span class="sxs-lookup"><span data-stu-id="d53b4-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>


## <a name="partial-active-patterns"></a><span data-ttu-id="d53b4-121">Partielle aktive Muster</span><span class="sxs-lookup"><span data-stu-id="d53b4-121">Partial Active Patterns</span></span>
<span data-ttu-id="d53b4-122">In einigen Fällen müssen Sie nur einen Teil der Eingabe Speicherplatz zu partitionieren.</span><span class="sxs-lookup"><span data-stu-id="d53b4-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="d53b4-123">In diesem Fall schreiben Sie einen Satz von partiellen Mustern, von denen mit einigen Eingaben übereinstimmt, aber nicht andere Eingaben entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d53b4-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="d53b4-124">Aktive Muster, die immer keinen Wert zurückgibt, heißen *partielle aktive Muster*; sie haben einen Rückgabewert, der ein Optionstyp ist.</span><span class="sxs-lookup"><span data-stu-id="d53b4-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="d53b4-125">Um eine partielle aktive Muster zu definieren, verwenden Sie ein Platzhalterzeichen (_) am Ende der Liste von Mustern innerhalb der Bananenklammern.</span><span class="sxs-lookup"><span data-stu-id="d53b4-125">To define a partial active pattern, you use a wildcard character (_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="d53b4-126">Der folgende Code veranschaulicht die Verwendung eines partiellen aktiven Musters.</span><span class="sxs-lookup"><span data-stu-id="d53b4-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="d53b4-127">Die Ausgabe des vorherigen Beispiels lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d53b4-127">The output of the previous example is as follows:</span></span>

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="d53b4-128">Wenn Sie teilweise mit aktiven Mustern verwenden, können manchmal die einzelnen Optionen nicht zusammenhängenden oder sich gegenseitig ausschließende, jedoch müssen nicht sein.</span><span class="sxs-lookup"><span data-stu-id="d53b4-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="d53b4-129">Im folgenden Beispiel sind die Muster Square und Cube-Muster nicht zusammenhanglos, da einige Zahlen Quadrate und Cubes, z. B. 64 darstellen.</span><span class="sxs-lookup"><span data-stu-id="d53b4-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="d53b4-130">Das folgende Programm druckt alle ganzen Zahlen bis 1000000, die Quadrate und Cubes sind.</span><span class="sxs-lookup"><span data-stu-id="d53b4-130">The following program prints out all integers up to 1000000 that are both squares and cubes.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="d53b4-131">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d53b4-131">The output is as follows:</span></span>

```
1
64
729
4096
15625
46656
117649
262144
531441
1000000
```

## <a name="parameterized-active-patterns"></a><span data-ttu-id="d53b4-132">Parametrisierte aktive Muster</span><span class="sxs-lookup"><span data-stu-id="d53b4-132">Parameterized Active Patterns</span></span>
<span data-ttu-id="d53b4-133">Aktive Muster akzeptieren immer mindestens ein Argument für das Element, das abgeglichen wird, aber möglicherweise nehmen sie weitere Argumente als auch in diesem Fall, dass der Name *parametrisierte aktives Muster* gilt.</span><span class="sxs-lookup"><span data-stu-id="d53b4-133">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="d53b4-134">Mit zusätzlichen Argumenten kann es sich um ein allgemeines Muster spezialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="d53b4-134">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="d53b4-135">Aktive Muster, die Verwendung von regulären Ausdrücken zum Analysieren von Zeichenfolgen häufig umfassen z. B. den regulären Ausdruck als zusätzlichen Parameter, wie im folgenden Code, der auch das partielle aktive Muster verwendet `Integer` im vorherigen Codebeispiel definiert.</span><span class="sxs-lookup"><span data-stu-id="d53b4-135">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="d53b4-136">In diesem Beispiel sind Zeichenfolgen, die regulären Ausdrücke für verschiedene Datumsformate verwenden angegeben, die allgemeine aktive Muster ParseRegex anpassen.</span><span class="sxs-lookup"><span data-stu-id="d53b4-136">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="d53b4-137">Aktive Integer-Muster wird verwendet, die übereinstimmenden Zeichenfolgen in ganze Zahlen konvertiert, die an den DateTime-Konstruktor übergeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="d53b4-137">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="d53b4-138">Die Ausgabe des vorherigen Codes lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d53b4-138">The output of the previous code is as follows:</span></span>

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="d53b4-139">Aktive Muster sind nicht nur auf übereinstimmende Ausdrücke das Muster beschränkt, Sie können diese auch für Let-Bindungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d53b4-139">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="d53b4-140">Die Ausgabe des vorherigen Codes lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d53b4-140">The output of the previous code is as follows:</span></span>

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="d53b4-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d53b4-141">See Also</span></span>
[<span data-ttu-id="d53b4-142">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="d53b4-142">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="d53b4-143">Vergleichsausdrücke</span><span class="sxs-lookup"><span data-stu-id="d53b4-143">Match Expressions</span></span>](match-expressions.md)

