---
title: '`Scope`'
ms.date: 07/20/2015
helpviewer_keywords:
- module scope [Visual Basic]
- scope [Visual Basic], levels
- module level
- procedures [Visual Basic], scope
- declared elements [Visual Basic], scope
- namespaces [Visual Basic], scope
- scope [Visual Basic], declared elements
- scope [Visual Basic], about scope
- levels of scope [Visual Basic]
- block scope [Visual Basic]
- scope [Visual Basic], Visual Basic
- procedure scope [Visual Basic]
ms.assetid: 208106fe-79c9-4eec-93c6-55f08548895f
ms.openlocfilehash: 1bee904996257474b7457b2aefb1f17d250933cb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410733"
---
# <a name="scope-in-visual-basic"></a><span data-ttu-id="1cb99-102">Gültigkeitsbereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1cb99-102">Scope in Visual Basic</span></span>

<span data-ttu-id="1cb99-103">Der Gültigkeits *Bereich* eines deklarierten Elements ist der Satz des gesamten Codes, der darauf verweisen kann, ohne den Namen zu qualifizieren oder über eine [Imports-Anweisung (.NET-Namespace und-Typ)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)verfügbar zu gemacht.</span><span class="sxs-lookup"><span data-stu-id="1cb99-103">The *scope* of a declared element is the set of all code that can refer to it without qualifying its name or making it available through an [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span> <span data-ttu-id="1cb99-104">Ein Element kann einen Bereich auf einer der folgenden Ebenen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="1cb99-104">An element can have scope at one of the following levels:</span></span>

|<span data-ttu-id="1cb99-105">Ebene</span><span class="sxs-lookup"><span data-stu-id="1cb99-105">Level</span></span>|<span data-ttu-id="1cb99-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1cb99-106">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="1cb99-107">Blockbereich</span><span class="sxs-lookup"><span data-stu-id="1cb99-107">Block scope</span></span>|<span data-ttu-id="1cb99-108">Nur innerhalb des Codeblocks verfügbar, in dem er deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="1cb99-108">Available only within the code block in which it is declared</span></span>|
|<span data-ttu-id="1cb99-109">Prozedur Bereich</span><span class="sxs-lookup"><span data-stu-id="1cb99-109">Procedure scope</span></span>|<span data-ttu-id="1cb99-110">Verfügbar für den gesamten Code in der Prozedur, in der er deklariert ist</span><span class="sxs-lookup"><span data-stu-id="1cb99-110">Available to all code within the procedure in which it is declared</span></span>|
|<span data-ttu-id="1cb99-111">Modul Bereich</span><span class="sxs-lookup"><span data-stu-id="1cb99-111">Module scope</span></span>|<span data-ttu-id="1cb99-112">Verfügbar für den gesamten Code im Modul, der Klasse oder Struktur, in der er deklariert ist</span><span class="sxs-lookup"><span data-stu-id="1cb99-112">Available to all code within the module, class, or structure in which it is declared</span></span>|
|<span data-ttu-id="1cb99-113">Namespace Bereich</span><span class="sxs-lookup"><span data-stu-id="1cb99-113">Namespace scope</span></span>|<span data-ttu-id="1cb99-114">Verfügbar für den gesamten Code im Namespace, in dem er deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="1cb99-114">Available to all code in the namespace in which it is declared</span></span>|

<span data-ttu-id="1cb99-115">Diese Ebenen des Bereichs werden vom engsten (Block) zum breiteste (-Namespace), wobei der *engste* Gültigkeitsbereich die kleinste Codemenge bedeutet, die ohne Qualifizierung auf das Element verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="1cb99-115">These levels of scope progress from the narrowest (block) to the widest (namespace), where *narrowest scope* means the smallest set of code that can refer to the element without qualification.</span></span> <span data-ttu-id="1cb99-116">Weitere Informationen finden Sie auf dieser Seite unter "Ebenen des Bereichs".</span><span class="sxs-lookup"><span data-stu-id="1cb99-116">For more information, see "Levels of Scope" on this page.</span></span>

## <a name="specifying-scope-and-defining-variables"></a><span data-ttu-id="1cb99-117">Festlegen des Bereichs und Definieren von Variablen</span><span class="sxs-lookup"><span data-stu-id="1cb99-117">Specifying Scope and Defining Variables</span></span>

<span data-ttu-id="1cb99-118">Sie geben den Bereich eines Elements an, wenn Sie es deklarieren.</span><span class="sxs-lookup"><span data-stu-id="1cb99-118">You specify the scope of an element when you declare it.</span></span> <span data-ttu-id="1cb99-119">Der Bereich kann von folgenden Faktoren abhängen:</span><span class="sxs-lookup"><span data-stu-id="1cb99-119">The scope can depend on the following factors:</span></span>

- <span data-ttu-id="1cb99-120">Der Bereich (Block, Prozedur, Modul, Klasse oder Struktur), in dem Sie das Element deklarieren.</span><span class="sxs-lookup"><span data-stu-id="1cb99-120">The region (block, procedure, module, class, or structure) in which you declare the element</span></span>

- <span data-ttu-id="1cb99-121">Der Namespace, der die Deklaration des Elements enthält.</span><span class="sxs-lookup"><span data-stu-id="1cb99-121">The namespace containing the element's declaration</span></span>

- <span data-ttu-id="1cb99-122">Die Zugriffsebene, die Sie für das Element deklarieren.</span><span class="sxs-lookup"><span data-stu-id="1cb99-122">The access level you declare for the element</span></span>

<span data-ttu-id="1cb99-123">Verwenden Sie Vorsicht, wenn Sie Variablen mit demselben Namen, aber unterschiedlichen Gültigkeitsbereich definieren, da dies zu unerwarteten Ergebnissen führen kann.</span><span class="sxs-lookup"><span data-stu-id="1cb99-123">Use care when you define variables with the same name but different scope, because doing so can lead to unexpected results.</span></span> <span data-ttu-id="1cb99-124">Weitere Informationen finden Sie unter [References to Declared Elements](references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="1cb99-124">For more information, see [References to Declared Elements](references-to-declared-elements.md).</span></span>

## <a name="levels-of-scope"></a><span data-ttu-id="1cb99-125">Ebenen des Gültigkeits Bereichs</span><span class="sxs-lookup"><span data-stu-id="1cb99-125">Levels of Scope</span></span>

<span data-ttu-id="1cb99-126">Ein Programmier Element ist in der Region verfügbar, in der Sie es deklarieren.</span><span class="sxs-lookup"><span data-stu-id="1cb99-126">A programming element is available throughout the region in which you declare it.</span></span> <span data-ttu-id="1cb99-127">Der gesamte Code in der gleichen Region kann auf das Element verweisen, ohne den Namen zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="1cb99-127">All code in the same region can refer to the element without qualifying its name.</span></span>

### <a name="block-scope"></a><span data-ttu-id="1cb99-128">Block Bereich</span><span class="sxs-lookup"><span data-stu-id="1cb99-128">Block Scope</span></span>

<span data-ttu-id="1cb99-129">Ein-Block ist ein Satz von-Anweisungen, die in initiieren und Beenden von Deklarations Anweisungen eingeschlossen sind, wie z. b.:</span><span class="sxs-lookup"><span data-stu-id="1cb99-129">A block is a set of statements enclosed within initiating and terminating declaration statements, such as the following:</span></span>

- <span data-ttu-id="1cb99-130">`Do` und `Loop`</span><span class="sxs-lookup"><span data-stu-id="1cb99-130">`Do` and `Loop`</span></span>

- <span data-ttu-id="1cb99-131">`For`[ `Each` ] und`Next`</span><span class="sxs-lookup"><span data-stu-id="1cb99-131">`For` [`Each`] and `Next`</span></span>

- <span data-ttu-id="1cb99-132">`If` und `End If`</span><span class="sxs-lookup"><span data-stu-id="1cb99-132">`If` and `End If`</span></span>

- <span data-ttu-id="1cb99-133">`Select` und `End Select`</span><span class="sxs-lookup"><span data-stu-id="1cb99-133">`Select` and `End Select`</span></span>

- <span data-ttu-id="1cb99-134">`SyncLock` und `End SyncLock`</span><span class="sxs-lookup"><span data-stu-id="1cb99-134">`SyncLock` and `End SyncLock`</span></span>

- <span data-ttu-id="1cb99-135">`Try` und `End Try`</span><span class="sxs-lookup"><span data-stu-id="1cb99-135">`Try` and `End Try`</span></span>

- <span data-ttu-id="1cb99-136">`While` und `End While`</span><span class="sxs-lookup"><span data-stu-id="1cb99-136">`While` and `End While`</span></span>

- <span data-ttu-id="1cb99-137">`With` und `End With`</span><span class="sxs-lookup"><span data-stu-id="1cb99-137">`With` and `End With`</span></span>

<span data-ttu-id="1cb99-138">Wenn Sie eine Variable innerhalb eines-Blocks deklarieren, können Sie Sie nur innerhalb dieses Blocks verwenden.</span><span class="sxs-lookup"><span data-stu-id="1cb99-138">If you declare a variable within a block, you can use it only within that block.</span></span> <span data-ttu-id="1cb99-139">Im folgenden Beispiel ist der Gültigkeitsbereich der ganzzahligen Variablen `cube` der-Block zwischen `If` und `End If` , und Sie können nicht mehr auf verweisen, `cube` Wenn die Ausführung aus dem-Block besteht.</span><span class="sxs-lookup"><span data-stu-id="1cb99-139">In the following example, the scope of the integer variable `cube` is the block between `If` and `End If`, and you can no longer refer to `cube` when execution passes out of the block.</span></span>

```vb
If n < 1291 Then
    Dim cube As Integer
    cube = n ^ 3
End If
```

> [!NOTE]
> <span data-ttu-id="1cb99-140">Auch wenn der Gültigkeitsbereich einer Variablen auf einen-Block beschränkt ist, liegt seine Lebensdauer immer noch bei der gesamten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="1cb99-140">Even if the scope of a variable is limited to a block, its lifetime is still that of the entire procedure.</span></span> <span data-ttu-id="1cb99-141">Wenn Sie den Block während der Prozedur mehrmals eingeben, behält jede Block Variable ihren vorherigen Wert bei.</span><span class="sxs-lookup"><span data-stu-id="1cb99-141">If you enter the block more than once during the procedure, each block variable retains its previous value.</span></span> <span data-ttu-id="1cb99-142">Um unerwartete Ergebnisse in einem solchen Fall zu vermeiden, ist es ratsam, Block Variablen am Anfang des Blocks zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="1cb99-142">To avoid unexpected results in such a case, it is wise to initialize block variables at the beginning of the block.</span></span>

### <a name="procedure-scope"></a><span data-ttu-id="1cb99-143">Prozedur Bereich</span><span class="sxs-lookup"><span data-stu-id="1cb99-143">Procedure Scope</span></span>

<span data-ttu-id="1cb99-144">Ein innerhalb einer Prozedur deklariertes Element ist außerhalb dieses Verfahrens nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1cb99-144">An element declared within a procedure is not available outside that procedure.</span></span> <span data-ttu-id="1cb99-145">Nur die Prozedur, die die Deklaration enthält, kann diese verwenden.</span><span class="sxs-lookup"><span data-stu-id="1cb99-145">Only the procedure that contains the declaration can use it.</span></span> <span data-ttu-id="1cb99-146">Variablen auf dieser Ebene werden auch als *lokale Variablen*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="1cb99-146">Variables at this level are also known as *local variables*.</span></span> <span data-ttu-id="1cb99-147">Sie deklarieren Sie mit der [Dim-Anweisung](../../../language-reference/statements/dim-statement.md)mit oder ohne das [static](../../../language-reference/modifiers/static.md) -Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="1cb99-147">You declare them with the [Dim Statement](../../../language-reference/statements/dim-statement.md), with or without the [Static](../../../language-reference/modifiers/static.md) keyword.</span></span>

<span data-ttu-id="1cb99-148">Prozedur-und Block Bereich sind eng miteinander verknüpft.</span><span class="sxs-lookup"><span data-stu-id="1cb99-148">Procedure and block scope are closely related.</span></span> <span data-ttu-id="1cb99-149">Wenn Sie eine Variable innerhalb einer Prozedur, aber außerhalb eines Blocks innerhalb dieser Prozedur deklarieren, können Sie sich die Variable als Block Bereich vorstellen, in dem der Block die gesamte Prozedur ist.</span><span class="sxs-lookup"><span data-stu-id="1cb99-149">If you declare a variable inside a procedure but outside any block within that procedure, you can think of the variable as having block scope, where the block is the entire procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="1cb99-150">Alle lokalen Elemente, selbst wenn Sie `Static` Variablen sind, sind privat für die Prozedur, in der Sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1cb99-150">All local elements, even if they are `Static` variables, are private to the procedure in which they appear.</span></span> <span data-ttu-id="1cb99-151">Sie können ein beliebiges Element nicht mithilfe des [Public](../../../language-reference/modifiers/public.md) -Schlüssel Worts innerhalb einer Prozedur deklarieren.</span><span class="sxs-lookup"><span data-stu-id="1cb99-151">You cannot declare any element using the [Public](../../../language-reference/modifiers/public.md) keyword within a procedure.</span></span>

### <a name="module-scope"></a><span data-ttu-id="1cb99-152">Modul Bereich</span><span class="sxs-lookup"><span data-stu-id="1cb99-152">Module Scope</span></span>

<span data-ttu-id="1cb99-153">Der Vorteil ist, dass die einzelne Begriffs *Modulebene* gleichermaßen auf Module, Klassen und Strukturen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="1cb99-153">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="1cb99-154">Sie können Elemente auf dieser Ebene deklarieren, indem Sie die Deklarations Anweisung außerhalb einer Prozedur oder eines Blocks, aber innerhalb des Moduls, der Klasse oder der Struktur platzieren.</span><span class="sxs-lookup"><span data-stu-id="1cb99-154">You can declare elements at this level by placing the declaration statement outside of any procedure or block but within the module, class, or structure.</span></span>

<span data-ttu-id="1cb99-155">Wenn Sie auf Modulebene eine Deklaration erstellen, bestimmt die von Ihnen gewählte Zugriffsebene den Bereich.</span><span class="sxs-lookup"><span data-stu-id="1cb99-155">When you make a declaration at the module level, the access level you choose determines the scope.</span></span> <span data-ttu-id="1cb99-156">Der Namespace, der das Modul, die Klasse oder die Struktur enthält, wirkt sich auch auf den Bereich aus.</span><span class="sxs-lookup"><span data-stu-id="1cb99-156">The namespace that contains the module, class, or structure also affects the scope.</span></span>

<span data-ttu-id="1cb99-157">Elemente, für die Sie die [private](../../../language-reference/modifiers/private.md) Zugriffsebene deklarieren, sind für jede Prozedur in diesem Modul verfügbar, aber nicht für Code in einem anderen Modul.</span><span class="sxs-lookup"><span data-stu-id="1cb99-157">Elements for which you declare [Private](../../../language-reference/modifiers/private.md) access level are available to every procedure in that module, but not to any code in a different module.</span></span> <span data-ttu-id="1cb99-158">Die- `Dim` Anweisung auf Modulebene hat standardmäßig den Wert, `Private` Wenn Sie keine Zugriffsebenen-Schlüsselwörter verwenden.</span><span class="sxs-lookup"><span data-stu-id="1cb99-158">The `Dim` statement at module level defaults to `Private` if you do not use any access level keywords.</span></span> <span data-ttu-id="1cb99-159">Sie können jedoch den Bereich und die Zugriffsebene deutlicher machen, indem Sie das- `Private` Schlüsselwort in der- `Dim` Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="1cb99-159">However, you can make the scope and access level more obvious by using the `Private` keyword in the `Dim` statement.</span></span>

<span data-ttu-id="1cb99-160">Im folgenden Beispiel können alle im Modul definierten Prozeduren auf die Zeichen folgen Variable verweisen `strMsg` .</span><span class="sxs-lookup"><span data-stu-id="1cb99-160">In the following example, all procedures defined in the module can refer to the string variable `strMsg`.</span></span> <span data-ttu-id="1cb99-161">Wenn die zweite Prozedur aufgerufen wird, wird der Inhalt der Zeichen folgen Variablen `strMsg` in einem Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1cb99-161">When the second procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>

```vb
' Put the following declaration at module level (not in any procedure).
Private strMsg As String
' Put the following Sub procedure in the same module.
Sub initializePrivateVariable()
    strMsg = "This variable cannot be used outside this module."
End Sub
' Put the following Sub procedure in the same module.
Sub usePrivateVariable()
    MsgBox(strMsg)
End Sub
```

### <a name="namespace-scope"></a><span data-ttu-id="1cb99-162">Namespace Bereich</span><span class="sxs-lookup"><span data-stu-id="1cb99-162">Namespace Scope</span></span>

<span data-ttu-id="1cb99-163">Wenn Sie ein Element auf Modulebene mit dem [Friend](../../../language-reference/modifiers/friend.md) -oder [Public](../../../language-reference/modifiers/public.md) -Schlüsselwort deklarieren, steht es allen Prozeduren im gesamten Namespace zur Verfügung, in dem das Element deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="1cb99-163">If you declare an element at module level using the [Friend](../../../language-reference/modifiers/friend.md) or [Public](../../../language-reference/modifiers/public.md) keyword, it becomes available to all procedures throughout the namespace in which the element is declared.</span></span> <span data-ttu-id="1cb99-164">Mit der folgenden Änderung am vorangehenden Beispiel kann auf die Zeichen folgen Variable an `strMsg` beliebiger Stelle im Namespace der zugehörigen Deklaration verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1cb99-164">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>

```vb
' Include this declaration at module level (not inside any procedure).
Public strMsg As String
```

<span data-ttu-id="1cb99-165">Der Namespace Bereich schließt schsted Namespaces ein.</span><span class="sxs-lookup"><span data-stu-id="1cb99-165">Namespace scope includes nested namespaces.</span></span> <span data-ttu-id="1cb99-166">Ein Element, das in einem Namespace verfügbar ist, steht auch in allen Namespaces zur Verfügung, die in diesem Namespace geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="1cb99-166">An element available from within a namespace is also available from within any namespace nested inside that namespace.</span></span>

<span data-ttu-id="1cb99-167">Wenn das Projekt keine [Namespace-Anweisung](../../../language-reference/statements/namespace-statement.md)s enthält, befindet sich alles im Projekt im selben Namespace.</span><span class="sxs-lookup"><span data-stu-id="1cb99-167">If your project does not contain any [Namespace Statement](../../../language-reference/statements/namespace-statement.md)s, everything in the project is in the same namespace.</span></span> <span data-ttu-id="1cb99-168">In diesem Fall kann sich der Namespace Bereich als Projektbereich vorstellen.</span><span class="sxs-lookup"><span data-stu-id="1cb99-168">In this case, namespace scope can be thought of as project scope.</span></span> <span data-ttu-id="1cb99-169">`Public`Elemente in einem Modul, einer Klasse oder einer Struktur sind auch für jedes Projekt verfügbar, das auf das Projekt verweist.</span><span class="sxs-lookup"><span data-stu-id="1cb99-169">`Public` elements in a module, class, or structure are also available to any project that references their project.</span></span>

## <a name="choice-of-scope"></a><span data-ttu-id="1cb99-170">Auswahl des Bereichs</span><span class="sxs-lookup"><span data-stu-id="1cb99-170">Choice of Scope</span></span>

<span data-ttu-id="1cb99-171">Wenn Sie eine Variable deklarieren, sollten Sie die folgenden Punkte berücksichtigen, wenn Sie Ihren Bereich auswählen.</span><span class="sxs-lookup"><span data-stu-id="1cb99-171">When you declare a variable, you should keep in mind the following points when choosing its scope.</span></span>

### <a name="advantages-of-local-variables"></a><span data-ttu-id="1cb99-172">Vorteile lokaler Variablen</span><span class="sxs-lookup"><span data-stu-id="1cb99-172">Advantages of Local Variables</span></span>

<span data-ttu-id="1cb99-173">Lokale Variablen sind aus folgenden Gründen eine gute Wahl für jede Art von temporärer Berechnung:</span><span class="sxs-lookup"><span data-stu-id="1cb99-173">Local variables are a good choice for any kind of temporary calculation, for the following reasons:</span></span>

- <span data-ttu-id="1cb99-174">**Vermeiden von Namenskonflikten.**</span><span class="sxs-lookup"><span data-stu-id="1cb99-174">**Name Conflict Avoidance.**</span></span> <span data-ttu-id="1cb99-175">Lokale Variablennamen sind nicht anfällig für Konflikte.</span><span class="sxs-lookup"><span data-stu-id="1cb99-175">Local variable names are not susceptible to conflict.</span></span> <span data-ttu-id="1cb99-176">Beispielsweise können Sie mehrere verschiedene Prozeduren erstellen, die eine Variable mit dem Namen enthalten `intTemp` .</span><span class="sxs-lookup"><span data-stu-id="1cb99-176">For example, you can create several different procedures containing a variable called `intTemp`.</span></span> <span data-ttu-id="1cb99-177">Solange `intTemp` die einzelnen Prozeduren als lokale Variable deklariert sind, erkennt jede Prozedur nur Ihre eigene Version von `intTemp` .</span><span class="sxs-lookup"><span data-stu-id="1cb99-177">As long as each `intTemp` is declared as a local variable, each procedure recognizes only its own version of `intTemp`.</span></span> <span data-ttu-id="1cb99-178">Jede der Prozeduren kann den Wert in der lokalen ändern, `intTemp` ohne dass `intTemp` Variablen in anderen Prozeduren beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="1cb99-178">Any one procedure can alter the value in its local `intTemp` without affecting `intTemp` variables in other procedures.</span></span>

- <span data-ttu-id="1cb99-179">**Arbeitsspeicher Nutzung.**</span><span class="sxs-lookup"><span data-stu-id="1cb99-179">**Memory Consumption.**</span></span> <span data-ttu-id="1cb99-180">Lokale Variablen belegen nur Speicher, während Ihre Prozedur ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1cb99-180">Local variables consume memory only while their procedure is running.</span></span> <span data-ttu-id="1cb99-181">Der Arbeitsspeicher wird freigegeben, wenn die Prozedur an den aufrufenden Code zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1cb99-181">Their memory is released when the procedure returns to the calling code.</span></span> <span data-ttu-id="1cb99-182">Im Gegensatz dazu verbrauchen frei [gegebene](../../../language-reference/modifiers/shared.md) und [statische](../../../language-reference/modifiers/static.md) Variablen Speicherressourcen, bis Ihre Anwendung nicht mehr ausgeführt wird. verwenden Sie Sie daher nur bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="1cb99-182">By contrast, [Shared](../../../language-reference/modifiers/shared.md) and [Static](../../../language-reference/modifiers/static.md) variables consume memory resources until your application stops running, so use them only when necessary.</span></span> <span data-ttu-id="1cb99-183">*Instanzvariablen* belegen Arbeitsspeicher, während Ihre Instanz weiterhin vorhanden ist, wodurch Sie weniger effizient sind als lokale Variablen, aber potenziell effizienter als- `Shared` oder- `Static` Variablen.</span><span class="sxs-lookup"><span data-stu-id="1cb99-183">*Instance variables* consume memory while their instance continues to exist, which makes them less efficient than local variables, but potentially more efficient than `Shared` or `Static` variables.</span></span>

### <a name="minimizing-scope"></a><span data-ttu-id="1cb99-184">Minimieren des Bereichs</span><span class="sxs-lookup"><span data-stu-id="1cb99-184">Minimizing Scope</span></span>

<span data-ttu-id="1cb99-185">Beim Deklarieren einer Variablen oder Konstanten empfiehlt es sich im Allgemeinen, den Bereich so schmal wie möglich zu machen (Block Bereich ist die engste).</span><span class="sxs-lookup"><span data-stu-id="1cb99-185">In general, when declaring any variable or constant, it is good programming practice to make the scope as narrow as possible (block scope is the narrowest).</span></span> <span data-ttu-id="1cb99-186">Dadurch wird Speicherplatz gespart, und die Wahrscheinlichkeit, dass Ihr Code fälschlicherweise auf die falsche Variable verweist, wird minimiert.</span><span class="sxs-lookup"><span data-stu-id="1cb99-186">This helps conserve memory and minimizes the chances of your code erroneously referring to the wrong variable.</span></span> <span data-ttu-id="1cb99-187">Ebenso sollten Sie eine Variable so deklarieren, dass Sie nur [statisch](../../../language-reference/modifiers/static.md) ist, wenn der Wert zwischen Prozedur aufrufen beibehalten werden muss.</span><span class="sxs-lookup"><span data-stu-id="1cb99-187">Similarly, you should declare a variable to be [Static](../../../language-reference/modifiers/static.md) only when it is necessary to preserve its value between procedure calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="1cb99-188">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1cb99-188">See also</span></span>

- [<span data-ttu-id="1cb99-189">Merkmale deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="1cb99-189">Declared Element Characteristics</span></span>](declared-element-characteristics.md)
- [<span data-ttu-id="1cb99-190">Vorgehensweise: Steuern des Gültigkeitsbereichs einer Variablen</span><span class="sxs-lookup"><span data-stu-id="1cb99-190">How to: Control the Scope of a Variable</span></span>](how-to-control-the-scope-of-a-variable.md)
- [<span data-ttu-id="1cb99-191">Lebensdauer in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1cb99-191">Lifetime in Visual Basic</span></span>](lifetime.md)
- [<span data-ttu-id="1cb99-192">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1cb99-192">Access levels in Visual Basic</span></span>](access-levels.md)
- [<span data-ttu-id="1cb99-193">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="1cb99-193">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="1cb99-194">Variablen Deklaration</span><span class="sxs-lookup"><span data-stu-id="1cb99-194">Variable Declaration</span></span>](../variables/variable-declaration.md)
