---
title: 'Importdeklarationen: Das open-Schlüsselwort'
description: 'Erfahren Sie mehr über F #-Import Deklarationen und wie Sie ein Modul oder einen Namespace angeben, auf dessen Elemente verwiesen werden kann, ohne einen voll qualifizierten Namen zu verwenden.'
ms.date: 04/04/2019
ms.openlocfilehash: 2b88427ca92212fb4a7598447dd1a5e12061093a
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855087"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="7a221-103">Import Deklarationen: das- `open` Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="7a221-103">Import declarations: The `open` keyword</span></span>

<span data-ttu-id="7a221-104">Eine *Import Deklaration* gibt ein Modul oder einen Namespace an, auf dessen Elemente verwiesen werden kann, ohne einen voll qualifizierten Namen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a221-104">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="7a221-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a221-105">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="7a221-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7a221-106">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="7a221-107">Die docs.Microsoft.com-API-Referenz für F # ist nicht fertig.</span><span class="sxs-lookup"><span data-stu-id="7a221-107">The docs.microsoft.com API reference for F# is not complete.</span></span> <span data-ttu-id="7a221-108">Wenn Sie auf unterbrochene Verknüpfungen stoßen, verweisen Sie stattdessen auf die [Dokumentation der F #-Kernbibliothek](https://fsharp.github.io/fsharp-core-docs/) .</span><span class="sxs-lookup"><span data-stu-id="7a221-108">If you encounter any broken links, reference [F# Core Library Documentation](https://fsharp.github.io/fsharp-core-docs/) instead.</span></span>

<span data-ttu-id="7a221-109">Wenn Sie den voll qualifizierten Namespace-oder Modulpfad jedes Mal auf Code verweisen, können Sie Code erstellen, der schwer zu schreiben, zu lesen und zu warten ist.</span><span class="sxs-lookup"><span data-stu-id="7a221-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="7a221-110">Stattdessen können Sie das `open` -Schlüsselwort für häufig verwendete Module und Namespaces verwenden, sodass Sie die Kurzform des Namens anstelle des voll qualifizierten Namens verwenden können, wenn Sie auf ein Member dieses Moduls oder Namespace verweisen.</span><span class="sxs-lookup"><span data-stu-id="7a221-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="7a221-111">Dieses Schlüsselwort ähnelt dem `using` -Schlüsselwort in c#, `using namespace` in Visual C++ und `Imports` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7a221-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="7a221-112">Das angegebene Modul oder der angegebene Namespace muss sich im selben Projekt oder in einem referenzierten Projekt oder einer referenzierten Assembly befinden.</span><span class="sxs-lookup"><span data-stu-id="7a221-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="7a221-113">Wenn dies nicht der Fall ist, können Sie dem Projekt einen Verweis hinzufügen oder die `-reference` Befehlszeilenoption (oder die Abkürzung, `-r` ) verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a221-113">If it is not, you can add a reference to the project, or use the `-reference` command-line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="7a221-114">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="7a221-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="7a221-115">Die Import Deklaration stellt die Namen im Code, der der Deklaration folgt, bis zum Ende des einschließenden Namespace, Moduls oder der Datei zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7a221-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="7a221-116">Wenn Sie mehrere Import Deklarationen verwenden, sollten diese in separaten Zeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7a221-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="7a221-117">Der folgende Code zeigt die Verwendung des- `open` Schlüssel Worts, um Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="7a221-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="7a221-118">Der F #-Compiler gibt keinen Fehler oder eine Warnung aus, wenn Mehrdeutigkeiten auftreten, wenn derselbe Name in mehreren geöffneten Modulen oder Namespaces auftritt.</span><span class="sxs-lookup"><span data-stu-id="7a221-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="7a221-119">Wenn Mehrdeutigkeiten auftreten, gibt F # dem zuletzt geöffneten Modul oder Namespace Vorrang.</span><span class="sxs-lookup"><span data-stu-id="7a221-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="7a221-120">Im folgenden Code bedeutet beispielsweise, dass `empty` sich `Seq.empty` `empty` sowohl im `List` -Modul als auch im- `Seq` Modul befindet.</span><span class="sxs-lookup"><span data-stu-id="7a221-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="7a221-121">Daher sollten Sie beim Öffnen von Modulen oder Namespaces wie oder, die Member `List` `Seq` mit identischen Namen enthalten, vorsichtig sein. verwenden Sie stattdessen die qualifizierten Namen.</span><span class="sxs-lookup"><span data-stu-id="7a221-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="7a221-122">Vermeiden Sie jede Situation, in der der Code von der Reihenfolge der Import Deklarationen abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="7a221-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="7a221-123">Standardmäßig geöffnete Namespaces</span><span class="sxs-lookup"><span data-stu-id="7a221-123">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="7a221-124">Einige Namespaces werden so häufig in F #-Code verwendet, dass Sie implizit geöffnet werden, ohne dass eine explizite Import Deklaration erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7a221-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="7a221-125">In der folgenden Tabelle werden die standardmäßig geöffneten Namespaces angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7a221-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="7a221-126">Namespace</span><span class="sxs-lookup"><span data-stu-id="7a221-126">Namespace</span></span>|<span data-ttu-id="7a221-127">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7a221-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="7a221-128">Enthält grundlegende F #-Typdefinitionen für integrierte Typen wie `int` und `float` .</span><span class="sxs-lookup"><span data-stu-id="7a221-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="7a221-129">Enthält grundlegende arithmetische Operationen wie `+` und `*` .</span><span class="sxs-lookup"><span data-stu-id="7a221-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="7a221-130">Enthält unveränderliche Auflistungs Klassen, `List` z `Array` . b. und.</span><span class="sxs-lookup"><span data-stu-id="7a221-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="7a221-131">Enthält Typen für steuerungskonstrukte, wie z. b. Lazy Evaluation und asynchrone Workflows.</span><span class="sxs-lookup"><span data-stu-id="7a221-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="7a221-132">Enthält Funktionen für formatierte e/a, z `printf` . b. die Funktion.</span><span class="sxs-lookup"><span data-stu-id="7a221-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="7a221-133">AutoOpen-Attribut</span><span class="sxs-lookup"><span data-stu-id="7a221-133">AutoOpen Attribute</span></span>

<span data-ttu-id="7a221-134">Sie können das- `AutoOpen` Attribut auf eine Assembly anwenden, wenn Sie einen Namespace oder ein Modul automatisch öffnen möchten, wenn auf die Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7a221-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="7a221-135">Sie können auch das- `AutoOpen` Attribut auf ein Modul anwenden, um dieses Modul automatisch zu öffnen, wenn das übergeordnete Modul oder der übergeordnete Namespace geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="7a221-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="7a221-136">Weitere Informationen finden Sie unter [Core. AutoOpenAttribute-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="7a221-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="7a221-137">Requirements qualifiedaccess-Attribut</span><span class="sxs-lookup"><span data-stu-id="7a221-137">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="7a221-138">Einige Module, Datensätze oder Union-Typen können das- `RequireQualifiedAccess` Attribut angeben.</span><span class="sxs-lookup"><span data-stu-id="7a221-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="7a221-139">Wenn Sie auf Elemente dieser Module, Datensätze oder Unions verweisen, müssen Sie einen qualifizierten Namen verwenden, unabhängig davon, ob Sie eine Import Deklaration einschließen.</span><span class="sxs-lookup"><span data-stu-id="7a221-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="7a221-140">Wenn Sie dieses Attribut bei Typen, die häufig verwendete Namen definieren, strategisch verwenden, vermeiden Sie Namenskollisionen und sorgen dadurch für eine stabilere Codeänderung gegenüber den Änderungen in Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="7a221-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="7a221-141">Weitere Informationen finden Sie unter [Core. Requirements qualifiedaccessattribute-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span><span class="sxs-lookup"><span data-stu-id="7a221-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>

## <a name="see-also"></a><span data-ttu-id="7a221-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7a221-142">See also</span></span>

- [<span data-ttu-id="7a221-143">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="7a221-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="7a221-144">Namespaces</span><span class="sxs-lookup"><span data-stu-id="7a221-144">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="7a221-145">Module</span><span class="sxs-lookup"><span data-stu-id="7a221-145">Modules</span></span>](modules.md)
