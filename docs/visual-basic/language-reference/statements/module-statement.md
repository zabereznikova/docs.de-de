---
title: Module-Anweisung (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: f546498e5282bcf58d07a06968bb4303e4e6d7b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838143"
---
# <a name="module-statement"></a><span data-ttu-id="3924c-102">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3924c-102">Module Statement</span></span>
<span data-ttu-id="3924c-103">Deklariert den Namen eines Moduls, und führt die Definitionen der Variablen, Eigenschaften, Ereignisse und Prozeduren ein, denen das Modul enthält.</span><span class="sxs-lookup"><span data-stu-id="3924c-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3924c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3924c-104">Syntax</span></span>  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a><span data-ttu-id="3924c-105">Teile</span><span class="sxs-lookup"><span data-stu-id="3924c-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="3924c-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3924c-106">Optional.</span></span> <span data-ttu-id="3924c-107">Finden Sie unter [Liste](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="3924c-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="3924c-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3924c-108">Optional.</span></span> <span data-ttu-id="3924c-109">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="3924c-109">Can be one of the following:</span></span>  
  
-   [<span data-ttu-id="3924c-110">Public</span><span class="sxs-lookup"><span data-stu-id="3924c-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [<span data-ttu-id="3924c-111">Friend</span><span class="sxs-lookup"><span data-stu-id="3924c-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 <span data-ttu-id="3924c-112">Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3924c-112">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `name`  
 <span data-ttu-id="3924c-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3924c-113">Required.</span></span> <span data-ttu-id="3924c-114">Der Name dieses Moduls.</span><span class="sxs-lookup"><span data-stu-id="3924c-114">Name of this module.</span></span> <span data-ttu-id="3924c-115">Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="3924c-115">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `statements`  
 <span data-ttu-id="3924c-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3924c-116">Optional.</span></span> <span data-ttu-id="3924c-117">Anweisungen, die definieren, die Variablen, Eigenschaften, Ereignisse, Verfahren und geschachtelte Typen dieses Moduls.</span><span class="sxs-lookup"><span data-stu-id="3924c-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>  
  
 `End Module`  
 <span data-ttu-id="3924c-118">Beendet die `Module`-Definition.</span><span class="sxs-lookup"><span data-stu-id="3924c-118">Terminates the `Module` definition.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3924c-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3924c-119">Remarks</span></span>  
 <span data-ttu-id="3924c-120">Ein `Module` -Anweisung definiert einen Verweistyp handelt, die im gesamten Namespace verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3924c-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="3924c-121">Ein *Modul* (bezeichnet ein *Standardmodul*) wird der ähnlich wie eine Klasse jedoch einige wichtige Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="3924c-121">A *module* (sometimes called a *standard module*)is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="3924c-122">Jedes Modul verfügt über genau eine Instanz, und es muss nicht erstellt oder einer Variablen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="3924c-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="3924c-123">Module nicht unterstützen die Vererbung und Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="3924c-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="3924c-124">Beachten Sie, dass ein Modul kein *Typ* in dem Sinne, dass eine Klasse oder Struktur ist – ein Programmierelement, damit Sie den Datentyp eines Moduls kann nicht deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="3924c-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>  
  
 <span data-ttu-id="3924c-125">Sie können `Module` nur auf Namespaceebene.</span><span class="sxs-lookup"><span data-stu-id="3924c-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="3924c-126">Dies bedeutet, dass die *Deklarationskontext* für ein Modul, eine Quelldatei oder der Namespace sein muss, und nicht, eine Klasse, Struktur, Modul, Schnittstelle, Prozedur oder Block möglich.</span><span class="sxs-lookup"><span data-stu-id="3924c-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="3924c-127">Sie können ein Modul in einem anderen Modul oder in einen beliebigen Typ nicht schachteln.</span><span class="sxs-lookup"><span data-stu-id="3924c-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="3924c-128">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3924c-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="3924c-129">Ein Modul hat die gleiche Lebensdauer wie Ihr Programm.</span><span class="sxs-lookup"><span data-stu-id="3924c-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="3924c-130">Da die Member aller werden `Shared`, sie verfügen auch über eine Lebensdauer, die gleich dem des Programms.</span><span class="sxs-lookup"><span data-stu-id="3924c-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>  
  
 <span data-ttu-id="3924c-131">Module standardmäßig [Friend](../../../visual-basic/language-reference/modifiers/friend.md) Zugriff.</span><span class="sxs-lookup"><span data-stu-id="3924c-131">Modules default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access.</span></span> <span data-ttu-id="3924c-132">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="3924c-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="3924c-133">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3924c-133">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="3924c-134">Alle Elemente eines Moduls handelt es sich implizit `Shared`.</span><span class="sxs-lookup"><span data-stu-id="3924c-134">All members of a module are implicitly `Shared`.</span></span>  
  
## <a name="classes-and-modules"></a><span data-ttu-id="3924c-135">Klassen und Modulen</span><span class="sxs-lookup"><span data-stu-id="3924c-135">Classes and Modules</span></span>  
 <span data-ttu-id="3924c-136">Diese Elemente verfügen über viele ähnlichkeiten, aber es gibt auch einige wichtige Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="3924c-136">These elements have many similarities, but there are some important differences as well.</span></span>  
  
-   <span data-ttu-id="3924c-137">**-Terminologie verwenden.**</span><span class="sxs-lookup"><span data-stu-id="3924c-137">**Terminology.**</span></span> <span data-ttu-id="3924c-138">Zwei Arten von Modulen zur Erkennung von früheren Versionen von Visual Basic: *Klassenmodule* (CLS-Dateien) und *Standardmodulen* (BAS-Dateien).</span><span class="sxs-lookup"><span data-stu-id="3924c-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="3924c-139">Der aktuellen Version werden diese *Klassen* und *Module*bzw.</span><span class="sxs-lookup"><span data-stu-id="3924c-139">The current version calls these *classes* and *modules*, respectively.</span></span>  
  
-   <span data-ttu-id="3924c-140">**Freigegebene Member.**</span><span class="sxs-lookup"><span data-stu-id="3924c-140">**Shared Members.**</span></span> <span data-ttu-id="3924c-141">Sie können steuern, ob ein Member einer Klasse eines freigegebenen oder Instanzmember.</span><span class="sxs-lookup"><span data-stu-id="3924c-141">You can control whether a member of a class is a shared or instance member.</span></span>  
  
-   <span data-ttu-id="3924c-142">**Objektorientierung.**</span><span class="sxs-lookup"><span data-stu-id="3924c-142">**Object Orientation.**</span></span> <span data-ttu-id="3924c-143">Klassen sind objektorientiert, Module jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="3924c-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="3924c-144">Damit nur Klassen als Objekte instanziiert werden können.</span><span class="sxs-lookup"><span data-stu-id="3924c-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="3924c-145">Weitere Informationen finden Sie unter [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="3924c-145">For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="3924c-146">Regeln</span><span class="sxs-lookup"><span data-stu-id="3924c-146">Rules</span></span>  
  
-   <span data-ttu-id="3924c-147">**Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="3924c-147">**Modifiers.**</span></span> <span data-ttu-id="3924c-148">Alle Member des Moduls handelt es sich implizit [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="3924c-148">All module members are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="3924c-149">Sie können keine der `Shared` -Schlüsselwort deklariert einen Member, und Sie den freigegebenen Status aller Mitglieder ändern kann nicht.</span><span class="sxs-lookup"><span data-stu-id="3924c-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>  
  
-   <span data-ttu-id="3924c-150">**Vererbung.**</span><span class="sxs-lookup"><span data-stu-id="3924c-150">**Inheritance.**</span></span> <span data-ttu-id="3924c-151">Ein Modul kann nicht von einem Typ erben, außer <xref:System.Object>, von dem alle Module zu erben.</span><span class="sxs-lookup"><span data-stu-id="3924c-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="3924c-152">Ein Modul kann nicht vor allem von einem anderen erben.</span><span class="sxs-lookup"><span data-stu-id="3924c-152">In particular, one module cannot inherit from another.</span></span>  
  
     <span data-ttu-id="3924c-153">Sie können keine der [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) auch nicht zum angeben, in der Moduldefinition eines <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="3924c-153">You cannot use the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>  
  
-   <span data-ttu-id="3924c-154">**Standardeigenschaft.**</span><span class="sxs-lookup"><span data-stu-id="3924c-154">**Default Property.**</span></span> <span data-ttu-id="3924c-155">Sie können keine standardmäßigen Eigenschaften in einem Modul definieren.</span><span class="sxs-lookup"><span data-stu-id="3924c-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="3924c-156">Weitere Informationen finden Sie unter [Standard](../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="3924c-156">For more information, see [Default](../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="3924c-157">Verhalten</span><span class="sxs-lookup"><span data-stu-id="3924c-157">Behavior</span></span>  
  
-   <span data-ttu-id="3924c-158">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="3924c-158">**Access Level.**</span></span> <span data-ttu-id="3924c-159">Innerhalb eines Moduls können Sie jeden Member mit einer eigenen Zugriffsebene deklarieren.</span><span class="sxs-lookup"><span data-stu-id="3924c-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="3924c-160">Standardzugriff für Module [öffentliche](../../../visual-basic/language-reference/modifiers/public.md) zuzugreifen, mit Ausnahme von Variablen und Konstanten, die standardmäßig [Private](../../../visual-basic/language-reference/modifiers/private.md) Zugriff.</span><span class="sxs-lookup"><span data-stu-id="3924c-160">Module members default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access, except variables and constants, which default to [Private](../../../visual-basic/language-reference/modifiers/private.md) access.</span></span> <span data-ttu-id="3924c-161">Wenn ein Modul mehr als einen seiner Member Zugriff eingeschränktem, hat die Zugriffsebene des angegebenen Moduls Vorrang vor.</span><span class="sxs-lookup"><span data-stu-id="3924c-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>  
  
-   <span data-ttu-id="3924c-162">**Bereich.**</span><span class="sxs-lookup"><span data-stu-id="3924c-162">**Scope.**</span></span> <span data-ttu-id="3924c-163">Ein Modul ist im Bereich im gesamten Namespace.</span><span class="sxs-lookup"><span data-stu-id="3924c-163">A module is in scope throughout its namespace.</span></span>  
  
     <span data-ttu-id="3924c-164">Der Gültigkeitsbereich jedes Modul-Element ist das gesamte Modul.</span><span class="sxs-lookup"><span data-stu-id="3924c-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="3924c-165">Beachten Sie, die alle Elemente werden *typerweiterung*, wodurch ihres Bereichs, die auf den Namespace, die das Modul höher gestuft werden.</span><span class="sxs-lookup"><span data-stu-id="3924c-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="3924c-166">Weitere Informationen finden Sie unter [Typerweiterung](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="3924c-166">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
-   <span data-ttu-id="3924c-167">**Qualifizierung.**</span><span class="sxs-lookup"><span data-stu-id="3924c-167">**Qualification.**</span></span> <span data-ttu-id="3924c-168">Sie haben mehrere Module in einem Projekt, und Sie können Member mit demselben Namen in zwei oder mehrere Module deklarieren.</span><span class="sxs-lookup"><span data-stu-id="3924c-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="3924c-169">Allerdings müssen Sie alle Verweise auf einen solchen Member mit dem entsprechenden Modulnamen qualifizieren, wenn der Verweis von außerhalb des Moduls ist.</span><span class="sxs-lookup"><span data-stu-id="3924c-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="3924c-170">Weitere Informationen finden Sie unter [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="3924c-170">For more information, see [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3924c-171">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3924c-171">Example</span></span>  
 [!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]  
  
## <a name="see-also"></a><span data-ttu-id="3924c-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3924c-172">See also</span></span>

- [<span data-ttu-id="3924c-173">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3924c-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="3924c-174">Namespace-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3924c-174">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="3924c-175">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3924c-175">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="3924c-176">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3924c-176">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="3924c-177">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3924c-177">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="3924c-178">Typerweiterung</span><span class="sxs-lookup"><span data-stu-id="3924c-178">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
