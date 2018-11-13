---
title: Schnittstellen (F#)
description: Erfahren Sie, wie F#-Schnittstellen für Gruppen von verwandten Elementen angeben, die anderen Klassen implementiert.
ms.date: 05/16/2016
ms.openlocfilehash: 6d7f8ee9ea17d2294933f88577c30a96975ae5d4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "47231439"
---
# <a name="interfaces"></a><span data-ttu-id="c3fc3-103">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c3fc3-103">Interfaces</span></span>

<span data-ttu-id="c3fc3-104">*Schnittstellen* angeben von Gruppen von verwandten Elementen, die anderen Klassen implementiert.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="c3fc3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3fc3-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="c3fc3-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c3fc3-106">Remarks</span></span>

<span data-ttu-id="c3fc3-107">Deklarationen von Schnittstellen entsprechen Klassendeklarationen keine Member implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="c3fc3-108">Stattdessen werden alle Member abstrakt, wie durch das Schlüsselwort `abstract`.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="c3fc3-109">Sie bieten keine Methodentext für abstrakte Methoden.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="c3fc3-110">Sie können jedoch eine standardmäßige Implementierung bereitstellen, dazu auch eine separate Definition des Members als Methode zusammen mit den `default` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="c3fc3-111">Auf diese Weise ist gleichbedeutend mit eine virtuelle Methode in einer Basisklasse in anderen .NET-Sprachen erstellen.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="c3fc3-112">In Klassen, die die Schnittstelle implementieren, kann solche eine virtuelle Methode überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="c3fc3-113">Der Standardzugriff für Schnittstellen ist `public`.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="c3fc3-114">Optional können jeden Methodenparameter Geben Sie einen Namen mit normalen F#-Syntax:</span><span class="sxs-lookup"><span data-stu-id="c3fc3-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="c3fc3-115">In der obigen `ISprintable` beispielsweise die `Print` Methode verfügt über einen einzelnen Parameter des Typs `string` mit dem Namen `format`.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="c3fc3-116">Es gibt zwei Möglichkeiten, um Schnittstellen zu implementieren: mithilfe von Object-Ausdrücke und mithilfe von Klassentypen.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="c3fc3-117">In beiden Fällen bietet der Klasse Typ oder ein Objekt Ausdruck Methodentext für abstrakte Methoden der Schnittstelle an.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="c3fc3-118">Implementierungen sind spezifisch für jeden Typ, der die Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="c3fc3-119">Aus diesem Grund können Schnittstellenmethoden auf verschiedene Arten voneinander abweichen.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="c3fc3-120">Die Schlüsselwörter `interface` und `end`, die Anfang und Ende der Definition kennzeichnen, sind optional, wenn Sie einfache Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="c3fc3-121">Wenn Sie diese Schlüsselwörter nicht verwenden, versucht der Compiler, um rückzufolgern, ob der Typ ist eine Klasse oder Schnittstelle, durch die Analyse der erstellt, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="c3fc3-122">Wenn Sie ein Element definieren oder andere Klassensyntax verwenden, wird der Typ als eine Klasse interpretiert.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="c3fc3-123">Das .NET codierstil begonnen werden soll alle Schnittstellen im wahrsten Sinne `I`.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>

## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="c3fc3-124">Implementieren von Schnittstellen mit Klassentypen</span><span class="sxs-lookup"><span data-stu-id="c3fc3-124">Implementing Interfaces by Using Class Types</span></span>

<span data-ttu-id="c3fc3-125">Sie können in einem Klassentyp eine oder mehrere Schnittstellen implementieren, mit der `interface` Schlüsselwort, den Namen der Schnittstelle und die `with` -Schlüsselwort, gefolgt von den Definitionen für Schnittstellen Member, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-125">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="c3fc3-126">Schnittstellenimplementierungen werden geerbt, sodass keine abgeleiteten Klassen nicht erneut implementieren, sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-126">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>

## <a name="calling-interface-methods"></a><span data-ttu-id="c3fc3-127">Aufrufen von Schnittstellenmethoden</span><span class="sxs-lookup"><span data-stu-id="c3fc3-127">Calling Interface Methods</span></span>

<span data-ttu-id="c3fc3-128">Schnittstellenmethoden können nur über die Schnittstelle, nicht über ein Objekt des Typs aufgerufen werden, die die Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-128">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="c3fc3-129">Daher möglicherweise müssen Sie Typumwandlung nach oben in den Schnittstellentyp mithilfe der `:>` Operator oder die `upcast` Operator, um diese Methoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-129">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="c3fc3-130">Die Schnittstellenmethode aufrufen, wenn Sie ein Objekt des Typs haben `SomeClass`, müssen Sie Typumwandlung nach oben das Objekt, das den Schnittstellentyp an, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-130">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="c3fc3-131">Eine Alternative besteht darin, eine Methode für das Objekt deklariert wird, werden und ruft die Schnittstellenmethode, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-131">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="c3fc3-132">Implementieren von Schnittstellen mit Objektausdrücken</span><span class="sxs-lookup"><span data-stu-id="c3fc3-132">Implementing Interfaces by Using Object Expressions</span></span>

<span data-ttu-id="c3fc3-133">Object-Ausdrücke bieten eine mühelose Möglichkeit, eine Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-133">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="c3fc3-134">Sie sind hilfreich, wenn Sie keinen benannten Typ erstellen, und sollen einfach nur ein Objekt, das die Schnittstellenmethoden, ohne zusätzlichen Methoden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-134">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="c3fc3-135">Ein Object-Ausdruck wird im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-135">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a><span data-ttu-id="c3fc3-136">Schnittstellenvererbung</span><span class="sxs-lookup"><span data-stu-id="c3fc3-136">Interface Inheritance</span></span>

<span data-ttu-id="c3fc3-137">Schnittstellen können von einem oder mehreren Basisschnittstellen erben.</span><span class="sxs-lookup"><span data-stu-id="c3fc3-137">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a><span data-ttu-id="c3fc3-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3fc3-138">See also</span></span>

- [<span data-ttu-id="c3fc3-139">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="c3fc3-139">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="c3fc3-140">Objektausdrücke</span><span class="sxs-lookup"><span data-stu-id="c3fc3-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="c3fc3-141">Klassen</span><span class="sxs-lookup"><span data-stu-id="c3fc3-141">Classes</span></span>](classes.md)
