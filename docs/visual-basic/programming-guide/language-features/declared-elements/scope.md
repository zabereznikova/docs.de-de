---
title: "Gültigkeitsbereich in Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a9bfda19b9f5ee96d45a0322541b35dfab7635d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="scope-in-visual-basic"></a><span data-ttu-id="d6b92-102">Gültigkeitsbereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d6b92-102">Scope in Visual Basic</span></span>
<span data-ttu-id="d6b92-103">Die *Bereich* eines deklarierten Elements ist die Menge des gesamten Codes, die darauf verweisen kann, ohne seinen Namen qualifizieren oder durch Verfügbarmachen einer [Imports-Anweisung (.NET Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="d6b92-103">The *scope* of a declared element is the set of all code that can refer to it without qualifying its name or making it available through an [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span> <span data-ttu-id="d6b92-104">Ein Element kann in einem der folgenden Ebenen Bereich aufweisen:</span><span class="sxs-lookup"><span data-stu-id="d6b92-104">An element can have scope at one of the following levels:</span></span>  
  
|<span data-ttu-id="d6b92-105">Ebene</span><span class="sxs-lookup"><span data-stu-id="d6b92-105">Level</span></span>|<span data-ttu-id="d6b92-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d6b92-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d6b92-107">Blockbereich</span><span class="sxs-lookup"><span data-stu-id="d6b92-107">Block scope</span></span>|<span data-ttu-id="d6b92-108">Verfügbar nur innerhalb des Codes blockiert, in dem sie deklariert ist</span><span class="sxs-lookup"><span data-stu-id="d6b92-108">Available only within the code block in which it is declared</span></span>|  
|<span data-ttu-id="d6b92-109">Prozedurbereich</span><span class="sxs-lookup"><span data-stu-id="d6b92-109">Procedure scope</span></span>|<span data-ttu-id="d6b92-110">Verfügbar für sämtlichen Code innerhalb der Prozedur, die in der sie deklariert ist</span><span class="sxs-lookup"><span data-stu-id="d6b92-110">Available to all code within the procedure in which it is declared</span></span>|  
|<span data-ttu-id="d6b92-111">Modulbereich</span><span class="sxs-lookup"><span data-stu-id="d6b92-111">Module scope</span></span>|<span data-ttu-id="d6b92-112">Verfügbar für sämtlichen Code innerhalb das Modul, Klasse oder Struktur, die in der sie deklariert ist</span><span class="sxs-lookup"><span data-stu-id="d6b92-112">Available to all code within the module, class, or structure in which it is declared</span></span>|  
|<span data-ttu-id="d6b92-113">Namespace-Gültigkeitsbereich</span><span class="sxs-lookup"><span data-stu-id="d6b92-113">Namespace scope</span></span>|<span data-ttu-id="d6b92-114">Verfügbar für den gesamten Code im Namespace, in dem sie deklariert ist</span><span class="sxs-lookup"><span data-stu-id="d6b92-114">Available to all code in the namespace in which it is declared</span></span>|  
  
 <span data-ttu-id="d6b92-115">Diese Ebenen Bereich Status aus dem engsten (Block) auf den umfassendsten (Namespace), in denen *engsten Gültigkeitsbereich* bedeutet, dass die kleinste Menge der Code, der auf das Element ohne Qualifizierung verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="d6b92-115">These levels of scope progress from the narrowest (block) to the widest (namespace), where *narrowest scope* means the smallest set of code that can refer to the element without qualification.</span></span> <span data-ttu-id="d6b92-116">Weitere Informationen finden Sie unter "Ebenen Scope" auf dieser Seite.</span><span class="sxs-lookup"><span data-stu-id="d6b92-116">For more information, see "Levels of Scope" on this page.</span></span>  
  
## <a name="specifying-scope-and-defining-variables"></a><span data-ttu-id="d6b92-117">Festlegen des Gültigkeitsbereichs und Definieren von Variablen</span><span class="sxs-lookup"><span data-stu-id="d6b92-117">Specifying Scope and Defining Variables</span></span>  
 <span data-ttu-id="d6b92-118">Wenn Sie deklariert werden, geben Sie den Bereich eines Elements.</span><span class="sxs-lookup"><span data-stu-id="d6b92-118">You specify the scope of an element when you declare it.</span></span> <span data-ttu-id="d6b92-119">Der Bereich kann die folgenden Faktoren abhängig:</span><span class="sxs-lookup"><span data-stu-id="d6b92-119">The scope can depend on the following factors:</span></span>  
  
-   <span data-ttu-id="d6b92-120">Die Region (Block, Prozedur, Modul, Klasse oder Struktur), in der Sie das Element deklariert werden</span><span class="sxs-lookup"><span data-stu-id="d6b92-120">The region (block, procedure, module, class, or structure) in which you declare the element</span></span>  
  
-   <span data-ttu-id="d6b92-121">Der Namespace, die die Deklaration des Elements enthält.</span><span class="sxs-lookup"><span data-stu-id="d6b92-121">The namespace containing the element's declaration</span></span>  
  
-   <span data-ttu-id="d6b92-122">Die Zugriffsebene, die Sie für das Element deklarieren</span><span class="sxs-lookup"><span data-stu-id="d6b92-122">The access level you declare for the element</span></span>  
  
 <span data-ttu-id="d6b92-123">Gehen Sie sorgfältig vor, wenn Sie Variablen mit dem gleichen Namen, aber andere Bereiche definieren, da dies zu erheblichen kann zu unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="d6b92-123">Use care when you define variables with the same name but different scope, because doing so can lead to unexpected results.</span></span> <span data-ttu-id="d6b92-124">Weitere Informationen finden Sie unter [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="d6b92-124">For more information, see [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="levels-of-scope"></a><span data-ttu-id="d6b92-125">Ebenen des Gültigkeitsbereichs</span><span class="sxs-lookup"><span data-stu-id="d6b92-125">Levels of Scope</span></span>  
 <span data-ttu-id="d6b92-126">Ein Programmierelement ist verfügbar in der Region, in der Sie deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="d6b92-126">A programming element is available throughout the region in which you declare it.</span></span> <span data-ttu-id="d6b92-127">Der gesamte Code in der gleichen Region kann auf das Element verweisen, ohne dessen Namen zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="d6b92-127">All code in the same region can refer to the element without qualifying its name.</span></span>  
  
### <a name="block-scope"></a><span data-ttu-id="d6b92-128">Blockbereich</span><span class="sxs-lookup"><span data-stu-id="d6b92-128">Block Scope</span></span>  
 <span data-ttu-id="d6b92-129">Ein Block ist eine Reihe von Anweisungen eingefasst initiiert und beendet deklarationsanweisungen, wie z. B. die folgenden:</span><span class="sxs-lookup"><span data-stu-id="d6b92-129">A block is a set of statements enclosed within initiating and terminating declaration statements, such as the following:</span></span>  
  
-   <span data-ttu-id="d6b92-130">`Do` und `Loop`</span><span class="sxs-lookup"><span data-stu-id="d6b92-130">`Do` and `Loop`</span></span>  
  
-   <span data-ttu-id="d6b92-131">`For`[`Each`] und`Next`</span><span class="sxs-lookup"><span data-stu-id="d6b92-131">`For` [`Each`] and `Next`</span></span>  
  
-   <span data-ttu-id="d6b92-132">`If` und `End If`</span><span class="sxs-lookup"><span data-stu-id="d6b92-132">`If` and `End If`</span></span>  
  
-   <span data-ttu-id="d6b92-133">`Select` und `End Select`</span><span class="sxs-lookup"><span data-stu-id="d6b92-133">`Select` and `End Select`</span></span>  
  
-   <span data-ttu-id="d6b92-134">`SyncLock` und `End SyncLock`</span><span class="sxs-lookup"><span data-stu-id="d6b92-134">`SyncLock` and `End SyncLock`</span></span>  
  
-   <span data-ttu-id="d6b92-135">`Try` und `End Try`</span><span class="sxs-lookup"><span data-stu-id="d6b92-135">`Try` and `End Try`</span></span>  
  
-   <span data-ttu-id="d6b92-136">`While` und `End While`</span><span class="sxs-lookup"><span data-stu-id="d6b92-136">`While` and `End While`</span></span>  
  
-   <span data-ttu-id="d6b92-137">`With` und `End With`</span><span class="sxs-lookup"><span data-stu-id="d6b92-137">`With` and `End With`</span></span>  
  
 <span data-ttu-id="d6b92-138">Wenn Sie eine Variable innerhalb eines Blocks zu deklarieren, können Sie es nur innerhalb dieses Blocks verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6b92-138">If you declare a variable within a block, you can use it only within that block.</span></span> <span data-ttu-id="d6b92-139">Im folgenden Beispiel, den Bereich der ganzzahligen Variablen `cube` wird der Block zwischen `If` und `End If`, und Sie können nicht mehr beziehen sich auf `cube` Wenn die Ausführung aus dem Block übergeben.</span><span class="sxs-lookup"><span data-stu-id="d6b92-139">In the following example, the scope of the integer variable `cube` is the block between `If` and `End If`, and you can no longer refer to `cube` when execution passes out of the block.</span></span>  
  
```  
If n < 1291 Then  
    Dim cube As Integer  
    cube = n ^ 3  
End If  
```  
  
> [!NOTE]
>  <span data-ttu-id="d6b92-140">Auch wenn der Gültigkeitsbereich einer Variablen auf einen Block beschränkt ist, ist seine Lebensdauer immer noch der gesamten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="d6b92-140">Even if the scope of a variable is limited to a block, its lifetime is still that of the entire procedure.</span></span> <span data-ttu-id="d6b92-141">Wenn Sie den Block während der Prozedur mehr als einmal eingeben, behält jede Blockvariable seinen ursprünglichen Wert.</span><span class="sxs-lookup"><span data-stu-id="d6b92-141">If you enter the block more than once during the procedure, each block variable retains its previous value.</span></span> <span data-ttu-id="d6b92-142">Um unerwartete Ergebnisse in einem solchen Fall zu vermeiden, ist es ratsam, Block Variablen am Anfang des Blocks zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="d6b92-142">To avoid unexpected results in such a case, it is wise to initialize block variables at the beginning of the block.</span></span>  
  
### <a name="procedure-scope"></a><span data-ttu-id="d6b92-143">Prozedurbereich</span><span class="sxs-lookup"><span data-stu-id="d6b92-143">Procedure Scope</span></span>  
 <span data-ttu-id="d6b92-144">Ein Element innerhalb einer Prozedur deklariert ist nicht außerhalb dieser Prozedur verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d6b92-144">An element declared within a procedure is not available outside that procedure.</span></span> <span data-ttu-id="d6b92-145">Nur die Prozedur, die die Deklaration enthält können.</span><span class="sxs-lookup"><span data-stu-id="d6b92-145">Only the procedure that contains the declaration can use it.</span></span> <span data-ttu-id="d6b92-146">Variablen, die auf dieser Ebene werden auch bezeichnet als *lokale Variablen*.</span><span class="sxs-lookup"><span data-stu-id="d6b92-146">Variables at this level are also known as *local variables*.</span></span> <span data-ttu-id="d6b92-147">Sie deklarieren sie mit der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)mit oder ohne die [statische](../../../../visual-basic/language-reference/modifiers/static.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="d6b92-147">You declare them with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), with or without the [Static](../../../../visual-basic/language-reference/modifiers/static.md) keyword.</span></span>  
  
 <span data-ttu-id="d6b92-148">Verfahren und der Blockbereich sind eng miteinander verknüpft.</span><span class="sxs-lookup"><span data-stu-id="d6b92-148">Procedure and block scope are closely related.</span></span> <span data-ttu-id="d6b92-149">Wenn Sie eine Variable innerhalb einer Prozedur deklarieren, jedoch außerhalb aller Blöcke innerhalb der Prozedur, können Sie die Variable als Blockbereich, wobei der Block die gesamte Prozedur ist vorstellen.</span><span class="sxs-lookup"><span data-stu-id="d6b92-149">If you declare a variable inside a procedure but outside any block within that procedure, you can think of the variable as having block scope, where the block is the entire procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6b92-150">Alle lokalen Elemente, auch wenn sie sind `Static` Variablen sind privat, an die Prozedur in der sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d6b92-150">All local elements, even if they are `Static` variables, are private to the procedure in which they appear.</span></span> <span data-ttu-id="d6b92-151">Sie können nicht deklariert werden alle-Element mithilfe der [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md) Schlüsselwort innerhalb einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="d6b92-151">You cannot declare any element using the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword within a procedure.</span></span>  
  
### <a name="module-scope"></a><span data-ttu-id="d6b92-152">Modulbereich</span><span class="sxs-lookup"><span data-stu-id="d6b92-152">Module Scope</span></span>  
 <span data-ttu-id="d6b92-153">Der Einfachheit halber einen einzelnen Ausdruck *Modulebene* gilt gleichermaßen für Module, Klassen und Strukturen.</span><span class="sxs-lookup"><span data-stu-id="d6b92-153">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="d6b92-154">Sie können Elemente auf dieser Ebene platzieren der deklarationsanweisung außerhalb von Prozeduren oder Block, jedoch innerhalb das Modul, Klasse oder Struktur deklarieren.</span><span class="sxs-lookup"><span data-stu-id="d6b92-154">You can declare elements at this level by placing the declaration statement outside of any procedure or block but within the module, class, or structure.</span></span>  
  
 <span data-ttu-id="d6b92-155">Wenn Sie eine Deklaration auf Modulebene vornehmen, bestimmt die Zugriffsebene, die Sie auswählen, den Bereich an.</span><span class="sxs-lookup"><span data-stu-id="d6b92-155">When you make a declaration at the module level, the access level you choose determines the scope.</span></span> <span data-ttu-id="d6b92-156">Der Namespace, der das Modul, Klasse oder Struktur enthält, wirkt sich auch auf den Bereich aus.</span><span class="sxs-lookup"><span data-stu-id="d6b92-156">The namespace that contains the module, class, or structure also affects the scope.</span></span>  
  
 <span data-ttu-id="d6b92-157">Elemente, die für die Sie deklarieren [Private](../../../../visual-basic/language-reference/modifiers/private.md) Zugriffsebene zur Verfügung stehen, um jede Prozedur in diesem Modul, jedoch nicht zu jedem Code in einem anderen Modul.</span><span class="sxs-lookup"><span data-stu-id="d6b92-157">Elements for which you declare [Private](../../../../visual-basic/language-reference/modifiers/private.md) access level are available to every procedure in that module, but not to any code in a different module.</span></span> <span data-ttu-id="d6b92-158">Die `Dim` Anweisung auf Modulebene standardmäßig `Private` , wenn Sie keine Zugriffsebenen-Schlüsselwörter verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6b92-158">The `Dim` statement at module level defaults to `Private` if you do not use any access level keywords.</span></span> <span data-ttu-id="d6b92-159">Allerdings möglich den Bereich und die erforderlichen Zugriffsebenen leichter mithilfe der `Private` -Schlüsselwort in der `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d6b92-159">However, you can make the scope and access level more obvious by using the `Private` keyword in the `Dim` statement.</span></span>  
  
 <span data-ttu-id="d6b92-160">Im folgenden Beispiel können alle im Modul definierte Prozeduren verweisen, der Zeichenfolgenvariablen `strMsg`.</span><span class="sxs-lookup"><span data-stu-id="d6b92-160">In the following example, all procedures defined in the module can refer to the string variable `strMsg`.</span></span> <span data-ttu-id="d6b92-161">Wenn die zweite Prozedur aufgerufen wird, zeigt er den Inhalt der Zeichenfolgenvariablen `strMsg` in einem Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="d6b92-161">When the second procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
```  
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
  
### <a name="namespace-scope"></a><span data-ttu-id="d6b92-162">Namespace-Gültigkeitsbereich</span><span class="sxs-lookup"><span data-stu-id="d6b92-162">Namespace Scope</span></span>  
 <span data-ttu-id="d6b92-163">Wenn Sie ein Element an das Modul mit deklarieren die ["Friend"](../../../../visual-basic/language-reference/modifiers/friend.md) oder [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüsselwort verwenden, steht es für alle Prozeduren in der gesamten den Namespace, in dem das Element deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="d6b92-163">If you declare an element at module level using the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword, it becomes available to all procedures throughout the namespace in which the element is declared.</span></span> <span data-ttu-id="d6b92-164">Mit der folgenden Änderung im vorhergehenden Beispiel, die Zeichenfolgenvariable `strMsg` können von Code an einer beliebigen Stelle in den Namespace der Deklaration bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="d6b92-164">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```  
' Include this declaration at module level (not inside any procedure).  
Public strMsg As String  
```  
  
 <span data-ttu-id="d6b92-165">Namespace-Gültigkeitsbereich enthält geschachtelte Namespaces.</span><span class="sxs-lookup"><span data-stu-id="d6b92-165">Namespace scope includes nested namespaces.</span></span> <span data-ttu-id="d6b92-166">Ein Element innerhalb eines Namespaces zur Verfügung steht auch auf in allen Namespaces, die in diesem Namespace geschachtelt.</span><span class="sxs-lookup"><span data-stu-id="d6b92-166">An element available from within a namespace is also available from within any namespace nested inside that namespace.</span></span>  
  
 <span data-ttu-id="d6b92-167">Wenn Ihr Projekt keine enthält [Namespace-Anweisung](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, alles im Projekt befindet sich im gleichen Namespace.</span><span class="sxs-lookup"><span data-stu-id="d6b92-167">If your project does not contain any [Namespace Statement](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, everything in the project is in the same namespace.</span></span> <span data-ttu-id="d6b92-168">In diesem Fall kann der Namespace-Gültigkeitsbereich als Projektumfang betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="d6b92-168">In this case, namespace scope can be thought of as project scope.</span></span> <span data-ttu-id="d6b92-169">`Public`Elemente in einem Modul, Klasse oder Struktur stehen auch zu einem Projekt, die ihr Projekt verweist.</span><span class="sxs-lookup"><span data-stu-id="d6b92-169">`Public` elements in a module, class, or structure are also available to any project that references their project.</span></span>  
  
## <a name="choice-of-scope"></a><span data-ttu-id="d6b92-170">Auswahl eines Bereichs</span><span class="sxs-lookup"><span data-stu-id="d6b92-170">Choice of Scope</span></span>  
 <span data-ttu-id="d6b92-171">Wenn Sie eine Variable deklarieren, sollten Sie die folgenden Punkte bedenken bei der Auswahl des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="d6b92-171">When you declare a variable, you should keep in mind the following points when choosing its scope.</span></span>  
  
### <a name="advantages-of-local-variables"></a><span data-ttu-id="d6b92-172">Vorteile von lokalen Variablen</span><span class="sxs-lookup"><span data-stu-id="d6b92-172">Advantages of Local Variables</span></span>  
 <span data-ttu-id="d6b92-173">Lokale Variablen sind eine gute Wahl für alle Arten von temporären Berechnung folgende Gründe vorliegen:</span><span class="sxs-lookup"><span data-stu-id="d6b92-173">Local variables are a good choice for any kind of temporary calculation, for the following reasons:</span></span>  
  
-   <span data-ttu-id="d6b92-174">**Vermeidung von Namenskonflikten.**</span><span class="sxs-lookup"><span data-stu-id="d6b92-174">**Name Conflict Avoidance.**</span></span> <span data-ttu-id="d6b92-175">Namen lokaler Variable sind nicht anfällig für in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="d6b92-175">Local variable names are not susceptible to conflict.</span></span> <span data-ttu-id="d6b92-176">Sie können z. B. mehrere unterschiedliche Verfahren, die eine Variable Namens enthält erstellen `intTemp`.</span><span class="sxs-lookup"><span data-stu-id="d6b92-176">For example, you can create several different procedures containing a variable called `intTemp`.</span></span> <span data-ttu-id="d6b92-177">Solange jeder `intTemp` wird deklariert als lokale Variable, jede Prozedur erkennt nur ihre eigene Version der `intTemp`.</span><span class="sxs-lookup"><span data-stu-id="d6b92-177">As long as each `intTemp` is declared as a local variable, each procedure recognizes only its own version of `intTemp`.</span></span> <span data-ttu-id="d6b92-178">Jede Prozedur ändern, kann den Wert in der lokalen `intTemp` ohne `intTemp` Variablen in anderen Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="d6b92-178">Any one procedure can alter the value in its local `intTemp` without affecting `intTemp` variables in other procedures.</span></span>  
  
-   <span data-ttu-id="d6b92-179">**Speicherverbrauch.**</span><span class="sxs-lookup"><span data-stu-id="d6b92-179">**Memory Consumption.**</span></span> <span data-ttu-id="d6b92-180">Lokale Variablen belegt Arbeitsspeicher nur, wenn die Prozedur ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d6b92-180">Local variables consume memory only while their procedure is running.</span></span> <span data-ttu-id="d6b92-181">Ihre Arbeitsspeicher wird freigegeben, wenn die Prozedur an den aufrufenden Code zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d6b92-181">Their memory is released when the procedure returns to the calling code.</span></span> <span data-ttu-id="d6b92-182">Im Gegensatz dazu [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) und [statische](../../../../visual-basic/language-reference/modifiers/static.md) Variablen Arbeitsspeicherressourcen beanspruchen, bis die Anwendung beendet wird, werden daher nur bei Bedarf verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6b92-182">By contrast, [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) and [Static](../../../../visual-basic/language-reference/modifiers/static.md) variables consume memory resources until your application stops running, so use them only when necessary.</span></span> <span data-ttu-id="d6b92-183">*Instanzvariablen* belegt Arbeitsspeicher während ihrer Instanz vorhanden weiterhin, sodass sie weniger effizient als lokale Variablen, aber möglicherweise effizienter als `Shared` oder `Static` Variablen.</span><span class="sxs-lookup"><span data-stu-id="d6b92-183">*Instance variables* consume memory while their instance continues to exist, which makes them less efficient than local variables, but potentially more efficient than `Shared` or `Static` variables.</span></span>  
  
### <a name="minimizing-scope"></a><span data-ttu-id="d6b92-184">Minimieren des Gültigkeitsbereichs</span><span class="sxs-lookup"><span data-stu-id="d6b92-184">Minimizing Scope</span></span>  
 <span data-ttu-id="d6b92-185">Wenn Sie eine Variable oder Konstante deklarieren, wird es im Allgemeinen als guter Programmierstil, um den Bereich so eng wie möglich zu machen (Blockbereich ist die engste).</span><span class="sxs-lookup"><span data-stu-id="d6b92-185">In general, when declaring any variable or constant, it is good programming practice to make the scope as narrow as possible (block scope is the narrowest).</span></span> <span data-ttu-id="d6b92-186">Dies hilft, Speicherplatz zu sparen und minimiert die Wahrscheinlichkeit des Codes, die fälschlicherweise auf die falsche Variable verweisen.</span><span class="sxs-lookup"><span data-stu-id="d6b92-186">This helps conserve memory and minimizes the chances of your code erroneously referring to the wrong variable.</span></span> <span data-ttu-id="d6b92-187">Ebenso sollten Sie eine Variable deklarieren [statische](../../../../visual-basic/language-reference/modifiers/static.md) nur wenn Objektwerts zwischen Prozeduraufrufe beibehalten werden muss.</span><span class="sxs-lookup"><span data-stu-id="d6b92-187">Similarly, you should declare a variable to be [Static](../../../../visual-basic/language-reference/modifiers/static.md) only when it is necessary to preserve its value between procedure calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6b92-188">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6b92-188">See Also</span></span>  
 [<span data-ttu-id="d6b92-189">Merkmale deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="d6b92-189">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [<span data-ttu-id="d6b92-190">Gewusst wie: Steuern des Gültigkeitsbereichs einer Variablen</span><span class="sxs-lookup"><span data-stu-id="d6b92-190">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)  
 [<span data-ttu-id="d6b92-191">Lebensdauer in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d6b92-191">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [<span data-ttu-id="d6b92-192">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d6b92-192">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="d6b92-193">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="d6b92-193">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="d6b92-194">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="d6b92-194">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
