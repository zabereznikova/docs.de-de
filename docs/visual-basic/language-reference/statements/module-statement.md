---
title: Module-Anweisung
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 92cdcd1919f21243118108da3bc382ea5d954130
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="module-statement"></a><span data-ttu-id="2e2a8-102">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2e2a8-102">Module Statement</span></span>
<span data-ttu-id="2e2a8-103">Deklariert den Namen eines Moduls, und führt die Definitionen der Variablen, Eigenschaften, Ereignisse und Prozeduren, die das Modul besteht aus.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e2a8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e2a8-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a><span data-ttu-id="2e2a8-105">Teile</span><span class="sxs-lookup"><span data-stu-id="2e2a8-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="2e2a8-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-106">Optional.</span></span> <span data-ttu-id="2e2a8-107">Finden Sie unter [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="2e2a8-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="2e2a8-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-108">Optional.</span></span> <span data-ttu-id="2e2a8-109">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="2e2a8-109">Can be one of the following:</span></span>  
  
-   [<span data-ttu-id="2e2a8-110">Public</span><span class="sxs-lookup"><span data-stu-id="2e2a8-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [<span data-ttu-id="2e2a8-111">Friend</span><span class="sxs-lookup"><span data-stu-id="2e2a8-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 <span data-ttu-id="2e2a8-112">Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2e2a8-112">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `name`  
 <span data-ttu-id="2e2a8-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-113">Required.</span></span> <span data-ttu-id="2e2a8-114">Der Name dieses Moduls.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-114">Name of this module.</span></span> <span data-ttu-id="2e2a8-115">Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="2e2a8-115">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `statements`  
 <span data-ttu-id="2e2a8-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-116">Optional.</span></span> <span data-ttu-id="2e2a8-117">Anweisungen, die der Variablen, Eigenschaften, Ereignisse, Prozeduren und geschachtelte Typen dieses Moduls definieren.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>  
  
 `End Module`  
 <span data-ttu-id="2e2a8-118">Beendet die `Module`-Definition.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-118">Terminates the `Module` definition.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e2a8-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2e2a8-119">Remarks</span></span>  
 <span data-ttu-id="2e2a8-120">Ein `Module` -Anweisung definiert einen Referenztyp darstellt, die im gesamten Namespace verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="2e2a8-121">Ein *Modul* (bezeichnet einen *Standardmodul*) ähnelt einer Klasse, doch einige wichtige Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-121">A *module* (sometimes called a *standard module*)is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="2e2a8-122">Jedes Modul verfügt über genau eine Instanz und muss nicht erstellt oder einer Variablen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="2e2a8-123">Module nicht Vererbung unterstützen, und Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="2e2a8-124">Beachten Sie, dass ein Modul kein *Typ* in dem Sinne, dass eine Klasse oder Struktur ist – ein Programmierelement haben Sie den Datentyp eines Moduls kann nicht deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>  
  
 <span data-ttu-id="2e2a8-125">Sie können `Module` nur auf Namespaceebene.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="2e2a8-126">Dies bedeutet, dass die *Deklarationskontext* für ein Modul eine Quelldatei oder Namespace sein muss und nicht mit einer Klasse, Struktur, Modul, Schnittstelle, Prozedur oder Block.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="2e2a8-127">Ein Modul in ein anderes Modul oder in einen beliebigen Typ können nicht geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="2e2a8-128">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2e2a8-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="2e2a8-129">Ein Modul hat die gleiche Lebensdauer wie das Programm.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="2e2a8-130">Da die Member aller werden `Shared`, sie verfügen auch über eine Lebensdauer, die gleich des Programms.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>  
  
 <span data-ttu-id="2e2a8-131">Module standardmäßig ["Friend"](../../../visual-basic/language-reference/modifiers/friend.md) Zugriff.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-131">Modules default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access.</span></span> <span data-ttu-id="2e2a8-132">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="2e2a8-133">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2e2a8-133">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="2e2a8-134">Alle Member eines Moduls sind implizit `Shared`.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-134">All members of a module are implicitly `Shared`.</span></span>  
  
## <a name="classes-and-modules"></a><span data-ttu-id="2e2a8-135">Klassen und Module</span><span class="sxs-lookup"><span data-stu-id="2e2a8-135">Classes and Modules</span></span>  
 <span data-ttu-id="2e2a8-136">Diese Elemente haben viele ähnlichkeiten, aber es gibt auch einige wichtige Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-136">These elements have many similarities, but there are some important differences as well.</span></span>  
  
-   <span data-ttu-id="2e2a8-137">**Terminologie.**</span><span class="sxs-lookup"><span data-stu-id="2e2a8-137">**Terminology.**</span></span> <span data-ttu-id="2e2a8-138">Frühere Versionen von Visual Basic werden zwei Typen von Modulen erkannt: *Klassenmodule* (CLS-Dateien) und *Standardmodulen* (BAS-Dateien).</span><span class="sxs-lookup"><span data-stu-id="2e2a8-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="2e2a8-139">Die aktuelle Version ruft diese *Klassen* und *Module*zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-139">The current version calls these *classes* and *modules*, respectively.</span></span>  
  
-   <span data-ttu-id="2e2a8-140">**Freigegebene Member.**</span><span class="sxs-lookup"><span data-stu-id="2e2a8-140">**Shared Members.**</span></span> <span data-ttu-id="2e2a8-141">Sie können steuern, ob ein Member einer Klasse eine freigegebene oder Instanzmember.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-141">You can control whether a member of a class is a shared or instance member.</span></span>  
  
-   <span data-ttu-id="2e2a8-142">**Objektorientierung.**</span><span class="sxs-lookup"><span data-stu-id="2e2a8-142">**Object Orientation.**</span></span> <span data-ttu-id="2e2a8-143">Klassen können mit dem objektorientierten Module sind allerdings nicht.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="2e2a8-144">Damit nur Klassen als Objekte instanziiert werden können.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="2e2a8-145">Weitere Informationen finden Sie unter [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="2e2a8-145">For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="2e2a8-146">Regeln</span><span class="sxs-lookup"><span data-stu-id="2e2a8-146">Rules</span></span>  
  
-   <span data-ttu-id="2e2a8-147">**Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="2e2a8-147">**Modifiers.**</span></span> <span data-ttu-id="2e2a8-148">Alle Modulmember sind implizit [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="2e2a8-148">All module members are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="2e2a8-149">Sie können keine der `Shared` -Schlüsselwort, wenn ein Element, und Sie deklarieren den freigegebenen Status aller Mitglieder nicht ändern können.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>  
  
-   <span data-ttu-id="2e2a8-150">**Vererbung.**</span><span class="sxs-lookup"><span data-stu-id="2e2a8-150">**Inheritance.**</span></span> <span data-ttu-id="2e2a8-151">Ein Modul kann nicht von einem Typ erben, außer <xref:System.Object>, von dem alle Module erben.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="2e2a8-152">Insbesondere kann nicht einem Modul voneinander erben.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-152">In particular, one module cannot inherit from another.</span></span>  
  
     <span data-ttu-id="2e2a8-153">Können Sie keine der [Anweisung erbt](../../../visual-basic/language-reference/statements/inherits-statement.md) auch nicht zum angeben, in der Moduldefinition eines <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-153">You cannot use the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>  
  
-   <span data-ttu-id="2e2a8-154">**Standardeigenschaft.**</span><span class="sxs-lookup"><span data-stu-id="2e2a8-154">**Default Property.**</span></span> <span data-ttu-id="2e2a8-155">Sie können keine standardmäßigen Eigenschaften in einem Modul definieren.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="2e2a8-156">Weitere Informationen finden Sie unter [Standard](../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="2e2a8-156">For more information, see [Default](../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="2e2a8-157">Verhalten</span><span class="sxs-lookup"><span data-stu-id="2e2a8-157">Behavior</span></span>  
  
-   <span data-ttu-id="2e2a8-158">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="2e2a8-158">**Access Level.**</span></span> <span data-ttu-id="2e2a8-159">Innerhalb eines Moduls können Sie jeden Member mit einer eigenen Zugriffsebene deklarieren.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="2e2a8-160">Standardzugriff für Module [öffentlichen](../../../visual-basic/language-reference/modifiers/public.md) zuzugreifen, mit Ausnahme von Variablen und Konstanten, die standardmäßig die [Private](../../../visual-basic/language-reference/modifiers/private.md) Zugriff.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-160">Module members default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access, except variables and constants, which default to [Private](../../../visual-basic/language-reference/modifiers/private.md) access.</span></span> <span data-ttu-id="2e2a8-161">Wenn ein Modul den Zugriff eines seiner Elemente ist stärker als eingeschränkt, hat das angegebene Modul Zugriffsebene Vorrang vor.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>  
  
-   <span data-ttu-id="2e2a8-162">**Bereich.**</span><span class="sxs-lookup"><span data-stu-id="2e2a8-162">**Scope.**</span></span> <span data-ttu-id="2e2a8-163">Ein Modul ist der Gültigkeitsbereich des Namespace.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-163">A module is in scope throughout its namespace.</span></span>  
  
     <span data-ttu-id="2e2a8-164">Der Bereich jedes Elements Modul ist das gesamte Modul.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="2e2a8-165">Beachten Sie, die alle Elemente werden *heraufstufung geben*, wodurch ihres Bereichs auf den Namespace, mit dem Modul höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="2e2a8-166">Weitere Informationen finden Sie unter [Typerweiterung](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="2e2a8-166">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
-   <span data-ttu-id="2e2a8-167">**Qualifizierung.**</span><span class="sxs-lookup"><span data-stu-id="2e2a8-167">**Qualification.**</span></span> <span data-ttu-id="2e2a8-168">Sie können mehrere Module in einem Projekt haben, und Sie können Member mit demselben Namen in zwei oder mehrere Module deklarieren.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="2e2a8-169">Allerdings müssen Sie alle Verweise auf ein Element mit dem entsprechenden Modulnamen qualifizieren, wenn der Verweis, der außerhalb des Moduls stammt.</span><span class="sxs-lookup"><span data-stu-id="2e2a8-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="2e2a8-170">Weitere Informationen finden Sie unter [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="2e2a8-170">For more information, see [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e2a8-171">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2e2a8-171">Example</span></span>  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2e2a8-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e2a8-172">See Also</span></span>  
 [<span data-ttu-id="2e2a8-173">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2e2a8-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="2e2a8-174">Namespace-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2e2a8-174">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="2e2a8-175">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2e2a8-175">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="2e2a8-176">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2e2a8-176">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="2e2a8-177">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2e2a8-177">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="2e2a8-178">Typerweiterung</span><span class="sxs-lookup"><span data-stu-id="2e2a8-178">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
