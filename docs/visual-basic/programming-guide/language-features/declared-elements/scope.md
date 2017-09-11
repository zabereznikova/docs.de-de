---
title: "Gültigkeitsbereich in Visual Basic | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- module scope
- scope, levels
- module level
- procedures, scope
- declared elements, scope
- namespaces, scope
- scope, declared elements
- scope, about scope
- levels of scope
- block scope
- scope, Visual Basic
- procedure scope
ms.assetid: 208106fe-79c9-4eec-93c6-55f08548895f
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9b938ed940dd0fd57707c39626f7b69dc0589af1
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="scope-in-visual-basic"></a><span data-ttu-id="75ec9-102">Gültigkeitsbereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="75ec9-102">Scope in Visual Basic</span></span>
<span data-ttu-id="75ec9-103">Die *Bereich* eines deklarierten Elements ist ein Satz von Code, die darauf verweisen kann, ohne seinen Namen qualifizieren oder durch Verfügbarmachen, einer [Imports-Anweisung (.NET Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="75ec9-103">The *scope* of a declared element is the set of all code that can refer to it without qualifying its name or making it available through an [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span> <span data-ttu-id="75ec9-104">Ein Element kann an einem der folgenden Ebenen Bereich aufweisen:</span><span class="sxs-lookup"><span data-stu-id="75ec9-104">An element can have scope at one of the following levels:</span></span>  
  
|<span data-ttu-id="75ec9-105">Ebene</span><span class="sxs-lookup"><span data-stu-id="75ec9-105">Level</span></span>|<span data-ttu-id="75ec9-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75ec9-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="75ec9-107">Blockbereich</span><span class="sxs-lookup"><span data-stu-id="75ec9-107">Block scope</span></span>|<span data-ttu-id="75ec9-108">Verfügbar nur innerhalb des Codes blockieren, in dem sie deklariert ist</span><span class="sxs-lookup"><span data-stu-id="75ec9-108">Available only within the code block in which it is declared</span></span>|  
|<span data-ttu-id="75ec9-109">Prozedurbereich</span><span class="sxs-lookup"><span data-stu-id="75ec9-109">Procedure scope</span></span>|<span data-ttu-id="75ec9-110">Für sämtlichen Code innerhalb der Prozedur, in der sie deklariert ist, verfügbar</span><span class="sxs-lookup"><span data-stu-id="75ec9-110">Available to all code within the procedure in which it is declared</span></span>|  
|<span data-ttu-id="75ec9-111">Modulbereich</span><span class="sxs-lookup"><span data-stu-id="75ec9-111">Module scope</span></span>|<span data-ttu-id="75ec9-112">Für den gesamten Code im Modul, Klasse oder Struktur, in der sie deklariert ist, verfügbar</span><span class="sxs-lookup"><span data-stu-id="75ec9-112">Available to all code within the module, class, or structure in which it is declared</span></span>|  
|<span data-ttu-id="75ec9-113">Namespace-Bereich</span><span class="sxs-lookup"><span data-stu-id="75ec9-113">Namespace scope</span></span>|<span data-ttu-id="75ec9-114">Für den gesamten Code im Namespace, in dem sie deklariert ist, verfügbar</span><span class="sxs-lookup"><span data-stu-id="75ec9-114">Available to all code in the namespace in which it is declared</span></span>|  
  
 <span data-ttu-id="75ec9-115">Diese Ebenen des Gültigkeitsbereichs steigern vom engsten (Block) auf den längsten (Namespace), wobei *engsten Gültigkeitsbereich* bedeutet, dass die kleinste Menge der Code, der ohne Qualifizierung auf dieses Element verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="75ec9-115">These levels of scope progress from the narrowest (block) to the widest (namespace), where *narrowest scope* means the smallest set of code that can refer to the element without qualification.</span></span> <span data-ttu-id="75ec9-116">Weitere Informationen finden Sie unter "Ebenen des Gültigkeitsbereichs" auf dieser Seite.</span><span class="sxs-lookup"><span data-stu-id="75ec9-116">For more information, see "Levels of Scope" on this page.</span></span>  
  
## <a name="specifying-scope-and-defining-variables"></a><span data-ttu-id="75ec9-117">Festlegen des Gültigkeitsbereichs und Definieren von Variablen</span><span class="sxs-lookup"><span data-stu-id="75ec9-117">Specifying Scope and Defining Variables</span></span>  
 <span data-ttu-id="75ec9-118">Sie geben den Umfang eines Elements, wenn Sie deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="75ec9-118">You specify the scope of an element when you declare it.</span></span> <span data-ttu-id="75ec9-119">Der Bereich kann von folgenden Faktoren abhängen:</span><span class="sxs-lookup"><span data-stu-id="75ec9-119">The scope can depend on the following factors:</span></span>  
  
-   <span data-ttu-id="75ec9-120">Die Region (Block, Prozedur, Modul, Klasse oder Struktur), in der Sie das Element deklarieren</span><span class="sxs-lookup"><span data-stu-id="75ec9-120">The region (block, procedure, module, class, or structure) in which you declare the element</span></span>  
  
-   <span data-ttu-id="75ec9-121">Der Namespace, die die Deklaration des Elements enthält.</span><span class="sxs-lookup"><span data-stu-id="75ec9-121">The namespace containing the element's declaration</span></span>  
  
-   <span data-ttu-id="75ec9-122">Die Zugriffsebene, die Sie für das Element deklarieren</span><span class="sxs-lookup"><span data-stu-id="75ec9-122">The access level you declare for the element</span></span>  
  
 <span data-ttu-id="75ec9-123">Gehen Sie sorgfältig vor, wenn Sie Variablen mit demselben Namen, aber andere Bereiche definieren, da dies kann zu unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="75ec9-123">Use care when you define variables with the same name but different scope, because doing so can lead to unexpected results.</span></span> <span data-ttu-id="75ec9-124">Weitere Informationen finden Sie unter [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="75ec9-124">For more information, see [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="levels-of-scope"></a><span data-ttu-id="75ec9-125">Ebenen des Gültigkeitsbereichs</span><span class="sxs-lookup"><span data-stu-id="75ec9-125">Levels of Scope</span></span>  
 <span data-ttu-id="75ec9-126">Ein Programmierelement steht innerhalb der Region, in der Sie deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="75ec9-126">A programming element is available throughout the region in which you declare it.</span></span> <span data-ttu-id="75ec9-127">Der gesamte Code in der gleichen Region kann auf das Element verweisen, ohne dessen Namen zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="75ec9-127">All code in the same region can refer to the element without qualifying its name.</span></span>  
  
### <a name="block-scope"></a><span data-ttu-id="75ec9-128">Blockbereich</span><span class="sxs-lookup"><span data-stu-id="75ec9-128">Block Scope</span></span>  
 <span data-ttu-id="75ec9-129">Ein Block ist eine Gruppe von Anweisungen, die innerhalb der starten und Beenden von deklarationsanweisungen, wie z. B. die folgenden:</span><span class="sxs-lookup"><span data-stu-id="75ec9-129">A block is a set of statements enclosed within initiating and terminating declaration statements, such as the following:</span></span>  
  
-   <span data-ttu-id="75ec9-130">`Do` und `Loop`</span><span class="sxs-lookup"><span data-stu-id="75ec9-130">`Do` and `Loop`</span></span>  
  
-   <span data-ttu-id="75ec9-131">`For`[`Each`] and`Next`</span><span class="sxs-lookup"><span data-stu-id="75ec9-131">`For` [`Each`] and `Next`</span></span>  
  
-   <span data-ttu-id="75ec9-132">`If` und `End If`</span><span class="sxs-lookup"><span data-stu-id="75ec9-132">`If` and `End If`</span></span>  
  
-   <span data-ttu-id="75ec9-133">`Select` und `End Select`</span><span class="sxs-lookup"><span data-stu-id="75ec9-133">`Select` and `End Select`</span></span>  
  
-   <span data-ttu-id="75ec9-134">`SyncLock` und `End SyncLock`</span><span class="sxs-lookup"><span data-stu-id="75ec9-134">`SyncLock` and `End SyncLock`</span></span>  
  
-   <span data-ttu-id="75ec9-135">`Try` und `End Try`</span><span class="sxs-lookup"><span data-stu-id="75ec9-135">`Try` and `End Try`</span></span>  
  
-   <span data-ttu-id="75ec9-136">`While` und `End While`</span><span class="sxs-lookup"><span data-stu-id="75ec9-136">`While` and `End While`</span></span>  
  
-   <span data-ttu-id="75ec9-137">`With` und `End With`</span><span class="sxs-lookup"><span data-stu-id="75ec9-137">`With` and `End With`</span></span>  
  
 <span data-ttu-id="75ec9-138">Wenn Sie eine Variable innerhalb eines Blocks zu deklarieren, können Sie es nur innerhalb dieses Blocks.</span><span class="sxs-lookup"><span data-stu-id="75ec9-138">If you declare a variable within a block, you can use it only within that block.</span></span> <span data-ttu-id="75ec9-139">Im folgenden Beispiel den Bereich der ganzzahligen Variable `cube` der Block zwischen `If` und `End If`, und Sie können nicht mehr verweisen `cube` bei Ausführung aus dem Block weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="75ec9-139">In the following example, the scope of the integer variable `cube` is the block between `If` and `End If`, and you can no longer refer to `cube` when execution passes out of the block.</span></span>  
  
```  
If n < 1291 Then  
    Dim cube As Integer  
    cube = n ^ 3  
End If  
```  
  
> [!NOTE]
>  <span data-ttu-id="75ec9-140">Auch wenn der Gültigkeitsbereich einer Variablen auf einen Block beschränkt ist, ist seine Lebensdauer immer noch die gesamte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="75ec9-140">Even if the scope of a variable is limited to a block, its lifetime is still that of the entire procedure.</span></span> <span data-ttu-id="75ec9-141">Wenn Sie den Block mehrmals während des Verfahrens eingeben, behält jede Blockvariable den vorhergehenden Wert.</span><span class="sxs-lookup"><span data-stu-id="75ec9-141">If you enter the block more than once during the procedure, each block variable retains its previous value.</span></span> <span data-ttu-id="75ec9-142">Um unerwartete Ergebnisse in einem solchen Fall zu vermeiden, ist es ratsam, Block Variablen am Anfang des Blocks zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="75ec9-142">To avoid unexpected results in such a case, it is wise to initialize block variables at the beginning of the block.</span></span>  
  
### <a name="procedure-scope"></a><span data-ttu-id="75ec9-143">Prozedurbereich</span><span class="sxs-lookup"><span data-stu-id="75ec9-143">Procedure Scope</span></span>  
 <span data-ttu-id="75ec9-144">Ein Element innerhalb einer Prozedur ist nicht außerhalb dieser Prozedur verfügbar.</span><span class="sxs-lookup"><span data-stu-id="75ec9-144">An element declared within a procedure is not available outside that procedure.</span></span> <span data-ttu-id="75ec9-145">Nur die Prozedur, die die Deklaration enthält können.</span><span class="sxs-lookup"><span data-stu-id="75ec9-145">Only the procedure that contains the declaration can use it.</span></span> <span data-ttu-id="75ec9-146">Elemente auf dieser Ebene werden auch bekannt als *lokale Variablen*.</span><span class="sxs-lookup"><span data-stu-id="75ec9-146">Variables at this level are also known as *local variables*.</span></span> <span data-ttu-id="75ec9-147">Sie deklarieren sie mit der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)mit oder ohne den [statische](../../../../visual-basic/language-reference/modifiers/static.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="75ec9-147">You declare them with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), with or without the [Static](../../../../visual-basic/language-reference/modifiers/static.md) keyword.</span></span>  
  
 <span data-ttu-id="75ec9-148">Verfahren und der Blockbereich sind eng miteinander verknüpft.</span><span class="sxs-lookup"><span data-stu-id="75ec9-148">Procedure and block scope are closely related.</span></span> <span data-ttu-id="75ec9-149">Wenn Sie eine Variable innerhalb einer Prozedur, aber außerhalb aller Blöcke in dieser Prozedur deklarieren, können Sie sich vorstellen der Variablen Blockbereich, wobei der Block die gesamte Prozedur ist.</span><span class="sxs-lookup"><span data-stu-id="75ec9-149">If you declare a variable inside a procedure but outside any block within that procedure, you can think of the variable as having block scope, where the block is the entire procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75ec9-150">Alle lokalen Elemente, auch wenn sie sind `Static` Variablen, für die Prozedur, in der sie erscheinen, privat sind.</span><span class="sxs-lookup"><span data-stu-id="75ec9-150">All local elements, even if they are `Static` variables, are private to the procedure in which they appear.</span></span> <span data-ttu-id="75ec9-151">Kann nicht deklariert werden jedem Element mithilfe der [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md) Schlüsselwort innerhalb einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="75ec9-151">You cannot declare any element using the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword within a procedure.</span></span>  
  
### <a name="module-scope"></a><span data-ttu-id="75ec9-152">Modulbereich</span><span class="sxs-lookup"><span data-stu-id="75ec9-152">Module Scope</span></span>  
 <span data-ttu-id="75ec9-153">Der Einfachheit halber der Begriff *Modulebene* gilt gleichermaßen für Module, Klassen und Strukturen.</span><span class="sxs-lookup"><span data-stu-id="75ec9-153">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="75ec9-154">Sie können Elemente auf dieser Ebene die Deklaration-Anweisung außerhalb jeder Prozedur oder eines Blocks jedoch in Modul, Klasse oder Struktur deklarieren.</span><span class="sxs-lookup"><span data-stu-id="75ec9-154">You can declare elements at this level by placing the declaration statement outside of any procedure or block but within the module, class, or structure.</span></span>  
  
 <span data-ttu-id="75ec9-155">Wenn Sie eine Deklaration auf Modulebene vornehmen, bestimmt die Zugriffsebene, die Sie wählen den Bereich.</span><span class="sxs-lookup"><span data-stu-id="75ec9-155">When you make a declaration at the module level, the access level you choose determines the scope.</span></span> <span data-ttu-id="75ec9-156">Der Namespace, der das Modul, Klasse oder Struktur enthält, wirkt sich auch auf den Bereich aus.</span><span class="sxs-lookup"><span data-stu-id="75ec9-156">The namespace that contains the module, class, or structure also affects the scope.</span></span>  
  
 <span data-ttu-id="75ec9-157">Elemente, für die Sie deklarieren [Private](../../../../visual-basic/language-reference/modifiers/private.md) Zugriffsebene auf alle Prozeduren in diesem Modul, jedoch nicht für den gesamten Code in einem anderen Modul verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="75ec9-157">Elements for which you declare [Private](../../../../visual-basic/language-reference/modifiers/private.md) access level are available to every procedure in that module, but not to any code in a different module.</span></span> <span data-ttu-id="75ec9-158">Die `Dim` -Anweisung auf Modulebene Standardwert `Private` , wenn Sie keine Zugriffsebenen-Schlüsselwörter verwenden.</span><span class="sxs-lookup"><span data-stu-id="75ec9-158">The `Dim` statement at module level defaults to `Private` if you do not use any access level keywords.</span></span> <span data-ttu-id="75ec9-159">Allerdings Sie können den Gültigkeitsbereich und Zugriffsebene deutlicher über stellen die `Private` -Schlüsselwort in der `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="75ec9-159">However, you can make the scope and access level more obvious by using the `Private` keyword in the `Dim` statement.</span></span>  
  
 <span data-ttu-id="75ec9-160">Im folgenden Beispiel können alle im Modul definierte Prozeduren finden Sie in der Zeichenfolgenvariablen `strMsg`.</span><span class="sxs-lookup"><span data-stu-id="75ec9-160">In the following example, all procedures defined in the module can refer to the string variable `strMsg`.</span></span> <span data-ttu-id="75ec9-161">Wenn die zweite Prozedur aufgerufen wird, wird es zeigt den Inhalt der Zeichenfolgenvariablen `strMsg` in einem Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="75ec9-161">When the second procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
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
  
### <a name="namespace-scope"></a><span data-ttu-id="75ec9-162">Namespace-Bereich</span><span class="sxs-lookup"><span data-stu-id="75ec9-162">Namespace Scope</span></span>  
 <span data-ttu-id="75ec9-163">Wenn Sie ein Element an das Modul mit deklarieren die [Freund](../../../../visual-basic/language-reference/modifiers/friend.md) oder [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüsselwort, steht es allen Prozeduren des gesamten Namespace, in dem das Element deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="75ec9-163">If you declare an element at module level using the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword, it becomes available to all procedures throughout the namespace in which the element is declared.</span></span> <span data-ttu-id="75ec9-164">Durch die folgende Änderung zum vorherigen Beispiel, die Zeichenfolgenvariable `strMsg` können durch Code an einer beliebigen Stelle im Namespace der Deklaration bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="75ec9-164">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```  
' Include this declaration at module level (not inside any procedure).  
Public strMsg As String  
```  
  
 <span data-ttu-id="75ec9-165">Namespace-Bereich enthält geschachtelte Namespaces.</span><span class="sxs-lookup"><span data-stu-id="75ec9-165">Namespace scope includes nested namespaces.</span></span> <span data-ttu-id="75ec9-166">Ein Element innerhalb eines Namespace verfügbar ist auch in jedem innerhalb dieses Namespace geschachtelten Namespace verfügbar.</span><span class="sxs-lookup"><span data-stu-id="75ec9-166">An element available from within a namespace is also available from within any namespace nested inside that namespace.</span></span>  
  
 <span data-ttu-id="75ec9-167">Wenn das Projekt keine enthält [Namespace-Anweisung](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, alles im Projekt ist im selben Namespace.</span><span class="sxs-lookup"><span data-stu-id="75ec9-167">If your project does not contain any [Namespace Statement](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, everything in the project is in the same namespace.</span></span> <span data-ttu-id="75ec9-168">In diesem Fall kann der Namespacebereich als Projektumfang betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="75ec9-168">In this case, namespace scope can be thought of as project scope.</span></span> <span data-ttu-id="75ec9-169">`Public`Elemente in einem Modul, Klasse oder Struktur stehen auch jedem Projekt, das auf ihr Projekt verweist.</span><span class="sxs-lookup"><span data-stu-id="75ec9-169">`Public` elements in a module, class, or structure are also available to any project that references their project.</span></span>  
  
## <a name="choice-of-scope"></a><span data-ttu-id="75ec9-170">Auswahl des Gültigkeitsbereichs</span><span class="sxs-lookup"><span data-stu-id="75ec9-170">Choice of Scope</span></span>  
 <span data-ttu-id="75ec9-171">Wenn Sie eine Variable deklarieren, sollten Sie die folgenden Punkte bedenken bei der Auswahl des Gültigkeitsbereichs.</span><span class="sxs-lookup"><span data-stu-id="75ec9-171">When you declare a variable, you should keep in mind the following points when choosing its scope.</span></span>  
  
### <a name="advantages-of-local-variables"></a><span data-ttu-id="75ec9-172">Vorteile von lokalen Variablen</span><span class="sxs-lookup"><span data-stu-id="75ec9-172">Advantages of Local Variables</span></span>  
 <span data-ttu-id="75ec9-173">Lokale Variablen sind eine gute Wahl für alle Arten von temporären Berechnung aus den folgenden Gründen:</span><span class="sxs-lookup"><span data-stu-id="75ec9-173">Local variables are a good choice for any kind of temporary calculation, for the following reasons:</span></span>  
  
-   <span data-ttu-id="75ec9-174">**Vermeidung von Namenskonflikten.**</span><span class="sxs-lookup"><span data-stu-id="75ec9-174">**Name Conflict Avoidance.**</span></span> <span data-ttu-id="75ec9-175">Namen lokaler Variable sind nicht anfällig für in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="75ec9-175">Local variable names are not susceptible to conflict.</span></span> <span data-ttu-id="75ec9-176">Sie können z. B. mehrere verschiedene Prozeduren, die eine Variable namens erstellen `intTemp`.</span><span class="sxs-lookup"><span data-stu-id="75ec9-176">For example, you can create several different procedures containing a variable called `intTemp`.</span></span> <span data-ttu-id="75ec9-177">Solange jeder `intTemp` wird als deklariert eine lokale Variable, erkennen die einzelnen Prozeduren nur ihre eigene Version der `intTemp`.</span><span class="sxs-lookup"><span data-stu-id="75ec9-177">As long as each `intTemp` is declared as a local variable, each procedure recognizes only its own version of `intTemp`.</span></span> <span data-ttu-id="75ec9-178">Jede Prozedur ändern, kann den Wert in der lokalen `intTemp` ohne `intTemp` -Variablen in anderen Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="75ec9-178">Any one procedure can alter the value in its local `intTemp` without affecting `intTemp` variables in other procedures.</span></span>  
  
-   <span data-ttu-id="75ec9-179">**Speicherverbrauch.**</span><span class="sxs-lookup"><span data-stu-id="75ec9-179">**Memory Consumption.**</span></span> <span data-ttu-id="75ec9-180">Lokale Variablen belegen Arbeitsspeicher nur, wenn ihre Prozedur aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="75ec9-180">Local variables consume memory only while their procedure is running.</span></span> <span data-ttu-id="75ec9-181">Ihre Speicher wird freigegeben, wenn die Prozedur an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="75ec9-181">Their memory is released when the procedure returns to the calling code.</span></span> <span data-ttu-id="75ec9-182">Im Gegensatz dazu [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) und [statische](../../../../visual-basic/language-reference/modifiers/static.md) Variablen Speicherressourcen beanspruchen, bis die Anwendung beendet wird, werden daher nur bei Bedarf verwendet.</span><span class="sxs-lookup"><span data-stu-id="75ec9-182">By contrast, [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) and [Static](../../../../visual-basic/language-reference/modifiers/static.md) variables consume memory resources until your application stops running, so use them only when necessary.</span></span> <span data-ttu-id="75ec9-183">*Instanzvariablen* verbrauchen Speicher während ihrer Instanz vorhanden weiterhin, sodass sie weniger effizient als lokale Variablen, aber möglicherweise effizienter als `Shared` oder `Static` Variablen.</span><span class="sxs-lookup"><span data-stu-id="75ec9-183">*Instance variables* consume memory while their instance continues to exist, which makes them less efficient than local variables, but potentially more efficient than `Shared` or `Static` variables.</span></span>  
  
### <a name="minimizing-scope"></a><span data-ttu-id="75ec9-184">Minimieren des Gültigkeitsbereichs</span><span class="sxs-lookup"><span data-stu-id="75ec9-184">Minimizing Scope</span></span>  
 <span data-ttu-id="75ec9-185">Wenn Sie eine Variable oder Konstante deklarieren, ist es im Allgemeinen guter Programmierstil, den Bereich so eng wie möglich machen (Blockbereich ist der engste).</span><span class="sxs-lookup"><span data-stu-id="75ec9-185">In general, when declaring any variable or constant, it is good programming practice to make the scope as narrow as possible (block scope is the narrowest).</span></span> <span data-ttu-id="75ec9-186">Dadurch wird Speicherplatz gespart und minimiert die Wahrscheinlichkeit des Codes fälschlicherweise auf die falsche Variable verweisen.</span><span class="sxs-lookup"><span data-stu-id="75ec9-186">This helps conserve memory and minimizes the chances of your code erroneously referring to the wrong variable.</span></span> <span data-ttu-id="75ec9-187">Ebenso sollten Sie eine Variable deklarieren [statische](../../../../visual-basic/language-reference/modifiers/static.md) nur wenn es ihr Wert über mehrere Prozeduraufrufe hinweg erhalten bleiben muss.</span><span class="sxs-lookup"><span data-stu-id="75ec9-187">Similarly, you should declare a variable to be [Static](../../../../visual-basic/language-reference/modifiers/static.md) only when it is necessary to preserve its value between procedure calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75ec9-188">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75ec9-188">See Also</span></span>  
 <span data-ttu-id="75ec9-189">[Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="75ec9-189">[Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span></span>  
<span data-ttu-id="75ec9-190"> [Gewusst wie: Steuern des Gültigkeitsbereichs einer Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md) </span><span class="sxs-lookup"><span data-stu-id="75ec9-190"> [How to: Control the Scope of a Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md) </span></span>  
<span data-ttu-id="75ec9-191"> [Lebensdauer in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md) </span><span class="sxs-lookup"><span data-stu-id="75ec9-191"> [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md) </span></span>  
<span data-ttu-id="75ec9-192"> [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="75ec9-192"> [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md) </span></span>  
<span data-ttu-id="75ec9-193"> [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span><span class="sxs-lookup"><span data-stu-id="75ec9-193"> [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span></span>  
<span data-ttu-id="75ec9-194"> [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)</span><span class="sxs-lookup"><span data-stu-id="75ec9-194"> [Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)</span></span>
