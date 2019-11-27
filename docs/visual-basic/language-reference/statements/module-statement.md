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
# <a name="module-statement"></a><span data-ttu-id="e297c-102">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e297c-102">Module Statement</span></span>

<span data-ttu-id="e297c-103">Deklariert den Namen eines Moduls und führt die Definition der Variablen, Eigenschaften, Ereignisse und Prozeduren ein, die das Modul umfasst.</span><span class="sxs-lookup"><span data-stu-id="e297c-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>

## <a name="syntax"></a><span data-ttu-id="e297c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e297c-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ]  Module name
    [ statements ]
End Module
```

## <a name="parts"></a><span data-ttu-id="e297c-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="e297c-105">Parts</span></span>

`attributelist`  
<span data-ttu-id="e297c-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="e297c-106">Optional.</span></span> <span data-ttu-id="e297c-107">Siehe [Attribut Liste](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="e297c-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>

`accessmodifier`  
<span data-ttu-id="e297c-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="e297c-108">Optional.</span></span> <span data-ttu-id="e297c-109">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="e297c-109">Can be one of the following:</span></span>

- [<span data-ttu-id="e297c-110">Public</span><span class="sxs-lookup"><span data-stu-id="e297c-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

- [<span data-ttu-id="e297c-111">Friend</span><span class="sxs-lookup"><span data-stu-id="e297c-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

<span data-ttu-id="e297c-112">Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e297c-112">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

`name`  
<span data-ttu-id="e297c-113">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="e297c-113">Required.</span></span> <span data-ttu-id="e297c-114">Der Name dieses Moduls.</span><span class="sxs-lookup"><span data-stu-id="e297c-114">Name of this module.</span></span> <span data-ttu-id="e297c-115">Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="e297c-115">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

`statements`  
<span data-ttu-id="e297c-116">Optional.</span><span class="sxs-lookup"><span data-stu-id="e297c-116">Optional.</span></span> <span data-ttu-id="e297c-117">Anweisungen, die die Variablen, Eigenschaften, Ereignisse, Prozeduren und die Typen dieses Moduls definieren.</span><span class="sxs-lookup"><span data-stu-id="e297c-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>

`End Module`  
<span data-ttu-id="e297c-118">Beendet die `Module`-Definition.</span><span class="sxs-lookup"><span data-stu-id="e297c-118">Terminates the `Module` definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="e297c-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e297c-119">Remarks</span></span>

<span data-ttu-id="e297c-120">Eine `Module`-Anweisung definiert einen Referenztyp, der im gesamten Namespace verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e297c-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="e297c-121">Ein *Modul* (manchmal auch als *Standardmodul*bezeichnet) ähnelt einer Klasse, jedoch mit einigen wichtigen unterschieden.</span><span class="sxs-lookup"><span data-stu-id="e297c-121">A *module* (sometimes called a *standard module*) is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="e297c-122">Jedes Modul verfügt über genau eine Instanz und muss weder erstellt noch einer Variablen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="e297c-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="e297c-123">Module unterstützen keine Vererbung oder Implementierung von Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="e297c-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="e297c-124">Beachten Sie, dass ein Modul kein *Typ* in dem Sinn ist, dass eine Klasse oder Struktur ist – Sie können kein Programmier Element deklarieren, um den Datentyp eines Moduls zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e297c-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>

<span data-ttu-id="e297c-125">Sie können `Module` nur auf Namespace Ebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="e297c-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="e297c-126">Dies bedeutet, dass der *Deklarations Kontext* für ein Modul eine Quelldatei oder ein Namespace sein muss und weder eine Klasse noch eine Struktur, ein Modul, eine Schnittstelle, eine Prozedur oder einen Block sein kann.</span><span class="sxs-lookup"><span data-stu-id="e297c-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="e297c-127">Sie können ein Modul nicht in einem anderen Modul oder in einem beliebigen Typ Schachteln.</span><span class="sxs-lookup"><span data-stu-id="e297c-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="e297c-128">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e297c-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="e297c-129">Ein Modul hat die gleiche Lebensdauer wie das Programm.</span><span class="sxs-lookup"><span data-stu-id="e297c-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="e297c-130">Da die Elemente alle `Shared`sind, haben Sie auch die Lebensdauer, die der des Programms entspricht.</span><span class="sxs-lookup"><span data-stu-id="e297c-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>

<span data-ttu-id="e297c-131">Module haben standardmäßig den [Friend](../../../visual-basic/language-reference/modifiers/friend.md) -Zugriff.</span><span class="sxs-lookup"><span data-stu-id="e297c-131">Modules default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access.</span></span> <span data-ttu-id="e297c-132">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="e297c-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="e297c-133">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e297c-133">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="e297c-134">Alle Member eines Moduls werden implizit `Shared`.</span><span class="sxs-lookup"><span data-stu-id="e297c-134">All members of a module are implicitly `Shared`.</span></span>

## <a name="classes-and-modules"></a><span data-ttu-id="e297c-135">Klassen und Module</span><span class="sxs-lookup"><span data-stu-id="e297c-135">Classes and Modules</span></span>

<span data-ttu-id="e297c-136">Diese Elemente weisen viele Ähnlichkeiten auf, aber es gibt auch einige wichtige Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="e297c-136">These elements have many similarities, but there are some important differences as well.</span></span>

- <span data-ttu-id="e297c-137">**Begriffs.**</span><span class="sxs-lookup"><span data-stu-id="e297c-137">**Terminology.**</span></span> <span data-ttu-id="e297c-138">In früheren Versionen von Visual Basic werden zwei Arten von Modulen erkannt: *Klassen Module* (CLS-Dateien) und *Standardmodule* (Bas-Dateien).</span><span class="sxs-lookup"><span data-stu-id="e297c-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="e297c-139">Mit der aktuellen Version werden diese *Klassen* bzw. *Module*aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e297c-139">The current version calls these *classes* and *modules*, respectively.</span></span>

- <span data-ttu-id="e297c-140">**Freigegebene Member.**</span><span class="sxs-lookup"><span data-stu-id="e297c-140">**Shared Members.**</span></span> <span data-ttu-id="e297c-141">Sie können steuern, ob ein Member einer Klasse ein frei Gegebenes oder ein Instanzmember ist.</span><span class="sxs-lookup"><span data-stu-id="e297c-141">You can control whether a member of a class is a shared or instance member.</span></span>

- <span data-ttu-id="e297c-142">**Objekt Ausrichtung.**</span><span class="sxs-lookup"><span data-stu-id="e297c-142">**Object Orientation.**</span></span> <span data-ttu-id="e297c-143">Klassen sind objektorientiert, aber Module sind nicht.</span><span class="sxs-lookup"><span data-stu-id="e297c-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="e297c-144">Daher können nur Klassen als Objekte instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="e297c-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="e297c-145">Weitere Informationen finden Sie unter [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="e297c-145">For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>

## <a name="rules"></a><span data-ttu-id="e297c-146">Regeln</span><span class="sxs-lookup"><span data-stu-id="e297c-146">Rules</span></span>

- <span data-ttu-id="e297c-147">**Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="e297c-147">**Modifiers.**</span></span> <span data-ttu-id="e297c-148">Alle Modulmember werden implizit frei [gegeben](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="e297c-148">All module members are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="e297c-149">Sie können das `Shared`-Schlüsselwort nicht verwenden, wenn Sie einen Member deklarieren, und Sie können den freigegebenen Status eines beliebigen Members nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="e297c-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>

- <span data-ttu-id="e297c-150">**Vererbung.**</span><span class="sxs-lookup"><span data-stu-id="e297c-150">**Inheritance.**</span></span> <span data-ttu-id="e297c-151">Ein Modul kann nicht von einem anderen Typ als dem <xref:System.Object>erben, von dem alle Module erben.</span><span class="sxs-lookup"><span data-stu-id="e297c-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="e297c-152">Insbesondere kann ein Modul nicht von einem anderen Modul erben.</span><span class="sxs-lookup"><span data-stu-id="e297c-152">In particular, one module cannot inherit from another.</span></span>

  <span data-ttu-id="e297c-153">Die [erbt-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md) kann nicht in einer Modul Definition verwendet werden, auch um <xref:System.Object>anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e297c-153">You cannot use the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>

- <span data-ttu-id="e297c-154">**Standard Eigenschaft.**</span><span class="sxs-lookup"><span data-stu-id="e297c-154">**Default Property.**</span></span> <span data-ttu-id="e297c-155">In einem Modul können keine Standardeigenschaften definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e297c-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="e297c-156">Weitere Informationen finden Sie unter [default (Standard](../../../visual-basic/language-reference/modifiers/default.md)).</span><span class="sxs-lookup"><span data-stu-id="e297c-156">For more information, see [Default](../../../visual-basic/language-reference/modifiers/default.md).</span></span>

## <a name="behavior"></a><span data-ttu-id="e297c-157">Verhalten</span><span class="sxs-lookup"><span data-stu-id="e297c-157">Behavior</span></span>

- <span data-ttu-id="e297c-158">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="e297c-158">**Access Level.**</span></span> <span data-ttu-id="e297c-159">Innerhalb eines Moduls können Sie jeden Member mit einer eigenen Zugriffsebene deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e297c-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="e297c-160">Modul Elemente haben standardmäßig den [öffentlichen](../../../visual-basic/language-reference/modifiers/public.md) Zugriff, mit Ausnahme von Variablen und Konstanten, die standardmäßig den [privaten](../../../visual-basic/language-reference/modifiers/private.md) Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="e297c-160">Module members default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access, except variables and constants, which default to [Private](../../../visual-basic/language-reference/modifiers/private.md) access.</span></span> <span data-ttu-id="e297c-161">Wenn ein Modul über einen eingeschränkteren Zugriff als einen seiner Mitglieder verfügt, hat die angegebene Modul Zugriffsebene Vorrang.</span><span class="sxs-lookup"><span data-stu-id="e297c-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>

- <span data-ttu-id="e297c-162">**Umfang.**</span><span class="sxs-lookup"><span data-stu-id="e297c-162">**Scope.**</span></span> <span data-ttu-id="e297c-163">Ein Modul befindet sich im gesamten Namespace im Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="e297c-163">A module is in scope throughout its namespace.</span></span>

  <span data-ttu-id="e297c-164">Der Gültigkeitsbereich jedes Modulmembers ist das gesamte Modul.</span><span class="sxs-lookup"><span data-stu-id="e297c-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="e297c-165">Beachten Sie, dass alle Member eine *typherauf*Stufung durchlaufen, was bewirkt, dass Ihr Bereich in den Namespace herauf gestuft wird, der das Modul enthält.</span><span class="sxs-lookup"><span data-stu-id="e297c-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="e297c-166">Weitere Informationen finden Sie unter [Typerweiterung](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="e297c-166">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>

- <span data-ttu-id="e297c-167">**Abschluss.**</span><span class="sxs-lookup"><span data-stu-id="e297c-167">**Qualification.**</span></span> <span data-ttu-id="e297c-168">Sie können über mehrere Module in einem Projekt verfügen, und Sie können in zwei oder mehr Modulen Member mit demselben Namen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e297c-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="e297c-169">Sie müssen allerdings einen beliebigen Verweis auf ein solches Element mit dem entsprechenden Modulnamen qualifizieren, wenn der Verweis von außerhalb dieses Moduls liegt.</span><span class="sxs-lookup"><span data-stu-id="e297c-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="e297c-170">Weitere Informationen finden Sie unter [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="e297c-170">For more information, see [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

## <a name="example"></a><span data-ttu-id="e297c-171">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e297c-171">Example</span></span>

[!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]

## <a name="see-also"></a><span data-ttu-id="e297c-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e297c-172">See also</span></span>

- [<span data-ttu-id="e297c-173">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e297c-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="e297c-174">Namespace-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e297c-174">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="e297c-175">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e297c-175">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="e297c-176">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e297c-176">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="e297c-177">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e297c-177">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="e297c-178">Typerweiterung</span><span class="sxs-lookup"><span data-stu-id="e297c-178">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
