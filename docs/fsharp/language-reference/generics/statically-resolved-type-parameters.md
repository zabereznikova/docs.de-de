---
title: "Statisch aufgelöste Typparameter (F#)"
description: "Informationen zum Verwenden von f#-statisch aufgelösten Typparameter, der zur Kompilierzeit statt zur Laufzeit durch einen tatsächlichen Typ ersetzt wird."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b3797415-3e49-4f8a-a8ee-fa614c5721aa
ms.openlocfilehash: 14c629d6223584113af47636495be61decca02ad
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="statically-resolved-type-parameters"></a><span data-ttu-id="fc4cb-104">Statisch aufgelöste Typparameter</span><span class="sxs-lookup"><span data-stu-id="fc4cb-104">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="fc4cb-105">Ein *statisch aufgelösten Typparameter* ist ein Typparameter, der zur Kompilierzeit statt zur Laufzeit durch einen tatsächlichen Typ ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-105">A *statically resolved type parameter* is a type parameter that is replaced with an actual type at compile time instead of at run time.</span></span> <span data-ttu-id="fc4cb-106">Ihnen wird ein Caretzeichen (^) vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-106">They are preceded by a caret (^) symbol.</span></span>


## <a name="syntax"></a><span data-ttu-id="fc4cb-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc4cb-107">Syntax</span></span>

```
ˆtype-parameter
```

## <a name="remarks"></a><span data-ttu-id="fc4cb-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fc4cb-108">Remarks</span></span>
<span data-ttu-id="fc4cb-109">In der Programmiersprache F# gibt es zwei unterschiedliche Arten von Typparametern.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-109">In the F# language, there are two distinct kinds of type parameters.</span></span> <span data-ttu-id="fc4cb-110">Die erste Art ist der standardmäßige generische Typparameter.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-110">The first kind is the standard generic type parameter.</span></span> <span data-ttu-id="fc4cb-111">Diese werden durch ein Apostroph (') angegeben, wie bei `'T` und `'U`.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-111">These are indicated by an apostrophe ('), as in `'T` and `'U`.</span></span> <span data-ttu-id="fc4cb-112">Sie entsprechen generischen Typparametern in anderen .NET Framework-Sprachen.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-112">They are equivalent to generic type parameters in other .NET Framework languages.</span></span> <span data-ttu-id="fc4cb-113">Die andere Art ist statisch aufgelöst und wird von einem Caretzeichensymbol, wie in `^T` und `^U`.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-113">The other kind is statically resolved and is indicated by a caret symbol, as in `^T` and `^U`.</span></span>

<span data-ttu-id="fc4cb-114">Statisch aufgelöste Typparameter sind hauptsächlich in Verbindung mit Membereinschränkungen nützlich, die Ihnen die Angabe ermöglichen, dass ein Typargument zur Verwendung einen bestimmten Member oder mehrere Member aufweisen muss.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-114">Statically resolved type parameters are primarily useful in conjunction with member constraints, which are constraints that allow you to specify that a type argument must have a particular member or members in order to be used.</span></span> <span data-ttu-id="fc4cb-115">Es gibt keine Möglichkeit, diese Art von Einschränkung mit einem regulären generischen Typparameter zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-115">There is no way to create this kind of constraint by using a regular generic type parameter.</span></span>

<span data-ttu-id="fc4cb-116">In der folgenden Tabelle werden die Ähnlichkeiten und die Unterschiede zwischen den beiden Arten von Typparametern zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-116">The following table summarizes the similarities and differences between the two kinds of type parameters.</span></span>

|<span data-ttu-id="fc4cb-117">Feature</span><span class="sxs-lookup"><span data-stu-id="fc4cb-117">Feature</span></span>|<span data-ttu-id="fc4cb-118">Generisch</span><span class="sxs-lookup"><span data-stu-id="fc4cb-118">Generic</span></span>|<span data-ttu-id="fc4cb-119">Statisch aufgelöst</span><span class="sxs-lookup"><span data-stu-id="fc4cb-119">Statically resolved</span></span>|
|-------|-------|-------------------|
|<span data-ttu-id="fc4cb-120">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc4cb-120">Syntax</span></span>|<span data-ttu-id="fc4cb-121">`'T`, `'U`</span><span class="sxs-lookup"><span data-stu-id="fc4cb-121">`'T`, `'U`</span></span>|<span data-ttu-id="fc4cb-122">`^T`, `^U`</span><span class="sxs-lookup"><span data-stu-id="fc4cb-122">`^T`, `^U`</span></span>|
|<span data-ttu-id="fc4cb-123">Auflösungszeit</span><span class="sxs-lookup"><span data-stu-id="fc4cb-123">Resolution time</span></span>|<span data-ttu-id="fc4cb-124">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="fc4cb-124">Run time</span></span>|<span data-ttu-id="fc4cb-125">Kompilierungsfehler</span><span class="sxs-lookup"><span data-stu-id="fc4cb-125">Compile time</span></span>|
|<span data-ttu-id="fc4cb-126">Member-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="fc4cb-126">Member constraints</span></span>|<span data-ttu-id="fc4cb-127">Kann nicht mit Membereinschränkungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-127">Cannot be used with member constraints.</span></span>|<span data-ttu-id="fc4cb-128">Kann mit Membereinschränkungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-128">Can be used with member constraints.</span></span>|
|<span data-ttu-id="fc4cb-129">Codeerzeugung</span><span class="sxs-lookup"><span data-stu-id="fc4cb-129">Code generation</span></span>|<span data-ttu-id="fc4cb-130">Ein Typ (oder eine Methode) mit standardmäßigen generischen Typparametern führt zur Erstellung eines einzelnen generischen Typs oder einer Methode.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-130">A type (or method) with standard generic type parameters results in the generation of a single generic type or method.</span></span>|<span data-ttu-id="fc4cb-131">Mehrere Instanziierungen von Typen und Methoden werden generiert, einer für jeden erforderlichen Typ.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-131">Multiple instantiations of types and methods are generated, one for each type that is needed.</span></span>|
|<span data-ttu-id="fc4cb-132">Verwendung mit Typen</span><span class="sxs-lookup"><span data-stu-id="fc4cb-132">Use with types</span></span>|<span data-ttu-id="fc4cb-133">Kann mit Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-133">Can be used on types.</span></span>|<span data-ttu-id="fc4cb-134">Kann nicht mit Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-134">Cannot be used on types.</span></span>|
|<span data-ttu-id="fc4cb-135">Verwendung mit Inlinefunktionen</span><span class="sxs-lookup"><span data-stu-id="fc4cb-135">Use with inline functions</span></span>|<span data-ttu-id="fc4cb-136">Nein.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-136">No.</span></span> <span data-ttu-id="fc4cb-137">Eine Inlinefunktion kann nicht mit einem standardmäßigen generischen Typparameter parametrisiert werden.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-137">An inline function cannot be parameterized with a standard generic type parameter.</span></span>|<span data-ttu-id="fc4cb-138">Ja.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-138">Yes.</span></span> <span data-ttu-id="fc4cb-139">Statisch aufgelöste Typparameter können nicht auf Funktionen oder Methoden angewendet werden, die nicht inline sind.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-139">Statically resolved type parameters cannot be used on functions or methods that are not inline.</span></span>|

<span data-ttu-id="fc4cb-140">Viele F#-Kernbibliotheksfunktionen, besonders Operatoren, verfügen über statisch aufgelöste Typparameter.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-140">Many F# core library functions, especially operators, have statically resolved type parameters.</span></span> <span data-ttu-id="fc4cb-141">Diese Funktionen und die Operatoren sind inline, und ergeben effiziente Codeerstellung für numerische Berechnungen.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-141">These functions and operators are inline, and result in efficient code generation for numeric computations.</span></span>

<span data-ttu-id="fc4cb-142">Inlinemethoden und -funktionen, die Operatoren oder andere Funktionen mit statisch aufgelösten Typparametern verwenden, können auch selbst statisch aufgelöste Typparameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-142">Inline methods and functions that use operators, or use other functions that have statically resolved type parameters, can also use statically resolved type parameters themselves.</span></span> <span data-ttu-id="fc4cb-143">Oft leitet der Typrückschluss ab, dass solche Inlinefunktionen statisch aufgelöste Typparameter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-143">Often, type inference infers such inline functions to have statically resolved type parameters.</span></span> <span data-ttu-id="fc4cb-144">Im folgenden Beispiel wird eine Operatordefinition veranschaulicht, die so abgeleitet wird, dass sie einen statisch aufgelösten Typparameter hat.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-144">The following example illustrates an operator definition that is inferred to have a statically resolved type parameter.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

<span data-ttu-id="fc4cb-145">Der aufgelöste Typ von `(+@)` basiert auf der Verwendung von `(+)` und `(*)`, durch die vom Typrückschluss Membereinschränkungen für die statisch aufgelösten Typparameter abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-145">The resolved type of `(+@)` is based on the use of both `(+)` and `(*)`, both of which cause type inference to infer member constraints on the statically resolved type parameters.</span></span> <span data-ttu-id="fc4cb-146">Der aufgelöste Typ, wie im F#-Interpreter angezeigt, lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-146">The resolved type, as shown in the F# interpreter, is as follows.</span></span>

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

<span data-ttu-id="fc4cb-147">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-147">The output is as follows.</span></span>

```
2
1.500000
```

<span data-ttu-id="fc4cb-148">Ab f# 4.1, können Sie auch konkrete Typnamen in statisch aufgelösten Typsignaturen-Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-148">Starting with F# 4.1, you can also specify concrete type names in statically resolved type parameter signatures.</span></span>  <span data-ttu-id="fc4cb-149">In früheren Versionen der Sprache des Typnamens tatsächlich vom Compiler abgeleitet werden, aber konnte nicht tatsächlich in der Signatur angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-149">In previous versions of the language, the type name could actually be inferred by the compiler, but could not actually be specified in the signature.</span></span>  <span data-ttu-id="fc4cb-150">Ab f# 4.1 können Sie auch die konkrete Typnamen in statisch aufgelösten Typsignaturen-Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="fc4cb-150">As of F# 4.1, you may also specify concrete type names in statically resolved type parameter signatures.</span></span> <span data-ttu-id="fc4cb-151">Im Folgenden ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fc4cb-151">Here's an example:</span></span>

```fsharp
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

## <a name="see-also"></a><span data-ttu-id="fc4cb-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc4cb-152">See Also</span></span>
[<span data-ttu-id="fc4cb-153">Generika</span><span class="sxs-lookup"><span data-stu-id="fc4cb-153">Generics</span></span>](index.md)

[<span data-ttu-id="fc4cb-154">Typableitung</span><span class="sxs-lookup"><span data-stu-id="fc4cb-154">Type Inference</span></span>](../type-inference.md)

[<span data-ttu-id="fc4cb-155">Automatische Verallgemeinerung</span><span class="sxs-lookup"><span data-stu-id="fc4cb-155">Automatic Generalization</span></span>](automatic-generalization.md)

[<span data-ttu-id="fc4cb-156">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="fc4cb-156">Constraints</span></span>](constraints.md)

[<span data-ttu-id="fc4cb-157">Inlinefunktionen</span><span class="sxs-lookup"><span data-stu-id="fc4cb-157">Inline Functions</span></span>](../functions/inline-functions.md)
