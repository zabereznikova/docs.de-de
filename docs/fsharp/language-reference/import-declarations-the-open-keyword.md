---
title: 'Importdeklarationen: Das open-Schlüsselwort'
description: 'Erfahren Sie mehr über F #-Import Deklarationen und wie Sie ein Modul oder einen Namespace angeben, auf dessen Elemente verwiesen werden kann, ohne einen voll qualifizierten Namen zu verwenden.'
ms.date: 08/15/2020
ms.openlocfilehash: ab208c53809e120bc216c8f8b4d04a322d67cf2f
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557180"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="7bc6b-103">Import Deklarationen: das- `open` Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="7bc6b-103">Import declarations: The `open` keyword</span></span>

<span data-ttu-id="7bc6b-104">Eine *Import Deklaration* gibt ein Modul oder einen Namespace an, auf dessen Elemente verwiesen werden kann, ohne einen voll qualifizierten Namen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-104">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="7bc6b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7bc6b-105">Syntax</span></span>

```fsharp
open module-or-namespace-name
open type type-name
```

## <a name="remarks"></a><span data-ttu-id="7bc6b-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7bc6b-106">Remarks</span></span>

<span data-ttu-id="7bc6b-107">Wenn Sie den voll qualifizierten Namespace-oder Modulpfad jedes Mal auf Code verweisen, können Sie Code erstellen, der schwer zu schreiben, zu lesen und zu warten ist.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-107">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="7bc6b-108">Stattdessen können Sie das `open` -Schlüsselwort für häufig verwendete Module und Namespaces verwenden, sodass Sie die Kurzform des Namens anstelle des voll qualifizierten Namens verwenden können, wenn Sie auf ein Member dieses Moduls oder Namespace verweisen.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-108">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="7bc6b-109">Dieses Schlüsselwort ähnelt dem `using` -Schlüsselwort in c#, `using namespace` in Visual C++ und `Imports` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-109">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="7bc6b-110">Das angegebene Modul oder der angegebene Namespace muss sich im selben Projekt oder in einem referenzierten Projekt oder einer referenzierten Assembly befinden.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-110">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="7bc6b-111">Wenn dies nicht der Fall ist, können Sie dem Projekt einen Verweis hinzufügen oder die `-reference` Befehlszeilenoption (oder die Abkürzung, `-r` ) verwenden.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-111">If it is not, you can add a reference to the project, or use the `-reference` command-line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="7bc6b-112">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="7bc6b-112">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="7bc6b-113">Die Import Deklaration stellt die Namen im Code, der der Deklaration folgt, bis zum Ende des einschließenden Namespace, Moduls oder der Datei zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-113">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="7bc6b-114">Wenn Sie mehrere Import Deklarationen verwenden, sollten diese in separaten Zeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-114">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="7bc6b-115">Der folgende Code zeigt die Verwendung des- `open` Schlüssel Worts, um Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-115">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="7bc6b-116">Der F #-Compiler gibt keinen Fehler oder eine Warnung aus, wenn Mehrdeutigkeiten auftreten, wenn derselbe Name in mehreren geöffneten Modulen oder Namespaces auftritt.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-116">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="7bc6b-117">Wenn Mehrdeutigkeiten auftreten, gibt F # dem zuletzt geöffneten Modul oder Namespace Vorrang.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-117">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="7bc6b-118">Im folgenden Code bedeutet beispielsweise, dass `empty` sich `Seq.empty` `empty` sowohl im `List` -Modul als auch im- `Seq` Modul befindet.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-118">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="7bc6b-119">Daher sollten Sie beim Öffnen von Modulen oder Namespaces wie oder, die Member `List` `Seq` mit identischen Namen enthalten, vorsichtig sein. verwenden Sie stattdessen die qualifizierten Namen.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-119">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="7bc6b-120">Vermeiden Sie jede Situation, in der der Code von der Reihenfolge der Import Deklarationen abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-120">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="open-type-declarations"></a><span data-ttu-id="7bc6b-121">Open-Typdeklarationen</span><span class="sxs-lookup"><span data-stu-id="7bc6b-121">Open type declarations</span></span>

<span data-ttu-id="7bc6b-122">F # unterstützt `open` für einen Typ wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7bc6b-122">F# supports `open` on a type like so:</span></span>

```fsharp
open type System.Math
PI
```

<span data-ttu-id="7bc6b-123">Dadurch werden alle zugänglichen statischen Felder und Member für den-Typ verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-123">This will expose all accessible static fields and members on the type.</span></span>

<span data-ttu-id="7bc6b-124">Sie können auch `open` F #-definierte [Daten Satz](records.md) -und Unterscheidungs [Union](discriminated-unions.md) -Typen zur Offenlegung statischer Member nutzen.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-124">You can also `open` F#-defined [record](records.md) and [discriminated union](discriminated-unions.md) types to expose static members.</span></span> <span data-ttu-id="7bc6b-125">Im Fall von Unterscheidungs-Unions können Sie auch die Union-Fälle verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-125">In the case of discriminated unions, you can also expose the union cases.</span></span> <span data-ttu-id="7bc6b-126">Dies kann hilfreich sein, um auf Union-Fälle in einem Typ zuzugreifen, der innerhalb eines Moduls deklariert ist, das Sie möglicherweise nicht öffnen möchten, wie hier:</span><span class="sxs-lookup"><span data-stu-id="7bc6b-126">This can be helpful for accessing union cases in a type declared inside of a module that you may not want to open, like so:</span></span>

```fsharp
module M =
    type DU = A | B | C

    let someOtherFunction x = x + 1

// Open only the type inside the module
open type M.DU

printfn "%A" A
```

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="7bc6b-127">Standardmäßig geöffnete Namespaces</span><span class="sxs-lookup"><span data-stu-id="7bc6b-127">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="7bc6b-128">Einige Namespaces werden so häufig in F #-Code verwendet, dass Sie implizit geöffnet werden, ohne dass eine explizite Import Deklaration erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-128">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="7bc6b-129">In der folgenden Tabelle werden die standardmäßig geöffneten Namespaces angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-129">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="7bc6b-130">Namespace</span><span class="sxs-lookup"><span data-stu-id="7bc6b-130">Namespace</span></span>|<span data-ttu-id="7bc6b-131">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7bc6b-131">Description</span></span>|
|---------|-----------|
|`FSharp.Core`|<span data-ttu-id="7bc6b-132">Enthält grundlegende F #-Typdefinitionen für integrierte Typen wie `int` und `float` .</span><span class="sxs-lookup"><span data-stu-id="7bc6b-132">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`FSharp.Core.Operators`|<span data-ttu-id="7bc6b-133">Enthält grundlegende arithmetische Operationen wie `+` und `*` .</span><span class="sxs-lookup"><span data-stu-id="7bc6b-133">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`FSharp.Collections`|<span data-ttu-id="7bc6b-134">Enthält unveränderliche Auflistungs Klassen, `List` z `Array` . b. und.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-134">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`FSharp.Control`|<span data-ttu-id="7bc6b-135">Enthält Typen für steuerungskonstrukte, wie z. b. Lazy Evaluation und asynchrone Workflows.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-135">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`FSharp.Text`|<span data-ttu-id="7bc6b-136">Enthält Funktionen für formatierte e/a, z `printf` . b. die Funktion.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-136">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="7bc6b-137">AutoOpen-Attribut</span><span class="sxs-lookup"><span data-stu-id="7bc6b-137">AutoOpen Attribute</span></span>

<span data-ttu-id="7bc6b-138">Sie können das- `AutoOpen` Attribut auf eine Assembly anwenden, wenn Sie einen Namespace oder ein Modul automatisch öffnen möchten, wenn auf die Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-138">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="7bc6b-139">Sie können auch das- `AutoOpen` Attribut auf ein Modul anwenden, um dieses Modul automatisch zu öffnen, wenn das übergeordnete Modul oder der übergeordnete Namespace geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-139">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="7bc6b-140">Weitere Informationen finden Sie unter [AutoOpenAttribute](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-autoopenattribute.html).</span><span class="sxs-lookup"><span data-stu-id="7bc6b-140">For more information, see [AutoOpenAttribute](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-autoopenattribute.html).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="7bc6b-141">Requirements qualifiedaccess-Attribut</span><span class="sxs-lookup"><span data-stu-id="7bc6b-141">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="7bc6b-142">Einige Module, Datensätze oder Union-Typen können das- `RequireQualifiedAccess` Attribut angeben.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-142">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="7bc6b-143">Wenn Sie auf Elemente dieser Module, Datensätze oder Unions verweisen, müssen Sie einen qualifizierten Namen verwenden, unabhängig davon, ob Sie eine Import Deklaration einschließen.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-143">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="7bc6b-144">Wenn Sie dieses Attribut bei Typen, die häufig verwendete Namen definieren, strategisch verwenden, vermeiden Sie Namenskollisionen und sorgen dadurch für eine stabilere Codeänderung gegenüber den Änderungen in Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-144">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="7bc6b-145">Weitere Informationen finden Sie unter "Requirements [qualifiedaccessattribute](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html)".</span><span class="sxs-lookup"><span data-stu-id="7bc6b-145">For more information, see [RequireQualifiedAccessAttribute](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html).</span></span>

## <a name="see-also"></a><span data-ttu-id="7bc6b-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7bc6b-146">See also</span></span>

- [<span data-ttu-id="7bc6b-147">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="7bc6b-147">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="7bc6b-148">Namespaces</span><span class="sxs-lookup"><span data-stu-id="7bc6b-148">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="7bc6b-149">Module</span><span class="sxs-lookup"><span data-stu-id="7bc6b-149">Modules</span></span>](modules.md)
