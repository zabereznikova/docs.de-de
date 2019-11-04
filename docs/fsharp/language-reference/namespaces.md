---
title: Namespaces
description: Erfahren Sie, F# wie ein Namespace Ihnen ermöglicht, Code in Bereichen verwandter Funktionalität zu organisieren, indem Sie einen Namen an eine Gruppierung von Programmelementen anfügen können.
ms.date: 12/08/2018
ms.openlocfilehash: a55da1592b04c64576b4c66de61b5ca137289a6f
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425046"
---
# <a name="namespaces"></a><span data-ttu-id="168f4-103">Namespaces</span><span class="sxs-lookup"><span data-stu-id="168f4-103">Namespaces</span></span>

<span data-ttu-id="168f4-104">Mit einem Namespace können Sie Code in Bereichen verwandter Funktionalität organisieren, indem Sie einen Namen an eine Gruppierung von F# Programmelementen anfügen können.</span><span class="sxs-lookup"><span data-stu-id="168f4-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of F# program elements.</span></span> <span data-ttu-id="168f4-105">Namespaces sind in der Regel Elemente der obersten F# Ebene in Dateien.</span><span class="sxs-lookup"><span data-stu-id="168f4-105">Namespaces are typically top-level elements in F# files.</span></span>

## <a name="syntax"></a><span data-ttu-id="168f4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="168f4-106">Syntax</span></span>

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="168f4-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="168f4-107">Remarks</span></span>

<span data-ttu-id="168f4-108">Wenn Sie Code in einem Namespace platzieren möchten, muss die erste Deklaration in der Datei den Namespace deklarieren.</span><span class="sxs-lookup"><span data-stu-id="168f4-108">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="168f4-109">Der Inhalt der gesamten Datei wird dann Teil des Namespaces, sofern keine weitere Namespace-Deklaration in der Datei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="168f4-109">The contents of the entire file then become part of the namespace, provided no other namespaces declaration exists further in the file.</span></span> <span data-ttu-id="168f4-110">Wenn dies der Fall ist, wird der gesamte Code bis zur nächsten Namespace Deklaration als innerhalb des ersten Namespaces betrachtet.</span><span class="sxs-lookup"><span data-stu-id="168f4-110">If that is the case, then all code up until the next namespace declaration is considered to be within the first namespace.</span></span>

<span data-ttu-id="168f4-111">Namespaces können nicht direkt Werte und Funktionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="168f4-111">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="168f4-112">Stattdessen müssen Werte und Funktionen in Module enthalten sein, und Module sind in Namespaces enthalten.</span><span class="sxs-lookup"><span data-stu-id="168f4-112">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="168f4-113">Namespaces können Typen, Module enthalten.</span><span class="sxs-lookup"><span data-stu-id="168f4-113">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="168f4-114">XML-Dokument Kommentare können über einem Namespace deklariert werden, werden jedoch ignoriert.</span><span class="sxs-lookup"><span data-stu-id="168f4-114">XML doc comments can be declared above a namespace, but they're ignored.</span></span> <span data-ttu-id="168f4-115">Compilerdirektiven können auch über einem Namespace deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="168f4-115">Compiler directives can also be declared above a namespace.</span></span>

<span data-ttu-id="168f4-116">Namespaces können explizit mit dem Namespace-Schlüsselwort oder implizit beim Deklarieren eines Moduls deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="168f4-116">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="168f4-117">Um einen Namespace explizit zu deklarieren, verwenden Sie das Namespace-Schlüsselwort, gefolgt vom Namespace Namen.</span><span class="sxs-lookup"><span data-stu-id="168f4-117">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="168f4-118">Das folgende Beispiel zeigt eine Codedatei, die einen Namespace `Widgets` mit einem Typ und einem Modul deklariert, das in diesem Namespace enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="168f4-118">The following example shows a code file that declares a namespace `Widgets` with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="168f4-119">Wenn sich der gesamte Inhalt der Datei in einem Modul befindet, können Sie Namespaces auch implizit deklarieren, indem Sie das `module`-Schlüsselwort verwenden und den neuen Namespace Namen im voll qualifizierten Modulnamen angeben.</span><span class="sxs-lookup"><span data-stu-id="168f4-119">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="168f4-120">Das folgende Beispiel zeigt eine Codedatei, die einen Namespace deklariert `Widgets` und ein Modul `WidgetsModule`, das eine Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="168f4-120">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="168f4-121">Der folgende Code entspricht dem vorangehenden Code, aber das Modul ist eine lokale Modul Deklaration.</span><span class="sxs-lookup"><span data-stu-id="168f4-121">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="168f4-122">In diesem Fall muss der Namespace in einer eigenen Zeile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="168f4-122">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="168f4-123">Wenn mehr als ein Modul in derselben Datei in einem oder mehreren Namespaces erforderlich ist, müssen Sie lokale Modul Deklarationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="168f4-123">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="168f4-124">Wenn Sie lokale Modul Deklarationen verwenden, kann der qualifizierte Namespace in den Modul Deklarationen nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="168f4-124">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="168f4-125">Der folgende Code zeigt eine Datei mit einer Namespace Deklaration und zwei Deklarationen von lokalen Modulen.</span><span class="sxs-lookup"><span data-stu-id="168f4-125">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="168f4-126">In diesem Fall sind die Module direkt im-Namespace enthalten. Es ist kein implizit erstelltes Modul vorhanden, das denselben Namen wie die Datei hat.</span><span class="sxs-lookup"><span data-stu-id="168f4-126">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="168f4-127">Jeder andere Code in der Datei, z. b. eine `do` Bindung, befindet sich im-Namespace, jedoch nicht in den inneren Modulen. Daher müssen Sie das Modulmember `widgetFunction` mithilfe des Modul namens qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="168f4-127">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="168f4-128">Die Ausgabe dieses Beispiels lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="168f4-128">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="168f4-129">Weitere Informationen finden Sie unter [Module](modules.md).</span><span class="sxs-lookup"><span data-stu-id="168f4-129">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="168f4-130">Schsted Namespaces</span><span class="sxs-lookup"><span data-stu-id="168f4-130">Nested Namespaces</span></span>

<span data-ttu-id="168f4-131">Wenn Sie einen in einem netsted Namespace erstellten Namespace erstellen, müssen Sie ihn vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="168f4-131">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="168f4-132">Andernfalls erstellen Sie einen neuen Namespace der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="168f4-132">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="168f4-133">Der Einzug wird in Namespace Deklarationen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="168f4-133">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="168f4-134">Im folgenden Beispiel wird gezeigt, wie ein schsted Namespace deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="168f4-134">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="168f4-135">Namespaces in Dateien und Assemblys</span><span class="sxs-lookup"><span data-stu-id="168f4-135">Namespaces in Files and Assemblies</span></span>

<span data-ttu-id="168f4-136">Namespaces können mehrere Dateien in einem einzelnen Projekt oder einer Kompilierung umfassen.</span><span class="sxs-lookup"><span data-stu-id="168f4-136">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="168f4-137">Der Begriff *Namespace Fragment* beschreibt den Teil eines Namespace, der in einer Datei enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="168f4-137">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="168f4-138">Namespaces können sich auch über mehrere Assemblys erstrecken.</span><span class="sxs-lookup"><span data-stu-id="168f4-138">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="168f4-139">Der `System`-Namespace enthält z. b. den gesamten .NET Framework, der sich über viele Assemblys erstreckt und viele eingefügte Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="168f4-139">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>

## <a name="global-namespace"></a><span data-ttu-id="168f4-140">Globaler Namespace</span><span class="sxs-lookup"><span data-stu-id="168f4-140">Global Namespace</span></span>

<span data-ttu-id="168f4-141">Sie verwenden den vordefinierten Namespace `global`, um Namen in den .NET-Namespace auf oberster Ebene zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="168f4-141">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="168f4-142">Sie können auch global verwenden, um auf den .NET-Namespace der obersten Ebene zu verweisen, z. b. um Namenskonflikte mit anderen Namespaces aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="168f4-142">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="168f4-143">Rekursive Namespaces</span><span class="sxs-lookup"><span data-stu-id="168f4-143">Recursive namespaces</span></span>

<span data-ttu-id="168f4-144">Namespaces können auch als rekursiv deklariert werden, damit der gesamte enthaltene Code gegenseitig rekursiv ist.</span><span class="sxs-lookup"><span data-stu-id="168f4-144">Namespaces can also be declared as recursive to allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="168f4-145">Dies erfolgt über `namespace rec`.</span><span class="sxs-lookup"><span data-stu-id="168f4-145">This is done via `namespace rec`.</span></span> <span data-ttu-id="168f4-146">Die Verwendung von `namespace rec` kann einige Probleme verringern, die sich nicht gegenseitig referenziellen Code zwischen Typen und Modulen schreiben können.</span><span class="sxs-lookup"><span data-stu-id="168f4-146">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span> <span data-ttu-id="168f4-147">Im folgenden finden Sie ein Beispiel hierfür:</span><span class="sxs-lookup"><span data-stu-id="168f4-147">The following is an example of this:</span></span>

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

type BananaPeel() = class end

type Banana(orientation : Orientation) =
    member val IsPeeled = false with get, set
    member val Orientation = orientation with get, set
    member val Sides: PeelState list = [ Unpeeled; Unpeeled; Unpeeled; Unpeeled] with get, set

    member self.Peel() = BananaHelpers.peel self // Note the dependency on the BananaHelpers module.
    member self.SqueezeJuiceOut() = raise (DontSqueezeTheBananaException self) // This member depends on the exception above.

module BananaHelpers =
    let peel (b: Banana) =
        let flip (banana: Banana) =
            match banana.Orientation with
            | Up ->
                banana.Orientation <- Down
                banana
            | Down -> banana

        let peelSides (banana: Banana) =
            banana.Sides
            |> List.map (function
                         | Unpeeled -> Peeled
                         | Peeled -> Peeled)

        match b.Orientation with
        | Up ->   b |> flip |> peelSides
        | Down -> b |> peelSides
```

<span data-ttu-id="168f4-148">Beachten Sie, dass die Ausnahme `DontSqueezeTheBananaException` und die-Klasse `Banana` beide aufeinander verweisen.</span><span class="sxs-lookup"><span data-stu-id="168f4-148">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="168f4-149">Außerdem verweisen das Modul `BananaHelpers` und die Klasse `Banana` auch aufeinander.</span><span class="sxs-lookup"><span data-stu-id="168f4-149">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span> <span data-ttu-id="168f4-150">Dies wäre nicht möglich, F# Wenn Sie das `rec`-Schlüsselwort aus dem `MutualReferences`-Namespace entfernt haben.</span><span class="sxs-lookup"><span data-stu-id="168f4-150">This wouldn't be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="168f4-151">Diese Funktion ist auch für [Module](modules.md)der obersten Ebene verfügbar.</span><span class="sxs-lookup"><span data-stu-id="168f4-151">This feature is also available for top-level [Modules](modules.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="168f4-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="168f4-152">See also</span></span>

- [<span data-ttu-id="168f4-153">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="168f4-153">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="168f4-154">Module</span><span class="sxs-lookup"><span data-stu-id="168f4-154">Modules</span></span>](modules.md)
- [<span data-ttu-id="168f4-155">F#RFC FS-1009-zulassen von sich gegenseitig referenziellen Typen und Modulen über größere Bereiche innerhalb von Dateien</span><span class="sxs-lookup"><span data-stu-id="168f4-155">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
