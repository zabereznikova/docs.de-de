---
title: Namespaces (F#)
description: "Erfahren Sie, wie ein f#-datennamespace Sie Code in Funktionsbereichen organisieren, indem Sie einen Namen für die Gruppierung von Programmelemente anfügen kann."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea42156f-e1b9-4535-9383-b45f46f3f7ca
ms.openlocfilehash: 4378afebe6fd0d9317f734457576dc75d7488bf0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="namespaces"></a><span data-ttu-id="62110-104">Namespaces</span><span class="sxs-lookup"><span data-stu-id="62110-104">Namespaces</span></span>

<span data-ttu-id="62110-105">Mit einem Namespace können Sie Code in Bereichen verwandter Funktionalität organisieren, indem Sie einen Namen an eine Gruppierung von Programmelementen anfügen.</span><span class="sxs-lookup"><span data-stu-id="62110-105">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of program elements.</span></span>


## <a name="syntax"></a><span data-ttu-id="62110-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="62110-106">Syntax</span></span>

```fsharp
namespace [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="62110-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62110-107">Remarks</span></span>
<span data-ttu-id="62110-108">Wenn Code in einem Namespace platziert werden sollen, muss die erste Deklaration in der Datei den Namespace deklarieren.</span><span class="sxs-lookup"><span data-stu-id="62110-108">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="62110-109">Der Inhalt der gesamten Datei wird dann Teil des Namespace.</span><span class="sxs-lookup"><span data-stu-id="62110-109">The contents of the entire file then become part of the namespace.</span></span>

<span data-ttu-id="62110-110">Namespaces kann nicht direkt, Werte und Funktionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="62110-110">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="62110-111">Stattdessen Werte und Funktionen in Modulen enthalten sein müssen, und Module in Namespaces enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="62110-111">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="62110-112">Namespaces können Typen, Module enthalten.</span><span class="sxs-lookup"><span data-stu-id="62110-112">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="62110-113">Namespaces können explizit mit dem namespaceschlüsselwort oder implizit deklariert werden, wenn ein Modul deklariert.</span><span class="sxs-lookup"><span data-stu-id="62110-113">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="62110-114">Um einen Namespace explizit zu deklarieren, verwenden Sie die Namespace-Schlüsselwort, gefolgt vom Namespacenamen.</span><span class="sxs-lookup"><span data-stu-id="62110-114">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="62110-115">Das folgende Beispiel zeigt eine Codedatei, die einen Namespace mit dem Typ und ein Modul, das in diesem Namespace enthaltenen Widgets deklariert.</span><span class="sxs-lookup"><span data-stu-id="62110-115">The following example shows a code file that declares a namespace Widgets with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="62110-116">Wenn der gesamte Inhalt der Datei in einem Modul sind, Sie können auch Namespaces deklarieren implizit mithilfe der `module` -Schlüsselwort und den neuen Namespacenamen in den vollständig qualifizierten Modulnamen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="62110-116">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="62110-117">Das folgende Beispiel zeigt eine Codedatei, die einen Namespace deklariert `Widgets` und ein Modul `WidgetsModule`, das eine Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="62110-117">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="62110-118">Der folgende Code entspricht dem vorangehenden Code, aber das Modul ist eine lokale Moduldeklaration.</span><span class="sxs-lookup"><span data-stu-id="62110-118">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="62110-119">In diesem Fall muss der Namespace in einer eigenen Zeile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="62110-119">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="62110-120">Wenn mehr als einem Modul in der gleichen Datei in einem oder mehreren Namespaces erforderlich ist, müssen Sie lokale Moduldeklarationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="62110-120">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="62110-121">Bei Verwendung von lokalen Moduldeklarationen kann nicht die vollqualifizierten Namespace in den Moduldeklarationen verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="62110-121">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="62110-122">Der folgende Code zeigt eine Datei, die eine Namespacedeklaration und zwei lokale Moduldeklarationen verfügt.</span><span class="sxs-lookup"><span data-stu-id="62110-122">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="62110-123">In diesem Fall sind die Module direkt im Namespace enthalten. Es ist kein implizit erstelltes Modul, das den gleichen Namen wie die Datei verfügt.</span><span class="sxs-lookup"><span data-stu-id="62110-123">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="62110-124">Alle anderen code in die Datei, z. B. eine `do` binden, ist im Namespace, jedoch nicht in den inneren Modulen, daher Sie das Modul-Element zu qualifizieren müssen `widgetFunction` mit den Namen des Moduls.</span><span class="sxs-lookup"><span data-stu-id="62110-124">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="62110-125">Die Ausgabe dieses Beispiels lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="62110-125">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="62110-126">Weitere Informationen finden Sie unter [Module](modules.md).</span><span class="sxs-lookup"><span data-stu-id="62110-126">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="62110-127">Geschachtelte Namespaces</span><span class="sxs-lookup"><span data-stu-id="62110-127">Nested Namespaces</span></span>
<span data-ttu-id="62110-128">Wenn Sie einen geschachtelten Namespace erstellen, müssen Sie vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="62110-128">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="62110-129">Andernfalls erstellen Sie einen neuen Namespace der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="62110-129">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="62110-130">Einzug wird in Namespacedeklarationen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="62110-130">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="62110-131">Im folgende Beispiel wird das Deklarieren eines geschachtelten Namespaces veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="62110-131">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="62110-132">Namespaces in Dateien und Assemblys</span><span class="sxs-lookup"><span data-stu-id="62110-132">Namespaces in Files and Assemblies</span></span>
<span data-ttu-id="62110-133">Namespaces können mehrere Dateien in einem einzelnen Projekt oder die Kompilierung umfassen.</span><span class="sxs-lookup"><span data-stu-id="62110-133">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="62110-134">Der Begriff *Namespacefragment* beschreibt den Teil eines Namespaces, die in einer Datei enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="62110-134">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="62110-135">Namespaces können auch mehrere Assemblys umfassen.</span><span class="sxs-lookup"><span data-stu-id="62110-135">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="62110-136">Z. B. die `System` Namespace enthält die gesamte .NET Framework, die viele Assemblys umfasst und zahlreiche geschachtelte Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="62110-136">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>


## <a name="global-namespace"></a><span data-ttu-id="62110-137">Globaler Namespace</span><span class="sxs-lookup"><span data-stu-id="62110-137">Global Namespace</span></span>
<span data-ttu-id="62110-138">Sie verwenden den vordefinierten Namespace `global` Namen in den Namespace der obersten Ebene .NET aufgenommen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="62110-138">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="62110-139">Sie können auch globale verwenden, z. B. den Namespace der obersten Ebene .NET verweisen, um Namenskonflikte mit anderen Namespaces zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="62110-139">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

##

<span data-ttu-id="62110-140">F#-4.1 führt das Konzept von Namespaces, die für alle enthaltenen Code wechselseitig rekursive werden zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="62110-140">F# 4.1 introduces the notion of namespaces which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="62110-141">Dies geschieht über `namespace rec`.</span><span class="sxs-lookup"><span data-stu-id="62110-141">This is done via `namespace rec`.</span></span>  <span data-ttu-id="62110-142">Verwenden von `namespace rec` verringern, können einige sorgen, nicht aufeinander Code für Typen und Module schreiben können.</span><span class="sxs-lookup"><span data-stu-id="62110-142">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="62110-143">Im folgenden finden ein Beispiel dafür:</span><span class="sxs-lookup"><span data-stu-id="62110-143">The following is an example of this:</span></span>

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
    let peel (b : Banana) =
        let flip banana =
            match banana.Orientation with
            | Up -> 
                banana.Orientation <- Down
                banana
            | Down -> banana

        let peelSides banana =
            for side in banana.Sides do
                if side = Unpeeled then
                    side <- Peeled

        match b.Orientation with
        | Up ->   b |> flip |> peelSides
        | Down -> b |> peelSides
```

<span data-ttu-id="62110-144">Beachten Sie, dass die Ausnahme `DontSqueezeTheBananaException` und die Klasse `Banana` beide aufeinander verweisen.</span><span class="sxs-lookup"><span data-stu-id="62110-144">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="62110-145">Darüber hinaus das Modul `BananaHelpers` und die Klasse `Banana` auch miteinander verweisen.</span><span class="sxs-lookup"><span data-stu-id="62110-145">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="62110-146">Dies ist nicht möglich, express in F# erläutert werden, wenn Sie entfernt die `rec` -Schlüsselwort aus der `MutualReferences` Namespace.</span><span class="sxs-lookup"><span data-stu-id="62110-146">This would not be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="62110-147">Diese Funktion steht auch für die obersten Ebene [Module](modules.md) in f# 4.1 oder höher.</span><span class="sxs-lookup"><span data-stu-id="62110-147">This feature is also available for top-level [Modules](modules.md) in F# 4.1 or higher.</span></span>

## <a name="see-also"></a><span data-ttu-id="62110-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62110-148">See Also</span></span>
[<span data-ttu-id="62110-149">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="62110-149">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="62110-150">Module</span><span class="sxs-lookup"><span data-stu-id="62110-150">Modules</span></span>](modules.md)

[<span data-ttu-id="62110-151">F#-RFC-EA-1009 - aufeinander Typen und Module über größere Bereiche innerhalb von Dateien zulassen</span><span class="sxs-lookup"><span data-stu-id="62110-151">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
