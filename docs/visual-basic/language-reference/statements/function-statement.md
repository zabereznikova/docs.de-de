---
title: Function-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 52e9210f9e715b6055e6ed199ef1aa4b919c6dd6
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="4c9f6-102">Function-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c9f6-102">Function Statement (Visual Basic)</span></span>
<span data-ttu-id="4c9f6-103">Deklariert den Namen, Parameter und Code, definieren eine `Function` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c9f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c9f6-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]  
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Function ]  
    [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="4c9f6-105">Teile</span><span class="sxs-lookup"><span data-stu-id="4c9f6-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="4c9f6-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-106">Optional.</span></span> <span data-ttu-id="4c9f6-107">Finden Sie unter [Attributliste](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="4c9f6-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="4c9f6-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-108">Optional.</span></span> <span data-ttu-id="4c9f6-109">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="4c9f6-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="4c9f6-110">Public</span><span class="sxs-lookup"><span data-stu-id="4c9f6-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="4c9f6-111">Protected</span><span class="sxs-lookup"><span data-stu-id="4c9f6-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="4c9f6-112">Friend</span><span class="sxs-lookup"><span data-stu-id="4c9f6-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="4c9f6-113">Private</span><span class="sxs-lookup"><span data-stu-id="4c9f6-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="4c9f6-114">Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4c9f6-114">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="4c9f6-115">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-115">Optional.</span></span> <span data-ttu-id="4c9f6-116">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="4c9f6-116">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="4c9f6-117">Overloads</span><span class="sxs-lookup"><span data-stu-id="4c9f6-117">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="4c9f6-118">Overrides</span><span class="sxs-lookup"><span data-stu-id="4c9f6-118">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="4c9f6-119">Overridable</span><span class="sxs-lookup"><span data-stu-id="4c9f6-119">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="4c9f6-120">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="4c9f6-120">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="4c9f6-121">MustOverride</span><span class="sxs-lookup"><span data-stu-id="4c9f6-121">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="4c9f6-122">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-122">Optional.</span></span> <span data-ttu-id="4c9f6-123">Finden Sie unter [freigegebene](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="4c9f6-123">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="4c9f6-124">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-124">Optional.</span></span> <span data-ttu-id="4c9f6-125">Finden Sie unter [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="4c9f6-125">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="4c9f6-126">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-126">Optional.</span></span> <span data-ttu-id="4c9f6-127">Finden Sie unter [Async](../../../visual-basic/language-reference/modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="4c9f6-127">See [Async](../../../visual-basic/language-reference/modifiers/async.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="4c9f6-128">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-128">Optional.</span></span> <span data-ttu-id="4c9f6-129">Finden Sie unter [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="4c9f6-129">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="4c9f6-130">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-130">Required.</span></span> <span data-ttu-id="4c9f6-131">Der Name der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-131">Name of the procedure.</span></span> <span data-ttu-id="4c9f6-132">Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="4c9f6-132">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="4c9f6-133">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-133">Optional.</span></span> <span data-ttu-id="4c9f6-134">Liste mit Typparametern für eine generische Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-134">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="4c9f6-135">Finden Sie unter [geben Liste](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="4c9f6-135">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="4c9f6-136">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-136">Optional.</span></span> <span data-ttu-id="4c9f6-137">Liste der Namen lokaler Variablen, die die Parameter dieser Prozedur darstellt.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-137">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="4c9f6-138">Finden Sie unter [Parameterliste](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="4c9f6-138">See [Parameter List](parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="4c9f6-139">Erforderlich, wenn `Option Strict` ist `On`.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-139">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="4c9f6-140">Der Datentyp des Werts, der von dieser Prozedur zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-140">Data type of the value returned by this procedure.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="4c9f6-141">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-141">Optional.</span></span> <span data-ttu-id="4c9f6-142">Gibt an, dass dieses Verfahren eine oder mehrere implementiert `Function` Prozeduren, die jeweils in einer Schnittstelle implementiert, die von dieser Prozedur enthaltenen Klasse oder Struktur definiert.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-142">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="4c9f6-143">Finden Sie unter [Anweisung implementiert](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4c9f6-143">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="4c9f6-144">Erforderlich, wenn `Implements` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-144">Required if `Implements` is supplied.</span></span> <span data-ttu-id="4c9f6-145">Liste der zu implementierenden `Function`-Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-145">List of `Function` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="4c9f6-146">Jede `implementedprocedure` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="4c9f6-146">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="4c9f6-147">Segment</span><span class="sxs-lookup"><span data-stu-id="4c9f6-147">Part</span></span>|<span data-ttu-id="4c9f6-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c9f6-148">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="4c9f6-149">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-149">Required.</span></span> <span data-ttu-id="4c9f6-150">Name einer Schnittstelle implementiert, die von dieser Prozedur der enthaltenden Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-150">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="4c9f6-151">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-151">Required.</span></span> <span data-ttu-id="4c9f6-152">Name, wodurch die Prozedur in `interface` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-152">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="4c9f6-153">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-153">Optional.</span></span> <span data-ttu-id="4c9f6-154">Gibt an, dass dieses Verfahren eine oder mehrere bestimmte Ereignisse verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-154">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="4c9f6-155">Finden Sie unter [behandelt](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4c9f6-155">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="4c9f6-156">Erforderlich, wenn `Handles` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-156">Required if `Handles` is supplied.</span></span> <span data-ttu-id="4c9f6-157">Die Liste der Ereignisse, die diese Prozedur behandelt.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-157">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="4c9f6-158">Jede `eventspecifier` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="4c9f6-158">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="4c9f6-159">Segment</span><span class="sxs-lookup"><span data-stu-id="4c9f6-159">Part</span></span>|<span data-ttu-id="4c9f6-160">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c9f6-160">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="4c9f6-161">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-161">Required.</span></span> <span data-ttu-id="4c9f6-162">Mit dem Datentyp der Klasse oder Struktur, die das Ereignis auslöst deklarierte Objektvariable.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-162">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="4c9f6-163">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-163">Required.</span></span> <span data-ttu-id="4c9f6-164">Der Name des Ereignisses, das dieses Verfahren behandelt.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-164">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="4c9f6-165">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-165">Optional.</span></span> <span data-ttu-id="4c9f6-166">Der Block von Anweisungen in diesem Verfahren ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-166">Block of statements to be executed within this procedure.</span></span>  
  
-   `End Function`  
  
     <span data-ttu-id="4c9f6-167">Beendet die Definition dieses Verfahrens fort.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-167">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c9f6-168">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4c9f6-168">Remarks</span></span>  
 <span data-ttu-id="4c9f6-169">Alle ausführbaren Code muss innerhalb einer Prozedur sein.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-169">All executable code must be inside a procedure.</span></span> <span data-ttu-id="4c9f6-170">Jede Prozedur deklariert wiederum innerhalb einer Klasse, eine Struktur oder ein Modul, das als die enthaltende Klasse, Struktur oder Modul bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-170">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>  
  
 <span data-ttu-id="4c9f6-171">Um einen Wert an den aufrufenden Code zurückzugeben, verwenden eine `Function` Prozedur; verwenden Sie andernfalls eine `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-171">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>  
  
## <a name="defining-a-function"></a><span data-ttu-id="4c9f6-172">Definieren einer Funktion</span><span class="sxs-lookup"><span data-stu-id="4c9f6-172">Defining a Function</span></span>  
 <span data-ttu-id="4c9f6-173">Sie können definieren, eine `Function` Prozedur nur auf Modulebene.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-173">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="4c9f6-174">Aus diesem Grund wird der Deklarationskontext für eine Funktion muss eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle und nicht mit einer Quelldatei, einen Namespace, eine Prozedur oder eines Blocks.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-174">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="4c9f6-175">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4c9f6-175">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="4c9f6-176">`Function`Prozeduren standardmäßig öffentlichen Zugriff auf.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-176">`Function` procedures default to public access.</span></span> <span data-ttu-id="4c9f6-177">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-177">You can adjust their access levels with the access modifiers.</span></span>  
  
 <span data-ttu-id="4c9f6-178">Ein `Function` Prozedur deklariert den Datentyp des Werts, der die Prozedur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-178">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="4c9f6-179">Sie können einen beliebigen Datentyp aufweisen oder den Namen des eine Enumeration, eine Struktur, eine Klasse oder einer Schnittstelle angeben.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-179">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="4c9f6-180">Wenn Sie nicht angeben, die `returntype` -Parameter der Prozedur zurückgibt `Object`.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-180">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>  
  
 <span data-ttu-id="4c9f6-181">Wenn die Prozedur verwendet die `Implements` -Schlüsselwort, der enthaltenden Klasse oder Struktur benötigen auch eine `Implements` -Anweisung, die unmittelbar folgt seine `Class` oder `Structure` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-181">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="4c9f6-182">Die `Implements` -Anweisung muss jede Schnittstelle, die im angegebenen enthalten `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="4c9f6-183">Jedoch den Namen, die mit dem eine Schnittstelle definiert die `Function` (in `definedname`) muss nicht mit dem Namen dieser Prozedur übereinstimmen (in `name`).</span><span class="sxs-lookup"><span data-stu-id="4c9f6-183">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c9f6-184">Lambda-Ausdrücke können Funktion Ausdrücke Inline definiert werden.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-184">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="4c9f6-185">Weitere Informationen finden Sie unter [Funktionsausdruck](../../../visual-basic/language-reference/operators/function-expression.md) und [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4c9f6-185">For more information, see [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md) and [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="returning-from-a-function"></a><span data-ttu-id="4c9f6-186">Zurückgeben aus einer Funktion</span><span class="sxs-lookup"><span data-stu-id="4c9f6-186">Returning from a Function</span></span>  
 <span data-ttu-id="4c9f6-187">Wenn die `Function` Prozedur werden an den aufrufenden Code zurückgibt, die Ausführung wird fortgeführt, mit der Anweisung, die die Anweisung folgt, die die Prozedur aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-187">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>  
  
 <span data-ttu-id="4c9f6-188">Um einen Wert aus einer Funktion zurückgeben, können Sie entweder den Wert dem Funktionsnamen zuweisen bzw. Fügen Sie ihn in eine `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-188">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>  
  
 <span data-ttu-id="4c9f6-189">Die `Return` Anweisung gleichzeitig weist den Rückgabewert und die Funktion beendet, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-189">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]  
  
 <span data-ttu-id="4c9f6-190">Im folgende Beispiel weist den Rückgabewert den Namen der Funktion `myFunction` und verwendet dann die `Exit Function` -Anweisung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-190">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]  
  
 <span data-ttu-id="4c9f6-191">Die `Exit Function` und `Return` Anweisungen bewirken, dass eine sofortige Beendigung von einem `Function` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-191">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="4c9f6-192">Eine beliebige Anzahl von `Exit Function` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie können kombinieren `Exit Function` und `Return` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-192">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>  
  
 <span data-ttu-id="4c9f6-193">Bei Verwendung von `Exit Function` ohne Zuweisen eines Werts zur `name`, die Prozedur gibt zurück, der Standardwert für den Datentyp, der im angegebenen `returntype`.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-193">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="4c9f6-194">Wenn `returntype` nicht angegeben ist, gibt die Prozedur `Nothing`, dies ist der Standardwert für `Object`.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-194">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>  
  
## <a name="calling-a-function"></a><span data-ttu-id="4c9f6-195">Aufrufen einer Funktion</span><span class="sxs-lookup"><span data-stu-id="4c9f6-195">Calling a Function</span></span>  
 <span data-ttu-id="4c9f6-196">Rufen Sie eine `Function` Prozedur mithilfe der Prozedurname gefolgt von der Argumentliste in Klammern in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-196">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="4c9f6-197">Sie können die Klammern weglassen, nur dann, wenn Sie Argumente angeben, werden nicht.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-197">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="4c9f6-198">Allerdings ist der Code besser lesbar, wenn Sie immer die Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-198">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="4c9f6-199">Rufen Sie eine `Function` Prozedur, die die gleiche Weise, dass Sie jede Bibliothek aufrufen, wie z. B. Funktion `Sqrt`, `Cos`, oder `ChrW`.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-199">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>  
  
 <span data-ttu-id="4c9f6-200">Sie können auch eine Funktion aufrufen, mit dem `Call` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-200">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="4c9f6-201">In diesem Fall wird der zurückgegebene Wert ignoriert.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-201">In that case, the return value is ignored.</span></span> <span data-ttu-id="4c9f6-202">Verwenden der `Call` Schlüsselwort wird nicht in den meisten Fällen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-202">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="4c9f6-203">Weitere Informationen finden Sie unter [-Anweisung Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4c9f6-203">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="4c9f6-204">Visual Basic werden manchmal neu angeordnet, arithmetische Ausdrücke, um die interne Effizienz steigern.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-204">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="4c9f6-205">Aus diesem Grund verwenden Sie keine `Function` Prozedur in einem arithmetischen Ausdruck, wenn die Funktion den Wert von Variablen im selben Ausdruck ändert.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-205">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>  
  
## <a name="async-functions"></a><span data-ttu-id="4c9f6-206">Asynchrone Funktionen</span><span class="sxs-lookup"><span data-stu-id="4c9f6-206">Async Functions</span></span>  
 <span data-ttu-id="4c9f6-207">Die *Async* Funktion können Sie asynchrone Funktionen aufrufen, ohne explizite Rückrufe verwenden oder manuell über mehrere Funktionen oder Lambda-Ausdrücke Teilen Codes zu müssen.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-207">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="4c9f6-208">Wenn Sie eine Funktion mit kennzeichnen der [Async](../../../visual-basic/language-reference/modifiers/async.md) Modifizierer verwenden, können Sie die ["await"](../../../visual-basic/language-reference/operators/await-operator.md) Operator in der Funktion.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-208">If you mark a function with the [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="4c9f6-209">Wenn Steuerung erreicht eine `Await` Ausdruck in der `Async` Funktion, Steuerung an den Aufrufer zurückgegeben, und die Funktion Ausführung wird angehalten, bis die erwartete Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-209">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="4c9f6-210">Wenn die Aufgabe abgeschlossen ist, kann die Ausführung in der Funktion fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-210">When the task is complete, execution can resume in the function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c9f6-211">Ein `Async` Prozedur an den Aufrufer zurückgegeben, wenn entweder das erste erwartete Objekt gefunden wird, die noch nicht abgeschlossen ist, oder er ruft am Ende der `Async` Prozedur, welches Ereignis zuerst eintritt.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-211">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>  
  
 <span data-ttu-id="4c9f6-212">Ein `Async` Funktion kann den Rückgabetyp haben <xref:System.Threading.Tasks.Task%601> oder <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-212">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="4c9f6-213">Ein Beispiel für eine `Async` -Funktion, die einen Rückgabetyp <xref:System.Threading.Tasks.Task%601> wird unten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-213">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>  
  
 <span data-ttu-id="4c9f6-214">Ein `Async` Funktion kann nicht deklariert werden alle [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) Parameter.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-214">An `Async` function cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="4c9f6-215">Ein [Sub-Anweisung](sub-statement.md) kann auch mit gekennzeichnet werden die `Async` Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-215">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="4c9f6-216">Dies wird in erster Linie für Ereignishandler verwendet, in dem ein Wert kann nicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-216">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="4c9f6-217">Ein `Async``Sub` Prozedur kann nicht abgewartet werden, und der Aufrufer eine `Async``Sub` Prozedur kann nicht durch ausgelöste Ausnahmen abfangen der `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-217">An `Async``Sub` procedure can't be awaited, and the caller of an `Async``Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>  
  
 <span data-ttu-id="4c9f6-218">Weitere Informationen zu `Async` -Funktionen finden Sie unter [asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Ablaufsteuerung in asynchronen Programmen](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), und [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="4c9f6-218">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="iterator-functions"></a><span data-ttu-id="4c9f6-219">Iteratorfunktionen</span><span class="sxs-lookup"><span data-stu-id="4c9f6-219">Iterator Functions</span></span>  
 <span data-ttu-id="4c9f6-220">Ein *Iterator* Funktion führt eine benutzerdefinierte Iteration durch eine Auflistung, z. B. eine Liste oder ein Array.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-220">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="4c9f6-221">Eine Iteratorfunktion verwendet die [Yield](yield-statement.md) Anweisung, um jedes Element einzeln nacheinander zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-221">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="4c9f6-222">Wenn eine [Yield](yield-statement.md) -Anweisung erreicht wird, wird die aktuelle Position im Code gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-222">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="4c9f6-223">Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-223">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="4c9f6-224">Sie rufen einen Iterator im Clientcode mithilfe einer [für jede... Nächste](for-each-next-statement.md) Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-224">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>  
  
 <span data-ttu-id="4c9f6-225">Der Rückgabetyp einer Funktion Iterator kann <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, oder <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-225">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="4c9f6-226">Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="4c9f6-226">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c9f6-227">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4c9f6-227">Example</span></span>  
 <span data-ttu-id="4c9f6-228">Im folgenden Beispiel wird die `Function` -Anweisung zum Deklarieren, deren Name, Parameter und Code, der den Text der bilden eine `Function` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-228">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="4c9f6-229">Die `ParamArray` Modifizierer ermöglicht die Funktion eine Variable Anzahl von Argumenten akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-229">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#25](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="4c9f6-230">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4c9f6-230">Example</span></span>  
 <span data-ttu-id="4c9f6-231">Im folgende Beispiel wird die Funktion deklariert, die im vorherigen Beispiel aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-231">The following example invokes the function declared in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="4c9f6-232">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4c9f6-232">Example</span></span>  
 <span data-ttu-id="4c9f6-233">Im folgenden Beispiel `DelayAsync` ist ein `Async``Function` , die einen Rückgabetyp hat <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-233">In the following example, `DelayAsync` is an `Async``Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="4c9f6-234">`DelayAsync` enthält eine `Return`-Anweisung, die eine ganze Zahl zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-234">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="4c9f6-235">Aus diesem Grund die Funktionsdeklaration von `DelayAsync` muss einen Rückgabetyp verfügen `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-235">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="4c9f6-236">Da der Rückgabetyp ist `Task(Of Integer)`, der Auswertung der `Await` Ausdruck in `DoSomethingAsync` erzeugt eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-236">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="4c9f6-237">Dies wird in dieser Anweisung dargestellt: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-237">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="4c9f6-238">Die `startButton_Click` Verfahren ist ein Beispiel für eine `Async Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-238">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="4c9f6-239">Da `DoSomethingAsync` ist ein `Async` -Funktion, die Aufgabe für den Aufruf von `DoSomethingAsync` muss abgewartet werden, wie die folgende Anweisung veranschaulicht: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-239">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="4c9f6-240">Die `startButton_Click``Sub` Prozedur muss definiert werden, mit der `Async` Modifizierer, da es wurde ein `Await` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="4c9f6-240">The `startButton_Click``Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4c9f6-241">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c9f6-241">See Also</span></span>  
 [<span data-ttu-id="4c9f6-242">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4c9f6-242">Sub Statement</span></span>](sub-statement.md)  
 [<span data-ttu-id="4c9f6-243">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="4c9f6-243">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [<span data-ttu-id="4c9f6-244">Parameterliste</span><span class="sxs-lookup"><span data-stu-id="4c9f6-244">Parameter List</span></span>](parameter-list.md)  
 [<span data-ttu-id="4c9f6-245">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4c9f6-245">Dim Statement</span></span>](dim-statement.md)  
 [<span data-ttu-id="4c9f6-246">Call-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4c9f6-246">Call Statement</span></span>](call-statement.md)  
 [<span data-ttu-id="4c9f6-247">Of</span><span class="sxs-lookup"><span data-stu-id="4c9f6-247">Of</span></span>](of-clause.md)  
 [<span data-ttu-id="4c9f6-248">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="4c9f6-248">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [<span data-ttu-id="4c9f6-249">Gewusst wie: Verwenden einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="4c9f6-249">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="4c9f6-250">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="4c9f6-250">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [<span data-ttu-id="4c9f6-251">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="4c9f6-251">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="4c9f6-252">Function Expression</span><span class="sxs-lookup"><span data-stu-id="4c9f6-252">Function Expression</span></span>](../../../visual-basic/language-reference/operators/function-expression.md)
