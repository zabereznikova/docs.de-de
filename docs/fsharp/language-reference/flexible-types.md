---
title: Flexible Typen
description: Erfahren Sie, wie F# Sie eine flexible Typanmerkung verwenden, die angibt, dass ein Parameter, eine Variable oder ein Wert einen Typ aufweist, der mit einem angegebenen Typ kompatibel ist.
ms.date: 05/16/2016
ms.openlocfilehash: 43caa6cd35630df648beda5cc43cffae2ecd6f6a
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630259"
---
# <a name="flexible-types"></a><span data-ttu-id="fd5b9-103">Flexible Typen</span><span class="sxs-lookup"><span data-stu-id="fd5b9-103">Flexible Types</span></span>

<span data-ttu-id="fd5b9-104">Eine *flexible* Typanmerkung gibt an, dass ein Parameter, eine Variable oder ein Wert einen Typ aufweist, der mit einem angegebenen Typ kompatibel ist, wobei die Kompatibilität durch die Position in einer objektorientierten Hierarchie von Klassen oder Schnittstellen bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="fd5b9-104">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="fd5b9-105">Flexible Typen sind besonders nützlich, wenn die automatische Konvertierung in Typen, die in der Typhierarchie höher sind, nicht stattfindet, Sie aber weiterhin die Funktion für die Arbeit mit einem beliebigen Typ in der Hierarchie oder einem beliebigen Typ aktivieren möchten, der eine Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="fd5b9-105">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="fd5b9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd5b9-106">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="fd5b9-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd5b9-107">Remarks</span></span>

<span data-ttu-id="fd5b9-108">In der vorherigen Syntax stellt *Type* einen Basistyp oder eine Schnittstelle dar.</span><span class="sxs-lookup"><span data-stu-id="fd5b9-108">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="fd5b9-109">Ein flexibler Typ entspricht einem generischen Typ, der über eine Einschränkung verfügt, die die zulässigen Typen auf Typen beschränkt, die mit dem Basis-oder Schnittstellentyp kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="fd5b9-109">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="fd5b9-110">Das heißt, die folgenden zwei Codezeilen sind äquivalent.</span><span class="sxs-lookup"><span data-stu-id="fd5b9-110">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="fd5b9-111">Flexible Typen sind in verschiedenen Arten von Situationen nützlich.</span><span class="sxs-lookup"><span data-stu-id="fd5b9-111">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="fd5b9-112">Wenn Sie z. b. über eine Funktion höherer Ordnung verfügen (eine Funktion, die eine Funktion als Argument annimmt), ist es oft hilfreich, dass die Funktion einen flexiblen Typ zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fd5b9-112">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="fd5b9-113">Im folgenden Beispiel ermöglicht die Verwendung eines flexiblen Typs mit einem Sequence-Argument in `iterate2` der Funktion höherer Ordnung die Verwendung von Funktionen, die Sequenzen, Arrays, Listen und alle anderen Aufzähl Bare-Typen generieren.</span><span class="sxs-lookup"><span data-stu-id="fd5b9-113">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="fd5b9-114">Beachten Sie die folgenden zwei Funktionen, von denen eine eine Sequenz zurückgibt, die andere einen flexiblen Typ zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fd5b9-114">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="fd5b9-115">Betrachten Sie als weiteres Beispiel die Bibliotheksfunktion " [setq. Concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) ":</span><span class="sxs-lookup"><span data-stu-id="fd5b9-115">As another example, consider the [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="fd5b9-116">Sie können jede der folgenden Aufzähl Bare-Sequenzen an diese Funktion übergeben:</span><span class="sxs-lookup"><span data-stu-id="fd5b9-116">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="fd5b9-117">Eine Liste mit Listen</span><span class="sxs-lookup"><span data-stu-id="fd5b9-117">A list of lists</span></span>
- <span data-ttu-id="fd5b9-118">Eine Liste von Arrays</span><span class="sxs-lookup"><span data-stu-id="fd5b9-118">A list of arrays</span></span>
- <span data-ttu-id="fd5b9-119">Ein Array von Listen</span><span class="sxs-lookup"><span data-stu-id="fd5b9-119">An array of lists</span></span>
- <span data-ttu-id="fd5b9-120">Ein Array von Sequenzen</span><span class="sxs-lookup"><span data-stu-id="fd5b9-120">An array of sequences</span></span>
- <span data-ttu-id="fd5b9-121">Eine beliebige andere Kombination von Aufzähl Bare-Sequenzen</span><span class="sxs-lookup"><span data-stu-id="fd5b9-121">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="fd5b9-122">Der folgende Code verwendet `Seq.concat` , um die Szenarien zu veranschaulichen, die Sie mithilfe von flexiblen Typen unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="fd5b9-122">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="fd5b9-123">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="fd5b9-123">The output is as follows.</span></span>

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="fd5b9-124">In F# sind wie in anderen objektorientierten Sprachen Kontexte, die in denen abgeleiteten Typen oder Typen, die Schnittstellen implementieren automatisch in einem Basistyp oder der Schnittstellentyp konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="fd5b9-124">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="fd5b9-125">Diese automatischen Konvertierungen erfolgen in direkten Argumenten, jedoch nicht, wenn sich der Typ in einer untergeordneten Position befindet, als Teil eines komplexeren Typs, z. b. eines Rückgabe Typs eines Funktions Typs, oder als Typargument.</span><span class="sxs-lookup"><span data-stu-id="fd5b9-125">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="fd5b9-126">Daher ist die flexible typnotation vor allem dann nützlich, wenn der Typ, auf den Sie Sie anwenden, Teil eines komplexeren Typs ist.</span><span class="sxs-lookup"><span data-stu-id="fd5b9-126">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd5b9-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd5b9-127">See also</span></span>

- [<span data-ttu-id="fd5b9-128">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="fd5b9-128">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="fd5b9-129">Generika</span><span class="sxs-lookup"><span data-stu-id="fd5b9-129">Generics</span></span>](./generics/index.md)
