---
title: Schnittstellen (F#)
description: Erfahren Sie, wie Schnittstellen f# Sätze von verwandten Elementen angeben, die anderen Klassen implementieren.
ms.date: 05/16/2016
ms.openlocfilehash: 54ae8a2840ce26814be25f08c3ed02e12df6b7c0
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2018
---
# <a name="interfaces"></a><span data-ttu-id="a0315-103">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a0315-103">Interfaces</span></span>

<span data-ttu-id="a0315-104">*Schnittstellen* geben Sätze von verwandten Elementen, die anderen Klassen implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="a0315-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="a0315-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0315-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="a0315-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0315-106">Remarks</span></span>
<span data-ttu-id="a0315-107">Schnittstellendeklarationen ähneln Klassendeklarationen, mit dem Unterschied, dass keine Member implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="a0315-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="a0315-108">Stattdessen sind alle Member abstrakt, wie durch das Schlüsselwort angegeben `abstract`.</span><span class="sxs-lookup"><span data-stu-id="a0315-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="a0315-109">Sie bieten keine keinen Methodentext für abstrakte Methoden.</span><span class="sxs-lookup"><span data-stu-id="a0315-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="a0315-110">Sie können jedoch eine standardmäßige Implementierung bereitstellen, indem Sie auch eine separate Definition des Members als Methode zusammen mit der `default` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="a0315-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="a0315-111">Auf diese Weise wird die gleiche Funktion wie eine virtuelle Methode in einer Basisklasse in anderen .NET-Sprachen erstellen.</span><span class="sxs-lookup"><span data-stu-id="a0315-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="a0315-112">In Klassen, die die Schnittstelle implementieren, kann solche eine virtuelle Methode überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="a0315-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="a0315-113">Der Standardzugriff für Schnittstellen ist `public`.</span><span class="sxs-lookup"><span data-stu-id="a0315-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="a0315-114">Sie können jeden Methodenparameter mit normalen F#-Syntax einen Namen geben:</span><span class="sxs-lookup"><span data-stu-id="a0315-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="a0315-115">In den oben genannten `ISprintable` beispielsweise die `Print` Methode verfügt über einen einzelnen Parameter des Typs `string` mit dem Namen `format`.</span><span class="sxs-lookup"><span data-stu-id="a0315-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="a0315-116">Es gibt zwei Möglichkeiten, um Schnittstellen zu implementieren: mit Objektausdrücken und mithilfe von Klassentypen.</span><span class="sxs-lookup"><span data-stu-id="a0315-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="a0315-117">In beiden Fällen enthält die Klasse Typs oder der Objektinstanz Ausdruck Methodentexte für abstrakte Methoden der Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a0315-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="a0315-118">Implementierungen sind spezifisch für jeden Typ, der die Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="a0315-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="a0315-119">Aus diesem Grund können Schnittstellenmethoden für verschiedene Typen voneinander abweichen.</span><span class="sxs-lookup"><span data-stu-id="a0315-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="a0315-120">Die Schlüsselwörter `interface` und `end`, die den Beginn und Ende von der Definition kennzeichnen, sind optional, wenn Sie einfachen Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="a0315-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="a0315-121">Wenn Sie diese Schlüsselwörter nicht verwenden, versucht der Compiler anweisen abzuleiten, ob der Typ ist eine Klasse oder eine Schnittstelle, durch die Analyse der Konstrukte, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="a0315-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="a0315-122">Wenn Sie ein Element definieren oder andere Klassensyntax verwenden, wird der Typ als Klasse interpretiert.</span><span class="sxs-lookup"><span data-stu-id="a0315-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="a0315-123">.NET Stil Codierung ist auf allen Schnittstellen mit einem Großbuchstaben beginnen `I`.</span><span class="sxs-lookup"><span data-stu-id="a0315-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>


## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="a0315-124">Implementieren von Schnittstellen mit Klassentypen</span><span class="sxs-lookup"><span data-stu-id="a0315-124">Implementing Interfaces by Using Class Types</span></span>
<span data-ttu-id="a0315-125">Sie können eine oder mehrere Schnittstellen auf einen Klassentyp implementieren, mit der `interface` Schlüsselwort, den Namen der Schnittstelle, und die `with` Schlüsselwort, gefolgt von den Schnittstellenmemberdefinitionen, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0315-125">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="a0315-126">Schnittstellenimplementierungen werden geerbt, sodass keine abgeleiteten Klassen brauchen diese neu implementiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="a0315-126">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>


## <a name="calling-interface-methods"></a><span data-ttu-id="a0315-127">Schnittstellenmethoden aufrufen</span><span class="sxs-lookup"><span data-stu-id="a0315-127">Calling Interface Methods</span></span>
<span data-ttu-id="a0315-128">Schnittstellenmethoden können nur über die Benutzeroberfläche, nicht über ein Objekt des Typs aufgerufen werden, die die Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="a0315-128">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="a0315-129">Daher möglicherweise müssen Sie Typumwandlung nach oben, um den Schnittstellentyp mithilfe der `:>` Operator oder die `upcast` Operator, um diese Methoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a0315-129">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="a0315-130">Die Schnittstellenmethode aufgerufen werden, wenn Sie ein Objekt des Typs haben `SomeClass`, müssen Sie Upcast das Objekt, das den Schnittstellentyp, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0315-130">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="a0315-131">Eine Alternative besteht darin, eine Methode für das Objekt deklariert wird, wandelt und ruft die Schnittstellenmethode, wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a0315-131">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]
    
## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="a0315-132">Implementieren von Schnittstellen mit Objektausdrücken</span><span class="sxs-lookup"><span data-stu-id="a0315-132">Implementing Interfaces by Using Object Expressions</span></span>
<span data-ttu-id="a0315-133">Objektausdrücke bieten eine kurze Möglichkeit, eine Schnittstelle zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="a0315-133">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="a0315-134">Sie sind hilfreich, wenn Sie keinen benannten Typ erstellen, und Sie nur ein Objekt, das die Schnittstellenmethoden, ohne zusätzlichen Methoden unterstützt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a0315-134">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="a0315-135">Ein Objektausdrücke wird im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a0315-135">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]
    
## <a name="interface-inheritance"></a><span data-ttu-id="a0315-136">Schnittstellenvererbung</span><span class="sxs-lookup"><span data-stu-id="a0315-136">Interface Inheritance</span></span>
<span data-ttu-id="a0315-137">Schnittstellen können von einem oder mehreren Basisschnittstellen erben.</span><span class="sxs-lookup"><span data-stu-id="a0315-137">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]
    
## <a name="see-also"></a><span data-ttu-id="a0315-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0315-138">See Also</span></span>
[<span data-ttu-id="a0315-139">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="a0315-139">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="a0315-140">Objektausdrücke</span><span class="sxs-lookup"><span data-stu-id="a0315-140">Object Expressions</span></span>](object-expressions.md)

[<span data-ttu-id="a0315-141">Klassen</span><span class="sxs-lookup"><span data-stu-id="a0315-141">Classes</span></span>](classes.md)
