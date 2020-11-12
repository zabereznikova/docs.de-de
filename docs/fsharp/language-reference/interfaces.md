---
title: Schnittstellen
description: 'Erfahren Sie, wie F #-Schnittstellen Sätze verwandter Member angeben, die von anderen Klassen implementiert werden.'
ms.date: 08/15/2020
ms.openlocfilehash: 0cef2932045dae401f5aa069107815543457ca4a
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557050"
---
# <a name="interfaces"></a><span data-ttu-id="4cff6-103">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4cff6-103">Interfaces</span></span>

<span data-ttu-id="4cff6-104">*Schnittstellen* geben Sätze verwandter Member an, die von anderen Klassen implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="4cff6-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="4cff6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4cff6-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="4cff6-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4cff6-106">Remarks</span></span>

<span data-ttu-id="4cff6-107">Schnittstellen Deklarationen ähneln Klassen Deklarationen, außer dass keine Member implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="4cff6-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="4cff6-108">Stattdessen sind alle Member abstrakt, wie durch das-Schlüsselwort angegeben `abstract` .</span><span class="sxs-lookup"><span data-stu-id="4cff6-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="4cff6-109">Sie stellen keinen Methoden Text für abstrakte Methoden bereit.</span><span class="sxs-lookup"><span data-stu-id="4cff6-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="4cff6-110">Sie können jedoch auch eine Standard Implementierung bereitstellen, indem Sie eine separate Definition des Members als Methode in Verbindung mit dem- `default` Schlüsselwort einschließen.</span><span class="sxs-lookup"><span data-stu-id="4cff6-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="4cff6-111">Dies entspricht dem Erstellen einer virtuellen Methode in einer Basisklasse in anderen .NET-Sprachen.</span><span class="sxs-lookup"><span data-stu-id="4cff6-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="4cff6-112">Eine solche virtuelle Methode kann in Klassen, die die-Schnittstelle implementieren, überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="4cff6-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="4cff6-113">Der Standard Zugriff für Schnittstellen ist `public` .</span><span class="sxs-lookup"><span data-stu-id="4cff6-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="4cff6-114">Sie können jedem Methoden Parameter optional einen Namen über die normale F #-Syntax übergeben:</span><span class="sxs-lookup"><span data-stu-id="4cff6-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="4cff6-115">Im obigen `ISprintable` Beispiel verfügt die- `Print` Methode über einen einzelnen Parameter vom Typ `string` mit dem Namen `format` .</span><span class="sxs-lookup"><span data-stu-id="4cff6-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="4cff6-116">Es gibt zwei Möglichkeiten zum Implementieren von Schnittstellen: mithilfe von Objekt Ausdrücken und mithilfe von Klassentypen.</span><span class="sxs-lookup"><span data-stu-id="4cff6-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="4cff6-117">In beiden Fällen stellt der Klassentyp oder der Objekt Ausdruck Methoden Körper für abstrakte Methoden der Schnittstelle bereit.</span><span class="sxs-lookup"><span data-stu-id="4cff6-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="4cff6-118">Implementierungen sind spezifisch für jeden Typ, der die-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="4cff6-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="4cff6-119">Daher können sich Schnittstellen Methoden für verschiedene Typen voneinander unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4cff6-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="4cff6-120">Die Schlüsselwörter `interface` und `end` , die den Anfang und das Ende der Definition markieren, sind optional, wenn Sie die Lightweight-Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cff6-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="4cff6-121">Wenn Sie diese Schlüsselwörter nicht verwenden, versucht der Compiler zu ableiten, ob der Typ eine Klasse oder eine Schnittstelle ist, indem die Konstrukte analysiert werden, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cff6-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="4cff6-122">Wenn Sie einen Member definieren oder eine andere Klassen Syntax verwenden, wird der Typ als Klasse interpretiert.</span><span class="sxs-lookup"><span data-stu-id="4cff6-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="4cff6-123">Der .net-Codierungsstil besteht darin, alle Schnittstellen mit einem Kapital zu beginnen `I` .</span><span class="sxs-lookup"><span data-stu-id="4cff6-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>

<span data-ttu-id="4cff6-124">Sie können mehrere Parameter auf zweierlei Weise angeben: F #-Style und. NET-Stil.</span><span class="sxs-lookup"><span data-stu-id="4cff6-124">You can specify multiple parameters in two ways: F#-style and .NET-style.</span></span> <span data-ttu-id="4cff6-125">Beide werden auf die gleiche Weise für .net-Consumer kompiliert, f #-Style erzwingt jedoch f #-Aufrufer, die Parameter Anwendung und in f # zu verwenden. Der Netzwerk Stil erzwingt F #-Aufrufer, eine Tupel-Argument Anwendung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cff6-125">Both will compile the same way for .NET consumers, but F#-style will force F# callers to use F#-style parameter application and .NET-style will force F# callers to use tupled argument application.</span></span>

```fsharp
type INumeric1 =
    abstract Add: x: int -> y: int -> int

type INumeric2 =
    abstract Add: x: int * y: int -> int
```

## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="4cff6-126">Implementieren von Schnittstellen mithilfe von Klassentypen</span><span class="sxs-lookup"><span data-stu-id="4cff6-126">Implementing Interfaces by Using Class Types</span></span>

<span data-ttu-id="4cff6-127">Sie können eine oder mehrere Schnittstellen in einem Klassentyp mithilfe des `interface` -Schlüssel Worts, des Namens der-Schnittstelle und des- `with` Schlüssel Worts implementieren, gefolgt von den Schnittstellen Element Definitionen, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4cff6-127">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="4cff6-128">Schnittstellen Implementierungen werden geerbt, sodass alle abgeleiteten Klassen Sie nicht neu implementieren müssen.</span><span class="sxs-lookup"><span data-stu-id="4cff6-128">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>

## <a name="calling-interface-methods"></a><span data-ttu-id="4cff6-129">Aufrufen von Schnittstellen Methoden</span><span class="sxs-lookup"><span data-stu-id="4cff6-129">Calling Interface Methods</span></span>

<span data-ttu-id="4cff6-130">Schnittstellen Methoden können nur über die-Schnittstelle aufgerufen werden, nicht über ein Objekt des Typs, der die-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="4cff6-130">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="4cff6-131">Folglich müssen Sie ggf. den- `:>` Operator oder den-Operator verwenden, um `upcast` Diese Methoden aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="4cff6-131">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="4cff6-132">Um die Schnittstellen Methode aufzurufen, wenn Sie ein Objekt vom Typ haben `SomeClass` , müssen Sie das Objekt in den Schnittstellentyp umwandeln, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4cff6-132">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="4cff6-133">Eine Alternative besteht darin, eine Methode für das Objekt zu deklarieren, das die Schnittstellen Methode upwandelt und aufruft, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4cff6-133">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="4cff6-134">Implementieren von Schnittstellen mithilfe von Objekt Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="4cff6-134">Implementing Interfaces by Using Object Expressions</span></span>

<span data-ttu-id="4cff6-135">Objekt Ausdrücke bieten eine kurze Möglichkeit, eine Schnittstelle zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="4cff6-135">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="4cff6-136">Sie sind nützlich, wenn Sie keinen benannten Typ erstellen müssen und nur ein Objekt, das die Schnittstellen Methoden unterstützt, ohne zusätzliche Methoden.</span><span class="sxs-lookup"><span data-stu-id="4cff6-136">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="4cff6-137">Ein Objekt Ausdruck wird im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4cff6-137">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a><span data-ttu-id="4cff6-138">Schnittstellenvererbung</span><span class="sxs-lookup"><span data-stu-id="4cff6-138">Interface Inheritance</span></span>

<span data-ttu-id="4cff6-139">Schnittstellen können von einer oder mehreren Basis Schnittstellen erben.</span><span class="sxs-lookup"><span data-stu-id="4cff6-139">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="implementing-interfaces-with-default-implementations"></a><span data-ttu-id="4cff6-140">Implementieren von Schnittstellen mit Standard Implementierungen</span><span class="sxs-lookup"><span data-stu-id="4cff6-140">Implementing interfaces with default implementations</span></span>

<span data-ttu-id="4cff6-141">C# unterstützt das Definieren von Schnittstellen mit Standard Implementierungen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4cff6-141">C# supports defining interfaces with default implementations, like so:</span></span>

```csharp
using System;

namespace CSharp
{
    public interface MyDim
    {
        public int Z => 0;
    }
}
```

<span data-ttu-id="4cff6-142">Diese können direkt von F # genutzt werden:</span><span class="sxs-lookup"><span data-stu-id="4cff6-142">These are directly consumable from F#:</span></span>

```fsharp
open CSharp

// You can implement the interface via a class
type MyType() =
    member _.M() = ()

    interface MyDim

let md = MyType() :> MyDim
printfn $"DIM from C#: %d{md.Z}"

// You can also implement it via an object expression
let md' = { new MyDim }
printfn $"DIM from C# but via Object Expression: %d{md'.Z}"
```

<span data-ttu-id="4cff6-143">Sie können eine Standard Implementierung mit überschreiben, z. b. überschreiben `override` eines beliebigen virtuellen Members.</span><span class="sxs-lookup"><span data-stu-id="4cff6-143">You can override a default implementation with `override`, like overriding any virtual member.</span></span>

<span data-ttu-id="4cff6-144">Alle Member in einer Schnittstelle, die keine Standard Implementierung haben, müssen weiterhin explizit implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="4cff6-144">Any members in an interface that do not have a default implementation must still be explicitly implemented.</span></span>

## <a name="implementing-the-same-interface-at-different-generic-instantiations"></a><span data-ttu-id="4cff6-145">Implementieren derselben Schnittstelle bei unterschiedlichen generischen Instanziierungen</span><span class="sxs-lookup"><span data-stu-id="4cff6-145">Implementing the same interface at different generic instantiations</span></span>

<span data-ttu-id="4cff6-146">F # unterstützt die Implementierung derselben Schnittstelle in unterschiedlichen generischen Instanziierungen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4cff6-146">F# supports implementing the same interface at different generic instantiations like so:</span></span>

```fsharp
type IA<'T> =
    abstract member Get : unit -> 'T

type MyClass() =
    interface IA<int> with
        member x.Get() = 1
    interface IA<string> with
        member x.Get() = "hello"

let mc = MyClass()
let iaInt = mc :> IA<int>
let iaString = mc :> IA<string>

iaInt.Get() // 1
iaString.Get() // "hello"
```

## <a name="see-also"></a><span data-ttu-id="4cff6-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4cff6-147">See also</span></span>

- [<span data-ttu-id="4cff6-148">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="4cff6-148">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="4cff6-149">Objektausdrücke</span><span class="sxs-lookup"><span data-stu-id="4cff6-149">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="4cff6-150">Klassen</span><span class="sxs-lookup"><span data-stu-id="4cff6-150">Classes</span></span>](classes.md)
