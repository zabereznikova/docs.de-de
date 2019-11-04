---
title: Statisch aufgelöste Typparameter
description: Erfahren Sie, wie ein F# statisch aufgelöster Typparameter verwendet wird, der zur Kompilierzeit anstelle der Laufzeit durch einen tatsächlichen Typ ersetzt wird.
ms.date: 05/16/2016
ms.openlocfilehash: 017c18dd3caaa484ddc653557573f548e3224ca0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424999"
---
# <a name="statically-resolved-type-parameters"></a><span data-ttu-id="336e4-103">Statisch aufgelöste Typparameter</span><span class="sxs-lookup"><span data-stu-id="336e4-103">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="336e4-104">Ein *statisch aufgelöster Typparameter* ist ein Typparameter, der zur Kompilierzeit anstelle der Laufzeit durch einen tatsächlichen Typ ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="336e4-104">A *statically resolved type parameter* is a type parameter that is replaced with an actual type at compile time instead of at run time.</span></span> <span data-ttu-id="336e4-105">Ihnen wird ein Caretzeichen (^) vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="336e4-105">They are preceded by a caret (^) symbol.</span></span>

## <a name="syntax"></a><span data-ttu-id="336e4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="336e4-106">Syntax</span></span>

```fsharp
ˆtype-parameter
```

## <a name="remarks"></a><span data-ttu-id="336e4-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="336e4-107">Remarks</span></span>

<span data-ttu-id="336e4-108">In der Programmiersprache F# gibt es zwei unterschiedliche Arten von Typparametern.</span><span class="sxs-lookup"><span data-stu-id="336e4-108">In the F# language, there are two distinct kinds of type parameters.</span></span> <span data-ttu-id="336e4-109">Die erste Art ist der standardmäßige generische Typparameter.</span><span class="sxs-lookup"><span data-stu-id="336e4-109">The first kind is the standard generic type parameter.</span></span> <span data-ttu-id="336e4-110">Diese werden durch ein Apostroph (') angegeben, wie bei `'T` und `'U`.</span><span class="sxs-lookup"><span data-stu-id="336e4-110">These are indicated by an apostrophe ('), as in `'T` and `'U`.</span></span> <span data-ttu-id="336e4-111">Sie entsprechen generischen Typparametern in anderen .NET Framework-Sprachen.</span><span class="sxs-lookup"><span data-stu-id="336e4-111">They are equivalent to generic type parameters in other .NET Framework languages.</span></span> <span data-ttu-id="336e4-112">Die andere Art ist statisch aufgelöst und wird von einem Caretzeichensymbol, wie in `^T` und `^U`.</span><span class="sxs-lookup"><span data-stu-id="336e4-112">The other kind is statically resolved and is indicated by a caret symbol, as in `^T` and `^U`.</span></span>

<span data-ttu-id="336e4-113">Statisch aufgelöste Typparameter sind hauptsächlich in Verbindung mit Membereinschränkungen nützlich, die Ihnen die Angabe ermöglichen, dass ein Typargument zur Verwendung einen bestimmten Member oder mehrere Member aufweisen muss.</span><span class="sxs-lookup"><span data-stu-id="336e4-113">Statically resolved type parameters are primarily useful in conjunction with member constraints, which are constraints that allow you to specify that a type argument must have a particular member or members in order to be used.</span></span> <span data-ttu-id="336e4-114">Es gibt keine Möglichkeit, diese Art von Einschränkung mit einem regulären generischen Typparameter zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="336e4-114">There is no way to create this kind of constraint by using a regular generic type parameter.</span></span>

<span data-ttu-id="336e4-115">In der folgenden Tabelle werden die Ähnlichkeiten und die Unterschiede zwischen den beiden Arten von Typparametern zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="336e4-115">The following table summarizes the similarities and differences between the two kinds of type parameters.</span></span>

|<span data-ttu-id="336e4-116">Feature</span><span class="sxs-lookup"><span data-stu-id="336e4-116">Feature</span></span>|<span data-ttu-id="336e4-117">Generisch</span><span class="sxs-lookup"><span data-stu-id="336e4-117">Generic</span></span>|<span data-ttu-id="336e4-118">Statisch aufgelöst</span><span class="sxs-lookup"><span data-stu-id="336e4-118">Statically resolved</span></span>|
|-------|-------|-------------------|
|<span data-ttu-id="336e4-119">Syntax</span><span class="sxs-lookup"><span data-stu-id="336e4-119">Syntax</span></span>|<span data-ttu-id="336e4-120">`'T`, `'U`</span><span class="sxs-lookup"><span data-stu-id="336e4-120">`'T`, `'U`</span></span>|<span data-ttu-id="336e4-121">`^T`, `^U`</span><span class="sxs-lookup"><span data-stu-id="336e4-121">`^T`, `^U`</span></span>|
|<span data-ttu-id="336e4-122">Auflösungszeit</span><span class="sxs-lookup"><span data-stu-id="336e4-122">Resolution time</span></span>|<span data-ttu-id="336e4-123">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="336e4-123">Run time</span></span>|<span data-ttu-id="336e4-124">Kompilierungsfehler</span><span class="sxs-lookup"><span data-stu-id="336e4-124">Compile time</span></span>|
|<span data-ttu-id="336e4-125">Member-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="336e4-125">Member constraints</span></span>|<span data-ttu-id="336e4-126">Kann nicht mit Membereinschränkungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="336e4-126">Cannot be used with member constraints.</span></span>|<span data-ttu-id="336e4-127">Kann mit Membereinschränkungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="336e4-127">Can be used with member constraints.</span></span>|
|<span data-ttu-id="336e4-128">Codeerzeugung</span><span class="sxs-lookup"><span data-stu-id="336e4-128">Code generation</span></span>|<span data-ttu-id="336e4-129">Ein Typ (oder eine Methode) mit standardmäßigen generischen Typparametern führt zur Erstellung eines einzelnen generischen Typs oder einer Methode.</span><span class="sxs-lookup"><span data-stu-id="336e4-129">A type (or method) with standard generic type parameters results in the generation of a single generic type or method.</span></span>|<span data-ttu-id="336e4-130">Mehrere Instanziierungen von Typen und Methoden werden generiert, einer für jeden erforderlichen Typ.</span><span class="sxs-lookup"><span data-stu-id="336e4-130">Multiple instantiations of types and methods are generated, one for each type that is needed.</span></span>|
|<span data-ttu-id="336e4-131">Verwendung mit Typen</span><span class="sxs-lookup"><span data-stu-id="336e4-131">Use with types</span></span>|<span data-ttu-id="336e4-132">Kann mit Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="336e4-132">Can be used on types.</span></span>|<span data-ttu-id="336e4-133">Kann nicht mit Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="336e4-133">Cannot be used on types.</span></span>|
|<span data-ttu-id="336e4-134">Verwendung mit Inlinefunktionen</span><span class="sxs-lookup"><span data-stu-id="336e4-134">Use with inline functions</span></span>|<span data-ttu-id="336e4-135">Nein.</span><span class="sxs-lookup"><span data-stu-id="336e4-135">No.</span></span> <span data-ttu-id="336e4-136">Eine Inlinefunktion kann nicht mit einem standardmäßigen generischen Typparameter parametrisiert werden.</span><span class="sxs-lookup"><span data-stu-id="336e4-136">An inline function cannot be parameterized with a standard generic type parameter.</span></span>|<span data-ttu-id="336e4-137">Ja.</span><span class="sxs-lookup"><span data-stu-id="336e4-137">Yes.</span></span> <span data-ttu-id="336e4-138">Statisch aufgelöste Typparameter können nicht auf Funktionen oder Methoden angewendet werden, die nicht inline sind.</span><span class="sxs-lookup"><span data-stu-id="336e4-138">Statically resolved type parameters cannot be used on functions or methods that are not inline.</span></span>|

<span data-ttu-id="336e4-139">Viele F#-Kernbibliotheksfunktionen, besonders Operatoren, verfügen über statisch aufgelöste Typparameter.</span><span class="sxs-lookup"><span data-stu-id="336e4-139">Many F# core library functions, especially operators, have statically resolved type parameters.</span></span> <span data-ttu-id="336e4-140">Diese Funktionen und die Operatoren sind inline, und ergeben effiziente Codeerstellung für numerische Berechnungen.</span><span class="sxs-lookup"><span data-stu-id="336e4-140">These functions and operators are inline, and result in efficient code generation for numeric computations.</span></span>

<span data-ttu-id="336e4-141">Inlinemethoden und -funktionen, die Operatoren oder andere Funktionen mit statisch aufgelösten Typparametern verwenden, können auch selbst statisch aufgelöste Typparameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="336e4-141">Inline methods and functions that use operators, or use other functions that have statically resolved type parameters, can also use statically resolved type parameters themselves.</span></span> <span data-ttu-id="336e4-142">Oft leitet der Typrückschluss ab, dass solche Inlinefunktionen statisch aufgelöste Typparameter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="336e4-142">Often, type inference infers such inline functions to have statically resolved type parameters.</span></span> <span data-ttu-id="336e4-143">Im folgenden Beispiel wird eine Operatordefinition veranschaulicht, die so abgeleitet wird, dass sie einen statisch aufgelösten Typparameter hat.</span><span class="sxs-lookup"><span data-stu-id="336e4-143">The following example illustrates an operator definition that is inferred to have a statically resolved type parameter.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

<span data-ttu-id="336e4-144">Der aufgelöste Typ von `(+@)` basiert auf der Verwendung von `(+)` und `(*)`, durch die vom Typrückschluss Membereinschränkungen für die statisch aufgelösten Typparameter abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="336e4-144">The resolved type of `(+@)` is based on the use of both `(+)` and `(*)`, both of which cause type inference to infer member constraints on the statically resolved type parameters.</span></span> <span data-ttu-id="336e4-145">Der aufgelöste Typ, wie im F#-Interpreter angezeigt, lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="336e4-145">The resolved type, as shown in the F# interpreter, is as follows.</span></span>

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

<span data-ttu-id="336e4-146">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="336e4-146">The output is as follows.</span></span>

```console
2
1.500000
```

<span data-ttu-id="336e4-147">Ab F# 4,1 können Sie auch konkrete Typnamen in statisch aufgelösten Typparameter Signaturen angeben.</span><span class="sxs-lookup"><span data-stu-id="336e4-147">Starting with F# 4.1, you can also specify concrete type names in statically resolved type parameter signatures.</span></span>  <span data-ttu-id="336e4-148">In früheren Versionen der Sprache konnte der Typname tatsächlich vom Compiler abgeleitet werden, konnte aber nicht in der Signatur angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="336e4-148">In previous versions of the language, the type name could actually be inferred by the compiler, but could not actually be specified in the signature.</span></span>  <span data-ttu-id="336e4-149">Ab F# 4,1 können Sie auch konkrete Typnamen in statisch aufgelösten Typparameter Signaturen angeben.</span><span class="sxs-lookup"><span data-stu-id="336e4-149">As of F# 4.1, you may also specify concrete type names in statically resolved type parameter signatures.</span></span> <span data-ttu-id="336e4-150">Im Folgenden ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="336e4-150">Here's an example:</span></span>

```fsharp
let inline konst x _ = x

type CFunctor() =
    static member inline fmap (f: ^a -> ^b, a: ^a list) = List.map f a
    static member inline fmap (f: ^a -> ^b, a: ^a option) =
        match a with
        | None -> None
        | Some x -> Some (f x)

    // default implementation of replace
    static member inline replace< ^a, ^b, ^c, ^d, ^e when ^a :> CFunctor and (^a or ^d): (static member fmap: (^b -> ^c) * ^d -> ^e) > (a, f) =
        ((^a or ^d) : (static member fmap : (^b -> ^c) * ^d -> ^e) (konst a, f))

    // call overridden replace if present
    static member inline replace< ^a, ^b, ^c when ^b: (static member replace: ^a * ^b -> ^c)>(a: ^a, f: ^b) =
        (^b : (static member replace: ^a * ^b -> ^c) (a, f))

let inline replace_instance< ^a, ^b, ^c, ^d when (^a or ^c): (static member replace: ^b * ^c -> ^d)> (a: ^b, f: ^c) =
        ((^a or ^c): (static member replace: ^b * ^c -> ^d) (a, f))

// Note the concrete type 'CFunctor' specified in the signature
let inline replace (a: ^a) (f: ^b): ^a0 when (CFunctor or  ^b): (static member replace: ^a *  ^b ->  ^a0) =
    replace_instance<CFunctor, _, _, _> (a, f)
```

## <a name="see-also"></a><span data-ttu-id="336e4-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="336e4-151">See also</span></span>

- [<span data-ttu-id="336e4-152">Generics</span><span class="sxs-lookup"><span data-stu-id="336e4-152">Generics</span></span>](index.md)
- [<span data-ttu-id="336e4-153">Typableitung</span><span class="sxs-lookup"><span data-stu-id="336e4-153">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="336e4-154">Automatische Verallgemeinerung</span><span class="sxs-lookup"><span data-stu-id="336e4-154">Automatic Generalization</span></span>](automatic-generalization.md)
- [<span data-ttu-id="336e4-155">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="336e4-155">Constraints</span></span>](constraints.md)
- [<span data-ttu-id="336e4-156">Inlinefunktionen</span><span class="sxs-lookup"><span data-stu-id="336e4-156">Inline Functions</span></span>](../functions/inline-functions.md)
