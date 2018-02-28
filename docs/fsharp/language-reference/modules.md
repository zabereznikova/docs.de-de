---
title: Module (F#)
description: Erfahren Sie, wie ein f#-Modul eine Gruppierung von f#-Code, z. B. Werte, Typen und Funktionswerte in einem f#-Programm ist.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 46de2d18-da51-40fa-a262-92edecada79d
ms.openlocfilehash: 9b189903511f53d3ecceb30f3d056e189b00511d
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2018
---
# <a name="modules"></a><span data-ttu-id="c8138-104">Module</span><span class="sxs-lookup"><span data-stu-id="c8138-104">Modules</span></span>

<span data-ttu-id="c8138-105">Im Rahmen der Programmiersprache f# ein *Modul* ist eine Gruppierung von f#-Code, z. B. Werte, Typen und Funktionswerte in einem f#-Programm.</span><span class="sxs-lookup"><span data-stu-id="c8138-105">In the context of the F# language, a *module* is a grouping of F# code, such as values, types, and function values, in an F# program.</span></span> <span data-ttu-id="c8138-106">Das Gruppieren von Code in Modulen hilft dabei, verwandten Code zusammen zu halten und Namenskonflikte in Ihrem Programm zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="c8138-106">Grouping code in modules helps keep related code together and helps avoid name conflicts in your program.</span></span>

## <a name="syntax"></a><span data-ttu-id="c8138-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8138-107">Syntax</span></span>

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a><span data-ttu-id="c8138-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c8138-108">Remarks</span></span>
<span data-ttu-id="c8138-109">Ein f#-Modul ist eine Gruppierung von F#-Code-Konstrukte wie Typen, Werte Funktionswerte und Code in `do` Bindungen.</span><span class="sxs-lookup"><span data-stu-id="c8138-109">An F# module is a grouping of F# code constructs such as types, values, function values, and code in `do` bindings.</span></span> <span data-ttu-id="c8138-110">Es wird als eine common Language Runtime (CLR)-Klasse implementiert, die nur statische Member verfügt.</span><span class="sxs-lookup"><span data-stu-id="c8138-110">It is implemented as a common language runtime (CLR) class that has only static members.</span></span> <span data-ttu-id="c8138-111">Es gibt zwei Arten von Moduldeklarationen, je nachdem, ob die gesamte Datei im Modul enthalten ist: eine Moduldeklaration der obersten Ebene und eine lokale Moduldeklaration.</span><span class="sxs-lookup"><span data-stu-id="c8138-111">There are two types of module declarations, depending on whether the whole file is included in the module: a top-level module declaration and a local module declaration.</span></span> <span data-ttu-id="c8138-112">Eine Moduldeklaration der obersten Ebene enthält die gesamte Datei im Modul an.</span><span class="sxs-lookup"><span data-stu-id="c8138-112">A top-level module declaration includes the whole file in the module.</span></span> <span data-ttu-id="c8138-113">Eine Moduldeklaration der obersten Ebene kann nur als die erste Deklaration in einer Datei angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c8138-113">A top-level module declaration can appear only as the first declaration in a file.</span></span>

<span data-ttu-id="c8138-114">In der Syntax für die Moduldeklaration der obersten Ebene, das optionale *qualifiziert Namespace* ist die Abfolge von geschachtelten Namespace-Namen, die das Modul enthält.</span><span class="sxs-lookup"><span data-stu-id="c8138-114">In the syntax for the top-level module declaration, the optional *qualified-namespace* is the sequence of nested namespace names that contains the module.</span></span> <span data-ttu-id="c8138-115">Die vollqualifizierten Namespace muss nicht zuvor deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="c8138-115">The qualified namespace does not have to be previously declared.</span></span>

<span data-ttu-id="c8138-116">Sie müssen keinen Einzug Deklarationen in einem Modul der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="c8138-116">You do not have to indent declarations in a top-level module.</span></span> <span data-ttu-id="c8138-117">Sie müssen alle Deklarationen in den lokalen Modulen Einzug.</span><span class="sxs-lookup"><span data-stu-id="c8138-117">You do have to indent all declarations in local modules.</span></span> <span data-ttu-id="c8138-118">In einer lokalen Moduldeklaration sind nur die Deklarationen, die unter diesem Moduldeklaration eingerückt sind Teil des Moduls.</span><span class="sxs-lookup"><span data-stu-id="c8138-118">In a local module declaration, only the declarations that are indented under that module declaration are part of the module.</span></span>

<span data-ttu-id="c8138-119">Wenn eine Codedatei nicht mit einer Moduldeklaration der obersten Ebene oder eine Namespacedeklaration beginnt, wird der gesamte Inhalt der Datei, einschließlich lokaler Module, Teil eines implizit erstellten Moduls der obersten Ebene, die den gleichen Namen wie die Datei ohne Erweiterung hat, mit dem ersten Buchstaben in Großbuchstaben konvertiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c8138-119">If a code file does not begin with a top-level module declaration or a namespace declaration, the whole contents of the file, including any local modules, becomes part of an implicitly created top-level module that has the same name as the file, without the extension, with the first letter converted to uppercase.</span></span> <span data-ttu-id="c8138-120">Betrachten Sie beispielsweise die folgende Datei aus.</span><span class="sxs-lookup"><span data-stu-id="c8138-120">For example, consider the following file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6601.fs)]

<span data-ttu-id="c8138-121">Diese Datei würde kompiliert werden, als wäre sie auf diese Weise geschrieben wurden:</span><span class="sxs-lookup"><span data-stu-id="c8138-121">This file would be compiled as if it were written in this manner:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6602.fs)]

<span data-ttu-id="c8138-122">Wenn Sie mehrere Module in einer Datei haben, müssen Sie eine lokale Moduldeklaration für jedes Modul verwenden.</span><span class="sxs-lookup"><span data-stu-id="c8138-122">If you have multiple modules in a file, you must use a local module declaration for each module.</span></span> <span data-ttu-id="c8138-123">Wenn ein einschließender Namespace deklariert ist, sind diese Module Teil des einschließenden Namespace an.</span><span class="sxs-lookup"><span data-stu-id="c8138-123">If an enclosing namespace is declared, these modules are part of the enclosing namespace.</span></span> <span data-ttu-id="c8138-124">Wenn ein einschließender Namespace nicht deklariert ist, werden die Module Teil des implizit erstellten auf oberster Ebene Moduls an.</span><span class="sxs-lookup"><span data-stu-id="c8138-124">If an enclosing namespace is not declared, the modules become part of the implicitly created top-level module.</span></span> <span data-ttu-id="c8138-125">Das folgende Codebeispiel zeigt eine Codedatei, die mehrere Module enthält.</span><span class="sxs-lookup"><span data-stu-id="c8138-125">The following code example shows a code file that contains multiple modules.</span></span> <span data-ttu-id="c8138-126">Der Compiler erstellt implizit ein Modul der obersten Ebene mit dem Namen `Multiplemodules`, und `MyModule1` und `MyModule2` in diesem Modul der obersten Ebene geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="c8138-126">The compiler implicitly creates a top-level module named `Multiplemodules`, and `MyModule1` and `MyModule2` are nested in that top-level module.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6603.fs)]

<span data-ttu-id="c8138-127">Wenn Sie mehrere Dateien in einem Projekt oder in einer einzigen Kompilierung haben oder wenn Sie eine Bibliothek erstellen, müssen Sie eine Namespacedeklaration oder Moduldeklaration am Anfang der Datei einschließen.</span><span class="sxs-lookup"><span data-stu-id="c8138-127">If you have multiple files in a project or in a single compilation, or if you are building a library, you must include a namespace declaration or module declaration at the top of the file.</span></span> <span data-ttu-id="c8138-128">F#-Compiler bestimmt einen Modulnamen nur implizit, wenn nur eine Datei im Projekt oder die Kompilierung über die Befehlszeile vorhanden ist, und Sie eine Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="c8138-128">The F# compiler only determines a module name implicitly when there is only one file in a project or compilation command line, and you are creating an application.</span></span>

<span data-ttu-id="c8138-129">Die *Zugriffsmodifizierer* kann eines der folgenden sein: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="c8138-129">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="c8138-130">Weitere Informationen finden Sie unter [Zugriffssteuerung](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="c8138-130">For more information, see [Access Control](access-control.md).</span></span> <span data-ttu-id="c8138-131">Der Standardwert ist „öffentlich“.</span><span class="sxs-lookup"><span data-stu-id="c8138-131">The default is public.</span></span>


## <a name="referencing-code-in-modules"></a><span data-ttu-id="c8138-132">Verweisen auf Code in Module</span><span class="sxs-lookup"><span data-stu-id="c8138-132">Referencing Code in Modules</span></span>
<span data-ttu-id="c8138-133">Wenn Sie Funktionen, Typen und Werte aus einem anderen Modul verweisen, müssen Sie einen qualifizierten Namen verwenden oder öffnen Sie das Modul.</span><span class="sxs-lookup"><span data-stu-id="c8138-133">When you reference functions, types, and values from another module, you must either use a qualified name or open the module.</span></span> <span data-ttu-id="c8138-134">Wenn Sie einen qualifizierten Namen verwenden, müssen Sie angeben, die Namespaces, das Modul und der Bezeichner für das gewünschte Programmelement.</span><span class="sxs-lookup"><span data-stu-id="c8138-134">If you use a qualified name, you must specify the namespaces, the module, and the identifier for the program element you want.</span></span> <span data-ttu-id="c8138-135">Sie trennen, jeden Teil des vollqualifizierten Pfads mit einem Punkt (.), wie folgt.</span><span class="sxs-lookup"><span data-stu-id="c8138-135">You separate each part of the qualified path with a dot (.), as follows.</span></span>

`Namespace1.Namespace2.ModuleName.Identifier`

<span data-ttu-id="c8138-136">Öffnen Sie das Modul und mindestens eine der Namespaces auf den Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="c8138-136">You can open the module or one or more of the namespaces to simplify the code.</span></span> <span data-ttu-id="c8138-137">Weitere Informationen zum Öffnen von Namespaces und Modulen finden Sie unter [Importdeklarationen: das `open` Schlüsselwort](import-declarations-the-open-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="c8138-137">For more information about opening namespaces and modules, see [Import Declarations: The `open` Keyword](import-declarations-the-open-keyword.md).</span></span>

<span data-ttu-id="c8138-138">Das folgende Codebeispiel zeigt ein auf oberster Ebene Modul, das den Code für die bis zum Ende der Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="c8138-138">The following code example shows a top-level module that contains all the code up to the end of the file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6604.fs)]

<span data-ttu-id="c8138-139">Um diesen Code aus einer anderen Datei im selben Projekt verwenden möchten, verwenden Sie qualifizierte Namen, oder Sie öffnen das Modul vor der Verwendung der Funktionen, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c8138-139">To use this code from another file in the same project, you either use qualified names or you open the module before you use the functions, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a><span data-ttu-id="c8138-140">Geschachtelte Module</span><span class="sxs-lookup"><span data-stu-id="c8138-140">Nested Modules</span></span>
<span data-ttu-id="c8138-141">Module können geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="c8138-141">Modules can be nested.</span></span> <span data-ttu-id="c8138-142">Innere Module müssen eingezogen werden, so weit wie äußere Moduldeklarationen, um anzugeben, dass sie die inneren Module keine neuen Module sind.</span><span class="sxs-lookup"><span data-stu-id="c8138-142">Inner modules must be indented as far as outer module declarations to indicate that they are inner modules, not new modules.</span></span> <span data-ttu-id="c8138-143">Vergleichen Sie beispielsweise die folgenden zwei Beispiele.</span><span class="sxs-lookup"><span data-stu-id="c8138-143">For example, compare the following two examples.</span></span> <span data-ttu-id="c8138-144">Modul `Z` ist ein inneres Modul in den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="c8138-144">Module `Z` is an inner module in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6607.fs)]

<span data-ttu-id="c8138-145">Aber Modul `Z` ein gleichgeordnetes Element Modul `Y` in den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="c8138-145">But module `Z` is a sibling to module `Y` in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6608.fs)]
<span data-ttu-id="c8138-146">Modul `Z` ist auch ein gleichgeordnetes Element-Modul in den folgenden Code, da sie nicht so weit wie andere Deklarationen in Modul eingezogen ist `Y`.</span><span class="sxs-lookup"><span data-stu-id="c8138-146">Module `Z` is also a sibling module in the following code, because it is not indented as far as other declarations in module `Y`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6609.fs)]
<span data-ttu-id="c8138-147">Schließlich, wenn das äußere Modul verfügt über keine Deklarationen und unmittelbar, von einem anderen Moduldeklaration gefolgt wird, neue Moduldeklaration wird davon ausgegangen, dass ein inneres Modul, aber der Compiler warnt Sie, wenn die zweite Moduldefinition hin als nicht eingezogen wird die erste.</span><span class="sxs-lookup"><span data-stu-id="c8138-147">Finally, if the outer module has no declarations and is followed immediately by another module declaration, the new module declaration is assumed to be an inner module, but the compiler will warn you if the second module definition is not indented farther than the first.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6610.fs)]
<span data-ttu-id="c8138-148">Um die Warnung zu vermeiden, ziehen Sie das innere Modul ein.</span><span class="sxs-lookup"><span data-stu-id="c8138-148">To eliminate the warning, indent the inner module.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6611.fs)]
<span data-ttu-id="c8138-149">Wenn alle Code in einer Datei in einem einzelnen äußeren Modul sein soll, und inneren Module werden sollen, das äußere Modul erfordert nicht das Gleichheitszeichen und die Deklarationen, einschließlich möglichen Deklarationen innerer Module, die im äußeren Modul geleitet werden müssen nicht mit Einzug dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c8138-149">If you want all the code in a file to be in a single outer module and you want inner modules, the outer module does not require the equal sign, and the declarations, including any inner module declarations, that will go in the outer module do not have to be indented.</span></span> <span data-ttu-id="c8138-150">Deklarationen innerhalb der inneren Moduldeklarationen eingezogen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c8138-150">Declarations inside the inner module declarations do have to be indented.</span></span> <span data-ttu-id="c8138-151">Der folgende Code zeigt diesen Fall.</span><span class="sxs-lookup"><span data-stu-id="c8138-151">The following code shows this case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a><span data-ttu-id="c8138-152">Rekursive Module</span><span class="sxs-lookup"><span data-stu-id="c8138-152">Recursive modules</span></span>

<span data-ttu-id="c8138-153">F#-4.1 führt das Konzept der Module, die für alle enthaltenen Code wechselseitig rekursive sein können.</span><span class="sxs-lookup"><span data-stu-id="c8138-153">F# 4.1 introduces the notion of modules which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="c8138-154">Dies geschieht über `module rec`.</span><span class="sxs-lookup"><span data-stu-id="c8138-154">This is done via `module rec`.</span></span>  <span data-ttu-id="c8138-155">Verwenden von `module rec` verringern, können einige sorgen, nicht aufeinander Code für Typen und Module schreiben können.</span><span class="sxs-lookup"><span data-stu-id="c8138-155">Use of `module rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="c8138-156">Im folgenden finden ein Beispiel dafür:</span><span class="sxs-lookup"><span data-stu-id="c8138-156">The following is an example of this:</span></span>

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

    module private BananaHelpers =
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

<span data-ttu-id="c8138-157">Beachten Sie, dass die Ausnahme `DontSqueezeTheBananaException` und die Klasse `Banana` beide aufeinander verweisen.</span><span class="sxs-lookup"><span data-stu-id="c8138-157">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="c8138-158">Darüber hinaus das Modul `BananaHelpers` und die Klasse `Banana` auch miteinander verweisen.</span><span class="sxs-lookup"><span data-stu-id="c8138-158">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="c8138-159">Dies ist nicht möglich, express in F# erläutert werden, wenn Sie entfernt die `rec` -Schlüsselwort aus der `RecursiveModule` Modul.</span><span class="sxs-lookup"><span data-stu-id="c8138-159">This would not be possible to express in F# if you removed the `rec` keyword from the `RecursiveModule` module.</span></span>

<span data-ttu-id="c8138-160">Diese Funktion ist außerdem möglich [Namespaces](namespaces.md) f# 4.1.</span><span class="sxs-lookup"><span data-stu-id="c8138-160">This capability is also possible in [Namespaces](namespaces.md) with F# 4.1.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8138-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8138-161">See Also</span></span>

<span data-ttu-id="c8138-162">[F#-Sprachreferenz](index.md)
[Namespaces](namespaces.md)
[f# RFC FS 1009 - aufeinander Typen und Module über größere Bereiche innerhalb von Dateien zulassen](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)</span><span class="sxs-lookup"><span data-stu-id="c8138-162">[F# Language Reference](index.md)
[Namespaces](namespaces.md)
[F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)</span></span>
