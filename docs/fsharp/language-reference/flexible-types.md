---
title: Flexible Typen (F#)
description: Erfahren Sie, wie f# flexible typanmerkung verwendet wird, der angibt, dass ein Parameter, eine Variable oder ein Wert ein Typs mit einem angegebenen Typ kompatibel ist.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c8b510f2-3405-4cc9-b55b-e47b35e2b15b
ms.openlocfilehash: 7c5e4eb97791b9c6c56fe2847755866e8240e038
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2017
---
# <a name="flexible-types"></a><span data-ttu-id="01526-104">Flexible Typen</span><span class="sxs-lookup"><span data-stu-id="01526-104">Flexible Types</span></span>

<span data-ttu-id="01526-105">Ein *flexible typanmerkung* gibt an, dass ein Parameter, eine Variable oder ein Wert ein Typs ist kompatibel mit einem angegebenen Typ, in denen die Kompatibilität anhand der Position in einer objektorientierten Hierarchie von Klassen oder Schnittstellen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="01526-105">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="01526-106">Flexible Typen sind sinnvoll, insbesondere, wenn die automatische Konvertierung in Typen, die in der Hierarchie höher nicht erfolgt, aber immer noch die Funktionalität zum Arbeiten mit beliebigen Typs in der Hierarchie und für alle Typen, die eine Schnittstelle implementiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="01526-106">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="01526-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="01526-107">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="01526-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="01526-108">Remarks</span></span>

<span data-ttu-id="01526-109">In der vorherigen Syntax *Typ* ein Basistyp oder eine Schnittstelle darstellt.</span><span class="sxs-lookup"><span data-stu-id="01526-109">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="01526-110">Ein flexibler Typ entspricht einem generischen Typ, der eine Einschränkung aufweist, die die zulässigen Typen für Typen beschränkt, die mit dem Typ Basis oder Schnittstelle kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="01526-110">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="01526-111">D. h. entsprechen den folgenden zwei Codezeilen.</span><span class="sxs-lookup"><span data-stu-id="01526-111">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="01526-112">Flexible Typen sind in verschiedenen Arten von Situationen nützlich.</span><span class="sxs-lookup"><span data-stu-id="01526-112">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="01526-113">Bei einer Funktion höherer Ordnung (Funktion, die eine Funktion als Argument akzeptiert), ist es beispielsweise oft sinnvoll, verwenden die Funktion einen flexiblen Typ zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="01526-113">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="01526-114">Im folgenden Beispiel die Verwendung eines flexiblen Typs mit einem Sequenzargument in `iterate2` ermöglicht die Funktion höheren Ordnung arbeiten mit Funktionen, die Sequenzen, Arrays, Listen und aufzählbare andersartiges zu generieren.</span><span class="sxs-lookup"><span data-stu-id="01526-114">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="01526-115">Berücksichtigen Sie die folgenden beiden Funktionen, des welche eine Sequenz zurückgibt, von denen andere einen flexiblen Typ zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="01526-115">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="01526-116">Betrachten Sie als weiteres Beispiel die [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) Library-Funktion:</span><span class="sxs-lookup"><span data-stu-id="01526-116">As another example, consider the [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="01526-117">Sie können eine der folgenden aufzählbaren Sequenzen dieser Funktion übergeben:</span><span class="sxs-lookup"><span data-stu-id="01526-117">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="01526-118">Eine Liste mit Listen</span><span class="sxs-lookup"><span data-stu-id="01526-118">A list of lists</span></span>
- <span data-ttu-id="01526-119">Eine Liste von arrays</span><span class="sxs-lookup"><span data-stu-id="01526-119">A list of arrays</span></span>
- <span data-ttu-id="01526-120">Ein Array von Listen</span><span class="sxs-lookup"><span data-stu-id="01526-120">An array of lists</span></span>
- <span data-ttu-id="01526-121">Ein Array von Sequenzen</span><span class="sxs-lookup"><span data-stu-id="01526-121">An array of sequences</span></span>
- <span data-ttu-id="01526-122">Eine beliebige andere Kombination von aufzählbare Sequenzen</span><span class="sxs-lookup"><span data-stu-id="01526-122">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="01526-123">Der folgende code verwendet `Seq.concat` der Szenarien veranschaulicht, die Sie über flexible Typen unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="01526-123">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="01526-124">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="01526-124">The output is as follows.</span></span>

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="01526-125">In F# erläutert sind wie in anderen objektorientierten Sprachen Kontexte vorhanden in denen abgeleiteten Typen oder Typen, die Schnittstellen implementieren automatisch in einen Basistyp oder Schnittstellentyp konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="01526-125">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="01526-126">Diese automatische Konvertierungen erfolgen in direkten Argumente, aber nicht, wenn der Typ in einer untergeordneten Position, im Rahmen eines komplexen Typs wie z. B. einen Rückgabetyp eines Funktionstyps oder als Typargument ist.</span><span class="sxs-lookup"><span data-stu-id="01526-126">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="01526-127">Daher ist die flexiblen Typ Notation primär nützlich, wenn der Typ, den sie zum Anwenden eines komplexen Typs gehört.</span><span class="sxs-lookup"><span data-stu-id="01526-127">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="01526-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01526-128">See Also</span></span>

[<span data-ttu-id="01526-129">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="01526-129">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="01526-130">Generika</span><span class="sxs-lookup"><span data-stu-id="01526-130">Generics</span></span>](generics/index.md)
