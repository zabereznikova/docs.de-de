---
title: Flexible Typen (F#)
description: Erfahren Sie, wie f# flexible typanmerkung verwendet wird, der angibt, dass ein Parameter, eine Variable oder ein Wert ein Typs mit einem angegebenen Typ kompatibel ist.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: bee2364a6c30b1fbdc09aa0aac2249e3f0c295e8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="flexible-types"></a><span data-ttu-id="6d60d-103">Flexible Typen</span><span class="sxs-lookup"><span data-stu-id="6d60d-103">Flexible Types</span></span>

<span data-ttu-id="6d60d-104">Ein *flexible typanmerkung* gibt an, dass ein Parameter, eine Variable oder ein Wert ein Typs ist kompatibel mit einem angegebenen Typ, in denen die Kompatibilität anhand der Position in einer objektorientierten Hierarchie von Klassen oder Schnittstellen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="6d60d-104">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="6d60d-105">Flexible Typen sind sinnvoll, insbesondere, wenn die automatische Konvertierung in Typen, die in der Hierarchie höher nicht erfolgt, aber immer noch die Funktionalität zum Arbeiten mit beliebigen Typs in der Hierarchie und für alle Typen, die eine Schnittstelle implementiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="6d60d-105">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="6d60d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d60d-106">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="6d60d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6d60d-107">Remarks</span></span>

<span data-ttu-id="6d60d-108">In der vorherigen Syntax *Typ* ein Basistyp oder eine Schnittstelle darstellt.</span><span class="sxs-lookup"><span data-stu-id="6d60d-108">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="6d60d-109">Ein flexibler Typ entspricht einem generischen Typ, der eine Einschränkung aufweist, die die zulässigen Typen für Typen beschränkt, die mit dem Typ Basis oder Schnittstelle kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="6d60d-109">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="6d60d-110">D. h. entsprechen den folgenden zwei Codezeilen.</span><span class="sxs-lookup"><span data-stu-id="6d60d-110">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="6d60d-111">Flexible Typen sind in verschiedenen Arten von Situationen nützlich.</span><span class="sxs-lookup"><span data-stu-id="6d60d-111">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="6d60d-112">Bei einer Funktion höherer Ordnung (Funktion, die eine Funktion als Argument akzeptiert), ist es beispielsweise oft sinnvoll, verwenden die Funktion einen flexiblen Typ zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="6d60d-112">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="6d60d-113">Im folgenden Beispiel die Verwendung eines flexiblen Typs mit einem Sequenzargument in `iterate2` ermöglicht die Funktion höheren Ordnung arbeiten mit Funktionen, die Sequenzen, Arrays, Listen und aufzählbare andersartiges zu generieren.</span><span class="sxs-lookup"><span data-stu-id="6d60d-113">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="6d60d-114">Berücksichtigen Sie die folgenden beiden Funktionen, des welche eine Sequenz zurückgibt, von denen andere einen flexiblen Typ zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6d60d-114">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="6d60d-115">Betrachten Sie als weiteres Beispiel die [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) Library-Funktion:</span><span class="sxs-lookup"><span data-stu-id="6d60d-115">As another example, consider the [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="6d60d-116">Sie können eine der folgenden aufzählbaren Sequenzen dieser Funktion übergeben:</span><span class="sxs-lookup"><span data-stu-id="6d60d-116">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="6d60d-117">Eine Liste mit Listen</span><span class="sxs-lookup"><span data-stu-id="6d60d-117">A list of lists</span></span>
- <span data-ttu-id="6d60d-118">Eine Liste von arrays</span><span class="sxs-lookup"><span data-stu-id="6d60d-118">A list of arrays</span></span>
- <span data-ttu-id="6d60d-119">Ein Array von Listen</span><span class="sxs-lookup"><span data-stu-id="6d60d-119">An array of lists</span></span>
- <span data-ttu-id="6d60d-120">Ein Array von Sequenzen</span><span class="sxs-lookup"><span data-stu-id="6d60d-120">An array of sequences</span></span>
- <span data-ttu-id="6d60d-121">Eine beliebige andere Kombination von aufzählbare Sequenzen</span><span class="sxs-lookup"><span data-stu-id="6d60d-121">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="6d60d-122">Der folgende code verwendet `Seq.concat` der Szenarien veranschaulicht, die Sie über flexible Typen unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="6d60d-122">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="6d60d-123">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="6d60d-123">The output is as follows.</span></span>

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="6d60d-124">In F# erläutert sind wie in anderen objektorientierten Sprachen Kontexte vorhanden in denen abgeleiteten Typen oder Typen, die Schnittstellen implementieren automatisch in einen Basistyp oder Schnittstellentyp konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="6d60d-124">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="6d60d-125">Diese automatische Konvertierungen erfolgen in direkten Argumente, aber nicht, wenn der Typ in einer untergeordneten Position, im Rahmen eines komplexen Typs wie z. B. einen Rückgabetyp eines Funktionstyps oder als Typargument ist.</span><span class="sxs-lookup"><span data-stu-id="6d60d-125">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="6d60d-126">Daher ist die flexiblen Typ Notation primär nützlich, wenn der Typ, den sie zum Anwenden eines komplexen Typs gehört.</span><span class="sxs-lookup"><span data-stu-id="6d60d-126">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d60d-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d60d-127">See Also</span></span>

[<span data-ttu-id="6d60d-128">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="6d60d-128">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="6d60d-129">Generika</span><span class="sxs-lookup"><span data-stu-id="6d60d-129">Generics</span></span>](generics/index.md)
