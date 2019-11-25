---
title: Indizierte Eigenschaften
description: Erfahren Sie mehr über indizierte Eigenschaften in F#, die einen Array ähnlichen Zugriff auf geordnete Daten ermöglichen.
ms.date: 11/04/2019
ms.openlocfilehash: f6cf3bfa737d2bf458e379594be5884696cee3e1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976610"
---
# <a name="indexed-properties"></a><span data-ttu-id="57311-103">Indizierte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="57311-103">Indexed Properties</span></span>

<span data-ttu-id="57311-104">Beim Definieren einer Klasse, die geordnete Daten abstrahiert, kann es manchmal hilfreich sein, den indizierten Zugriff auf diese Daten bereitzustellen, ohne die zugrunde liegende Implementierung verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="57311-104">When defining a class that abstracts over ordered data, it can sometimes be helpful to provide indexed access to that data without exposing the underlying implementation.</span></span> <span data-ttu-id="57311-105">Dies erfolgt mit dem `Item`-Member.</span><span class="sxs-lookup"><span data-stu-id="57311-105">This is done with the `Item` member.</span></span>

## <a name="syntax"></a><span data-ttu-id="57311-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="57311-106">Syntax</span></span>

```fsharp
// Indexed property that can be read and written to
member self-identifier.Item
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property can only be read
member self-identifier.Item
    with get(index-values) =
        get-member-body

// Indexed property that can only be set
member self-identifier.Item
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a><span data-ttu-id="57311-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="57311-107">Remarks</span></span>

<span data-ttu-id="57311-108">Die Formen der vorherigen Syntax veranschaulichen, wie indizierte Eigenschaften definiert werden, die sowohl über eine `get`-als auch eine `set`-Methode verfügen, nur über eine `get`-Methode verfügen oder nur über eine `set`-Methode verfügen.</span><span class="sxs-lookup"><span data-stu-id="57311-108">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="57311-109">Sie können auch die Syntax für "Get only" und die für "Set" angezeigte Syntax kombinieren und eine Eigenschaft mit "Get" und "Set" entwickeln.</span><span class="sxs-lookup"><span data-stu-id="57311-109">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="57311-110">In diesem letzteren Formular können Sie verschiedene Zugriffsmodifizierer und Attribute für die Get-und Set-Methoden einfügen.</span><span class="sxs-lookup"><span data-stu-id="57311-110">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="57311-111">Wenn Sie den Namen `Item`verwenden, behandelt der Compiler die Eigenschaft als indizierte Standard Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="57311-111">By using the name `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="57311-112">Eine *indizierte Standard Eigenschaft* ist eine Eigenschaft, auf die Sie mithilfe einer Array ähnlichen Syntax für die Objektinstanz zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="57311-112">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="57311-113">Wenn `o` z. b. ein Objekt des Typs ist, der diese Eigenschaft definiert, wird die Syntax `o.[index]` verwendet, um auf die Eigenschaft zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="57311-113">For example, if `o` is an object of the type that defines this property, the syntax `o.[index]` is used to access the property.</span></span>

<span data-ttu-id="57311-114">Die Syntax für den Zugriff auf eine nicht standardmäßig indizierte Eigenschaft besteht darin, den Namen der Eigenschaft und den Index in Klammern wie einem regulären Member bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="57311-114">The syntax for accessing a non-default indexed property is to provide the name of the property and the index in parentheses, just like a regular member.</span></span> <span data-ttu-id="57311-115">Wenn beispielsweise die-Eigenschaft auf `o` `Ordinal`aufgerufen wird, schreiben Sie `o.Ordinal(index)`, um darauf zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="57311-115">For example, if the property on `o` is called `Ordinal`, you write `o.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="57311-116">Unabhängig davon, welches Formular Sie verwenden, sollten Sie immer das Curry-Formular für die Set-Methode für eine indizierte Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="57311-116">Regardless of which form you use, you should always use the curried form for the set method on an indexed property.</span></span> <span data-ttu-id="57311-117">Weitere Informationen zu Curry-Funktionen finden Sie unter [Functions](../functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="57311-117">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="57311-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="57311-118">Example</span></span>

<span data-ttu-id="57311-119">Im folgenden Codebeispiel werden die Definition und die Verwendung von standardmäßigen und nicht standardmäßig indizierten Eigenschaften veranschaulicht, die über Get-und Set-Methoden verfügen.</span><span class="sxs-lookup"><span data-stu-id="57311-119">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="57311-120">Output</span><span class="sxs-lookup"><span data-stu-id="57311-120">Output</span></span>

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a><span data-ttu-id="57311-121">Indizierte Eigenschaften mit mehreren Indexwerten</span><span class="sxs-lookup"><span data-stu-id="57311-121">Indexed Properties with multiple index values</span></span>

<span data-ttu-id="57311-122">Indizierte Eigenschaften können über mehr als einen Indexwert verfügen.</span><span class="sxs-lookup"><span data-stu-id="57311-122">Indexed properties can have more than one index value.</span></span> <span data-ttu-id="57311-123">In diesem Fall werden die Werte durch Kommas getrennt, wenn die-Eigenschaft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="57311-123">In that case, the values are separated by commas when the property is used.</span></span> <span data-ttu-id="57311-124">Die Set-Methode in einer solchen Eigenschaft muss zwei Curry-Argumente aufweisen, wobei das erste ein Tupel ist, das die Schlüssel enthält, und das zweite ist der festzulegende Wert.</span><span class="sxs-lookup"><span data-stu-id="57311-124">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value to set.</span></span>

<span data-ttu-id="57311-125">Der folgende Code veranschaulicht die Verwendung einer indizierten Eigenschaft mit mehreren Indexwerten.</span><span class="sxs-lookup"><span data-stu-id="57311-125">The following code demonstrates the use of an indexed property with multiple index values.</span></span>

```fsharp
open System.Collections.Generic

/// Basic implementation of a sparse matrix based on a dictionary
type SparseMatrix() =
    let table = new Dictionary<(int * int), float>()
    member _.Item
        // Because the key is comprised of two values, 'get' has two index values
        with get(key1, key2) = table.[(key1, key2)]

        // 'set' has two index values and a new value to place in the key's position
        and set (key1, key2) value = table.[(key1, key2)] <- value

let sm = new SparseMatrix()
for i in 1..1000 do
    sm.[i, i] <- float i * float i
```

## <a name="see-also"></a><span data-ttu-id="57311-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57311-126">See also</span></span>

- [<span data-ttu-id="57311-127">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="57311-127">Members</span></span>](index.md)
