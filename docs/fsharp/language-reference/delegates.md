---
title: Delegaten (F#)
description: Informationen Sie zum Arbeiten mit Delegaten in F# erläutert werden.
ms.date: 05/16/2016
ms.openlocfilehash: 664b4f80302871d05ea9604ca90219e19bc14ddb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563440"
---
# <a name="delegates"></a><span data-ttu-id="f5dcd-103">Delegaten</span><span class="sxs-lookup"><span data-stu-id="f5dcd-103">Delegates</span></span>

<span data-ttu-id="f5dcd-104">Ein Delegat stellt einen Funktionsaufruf dar, wie ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-104">A delegate represents a function call as an object.</span></span> <span data-ttu-id="f5dcd-105">In F# erläutert werden sollten Sie normalerweise Funktionswerte verwenden, um Funktionen als erstrangige Werte darzustellen. Allerdings Delegaten in .NET Framework verwendet werden und daher werden benötigt, wenn Interoperation mit APIs, die sie erwarten.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-105">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="f5dcd-106">Sie können auch verwendet werden, wenn authoring Bibliotheken, die für entwickelt von anderen .NET Framework-Sprachen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-106">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>


## <a name="syntax"></a><span data-ttu-id="f5dcd-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5dcd-107">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="f5dcd-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f5dcd-108">Remarks</span></span>
<span data-ttu-id="f5dcd-109">In der vorherigen Syntax `type1` stellt den Argumenttyp bzw. die Datentypen und `type2` den Rückgabetyp darstellt.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-109">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="f5dcd-110">Die Argumenttypen, das von dargestellt sind `type1` werden automatisch mit Currying.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-110">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="f5dcd-111">Dies legt nahe, die für diesen Typ, der ein Tupel-Formular verwenden, wenn die Argumente der Zielfunktion Curry sind, und ein Tupel in Klammern für Argumente, die bereits in der Tupelform sind.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-111">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="f5dcd-112">Die automatische currying entfernt einen Satz von Klammern, lassen ein Tupelargument, das die Zielmethode übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-112">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="f5dcd-113">Finden Sie im Codebeispiel wird die Syntax, die in jedem Fall verwendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-113">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="f5dcd-114">Delegaten angefügt werden können, in f#-Funktionswerte und statische oder Instanzmethoden.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-114">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="f5dcd-115">F#-Funktionswerte können direkt als Argumente an die Konstruktoren delegieren übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-115">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="f5dcd-116">Bei einer statischen Methode erstellen Sie den Delegaten mit dem Namen der Klasse und die Methode an.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-116">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="f5dcd-117">Für eine Instanzmethode ist Geben Sie die Objektinstanz und-Methode in ein Argument.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-117">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="f5dcd-118">In beiden Fällen wird der Memberzugriffsoperator (`.`) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-118">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="f5dcd-119">Die `Invoke` Methode auf den Delegattyp gekapselten Funktionsaufrufe.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-119">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="f5dcd-120">Darüber hinaus können Delegaten als Funktionswerte übergeben werden, auf den Namen des Invoke-Methode ohne Klammern verweisen.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-120">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="f5dcd-121">Der folgende Code zeigt die Syntax zum Erstellen von Delegaten, die verschiedene Methoden in einer Klasse darstellen.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-121">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="f5dcd-122">Je nachdem, ob die Methode eine statische Methode oder Instanzmethode handelt, und gibt an, ob Argumente in die Tupelform oder die Curry-Form verfügt ist die Syntax zum Deklarieren und Zuweisen der Delegat etwas anders.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-122">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="f5dcd-123">Der folgende Code zeigt einige der Arbeit mit Delegaten können unterschiedliche Arten.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-123">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="f5dcd-124">Im vorangehenden Codebeispiel wird die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-124">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="f5dcd-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5dcd-125">See Also</span></span>
[<span data-ttu-id="f5dcd-126">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="f5dcd-126">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="f5dcd-127">Parameter und Argumente</span><span class="sxs-lookup"><span data-stu-id="f5dcd-127">Parameters and Arguments</span></span>](parameters-and-arguments.md)

[<span data-ttu-id="f5dcd-128">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="f5dcd-128">Events</span></span>](members/events.md)
