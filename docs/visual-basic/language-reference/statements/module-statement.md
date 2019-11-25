---
title: Module-Anweisung
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
ms.openlocfilehash: 56fc4f9383f1fc4779358ef18a4e5c611d897eda
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348020"
---
# <a name="module-statement"></a><span data-ttu-id="9253f-102">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9253f-102">Module Statement</span></span>

<span data-ttu-id="9253f-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span><span class="sxs-lookup"><span data-stu-id="9253f-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>

## <a name="syntax"></a><span data-ttu-id="9253f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9253f-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ]  Module name
    [ statements ]
End Module
```

## <a name="parts"></a><span data-ttu-id="9253f-105">Teile</span><span class="sxs-lookup"><span data-stu-id="9253f-105">Parts</span></span>

`attributelist`  
<span data-ttu-id="9253f-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="9253f-106">Optional.</span></span> <span data-ttu-id="9253f-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="9253f-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>

`accessmodifier`  
<span data-ttu-id="9253f-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="9253f-108">Optional.</span></span> <span data-ttu-id="9253f-109">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="9253f-109">Can be one of the following:</span></span>

- [<span data-ttu-id="9253f-110">Public</span><span class="sxs-lookup"><span data-stu-id="9253f-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

- [<span data-ttu-id="9253f-111">Friend</span><span class="sxs-lookup"><span data-stu-id="9253f-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

<span data-ttu-id="9253f-112">Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="9253f-112">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

`name`  
<span data-ttu-id="9253f-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9253f-113">Required.</span></span> <span data-ttu-id="9253f-114">Name of this module.</span><span class="sxs-lookup"><span data-stu-id="9253f-114">Name of this module.</span></span> <span data-ttu-id="9253f-115">Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="9253f-115">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

`statements`  
<span data-ttu-id="9253f-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="9253f-116">Optional.</span></span> <span data-ttu-id="9253f-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span><span class="sxs-lookup"><span data-stu-id="9253f-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>

`End Module`  
<span data-ttu-id="9253f-118">Beendet die `Module`-Definition.</span><span class="sxs-lookup"><span data-stu-id="9253f-118">Terminates the `Module` definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="9253f-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9253f-119">Remarks</span></span>

<span data-ttu-id="9253f-120">A `Module` statement defines a reference type available throughout its namespace.</span><span class="sxs-lookup"><span data-stu-id="9253f-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="9253f-121">A *module* (sometimes called a *standard module*) is similar to a class but with some important distinctions.</span><span class="sxs-lookup"><span data-stu-id="9253f-121">A *module* (sometimes called a *standard module*) is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="9253f-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span><span class="sxs-lookup"><span data-stu-id="9253f-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="9253f-123">Modules do not support inheritance or implement interfaces.</span><span class="sxs-lookup"><span data-stu-id="9253f-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="9253f-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span><span class="sxs-lookup"><span data-stu-id="9253f-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>

<span data-ttu-id="9253f-125">You can use `Module` only at namespace level.</span><span class="sxs-lookup"><span data-stu-id="9253f-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="9253f-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span><span class="sxs-lookup"><span data-stu-id="9253f-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="9253f-127">You cannot nest a module within another module, or within any type.</span><span class="sxs-lookup"><span data-stu-id="9253f-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="9253f-128">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="9253f-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="9253f-129">A module has the same lifetime as your program.</span><span class="sxs-lookup"><span data-stu-id="9253f-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="9253f-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span><span class="sxs-lookup"><span data-stu-id="9253f-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>

<span data-ttu-id="9253f-131">Modules default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access.</span><span class="sxs-lookup"><span data-stu-id="9253f-131">Modules default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access.</span></span> <span data-ttu-id="9253f-132">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="9253f-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="9253f-133">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="9253f-133">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="9253f-134">All members of a module are implicitly `Shared`.</span><span class="sxs-lookup"><span data-stu-id="9253f-134">All members of a module are implicitly `Shared`.</span></span>

## <a name="classes-and-modules"></a><span data-ttu-id="9253f-135">Classes and Modules</span><span class="sxs-lookup"><span data-stu-id="9253f-135">Classes and Modules</span></span>

<span data-ttu-id="9253f-136">These elements have many similarities, but there are some important differences as well.</span><span class="sxs-lookup"><span data-stu-id="9253f-136">These elements have many similarities, but there are some important differences as well.</span></span>

- <span data-ttu-id="9253f-137">**Terminology.**</span><span class="sxs-lookup"><span data-stu-id="9253f-137">**Terminology.**</span></span> <span data-ttu-id="9253f-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span><span class="sxs-lookup"><span data-stu-id="9253f-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="9253f-139">The current version calls these *classes* and *modules*, respectively.</span><span class="sxs-lookup"><span data-stu-id="9253f-139">The current version calls these *classes* and *modules*, respectively.</span></span>

- <span data-ttu-id="9253f-140">**Shared Members.**</span><span class="sxs-lookup"><span data-stu-id="9253f-140">**Shared Members.**</span></span> <span data-ttu-id="9253f-141">You can control whether a member of a class is a shared or instance member.</span><span class="sxs-lookup"><span data-stu-id="9253f-141">You can control whether a member of a class is a shared or instance member.</span></span>

- <span data-ttu-id="9253f-142">**Object Orientation.**</span><span class="sxs-lookup"><span data-stu-id="9253f-142">**Object Orientation.**</span></span> <span data-ttu-id="9253f-143">Classes are object-oriented, but modules are not.</span><span class="sxs-lookup"><span data-stu-id="9253f-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="9253f-144">So only classes can be instantiated as objects.</span><span class="sxs-lookup"><span data-stu-id="9253f-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="9253f-145">For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="9253f-145">For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>

## <a name="rules"></a><span data-ttu-id="9253f-146">Regeln</span><span class="sxs-lookup"><span data-stu-id="9253f-146">Rules</span></span>

- <span data-ttu-id="9253f-147">**Modifiers.**</span><span class="sxs-lookup"><span data-stu-id="9253f-147">**Modifiers.**</span></span> <span data-ttu-id="9253f-148">All module members are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="9253f-148">All module members are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="9253f-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span><span class="sxs-lookup"><span data-stu-id="9253f-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>

- <span data-ttu-id="9253f-150">**Vererbung.**</span><span class="sxs-lookup"><span data-stu-id="9253f-150">**Inheritance.**</span></span> <span data-ttu-id="9253f-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span><span class="sxs-lookup"><span data-stu-id="9253f-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="9253f-152">In particular, one module cannot inherit from another.</span><span class="sxs-lookup"><span data-stu-id="9253f-152">In particular, one module cannot inherit from another.</span></span>

  <span data-ttu-id="9253f-153">You cannot use the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="9253f-153">You cannot use the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>

- <span data-ttu-id="9253f-154">**Default Property.**</span><span class="sxs-lookup"><span data-stu-id="9253f-154">**Default Property.**</span></span> <span data-ttu-id="9253f-155">You cannot define any default properties in a module.</span><span class="sxs-lookup"><span data-stu-id="9253f-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="9253f-156">For more information, see [Default](../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="9253f-156">For more information, see [Default](../../../visual-basic/language-reference/modifiers/default.md).</span></span>

## <a name="behavior"></a><span data-ttu-id="9253f-157">Verhalten</span><span class="sxs-lookup"><span data-stu-id="9253f-157">Behavior</span></span>

- <span data-ttu-id="9253f-158">**Access Level.**</span><span class="sxs-lookup"><span data-stu-id="9253f-158">**Access Level.**</span></span> <span data-ttu-id="9253f-159">Within a module, you can declare each member with its own access level.</span><span class="sxs-lookup"><span data-stu-id="9253f-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="9253f-160">Module members default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access, except variables and constants, which default to [Private](../../../visual-basic/language-reference/modifiers/private.md) access.</span><span class="sxs-lookup"><span data-stu-id="9253f-160">Module members default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access, except variables and constants, which default to [Private](../../../visual-basic/language-reference/modifiers/private.md) access.</span></span> <span data-ttu-id="9253f-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span><span class="sxs-lookup"><span data-stu-id="9253f-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>

- <span data-ttu-id="9253f-162">**Scope.**</span><span class="sxs-lookup"><span data-stu-id="9253f-162">**Scope.**</span></span> <span data-ttu-id="9253f-163">A module is in scope throughout its namespace.</span><span class="sxs-lookup"><span data-stu-id="9253f-163">A module is in scope throughout its namespace.</span></span>

  <span data-ttu-id="9253f-164">The scope of every module member is the entire module.</span><span class="sxs-lookup"><span data-stu-id="9253f-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="9253f-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span><span class="sxs-lookup"><span data-stu-id="9253f-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="9253f-166">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="9253f-166">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>

- <span data-ttu-id="9253f-167">**Qualification.**</span><span class="sxs-lookup"><span data-stu-id="9253f-167">**Qualification.**</span></span> <span data-ttu-id="9253f-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span><span class="sxs-lookup"><span data-stu-id="9253f-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="9253f-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span><span class="sxs-lookup"><span data-stu-id="9253f-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="9253f-170">Weitere Informationen finden Sie unter [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="9253f-170">For more information, see [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

## <a name="example"></a><span data-ttu-id="9253f-171">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9253f-171">Example</span></span>

[!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]

## <a name="see-also"></a><span data-ttu-id="9253f-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9253f-172">See also</span></span>

- [<span data-ttu-id="9253f-173">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9253f-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="9253f-174">Namespace-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9253f-174">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="9253f-175">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9253f-175">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="9253f-176">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9253f-176">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="9253f-177">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9253f-177">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="9253f-178">Typerweiterung</span><span class="sxs-lookup"><span data-stu-id="9253f-178">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
