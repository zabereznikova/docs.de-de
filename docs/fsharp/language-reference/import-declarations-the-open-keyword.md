---
title: 'Importdeklarationen: Das open-Schlüsselwort (F#)'
description: Erfahren Sie mehr über f# Importdeklarationen und wie sie ein Modul oder einen Namespace angeben, dessen Elemente, die Sie verweisen können, ohne einen vollqualifizierten Namen verwenden.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: ddbc1086e2adbe8dae408f4d39fd5af888d7fd5e
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="de8b5-103">Importdeklarationen: Das `open` Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="de8b5-103">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
<span data-ttu-id="de8b5-104">Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="de8b5-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="de8b5-105">Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="de8b5-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="de8b5-106">Ein *importieren Deklaration* gibt ein Modul oder einen Namespace, dessen Elemente, die Sie verweisen können, ohne einen vollqualifizierten Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="de8b5-106">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>


## <a name="syntax"></a><span data-ttu-id="de8b5-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="de8b5-107">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="de8b5-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="de8b5-108">Remarks</span></span>
<span data-ttu-id="de8b5-109">Verweisen auf Code mithilfe des vollqualifizierten Pfads der Namespace- oder Modulebene kann jedem Code erstellen, die schwer zu schreiben, lesen und zu pflegen ist.</span><span class="sxs-lookup"><span data-stu-id="de8b5-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="de8b5-110">Stattdessen können Sie die `open` -Schlüsselwort für häufig verwendete Module und Namespaces, damit Sie Folgendes: Wenn Sie ein Mitglied dieses Modul oder einen Namespace verweisen, können Sie die Kurzform des Namens anstelle des vollqualifizierten Namens verwenden.</span><span class="sxs-lookup"><span data-stu-id="de8b5-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="de8b5-111">Dieses Schlüsselwort ähnelt der `using` -Schlüsselwort in c#, `using namespace` in Visual C++ und `Imports` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="de8b5-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="de8b5-112">Das Modul oder einen angegebenen Namespace muss im selben Projekt oder in einem Projekt verwiesen wird oder die Assembly sein.</span><span class="sxs-lookup"><span data-stu-id="de8b5-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="de8b5-113">Wenn es nicht der Fall ist, können Sie einen Verweis auf das Projekt hinzufügen oder verwenden Sie die `-reference` Befehl`-`Befehlszeilenoption (oder dessen Abkürzung `-r`).</span><span class="sxs-lookup"><span data-stu-id="de8b5-113">If it is not, you can add a reference to the project, or use the `-reference` command`-`line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="de8b5-114">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="de8b5-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="de8b5-115">Die Importdeklaration stellt die Namen in der Deklaration bis zum Ende des einschließenden Namespace, Moduls oder Datei der folgende Code zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="de8b5-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="de8b5-116">Wenn Sie mehrere Importdeklarationen verwenden, sollten sie in separaten Zeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="de8b5-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="de8b5-117">Der folgende Code zeigt die Verwendung der `open` Schlüsselwort, um Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="de8b5-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="de8b5-118">F#-Compiler ausgeben, wenn Mehrdeutigkeiten auftreten, wenn es sich bei der gleiche Namen in mehr als eine open-Modul oder einen Namespace tritt auf, keinen Fehler oder eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="de8b5-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="de8b5-119">Wenn Mehrdeutigkeiten auftreten, bevorzugt f#, die mehr zuletzt geöffneten Modul oder einen Namespace.</span><span class="sxs-lookup"><span data-stu-id="de8b5-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="de8b5-120">Im folgenden Code wird z. B. `empty` bedeutet `Seq.empty`, obwohl `empty` befindet sich in beiden die `List` und `Seq` Module.</span><span class="sxs-lookup"><span data-stu-id="de8b5-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="de8b5-121">Aus diesem Grund, seien Sie vorsichtig, wenn Sie Module oder Namespaces wie z. B. Öffnen `List` oder `Seq` , die Elemente, die identische Namen haben, erwägen Sie stattdessen mit dem qualifizierten Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="de8b5-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="de8b5-122">Sie sollten jede Situation vermeiden, in der der Code die Reihenfolge der Importdeklarationen abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="de8b5-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>


## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="de8b5-123">Namespaces, die standardmäßig geöffnet sind</span><span class="sxs-lookup"><span data-stu-id="de8b5-123">Namespaces That Are Open by Default</span></span>
<span data-ttu-id="de8b5-124">Einige Namespaces werden so häufig in f#-Code verwendet, sie ohne die Notwendigkeit einer Deklaration expliziter Import implizit geöffnet sind.</span><span class="sxs-lookup"><span data-stu-id="de8b5-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="de8b5-125">In der folgenden Tabelle werden die Namespaces angezeigt, die standardmäßig geöffnet sind.</span><span class="sxs-lookup"><span data-stu-id="de8b5-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="de8b5-126">Namespace</span><span class="sxs-lookup"><span data-stu-id="de8b5-126">Namespace</span></span>|<span data-ttu-id="de8b5-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de8b5-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="de8b5-128">Enthält grundlegende F#-Typdefinitionen für integrierte Typen wie z. B. `int` und `float`.</span><span class="sxs-lookup"><span data-stu-id="de8b5-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="de8b5-129">Enthält grundlegende arithmetische Operationen wie `+` und `*`.</span><span class="sxs-lookup"><span data-stu-id="de8b5-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="de8b5-130">Enthält die unveränderlichen Auflistungsklassen wie `List` und `Array`.</span><span class="sxs-lookup"><span data-stu-id="de8b5-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="de8b5-131">Enthält Typen zum Steuerelementkonstrukte, wie z. B. verzögerte Auswertung und asynchrone Workflows.</span><span class="sxs-lookup"><span data-stu-id="de8b5-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="de8b5-132">Enthält Funktionen für formatierte e/a, z. B. die `printf` Funktion.</span><span class="sxs-lookup"><span data-stu-id="de8b5-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="de8b5-133">AutoOpen-Attribut</span><span class="sxs-lookup"><span data-stu-id="de8b5-133">AutoOpen Attribute</span></span>
<span data-ttu-id="de8b5-134">Sie können Anwenden der `AutoOpen` -Attribut auf eine Assembly, wenn ein Namespace oder Modul automatisch geöffnet, wenn die Assembly verwiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="de8b5-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="de8b5-135">Sie können auch anwenden, die `AutoOpen` -Attribut auf ein Modul, dass das Modul automatisch geöffnet, wenn das übergeordnete Modul oder einen Namespace geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="de8b5-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="de8b5-136">Weitere Informationen finden Sie unter [Core.AutoOpenAttribute-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="de8b5-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>


## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="de8b5-137">RequireQualifiedAccess-Attribut</span><span class="sxs-lookup"><span data-stu-id="de8b5-137">RequireQualifiedAccess Attribute</span></span>
<span data-ttu-id="de8b5-138">Einige Module, Datensätze oder union-Typen können angeben, die `RequireQualifiedAccess` Attribut.</span><span class="sxs-lookup"><span data-stu-id="de8b5-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="de8b5-139">Wenn Sie Elemente von diesen Modulen, Datensätze oder Unions verweisen, müssen Sie unabhängig davon, ob Sie eine Importdeklaration enthalten einen qualifizierten Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="de8b5-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="de8b5-140">Wenn Sie dieses Attribut strategisch auf Typen, die häufig definieren Namen verwendet, lassen sich Namenskonflikte vermieden und somit Code stabiler auf Änderungen in Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="de8b5-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="de8b5-141">Weitere Informationen finden Sie unter [Core.RequireQualifiedAccessAttribute-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span><span class="sxs-lookup"><span data-stu-id="de8b5-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>


## <a name="see-also"></a><span data-ttu-id="de8b5-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de8b5-142">See Also</span></span>
[<span data-ttu-id="de8b5-143">-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="de8b5-143"># Language Reference</span></span>](index.md)

[<span data-ttu-id="de8b5-144">Namespaces</span><span class="sxs-lookup"><span data-stu-id="de8b5-144">Namespaces</span></span>](namespaces.md)

[<span data-ttu-id="de8b5-145">Module</span><span class="sxs-lookup"><span data-stu-id="de8b5-145">Modules</span></span>](modules.md)

