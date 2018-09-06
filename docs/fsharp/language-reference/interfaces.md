---
title: Schnittstellen (F#)
description: Erfahren Sie, wie F#-Schnittstellen für Gruppen von verwandten Elementen angeben, die anderen Klassen implementiert.
ms.date: 05/16/2016
ms.openlocfilehash: 6d7f8ee9ea17d2294933f88577c30a96975ae5d4
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43802819"
---
# <a name="interfaces"></a><span data-ttu-id="b1b40-103">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b1b40-103">Interfaces</span></span>

<span data-ttu-id="b1b40-104">*Schnittstellen* angeben von Gruppen von verwandten Elementen, die anderen Klassen implementiert.</span><span class="sxs-lookup"><span data-stu-id="b1b40-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="b1b40-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1b40-105">Syntax</span></span>

```fsharp
// Interface declaration:
[ attributes ]
type [accessibility-modifier] interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a><span data-ttu-id="b1b40-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b1b40-106">Remarks</span></span>

<span data-ttu-id="b1b40-107">Deklarationen von Schnittstellen entsprechen Klassendeklarationen keine Member implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="b1b40-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="b1b40-108">Stattdessen werden alle Member abstrakt, wie durch das Schlüsselwort `abstract`.</span><span class="sxs-lookup"><span data-stu-id="b1b40-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="b1b40-109">Sie bieten keine Methodentext für abstrakte Methoden.</span><span class="sxs-lookup"><span data-stu-id="b1b40-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="b1b40-110">Sie können jedoch eine standardmäßige Implementierung bereitstellen, dazu auch eine separate Definition des Members als Methode zusammen mit den `default` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="b1b40-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="b1b40-111">Auf diese Weise ist gleichbedeutend mit eine virtuelle Methode in einer Basisklasse in anderen .NET-Sprachen erstellen.</span><span class="sxs-lookup"><span data-stu-id="b1b40-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="b1b40-112">In Klassen, die die Schnittstelle implementieren, kann solche eine virtuelle Methode überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="b1b40-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="b1b40-113">Der Standardzugriff für Schnittstellen ist `public`.</span><span class="sxs-lookup"><span data-stu-id="b1b40-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="b1b40-114">Optional können jeden Methodenparameter Geben Sie einen Namen mit normalen F#-Syntax:</span><span class="sxs-lookup"><span data-stu-id="b1b40-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="b1b40-115">In der obigen `ISprintable` beispielsweise die `Print` Methode verfügt über einen einzelnen Parameter des Typs `string` mit dem Namen `format`.</span><span class="sxs-lookup"><span data-stu-id="b1b40-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="b1b40-116">Es gibt zwei Möglichkeiten, um Schnittstellen zu implementieren: mithilfe von Object-Ausdrücke und mithilfe von Klassentypen.</span><span class="sxs-lookup"><span data-stu-id="b1b40-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="b1b40-117">In beiden Fällen bietet der Klasse Typ oder ein Objekt Ausdruck Methodentext für abstrakte Methoden der Schnittstelle an.</span><span class="sxs-lookup"><span data-stu-id="b1b40-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="b1b40-118">Implementierungen sind spezifisch für jeden Typ, der die Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="b1b40-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="b1b40-119">Aus diesem Grund können Schnittstellenmethoden auf verschiedene Arten voneinander abweichen.</span><span class="sxs-lookup"><span data-stu-id="b1b40-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="b1b40-120">Die Schlüsselwörter `interface` und `end`, die Anfang und Ende der Definition kennzeichnen, sind optional, wenn Sie einfache Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1b40-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="b1b40-121">Wenn Sie diese Schlüsselwörter nicht verwenden, versucht der Compiler, um rückzufolgern, ob der Typ ist eine Klasse oder Schnittstelle, durch die Analyse der erstellt, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1b40-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="b1b40-122">Wenn Sie ein Element definieren oder andere Klassensyntax verwenden, wird der Typ als eine Klasse interpretiert.</span><span class="sxs-lookup"><span data-stu-id="b1b40-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="b1b40-123">Das .NET codierstil begonnen werden soll alle Schnittstellen im wahrsten Sinne `I`.</span><span class="sxs-lookup"><span data-stu-id="b1b40-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>

## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="b1b40-124">Implementieren von Schnittstellen mit Klassentypen</span><span class="sxs-lookup"><span data-stu-id="b1b40-124">Implementing Interfaces by Using Class Types</span></span>

<span data-ttu-id="b1b40-125">Sie können in einem Klassentyp eine oder mehrere Schnittstellen implementieren, mit der `interface` Schlüsselwort, den Namen der Schnittstelle und die `with` -Schlüsselwort, gefolgt von den Definitionen für Schnittstellen Member, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b1b40-125">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="b1b40-126">Schnittstellenimplementierungen werden geerbt, sodass keine abgeleiteten Klassen nicht erneut implementieren, sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="b1b40-126">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>

## <a name="calling-interface-methods"></a><span data-ttu-id="b1b40-127">Aufrufen von Schnittstellenmethoden</span><span class="sxs-lookup"><span data-stu-id="b1b40-127">Calling Interface Methods</span></span>

<span data-ttu-id="b1b40-128">Schnittstellenmethoden können nur über die Schnittstelle, nicht über ein Objekt des Typs aufgerufen werden, die die Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="b1b40-128">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="b1b40-129">Daher möglicherweise müssen Sie Typumwandlung nach oben in den Schnittstellentyp mithilfe der `:>` Operator oder die `upcast` Operator, um diese Methoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b1b40-129">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="b1b40-130">Die Schnittstellenmethode aufrufen, wenn Sie ein Objekt des Typs haben `SomeClass`, müssen Sie Typumwandlung nach oben das Objekt, das den Schnittstellentyp an, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b1b40-130">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="b1b40-131">Eine Alternative besteht darin, eine Methode für das Objekt deklariert wird, werden und ruft die Schnittstellenmethode, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b1b40-131">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="b1b40-132">Implementieren von Schnittstellen mit Objektausdrücken</span><span class="sxs-lookup"><span data-stu-id="b1b40-132">Implementing Interfaces by Using Object Expressions</span></span>

<span data-ttu-id="b1b40-133">Object-Ausdrücke bieten eine mühelose Möglichkeit, eine Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="b1b40-133">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="b1b40-134">Sie sind hilfreich, wenn Sie keinen benannten Typ erstellen, und sollen einfach nur ein Objekt, das die Schnittstellenmethoden, ohne zusätzlichen Methoden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b1b40-134">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="b1b40-135">Ein Object-Ausdruck wird im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b1b40-135">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a><span data-ttu-id="b1b40-136">Schnittstellenvererbung</span><span class="sxs-lookup"><span data-stu-id="b1b40-136">Interface Inheritance</span></span>

<span data-ttu-id="b1b40-137">Schnittstellen können von einem oder mehreren Basisschnittstellen erben.</span><span class="sxs-lookup"><span data-stu-id="b1b40-137">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a><span data-ttu-id="b1b40-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1b40-138">See also</span></span>

- [<span data-ttu-id="b1b40-139">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="b1b40-139">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="b1b40-140">Objektausdrücke</span><span class="sxs-lookup"><span data-stu-id="b1b40-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="b1b40-141">Klassen</span><span class="sxs-lookup"><span data-stu-id="b1b40-141">Classes</span></span>](classes.md)
