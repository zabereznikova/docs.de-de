---
title: 'Importdeklarationen: Das open-Schlüsselwort'
description: 'Erfahren Sie mehr über F #-Import Deklarationen und wie Sie ein Modul oder einen Namespace angeben, auf dessen Elemente verwiesen werden kann, ohne einen voll qualifizierten Namen zu verwenden.'
ms.date: 08/15/2020
ms.openlocfilehash: 6420df071f86159c44606c2710331d5f587023cc
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557606"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="13e73-103">Import Deklarationen: das- `open` Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="13e73-103">Import declarations: The `open` keyword</span></span>

<span data-ttu-id="13e73-104">Eine *Import Deklaration* gibt ein Modul oder einen Namespace an, auf dessen Elemente verwiesen werden kann, ohne einen voll qualifizierten Namen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="13e73-104">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="13e73-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="13e73-105">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="13e73-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="13e73-106">Remarks</span></span>

<span data-ttu-id="13e73-107">Wenn Sie den voll qualifizierten Namespace-oder Modulpfad jedes Mal auf Code verweisen, können Sie Code erstellen, der schwer zu schreiben, zu lesen und zu warten ist.</span><span class="sxs-lookup"><span data-stu-id="13e73-107">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="13e73-108">Stattdessen können Sie das `open` -Schlüsselwort für häufig verwendete Module und Namespaces verwenden, sodass Sie die Kurzform des Namens anstelle des voll qualifizierten Namens verwenden können, wenn Sie auf ein Member dieses Moduls oder Namespace verweisen.</span><span class="sxs-lookup"><span data-stu-id="13e73-108">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="13e73-109">Dieses Schlüsselwort ähnelt dem `using` -Schlüsselwort in c#, `using namespace` in Visual C++ und `Imports` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="13e73-109">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="13e73-110">Das angegebene Modul oder der angegebene Namespace muss sich im selben Projekt oder in einem referenzierten Projekt oder einer referenzierten Assembly befinden.</span><span class="sxs-lookup"><span data-stu-id="13e73-110">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="13e73-111">Wenn dies nicht der Fall ist, können Sie dem Projekt einen Verweis hinzufügen oder die `-reference` Befehlszeilenoption (oder die Abkürzung, `-r` ) verwenden.</span><span class="sxs-lookup"><span data-stu-id="13e73-111">If it is not, you can add a reference to the project, or use the `-reference` command-line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="13e73-112">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="13e73-112">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="13e73-113">Die Import Deklaration stellt die Namen im Code, der der Deklaration folgt, bis zum Ende des einschließenden Namespace, Moduls oder der Datei zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="13e73-113">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="13e73-114">Wenn Sie mehrere Import Deklarationen verwenden, sollten diese in separaten Zeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="13e73-114">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="13e73-115">Der folgende Code zeigt die Verwendung des- `open` Schlüssel Worts, um Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="13e73-115">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="13e73-116">Der F #-Compiler gibt keinen Fehler oder eine Warnung aus, wenn Mehrdeutigkeiten auftreten, wenn derselbe Name in mehreren geöffneten Modulen oder Namespaces auftritt.</span><span class="sxs-lookup"><span data-stu-id="13e73-116">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="13e73-117">Wenn Mehrdeutigkeiten auftreten, gibt F # dem zuletzt geöffneten Modul oder Namespace Vorrang.</span><span class="sxs-lookup"><span data-stu-id="13e73-117">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="13e73-118">Im folgenden Code bedeutet beispielsweise, dass `empty` sich `Seq.empty` `empty` sowohl im `List` -Modul als auch im- `Seq` Modul befindet.</span><span class="sxs-lookup"><span data-stu-id="13e73-118">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="13e73-119">Daher sollten Sie beim Öffnen von Modulen oder Namespaces wie oder, die Member `List` `Seq` mit identischen Namen enthalten, vorsichtig sein. verwenden Sie stattdessen die qualifizierten Namen.</span><span class="sxs-lookup"><span data-stu-id="13e73-119">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="13e73-120">Vermeiden Sie jede Situation, in der der Code von der Reihenfolge der Import Deklarationen abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="13e73-120">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="13e73-121">Standardmäßig geöffnete Namespaces</span><span class="sxs-lookup"><span data-stu-id="13e73-121">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="13e73-122">Einige Namespaces werden so häufig in F #-Code verwendet, dass Sie implizit geöffnet werden, ohne dass eine explizite Import Deklaration erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="13e73-122">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="13e73-123">In der folgenden Tabelle werden die standardmäßig geöffneten Namespaces angezeigt.</span><span class="sxs-lookup"><span data-stu-id="13e73-123">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="13e73-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="13e73-124">Namespace</span></span>|<span data-ttu-id="13e73-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="13e73-125">Description</span></span>|
|---------|-----------|
|`FSharp.Core`|<span data-ttu-id="13e73-126">Enthält grundlegende F #-Typdefinitionen für integrierte Typen wie `int` und `float` .</span><span class="sxs-lookup"><span data-stu-id="13e73-126">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`FSharp.Core.Operators`|<span data-ttu-id="13e73-127">Enthält grundlegende arithmetische Operationen wie `+` und `*` .</span><span class="sxs-lookup"><span data-stu-id="13e73-127">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`FSharp.Collections`|<span data-ttu-id="13e73-128">Enthält unveränderliche Auflistungs Klassen, `List` z `Array` . b. und.</span><span class="sxs-lookup"><span data-stu-id="13e73-128">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`FSharp.Control`|<span data-ttu-id="13e73-129">Enthält Typen für steuerungskonstrukte, wie z. b. Lazy Evaluation und asynchrone Workflows.</span><span class="sxs-lookup"><span data-stu-id="13e73-129">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`FSharp.Text`|<span data-ttu-id="13e73-130">Enthält Funktionen für formatierte e/a, z `printf` . b. die Funktion.</span><span class="sxs-lookup"><span data-stu-id="13e73-130">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="13e73-131">AutoOpen-Attribut</span><span class="sxs-lookup"><span data-stu-id="13e73-131">AutoOpen Attribute</span></span>

<span data-ttu-id="13e73-132">Sie können das- `AutoOpen` Attribut auf eine Assembly anwenden, wenn Sie einen Namespace oder ein Modul automatisch öffnen möchten, wenn auf die Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="13e73-132">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="13e73-133">Sie können auch das- `AutoOpen` Attribut auf ein Modul anwenden, um dieses Modul automatisch zu öffnen, wenn das übergeordnete Modul oder der übergeordnete Namespace geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="13e73-133">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="13e73-134">Weitere Informationen finden Sie unter [AutoOpenAttribute](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-autoopenattribute.html).</span><span class="sxs-lookup"><span data-stu-id="13e73-134">For more information, see [AutoOpenAttribute](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-autoopenattribute.html).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="13e73-135">Requirements qualifiedaccess-Attribut</span><span class="sxs-lookup"><span data-stu-id="13e73-135">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="13e73-136">Einige Module, Datensätze oder Union-Typen können das- `RequireQualifiedAccess` Attribut angeben.</span><span class="sxs-lookup"><span data-stu-id="13e73-136">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="13e73-137">Wenn Sie auf Elemente dieser Module, Datensätze oder Unions verweisen, müssen Sie einen qualifizierten Namen verwenden, unabhängig davon, ob Sie eine Import Deklaration einschließen.</span><span class="sxs-lookup"><span data-stu-id="13e73-137">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="13e73-138">Wenn Sie dieses Attribut bei Typen, die häufig verwendete Namen definieren, strategisch verwenden, vermeiden Sie Namenskollisionen und sorgen dadurch für eine stabilere Codeänderung gegenüber den Änderungen in Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="13e73-138">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="13e73-139">Weitere Informationen finden Sie unter "Requirements [qualifiedaccessattribute](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html)".</span><span class="sxs-lookup"><span data-stu-id="13e73-139">For more information, see [RequireQualifiedAccessAttribute](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html).</span></span>

## <a name="see-also"></a><span data-ttu-id="13e73-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="13e73-140">See also</span></span>

- [<span data-ttu-id="13e73-141">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="13e73-141">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="13e73-142">Namespaces</span><span class="sxs-lookup"><span data-stu-id="13e73-142">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="13e73-143">Module</span><span class="sxs-lookup"><span data-stu-id="13e73-143">Modules</span></span>](modules.md)
