---
title: Namespaces (F#)
description: Erfahren Sie, wie ein f#-datennamespace Sie Code in Funktionsbereichen organisieren, indem Sie einen Namen für die Gruppierung von Programmelemente anfügen kann.
ms.date: 04/24/2017
ms.openlocfilehash: 151079864f18fff79dac108889b68b3acf1566a1
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957761"
---
# <a name="namespaces"></a><span data-ttu-id="133c0-103">Namespaces</span><span class="sxs-lookup"><span data-stu-id="133c0-103">Namespaces</span></span>

<span data-ttu-id="133c0-104">Mit einem Namespace können Sie Code in Bereichen verwandter Funktionalität organisieren, indem Sie einen Namen an eine Gruppierung von Programmelementen anfügen.</span><span class="sxs-lookup"><span data-stu-id="133c0-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of program elements.</span></span>


## <a name="syntax"></a><span data-ttu-id="133c0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="133c0-105">Syntax</span></span>

```fsharp
namespace [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="133c0-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="133c0-106">Remarks</span></span>
<span data-ttu-id="133c0-107">Wenn Code in einem Namespace platziert werden sollen, muss die erste Deklaration in der Datei den Namespace deklarieren.</span><span class="sxs-lookup"><span data-stu-id="133c0-107">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="133c0-108">Der Inhalt der gesamten Datei wird dann Teil des Namespace.</span><span class="sxs-lookup"><span data-stu-id="133c0-108">The contents of the entire file then become part of the namespace.</span></span>

<span data-ttu-id="133c0-109">Namespaces kann nicht direkt, Werte und Funktionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="133c0-109">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="133c0-110">Stattdessen Werte und Funktionen in Modulen enthalten sein müssen, und Module in Namespaces enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="133c0-110">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="133c0-111">Namespaces können Typen, Module enthalten.</span><span class="sxs-lookup"><span data-stu-id="133c0-111">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="133c0-112">Namespaces können explizit mit dem namespaceschlüsselwort oder implizit deklariert werden, wenn ein Modul deklariert.</span><span class="sxs-lookup"><span data-stu-id="133c0-112">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="133c0-113">Um einen Namespace explizit zu deklarieren, verwenden Sie die Namespace-Schlüsselwort, gefolgt vom Namespacenamen.</span><span class="sxs-lookup"><span data-stu-id="133c0-113">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="133c0-114">Das folgende Beispiel zeigt eine Codedatei, die einen Namespace mit dem Typ und ein Modul, das in diesem Namespace enthaltenen Widgets deklariert.</span><span class="sxs-lookup"><span data-stu-id="133c0-114">The following example shows a code file that declares a namespace Widgets with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="133c0-115">Wenn der gesamte Inhalt der Datei in einem Modul sind, Sie können auch Namespaces deklarieren implizit mithilfe der `module` -Schlüsselwort und den neuen Namespacenamen in den vollständig qualifizierten Modulnamen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="133c0-115">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="133c0-116">Das folgende Beispiel zeigt eine Codedatei, die einen Namespace deklariert `Widgets` und ein Modul `WidgetsModule`, das eine Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="133c0-116">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="133c0-117">Der folgende Code entspricht dem vorangehenden Code, aber das Modul ist eine lokale Moduldeklaration.</span><span class="sxs-lookup"><span data-stu-id="133c0-117">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="133c0-118">In diesem Fall muss der Namespace in einer eigenen Zeile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="133c0-118">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="133c0-119">Wenn mehr als einem Modul in der gleichen Datei in einem oder mehreren Namespaces erforderlich ist, müssen Sie lokale Moduldeklarationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="133c0-119">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="133c0-120">Bei Verwendung von lokalen Moduldeklarationen kann nicht die vollqualifizierten Namespace in den Moduldeklarationen verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="133c0-120">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="133c0-121">Der folgende Code zeigt eine Datei, die eine Namespacedeklaration und zwei lokale Moduldeklarationen verfügt.</span><span class="sxs-lookup"><span data-stu-id="133c0-121">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="133c0-122">In diesem Fall sind die Module direkt im Namespace enthalten. Es ist kein implizit erstelltes Modul, das den gleichen Namen wie die Datei verfügt.</span><span class="sxs-lookup"><span data-stu-id="133c0-122">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="133c0-123">Alle anderen code in die Datei, z. B. eine `do` binden, ist im Namespace, jedoch nicht in den inneren Modulen, daher Sie das Modul-Element zu qualifizieren müssen `widgetFunction` mit den Namen des Moduls.</span><span class="sxs-lookup"><span data-stu-id="133c0-123">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="133c0-124">Die Ausgabe dieses Beispiels lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="133c0-124">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="133c0-125">Weitere Informationen finden Sie unter [Module](modules.md).</span><span class="sxs-lookup"><span data-stu-id="133c0-125">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="133c0-126">Geschachtelte Namespaces</span><span class="sxs-lookup"><span data-stu-id="133c0-126">Nested Namespaces</span></span>
<span data-ttu-id="133c0-127">Wenn Sie einen geschachtelten Namespace erstellen, müssen Sie vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="133c0-127">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="133c0-128">Andernfalls erstellen Sie einen neuen Namespace der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="133c0-128">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="133c0-129">Einzug wird in Namespacedeklarationen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="133c0-129">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="133c0-130">Im folgende Beispiel wird das Deklarieren eines geschachtelten Namespaces veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="133c0-130">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="133c0-131">Namespaces in Dateien und Assemblys</span><span class="sxs-lookup"><span data-stu-id="133c0-131">Namespaces in Files and Assemblies</span></span>
<span data-ttu-id="133c0-132">Namespaces können mehrere Dateien in einem einzelnen Projekt oder die Kompilierung umfassen.</span><span class="sxs-lookup"><span data-stu-id="133c0-132">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="133c0-133">Der Begriff *Namespacefragment* beschreibt den Teil eines Namespaces, die in einer Datei enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="133c0-133">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="133c0-134">Namespaces können auch mehrere Assemblys umfassen.</span><span class="sxs-lookup"><span data-stu-id="133c0-134">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="133c0-135">Z. B. die `System` Namespace enthält die gesamte .NET Framework, die viele Assemblys umfasst und zahlreiche geschachtelte Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="133c0-135">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>


## <a name="global-namespace"></a><span data-ttu-id="133c0-136">Globaler Namespace</span><span class="sxs-lookup"><span data-stu-id="133c0-136">Global Namespace</span></span>
<span data-ttu-id="133c0-137">Sie verwenden den vordefinierten Namespace `global` Namen in den Namespace der obersten Ebene .NET aufgenommen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="133c0-137">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="133c0-138">Sie können auch globale verwenden, z. B. den Namespace der obersten Ebene .NET verweisen, um Namenskonflikte mit anderen Namespaces zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="133c0-138">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="133c0-139">Rekursive namespaces</span><span class="sxs-lookup"><span data-stu-id="133c0-139">Recursive namespaces</span></span>

<span data-ttu-id="133c0-140">F#-4.1 führt das Konzept von Namespaces, die für alle enthaltenen Code wechselseitig rekursive werden zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="133c0-140">F# 4.1 introduces the notion of namespaces which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="133c0-141">Dies geschieht über `namespace rec`.</span><span class="sxs-lookup"><span data-stu-id="133c0-141">This is done via `namespace rec`.</span></span>  <span data-ttu-id="133c0-142">Verwenden von `namespace rec` verringern, können einige sorgen, nicht aufeinander Code für Typen und Module schreiben können.</span><span class="sxs-lookup"><span data-stu-id="133c0-142">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="133c0-143">Im folgenden finden ein Beispiel dafür:</span><span class="sxs-lookup"><span data-stu-id="133c0-143">The following is an example of this:</span></span>

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

<span data-ttu-id="133c0-144">Beachten Sie, dass die Ausnahme `DontSqueezeTheBananaException` und die Klasse `Banana` beide aufeinander verweisen.</span><span class="sxs-lookup"><span data-stu-id="133c0-144">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="133c0-145">Darüber hinaus das Modul `BananaHelpers` und die Klasse `Banana` auch miteinander verweisen.</span><span class="sxs-lookup"><span data-stu-id="133c0-145">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="133c0-146">Dies ist nicht möglich, express in F# erläutert werden, wenn Sie entfernt die `rec` -Schlüsselwort aus der `MutualReferences` Namespace.</span><span class="sxs-lookup"><span data-stu-id="133c0-146">This would not be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="133c0-147">Diese Funktion steht auch für die obersten Ebene [Module](modules.md) in f# 4.1 oder höher.</span><span class="sxs-lookup"><span data-stu-id="133c0-147">This feature is also available for top-level [Modules](modules.md) in F# 4.1 or higher.</span></span>

## <a name="see-also"></a><span data-ttu-id="133c0-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="133c0-148">See Also</span></span>
[<span data-ttu-id="133c0-149">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="133c0-149">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="133c0-150">Module</span><span class="sxs-lookup"><span data-stu-id="133c0-150">Modules</span></span>](modules.md)

[<span data-ttu-id="133c0-151">F#-RFC-EA-1009 - aufeinander Typen und Module über größere Bereiche innerhalb von Dateien zulassen</span><span class="sxs-lookup"><span data-stu-id="133c0-151">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
