---
title: Delegaten
description: Erfahren Sie, wie Sie in F#mit Delegaten arbeiten.
ms.date: 05/16/2016
ms.openlocfilehash: 65875897d5fc4b2ac66f1dfbe913f29fb74137cd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630369"
---
# <a name="delegates"></a><span data-ttu-id="4ad72-103">Delegaten</span><span class="sxs-lookup"><span data-stu-id="4ad72-103">Delegates</span></span>

<span data-ttu-id="4ad72-104">Ein Delegat stellt einen Funktionsaufruf als-Objekt dar.</span><span class="sxs-lookup"><span data-stu-id="4ad72-104">A delegate represents a function call as an object.</span></span> <span data-ttu-id="4ad72-105">In F#sollten Sie in der Regel Funktions Werte verwenden, um Funktionen als First Class-Werte darzustellen. Delegaten werden jedoch im .NET Framework verwendet und sind daher erforderlich, wenn Sie mit APIs interagieren, die Sie erwarten.</span><span class="sxs-lookup"><span data-stu-id="4ad72-105">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="4ad72-106">Sie können auch beim Erstellen von Bibliotheken verwendet werden, die für die Verwendung in anderen .NET Framework Sprachen entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="4ad72-106">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>

## <a name="syntax"></a><span data-ttu-id="4ad72-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ad72-107">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="4ad72-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4ad72-108">Remarks</span></span>

<span data-ttu-id="4ad72-109">In der vorherigen Syntax `type1` stellt den Argumenttyp oder die Typen dar und `type2` stellt den Rückgabetyp dar.</span><span class="sxs-lookup"><span data-stu-id="4ad72-109">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="4ad72-110">Die Argument Typen, die durch `type1` dargestellt werden, werden automatisch Curry.</span><span class="sxs-lookup"><span data-stu-id="4ad72-110">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="4ad72-111">Dies deutet darauf hin, dass Sie bei diesem Typ ein tupelformular verwenden, wenn die Argumente der Zielfunktion "currried" sind, und ein Tupel in Klammern für Argumente, die sich bereits im tupelformular befinden.</span><span class="sxs-lookup"><span data-stu-id="4ad72-111">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="4ad72-112">Bei der automatischen Currying wird eine Reihe von Klammern entfernt, wobei ein tupelargument, das mit der Ziel Methode übereinstimmt, erhalten bleibt.</span><span class="sxs-lookup"><span data-stu-id="4ad72-112">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="4ad72-113">Die Syntax, die Sie in jedem Fall verwenden sollten, finden Sie im Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="4ad72-113">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="4ad72-114">Delegaten angefügt werden können, um F#-Funktionswerte, und statische oder Instanzmethoden.</span><span class="sxs-lookup"><span data-stu-id="4ad72-114">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="4ad72-115">F#Funktions Werte können direkt als Argumente an Delegatkonstruktoren übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="4ad72-115">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="4ad72-116">Bei einer statischen Methode erstellen Sie den Delegaten mit dem Namen der Klasse und der-Methode.</span><span class="sxs-lookup"><span data-stu-id="4ad72-116">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="4ad72-117">Bei einer Instanzmethode stellen Sie die Objektinstanz und-Methode in einem Argument bereit.</span><span class="sxs-lookup"><span data-stu-id="4ad72-117">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="4ad72-118">In beiden Fällen wird der Member Access-Operator`.`() verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ad72-118">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="4ad72-119">Die `Invoke` Methode für den Delegattyp Ruft die gekapselte Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="4ad72-119">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="4ad72-120">Delegaten können auch als Funktions Werte übergeben werden, indem auf den Aufruf Methodennamen ohne Klammern verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4ad72-120">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="4ad72-121">Der folgende Code zeigt die Syntax zum Erstellen von Delegaten, die verschiedene Methoden in einer Klasse darstellen.</span><span class="sxs-lookup"><span data-stu-id="4ad72-121">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="4ad72-122">Abhängig davon, ob es sich bei der Methode um eine statische Methode oder eine Instanzmethode handelt und ob Sie über Argumente im tupelformular oder in der geschweifenden Form verfügt, ist die Syntax zum Deklarieren und Zuweisen des Delegaten etwas anders.</span><span class="sxs-lookup"><span data-stu-id="4ad72-122">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="4ad72-123">Der folgende Code zeigt einige der verschiedenen Möglichkeiten, mit Delegaten zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="4ad72-123">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="4ad72-124">Die Ausgabe des vorherigen Code Beispiels lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="4ad72-124">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="4ad72-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ad72-125">See also</span></span>

- [<span data-ttu-id="4ad72-126">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="4ad72-126">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="4ad72-127">Parameter und Argumente</span><span class="sxs-lookup"><span data-stu-id="4ad72-127">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="4ad72-128">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="4ad72-128">Events</span></span>](./members/events.md)
