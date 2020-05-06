---
title: Module
description: 'Erfahren Sie, wie ein f #-Modul eine Gruppierung von f #-Code (z. b. Werte, Typen und Funktions Werte) in einem f #-Programm ist.'
ms.date: 04/24/2017
ms.openlocfilehash: 5f99bbd8069478bf0c7db2800ae545f31926728a
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794363"
---
# <a name="modules"></a><span data-ttu-id="e6ccf-103">Module</span><span class="sxs-lookup"><span data-stu-id="e6ccf-103">Modules</span></span>

<span data-ttu-id="e6ccf-104">Im Kontext der Sprache f # ist ein *Modul* eine Gruppierung von f #-Code, wie z. b. Werte, Typen und Funktions Werte in einem F #-Programm.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-104">In the context of the F# language, a *module* is a grouping of F# code, such as values, types, and function values, in an F# program.</span></span> <span data-ttu-id="e6ccf-105">Das Gruppieren von Code in Modulen hilft dabei, verwandten Code zusammen zu halten und Namenskonflikte in Ihrem Programm zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-105">Grouping code in modules helps keep related code together and helps avoid name conflicts in your program.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6ccf-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6ccf-106">Syntax</span></span>

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a><span data-ttu-id="e6ccf-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6ccf-107">Remarks</span></span>

<span data-ttu-id="e6ccf-108">Ein f #-Modul ist eine Gruppierung von f #-Codekonstrukten, z. b. Typen, Werte, `do` Funktions Werte und Code in Bindungen.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-108">An F# module is a grouping of F# code constructs such as types, values, function values, and code in `do` bindings.</span></span> <span data-ttu-id="e6ccf-109">Sie wird als Common Language Runtime (CLR)-Klasse implementiert, die nur statische Member aufweist.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-109">It is implemented as a common language runtime (CLR) class that has only static members.</span></span> <span data-ttu-id="e6ccf-110">Je nachdem, ob die gesamte Datei im Modul enthalten ist, gibt es zwei Arten von Modul Deklarationen: eine Modul Deklaration der obersten Ebene und eine lokale Modul Deklaration.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-110">There are two types of module declarations, depending on whether the whole file is included in the module: a top-level module declaration and a local module declaration.</span></span> <span data-ttu-id="e6ccf-111">Eine Modul Deklaration der obersten Ebene enthält die gesamte Datei im Modul.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-111">A top-level module declaration includes the whole file in the module.</span></span> <span data-ttu-id="e6ccf-112">Eine Modul Deklaration der obersten Ebene kann nur als erste Deklaration in einer Datei angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-112">A top-level module declaration can appear only as the first declaration in a file.</span></span>

<span data-ttu-id="e6ccf-113">In der Syntax für die Modul Deklaration der obersten Ebene ist der optionale *qualified-Namespace* die Sequenz von Namen in den Namen des in der Tabelle enthaltenen Namespace, die das Modul enthält.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-113">In the syntax for the top-level module declaration, the optional *qualified-namespace* is the sequence of nested namespace names that contains the module.</span></span> <span data-ttu-id="e6ccf-114">Der qualifizierte Namespace muss nicht zuvor deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-114">The qualified namespace does not have to be previously declared.</span></span>

<span data-ttu-id="e6ccf-115">Sie müssen keine Deklarationen in einem Modul der obersten Ebene einfügen.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-115">You do not have to indent declarations in a top-level module.</span></span> <span data-ttu-id="e6ccf-116">Sie müssen alle Deklarationen in lokalen Modulen einziehen.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-116">You do have to indent all declarations in local modules.</span></span> <span data-ttu-id="e6ccf-117">In einer lokalen Modul Deklaration sind nur die Deklarationen, die in dieser Modul Deklaration eingezogen werden, Teil des Moduls.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-117">In a local module declaration, only the declarations that are indented under that module declaration are part of the module.</span></span>

<span data-ttu-id="e6ccf-118">Wenn eine Codedatei nicht mit einer Modul Deklaration der obersten Ebene oder einer Namespace Deklaration beginnt, wird der gesamte Inhalt der Datei, einschließlich aller lokalen Module, Teil eines implizit erstellten Moduls auf oberster Ebene, das denselben Namen wie die Datei hat, ohne die Erweiterung, wobei der erste Buchstabe in Großbuchstaben konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-118">If a code file does not begin with a top-level module declaration or a namespace declaration, the whole contents of the file, including any local modules, becomes part of an implicitly created top-level module that has the same name as the file, without the extension, with the first letter converted to uppercase.</span></span> <span data-ttu-id="e6ccf-119">Sehen Sie sich beispielsweise die folgende Datei an.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-119">For example, consider the following file.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6601.fs)]

<span data-ttu-id="e6ccf-120">Diese Datei würde so kompiliert werden, als ob Sie auf diese Weise geschrieben würde:</span><span class="sxs-lookup"><span data-stu-id="e6ccf-120">This file would be compiled as if it were written in this manner:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6602.fs)]

<span data-ttu-id="e6ccf-121">Wenn Sie über mehrere Module in einer Datei verfügen, müssen Sie für jedes Modul eine lokale Modul Deklaration verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-121">If you have multiple modules in a file, you must use a local module declaration for each module.</span></span> <span data-ttu-id="e6ccf-122">Wenn ein einschließender Namespace deklariert wird, sind diese Module Teil des einschließenden Namespace.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-122">If an enclosing namespace is declared, these modules are part of the enclosing namespace.</span></span> <span data-ttu-id="e6ccf-123">Wenn kein einschließender Namespace deklariert wird, werden die Module Teil des implizit erstellten Moduls der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-123">If an enclosing namespace is not declared, the modules become part of the implicitly created top-level module.</span></span> <span data-ttu-id="e6ccf-124">Das folgende Codebeispiel zeigt eine Codedatei, die mehrere Module enthält.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-124">The following code example shows a code file that contains multiple modules.</span></span> <span data-ttu-id="e6ccf-125">Der Compiler erstellt implizit ein Modul der obersten Ebene mit `Multiplemodules`dem Namen `MyModule1` , `MyModule2` und und sind in diesem Modul der obersten Ebene eingebettet.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-125">The compiler implicitly creates a top-level module named `Multiplemodules`, and `MyModule1` and `MyModule2` are nested in that top-level module.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6603.fs)]

<span data-ttu-id="e6ccf-126">Wenn Sie über mehrere Dateien in einem Projekt oder einer einzelnen Kompilierung verfügen oder wenn Sie eine Bibliothek erstellt haben, müssen Sie am Anfang der Datei eine Namespace Deklaration oder Modul Deklaration einschließen.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-126">If you have multiple files in a project or in a single compilation, or if you are building a library, you must include a namespace declaration or module declaration at the top of the file.</span></span> <span data-ttu-id="e6ccf-127">Der F #-Compiler bestimmt einen Modulnamen nur implizit, wenn sich nur eine Datei in einer Projekt-oder Kompilierungs Befehlszeile befindet und Sie eine Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-127">The F# compiler only determines a module name implicitly when there is only one file in a project or compilation command line, and you are creating an application.</span></span>

<span data-ttu-id="e6ccf-128">Der Zugriffsmodifizierer kann eine der folgenden `public`sein `private`: `internal`,,. *accessibility-modifier*</span><span class="sxs-lookup"><span data-stu-id="e6ccf-128">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="e6ccf-129">Weitere Informationen finden Sie unter [Zugriffssteuerung](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="e6ccf-129">For more information, see [Access Control](access-control.md).</span></span> <span data-ttu-id="e6ccf-130">Der Standardwert ist public.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-130">The default is public.</span></span>

## <a name="referencing-code-in-modules"></a><span data-ttu-id="e6ccf-131">Verweisen auf Code in Modulen</span><span class="sxs-lookup"><span data-stu-id="e6ccf-131">Referencing Code in Modules</span></span>

<span data-ttu-id="e6ccf-132">Wenn Sie auf Funktionen, Typen und Werte eines anderen Moduls verweisen, müssen Sie entweder einen qualifizierten Namen verwenden oder das Modul öffnen.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-132">When you reference functions, types, and values from another module, you must either use a qualified name or open the module.</span></span> <span data-ttu-id="e6ccf-133">Wenn Sie einen qualifizierten Namen verwenden, müssen Sie die Namespaces, das Modul und den Bezeichner für das gewünschte Programmelement angeben.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-133">If you use a qualified name, you must specify the namespaces, the module, and the identifier for the program element you want.</span></span> <span data-ttu-id="e6ccf-134">Sie trennen die einzelnen Teile des qualifizierten Pfades wie folgt durch einen Punkt (.).</span><span class="sxs-lookup"><span data-stu-id="e6ccf-134">You separate each part of the qualified path with a dot (.), as follows.</span></span>

`Namespace1.Namespace2.ModuleName.Identifier`

<span data-ttu-id="e6ccf-135">Sie können das Modul oder einen oder mehrere Namespaces öffnen, um den Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-135">You can open the module or one or more of the namespaces to simplify the code.</span></span> <span data-ttu-id="e6ccf-136">Weitere Informationen zum Öffnen von Namespaces und Modulen finden Sie unter [Import Deklarationen `open` : das-Schlüsselwort](import-declarations-the-open-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="e6ccf-136">For more information about opening namespaces and modules, see [Import Declarations: The `open` Keyword](import-declarations-the-open-keyword.md).</span></span>

<span data-ttu-id="e6ccf-137">Das folgende Codebeispiel zeigt ein Modul der obersten Ebene, das den gesamten Code bis zum Ende der Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-137">The following code example shows a top-level module that contains all the code up to the end of the file.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6604.fs)]

<span data-ttu-id="e6ccf-138">Wenn Sie diesen Code aus einer anderen Datei im selben Projekt verwenden möchten, verwenden Sie entweder qualifizierte Namen, oder öffnen Sie das Modul, bevor Sie die Funktionen verwenden, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-138">To use this code from another file in the same project, you either use qualified names or you open the module before you use the functions, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a><span data-ttu-id="e6ccf-139">Geduckte Module</span><span class="sxs-lookup"><span data-stu-id="e6ccf-139">Nested Modules</span></span>

<span data-ttu-id="e6ccf-140">Module können eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-140">Modules can be nested.</span></span> <span data-ttu-id="e6ccf-141">Innere Module müssen in den Deklarationen äußerer Module eingezogen werden, um anzugeben, dass es sich um interne Module, nicht um neue Module handelt.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-141">Inner modules must be indented as far as outer module declarations to indicate that they are inner modules, not new modules.</span></span> <span data-ttu-id="e6ccf-142">Vergleichen Sie beispielsweise die folgenden beiden Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-142">For example, compare the following two examples.</span></span> <span data-ttu-id="e6ccf-143">Das `Z` Modul ist ein internes Modul im folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-143">Module `Z` is an inner module in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6607.fs)]

<span data-ttu-id="e6ccf-144">Das Modul `Z` ist aber ein gleich geordnetes Modul `Y` im folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-144">But module `Z` is a sibling to module `Y` in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6608.fs)]
<span data-ttu-id="e6ccf-145">Das `Z` Modul ist auch ein gleich geordnetes Modul im folgenden Code, da es nicht in das Modul eingefügt wird, das nicht in das `Y`Modul eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-145">Module `Z` is also a sibling module in the following code, because it is not indented as far as other declarations in module `Y`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6609.fs)]
<span data-ttu-id="e6ccf-146">Wenn das äußere Modul keine Deklarationen hat und unmittelbar eine andere Modul Deklaration folgt, wird angenommen, dass es sich bei der neuen Modul Deklaration um ein internes Modul handelt, aber der Compiler warnt Sie, wenn die zweite Modul Definition nicht weiter als die erste eingezogen ist.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-146">Finally, if the outer module has no declarations and is followed immediately by another module declaration, the new module declaration is assumed to be an inner module, but the compiler will warn you if the second module definition is not indented farther than the first.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6610.fs)]
<span data-ttu-id="e6ccf-147">Um die Warnung auszuschließen, einziehen Sie das innere Modul.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-147">To eliminate the warning, indent the inner module.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6611.fs)]
<span data-ttu-id="e6ccf-148">Wenn sich der gesamte Code in einer Datei in einem einzelnen äußeren Modul befinden soll und Sie innere Module benötigen, benötigt das äußere Modul nicht das Gleichheitszeichen, und die Deklarationen, einschließlich aller inneren Modul Deklarationen, die im äußeren Modul enthalten sind, müssen nicht eingezogen werden.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-148">If you want all the code in a file to be in a single outer module and you want inner modules, the outer module does not require the equal sign, and the declarations, including any inner module declarations, that will go in the outer module do not have to be indented.</span></span> <span data-ttu-id="e6ccf-149">Deklarationen innerhalb der inneren Modul Deklarationen müssen eingezogen werden.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-149">Declarations inside the inner module declarations do have to be indented.</span></span> <span data-ttu-id="e6ccf-150">Der folgende Code zeigt diesen Fall.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-150">The following code shows this case.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a><span data-ttu-id="e6ccf-151">Rekursive Module</span><span class="sxs-lookup"><span data-stu-id="e6ccf-151">Recursive modules</span></span>

<span data-ttu-id="e6ccf-152">F # 4,1 führt das Konzept von Modulen ein, die es ermöglichen, dass der gesamte enthaltene Code gegenseitig rekursiv ist.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-152">F# 4.1 introduces the notion of modules which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="e6ccf-153">Dies erfolgt über `module rec`.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-153">This is done via `module rec`.</span></span>  <span data-ttu-id="e6ccf-154">Die Verwendung `module rec` von kann einige Probleme verringern, die sich nicht gegenseitig referenziellen Code zwischen Typen und Modulen schreiben können.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-154">Use of `module rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="e6ccf-155">Im folgenden finden Sie ein Beispiel hierfür:</span><span class="sxs-lookup"><span data-stu-id="e6ccf-155">The following is an example of this:</span></span>

```fsharp
module rec RecursiveModule =
    type Orientation = Up | Down
    type PeelState = Peeled | Unpeeled

    // This exception depends on the type below.
    exception DontSqueezeTheBananaException of Banana

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

<span data-ttu-id="e6ccf-156">Beachten Sie, dass `DontSqueezeTheBananaException` die Ausnahme und `Banana` die Klasse beide aufeinander verweisen.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-156">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="e6ccf-157">Darüber hinaus verweisen das `BananaHelpers` Modul und die `Banana` Klasse auch aufeinander.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-157">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="e6ccf-158">Dies wäre in F # nicht möglich, wenn Sie das `rec` -Schlüsselwort aus dem `RecursiveModule` Modul entfernt haben.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-158">This would not be possible to express in F# if you removed the `rec` keyword from the `RecursiveModule` module.</span></span>

<span data-ttu-id="e6ccf-159">Diese Funktion ist auch in [Namespaces](namespaces.md) mit F # 4,1 möglich.</span><span class="sxs-lookup"><span data-stu-id="e6ccf-159">This capability is also possible in [Namespaces](namespaces.md) with F# 4.1.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6ccf-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e6ccf-160">See also</span></span>

- [<span data-ttu-id="e6ccf-161">F #-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="e6ccf-161">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="e6ccf-162">Namespaces</span><span class="sxs-lookup"><span data-stu-id="e6ccf-162">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="e6ccf-163">F # RFC FS-1009-zulassen von sich gegenseitig referenziellen Typen und Modulen über größere Bereiche innerhalb von Dateien</span><span class="sxs-lookup"><span data-stu-id="e6ccf-163">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
