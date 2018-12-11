---
title: Namespaces (F#)
description: Erfahren Sie, wie ein F# Namespace können Sie Code in Bereichen verwandter Funktionalität organisieren, indem Sie einen Namen für die Gruppierung von Programmelementen anfügen.
ms.date: 12/08/2018
ms.openlocfilehash: ad5cca8947d09d8480bfa418b003c84546edc29b
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169022"
---
# <a name="namespaces"></a><span data-ttu-id="a52ac-103">Namespaces</span><span class="sxs-lookup"><span data-stu-id="a52ac-103">Namespaces</span></span>

<span data-ttu-id="a52ac-104">Mit einem Namespace können Sie den Code in Bereichen verwandter Funktionalität organisieren, indem Sie einen Namen für die Gruppierung von Anfügen F# Programmelemente.</span><span class="sxs-lookup"><span data-stu-id="a52ac-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of F# program elements.</span></span> <span data-ttu-id="a52ac-105">Namespaces sind in der Regel auf oberster Ebene von Elementen in F# Dateien.</span><span class="sxs-lookup"><span data-stu-id="a52ac-105">Namespaces are typically top-level elements in F# files.</span></span>

## <a name="syntax"></a><span data-ttu-id="a52ac-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a52ac-106">Syntax</span></span>

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="a52ac-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a52ac-107">Remarks</span></span>

<span data-ttu-id="a52ac-108">Wenn Sie Code in einem Namespace einfügen möchten, muss die erste Deklaration in der Datei den Namespace deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a52ac-108">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="a52ac-109">Der Inhalt der gesamten Datei dann Teil des Namespace, sofern keine andere Namespacedeklaration vorhanden ist. weiter in der Datei.</span><span class="sxs-lookup"><span data-stu-id="a52ac-109">The contents of the entire file then become part of the namespace, provided no other namespaces declaration exists further in the file.</span></span> <span data-ttu-id="a52ac-110">Wenn dies der Fall ist, klicken Sie dann der gesamte Code, bis die nächste Namespacedeklaration gilt in den ersten Namespace auf.</span><span class="sxs-lookup"><span data-stu-id="a52ac-110">If that is the case, then all code up until the next namespace declaration is considered to be within the first namespace.</span></span>

<span data-ttu-id="a52ac-111">Namespaces können nicht direkt als Werte und Funktionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="a52ac-111">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="a52ac-112">Stattdessen Werte und Funktionen in Modulen enthalten sein müssen, und Module in Namespaces enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a52ac-112">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="a52ac-113">Namespaces kann es sich um Typen, Module enthalten.</span><span class="sxs-lookup"><span data-stu-id="a52ac-113">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="a52ac-114">XML-Dok-Kommentare können über einen Namespace deklariert werden, aber sie werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a52ac-114">XML doc comments can be declared above a namespace, but they're ignored.</span></span> <span data-ttu-id="a52ac-115">Compiler-Direktiven können auch über ein Namespace deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="a52ac-115">Compiler directives can also be declared above a namespace.</span></span>

<span data-ttu-id="a52ac-116">Namespaces können explizit mit dem Schlüsselwort "Namespace" oder implizit deklariert werden, wenn ein Modul zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a52ac-116">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="a52ac-117">Um einen Namespace explizit deklarieren, verwenden Sie das Schlüsselwort "Namespace" gefolgt vom Namespacenamen ein.</span><span class="sxs-lookup"><span data-stu-id="a52ac-117">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="a52ac-118">Das folgende Beispiel zeigt eine Codedatei, die einen Namespace deklariert `Widgets` mit einem Typ und ein Modul, das in diesem Namespace enthalten.</span><span class="sxs-lookup"><span data-stu-id="a52ac-118">The following example shows a code file that declares a namespace `Widgets` with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="a52ac-119">Wenn der gesamte Inhalt der Datei in einem Modul sind, Sie können auch Namespaces deklarieren implizit mithilfe der `module` -Schlüsselwort und den neuen Namespacenamen in der vollqualifizierte Modulname bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a52ac-119">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="a52ac-120">Das folgende Beispiel zeigt eine Codedatei, die einen Namespace deklariert `Widgets` und ein Modul `WidgetsModule`, das eine Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="a52ac-120">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="a52ac-121">Der folgende Code entspricht dem vorangehenden Code, aber das Modul ist eine lokale Moduldeklaration.</span><span class="sxs-lookup"><span data-stu-id="a52ac-121">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="a52ac-122">In diesem Fall muss der Namespace in einer eigenen Zeile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a52ac-122">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="a52ac-123">Wenn mehr als einem Modul in der gleichen Datei in einem oder mehreren Namespaces erforderlich ist, müssen Sie die Deklarationen der lokalen Modul verwenden.</span><span class="sxs-lookup"><span data-stu-id="a52ac-123">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="a52ac-124">Bei Verwendung von lokalen Moduldeklarationen können nicht Sie den vollqualifizierten Namespace in den Moduldeklarationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a52ac-124">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="a52ac-125">Der folgende Code zeigt eine Datei, die eine Namespacedeklaration und zwei lokale Moduldeklarationen verfügt.</span><span class="sxs-lookup"><span data-stu-id="a52ac-125">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="a52ac-126">In diesem Fall sind die Module direkt im Namespace enthalten. Es gibt keine implizit erstelltes Modul, das den gleichen Namen wie die Datei hat.</span><span class="sxs-lookup"><span data-stu-id="a52ac-126">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="a52ac-127">Jeder andere code in die Datei, z. B. eine `do` binden, ist im Namespace, jedoch nicht in der inneren Module, daher Sie die Modulmember qualifizieren müssen `widgetFunction` mit den Namen des Moduls.</span><span class="sxs-lookup"><span data-stu-id="a52ac-127">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="a52ac-128">Die Ausgabe dieses Beispiels ist wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="a52ac-128">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="a52ac-129">Weitere Informationen finden Sie unter [Module](modules.md).</span><span class="sxs-lookup"><span data-stu-id="a52ac-129">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="a52ac-130">Geschachtelte Namespaces</span><span class="sxs-lookup"><span data-stu-id="a52ac-130">Nested Namespaces</span></span>

<span data-ttu-id="a52ac-131">Wenn Sie einen geschachtelten Namespace erstellen, müssen Sie sie vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="a52ac-131">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="a52ac-132">Andernfalls erstellen Sie einen neuen Namespace der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="a52ac-132">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="a52ac-133">Einzug wird in Namespacedeklarationen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a52ac-133">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="a52ac-134">Das folgende Beispiel zeigt, wie Sie einen geschachtelten Namespace zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a52ac-134">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="a52ac-135">Namespaces in Dateien und Assemblys</span><span class="sxs-lookup"><span data-stu-id="a52ac-135">Namespaces in Files and Assemblies</span></span>

<span data-ttu-id="a52ac-136">Namespaces können mehrere Dateien in einem einzelnen Projekt oder die Kompilierung umfassen.</span><span class="sxs-lookup"><span data-stu-id="a52ac-136">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="a52ac-137">Der Begriff *Namespacefragment* beschreibt den Teil eines Namespace, die in einer Datei enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="a52ac-137">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="a52ac-138">Namespaces können auch mehrere Assemblys umfassen.</span><span class="sxs-lookup"><span data-stu-id="a52ac-138">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="a52ac-139">Z. B. die `System` Namespace enthält die gesamte .NET Framework, die viele Assemblys umfasst, und viele geschachtelte Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="a52ac-139">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>

## <a name="global-namespace"></a><span data-ttu-id="a52ac-140">Globaler Namespace</span><span class="sxs-lookup"><span data-stu-id="a52ac-140">Global Namespace</span></span>

<span data-ttu-id="a52ac-141">Sie verwenden den vordefinierten Namespace `global` setzen Sie die Namen in den obersten Namespace von .NET.</span><span class="sxs-lookup"><span data-stu-id="a52ac-141">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="a52ac-142">Sie können auch globale verwenden, z. B. den Namespace der obersten Ebene .NET zu verweisen, um Namenskonflikte mit anderen Namespaces zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="a52ac-142">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="a52ac-143">Rekursive-namespaces</span><span class="sxs-lookup"><span data-stu-id="a52ac-143">Recursive namespaces</span></span>

<span data-ttu-id="a52ac-144">Namespaces können auch als rekursiv, um alle enthaltenen Code gegenseitig rekursiver ermöglichen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="a52ac-144">Namespaces can also be declared as recursive to allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="a52ac-145">Dies erfolgt über `namespace rec`.</span><span class="sxs-lookup"><span data-stu-id="a52ac-145">This is done via `namespace rec`.</span></span> <span data-ttu-id="a52ac-146">Verwenden von `namespace rec` können einige Probleme, nicht mehr zum Schreiben von Code für sich gegenseitig referenzielle Typen und Module verringern.</span><span class="sxs-lookup"><span data-stu-id="a52ac-146">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span> <span data-ttu-id="a52ac-147">Im folgenden finden ein Beispiel hierfür:</span><span class="sxs-lookup"><span data-stu-id="a52ac-147">The following is an example of this:</span></span>

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

<span data-ttu-id="a52ac-148">Beachten Sie, dass die Ausnahme `DontSqueezeTheBananaException` und die Klasse `Banana` beide sich aufeinander beziehen.</span><span class="sxs-lookup"><span data-stu-id="a52ac-148">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="a52ac-149">Darüber hinaus das Modul `BananaHelpers` und die Klasse `Banana` auch sich aufeinander beziehen.</span><span class="sxs-lookup"><span data-stu-id="a52ac-149">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span> <span data-ttu-id="a52ac-150">Wäre dies nicht möglich, die in Ausdrücken F# , wenn Sie entfernt die `rec` -Schlüsselwort aus der `MutualReferences` Namespace.</span><span class="sxs-lookup"><span data-stu-id="a52ac-150">This wouldn't be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="a52ac-151">Dieses Feature ist auch verfügbar für die obersten Ebene [Module](modules.md).</span><span class="sxs-lookup"><span data-stu-id="a52ac-151">This feature is also available for top-level [Modules](modules.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a52ac-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a52ac-152">See also</span></span>

- [<span data-ttu-id="a52ac-153">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="a52ac-153">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="a52ac-154">Module</span><span class="sxs-lookup"><span data-stu-id="a52ac-154">Modules</span></span>](modules.md)
- [<span data-ttu-id="a52ac-155">F#RFC-FS-1009 – lassen Sie sich gegenseitig referenzielle Typen und Module über größere Bereiche in Dateien</span><span class="sxs-lookup"><span data-stu-id="a52ac-155">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
