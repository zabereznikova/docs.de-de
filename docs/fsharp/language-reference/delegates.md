---
title: Delegaten (F#)
description: "Informationen Sie zum Arbeiten mit Delegaten in F# erläutert werden."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 719948a3-83ba-4618-82d6-a22945c3f4b0
ms.openlocfilehash: c929a342ab4c5098062417691a99cee3b007d2d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="delegates"></a><span data-ttu-id="d2d83-104">Delegaten</span><span class="sxs-lookup"><span data-stu-id="d2d83-104">Delegates</span></span>

<span data-ttu-id="d2d83-105">Ein Delegat stellt einen Funktionsaufruf dar, wie ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="d2d83-105">A delegate represents a function call as an object.</span></span> <span data-ttu-id="d2d83-106">In F# erläutert werden sollten Sie normalerweise Funktionswerte verwenden, um Funktionen als erstrangige Werte darzustellen. Allerdings Delegaten in .NET Framework verwendet werden und daher werden benötigt, wenn Interoperation mit APIs, die sie erwarten.</span><span class="sxs-lookup"><span data-stu-id="d2d83-106">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="d2d83-107">Sie können auch verwendet werden, wenn authoring Bibliotheken, die für entwickelt von anderen .NET Framework-Sprachen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2d83-107">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>


## <a name="syntax"></a><span data-ttu-id="d2d83-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2d83-108">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="d2d83-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d2d83-109">Remarks</span></span>
<span data-ttu-id="d2d83-110">In der vorherigen Syntax `type1` stellt den Argumenttyp bzw. die Datentypen und `type2` den Rückgabetyp darstellt.</span><span class="sxs-lookup"><span data-stu-id="d2d83-110">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="d2d83-111">Die Argumenttypen, das von dargestellt sind `type1` werden automatisch mit Currying.</span><span class="sxs-lookup"><span data-stu-id="d2d83-111">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="d2d83-112">Dies legt nahe, die für diesen Typ, der ein Tupel-Formular verwenden, wenn die Argumente der Zielfunktion Curry sind, und ein Tupel in Klammern für Argumente, die bereits in der Tupelform sind.</span><span class="sxs-lookup"><span data-stu-id="d2d83-112">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="d2d83-113">Die automatische currying entfernt einen Satz von Klammern, lassen ein Tupelargument, das die Zielmethode übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="d2d83-113">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="d2d83-114">Finden Sie im Codebeispiel wird die Syntax, die in jedem Fall verwendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="d2d83-114">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="d2d83-115">Delegaten angefügt werden können, in f#-Funktionswerte und statische oder Instanzmethoden.</span><span class="sxs-lookup"><span data-stu-id="d2d83-115">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="d2d83-116">F#-Funktionswerte können direkt als Argumente an die Konstruktoren delegieren übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="d2d83-116">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="d2d83-117">Bei einer statischen Methode erstellen Sie den Delegaten mit dem Namen der Klasse und die Methode an.</span><span class="sxs-lookup"><span data-stu-id="d2d83-117">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="d2d83-118">Für eine Instanzmethode ist Geben Sie die Objektinstanz und-Methode in ein Argument.</span><span class="sxs-lookup"><span data-stu-id="d2d83-118">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="d2d83-119">In beiden Fällen wird der Memberzugriffsoperator (`.`) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d2d83-119">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="d2d83-120">Die `Invoke` Methode auf den Delegattyp gekapselten Funktionsaufrufe.</span><span class="sxs-lookup"><span data-stu-id="d2d83-120">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="d2d83-121">Darüber hinaus können Delegaten als Funktionswerte übergeben werden, auf den Namen des Invoke-Methode ohne Klammern verweisen.</span><span class="sxs-lookup"><span data-stu-id="d2d83-121">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="d2d83-122">Der folgende Code zeigt die Syntax zum Erstellen von Delegaten, die verschiedene Methoden in einer Klasse darstellen.</span><span class="sxs-lookup"><span data-stu-id="d2d83-122">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="d2d83-123">Je nachdem, ob die Methode eine statische Methode oder Instanzmethode handelt, und gibt an, ob Argumente in die Tupelform oder die Curry-Form verfügt ist die Syntax zum Deklarieren und Zuweisen der Delegat etwas anders.</span><span class="sxs-lookup"><span data-stu-id="d2d83-123">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="d2d83-124">Der folgende Code zeigt einige der Arbeit mit Delegaten können unterschiedliche Arten.</span><span class="sxs-lookup"><span data-stu-id="d2d83-124">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="d2d83-125">Im vorangehenden Codebeispiel wird die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="d2d83-125">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="d2d83-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2d83-126">See Also</span></span>
[<span data-ttu-id="d2d83-127">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="d2d83-127">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="d2d83-128">Parameter und Argumente</span><span class="sxs-lookup"><span data-stu-id="d2d83-128">Parameters and Arguments</span></span>](parameters-and-arguments.md)

[<span data-ttu-id="d2d83-129">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="d2d83-129">Events</span></span>](members/events.md)
