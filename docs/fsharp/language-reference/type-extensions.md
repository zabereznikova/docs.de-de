---
title: Typerweiterungen (F#)
description: Erfahren Sie, wie f# typerweiterungen erlauben, sich, dass Sie einen zuvor definierten Objekttyp neue Member hinzufügen.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 3399778799fbf0f8eee56e332135656150918a60
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="type-extensions"></a><span data-ttu-id="fb73f-103">Typerweiterungen</span><span class="sxs-lookup"><span data-stu-id="fb73f-103">Type Extensions</span></span>

<span data-ttu-id="fb73f-104">Mithilfe von Typerweiterungen können Sie einem zuvor definierten Objekttyp neue Member hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fb73f-104">Type extensions let you add new members to a previously defined object type.</span></span>

## <a name="syntax"></a><span data-ttu-id="fb73f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb73f-105">Syntax</span></span>

```fsharp
// Intrinsic extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]

// Optional extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]
```

## <a name="remarks"></a><span data-ttu-id="fb73f-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fb73f-106">Remarks</span></span>
<span data-ttu-id="fb73f-107">Es gibt zwei Formen von Typerweiterungen, deren Syntax und Verhalten geringfügig voneinander abweichen.</span><span class="sxs-lookup"><span data-stu-id="fb73f-107">There are two forms of type extensions that have slightly different syntax and behavior.</span></span> <span data-ttu-id="fb73f-108">Ein *systeminterne Erweiterung* ist eine Erweiterung, die im gleichen Namespace oder Modul, in der gleichen Quelldatei und in der gleichen Assembly (DLL oder ausführbare Datei) angezeigt wird wie der Typ, der erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="fb73f-108">An *intrinsic extension* is an extension that appears in the same namespace or module, in the same source file, and in the same assembly (DLL or executable file) as the type being extended.</span></span> <span data-ttu-id="fb73f-109">Ein *optionale Erweiterung* ist eine Erweiterung, die außerhalb der ursprünglichen Moduls, Namespace oder Assembly des Typs, der zu vergrößernden angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fb73f-109">An *optional extension* is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span> <span data-ttu-id="fb73f-110">Systeminterne Erweiterungen werden für einen Typ angezeigt, wenn der Typ durch Reflektion untersucht wird, nicht jedoch optionale Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="fb73f-110">Intrinsic extensions appear on the type when the type is examined by reflection, but optional extensions do not.</span></span> <span data-ttu-id="fb73f-111">Optionale Erweiterungen müssen in Modulen enthalten sein, und sie befinden sich nur im Gültigkeitsbereich, wenn das Modul, das die Erweiterung enthält, geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="fb73f-111">Optional extensions must be in modules, and they are only in scope when the module that contains the extension is open.</span></span>

<span data-ttu-id="fb73f-112">In der vorherigen Syntax *Typename* stellt den Typ, der erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="fb73f-112">In the previous syntax, *typename* represents the type that is being extended.</span></span> <span data-ttu-id="fb73f-113">Jeder Typ, auf den zugegriffen werden kann, ist erweiterbar, jedoch muss der Typname ein tatsächlicher Typname sein, keine Typabkürzung.</span><span class="sxs-lookup"><span data-stu-id="fb73f-113">Any type that can be accessed can be extended, but the type name must be an actual type name, not a type abbreviation.</span></span> <span data-ttu-id="fb73f-114">Sie können in einer Typerweiterung mehrere Member definieren.</span><span class="sxs-lookup"><span data-stu-id="fb73f-114">You can define multiple members in one type extension.</span></span> <span data-ttu-id="fb73f-115">Die *Selbstbezeichner* stellt die Instanz des Objekts aufgerufen wird, wie bei gewöhnlichen Membern.</span><span class="sxs-lookup"><span data-stu-id="fb73f-115">The *self-identifier* represents the instance of the object being invoked, just as in ordinary members.</span></span>

<span data-ttu-id="fb73f-116">Das `end`-Schlüsselwort ist in einfacher Syntax optional.</span><span class="sxs-lookup"><span data-stu-id="fb73f-116">The `end` keyword is optional in lightweight syntax.</span></span>

<span data-ttu-id="fb73f-117">In Typerweiterungen definierte Member können genau wie andere Member eines Klassentyps verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb73f-117">Members defined in type extensions can be used just like other members on a class type.</span></span> <span data-ttu-id="fb73f-118">Wie andere Member können sie statische Member oder Instanzmember sein.</span><span class="sxs-lookup"><span data-stu-id="fb73f-118">Like other members, they can be static or instance members.</span></span> <span data-ttu-id="fb73f-119">Diese Methoden werden auch bezeichnet als *Erweiterungsmethoden*; Eigenschaften werden als bezeichnet *Erweiterungseigenschaften*und so weiter.</span><span class="sxs-lookup"><span data-stu-id="fb73f-119">These methods are also known as *extension methods*; properties are known as *extension properties*, and so on.</span></span> <span data-ttu-id="fb73f-120">Member optionaler Erweiterungen werden in statische Member kompiliert, für die die Objektinstanz implizit als erster Parameter übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="fb73f-120">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="fb73f-121">Sie verhalten sich jedoch so, als ob sie Instanzmember oder statische Member wären, entsprechend der Art ihrer Deklarierung.</span><span class="sxs-lookup"><span data-stu-id="fb73f-121">However, they act as if they were instance members or static members according to how they are declared.</span></span> <span data-ttu-id="fb73f-122">Member impliziter Erweiterungen werden als Member des Typs eingeschlossen, und sie können ohne Einschränkung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb73f-122">Implicit extension members are included as members of the type and can be used without restriction.</span></span>

<span data-ttu-id="fb73f-123">Erweiterungsmethoden dürfen keine virtuellen oder abstrakten Methoden sein.</span><span class="sxs-lookup"><span data-stu-id="fb73f-123">Extension methods cannot be virtual or abstract methods.</span></span> <span data-ttu-id="fb73f-124">Sie können andere Methoden des gleichen Namens überladen, aber der Compiler bevorzugt im Fall eines mehrdeutigen Aufrufs Nicht-Erweiterungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="fb73f-124">They can overload other methods of the same name, but the compiler gives preference to non-extension methods in the case of an ambiguous call.</span></span>

<span data-ttu-id="fb73f-125">Wenn für einen Typ mehrere systeminterne Typerweiterungen vorhanden sind, müssen alle Member eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="fb73f-125">If multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="fb73f-126">Bei optionalen Typerweiterungen können Member in unterschiedlichen Typerweiterungen, die auf den gleichen Typ erweitert werden, die gleichen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="fb73f-126">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="fb73f-127">Mehrdeutigkeitsfehler treten nur auf, wenn Clientcode zwei unterschiedliche Gültigkeitsbereiche öffnet, die die gleichen Membernamen definieren.</span><span class="sxs-lookup"><span data-stu-id="fb73f-127">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

<span data-ttu-id="fb73f-128">Im folgenden Beispiel verfügt ein Typ in einem Modul über eine systeminterne Typerweiterung.</span><span class="sxs-lookup"><span data-stu-id="fb73f-128">In the following example, a type in a module has an intrinsic type extension.</span></span> <span data-ttu-id="fb73f-129">Für Clientcode außerhalb des Moduls wird die Typerweiterung in jeder Hinsicht als regulärer Member des Typs dargestellt.</span><span class="sxs-lookup"><span data-stu-id="fb73f-129">To client code outside the module, the type extension appears as a regular member of the type in all respects.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3701.fs)]

<span data-ttu-id="fb73f-130">Sie können mithilfe von systeminternen Typerweiterungen die Definition eines Typs in Abschnitte aufteilen.</span><span class="sxs-lookup"><span data-stu-id="fb73f-130">You can use intrinsic type extensions to separate the definition of a type into sections.</span></span> <span data-ttu-id="fb73f-131">Dies kann beim Verwalten umfangreicher Typdefinitionen hilfreich sein, um beispielsweise vom Compiler generierten Code und verfassten Code zu trennen oder um von verschiedenen Personen erstellten Code oder unterschiedlichen Funktionen zugeordneten Code in Gruppen zusammenzufassen.</span><span class="sxs-lookup"><span data-stu-id="fb73f-131">This can be useful in managing large type definitions, for example, to keep compiler-generated code and authored code separate or to group together code created by different people or associated with different functionality.</span></span>

<span data-ttu-id="fb73f-132">Im folgenden Beispiel erweitert eine optionale Typerweiterung den `System.Int32`-Typ mit der Erweiterungsmethode `FromString`, die den statischen Member `Parse` aufruft.</span><span class="sxs-lookup"><span data-stu-id="fb73f-132">In the following example, an optional type extension extends the `System.Int32` type with an extension method `FromString` that calls the static member `Parse`.</span></span> <span data-ttu-id="fb73f-133">Die `testFromString`-Methode veranschaulicht, dass der neue Member wie ein beliebiger Instanzmember aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fb73f-133">The `testFromString` method demonstrates that the new member is called just like any instance member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3702.fs)]

<span data-ttu-id="fb73f-134">Der neue Instanzmember wird in IntelliSense wie eine beliebige andere Methode des `Int32`-Typs angezeigt, jedoch nur, wenn das Modul, das die Erweiterung enthält, geöffnet ist oder die Erweiterung aus einem anderen Grund im Gültigkeitsbereich ist.</span><span class="sxs-lookup"><span data-stu-id="fb73f-134">The new instance member will appear like any other method of the `Int32` type in IntelliSense, but only when the module that contains the extension is open or otherwise in scope.</span></span>

## <a name="generic-extension-methods"></a><span data-ttu-id="fb73f-135">Generische Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="fb73f-135">Generic Extension Methods</span></span>
<span data-ttu-id="fb73f-136">Vor f# 3.1 unterstützte wurde im f#-Compiler unterstützt der Verwendung von c#-formaterweiterungsmethoden mit einer Variablen des generischen Typs, Arraytyps, Tupeltyps oder eines f#-Funktionstyps als "diesem" Parameter.</span><span class="sxs-lookup"><span data-stu-id="fb73f-136">Before F# 3.1, the F# compiler didn't support the use of C#-style extension methods with a generic type variable, array type, tuple type, or an F# function type as the "this" parameter.</span></span> <span data-ttu-id="fb73f-137">F# 3.1 unterstützt die Verwendung dieser Erweiterungsmember.</span><span class="sxs-lookup"><span data-stu-id="fb73f-137">F# 3.1 supports the use of these extension members.</span></span>

<span data-ttu-id="fb73f-138">Beispielsweise in F# 3.1-Code können Sie Erweiterungsmethoden mit Signaturen verwenden, die der folgenden Syntax in C# ähneln:</span><span class="sxs-lookup"><span data-stu-id="fb73f-138">For example, in F# 3.1 code, you can use extension methods with signatures that resemble the following syntax in C#:</span></span>

```csharp
static member Method<T>(this T input, T other)
```

<span data-ttu-id="fb73f-139">Dieser Ansatz ist insbesondere dann sinnvoll, wenn der generische Typparameter eingeschränkt wird.</span><span class="sxs-lookup"><span data-stu-id="fb73f-139">This approach is particularly useful when the generic type parameter is constrained.</span></span> <span data-ttu-id="fb73f-140">Darüber hinaus können Sie Erweiterungsmember nun so in F#-Code deklarieren und einen zusätzlichen, semantisch umfangreichen Satz von Erweiterungsmethoden definieren.</span><span class="sxs-lookup"><span data-stu-id="fb73f-140">Further, you can now declare extension members like this in F# code and define an additional, semantically rich set of extension methods.</span></span> <span data-ttu-id="fb73f-141">In F# definieren Sie normalerweise Erweiterungsmember, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fb73f-141">In F#, you usually define extension members as the following example shows:</span></span>

```fsharp
open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq { for x in xs do for i in 1 .. n do yield x }
```

<span data-ttu-id="fb73f-142">Für einen generischen Typ ist die Typvariable möglicherweise nicht beschränkt.</span><span class="sxs-lookup"><span data-stu-id="fb73f-142">However, for a generic type, the type variable may not be constrained.</span></span> <span data-ttu-id="fb73f-143">Sie können einen C#-Formaterweiterungsmember in F# deklarieren, um diese Einschränkung zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="fb73f-143">You can now declare a C#-style extension member in F# to work around this limitation.</span></span> <span data-ttu-id="fb73f-144">Wenn Sie diese Art der Deklaration mit der Inlinefunktion von F# kombinieren, können Sie generische Algorithmen als Erweiterungsmember darstellen.</span><span class="sxs-lookup"><span data-stu-id="fb73f-144">When you combine this kind of declaration with the inline feature of F#, you can present generic algorithms as extension members.</span></span>

<span data-ttu-id="fb73f-145">Betrachten Sie hierzu die folgende Deklaration:</span><span class="sxs-lookup"><span data-stu-id="fb73f-145">Consider the following declaration:</span></span>

```fsharp
[<Extension>]
type ExtraCSharpStyleExtensionMethodsInFSharp () =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="fb73f-146">Mit dieser Deklaration können Sie Code schreiben, der dem folgenden Beispiel ähnelt.</span><span class="sxs-lookup"><span data-stu-id="fb73f-146">By using this declaration, you can write code that resembles the following sample.</span></span>

```fsharp
let listOfIntegers = [ 1 .. 100 ]
let listOfBigIntegers = [ 1I to 100I ]
let sum1 = listOfIntegers.Sum()
let sum2 = listOfBigIntegers.Sum()
```

<span data-ttu-id="fb73f-147">In diesem Code wird der gleiche generische arithmetische Code in Listen mit zwei Typen ohne Überladung angewendet, indem ein einzelner Erweiterungsmember definiert wird.</span><span class="sxs-lookup"><span data-stu-id="fb73f-147">In this code, the same generic arithmetic code is applied to lists of two types without overloading, by defining a single extension member.</span></span>


## <a name="see-also"></a><span data-ttu-id="fb73f-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb73f-148">See Also</span></span>
[<span data-ttu-id="fb73f-149">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="fb73f-149">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="fb73f-150">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="fb73f-150">Members</span></span>](members/index.md)
