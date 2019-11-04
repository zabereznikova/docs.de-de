---
title: Aktive Muster
description: Erfahren Sie, wie Sie mit aktiven Mustern benannte Partitionen definieren, die Eingabedaten in der F# Programmiersprache unterteilen.
ms.date: 05/16/2016
ms.openlocfilehash: f5ed4a8600cba10d23d01628aba6ca07e543c586
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425092"
---
# <a name="active-patterns"></a><span data-ttu-id="a1d11-103">Aktive Muster</span><span class="sxs-lookup"><span data-stu-id="a1d11-103">Active Patterns</span></span>

<span data-ttu-id="a1d11-104">Mit *aktiven Mustern* können Sie benannte Partitionen definieren, die Eingabedaten unterteilen, sodass Sie diese Namen wie bei einer Unterscheidungs-Union in einem Muster Vergleichs Ausdruck verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a1d11-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="a1d11-105">Mit aktiven Mustern können Sie Daten benutzerdefiniert für jede Partition zerlegen.</span><span class="sxs-lookup"><span data-stu-id="a1d11-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="a1d11-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1d11-106">Syntax</span></span>

```fsharp
// Active pattern of one choice.
let (|identifier|) [arguments] valueToMatch= expression

// Active Pattern with multiple choices.
// Uses a FSharp.Core.Choice<_,...,_> based on the number of case names. In F#, the limitation n <= 7 applies.
let (|identifer1|identifier2|...|) valueToMatch = expression

// Partial active pattern definition.
// Uses a FSharp.Core.option<_> to represent if the type is satisfied at the call site.
let (|identifier|_|) [arguments ] valueToMatch = expression
```

## <a name="remarks"></a><span data-ttu-id="a1d11-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1d11-107">Remarks</span></span>

<span data-ttu-id="a1d11-108">In der vorherigen Syntax sind die Bezeichner Namen für Partitionen der Eingabedaten, die durch *Argumente*dargestellt werden, d. h. Namen für Teilmengen der Menge aller Werte der Argumente.</span><span class="sxs-lookup"><span data-stu-id="a1d11-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="a1d11-109">Eine aktive Muster Definition kann bis zu sieben Partitionen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a1d11-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="a1d11-110">Der *Ausdruck* beschreibt das Formular, in das die Daten zerlegt werden.</span><span class="sxs-lookup"><span data-stu-id="a1d11-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="a1d11-111">Sie können eine aktive Muster Definition verwenden, um die Regeln zum Bestimmen der benannten Partitionen zu definieren, zu denen die als Argumente angegebenen Werte gehören.</span><span class="sxs-lookup"><span data-stu-id="a1d11-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="a1d11-112">Die Symbole (| und |) werden als *Bananen Clips* bezeichnet, und die von dieser Art der Let-Bindung erstellte Funktion wird als *aktive Erkennung*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a1d11-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="a1d11-113">Sehen Sie sich als Beispiel das folgende aktive Muster mit einem Argument an.</span><span class="sxs-lookup"><span data-stu-id="a1d11-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="a1d11-114">Sie können das aktive Muster in einem Muster Vergleichs Ausdruck verwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a1d11-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="a1d11-115">Die Ausgabe dieses Programms lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a1d11-115">The output of this program is as follows:</span></span>

```console
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="a1d11-116">Eine andere Verwendung von aktiven Mustern besteht darin, Datentypen auf verschiedene Weise zu zerlegen, z. b. wenn die gleichen zugrunde liegenden Daten verschiedene mögliche Darstellungen haben.</span><span class="sxs-lookup"><span data-stu-id="a1d11-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="a1d11-117">Beispielsweise kann ein `Color` Objekt in eine RGB-Darstellung oder eine HSB-Darstellung zerlegt werden.</span><span class="sxs-lookup"><span data-stu-id="a1d11-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="a1d11-118">Die Ausgabe des obigen Programms lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a1d11-118">The output of the above program is as follows:</span></span>

```console
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

<span data-ttu-id="a1d11-119">In Kombination können Sie mit diesen beiden Methoden zum Verwenden von aktiven Mustern Daten in das entsprechende Formular partitionieren und Zerlegen sowie die entsprechenden Berechnungen für die entsprechenden Daten in der für die Berechnung am besten geeigneten Form ausführen.</span><span class="sxs-lookup"><span data-stu-id="a1d11-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="a1d11-120">Die sich ergebenden Muster Vergleichsausdrücke ermöglichen es, Daten auf bequeme Weise zu schreiben, die sehr lesbar ist, und potenziell komplexe Verzweigungen und Datenanalyse Code erheblich zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="a1d11-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="a1d11-121">Teilweise aktive Muster</span><span class="sxs-lookup"><span data-stu-id="a1d11-121">Partial Active Patterns</span></span>

<span data-ttu-id="a1d11-122">Manchmal müssen Sie nur einen Teil des Eingabe Raums partitionieren.</span><span class="sxs-lookup"><span data-stu-id="a1d11-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="a1d11-123">In diesem Fall schreiben Sie eine Reihe von partiellen Mustern, von denen jedes mit einigen Eingaben identisch ist, aber nicht mit anderen Eingaben verglichen werden kann.</span><span class="sxs-lookup"><span data-stu-id="a1d11-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="a1d11-124">Aktive Muster, die nicht immer einen Wert ergeben, werden als *teilweise aktive Muster*bezeichnet. Sie verfügen über einen Rückgabewert, der ein Optionstyp ist.</span><span class="sxs-lookup"><span data-stu-id="a1d11-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="a1d11-125">Wenn Sie ein teilweise aktives Muster definieren möchten, verwenden Sie ein Platzhalter Zeichen (\_) am Ende der Liste der Muster innerhalb der Bananen Clips.</span><span class="sxs-lookup"><span data-stu-id="a1d11-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="a1d11-126">Der folgende Code veranschaulicht die Verwendung eines teilweise aktiven Musters.</span><span class="sxs-lookup"><span data-stu-id="a1d11-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="a1d11-127">Die Ausgabe des vorherigen Beispiels lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a1d11-127">The output of the previous example is as follows:</span></span>

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="a1d11-128">Wenn Sie teilweise aktive Muster verwenden, kann es vorkommen, dass die einzelnen Optionen zusammen hanglos oder sich gegenseitig ausschließen, aber nicht sein müssen.</span><span class="sxs-lookup"><span data-stu-id="a1d11-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="a1d11-129">Im folgenden Beispiel sind das Muster Quadrat und der Pattern-Cube nicht zusammen hanglos, da einige Zahlen sowohl Quadrate als auch Cubes sind, z. b. 64.</span><span class="sxs-lookup"><span data-stu-id="a1d11-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="a1d11-130">Im folgenden Programm werden das-Muster und das-Muster verwendet, um die Quadrat-und die Cube-Muster</span><span class="sxs-lookup"><span data-stu-id="a1d11-130">The following program uses the AND pattern to combine the Square and Cube patterns.</span></span> <span data-ttu-id="a1d11-131">Dabei werden alle ganzen Zahlen bis zu 1000 gedruckt, bei denen es sich um Quadrate und Cubes handelt, sowie um diejenigen, bei denen es sich nur um Cubes handelt.</span><span class="sxs-lookup"><span data-stu-id="a1d11-131">It print out all integers up to 1000 that are both squares and cubes, as well as those which are only cubes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="a1d11-132">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a1d11-132">The output is as follows:</span></span>

```console
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

## <a name="parameterized-active-patterns"></a><span data-ttu-id="a1d11-133">Parametrisierte aktive Muster</span><span class="sxs-lookup"><span data-stu-id="a1d11-133">Parameterized Active Patterns</span></span>

<span data-ttu-id="a1d11-134">Aktive Muster akzeptieren immer mindestens ein Argument für das Element, das abgeglichen wird, Sie können jedoch auch zusätzliche Argumente annehmen. in diesem Fall gilt das *parametrisierte aktive Muster* für den Namen.</span><span class="sxs-lookup"><span data-stu-id="a1d11-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="a1d11-135">Mit zusätzlichen Argumenten kann ein allgemeines Muster spezialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="a1d11-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="a1d11-136">Beispielsweise enthalten aktive Muster, die reguläre Ausdrücke zum Analysieren von Zeichen folgen verwenden, häufig den regulären Ausdruck als zusätzlichen Parameter, wie im folgenden Code gezeigt, der auch das teilweise aktive Muster verwendet `Integer` das im vorherigen Codebeispiel definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a1d11-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="a1d11-137">In diesem Beispiel werden Zeichen folgen, die reguläre Ausdrücke für verschiedene Datumsformate verwenden, angegeben, um das allgemeine allgemeine parametopx-Muster anzupassen.</span><span class="sxs-lookup"><span data-stu-id="a1d11-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="a1d11-138">Das aktive integermuster wird verwendet, um die übereinstimmenden Zeichen folgen in ganze Zahlen zu konvertieren, die an den DateTime-Konstruktor übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="a1d11-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="a1d11-139">Die Ausgabe des vorherigen Codes lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a1d11-139">The output of the previous code is as follows:</span></span>

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="a1d11-140">Aktive Muster sind nicht auf Muster Vergleichsausdrücke beschränkt, Sie können Sie auch bei let-Bindungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a1d11-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="a1d11-141">Die Ausgabe des vorherigen Codes lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a1d11-141">The output of the previous code is as follows:</span></span>

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="a1d11-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1d11-142">See also</span></span>

- [<span data-ttu-id="a1d11-143">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="a1d11-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="a1d11-144">Vergleichsausdrücke</span><span class="sxs-lookup"><span data-stu-id="a1d11-144">Match Expressions</span></span>](match-expressions.md)
