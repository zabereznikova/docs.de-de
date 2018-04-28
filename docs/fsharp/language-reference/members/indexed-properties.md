---
title: Indizierte Eigenschaften (F#)
description: Informationen Sie zu f#-indizierte Eigenschaften, die Eigenschaften sind, die arrayähnlichen Zugriff auf geordnete Daten bereitstellen.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 39396b3a5ec43f9a8ab0df96afeb69e05801c752
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="indexed-properties"></a><span data-ttu-id="25c4d-103">Indizierte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="25c4d-103">Indexed Properties</span></span>

<span data-ttu-id="25c4d-104">*Indizierte Eigenschaften* befohlen Eigenschaften, die arrayähnlichen Zugriff auf Daten.</span><span class="sxs-lookup"><span data-stu-id="25c4d-104">*Indexed properties* are properties that provide array-like access to ordered data.</span></span>


## <a name="syntax"></a><span data-ttu-id="25c4d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="25c4d-105">Syntax</span></span>

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.PropertyName
    with get(index-variable) =
        get-function-body
    and set index-variablesvalue-variables =
        set-function-body

// Indexed property that has get only.
member self-identifier.PropertyName(index-variable) =
    get-function-body

// Alternative syntax for indexed property with get only
member self-identifier.PropertyName
    with get(index-variables) =
        get-function-body

// Indexed property that has set only.
member self-identifier.PropertyName
    with set index-variablesvalue-variables = 
        set-function-body
```

## <a name="remarks"></a><span data-ttu-id="25c4d-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25c4d-106">Remarks</span></span>
<span data-ttu-id="25c4d-107">Die drei Arten von der vorherigen Syntax zeigen, wie indizierte Eigenschaften definieren, die sowohl eine `get` und eine `set` -Methode, haben eine `get` Methode nur oder über eine `set` Methode nur.</span><span class="sxs-lookup"><span data-stu-id="25c4d-107">The three forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="25c4d-108">Sie können auch kombiniert sowohl die Syntax für nur Get- und Set nur die Syntax und erzeugt eine Eigenschaft, die Get- und Set hat.</span><span class="sxs-lookup"><span data-stu-id="25c4d-108">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="25c4d-109">Diese Form können Sie unterschiedliche Zugriffsmodifizierer und Attribute in der Get und set-Methoden.</span><span class="sxs-lookup"><span data-stu-id="25c4d-109">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="25c4d-110">Wenn die *PropertyName* ist `Item`, behandelt der Compiler die Eigenschaft als eine indizierte Standardeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="25c4d-110">When the *PropertyName* is `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="25c4d-111">Ein *indizierte Standardeigenschaft* ist eine Eigenschaft, die Sie mithilfe einer arrayähnlichen Syntax auf die Objektinstanz zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="25c4d-111">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="25c4d-112">Z. B. wenn `obj` ist ein Objekt des Typs, der diese Eigenschaft, die Syntax definiert `obj.[index]` wird verwendet, um Zugriff auf die Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="25c4d-112">For example, if `obj` is an object of the type that defines this property, the syntax `obj.[index]` is used to access the property.</span></span>

<span data-ttu-id="25c4d-113">Die Syntax für den Zugriff auf eine nicht standardmäßige indizierte Eigenschaft wird zum Bereitstellen des Namens der Eigenschaft und der Index in Klammern.</span><span class="sxs-lookup"><span data-stu-id="25c4d-113">The syntax for accessing a nondefault indexed property is to provide the name of the property and the index in parentheses.</span></span> <span data-ttu-id="25c4d-114">Wenn die Eigenschaft beispielsweise `Ordinal`, Schreiben Sie `obj.Ordinal(index)` darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="25c4d-114">For example, if the property is `Ordinal`, you write `obj.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="25c4d-115">Unabhängig davon, welche Form, die Sie verwenden, immer die Curry-Form verwenden sollte die `set` Methode nach einer indizierten Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="25c4d-115">Regardless of which form you use, you should always use the curried form for the `set` method on an indexed property.</span></span> <span data-ttu-id="25c4d-116">Informationen über Curry-Funktionen finden Sie unter [Funktionen](../functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="25c4d-116">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="25c4d-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="25c4d-117">Example</span></span>

<span data-ttu-id="25c4d-118">Das folgende Codebeispiel veranschaulicht die Definition und Verwendung von Standard- und nicht standardmäßiger indizierte Eigenschaften, die verfügen über get- und set-Methoden.</span><span class="sxs-lookup"><span data-stu-id="25c4d-118">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="25c4d-119">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="25c4d-119">Output</span></span>

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a><span data-ttu-id="25c4d-120">Indizierte Eigenschaften mit mehreren Indexvariablen</span><span class="sxs-lookup"><span data-stu-id="25c4d-120">Indexed Properties with Multiple Index Variables</span></span>
<span data-ttu-id="25c4d-121">Indizierte Eigenschaften können mehr als eine Indexvariable haben.</span><span class="sxs-lookup"><span data-stu-id="25c4d-121">Indexed properties can have more than one index variable.</span></span> <span data-ttu-id="25c4d-122">In diesem Fall werden die Variablen durch Kommas getrennt, wenn die Eigenschaft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="25c4d-122">In that case, the variables are separated by commas when the property is used.</span></span> <span data-ttu-id="25c4d-123">Die Set-Methode in einer solchen Eigenschaft benötigen zwei Curry-Argumenten, das erste ist ein Tupel, die mit den Schlüsseln, und das zweite ist der festgelegte Wert.</span><span class="sxs-lookup"><span data-stu-id="25c4d-123">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value being set.</span></span>

<span data-ttu-id="25c4d-124">Der folgende Code veranschaulicht die Verwendung einer indizierten Eigenschaft mit mehreren Indexvariablen.</span><span class="sxs-lookup"><span data-stu-id="25c4d-124">The following code demonstrates the use of an indexed property with multiple index variables.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]
    
## <a name="see-also"></a><span data-ttu-id="25c4d-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25c4d-125">See Also</span></span>
[<span data-ttu-id="25c4d-126">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="25c4d-126">Members</span></span>](index.md)
