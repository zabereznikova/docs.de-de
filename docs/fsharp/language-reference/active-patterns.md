---
title: Aktive Muster
description: Erfahren Sie, wie aktive Muster zu verwenden, um benannte Partitionen definieren, die Eingabedaten in der Programmiersprache F# zu unterteilen.
ms.date: 05/16/2016
ms.openlocfilehash: 0f1f57de425836738201d2d8f84ab67a0df142ee
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412083"
---
# <a name="active-patterns"></a><span data-ttu-id="b8685-103">Aktive Muster</span><span class="sxs-lookup"><span data-stu-id="b8685-103">Active Patterns</span></span>

<span data-ttu-id="b8685-104">*Aktive Muster* ermöglichen es Ihnen, definieren benannte Partitionen, die Eingabedaten unterteilen, sodass Sie diese Namen in einem musterabgleichsausdruck wie für eine Unterscheidungs-Union verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b8685-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="b8685-105">Mit aktiven Mustern können Sie Daten benutzerdefiniert für jede Partition zerlegen.</span><span class="sxs-lookup"><span data-stu-id="b8685-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="b8685-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8685-106">Syntax</span></span>

```fsharp
// Complete active pattern definition.
let (|identifer1|identifier2|...|) [ arguments ] = expression
// Partial active pattern definition.
let (|identifier|_|) [ arguments ] = expression
```

## <a name="remarks"></a><span data-ttu-id="b8685-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8685-107">Remarks</span></span>

<span data-ttu-id="b8685-108">In der vorherigen Syntax wird der Bezeichner sind die Namen für die Partitionen der Eingabedaten, die durch dargestellt werden *Argumente*, oder in anderen Worten: die Namen für Teilmengen der Menge aller Werte der Argumente.</span><span class="sxs-lookup"><span data-stu-id="b8685-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="b8685-109">Es können bis zu sieben Partitionen in der Definition eines aktiven Musters vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="b8685-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="b8685-110">Die *Ausdruck* beschreibt die Form, in dem die Daten zu zerlegen.</span><span class="sxs-lookup"><span data-stu-id="b8685-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="b8685-111">Definition eines aktiven Musters können Sie definieren die Regeln zur Bestimmung der benannte Partitionen die Werte, die als Argumente zu gehören.</span><span class="sxs-lookup"><span data-stu-id="b8685-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="b8685-112">Die (| und |) Symbole werden als bezeichnet *Bananenklammern* und die Funktion, die von diesem Typ der Let-Bindung erstellt haben, heißt ein *aktive Erkennung*.</span><span class="sxs-lookup"><span data-stu-id="b8685-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="b8685-113">Betrachten Sie beispielsweise das folgende aktive Muster mit einem Argument aus.</span><span class="sxs-lookup"><span data-stu-id="b8685-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="b8685-114">Sie können das aktive Muster in einem musterabgleichsausdruck wie im folgenden Beispiel gezeigt verwenden.</span><span class="sxs-lookup"><span data-stu-id="b8685-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="b8685-115">Die Ausgabe dieses Programms lautet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="b8685-115">The output of this program is as follows:</span></span>

```
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="b8685-116">Eine weitere Verwendungsmöglichkeit der aktive Muster ist Zerlegen von Datentypen auf verschiedene Weise, wie z. B. wenn die gleichen zugrunde liegenden Daten mögliche Darstellungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="b8685-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="b8685-117">Z. B. eine `Color` Objekt in eine RGB-Darstellung oder eine HSB-Darstellung zerlegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b8685-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="b8685-118">Die Ausgabe des obigen Programms lautet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="b8685-118">The output of the above program is as follows:</span></span>

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

<span data-ttu-id="b8685-119">In Kombination mit aktiven Mustern diese beiden Methoden ermöglichen Ihnen die Partition Daten in nur das entsprechende Formular zu zerlegen und führen Sie die entsprechenden Berechnungen für die entsprechenden Daten in der Form, die am einfachsten, für die Berechnung.</span><span class="sxs-lookup"><span data-stu-id="b8685-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="b8685-120">Die resultierende mustervergleichsausdrücke ermöglichen, Daten auf einfache Weise geschrieben werden, die sehr gut lesbar, erheblich vereinfachen potenziell komplexen Branchen und Datencode für die Analyse ist.</span><span class="sxs-lookup"><span data-stu-id="b8685-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="b8685-121">Partielle aktive Muster</span><span class="sxs-lookup"><span data-stu-id="b8685-121">Partial Active Patterns</span></span>

<span data-ttu-id="b8685-122">In einigen Fällen müssen Sie nur einen Teil der Eingabe Speicherplatz zu partitionieren.</span><span class="sxs-lookup"><span data-stu-id="b8685-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="b8685-123">In diesem Fall schreiben Sie eine Gruppe von partiellen Mustern, von denen einige Eingaben überein, aber nicht andere Eingaben entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b8685-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="b8685-124">Aktive Muster, die keine immer einen Wert produzieren heißen *partielle aktive Muster*; sie haben einen Rückgabewert, der ein Optionstyp ist.</span><span class="sxs-lookup"><span data-stu-id="b8685-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="b8685-125">Um eine partielle aktive Muster zu definieren, verwenden Sie ein Platzhalterzeichen (\_) am Ende der Liste der Muster innerhalb der Bananenklammern.</span><span class="sxs-lookup"><span data-stu-id="b8685-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="b8685-126">Der folgende Code veranschaulicht die Verwendung von partiellen aktiven Musters.</span><span class="sxs-lookup"><span data-stu-id="b8685-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="b8685-127">Die Ausgabe des vorherigen Beispiels lautet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="b8685-127">The output of the previous example is as follows:</span></span>

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="b8685-128">Wenn Sie partielle aktive Muster zu verwenden, können manchmal die einzelnen Optionen zusammenhanglosen oder sich gegenseitig ausschließende, jedoch keine sein müssen.</span><span class="sxs-lookup"><span data-stu-id="b8685-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="b8685-129">Im folgenden Beispiel sind das Muster Quadrat und den Cube-Muster nicht zusammenhanglos, da einige Zahlen sowohl Quadrate und Cubes, z. B. 64 sind.</span><span class="sxs-lookup"><span data-stu-id="b8685-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="b8685-130">Das folgende Programm verwendet die AND-Muster, das Quadrat und den Cube-Muster kombiniert.</span><span class="sxs-lookup"><span data-stu-id="b8685-130">The following program uses the AND pattern to combine the Square and Cube patterns.</span></span> <span data-ttu-id="b8685-131">Drucken alle ganzen Zahlen bis zu 1000, die sowohl Quadrate und Cubes, als auch diejenigen, bei die nur auf Cubes sind.</span><span class="sxs-lookup"><span data-stu-id="b8685-131">It print out all integers up to 1000 that are both squares and cubes, as well as those which are only cubes.</span></span> 

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="b8685-132">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b8685-132">The output is as follows:</span></span>

```
1 is a cube and a square
8 is a cube
27 is a cube
64 is a cube and a square
125 is a cube
216 is a cube
343 is a cube
512 is a cube
729 is a cube and a square
1000 is a cube
```

## <a name="parameterized-active-patterns"></a><span data-ttu-id="b8685-133">Parametrisierte aktive Muster</span><span class="sxs-lookup"><span data-stu-id="b8685-133">Parameterized Active Patterns</span></span>

<span data-ttu-id="b8685-134">Aktive Muster akzeptieren immer mindestens ein Argument für das Element, das abgeglichen wird, aber unter Umständen akzeptieren sie zusätzliche Argumente ebenfalls in diesem Fall, dass der Name *parametrisiertes aktives Muster* gilt.</span><span class="sxs-lookup"><span data-stu-id="b8685-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="b8685-135">Mit zusätzlichen Argumenten kann es sich um ein allgemeines Muster spezialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b8685-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="b8685-136">Aktive Muster, mit denen reguläre Ausdrücke zum Analysieren von Zeichenfolgen häufig kann beispielsweise den regulären Ausdruck als zusätzlichen Parameter, wie im folgenden Code, der auch das partielle aktive Muster verwendet `Integer` im vorherigen Codebeispiel definiert.</span><span class="sxs-lookup"><span data-stu-id="b8685-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="b8685-137">In diesem Beispiel werden Zeichenfolgen, die reguläre Ausdrücke für verschiedene Datumsformate verwenden angegeben, um das allgemeine ParseRegex-aktiv-Muster anzupassen.</span><span class="sxs-lookup"><span data-stu-id="b8685-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="b8685-138">Ganzzahl aktiven Musters wird verwendet, die übereinstimmenden Zeichenfolgen in ganze Zahlen zu konvertieren, die an den DateTime-Konstruktor übergeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="b8685-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="b8685-139">Die Ausgabe des vorherigen Codes lautet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="b8685-139">The output of the previous code is as follows:</span></span>

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="b8685-140">Aktive Muster sind nicht nur für Muster übereinstimmende Ausdrücke beschränkt, Sie können sie auch in Let-Bindungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b8685-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="b8685-141">Die Ausgabe des vorherigen Codes lautet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="b8685-141">The output of the previous code is as follows:</span></span>

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="b8685-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8685-142">See also</span></span>

- [<span data-ttu-id="b8685-143">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="b8685-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="b8685-144">Vergleichsausdrücke</span><span class="sxs-lookup"><span data-stu-id="b8685-144">Match Expressions</span></span>](match-expressions.md)
