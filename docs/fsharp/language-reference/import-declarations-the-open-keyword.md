---
title: 'Importdeklarationen: Das open-Schlüsselwort'
description: Erfahren Sie mehr über die Importdeklarationen von F- und deren Angabe eines Moduls oder Namespaces, auf deren Elemente Sie verweisen können, ohne einen vollqualifizierten Namen zu verwenden.
ms.date: 04/04/2019
ms.openlocfilehash: 0baef27c7dc3181b9da0defb1c793fec04269c09
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021530"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="2487b-103">Importdeklarationen: Das `open`-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="2487b-103">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
> <span data-ttu-id="2487b-104">Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="2487b-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="2487b-105">Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2487b-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="2487b-106">Eine *Importdeklaration* gibt ein Modul oder einen Namespace an, auf dessen Elemente Sie verweisen können, ohne einen vollqualifizierten Namen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2487b-106">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="2487b-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2487b-107">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="2487b-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2487b-108">Remarks</span></span>

<span data-ttu-id="2487b-109">Das Verweisen auf Code mithilfe des vollqualifizierten Namespace- oder Modulpfads kann jedes Mal Code erstellen, der schwer zu schreiben, zu lesen und zu verwalten ist.</span><span class="sxs-lookup"><span data-stu-id="2487b-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="2487b-110">Stattdessen können Sie `open` das Schlüsselwort für häufig verwendete Module und Namespaces verwenden, sodass Sie beim Verweisen auf ein Mitglied dieses Moduls oder Namespaces die Kurzform des Namens anstelle des vollqualifizierten Namens verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2487b-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="2487b-111">Dieses Schlüsselwort ähnelt `using` dem Schlüsselwort `using namespace` in C, In `Imports` Visual C++ und in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2487b-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="2487b-112">Das angegebene Modul oder der bereitgestellte Namespace muss sich im selben Projekt oder in einem referenzierten Projekt oder einer Assembly begeben.</span><span class="sxs-lookup"><span data-stu-id="2487b-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="2487b-113">Ist dies nicht der Fall, können Sie einen `-reference` Verweis auf das Projekt `-r`hinzufügen oder die Befehlszeilenoption (oder deren Abkürzung, ) verwenden.</span><span class="sxs-lookup"><span data-stu-id="2487b-113">If it is not, you can add a reference to the project, or use the `-reference` command-line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="2487b-114">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="2487b-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="2487b-115">Die Importdeklaration stellt die Namen im Code zur Verfügung, der auf die Deklaration folgt, bis zum Ende des einschließenden Namespace, Moduls oder der Datei.</span><span class="sxs-lookup"><span data-stu-id="2487b-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="2487b-116">Wenn Sie mehrere Importdeklarationen verwenden, sollten sie in separaten Zeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2487b-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="2487b-117">Der folgende Code zeigt `open` die Verwendung des Schlüsselworts, um Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="2487b-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="2487b-118">Der F-Compiler gibt keinen Fehler oder eine Warnung aus, wenn Mehrdeutigkeiten auftreten, wenn derselbe Name in mehr als einem geöffneten Modul oder Namespace auftritt.</span><span class="sxs-lookup"><span data-stu-id="2487b-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="2487b-119">Wenn Mehrdeutigkeiten auftreten, bevorzugt f. das kürzlich geöffnete Modul oder den Namespace.</span><span class="sxs-lookup"><span data-stu-id="2487b-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="2487b-120">Im folgenden Code bedeutet `empty` z. `Seq.empty`B., obwohl `empty` `List` es `Seq` sich sowohl in der als auch in den Modulen befindet.</span><span class="sxs-lookup"><span data-stu-id="2487b-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="2487b-121">Achten Sie daher darauf, wenn Sie Module `List` `Seq` oder Namespaces öffnen, z. B. oder die Member mit identischen Namen enthalten. Stattdessen sollten Sie die verwendungsberechtigten Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2487b-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="2487b-122">Sie sollten jede Situation vermeiden, in der der Code von der Reihenfolge der Einfuhrdeklarationen abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="2487b-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="2487b-123">Namespaces, die standardmäßig geöffnet sind</span><span class="sxs-lookup"><span data-stu-id="2487b-123">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="2487b-124">Einige Namespaces werden so häufig in F-Code verwendet, dass sie implizit geöffnet werden, ohne dass eine explizite Importdeklaration erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2487b-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="2487b-125">Die folgende Tabelle zeigt die standardmäßig geöffneten Namespaces.</span><span class="sxs-lookup"><span data-stu-id="2487b-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="2487b-126">Namespace</span><span class="sxs-lookup"><span data-stu-id="2487b-126">Namespace</span></span>|<span data-ttu-id="2487b-127">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2487b-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="2487b-128">Enthält grundlegende F-Typdefinitionen für integrierte `int` Typen `float`wie und .</span><span class="sxs-lookup"><span data-stu-id="2487b-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="2487b-129">Enthält grundlegende arithmetische `+` Operationen `*`wie und .</span><span class="sxs-lookup"><span data-stu-id="2487b-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="2487b-130">Enthält unveränderliche Auflistungsklassen wie `List` und `Array`.</span><span class="sxs-lookup"><span data-stu-id="2487b-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="2487b-131">Enthält Typen für Steuerelementkonstrukte, z. B. verzögerte Auswertung und asynchrone Workflows.</span><span class="sxs-lookup"><span data-stu-id="2487b-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="2487b-132">Enthält Funktionen für formatierte E/A, z. B. die `printf` Funktion.</span><span class="sxs-lookup"><span data-stu-id="2487b-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="2487b-133">AutoOpen-Attribut</span><span class="sxs-lookup"><span data-stu-id="2487b-133">AutoOpen Attribute</span></span>

<span data-ttu-id="2487b-134">Sie können `AutoOpen` das Attribut auf eine Assembly anwenden, wenn Sie automatisch einen Namespace oder ein Modul öffnen möchten, wenn auf die Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2487b-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="2487b-135">Sie können das `AutoOpen` Attribut auch auf ein Modul anwenden, um dieses Modul automatisch zu öffnen, wenn das übergeordnete Modul oder der Namespace geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="2487b-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="2487b-136">Weitere Informationen finden Sie unter [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="2487b-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="2487b-137">RequireQualifiedAccess-Attribut</span><span class="sxs-lookup"><span data-stu-id="2487b-137">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="2487b-138">Einige Module, Datensätze oder Union-Typen `RequireQualifiedAccess` können das Attribut angeben.</span><span class="sxs-lookup"><span data-stu-id="2487b-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="2487b-139">Wenn Sie auf Elemente dieser Module, Datensätze oder Unions verweisen, müssen Sie einen qualifizierten Namen verwenden, unabhängig davon, ob Sie eine Importdeklaration einschließen.</span><span class="sxs-lookup"><span data-stu-id="2487b-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="2487b-140">Wenn Sie dieses Attribut strategisch für Typen verwenden, die häufig verwendete Namen definieren, können Sie Namenskonflikte vermeiden und dadurch Code widerstandsfähiger gegenüber Änderungen in Bibliotheken machen.</span><span class="sxs-lookup"><span data-stu-id="2487b-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="2487b-141">Weitere Informationen finden Sie unter [Core.RequireQualifiedAccessAttribute-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span><span class="sxs-lookup"><span data-stu-id="2487b-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>

## <a name="see-also"></a><span data-ttu-id="2487b-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2487b-142">See also</span></span>

- [<span data-ttu-id="2487b-143">Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="2487b-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="2487b-144">Namespaces</span><span class="sxs-lookup"><span data-stu-id="2487b-144">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="2487b-145">Module</span><span class="sxs-lookup"><span data-stu-id="2487b-145">Modules</span></span>](modules.md)
