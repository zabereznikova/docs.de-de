---
title: Gültigkeitsbereich in Visual Basic
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
ms.openlocfilehash: 6139af65958cefe43578f436204fa6836a71de0b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58823544"
---
# <a name="scope-in-visual-basic"></a><span data-ttu-id="d4fc2-102">Gültigkeitsbereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4fc2-102">Scope in Visual Basic</span></span>
<span data-ttu-id="d4fc2-103">Die *Bereich* eines deklarierten Elements ist ein Satz von sämtlicher Code, die darauf verweisen kann, ohne seinen Namen qualifizieren oder durch Verfügbarmachen, einer [Imports-Anweisung (.NET-Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="d4fc2-103">The *scope* of a declared element is the set of all code that can refer to it without qualifying its name or making it available through an [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span> <span data-ttu-id="d4fc2-104">Ein Element kann eine der folgenden Ebenen Bereich sein:</span><span class="sxs-lookup"><span data-stu-id="d4fc2-104">An element can have scope at one of the following levels:</span></span>  
  
|<span data-ttu-id="d4fc2-105">Ebene</span><span class="sxs-lookup"><span data-stu-id="d4fc2-105">Level</span></span>|<span data-ttu-id="d4fc2-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4fc2-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d4fc2-107">Blockbereich</span><span class="sxs-lookup"><span data-stu-id="d4fc2-107">Block scope</span></span>|<span data-ttu-id="d4fc2-108">Verfügbar nur in den Code blockieren, in dem sie deklariert ist</span><span class="sxs-lookup"><span data-stu-id="d4fc2-108">Available only within the code block in which it is declared</span></span>|  
|<span data-ttu-id="d4fc2-109">Prozedurbereich</span><span class="sxs-lookup"><span data-stu-id="d4fc2-109">Procedure scope</span></span>|<span data-ttu-id="d4fc2-110">Verfügbar für sämtlichen Code innerhalb der Prozedur, die in der sie deklariert ist</span><span class="sxs-lookup"><span data-stu-id="d4fc2-110">Available to all code within the procedure in which it is declared</span></span>|  
|<span data-ttu-id="d4fc2-111">Modulbereich</span><span class="sxs-lookup"><span data-stu-id="d4fc2-111">Module scope</span></span>|<span data-ttu-id="d4fc2-112">Verfügbar für sämtlichen Code innerhalb der Module, Klasse oder Struktur, die in der sie deklariert ist</span><span class="sxs-lookup"><span data-stu-id="d4fc2-112">Available to all code within the module, class, or structure in which it is declared</span></span>|  
|<span data-ttu-id="d4fc2-113">Namespace-Bereich</span><span class="sxs-lookup"><span data-stu-id="d4fc2-113">Namespace scope</span></span>|<span data-ttu-id="d4fc2-114">Verfügbar für den gesamten Code in den Namespace, in dem sie deklariert ist</span><span class="sxs-lookup"><span data-stu-id="d4fc2-114">Available to all code in the namespace in which it is declared</span></span>|  
  
 <span data-ttu-id="d4fc2-115">Diese Ebenen des Status von engsten (Block) die größtmögliche (Namespace), Bereich, in denen *engsten Gültigkeitsbereich* bedeutet, dass die kleinste Menge der Code, der auf das Element ohne Qualifikation verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-115">These levels of scope progress from the narrowest (block) to the widest (namespace), where *narrowest scope* means the smallest set of code that can refer to the element without qualification.</span></span> <span data-ttu-id="d4fc2-116">Weitere Informationen finden Sie unter "Ebenen von Scope" auf dieser Seite.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-116">For more information, see "Levels of Scope" on this page.</span></span>  
  
## <a name="specifying-scope-and-defining-variables"></a><span data-ttu-id="d4fc2-117">Festlegen des Gültigkeitsbereichs und Definieren von Variablen</span><span class="sxs-lookup"><span data-stu-id="d4fc2-117">Specifying Scope and Defining Variables</span></span>  
 <span data-ttu-id="d4fc2-118">Wenn Sie sie deklarieren, geben Sie den Bereich eines Elements.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-118">You specify the scope of an element when you declare it.</span></span> <span data-ttu-id="d4fc2-119">Der Bereich kann auf folgenden Faktoren abhängen:</span><span class="sxs-lookup"><span data-stu-id="d4fc2-119">The scope can depend on the following factors:</span></span>  
  
-   <span data-ttu-id="d4fc2-120">Die Region (Block, Prozedur, Modul, Klasse oder Struktur), in der Sie das Element deklarieren.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-120">The region (block, procedure, module, class, or structure) in which you declare the element</span></span>  
  
-   <span data-ttu-id="d4fc2-121">Der Namespace, enthält die Deklaration des Elements</span><span class="sxs-lookup"><span data-stu-id="d4fc2-121">The namespace containing the element's declaration</span></span>  
  
-   <span data-ttu-id="d4fc2-122">Die Zugriffsebene, die Sie für das Element deklarieren.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-122">The access level you declare for the element</span></span>  
  
 <span data-ttu-id="d4fc2-123">Gehen Sie sorgfältig vor, wenn Sie Variablen mit dem gleichen Namen, aber anderen Bereich definieren, da dies kann zu unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-123">Use care when you define variables with the same name but different scope, because doing so can lead to unexpected results.</span></span> <span data-ttu-id="d4fc2-124">Weitere Informationen finden Sie unter [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="d4fc2-124">For more information, see [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="levels-of-scope"></a><span data-ttu-id="d4fc2-125">Bereichsebenen</span><span class="sxs-lookup"><span data-stu-id="d4fc2-125">Levels of Scope</span></span>  
 <span data-ttu-id="d4fc2-126">Ein Programmierelement ist verfügbar in der Region, in der Sie sie deklarieren.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-126">A programming element is available throughout the region in which you declare it.</span></span> <span data-ttu-id="d4fc2-127">Der gesamte Code in der gleichen Region kann auf das Element ohne Angabe ihres Namens verweisen.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-127">All code in the same region can refer to the element without qualifying its name.</span></span>  
  
### <a name="block-scope"></a><span data-ttu-id="d4fc2-128">Blockbereich</span><span class="sxs-lookup"><span data-stu-id="d4fc2-128">Block Scope</span></span>  
 <span data-ttu-id="d4fc2-129">Ein Block ist ein Satz von eingefasst wird initiiert, und Beenden von deklarationsanweisungen, wie z. B. die folgenden Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="d4fc2-129">A block is a set of statements enclosed within initiating and terminating declaration statements, such as the following:</span></span>  
  
-   <span data-ttu-id="d4fc2-130">`Do` und `Loop`</span><span class="sxs-lookup"><span data-stu-id="d4fc2-130">`Do` and `Loop`</span></span>  
  
-   <span data-ttu-id="d4fc2-131">`For` [`Each`] und `Next`</span><span class="sxs-lookup"><span data-stu-id="d4fc2-131">`For` [`Each`] and `Next`</span></span>  
  
-   <span data-ttu-id="d4fc2-132">`If` und `End If`</span><span class="sxs-lookup"><span data-stu-id="d4fc2-132">`If` and `End If`</span></span>  
  
-   <span data-ttu-id="d4fc2-133">`Select` und `End Select`</span><span class="sxs-lookup"><span data-stu-id="d4fc2-133">`Select` and `End Select`</span></span>  
  
-   <span data-ttu-id="d4fc2-134">`SyncLock` und `End SyncLock`</span><span class="sxs-lookup"><span data-stu-id="d4fc2-134">`SyncLock` and `End SyncLock`</span></span>  
  
-   <span data-ttu-id="d4fc2-135">`Try` und `End Try`</span><span class="sxs-lookup"><span data-stu-id="d4fc2-135">`Try` and `End Try`</span></span>  
  
-   <span data-ttu-id="d4fc2-136">`While` und `End While`</span><span class="sxs-lookup"><span data-stu-id="d4fc2-136">`While` and `End While`</span></span>  
  
-   <span data-ttu-id="d4fc2-137">`With` und `End With`</span><span class="sxs-lookup"><span data-stu-id="d4fc2-137">`With` and `End With`</span></span>  
  
 <span data-ttu-id="d4fc2-138">Wenn Sie eine Variable in einem Block deklarieren, können Sie es nur innerhalb dieses Blocks.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-138">If you declare a variable within a block, you can use it only within that block.</span></span> <span data-ttu-id="d4fc2-139">Im folgenden Beispiel ist der Bereich der ganzzahligen Variable `cube` der Block zwischen `If` und `End If`, und Sie können nicht mehr auf verweisen `cube` Wenn die Ausführung aus dem Block übergeben.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-139">In the following example, the scope of the integer variable `cube` is the block between `If` and `End If`, and you can no longer refer to `cube` when execution passes out of the block.</span></span>  
  
```  
If n < 1291 Then  
    Dim cube As Integer  
    cube = n ^ 3  
End If  
```  
  
> [!NOTE]
>  <span data-ttu-id="d4fc2-140">Auch wenn der Bereich einer Variablen auf einen Block beschränkt ist, ist seine Lebensdauer immer noch die gesamte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-140">Even if the scope of a variable is limited to a block, its lifetime is still that of the entire procedure.</span></span> <span data-ttu-id="d4fc2-141">Wenn Sie den Block während des Verfahrens mehrmals eingeben, behält jede Blockvariable seinen ursprünglichen Wert.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-141">If you enter the block more than once during the procedure, each block variable retains its previous value.</span></span> <span data-ttu-id="d4fc2-142">Um unerwartete Ergebnisse in einem solchen Fall zu vermeiden, ist es klug, Block Variablen am Anfang des Blocks zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-142">To avoid unexpected results in such a case, it is wise to initialize block variables at the beginning of the block.</span></span>  
  
### <a name="procedure-scope"></a><span data-ttu-id="d4fc2-143">Prozedurbereich</span><span class="sxs-lookup"><span data-stu-id="d4fc2-143">Procedure Scope</span></span>  
 <span data-ttu-id="d4fc2-144">Ein Element innerhalb einer Prozedur ist nicht verfügbar ist, außerhalb dieser Prozedur.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-144">An element declared within a procedure is not available outside that procedure.</span></span> <span data-ttu-id="d4fc2-145">Nur die Prozedur, die die Deklaration enthält, können sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-145">Only the procedure that contains the declaration can use it.</span></span> <span data-ttu-id="d4fc2-146">Variablen, die auf dieser Ebene werden auch bezeichnet als *lokale Variablen*.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-146">Variables at this level are also known as *local variables*.</span></span> <span data-ttu-id="d4fc2-147">Sie deklarieren sie mit der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)mit oder ohne die [statische](../../../../visual-basic/language-reference/modifiers/static.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-147">You declare them with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), with or without the [Static](../../../../visual-basic/language-reference/modifiers/static.md) keyword.</span></span>  
  
 <span data-ttu-id="d4fc2-148">Verfahren und der Blockbereich sind eng miteinander verknüpft.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-148">Procedure and block scope are closely related.</span></span> <span data-ttu-id="d4fc2-149">Wenn Sie eine Variable innerhalb einer Prozedur deklarieren, aber außerhalb aller Blöcke in diesem Verfahren werden soll, stellen Sie sich die Variable als Blockbereich, wobei der Block für die gesamte Prozedur ist.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-149">If you declare a variable inside a procedure but outside any block within that procedure, you can think of the variable as having block scope, where the block is the entire procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4fc2-150">Alle lokalen Elemente, auch wenn sie `Static` Variablen sind privat für die Prozedur, die in der sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-150">All local elements, even if they are `Static` variables, are private to the procedure in which they appear.</span></span> <span data-ttu-id="d4fc2-151">Kann nicht deklariert werden alle-Element mithilfe der [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md) Schlüsselwort in einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-151">You cannot declare any element using the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword within a procedure.</span></span>  
  
### <a name="module-scope"></a><span data-ttu-id="d4fc2-152">Modulbereich</span><span class="sxs-lookup"><span data-stu-id="d4fc2-152">Module Scope</span></span>  
 <span data-ttu-id="d4fc2-153">Der Einfachheit halber einen einzelnen Ausdruck *auf Modulebene* gilt gleichermaßen für Module, Klassen und Strukturen.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-153">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="d4fc2-154">Sie können Elemente auf dieser Ebene platzieren der deklarationsanweisung außerhalb von Prozeduren oder blockieren, aber in das Modul, Klasse oder Struktur deklarieren.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-154">You can declare elements at this level by placing the declaration statement outside of any procedure or block but within the module, class, or structure.</span></span>  
  
 <span data-ttu-id="d4fc2-155">Wenn Sie eine Deklaration auf Modulebene vornehmen, bestimmt die Zugriffsebene, die Sie auswählen, den Bereich an.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-155">When you make a declaration at the module level, the access level you choose determines the scope.</span></span> <span data-ttu-id="d4fc2-156">Der Namespace, der das Modul, Klasse oder Struktur enthält, wirkt sich auch auf den Bereich aus.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-156">The namespace that contains the module, class, or structure also affects the scope.</span></span>  
  
 <span data-ttu-id="d4fc2-157">Elemente, die für die Sie deklarieren [Private](../../../../visual-basic/language-reference/modifiers/private.md) Zugriffsebene zur Verfügung stehen, auf alle Prozeduren in diesem Modul, aber nicht auf Code in einem anderen Modul.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-157">Elements for which you declare [Private](../../../../visual-basic/language-reference/modifiers/private.md) access level are available to every procedure in that module, but not to any code in a different module.</span></span> <span data-ttu-id="d4fc2-158">Die `Dim` Anweisung auf Modulebene standardmäßig `Private` , wenn Sie keine Zugriffsebenen-Schlüsselwörter verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-158">The `Dim` statement at module level defaults to `Private` if you do not use any access level keywords.</span></span> <span data-ttu-id="d4fc2-159">Allerdings möglich den Bereich und die Zugriffsebene offensichtlicheren mithilfe der `Private` -Schlüsselwort in der `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-159">However, you can make the scope and access level more obvious by using the `Private` keyword in the `Dim` statement.</span></span>  
  
 <span data-ttu-id="d4fc2-160">Im folgenden Beispiel können alle im Modul definierte Prozeduren verweisen, der Zeichenfolgenvariablen `strMsg`.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-160">In the following example, all procedures defined in the module can refer to the string variable `strMsg`.</span></span> <span data-ttu-id="d4fc2-161">Wenn die zweite Prozedur aufgerufen wird, zeigt es den Inhalt der Zeichenfolgenvariablen `strMsg` in einem Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-161">When the second procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
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
  
### <a name="namespace-scope"></a><span data-ttu-id="d4fc2-162">Namespace-Bereich</span><span class="sxs-lookup"><span data-stu-id="d4fc2-162">Namespace Scope</span></span>  
 <span data-ttu-id="d4fc2-163">Wenn Sie ein Element an das Modul mit deklarieren die [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) oder [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüsselwort, es wird für alle Prozeduren während des gesamten Namespace in der das Element deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-163">If you declare an element at module level using the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword, it becomes available to all procedures throughout the namespace in which the element is declared.</span></span> <span data-ttu-id="d4fc2-164">Durch die folgende Änderung zum vorherigen Beispiel die Zeichenfolgenvariable `strMsg` kann vom Code an einer beliebigen Stelle in den Namespace der Deklaration verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-164">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```  
' Include this declaration at module level (not inside any procedure).  
Public strMsg As String  
```  
  
 <span data-ttu-id="d4fc2-165">Namespace-Gültigkeitsbereich enthält geschachtelte Namespaces.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-165">Namespace scope includes nested namespaces.</span></span> <span data-ttu-id="d4fc2-166">Ein Element in einem Namespace verfügbar ist auch in jedem Namespace, die in diesem Namespace geschachtelt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-166">An element available from within a namespace is also available from within any namespace nested inside that namespace.</span></span>  
  
 <span data-ttu-id="d4fc2-167">Wenn Ihr Projekt keine enthält [Namespace-Anweisung](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, alles im Projekt wird im selben Namespace.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-167">If your project does not contain any [Namespace Statement](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, everything in the project is in the same namespace.</span></span> <span data-ttu-id="d4fc2-168">In diesem Fall kann der Namespace-Gültigkeitsbereich als Projektumfang betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-168">In this case, namespace scope can be thought of as project scope.</span></span> <span data-ttu-id="d4fc2-169">`Public` Elemente in einem Modul, Klasse oder Struktur sind auch verfügbar, um Projekte, die ihr Projekt verweist.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-169">`Public` elements in a module, class, or structure are also available to any project that references their project.</span></span>  
  
## <a name="choice-of-scope"></a><span data-ttu-id="d4fc2-170">Auswahl des Bereichs</span><span class="sxs-lookup"><span data-stu-id="d4fc2-170">Choice of Scope</span></span>  
 <span data-ttu-id="d4fc2-171">Wenn Sie eine Variable deklarieren, sollten Sie die folgenden Punkte bedenken bei der Auswahl ihres Bereichs.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-171">When you declare a variable, you should keep in mind the following points when choosing its scope.</span></span>  
  
### <a name="advantages-of-local-variables"></a><span data-ttu-id="d4fc2-172">Vorteile von lokalen Variablen</span><span class="sxs-lookup"><span data-stu-id="d4fc2-172">Advantages of Local Variables</span></span>  
 <span data-ttu-id="d4fc2-173">Lokale Variablen sind eine gute Wahl für alle Arten von temporären Berechnungen aus, die aus den folgenden Gründen:</span><span class="sxs-lookup"><span data-stu-id="d4fc2-173">Local variables are a good choice for any kind of temporary calculation, for the following reasons:</span></span>  
  
-   <span data-ttu-id="d4fc2-174">**Namenskonflikt vermeiden.**</span><span class="sxs-lookup"><span data-stu-id="d4fc2-174">**Name Conflict Avoidance.**</span></span> <span data-ttu-id="d4fc2-175">Namen lokaler Variable sind nicht anfällig gegenüber in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-175">Local variable names are not susceptible to conflict.</span></span> <span data-ttu-id="d4fc2-176">Sie können z. B. mehrere unterschiedliche Verfahren, die eine Variable namens erstellen `intTemp`.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-176">For example, you can create several different procedures containing a variable called `intTemp`.</span></span> <span data-ttu-id="d4fc2-177">Solange alle `intTemp` wird deklariert als lokale Variable, jede Prozedur erkennt nur ihre eigene Version der `intTemp`.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-177">As long as each `intTemp` is declared as a local variable, each procedure recognizes only its own version of `intTemp`.</span></span> <span data-ttu-id="d4fc2-178">Jede Prozedur ändern, kann den Wert in der lokalen `intTemp` ohne `intTemp` Variablen in anderen Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-178">Any one procedure can alter the value in its local `intTemp` without affecting `intTemp` variables in other procedures.</span></span>  
  
-   <span data-ttu-id="d4fc2-179">**Die Arbeitsspeichernutzung.**</span><span class="sxs-lookup"><span data-stu-id="d4fc2-179">**Memory Consumption.**</span></span> <span data-ttu-id="d4fc2-180">Lokale Variablen belegt Arbeitsspeicher nur, solange die Prozedur ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-180">Local variables consume memory only while their procedure is running.</span></span> <span data-ttu-id="d4fc2-181">Ihren Arbeitsspeicher wird freigegeben, wenn die Prozedur an den aufrufenden Code zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-181">Their memory is released when the procedure returns to the calling code.</span></span> <span data-ttu-id="d4fc2-182">Im Gegensatz dazu [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) und [statische](../../../../visual-basic/language-reference/modifiers/static.md) Variablen Speicherressourcen beanspruchen, bis die Anwendung beendet wird, werden Sie also nur bei Bedarf verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-182">By contrast, [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) and [Static](../../../../visual-basic/language-reference/modifiers/static.md) variables consume memory resources until your application stops running, so use them only when necessary.</span></span> <span data-ttu-id="d4fc2-183">*Instanzvariablen* belegt Arbeitsspeicher während ihrer Instanz vorhanden weiterhin, was weniger effizient als lokale Variablen, aber möglicherweise effizienter als die `Shared` oder `Static` Variablen.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-183">*Instance variables* consume memory while their instance continues to exist, which makes them less efficient than local variables, but potentially more efficient than `Shared` or `Static` variables.</span></span>  
  
### <a name="minimizing-scope"></a><span data-ttu-id="d4fc2-184">Bereich minimiert</span><span class="sxs-lookup"><span data-stu-id="d4fc2-184">Minimizing Scope</span></span>  
 <span data-ttu-id="d4fc2-185">Wenn Sie eine Variable oder Konstante zu deklarieren, wird es im Allgemeinen guter Programmierstil, um den Bereich so eng wie möglich zu machen (Blockbereich ist die geringstmögliche).</span><span class="sxs-lookup"><span data-stu-id="d4fc2-185">In general, when declaring any variable or constant, it is good programming practice to make the scope as narrow as possible (block scope is the narrowest).</span></span> <span data-ttu-id="d4fc2-186">Dadurch wird Speicherplatz gespart und minimiert die Wahrscheinlichkeit, dass Ihr Code, der fälschlicherweise die falsche Variable auf.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-186">This helps conserve memory and minimizes the chances of your code erroneously referring to the wrong variable.</span></span> <span data-ttu-id="d4fc2-187">Ebenso sollten Sie eine Variable deklarieren [statische](../../../../visual-basic/language-reference/modifiers/static.md) nur wenn den Wert zwischen den Prozeduraufrufen beibehalten werden muss.</span><span class="sxs-lookup"><span data-stu-id="d4fc2-187">Similarly, you should declare a variable to be [Static](../../../../visual-basic/language-reference/modifiers/static.md) only when it is necessary to preserve its value between procedure calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4fc2-188">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4fc2-188">See also</span></span>

- [<span data-ttu-id="d4fc2-189">Merkmale deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="d4fc2-189">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="d4fc2-190">Vorgehensweise: Steuern des Gültigkeitsbereichs einer Variablen</span><span class="sxs-lookup"><span data-stu-id="d4fc2-190">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [<span data-ttu-id="d4fc2-191">Lebensdauer in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4fc2-191">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="d4fc2-192">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4fc2-192">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="d4fc2-193">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="d4fc2-193">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="d4fc2-194">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="d4fc2-194">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
