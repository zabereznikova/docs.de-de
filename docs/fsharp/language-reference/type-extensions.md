---
title: Typerweiterungen
description: Erfahren Sie, wie F# typerweiterungen können Sie einen zuvor definierten Objekttyp neue Member hinzufügen.
ms.date: 01/23/2019
ms.openlocfilehash: d52bc38850219a142ff4f5d840e418ea4bd50cca
ms.sourcegitcommit: d9a0071d0fd490ae006c816f78a563b9946e269a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2019
ms.locfileid: "55066154"
---
# <a name="type-extensions"></a><span data-ttu-id="28840-103">Erweiterungen des Typs</span><span class="sxs-lookup"><span data-stu-id="28840-103">Type extensions</span></span>

<span data-ttu-id="28840-104">Erweiterungen des Typs (so genannte _Erweiterungen_) sind eine Familie von Funktionen, die Sie einem zuvor definierten Objekttyp neue Member hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="28840-104">Type extensions (also called _augmentations_) are a family of features that let you add new members to a previously defined object type.</span></span> <span data-ttu-id="28840-105">Die drei Funktionen sind:</span><span class="sxs-lookup"><span data-stu-id="28840-105">The three features are:</span></span>

* <span data-ttu-id="28840-106">Systeminterne typerweiterungen</span><span class="sxs-lookup"><span data-stu-id="28840-106">Intrinsic type extensions</span></span>
* <span data-ttu-id="28840-107">Optionalen typerweiterungen</span><span class="sxs-lookup"><span data-stu-id="28840-107">Optional type extensions</span></span>
* <span data-ttu-id="28840-108">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="28840-108">Extension methods</span></span>

<span data-ttu-id="28840-109">Jede kann in verschiedenen Szenarien verwendet werden und verfügt über unterschiedliche Kompromisse.</span><span class="sxs-lookup"><span data-stu-id="28840-109">Each can be used in different scenarios and has different tradeoffs.</span></span>

## <a name="syntax"></a><span data-ttu-id="28840-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="28840-110">Syntax</span></span>

```fsharp
// Intrinsic and optional extensions
type typename with
    member self-identifier.member-name =
        body
    ...

// Extension methods
open System.Runtime.CompilerServices

[<Extension>]
type Extensions() =
    [static] member self-identifier.extension-name (ty: typename, [args]) =
        body
    ...
```

## <a name="intrinsic-type-extensions"></a><span data-ttu-id="28840-111">Systeminterne typerweiterungen</span><span class="sxs-lookup"><span data-stu-id="28840-111">Intrinsic type extensions</span></span>

<span data-ttu-id="28840-112">Eine systeminterne typerweiterung ist eine Erweiterung, die einen benutzerdefinierten Typ erweitert.</span><span class="sxs-lookup"><span data-stu-id="28840-112">An intrinsic type extension is a type extension that extends a user-defined type.</span></span>

<span data-ttu-id="28840-113">Systeminterne typerweiterungen müssen definiert werden, in der gleichen Datei **und** im gleichen Namespace oder Modul wie der Typ, die sie erweitern können.</span><span class="sxs-lookup"><span data-stu-id="28840-113">Intrinsic type extensions must be defined in the same file **and** in the same namespace or module as the type they're extending.</span></span> <span data-ttu-id="28840-114">Eine andere Definition führt dazu, ihnen wird [optionalen typerweiterungen](type-extensions.md#optional-type-extensions).</span><span class="sxs-lookup"><span data-stu-id="28840-114">Any other definition will result in them being [optional type extensions](type-extensions.md#optional-type-extensions).</span></span>

<span data-ttu-id="28840-115">Systeminterne typerweiterungen sind manchmal eine bessere Möglichkeit zur Funktionalität von der Typdeklaration zu trennen.</span><span class="sxs-lookup"><span data-stu-id="28840-115">Intrinsic type extensions are sometimes a cleaner way to separate functionality from the type declaration.</span></span> <span data-ttu-id="28840-116">Das folgende Beispiel zeigt, wie Sie eine systeminterne typerweiterung definieren:</span><span class="sxs-lookup"><span data-stu-id="28840-116">The following example shows how to define an intrinsic type extension:</span></span>

```fsharp
namespace Example

type Variant =
    | Num of int
    | Str of string
  
module Variant =
    let print v =
        match v with
        | Num n -> printf "Num %d" n
        | Str s -> printf "Str %s" s

// Add a member to Variant as an extension
type Variant with
    member x.Print() = Variant.print x
```

<span data-ttu-id="28840-117">Mithilfe einer Erweiterung des Typs, können Sie jede der folgenden trennen:</span><span class="sxs-lookup"><span data-stu-id="28840-117">Using a type extension allows you to separate each of the following:</span></span>

* <span data-ttu-id="28840-118">Die Deklaration einer `Variant` Typ</span><span class="sxs-lookup"><span data-stu-id="28840-118">The declaration of a `Variant` type</span></span>
* <span data-ttu-id="28840-119">Funktionen zum Drucken der `Variant` Klasse abhängig von der "Form"</span><span class="sxs-lookup"><span data-stu-id="28840-119">Functionality to print the `Variant` class depending on its "shape"</span></span>
* <span data-ttu-id="28840-120">Eine Möglichkeit zum Zugriff auf die Drucken Funktionen mit Objekt-Stil `.`-Notation</span><span class="sxs-lookup"><span data-stu-id="28840-120">A way to access the printing functionality with object-style `.`-notation</span></span>

<span data-ttu-id="28840-121">Dies ist eine Alternative zum Definieren von alles, was als ein Element auf `Variant`.</span><span class="sxs-lookup"><span data-stu-id="28840-121">This is an alternative to defining everything as a member on `Variant`.</span></span> <span data-ttu-id="28840-122">Obwohl dies nicht grundsätzlich besser ist, kann es eine übersichtlichere Darstellung der Funktionalität in einigen Situationen sein.</span><span class="sxs-lookup"><span data-stu-id="28840-122">Although it is not an inherently better approach, it can be a cleaner representation of functionality in some situations.</span></span>

<span data-ttu-id="28840-123">Systeminterne typerweiterungen werden als Member des Typs kompiliert, die Sie zu erweitern, die und für den Typ angezeigt wird, wenn der Typ durch Reflektion untersucht wird.</span><span class="sxs-lookup"><span data-stu-id="28840-123">Intrinsic type extensions are compiled as members of the type they augment, and appear on the type when the type is examined by reflection.</span></span>

## <a name="optional-type-extensions"></a><span data-ttu-id="28840-124">Optionalen typerweiterungen</span><span class="sxs-lookup"><span data-stu-id="28840-124">Optional type extensions</span></span>

<span data-ttu-id="28840-125">Eine optionale typerweiterung ist eine Erweiterung, die außerhalb der ursprünglichen Moduls, Namespace oder Assembly des Typs, der erweitert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="28840-125">An optional type extension is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span>

<span data-ttu-id="28840-126">Optionalen typerweiterungen eignen sich für die Erweiterung eines Typs, das Sie nicht selbst definiert haben.</span><span class="sxs-lookup"><span data-stu-id="28840-126">Optional type extensions are useful for extending a type that you have not defined yourself.</span></span> <span data-ttu-id="28840-127">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="28840-127">For example:</span></span>

```fsharp
module Extensions

open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for i in 1 .. n do
                    yield x
        }
```

<span data-ttu-id="28840-128">Sie können jetzt zugreifen `RepeatElements` , als ob es sich um ein Mitglied ist <xref:System.Collections.Generic.IEnumerable%601> , solange die `Extensions` Modul wird geöffnet, in den Bereich, den Sie gerade arbeiten.</span><span class="sxs-lookup"><span data-stu-id="28840-128">You can now access `RepeatElements` as if it's a member of <xref:System.Collections.Generic.IEnumerable%601> as long as the `Extensions` module is opened in the scope that you are working in.</span></span>

<span data-ttu-id="28840-129">Optionale Erweiterungen werden nicht für den erweiterten Typ, wenn durch Reflektion untersucht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="28840-129">Optional extensions do not appear on the extended type when examined by reflection.</span></span> <span data-ttu-id="28840-130">Optionale Erweiterungen müssen in Modulen sein, und sie sind nur im Gültigkeitsbereich, wenn das Modul, das die Erweiterung enthält, geöffnet ist, oder andernfalls befindet sich im Bereich.</span><span class="sxs-lookup"><span data-stu-id="28840-130">Optional extensions must be in modules, and they're only in scope when the module that contains the extension is open or is otherwise in scope.</span></span>

<span data-ttu-id="28840-131">Member optionaler Erweiterungen werden in statische Member kompiliert, für die die Objektinstanz implizit als erster Parameter übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="28840-131">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="28840-132">Verhalten sich jedoch, als befänden sie Instanzmember oder statische Member nach, wie sie deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="28840-132">However, they act as if they're instance members or static members according to how they're declared.</span></span>

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a><span data-ttu-id="28840-133">Generische Einschränkung der systeminterne und optionalen typerweiterungen</span><span class="sxs-lookup"><span data-stu-id="28840-133">Generic limitation of intrinsic and optional type extensions</span></span>

<span data-ttu-id="28840-134">Es ist möglich, eine Erweiterung für einen generischen Typ deklarieren, in dem die Variable vom Typ beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="28840-134">It's possible to declare a type extension on a generic type where the type variable is constrained.</span></span> <span data-ttu-id="28840-135">Die Anforderung ist, dass die Einschränkung der Erweiterung einer Deklaration für die Einschränkung des deklarierten Typs entspricht.</span><span class="sxs-lookup"><span data-stu-id="28840-135">The requirement is that the constraint of the extension declaration matches the constraint of the declared type.</span></span>

<span data-ttu-id="28840-136">Allerdings auch, wenn Einschränkungen zwischen einem deklarierten Typ und eine Erweiterung des Typs übereinstimmen, ist es möglich, für eine Einschränkung, die den Textkörper eines erweiterten Members abgeleitet werden, der andere Anforderungen für den Typparameter als den deklarierten Typ erzwingt.</span><span class="sxs-lookup"><span data-stu-id="28840-136">However, even when constraints are matched between a declared type and a type extension, it's possible for a constraint to be inferred by the body of an extended member that imposes a different requirement on the type parameter than the declared type.</span></span> <span data-ttu-id="28840-137">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="28840-137">For example:</span></span>

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

<span data-ttu-id="28840-138">Es gibt keine Möglichkeit, dieser Code funktioniert mit der eine optionale typerweiterung abzurufen:</span><span class="sxs-lookup"><span data-stu-id="28840-138">There is no way to get this code to work with an optional type extension:</span></span>

* <span data-ttu-id="28840-139">Da ist, die `Sum` Member hat eine andere Einschränkung auf `'T` (`static member get_Zero` und `static member (+)`) als durch die Erweiterung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="28840-139">As is, the `Sum` member has a different constraint on `'T` (`static member get_Zero` and `static member (+)`) than what the type extension defines.</span></span>
* <span data-ttu-id="28840-140">Ändern die Erweiterung für die gleiche Einschränkung wie `Sum` entspricht die definierte Einschränkung nicht mehr auf `IEnumerable<'T>`.</span><span class="sxs-lookup"><span data-stu-id="28840-140">Modifying the type extension to have the same constraint as `Sum` will no longer match the defined constraint on `IEnumerable<'T>`.</span></span>
* <span data-ttu-id="28840-141">Ändern der `member this.Sum` zu `member inline this.Sum` gibt einen Fehler, dass die typeinschränkungen nicht übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="28840-141">Changing `member this.Sum` to `member inline this.Sum` will give an error that type constraints are mismatched.</span></span>

<span data-ttu-id="28840-142">Erwünscht sind statische Methoden, die "im Bereich" float"und können angezeigt werden, als ob sie einen Typ erweitern können.</span><span class="sxs-lookup"><span data-stu-id="28840-142">What is desired are static methods that "float in space" and can be presented as if they're extending a type.</span></span> <span data-ttu-id="28840-143">Dies ist, in denen Erweiterungsmethoden bereit, die erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="28840-143">This is where extension methods become necessary.</span></span>

## <a name="extension-methods"></a><span data-ttu-id="28840-144">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="28840-144">Extension methods</span></span>

<span data-ttu-id="28840-145">Schließlich können Erweiterungsmethoden (manchmal als "Erweiterungsmember des C#-Stil" bezeichnet) in F# als statische Membermethode in einer Klasse deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="28840-145">Finally, extension methods (sometimes called "C# style extension members") can be declared in F# as a static member method on a class.</span></span>

<span data-ttu-id="28840-146">Erweiterungsmethoden sind nützlich für, wenn Sie Erweiterungen für einen generischen Typ definieren, die die Variable vom Typ eingeschränkt werden möchten.</span><span class="sxs-lookup"><span data-stu-id="28840-146">Extension methods are useful for when you wish to define extensions on a generic type that will constrain the type variable.</span></span> <span data-ttu-id="28840-147">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="28840-147">For example:</span></span>

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions() =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="28840-148">Wenn verwendet, wird dieser Code machen es so aussieht, als ob `Sum` definiert ist, auf <xref:System.Collections.Generic.IEnumerable%601>, solange `Extensions` geöffnet wurde oder befindet sich im Bereich.</span><span class="sxs-lookup"><span data-stu-id="28840-148">When used, this code will make it appear as if `Sum` is defined on <xref:System.Collections.Generic.IEnumerable%601>, so long as `Extensions` has been opened or is in scope.</span></span>

## <a name="other-remarks"></a><span data-ttu-id="28840-149">Andere Hinweise</span><span class="sxs-lookup"><span data-stu-id="28840-149">Other remarks</span></span>

<span data-ttu-id="28840-150">Erweiterungen des Typs haben auch die folgenden Attribute:</span><span class="sxs-lookup"><span data-stu-id="28840-150">Type extensions also have the following attributes:</span></span>

* <span data-ttu-id="28840-151">Jeder Typ, der zugegriffen werden kann, kann erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="28840-151">Any type that can be accessed can be extended.</span></span>
* <span data-ttu-id="28840-152">Systeminterne und optionalen typerweiterungen können definieren, _alle_ Elementtyp, nicht nur Methoden.</span><span class="sxs-lookup"><span data-stu-id="28840-152">Intrinsic and optional type extensions can define _any_ member type, not just methods.</span></span> <span data-ttu-id="28840-153">Daher sind Erweiterungseigenschaften auch möglich, z. B.</span><span class="sxs-lookup"><span data-stu-id="28840-153">So extension properties are also possible, for example.</span></span>
* <span data-ttu-id="28840-154">Die `self-identifier` -Tokens in der [Syntax](type-extensions.md#syntax) stellt die Instanz des Typs aufgerufen wird, wie bei gewöhnlichen Membern.</span><span class="sxs-lookup"><span data-stu-id="28840-154">The `self-identifier` token in the [syntax](type-extensions.md#syntax) represents the instance of the type being invoked, just like ordinary members.</span></span>
* <span data-ttu-id="28840-155">Erweiterte Mitglieder können statisch sein oder Instanzmember.</span><span class="sxs-lookup"><span data-stu-id="28840-155">Extended members can be static or instance members.</span></span>
* <span data-ttu-id="28840-156">Variablen für eine Erweiterung des Typs müssen es sich um die Einschränkungen des deklarierten Typs übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="28840-156">Type variables on a type extension must match the constraints of the declared type.</span></span>

<span data-ttu-id="28840-157">Die folgenden Einschränkungen gelten auch für Erweiterungen des Typs:</span><span class="sxs-lookup"><span data-stu-id="28840-157">The following limitations also exist for type extensions:</span></span>

* <span data-ttu-id="28840-158">Erweiterungen des Typs unterstützen keine virtuelle oder abstrakte Methoden.</span><span class="sxs-lookup"><span data-stu-id="28840-158">Type extensions do not support virtual or abstract methods.</span></span>
* <span data-ttu-id="28840-159">Erweiterungen des Typs unterstützen keine Methoden zum Überschreiben als Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="28840-159">Type extensions do not support override methods as augmentations.</span></span>
* <span data-ttu-id="28840-160">Erweiterungen des Typs unterstützen keine [Statisch aufgelöste Typparameter](generics/statically-resolved-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="28840-160">Type extensions do not support [Statically Resolved Type Parameters](generics/statically-resolved-type-parameters.md).</span></span>
* <span data-ttu-id="28840-161">Optionale Erweiterungen des Typs unterstützen keine Konstruktoren als Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="28840-161">Optional Type extensions do not support constructors as augmentations.</span></span>
* <span data-ttu-id="28840-162">Erweiterungen des Typs können nicht definiert werden [typabkürzungen](type-abbreviations.md).</span><span class="sxs-lookup"><span data-stu-id="28840-162">Type extensions cannot be defined on [type abbreviations](type-abbreviations.md).</span></span>
* <span data-ttu-id="28840-163">Erweiterungen des Typs gelten nicht für `byref<'T>` (auch wenn sie deklariert werden können).</span><span class="sxs-lookup"><span data-stu-id="28840-163">Type extensions are not valid for `byref<'T>` (though they can be declared).</span></span>
* <span data-ttu-id="28840-164">Erweiterungen des Typs gelten nicht für Attribute (auch wenn sie deklariert werden können).</span><span class="sxs-lookup"><span data-stu-id="28840-164">Type extensions are not valid for attributes (though they can be declared).</span></span>
* <span data-ttu-id="28840-165">Sie können definieren, Erweiterungen, die andere Methoden, mit dem gleichen Namen zu überladen, aber F#-Compiler bevorzugt nicht-Erweiterungsmethoden gibt es ist ein Mehrdeutiger Aufruf.</span><span class="sxs-lookup"><span data-stu-id="28840-165">You can define extensions that overload other methods of the same name, but the F# compiler gives preference to non-extension methods if there is an ambiguous call.</span></span>

<span data-ttu-id="28840-166">Schließlich, wenn für einen Typ mehrere systeminterne typerweiterungen vorhanden ist, müssen alle Member eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="28840-166">Finally, if multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="28840-167">Bei optionalen Typerweiterungen können Member in unterschiedlichen Typerweiterungen, die auf den gleichen Typ erweitert werden, die gleichen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="28840-167">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="28840-168">Mehrdeutigkeitsfehler treten nur auf, wenn Clientcode zwei unterschiedliche Gültigkeitsbereiche öffnet, die die gleichen Membernamen definieren.</span><span class="sxs-lookup"><span data-stu-id="28840-168">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

## <a name="see-also"></a><span data-ttu-id="28840-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28840-169">See also</span></span>

- [<span data-ttu-id="28840-170">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="28840-170">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="28840-171">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="28840-171">Members</span></span>](members/index.md)
