---
title: Module (F#)
description: Erfahren Sie, wie eine f#-Modul eine Gruppierung von F#-Code, z. B. Werte, Typen und Funktionswerte in einem F#-Programm.
ms.date: 04/24/2017
ms.openlocfilehash: fb0aa1d508d1141933b4fbdf10633f67ed078dc7
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44705124"
---
# <a name="modules"></a><span data-ttu-id="c9057-103">Module</span><span class="sxs-lookup"><span data-stu-id="c9057-103">Modules</span></span>

<span data-ttu-id="c9057-104">Im Rahmen der Sprache f# eine *Modul* ist eine Gruppierung von F#-Code, z. B. Werte, Typen und Funktionswerte in einem F#-Programm.</span><span class="sxs-lookup"><span data-stu-id="c9057-104">In the context of the F# language, a *module* is a grouping of F# code, such as values, types, and function values, in an F# program.</span></span> <span data-ttu-id="c9057-105">Das Gruppieren von Code in Modulen hilft dabei, verwandten Code zusammen zu halten und Namenskonflikte in Ihrem Programm zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="c9057-105">Grouping code in modules helps keep related code together and helps avoid name conflicts in your program.</span></span>

## <a name="syntax"></a><span data-ttu-id="c9057-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9057-106">Syntax</span></span>

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a><span data-ttu-id="c9057-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c9057-107">Remarks</span></span>

<span data-ttu-id="c9057-108">Eine f#-Modul ist eine Gruppierung von F#-Code-Konstrukte wie Typen, Werte, Werte von Funktionen und -Code in `do` Bindungen.</span><span class="sxs-lookup"><span data-stu-id="c9057-108">An F# module is a grouping of F# code constructs such as types, values, function values, and code in `do` bindings.</span></span> <span data-ttu-id="c9057-109">Es wird als eine common Language Runtime (CLR)-Klasse implementiert, die nur statische Member verfügt.</span><span class="sxs-lookup"><span data-stu-id="c9057-109">It is implemented as a common language runtime (CLR) class that has only static members.</span></span> <span data-ttu-id="c9057-110">Es gibt zwei Arten von Moduldeklarationen, je nachdem, ob die gesamte Datei im Modul enthalten ist: eine Moduldeklaration der obersten Ebene und einem lokalen Modul-Deklaration.</span><span class="sxs-lookup"><span data-stu-id="c9057-110">There are two types of module declarations, depending on whether the whole file is included in the module: a top-level module declaration and a local module declaration.</span></span> <span data-ttu-id="c9057-111">Eine Deklaration Modul auf oberster Ebene enthält die gesamte Datei im Modul an.</span><span class="sxs-lookup"><span data-stu-id="c9057-111">A top-level module declaration includes the whole file in the module.</span></span> <span data-ttu-id="c9057-112">Eine Moduldeklaration auf oberster Ebene kann nur als die erste Deklaration in einer Datei angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c9057-112">A top-level module declaration can appear only as the first declaration in a file.</span></span>

<span data-ttu-id="c9057-113">In der Syntax für die Deklaration Modul auf oberster Ebene, die den optionalen *qualifizierter Namespace* ist die Sequenz der geschachtelten Namespace-Namen, die das Modul enthält.</span><span class="sxs-lookup"><span data-stu-id="c9057-113">In the syntax for the top-level module declaration, the optional *qualified-namespace* is the sequence of nested namespace names that contains the module.</span></span> <span data-ttu-id="c9057-114">Die vollqualifizierten Namespace muss nicht zuvor deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="c9057-114">The qualified namespace does not have to be previously declared.</span></span>

<span data-ttu-id="c9057-115">Sie müssen keinen Deklarationen in einem Modul auf oberster Ebene eingezogen.</span><span class="sxs-lookup"><span data-stu-id="c9057-115">You do not have to indent declarations in a top-level module.</span></span> <span data-ttu-id="c9057-116">Sie müssen alle Deklarationen in den lokalen Modulen einziehen.</span><span class="sxs-lookup"><span data-stu-id="c9057-116">You do have to indent all declarations in local modules.</span></span> <span data-ttu-id="c9057-117">In der Deklaration einer lokalen Modul sind nur Deklarationen, die unter diesem Moduldeklaration eingezogen werden Teil des Moduls.</span><span class="sxs-lookup"><span data-stu-id="c9057-117">In a local module declaration, only the declarations that are indented under that module declaration are part of the module.</span></span>

<span data-ttu-id="c9057-118">Wenn Sie eine Codedatei mit einer Deklaration Modul auf oberster Ebene oder eine Namespacedeklaration nicht startet, wird der gesamte Inhalt der Datei, einschließlich lokalen Module, Teil einer implizit erstellten Modul auf oberster Ebene, die den gleichen Namen wie die Datei ohne Erweiterung hat, mit dem ersten Buchstaben in Großbuchstaben konvertiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c9057-118">If a code file does not begin with a top-level module declaration or a namespace declaration, the whole contents of the file, including any local modules, becomes part of an implicitly created top-level module that has the same name as the file, without the extension, with the first letter converted to uppercase.</span></span> <span data-ttu-id="c9057-119">Betrachten Sie beispielsweise die folgende Datei aus.</span><span class="sxs-lookup"><span data-stu-id="c9057-119">For example, consider the following file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6601.fs)]

<span data-ttu-id="c9057-120">Diese Datei würde kompiliert werden, als ob sie auf diese Weise geschrieben wurden:</span><span class="sxs-lookup"><span data-stu-id="c9057-120">This file would be compiled as if it were written in this manner:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6602.fs)]

<span data-ttu-id="c9057-121">Wenn Sie mehrere Module in einer Datei haben, müssen Sie eine lokale Moduldeklaration für jedes Modul verwenden.</span><span class="sxs-lookup"><span data-stu-id="c9057-121">If you have multiple modules in a file, you must use a local module declaration for each module.</span></span> <span data-ttu-id="c9057-122">Wenn ein einschließenden Namespace deklariert wird, sind diese Module Teil des einschließenden Namespace an.</span><span class="sxs-lookup"><span data-stu-id="c9057-122">If an enclosing namespace is declared, these modules are part of the enclosing namespace.</span></span> <span data-ttu-id="c9057-123">Wenn Sie ein Namespace des einschließender nicht deklariert ist, werden die Module des Moduls implizit erstellten auf oberster Ebene.</span><span class="sxs-lookup"><span data-stu-id="c9057-123">If an enclosing namespace is not declared, the modules become part of the implicitly created top-level module.</span></span> <span data-ttu-id="c9057-124">Das folgende Codebeispiel zeigt eine Codedatei, die mehrere Module enthält.</span><span class="sxs-lookup"><span data-stu-id="c9057-124">The following code example shows a code file that contains multiple modules.</span></span> <span data-ttu-id="c9057-125">Erstellt der Compiler implizit ein Modul auf oberster Ebene mit dem Namen `Multiplemodules`, und `MyModule1` und `MyModule2` in diesem Modul auf oberster Ebene geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="c9057-125">The compiler implicitly creates a top-level module named `Multiplemodules`, and `MyModule1` and `MyModule2` are nested in that top-level module.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6603.fs)]

<span data-ttu-id="c9057-126">Wenn Sie mehrere Dateien in einem Projekt oder in einer einzigen Kompilierung haben oder wenn Sie eine Bibliothek erstellen, müssen Sie einen Standardnamespace-Deklaration oder Moduldeklaration am Anfang der Datei einschließen.</span><span class="sxs-lookup"><span data-stu-id="c9057-126">If you have multiple files in a project or in a single compilation, or if you are building a library, you must include a namespace declaration or module declaration at the top of the file.</span></span> <span data-ttu-id="c9057-127">F#-Compiler bestimmt einen Modulnamen nur implizit, wenn es nur eine Datei in einer Befehlszeile Projekt oder die Kompilierung, und Sie eine Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="c9057-127">The F# compiler only determines a module name implicitly when there is only one file in a project or compilation command line, and you are creating an application.</span></span>

<span data-ttu-id="c9057-128">Die *Zugriffsmodifizierer* kann einen der folgenden sein: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="c9057-128">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="c9057-129">Weitere Informationen finden Sie unter [Zugriffssteuerung](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="c9057-129">For more information, see [Access Control](access-control.md).</span></span> <span data-ttu-id="c9057-130">Der Standardwert ist „öffentlich“.</span><span class="sxs-lookup"><span data-stu-id="c9057-130">The default is public.</span></span>

## <a name="referencing-code-in-modules"></a><span data-ttu-id="c9057-131">Verweisen auf Code in Modulen</span><span class="sxs-lookup"><span data-stu-id="c9057-131">Referencing Code in Modules</span></span>

<span data-ttu-id="c9057-132">Wenn Sie Funktionen, Typen und Werte aus einem anderen Modul verweisen, müssen Sie einen qualifizierten Namen verwenden oder öffnen Sie das Modul.</span><span class="sxs-lookup"><span data-stu-id="c9057-132">When you reference functions, types, and values from another module, you must either use a qualified name or open the module.</span></span> <span data-ttu-id="c9057-133">Wenn Sie einen qualifizierten Namen verwenden, müssen Sie angeben, die Namespaces, die das Modul und der Bezeichner für das gewünschte Programmelement.</span><span class="sxs-lookup"><span data-stu-id="c9057-133">If you use a qualified name, you must specify the namespaces, the module, and the identifier for the program element you want.</span></span> <span data-ttu-id="c9057-134">Sie trennen Sie jedes Teil des vollqualifizierten Pfads durch einen Punkt (.), wie folgt.</span><span class="sxs-lookup"><span data-stu-id="c9057-134">You separate each part of the qualified path with a dot (.), as follows.</span></span>

`Namespace1.Namespace2.ModuleName.Identifier`

<span data-ttu-id="c9057-135">Öffnen Sie das Modul oder eine oder mehrere Namespaces auf den Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="c9057-135">You can open the module or one or more of the namespaces to simplify the code.</span></span> <span data-ttu-id="c9057-136">Weitere Informationen zum Öffnen von Namespaces und Modulen finden Sie unter [Importdeklarationen: das `open` Schlüsselwort](import-declarations-the-open-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="c9057-136">For more information about opening namespaces and modules, see [Import Declarations: The `open` Keyword](import-declarations-the-open-keyword.md).</span></span>

<span data-ttu-id="c9057-137">Im folgenden Codebeispiel wird veranschaulicht, ein Modul auf oberster Ebene, die der gesamte Code bis zum Ende der Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="c9057-137">The following code example shows a top-level module that contains all the code up to the end of the file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6604.fs)]

<span data-ttu-id="c9057-138">Um diesen Code aus einer anderen Datei im gleichen Projekt verwenden, Sie qualifizierte Namen verwenden, oder Sie öffnen das Modul vor der Verwendung der Funktionen, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c9057-138">To use this code from another file in the same project, you either use qualified names or you open the module before you use the functions, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a><span data-ttu-id="c9057-139">Geschachtelte Module</span><span class="sxs-lookup"><span data-stu-id="c9057-139">Nested Modules</span></span>

<span data-ttu-id="c9057-140">Module können geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="c9057-140">Modules can be nested.</span></span> <span data-ttu-id="c9057-141">Inneren Module müssen eingezogen werden, so weit wie die äußere Moduldeklarationen, um anzugeben, dass sie die inneren Module, nicht um neue Module sind.</span><span class="sxs-lookup"><span data-stu-id="c9057-141">Inner modules must be indented as far as outer module declarations to indicate that they are inner modules, not new modules.</span></span> <span data-ttu-id="c9057-142">Vergleichen Sie beispielsweise die folgenden beiden Beispiele.</span><span class="sxs-lookup"><span data-stu-id="c9057-142">For example, compare the following two examples.</span></span> <span data-ttu-id="c9057-143">Modul `Z` ist ein inneres Modul in den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="c9057-143">Module `Z` is an inner module in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6607.fs)]

<span data-ttu-id="c9057-144">Aber Modul `Z` ein gleichgeordnetes Element Modul `Y` in den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="c9057-144">But module `Z` is a sibling to module `Y` in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6608.fs)]
<span data-ttu-id="c9057-145">Modul `Z` ist auch ein gleichgeordnetes Element-Modul in den folgenden Code, da sie nicht so weit wie die anderen Deklarationen in Modul eingezogen ist `Y`.</span><span class="sxs-lookup"><span data-stu-id="c9057-145">Module `Z` is also a sibling module in the following code, because it is not indented as far as other declarations in module `Y`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6609.fs)]
<span data-ttu-id="c9057-146">Schließlich, wenn das äußere Modul verfügt über keine Deklarationen, unmittelbar, von einem anderen Moduldeklaration gefolgt wird wird angenommen, dass der neue Moduldeklaration ein inneres Modul werden, aber der Compiler warnt Sie, wenn die zweite Moduldefinition konsequenter als nicht eingezogen ist die erste.</span><span class="sxs-lookup"><span data-stu-id="c9057-146">Finally, if the outer module has no declarations and is followed immediately by another module declaration, the new module declaration is assumed to be an inner module, but the compiler will warn you if the second module definition is not indented farther than the first.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6610.fs)]
<span data-ttu-id="c9057-147">Um die Warnung zu vermeiden, Rücken Sie das innere-Modul.</span><span class="sxs-lookup"><span data-stu-id="c9057-147">To eliminate the warning, indent the inner module.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6611.fs)]
<span data-ttu-id="c9057-148">Wenn Sie sich der gesamte Code in einer Datei in ein einzelnes Modul des äußeren und inneren Module angezeigt werden sollen, das äußere Modul erfordert nicht das Gleichheitszeichen und die Deklarationen, einschließlich möglichen Moduldeklarationen inneren-, die in das äußere Modul gespeichert werden müssen nicht mit Einzug dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c9057-148">If you want all the code in a file to be in a single outer module and you want inner modules, the outer module does not require the equal sign, and the declarations, including any inner module declarations, that will go in the outer module do not have to be indented.</span></span> <span data-ttu-id="c9057-149">Deklarationen innerhalb der inneren Moduldeklarationen eingezogen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c9057-149">Declarations inside the inner module declarations do have to be indented.</span></span> <span data-ttu-id="c9057-150">Der folgende Code zeigt diesen Fall.</span><span class="sxs-lookup"><span data-stu-id="c9057-150">The following code shows this case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a><span data-ttu-id="c9057-151">Rekursive Module</span><span class="sxs-lookup"><span data-stu-id="c9057-151">Recursive modules</span></span>

<span data-ttu-id="c9057-152">F# 4.1 führt das Konzept der Module ein, die für alle enthaltenen Code gegenseitig rekursiver sein können.</span><span class="sxs-lookup"><span data-stu-id="c9057-152">F# 4.1 introduces the notion of modules which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="c9057-153">Dies erfolgt über `module rec`.</span><span class="sxs-lookup"><span data-stu-id="c9057-153">This is done via `module rec`.</span></span>  <span data-ttu-id="c9057-154">Verwenden von `module rec` können einige Probleme, nicht mehr zum Schreiben von Code für sich gegenseitig referenzielle Typen und Module verringern.</span><span class="sxs-lookup"><span data-stu-id="c9057-154">Use of `module rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="c9057-155">Im folgenden finden ein Beispiel hierfür:</span><span class="sxs-lookup"><span data-stu-id="c9057-155">The following is an example of this:</span></span>

```fsharp
module rec RecursiveModule =
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

<span data-ttu-id="c9057-156">Beachten Sie, dass die Ausnahme `DontSqueezeTheBananaException` und die Klasse `Banana` beide sich aufeinander beziehen.</span><span class="sxs-lookup"><span data-stu-id="c9057-156">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="c9057-157">Darüber hinaus das Modul `BananaHelpers` und die Klasse `Banana` auch sich aufeinander beziehen.</span><span class="sxs-lookup"><span data-stu-id="c9057-157">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="c9057-158">Dies ist nicht möglich, die in f# zu express, wenn Sie entfernt die `rec` -Schlüsselwort aus der `RecursiveModule` Modul.</span><span class="sxs-lookup"><span data-stu-id="c9057-158">This would not be possible to express in F# if you removed the `rec` keyword from the `RecursiveModule` module.</span></span>

<span data-ttu-id="c9057-159">Diese Funktion ist auch möglich, im [Namespaces](namespaces.md) mit f# 4.1.</span><span class="sxs-lookup"><span data-stu-id="c9057-159">This capability is also possible in [Namespaces](namespaces.md) with F# 4.1.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9057-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9057-160">See also</span></span>

- [<span data-ttu-id="c9057-161">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="c9057-161">F# Language Reference</span></span>](index.md)  
- [<span data-ttu-id="c9057-162">Namespaces</span><span class="sxs-lookup"><span data-stu-id="c9057-162">Namespaces</span></span>](namespaces.md)  
- [<span data-ttu-id="c9057-163">F#-RFC-FS-1009 – lassen Sie sich gegenseitig referenzielle Typen und Module über größere Bereiche in Dateien</span><span class="sxs-lookup"><span data-stu-id="c9057-163">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)  
