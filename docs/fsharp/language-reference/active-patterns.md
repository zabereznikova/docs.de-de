---
title: Aktive Muster
description: Erfahren Sie, wie Sie mithilfe aktiver Muster benannte Partitionen definieren, die Eingabedaten in der Programmiersprache F- unterteilen.
ms.date: 05/16/2016
ms.openlocfilehash: 898ef201369683bfd49d53e863e86f919f5837fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187057"
---
# <a name="active-patterns"></a><span data-ttu-id="2e8fa-103">Aktive Muster</span><span class="sxs-lookup"><span data-stu-id="2e8fa-103">Active Patterns</span></span>

<span data-ttu-id="2e8fa-104">*Mit aktiven Mustern* können Sie benannte Partitionen definieren, die Eingabedaten unterteilen, sodass Sie diese Namen in einem Musterabgleichsausdruck genauso verwenden können wie für eine diskriminierte Union.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="2e8fa-105">Mit aktiven Mustern können Sie Daten benutzerdefiniert für jede Partition zerlegen.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="2e8fa-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e8fa-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="2e8fa-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2e8fa-107">Remarks</span></span>

<span data-ttu-id="2e8fa-108">In der vorherigen Syntax sind die Bezeichner Namen für Partitionen der Eingabedaten, die durch *Argumente*dargestellt werden, oder, mit anderen Worten, Namen für Teilmengen des Satzes aller Werte der Argumente.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="2e8fa-109">Es können bis zu sieben Partitionen in einer aktiven Musterdefinition vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="2e8fa-110">Der *Ausdruck* beschreibt die Form, in die die Daten zerlegen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="2e8fa-111">Sie können eine aktive Musterdefinition verwenden, um die Regeln zum Bestimmen zu definieren, zu welcher der benannten Partitionen die als Argumente angegebenen Werte gehören.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="2e8fa-112">Die Symbole (| und |) werden als *Bananenclips* bezeichnet, und die Funktion, die von diesem Typ der let-Bindung erstellt wird, wird als *aktive Erkennung*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="2e8fa-113">Betrachten Sie als Beispiel das folgende aktive Muster mit einem Argument.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="2e8fa-114">Sie können das aktive Muster in einem Musterabgleichsausdruck verwenden, wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="2e8fa-115">Die Ausgabe dieses Programms ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2e8fa-115">The output of this program is as follows:</span></span>

```console
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="2e8fa-116">Eine weitere Verwendung von aktiven Mustern besteht darin, Datentypen auf verschiedene Arten zu zerlegen, z. B. wenn dieselben zugrunde liegenden Daten verschiedene mögliche Darstellungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="2e8fa-117">Beispielsweise kann `Color` ein Objekt in eine RGB-Darstellung oder eine HSB-Darstellung zerlegt werden.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="2e8fa-118">Die Ausgabe des obigen Programms ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2e8fa-118">The output of the above program is as follows:</span></span>

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

<span data-ttu-id="2e8fa-119">In Kombination mit diesen beiden Methoden der Verwendung aktiver Muster können Sie Daten in die entsprechende Form partitionieren und zersetzen und die entsprechenden Berechnungen für die entsprechenden Daten in der für die Berechnung am besten geeigneten Daten durchführen.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="2e8fa-120">Die resultierenden Musterabgleichsausdrücke ermöglichen das Schreiben von Daten auf eine bequeme, sehr lesbare Weise, was potenziell komplexen Verzweigungs- und Datenanalysecode erheblich vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="2e8fa-121">Teilweise aktive Muster</span><span class="sxs-lookup"><span data-stu-id="2e8fa-121">Partial Active Patterns</span></span>

<span data-ttu-id="2e8fa-122">Manchmal müssen Sie nur einen Teil des Eingabebereichs partitionieren.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="2e8fa-123">In diesem Fall schreiben Sie einen Satz von Teilmustern, die jeweils mit einigen Eingaben übereinstimmen, aber nicht mit anderen Eingaben übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="2e8fa-124">Aktive Muster, die nicht immer einen Wert erzeugen, werden als *partielle aktive Muster*bezeichnet. Sie haben einen Rückgabewert, der ein Optionstyp ist.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="2e8fa-125">Um ein partielles aktives Muster\_zu definieren, verwenden Sie ein Platzhalterzeichen ( ) am Ende der Liste der Muster innerhalb der Bananenclips.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="2e8fa-126">Der folgende Code veranschaulicht die Verwendung eines partiellen aktiven Musters.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="2e8fa-127">Die Ausgabe des vorherigen Beispiels ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2e8fa-127">The output of the previous example is as follows:</span></span>

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="2e8fa-128">Bei der Verwendung partieller aktiver Muster können die einzelnen Entscheidungen manchmal getrennt oder sich gegenseitig ausschließen, aber sie müssen es nicht sein.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="2e8fa-129">Im folgenden Beispiel sind das Muster Quadrat und der Musterwürfel nicht getrennt, da einige Zahlen sowohl Quadrate als auch Würfel sind, z. B. 64.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="2e8fa-130">Das folgende Programm verwendet das UND-Muster, um die Quadrat- und Würfelmuster zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-130">The following program uses the AND pattern to combine the Square and Cube patterns.</span></span> <span data-ttu-id="2e8fa-131">Es druckt alle ganzen Zahlen bis zu 1000 aus, die sowohl Quadrate und Würfel sind, als auch solche, die nur Würfel sind.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-131">It prints out all integers up to 1000 that are both squares and cubes, as well as those which are only cubes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="2e8fa-132">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2e8fa-132">The output is as follows:</span></span>

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

## <a name="parameterized-active-patterns"></a><span data-ttu-id="2e8fa-133">Parametrisierte aktive Muster</span><span class="sxs-lookup"><span data-stu-id="2e8fa-133">Parameterized Active Patterns</span></span>

<span data-ttu-id="2e8fa-134">Aktive Muster verwenden immer mindestens ein Argument für das übereinstimmende Element, aber sie können auch zusätzliche Argumente annehmen, in diesem Fall gilt das *namensparametrierte aktive Muster.*</span><span class="sxs-lookup"><span data-stu-id="2e8fa-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="2e8fa-135">Zusätzliche Argumente ermöglichen es, ein allgemeines Muster zu spezialisieren.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="2e8fa-136">Aktive Muster, die reguläre Ausdrücke zum Analysieren von Zeichenfolgen verwenden, enthalten beispielsweise häufig den regulären Ausdruck `Integer` als zusätzlichen Parameter, wie im folgenden Code, der auch das im vorherigen Codebeispiel definierte partielle aktive Muster verwendet.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="2e8fa-137">In diesem Beispiel werden Zeichenfolgen, die reguläre Ausdrücke für verschiedene Datumsformate verwenden, angegeben, um das allgemeine aktive ParseRegex-Muster anzupassen.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="2e8fa-138">Das aktive Ganzzahlmuster wird verwendet, um die übereinstimmenden Zeichenfolgen in ganze Zahlen zu konvertieren, die an den DateTime-Konstruktor übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="2e8fa-139">Die Ausgabe des vorherigen Codes ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2e8fa-139">The output of the previous code is as follows:</span></span>

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="2e8fa-140">Aktive Muster sind nicht nur auf Musterabgleichsausdrücke beschränkt, sondern können sie auch für Let-Bindings verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e8fa-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="2e8fa-141">Die Ausgabe des vorherigen Codes ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2e8fa-141">The output of the previous code is as follows:</span></span>

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="2e8fa-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2e8fa-142">See also</span></span>

- [<span data-ttu-id="2e8fa-143">Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="2e8fa-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="2e8fa-144">Vergleichsausdrücke</span><span class="sxs-lookup"><span data-stu-id="2e8fa-144">Match Expressions</span></span>](match-expressions.md)
