---
title: Namespaces (F#)
description: Erfahren Sie, wie ein Namespace F#-Code in Bereichen verwandter Funktionalität organisieren, indem Sie einen Namen für die Gruppierung von Programmelementen anfügen kann.
ms.date: 04/24/2017
ms.openlocfilehash: 769a1241f76ac32d3a6a80bd637078493119bb3c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44178252"
---
# <a name="namespaces"></a><span data-ttu-id="792de-103">Namespaces</span><span class="sxs-lookup"><span data-stu-id="792de-103">Namespaces</span></span>

<span data-ttu-id="792de-104">Mit einem Namespace können Sie Code in Bereichen verwandter Funktionalität organisieren, indem Sie einen Namen an eine Gruppierung von Programmelementen anfügen.</span><span class="sxs-lookup"><span data-stu-id="792de-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of program elements.</span></span>

## <a name="syntax"></a><span data-ttu-id="792de-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="792de-105">Syntax</span></span>

```fsharp
namespace [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="792de-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="792de-106">Remarks</span></span>

<span data-ttu-id="792de-107">Wenn Sie Code in einem Namespace einfügen möchten, muss die erste Deklaration in der Datei den Namespace deklarieren.</span><span class="sxs-lookup"><span data-stu-id="792de-107">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="792de-108">Der Inhalt der gesamten Datei werden dann Teil des Namespace.</span><span class="sxs-lookup"><span data-stu-id="792de-108">The contents of the entire file then become part of the namespace.</span></span>

<span data-ttu-id="792de-109">Namespaces können nicht direkt als Werte und Funktionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="792de-109">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="792de-110">Stattdessen Werte und Funktionen in Modulen enthalten sein müssen, und Module in Namespaces enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="792de-110">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="792de-111">Namespaces kann es sich um Typen, Module enthalten.</span><span class="sxs-lookup"><span data-stu-id="792de-111">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="792de-112">Namespaces können explizit mit dem Schlüsselwort "Namespace" oder implizit deklariert werden, wenn ein Modul zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="792de-112">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="792de-113">Um einen Namespace explizit deklarieren, verwenden Sie das Schlüsselwort "Namespace" gefolgt vom Namespacenamen ein.</span><span class="sxs-lookup"><span data-stu-id="792de-113">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="792de-114">Das folgende Beispiel zeigt eine Codedatei, die einen Namespace Widgets mit einem Typ und einem Modul in diesem Namespace deklariert.</span><span class="sxs-lookup"><span data-stu-id="792de-114">The following example shows a code file that declares a namespace Widgets with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="792de-115">Wenn der gesamte Inhalt der Datei in einem Modul sind, Sie können auch Namespaces deklarieren implizit mithilfe der `module` -Schlüsselwort und den neuen Namespacenamen in der vollqualifizierte Modulname bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="792de-115">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="792de-116">Das folgende Beispiel zeigt eine Codedatei, die einen Namespace deklariert `Widgets` und ein Modul `WidgetsModule`, das eine Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="792de-116">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="792de-117">Der folgende Code entspricht dem vorangehenden Code, aber das Modul ist eine lokale Moduldeklaration.</span><span class="sxs-lookup"><span data-stu-id="792de-117">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="792de-118">In diesem Fall muss der Namespace in einer eigenen Zeile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="792de-118">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="792de-119">Wenn mehr als einem Modul in der gleichen Datei in einem oder mehreren Namespaces erforderlich ist, müssen Sie die Deklarationen der lokalen Modul verwenden.</span><span class="sxs-lookup"><span data-stu-id="792de-119">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="792de-120">Bei Verwendung von lokalen Moduldeklarationen können nicht Sie den vollqualifizierten Namespace in den Moduldeklarationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="792de-120">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="792de-121">Der folgende Code zeigt eine Datei, die eine Namespacedeklaration und zwei lokale Moduldeklarationen verfügt.</span><span class="sxs-lookup"><span data-stu-id="792de-121">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="792de-122">In diesem Fall sind die Module direkt im Namespace enthalten. Es gibt keine implizit erstelltes Modul, das den gleichen Namen wie die Datei hat.</span><span class="sxs-lookup"><span data-stu-id="792de-122">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="792de-123">Jeder andere code in die Datei, z. B. eine `do` binden, ist im Namespace, jedoch nicht in der inneren Module, daher Sie die Modulmember qualifizieren müssen `widgetFunction` mit den Namen des Moduls.</span><span class="sxs-lookup"><span data-stu-id="792de-123">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="792de-124">Die Ausgabe dieses Beispiels ist wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="792de-124">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="792de-125">Weitere Informationen finden Sie unter [Module](modules.md).</span><span class="sxs-lookup"><span data-stu-id="792de-125">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="792de-126">Geschachtelte Namespaces</span><span class="sxs-lookup"><span data-stu-id="792de-126">Nested Namespaces</span></span>

<span data-ttu-id="792de-127">Wenn Sie einen geschachtelten Namespace erstellen, müssen Sie sie vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="792de-127">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="792de-128">Andernfalls erstellen Sie einen neuen Namespace der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="792de-128">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="792de-129">Einzug wird in Namespacedeklarationen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="792de-129">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="792de-130">Das folgende Beispiel zeigt, wie Sie einen geschachtelten Namespace zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="792de-130">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="792de-131">Namespaces in Dateien und Assemblys</span><span class="sxs-lookup"><span data-stu-id="792de-131">Namespaces in Files and Assemblies</span></span>

<span data-ttu-id="792de-132">Namespaces können mehrere Dateien in einem einzelnen Projekt oder die Kompilierung umfassen.</span><span class="sxs-lookup"><span data-stu-id="792de-132">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="792de-133">Der Begriff *Namespacefragment* beschreibt den Teil eines Namespace, die in einer Datei enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="792de-133">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="792de-134">Namespaces können auch mehrere Assemblys umfassen.</span><span class="sxs-lookup"><span data-stu-id="792de-134">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="792de-135">Z. B. die `System` Namespace enthält die gesamte .NET Framework, die viele Assemblys umfasst, und viele geschachtelte Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="792de-135">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>

## <a name="global-namespace"></a><span data-ttu-id="792de-136">Globaler Namespace</span><span class="sxs-lookup"><span data-stu-id="792de-136">Global Namespace</span></span>

<span data-ttu-id="792de-137">Sie verwenden den vordefinierten Namespace `global` setzen Sie die Namen in den obersten Namespace von .NET.</span><span class="sxs-lookup"><span data-stu-id="792de-137">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="792de-138">Sie können auch globale verwenden, z. B. den Namespace der obersten Ebene .NET zu verweisen, um Namenskonflikte mit anderen Namespaces zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="792de-138">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="792de-139">Rekursive-namespaces</span><span class="sxs-lookup"><span data-stu-id="792de-139">Recursive namespaces</span></span>

<span data-ttu-id="792de-140">F# 4.1 führt das Konzept von Namespaces, die für alle enthaltenen Code gegenseitig rekursiver zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="792de-140">F# 4.1 introduces the notion of namespaces which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="792de-141">Dies erfolgt über `namespace rec`.</span><span class="sxs-lookup"><span data-stu-id="792de-141">This is done via `namespace rec`.</span></span>  <span data-ttu-id="792de-142">Verwenden von `namespace rec` können einige Probleme, nicht mehr zum Schreiben von Code für sich gegenseitig referenzielle Typen und Module verringern.</span><span class="sxs-lookup"><span data-stu-id="792de-142">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="792de-143">Im folgenden finden ein Beispiel hierfür:</span><span class="sxs-lookup"><span data-stu-id="792de-143">The following is an example of this:</span></span>

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

<span data-ttu-id="792de-144">Beachten Sie, dass die Ausnahme `DontSqueezeTheBananaException` und die Klasse `Banana` beide sich aufeinander beziehen.</span><span class="sxs-lookup"><span data-stu-id="792de-144">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="792de-145">Darüber hinaus das Modul `BananaHelpers` und die Klasse `Banana` auch sich aufeinander beziehen.</span><span class="sxs-lookup"><span data-stu-id="792de-145">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="792de-146">Dies ist nicht möglich, die in f# zu express, wenn Sie entfernt die `rec` -Schlüsselwort aus der `MutualReferences` Namespace.</span><span class="sxs-lookup"><span data-stu-id="792de-146">This would not be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="792de-147">Dieses Feature ist auch verfügbar für die obersten Ebene [Module](modules.md) in f# 4.1 oder höher.</span><span class="sxs-lookup"><span data-stu-id="792de-147">This feature is also available for top-level [Modules](modules.md) in F# 4.1 or higher.</span></span>

## <a name="see-also"></a><span data-ttu-id="792de-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="792de-148">See also</span></span>

- [<span data-ttu-id="792de-149">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="792de-149">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="792de-150">Module</span><span class="sxs-lookup"><span data-stu-id="792de-150">Modules</span></span>](modules.md)
- [<span data-ttu-id="792de-151">F#-RFC-FS-1009 – lassen Sie sich gegenseitig referenzielle Typen und Module über größere Bereiche in Dateien</span><span class="sxs-lookup"><span data-stu-id="792de-151">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
