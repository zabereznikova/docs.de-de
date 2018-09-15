---
title: Flexible Typen (F#)
description: Erfahren Sie, wie Sie mit F#-Anmerkung flexibler Typen, die angibt, dass ein Parameter, Variablen oder Wert ein Typs mit einem angegebenen Typ kompatibel ist.
ms.date: 05/16/2016
ms.openlocfilehash: b6c97c3cc19f15b2c8db74b2c55660a16b2858f7
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615559"
---
# <a name="flexible-types"></a><span data-ttu-id="2178c-103">Flexible Typen</span><span class="sxs-lookup"><span data-stu-id="2178c-103">Flexible Types</span></span>

<span data-ttu-id="2178c-104">Ein *Anmerkung flexibler Typen* gibt an, dass ein Parameter, Variablen oder Wert ein Typs, der mit einem angegebenen Typ kompatibel ist, in denen die Kompatibilität anhand der Position in einer objektorientierten Hierarchie von Klassen oder Schnittstellen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="2178c-104">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="2178c-105">Flexible Typen eignen sich besonders dann, wenn die automatische Konvertierung in Typen, die in der Hierarchie höher nicht erfolgt, aber weiterhin die Funktionen zum Arbeiten mit beliebigen Typs in der Hierarchie oder jeder Typ, der eine Schnittstelle implementiert aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="2178c-105">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="2178c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2178c-106">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="2178c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2178c-107">Remarks</span></span>

<span data-ttu-id="2178c-108">In der vorherigen Syntax *Typ* stellt einen Basistyp oder eine Schnittstelle dar.</span><span class="sxs-lookup"><span data-stu-id="2178c-108">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="2178c-109">Ein flexibler Typ entspricht ein generischer Typ mit einer Einschränkung, die die zulässigen Typen auf Typen beschränkt, die mit dem Typ Basis oder Schnittstelle kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="2178c-109">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="2178c-110">Das heißt, entsprechen die folgenden zwei Codezeilen.</span><span class="sxs-lookup"><span data-stu-id="2178c-110">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="2178c-111">Flexible Typen sind in verschiedenen Arten von Situationen nützlich.</span><span class="sxs-lookup"><span data-stu-id="2178c-111">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="2178c-112">Bei einer Funktion höherer Ordnung (eine Funktion, die eine Funktion als Argument akzeptiert), ist es beispielsweise häufig nützlich, um die Funktion einen flexiblen Typ zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="2178c-112">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="2178c-113">Im folgenden Beispiel ist die Verwendung eines flexiblen Typs mit einer Sequenzargument in `iterate2` ermöglicht die Funktion höheren Ordnung Arbeit mit Funktionen, die Sequenzen, Arrays, Listen und beliebige andere aufzählbare Typen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="2178c-113">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="2178c-114">Erwägen Sie die folgenden zwei Funktionen, die eine der gibt eine Sequenz, der andere einen flexiblen Typ zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2178c-114">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="2178c-115">Betrachten Sie als ein weiteres Beispiel: die [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) Library-Funktion:</span><span class="sxs-lookup"><span data-stu-id="2178c-115">As another example, consider the [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="2178c-116">Sie können eine der folgenden aufzählbaren Sequenzen dieser Funktion übergeben:</span><span class="sxs-lookup"><span data-stu-id="2178c-116">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="2178c-117">Eine Liste mit Listen</span><span class="sxs-lookup"><span data-stu-id="2178c-117">A list of lists</span></span>
- <span data-ttu-id="2178c-118">Eine Liste von arrays</span><span class="sxs-lookup"><span data-stu-id="2178c-118">A list of arrays</span></span>
- <span data-ttu-id="2178c-119">Ein Array von Listen</span><span class="sxs-lookup"><span data-stu-id="2178c-119">An array of lists</span></span>
- <span data-ttu-id="2178c-120">Ein Array von Sequenzen</span><span class="sxs-lookup"><span data-stu-id="2178c-120">An array of sequences</span></span>
- <span data-ttu-id="2178c-121">Eine beliebige andere Kombination der aufzählbaren Sequenzen</span><span class="sxs-lookup"><span data-stu-id="2178c-121">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="2178c-122">Der folgende code verwendet `Seq.concat` die Szenarien veranschaulicht werden, die Sie mithilfe flexible Typen unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="2178c-122">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="2178c-123">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="2178c-123">The output is as follows.</span></span>

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="2178c-124">In f# sind wie in anderen objektorientierten Sprachen Kontexte, die in denen abgeleiteten Typen oder Typen, die Schnittstellen implementieren automatisch in einem Basistyp oder der Schnittstellentyp konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="2178c-124">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="2178c-125">Diesen automatischen Konvertierungen erfolgen in direkten Argumente, jedoch nicht, wenn der Typ in eine untergeordnete Position, als Teil einer komplexeren Typ wie einen Rückgabetyp eines Funktionstyps oder als ein Argument vom Typ ist.</span><span class="sxs-lookup"><span data-stu-id="2178c-125">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="2178c-126">Daher ist die flexiblen Typ Notation vor allem nützlich, wenn der Typ, die, dem Sie sie anwenden können, sind, Teil eines komplexen Typs ist.</span><span class="sxs-lookup"><span data-stu-id="2178c-126">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="2178c-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2178c-127">See also</span></span>

- [<span data-ttu-id="2178c-128">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="2178c-128">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="2178c-129">Generika</span><span class="sxs-lookup"><span data-stu-id="2178c-129">Generics</span></span>](generics/index.md)
