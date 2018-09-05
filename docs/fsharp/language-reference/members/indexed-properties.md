---
title: Indizierte Eigenschaften (F#)
description: Informationen Sie zu F#-indizierte Eigenschaften, die Eigenschaften sind, die arrayähnlichen Zugriff auf sortierte Daten bereitstellen.
ms.date: 05/16/2016
ms.openlocfilehash: e56e4e2ea3f35df4c8ec46012357242cb6ce69f3
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43749592"
---
# <a name="indexed-properties"></a><span data-ttu-id="b9923-103">Indizierte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b9923-103">Indexed Properties</span></span>

<span data-ttu-id="b9923-104">*Indizierte Eigenschaften* sind Eigenschaften, die arrayähnlichen Zugriff auf bereitstellen sortiert Daten.</span><span class="sxs-lookup"><span data-stu-id="b9923-104">*Indexed properties* are properties that provide array-like access to ordered data.</span></span> <span data-ttu-id="b9923-105">Sie gibt drei Arten:</span><span class="sxs-lookup"><span data-stu-id="b9923-105">They come in three forms:</span></span>

* `Item`
* `Ordinal`
* `Cardinal`

<span data-ttu-id="b9923-106">Ein F#-Element muss einen dieser drei Namen arrayähnlichen Zugriff bereitstellen benannt werden.</span><span class="sxs-lookup"><span data-stu-id="b9923-106">An F# member must be named one of these three names to provide array-like access.</span></span> <span data-ttu-id="b9923-107">`IndexerName` wird verwendet, um jeden der drei folgenden Optionen darstellen:</span><span class="sxs-lookup"><span data-stu-id="b9923-107">`IndexerName` is used to represent any of the three options below:</span></span>

## <a name="syntax"></a><span data-ttu-id="b9923-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9923-108">Syntax</span></span>

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.IndexerName
    with get(index-variable) =
        get-function-body
    and set index-variablesvalue-variables =
        set-function-body

// Indexed property that has get only.
member self-identifier.IndexerName(index-variable) =
    get-function-body

// Alternative syntax for indexed property with get only
member self-identifier.IndexerName
    with get(index-variables) =
        get-function-body

// Indexed property that has set only.
member self-identifier.IndexerName
    with set index-variablesvalue-variables = 
        set-function-body
```

## <a name="remarks"></a><span data-ttu-id="b9923-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b9923-109">Remarks</span></span>

<span data-ttu-id="b9923-110">Die Formen der vorherigen Syntax zeigen, wie Sie indizierte Eigenschaften definiert, die sowohl eine `get` und ein `set` -Methode, haben eine `get` Methode nur oder über eine `set` Methode nur.</span><span class="sxs-lookup"><span data-stu-id="b9923-110">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="b9923-111">Sie können auch kombiniert sowohl die Syntax für nur Get- und die Syntax für die Gruppe nur und erzeugen eine Eigenschaft, die sowohl get- und Set hat.</span><span class="sxs-lookup"><span data-stu-id="b9923-111">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="b9923-112">Diese Form können Sie verschiedene Zugriffsmodifizierer und Attribute für die Get-und set-Methoden.</span><span class="sxs-lookup"><span data-stu-id="b9923-112">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="b9923-113">Wenn die *IndexerName* ist `Item`, behandelt der Compiler die Eigenschaft als eine indizierte Standardeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b9923-113">When the *IndexerName* is `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="b9923-114">Ein *indizierte Standardeigenschaft* ist eine Eigenschaft, die Sie zugreifen können, mithilfe einer arrayähnlichen Syntax in der Objektinstanz.</span><span class="sxs-lookup"><span data-stu-id="b9923-114">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="b9923-115">Z. B. wenn `obj` ist ein Objekt des Typs, der diese Eigenschaft, die Syntax definiert `obj.[index]` wird verwendet, um die Eigenschaft zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b9923-115">For example, if `obj` is an object of the type that defines this property, the syntax `obj.[index]` is used to access the property.</span></span>

<span data-ttu-id="b9923-116">Die Syntax für den Zugriff auf eine nicht standardmäßige indizierte Eigenschaft ist auf den Namen der Eigenschaft und der Index in Klammern angeben.</span><span class="sxs-lookup"><span data-stu-id="b9923-116">The syntax for accessing a nondefault indexed property is to provide the name of the property and the index in parentheses.</span></span> <span data-ttu-id="b9923-117">Wenn die Eigenschaft ist z. B. `Ordinal`, Sie schreiben `obj.Ordinal(index)` , darauf zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="b9923-117">For example, if the property is `Ordinal`, you write `obj.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="b9923-118">Unabhängig davon, welche Form, die Sie verwenden, Sie immer die Curry-Form verwenden sollten die `set` Methode für eine indizierte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b9923-118">Regardless of which form you use, you should always use the curried form for the `set` method on an indexed property.</span></span> <span data-ttu-id="b9923-119">Weitere Informationen zu Funktionen mit Currying, finden Sie unter [Funktionen](../functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="b9923-119">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="b9923-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9923-120">Example</span></span>

<span data-ttu-id="b9923-121">Das folgende Codebeispiel veranschaulicht die Definition und Verwendung von Standard- und nicht standardmäßigen indizierte Eigenschaften, die verfügen über get- und set-Methoden.</span><span class="sxs-lookup"><span data-stu-id="b9923-121">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="b9923-122">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="b9923-122">Output</span></span>

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a><span data-ttu-id="b9923-123">Indizierte Eigenschaften mit mehreren Indexvariablen</span><span class="sxs-lookup"><span data-stu-id="b9923-123">Indexed Properties with Multiple Index Variables</span></span>

<span data-ttu-id="b9923-124">Indizierte Eigenschaften können mehrere Indexvariable haben.</span><span class="sxs-lookup"><span data-stu-id="b9923-124">Indexed properties can have more than one index variable.</span></span> <span data-ttu-id="b9923-125">In diesem Fall werden die Variablen durch Kommas getrennt, wenn die Eigenschaft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b9923-125">In that case, the variables are separated by commas when the property is used.</span></span> <span data-ttu-id="b9923-126">Die Set-Methode in eine entsprechende Eigenschaft benötigen zwei Curry-Argumente, das erste Argument ist ein Tupel, die die Schlüssel und die zweite ist der Wert festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="b9923-126">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value being set.</span></span>

<span data-ttu-id="b9923-127">Der folgende Code veranschaulicht die Verwendung einer indizierten Eigenschaft mit mehreren Indexvariablen.</span><span class="sxs-lookup"><span data-stu-id="b9923-127">The following code demonstrates the use of an indexed property with multiple index variables.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]

## <a name="see-also"></a><span data-ttu-id="b9923-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9923-128">See also</span></span>

- [<span data-ttu-id="b9923-129">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="b9923-129">Members</span></span>](index.md)
