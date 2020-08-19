---
title: Flexible Typen
description: 'Erfahren Sie, wie Sie eine flexible F #-Typanmerkung verwenden, die angibt, dass ein Parameter, eine Variable oder ein Wert einen Typ aufweist, der mit einem angegebenen Typ kompatibel ist.'
ms.date: 08/15/2020
ms.openlocfilehash: 44241ad082cd7f3de9e0cc6a48b8a8946e7b33d3
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557749"
---
# <a name="flexible-types"></a><span data-ttu-id="3b836-103">Flexible Typen</span><span class="sxs-lookup"><span data-stu-id="3b836-103">Flexible Types</span></span>

<span data-ttu-id="3b836-104">Eine *flexible Typanmerkung* gibt an, dass ein Parameter, eine Variable oder ein Wert einen Typ aufweist, der mit einem angegebenen Typ kompatibel ist, wobei die Kompatibilität durch die Position in einer objektorientierten Hierarchie von Klassen oder Schnittstellen bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="3b836-104">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="3b836-105">Flexible Typen sind besonders nützlich, wenn die automatische Konvertierung in Typen, die in der Typhierarchie höher sind, nicht stattfindet, Sie aber weiterhin die Funktion für die Arbeit mit einem beliebigen Typ in der Hierarchie oder einem beliebigen Typ aktivieren möchten, der eine Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="3b836-105">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="3b836-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="3b836-106">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="3b836-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3b836-107">Remarks</span></span>

<span data-ttu-id="3b836-108">In der vorherigen Syntax stellt *Type* einen Basistyp oder eine Schnittstelle dar.</span><span class="sxs-lookup"><span data-stu-id="3b836-108">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="3b836-109">Ein flexibler Typ entspricht einem generischen Typ, der über eine Einschränkung verfügt, die die zulässigen Typen auf Typen beschränkt, die mit dem Basis-oder Schnittstellentyp kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="3b836-109">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="3b836-110">Das heißt, die folgenden zwei Codezeilen sind äquivalent.</span><span class="sxs-lookup"><span data-stu-id="3b836-110">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="3b836-111">Flexible Typen sind in verschiedenen Arten von Situationen nützlich.</span><span class="sxs-lookup"><span data-stu-id="3b836-111">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="3b836-112">Wenn Sie z. b. über eine Funktion höherer Ordnung verfügen (eine Funktion, die eine Funktion als Argument annimmt), ist es oft hilfreich, dass die Funktion einen flexiblen Typ zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3b836-112">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="3b836-113">Im folgenden Beispiel ermöglicht die Verwendung eines flexiblen Typs mit einem Sequence-Argument in `iterate2` der Funktion höherer Ordnung die Verwendung von Funktionen, die Sequenzen, Arrays, Listen und alle anderen Aufzähl Bare-Typen generieren.</span><span class="sxs-lookup"><span data-stu-id="3b836-113">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="3b836-114">Beachten Sie die folgenden zwei Funktionen, von denen eine eine Sequenz zurückgibt, die andere einen flexiblen Typ zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3b836-114">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="3b836-115">Betrachten Sie als weiteres Beispiel die Bibliotheksfunktion " [setq. Concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#concat) ":</span><span class="sxs-lookup"><span data-stu-id="3b836-115">As another example, consider the [Seq.concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#concat) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="3b836-116">Sie können jede der folgenden Aufzähl Bare-Sequenzen an diese Funktion übergeben:</span><span class="sxs-lookup"><span data-stu-id="3b836-116">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="3b836-117">Eine Liste mit Listen</span><span class="sxs-lookup"><span data-stu-id="3b836-117">A list of lists</span></span>
- <span data-ttu-id="3b836-118">Eine Liste von Arrays</span><span class="sxs-lookup"><span data-stu-id="3b836-118">A list of arrays</span></span>
- <span data-ttu-id="3b836-119">Ein Array von Listen</span><span class="sxs-lookup"><span data-stu-id="3b836-119">An array of lists</span></span>
- <span data-ttu-id="3b836-120">Ein Array von Sequenzen</span><span class="sxs-lookup"><span data-stu-id="3b836-120">An array of sequences</span></span>
- <span data-ttu-id="3b836-121">Eine beliebige andere Kombination von Aufzähl Bare-Sequenzen</span><span class="sxs-lookup"><span data-stu-id="3b836-121">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="3b836-122">Der folgende Code verwendet `Seq.concat` , um die Szenarien zu veranschaulichen, die Sie mithilfe von flexiblen Typen unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="3b836-122">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="3b836-123">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="3b836-123">The output is as follows.</span></span>

```console
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="3b836-124">In F # gibt es wie in anderen objektorientierten Sprachen Kontexte, in denen abgeleitete Typen oder Typen, die Schnittstellen implementieren, automatisch in einen Basistyp oder Schnittstellentyp konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="3b836-124">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="3b836-125">Diese automatischen Konvertierungen erfolgen in direkten Argumenten, jedoch nicht, wenn sich der Typ in einer untergeordneten Position befindet, als Teil eines komplexeren Typs, z. b. eines Rückgabe Typs eines Funktions Typs, oder als Typargument.</span><span class="sxs-lookup"><span data-stu-id="3b836-125">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="3b836-126">Daher ist die flexible typnotation vor allem dann nützlich, wenn der Typ, auf den Sie Sie anwenden, Teil eines komplexeren Typs ist.</span><span class="sxs-lookup"><span data-stu-id="3b836-126">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b836-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3b836-127">See also</span></span>

- [<span data-ttu-id="3b836-128">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="3b836-128">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="3b836-129">Generics</span><span class="sxs-lookup"><span data-stu-id="3b836-129">Generics</span></span>](./generics/index.md)
