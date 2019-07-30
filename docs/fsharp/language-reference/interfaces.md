---
title: Schnittstellen
description: Erfahren Sie F# , wie Schnittstellen Sätze verwandter Member angeben, die von anderen Klassen implementiert werden.
ms.date: 05/16/2016
ms.openlocfilehash: 8f054a668ad0fbc2453a45883e8052471280eca3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627648"
---
# <a name="interfaces"></a><span data-ttu-id="d10dd-103">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d10dd-103">Interfaces</span></span>

<span data-ttu-id="d10dd-104">*Schnittstellen* geben Sätze verwandter Member an, die von anderen Klassen implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="d10dd-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="d10dd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d10dd-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="d10dd-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d10dd-106">Remarks</span></span>

<span data-ttu-id="d10dd-107">Schnittstellen Deklarationen ähneln Klassen Deklarationen, außer dass keine Member implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="d10dd-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="d10dd-108">Stattdessen sind alle Member abstrakt, wie durch das-Schlüsselwort `abstract`angegeben.</span><span class="sxs-lookup"><span data-stu-id="d10dd-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="d10dd-109">Sie stellen keinen Methoden Text für abstrakte Methoden bereit.</span><span class="sxs-lookup"><span data-stu-id="d10dd-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="d10dd-110">Sie können jedoch auch eine Standard Implementierung bereitstellen, indem Sie eine separate Definition des Members als Methode in Verbindung mit dem `default` -Schlüsselwort einschließen.</span><span class="sxs-lookup"><span data-stu-id="d10dd-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="d10dd-111">Dies entspricht dem Erstellen einer virtuellen Methode in einer Basisklasse in anderen .NET-Sprachen.</span><span class="sxs-lookup"><span data-stu-id="d10dd-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="d10dd-112">Eine solche virtuelle Methode kann in Klassen, die die-Schnittstelle implementieren, überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="d10dd-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="d10dd-113">Der Standard Zugriff für Schnittstellen `public`ist.</span><span class="sxs-lookup"><span data-stu-id="d10dd-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="d10dd-114">Optional können Sie jedem Methoden Parameter einen Namen über die normale F# Syntax übergeben:</span><span class="sxs-lookup"><span data-stu-id="d10dd-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="d10dd-115">Im obigen `ISprintable` Beispiel verfügt die `Print` -Methode über einen einzelnen Parameter vom Typ `string` mit dem Namen `format`.</span><span class="sxs-lookup"><span data-stu-id="d10dd-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="d10dd-116">Es gibt zwei Möglichkeiten zum Implementieren von Schnittstellen: mithilfe von Objekt Ausdrücken und mithilfe von Klassentypen.</span><span class="sxs-lookup"><span data-stu-id="d10dd-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="d10dd-117">In beiden Fällen stellt der Klassentyp oder der Objekt Ausdruck Methoden Körper für abstrakte Methoden der Schnittstelle bereit.</span><span class="sxs-lookup"><span data-stu-id="d10dd-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="d10dd-118">Implementierungen sind spezifisch für jeden Typ, der die-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="d10dd-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="d10dd-119">Daher können sich Schnittstellen Methoden für verschiedene Typen voneinander unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="d10dd-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="d10dd-120">Die Schlüssel `interface` Wörter `end`und, die den Anfang und das Ende der Definition markieren, sind optional, wenn Sie die Lightweight-Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="d10dd-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="d10dd-121">Wenn Sie diese Schlüsselwörter nicht verwenden, versucht der Compiler zu ableiten, ob der Typ eine Klasse oder eine Schnittstelle ist, indem die Konstrukte analysiert werden, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="d10dd-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="d10dd-122">Wenn Sie einen Member definieren oder eine andere Klassen Syntax verwenden, wird der Typ als Klasse interpretiert.</span><span class="sxs-lookup"><span data-stu-id="d10dd-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="d10dd-123">Der .net-Codierungsstil besteht darin, alle Schnittstellen `I`mit einem Kapital zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="d10dd-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>

## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="d10dd-124">Implementieren von Schnittstellen mithilfe von Klassentypen</span><span class="sxs-lookup"><span data-stu-id="d10dd-124">Implementing Interfaces by Using Class Types</span></span>

<span data-ttu-id="d10dd-125">Sie können eine oder mehrere Schnittstellen in einem Klassentyp mithilfe des `interface` -Schlüssel Worts, des Namens der-Schnittstelle `with` und des-Schlüssel Worts implementieren, gefolgt von den Schnittstellen Element Definitionen, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d10dd-125">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="d10dd-126">Schnittstellen Implementierungen werden geerbt, sodass alle abgeleiteten Klassen Sie nicht neu implementieren müssen.</span><span class="sxs-lookup"><span data-stu-id="d10dd-126">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>

## <a name="calling-interface-methods"></a><span data-ttu-id="d10dd-127">Aufrufen von Schnittstellen Methoden</span><span class="sxs-lookup"><span data-stu-id="d10dd-127">Calling Interface Methods</span></span>

<span data-ttu-id="d10dd-128">Schnittstellen Methoden können nur über die-Schnittstelle aufgerufen werden, nicht über ein Objekt des Typs, der die-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="d10dd-128">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="d10dd-129">Folglich müssen Sie ggf. den `:>` -Operator oder den `upcast` -Operator verwenden, um diese Methoden aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="d10dd-129">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="d10dd-130">Um die Schnittstellen Methode aufzurufen, wenn Sie ein Objekt vom `SomeClass`Typ haben, müssen Sie das Objekt in den Schnittstellentyp umwandeln, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d10dd-130">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="d10dd-131">Eine Alternative besteht darin, eine Methode für das Objekt zu deklarieren, das die Schnittstellen Methode upwandelt und aufruft, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d10dd-131">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="d10dd-132">Implementieren von Schnittstellen mithilfe von Objekt Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="d10dd-132">Implementing Interfaces by Using Object Expressions</span></span>

<span data-ttu-id="d10dd-133">Objekt Ausdrücke bieten eine kurze Möglichkeit, eine Schnittstelle zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="d10dd-133">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="d10dd-134">Sie sind nützlich, wenn Sie keinen benannten Typ erstellen müssen und nur ein Objekt, das die Schnittstellen Methoden unterstützt, ohne zusätzliche Methoden.</span><span class="sxs-lookup"><span data-stu-id="d10dd-134">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="d10dd-135">Ein Objekt Ausdruck wird im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d10dd-135">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a><span data-ttu-id="d10dd-136">Schnittstellenvererbung</span><span class="sxs-lookup"><span data-stu-id="d10dd-136">Interface Inheritance</span></span>

<span data-ttu-id="d10dd-137">Schnittstellen können von einer oder mehreren Basis Schnittstellen erben.</span><span class="sxs-lookup"><span data-stu-id="d10dd-137">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a><span data-ttu-id="d10dd-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d10dd-138">See also</span></span>

- [<span data-ttu-id="d10dd-139">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="d10dd-139">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="d10dd-140">Objektausdrücke</span><span class="sxs-lookup"><span data-stu-id="d10dd-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="d10dd-141">Klassen</span><span class="sxs-lookup"><span data-stu-id="d10dd-141">Classes</span></span>](classes.md)
