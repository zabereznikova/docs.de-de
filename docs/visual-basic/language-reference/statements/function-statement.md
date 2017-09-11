---
title: Funktion-Anweisung (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Function
dev_langs:
- VB
helpviewer_keywords:
- procedures, creating
- Function procedures, Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword, Function statements
- Private keyword, Function statements
- declarations, procedures
- procedures, declaration
- Public keyword, in Function statement
- ByVal keyword, Function statements
- procedures, recursive
- Implements keyword, Function statements
- procedures, returning values
- Exit statement, in Function procedures
- recursive procedures
- As keyword, in Function statement
- Optional keyword, Function statements
- Function statement
- Visual Basic code, Function procedures
- procedures, function
- ByRef keyword, Function statements
- Friend keyword, Function statements
- End keyword, Function statements
- Handles keyword, Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
caps.latest.revision: 62
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
ms.sourcegitcommit: dc1c456c71efb3cc6e60a8fdc77384e65975f110
ms.openlocfilehash: d875fe6df3ef7ac9390346588b1c2d48497d7116
ms.contentlocale: de-de
ms.lasthandoff: 05/15/2017

---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="2b991-102">Function-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b991-102">Function Statement (Visual Basic)</span></span>
<span data-ttu-id="2b991-103">Deklariert den Namen, Parameter und Code, definieren ein `Function` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="2b991-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b991-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b991-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]  
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Function ]  
    [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="2b991-105">Teile</span><span class="sxs-lookup"><span data-stu-id="2b991-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="2b991-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="2b991-106">Optional.</span></span> <span data-ttu-id="2b991-107">Finden Sie unter [Attributliste](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="2b991-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="2b991-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="2b991-108">Optional.</span></span> <span data-ttu-id="2b991-109">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="2b991-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="2b991-110">Public</span><span class="sxs-lookup"><span data-stu-id="2b991-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="2b991-111">Protected</span><span class="sxs-lookup"><span data-stu-id="2b991-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="2b991-112">Friend</span><span class="sxs-lookup"><span data-stu-id="2b991-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="2b991-113">Private</span><span class="sxs-lookup"><span data-stu-id="2b991-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="2b991-114">Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2b991-114">See [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="2b991-115">Optional.</span><span class="sxs-lookup"><span data-stu-id="2b991-115">Optional.</span></span> <span data-ttu-id="2b991-116">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="2b991-116">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="2b991-117">Overloads</span><span class="sxs-lookup"><span data-stu-id="2b991-117">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="2b991-118">Overrides</span><span class="sxs-lookup"><span data-stu-id="2b991-118">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="2b991-119">Overridable</span><span class="sxs-lookup"><span data-stu-id="2b991-119">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="2b991-120">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="2b991-120">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="2b991-121">MustOverride</span><span class="sxs-lookup"><span data-stu-id="2b991-121">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="2b991-122">Optional.</span><span class="sxs-lookup"><span data-stu-id="2b991-122">Optional.</span></span> <span data-ttu-id="2b991-123">Finden Sie unter [freigegebenen](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="2b991-123">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="2b991-124">Optional.</span><span class="sxs-lookup"><span data-stu-id="2b991-124">Optional.</span></span> <span data-ttu-id="2b991-125">Finden Sie unter [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="2b991-125">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="2b991-126">Optional.</span><span class="sxs-lookup"><span data-stu-id="2b991-126">Optional.</span></span> <span data-ttu-id="2b991-127">Finden Sie unter [Async](../../../visual-basic/language-reference/modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="2b991-127">See [Async](../../../visual-basic/language-reference/modifiers/async.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="2b991-128">Optional.</span><span class="sxs-lookup"><span data-stu-id="2b991-128">Optional.</span></span> <span data-ttu-id="2b991-129">Finden Sie unter [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="2b991-129">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="2b991-130">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2b991-130">Required.</span></span> <span data-ttu-id="2b991-131">Der Name der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="2b991-131">Name of the procedure.</span></span> <span data-ttu-id="2b991-132">Finden Sie unter [deklarierten Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="2b991-132">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="2b991-133">Optional.</span><span class="sxs-lookup"><span data-stu-id="2b991-133">Optional.</span></span> <span data-ttu-id="2b991-134">Liste mit Typparametern für eine generische Prozedur.</span><span class="sxs-lookup"><span data-stu-id="2b991-134">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="2b991-135">Finden Sie unter [Liste](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="2b991-135">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="2b991-136">Optional.</span><span class="sxs-lookup"><span data-stu-id="2b991-136">Optional.</span></span> <span data-ttu-id="2b991-137">Die Liste der Namen lokaler Variablen, die die Parameter dieser Prozedur darstellt.</span><span class="sxs-lookup"><span data-stu-id="2b991-137">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="2b991-138">Finden Sie unter [Parameterliste](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="2b991-138">See [Parameter List](parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="2b991-139">Erforderlich, wenn `Option Strict` ist `On`.</span><span class="sxs-lookup"><span data-stu-id="2b991-139">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="2b991-140">Der Datentyp des Werts, der von dieser Prozedur zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2b991-140">Data type of the value returned by this procedure.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="2b991-141">Optional.</span><span class="sxs-lookup"><span data-stu-id="2b991-141">Optional.</span></span> <span data-ttu-id="2b991-142">Gibt an, dass diese Prozedur eine oder mehrere implementiert `Function` Prozeduren, die jeweils in einer Schnittstelle, die von der enthaltenden Klasse oder Struktur dieser Prozedur implementiert definiert.</span><span class="sxs-lookup"><span data-stu-id="2b991-142">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="2b991-143">Finden Sie unter [Anweisung implementiert](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2b991-143">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="2b991-144">Erforderlich, wenn `Implements` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2b991-144">Required if `Implements` is supplied.</span></span> <span data-ttu-id="2b991-145">Liste der zu implementierenden `Function`-Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="2b991-145">List of `Function` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="2b991-146">Jede `implementedprocedure` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="2b991-146">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="2b991-147">Segment</span><span class="sxs-lookup"><span data-stu-id="2b991-147">Part</span></span>|<span data-ttu-id="2b991-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b991-148">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="2b991-149">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2b991-149">Required.</span></span> <span data-ttu-id="2b991-150">Name der Schnittstelle implementiert, die von dieser Prozedur der enthaltenden Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="2b991-150">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="2b991-151">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2b991-151">Required.</span></span> <span data-ttu-id="2b991-152">Name, wodurch die Prozedur in `interface` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="2b991-152">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="2b991-153">Optional.</span><span class="sxs-lookup"><span data-stu-id="2b991-153">Optional.</span></span> <span data-ttu-id="2b991-154">Gibt an, dass diese Prozedur eine oder mehrere bestimmte Ereignisse behandeln kann.</span><span class="sxs-lookup"><span data-stu-id="2b991-154">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="2b991-155">Finden Sie unter [behandelt](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="2b991-155">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="2b991-156">Erforderlich, wenn `Handles` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2b991-156">Required if `Handles` is supplied.</span></span> <span data-ttu-id="2b991-157">Die Liste der Ereignisse, die diese Prozedur behandelt.</span><span class="sxs-lookup"><span data-stu-id="2b991-157">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="2b991-158">Jede `eventspecifier` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="2b991-158">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="2b991-159">Segment</span><span class="sxs-lookup"><span data-stu-id="2b991-159">Part</span></span>|<span data-ttu-id="2b991-160">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b991-160">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="2b991-161">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2b991-161">Required.</span></span> <span data-ttu-id="2b991-162">Objektvariable deklariert, die mit dem Datentyp der Klasse oder Struktur, die das Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="2b991-162">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="2b991-163">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2b991-163">Required.</span></span> <span data-ttu-id="2b991-164">Der Name des Ereignisses, die diese Prozedur behandelt.</span><span class="sxs-lookup"><span data-stu-id="2b991-164">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="2b991-165">Optional.</span><span class="sxs-lookup"><span data-stu-id="2b991-165">Optional.</span></span> <span data-ttu-id="2b991-166">Der Block von Anweisungen, die innerhalb dieser Prozedur ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2b991-166">Block of statements to be executed within this procedure.</span></span>  
  
-   `End Function`  
  
     <span data-ttu-id="2b991-167">Beendet die Definition dieser Prozedur.</span><span class="sxs-lookup"><span data-stu-id="2b991-167">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b991-168">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b991-168">Remarks</span></span>  
 <span data-ttu-id="2b991-169">Der gesamte ausführbare Code muss innerhalb einer Prozedur sein.</span><span class="sxs-lookup"><span data-stu-id="2b991-169">All executable code must be inside a procedure.</span></span> <span data-ttu-id="2b991-170">Jede Prozedur deklariert, innerhalb einer Klasse, eine Struktur oder ein Modul, das als die enthaltende Klasse, Struktur oder Modul bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="2b991-170">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>  
  
 <span data-ttu-id="2b991-171">Verwenden, um einen Wert an den aufrufenden Code zurückgeben, eine `Function` Verfahren; verwenden Sie andernfalls ein `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="2b991-171">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>  
  
## <a name="defining-a-function"></a><span data-ttu-id="2b991-172">Definieren einer Funktion</span><span class="sxs-lookup"><span data-stu-id="2b991-172">Defining a Function</span></span>  
 <span data-ttu-id="2b991-173">Sie können eine `Function` Prozedur nur auf Modulebene.</span><span class="sxs-lookup"><span data-stu-id="2b991-173">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="2b991-174">Aus diesem Grund Deklarationskontext für eine Funktion muss eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein und darf keine Quelldatei, einen Namespace, eine Prozedur oder ein Block sein.</span><span class="sxs-lookup"><span data-stu-id="2b991-174">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="2b991-175">Weitere Informationen finden Sie unter [Deklarationskontexte und Zugriffsebenen standardmäßig](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2b991-175">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="2b991-176">`Function`-Prozeduren weisen standardmäßig öffentlichen Zugriff.</span><span class="sxs-lookup"><span data-stu-id="2b991-176">`Function` procedures default to public access.</span></span> <span data-ttu-id="2b991-177">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="2b991-177">You can adjust their access levels with the access modifiers.</span></span>  
  
 <span data-ttu-id="2b991-178">Ein `Function` Prozedur deklariert den Datentyp des Werts, der die Prozedur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2b991-178">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="2b991-179">Sie können einen beliebigen Datentyp oder den Namen einer Enumeration, einer Struktur, einer Klasse oder Schnittstelle angeben.</span><span class="sxs-lookup"><span data-stu-id="2b991-179">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="2b991-180">Wenn Sie keinen der `returntype` -Parameter der Prozedur zurückgegebenen `Object`.</span><span class="sxs-lookup"><span data-stu-id="2b991-180">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>  
  
 <span data-ttu-id="2b991-181">Wenn die Prozedur verwendet die `Implements` -Schlüsselwort, der enthaltenden Klasse oder Struktur müssen eine `Implements` Anweisung unmittelbar nach seiner `Class` oder `Structure` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2b991-181">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="2b991-182">Die `Implements` -Anweisung muss jede Schnittstelle, die im angegebenen enthalten `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="2b991-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="2b991-183">Allerdings den Namen, mit dem eine Schnittstelle definiert, die `Function` (in `definedname`) muss mit dem Namen dieser Prozedur übereinstimmen (in `name`).</span><span class="sxs-lookup"><span data-stu-id="2b991-183">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b991-184">Lambda-Ausdrücke können Inlinefunktion Ausdrücken definieren.</span><span class="sxs-lookup"><span data-stu-id="2b991-184">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="2b991-185">Weitere Informationen finden Sie unter [Funktionsausdruck](../../../visual-basic/language-reference/operators/function-expression.md) und [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2b991-185">For more information, see [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md) and [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="returning-from-a-function"></a><span data-ttu-id="2b991-186">Zurückgeben aus einer Funktion</span><span class="sxs-lookup"><span data-stu-id="2b991-186">Returning from a Function</span></span>  
 <span data-ttu-id="2b991-187">Wenn die `Function` -Prozedur zum aufrufenden Code zurückkehrt, Ausführung mit der Anweisung fortgesetzt, die auf die Anweisung folgt, die die Prozedur aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="2b991-187">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>  
  
 <span data-ttu-id="2b991-188">Um einen Wert aus einer Funktion zurückgeben, Sie können entweder den Wert dem Funktionsnamen zuweisen oder ihn in eine `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2b991-188">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>  
  
 <span data-ttu-id="2b991-189">Die `Return` Anweisung gleichzeitig weist den Rückgabewert und beendet die Funktion wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2b991-189">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>  
  
 <span data-ttu-id="2b991-190">[!code-vb[VbVbalrStatements&#24;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2b991-190">[!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]</span></span>  
  
 <span data-ttu-id="2b991-191">Das folgende Beispiel weist den Rückgabewert an den Funktionsnamen `myFunction` und verwendet dann die `Exit Function` -Anweisung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2b991-191">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>  
  
 <span data-ttu-id="2b991-192">[!code-vb[VbVbalrStatements&23;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="2b991-192">[!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]</span></span>  
  
 <span data-ttu-id="2b991-193">Die `Exit Function` und `Return` -Anweisung führen zur unmittelbare Beendigung einer `Function` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="2b991-193">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="2b991-194">Eine beliebige Anzahl von `Exit Function` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie kombinieren können `Exit Function` und `Return` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="2b991-194">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>  
  
 <span data-ttu-id="2b991-195">Bei Verwendung von `Exit Function` ohne Zuweisen eines Werts zur `name`, die Prozedur gibt den Standardwert für den Datentyp, der im angegebenen `returntype`.</span><span class="sxs-lookup"><span data-stu-id="2b991-195">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="2b991-196">Wenn `returntype` nicht angegeben ist, gibt die Prozedur `Nothing`, der Standardwert für `Object`.</span><span class="sxs-lookup"><span data-stu-id="2b991-196">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>  
  
## <a name="calling-a-function"></a><span data-ttu-id="2b991-197">Aufrufen einer Funktion</span><span class="sxs-lookup"><span data-stu-id="2b991-197">Calling a Function</span></span>  
 <span data-ttu-id="2b991-198">Rufen Sie eine `Function` Prozedur über den Prozedurnamen, gefolgt von der Argumentliste in Klammern in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="2b991-198">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="2b991-199">Sie können die Klammern weglassen, nur dann, wenn Sie Argumente angeben, werden nicht.</span><span class="sxs-lookup"><span data-stu-id="2b991-199">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="2b991-200">Allerdings ist der Code besser lesbar, wenn Sie immer die Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="2b991-200">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="2b991-201">Rufen Sie eine `Function` Prozedur genauso, als Sie jede Bibliothek aufrufen, wie z. B. Funktion `Sqrt`, `Cos`, oder `ChrW`.</span><span class="sxs-lookup"><span data-stu-id="2b991-201">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>  
  
 <span data-ttu-id="2b991-202">Sie können auch eine Funktion aufrufen, mit dem `Call` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="2b991-202">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="2b991-203">In diesem Fall ist der Rückgabewert ignoriert.</span><span class="sxs-lookup"><span data-stu-id="2b991-203">In that case, the return value is ignored.</span></span> <span data-ttu-id="2b991-204">Verwenden der `Call` Schlüsselwort wird nicht in den meisten Fällen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="2b991-204">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="2b991-205">Weitere Informationen finden Sie unter [Call-Anweisung](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2b991-205">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="2b991-206">Visual Basic werden manchmal neu angeordnet, arithmetische Ausdrücke, um die interne Effizienz zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="2b991-206">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="2b991-207">Aus diesem Grund sollten Sie nicht verwenden einer `Function` Prozedur in einem arithmetischen Ausdruck, wenn die Funktion den Wert von Variablen im selben Ausdruck ändert.</span><span class="sxs-lookup"><span data-stu-id="2b991-207">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>  
  
## <a name="async-functions"></a><span data-ttu-id="2b991-208">Async-Funktion</span><span class="sxs-lookup"><span data-stu-id="2b991-208">Async Functions</span></span>  
 <span data-ttu-id="2b991-209">Die *Async* Feature können Sie zum Aufrufen von asynchronen Funktionen ohne explizite Rückrufe verwenden oder den Code manuell über mehrere Funktionen oder Lambda-Ausdrücke teilen.</span><span class="sxs-lookup"><span data-stu-id="2b991-209">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="2b991-210">Das Markieren eine Funktion mit der [Async](../../../visual-basic/language-reference/modifiers/async.md) Modifizierer verwenden, können Sie die ["await"](../../../visual-basic/language-reference/operators/await-operator.md) Operator in der Funktion.</span><span class="sxs-lookup"><span data-stu-id="2b991-210">If you mark a function with the [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="2b991-211">Wenn das Steuerelement erreicht eine `Await` Ausdruck in der `Async` Funktion, die Steuerung an den Aufrufer zurückgegeben, und Status in der Funktion wird angehalten, bis die Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2b991-211">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="2b991-212">Wenn der Vorgang abgeschlossen ist, können in der Funktion die Ausführung fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="2b991-212">When the task is complete, execution can resume in the function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b991-213">Ein `Async` Prozedur an den Aufrufer zurückgegeben, wenn entweder das erste await-Objekt gefunden, die noch nicht abgeschlossen ist oder das Ende erreicht die `Async` Verfahren, welches Ereignis zuerst eintritt.</span><span class="sxs-lookup"><span data-stu-id="2b991-213">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>  
  
 <span data-ttu-id="2b991-214">Ein `Async` Funktion kann keinen Rückgabetyp aufweisen oder <xref:System.Threading.Tasks.Task%601> <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="2b991-214">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="2b991-215">Ein Beispiel für eine `Async` -Funktion, die einen Rückgabetyp hat <xref:System.Threading.Tasks.Task%601>finden Sie weiter unten.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="2b991-215">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>  
  
 <span data-ttu-id="2b991-216">Ein `Async` Funktion kann nicht deklariert werden, keine [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) Parameter.</span><span class="sxs-lookup"><span data-stu-id="2b991-216">An `Async` function cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="2b991-217">Ein [Sub-Anweisung](sub-statement.md) kann auch gekennzeichnet werden, mit der `Async` Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="2b991-217">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="2b991-218">Dies wird hauptsächlich für Ereignishandler verwendet, kann ein Wert zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2b991-218">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="2b991-219">Ein `Async``Sub` Prozedur kann nicht abgewartet werden, und der Aufrufer eine `Async``Sub` Prozedur kann nicht von ausgelösten Ausnahmen abfangen der `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="2b991-219">An `Async``Sub` procedure can't be awaited, and the caller of an `Async``Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>  
  
 <span data-ttu-id="2b991-220">Weitere Informationen zu `Async` -Funktionen finden Sie unter [asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Ablaufsteuerung in asynchronen Programmen](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), und [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="2b991-220">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="iterator-functions"></a><span data-ttu-id="2b991-221">Iteratorfunktionen</span><span class="sxs-lookup"><span data-stu-id="2b991-221">Iterator Functions</span></span>  
 <span data-ttu-id="2b991-222">Ein *Iterator* Funktion führt eine benutzerdefinierte Iteration durch eine Auflistung, z. B. eine Liste oder ein Array.</span><span class="sxs-lookup"><span data-stu-id="2b991-222">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="2b991-223">Eine Iteratorfunktion verwendet die [ergeben](yield-statement.md) Anweisung, um jedes Element einzeln nacheinander zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="2b991-223">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="2b991-224">Wenn ein [ergeben](yield-statement.md) -Anweisung erreicht ist, wird die aktuelle Position im Code gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2b991-224">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="2b991-225">Die Ausführung wird von diesem Speicherort das nächste Mal neu gestartet, wenn, das die Iteratorfunktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2b991-225">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="2b991-226">Sie rufen den Iterator im Client-Code mit einem [für jeden... Nächste](for-each-next-statement.md) Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2b991-226">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>  
  
 <span data-ttu-id="2b991-227">Der Rückgabetyp einer Funktion Iterator kann <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, oder <xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="2b991-227">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="2b991-228">Weitere Informationen finden Sie unter [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="2b991-228">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b991-229">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2b991-229">Example</span></span>  
 <span data-ttu-id="2b991-230">Im folgenden Beispiel wird die `Function` Anweisung deklariert den Namen, Parameter und Code, der den Text der form einer `Function` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="2b991-230">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="2b991-231">Die `ParamArray` -Modifizierer kann eine Funktion eine Variable Anzahl von Argumenten akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="2b991-231">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>  
  
 <span data-ttu-id="2b991-232">[!code-vb[VbVbalrStatements&#25;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="2b991-232">[!code-vb[VbVbalrStatements#25](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b991-233">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2b991-233">Example</span></span>  
 <span data-ttu-id="2b991-234">Im folgende Beispiel wird die im vorangehenden Beispiel deklarierte Funktion aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="2b991-234">The following example invokes the function declared in the preceding example.</span></span>  
  
 <span data-ttu-id="2b991-235">[!code-vb[VbVbalrStatements&#26;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="2b991-235">[!code-vb[VbVbalrStatements#26](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b991-236">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2b991-236">Example</span></span>  
 <span data-ttu-id="2b991-237">Im folgenden Beispiel `DelayAsync` ist ein `Async``Function` , bei dem Rückgabetyp <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="2b991-237">In the following example, `DelayAsync` is an `Async``Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="2b991-238">`DelayAsync` enthält eine `Return`-Anweisung, die eine ganze Zahl zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2b991-238">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="2b991-239">Aus diesem Grund der Deklaration des `DelayAsync` muss einen Rückgabetyp haben `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="2b991-239">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="2b991-240">Da der Rückgabetyp ist `Task(Of Integer)`, die Auswertung der `Await` Ausdruck in `DoSomethingAsync` erzeugt eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="2b991-240">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="2b991-241">Dies wird in der folgenden Anweisung dargestellt: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="2b991-241">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="2b991-242">Die `startButton_Click` Verfahren ist ein Beispiel für ein `Async Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="2b991-242">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="2b991-243">Da `DoSomethingAsync` ist ein `Async` -Funktion, die die Aufgabe für den Aufruf von `DoSomethingAsync` muss gewartet werden, wie die folgende Anweisung veranschaulicht: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="2b991-243">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="2b991-244">Die `startButton_Click``Sub` Prozedur muss definiert werden, mit der `Async` Modifizierer, weil sie verfügt über eine `Await` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="2b991-244">The `startButton_Click``Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 <span data-ttu-id="2b991-245">[!code-vb[CsAsyncMethod&#1;](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="2b991-245">[!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b991-246">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b991-246">See Also</span></span>  
 <span data-ttu-id="2b991-247">[Sub-Anweisung](sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2b991-247">[Sub Statement](sub-statement.md) </span></span>  
<span data-ttu-id="2b991-248"> [Function-Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="2b991-248"> [Function Procedures](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) </span></span>  
<span data-ttu-id="2b991-249"> [Parameterliste](parameter-list.md) </span><span class="sxs-lookup"><span data-stu-id="2b991-249"> [Parameter List](parameter-list.md) </span></span>  
<span data-ttu-id="2b991-250"> [Dim-Anweisung](dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2b991-250"> [Dim Statement](dim-statement.md) </span></span>  
<span data-ttu-id="2b991-251"> [Call-Anweisung](call-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2b991-251"> [Call Statement](call-statement.md) </span></span>  
<span data-ttu-id="2b991-252"> [Of](of-clause.md) </span><span class="sxs-lookup"><span data-stu-id="2b991-252"> [Of](of-clause.md) </span></span>  
<span data-ttu-id="2b991-253"> [Parameterarrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="2b991-253"> [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md) </span></span>  
<span data-ttu-id="2b991-254"> [Gewusst wie: Verwenden einer generischen Klasse](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md) </span><span class="sxs-lookup"><span data-stu-id="2b991-254"> [How to: Use a Generic Class](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md) </span></span>  
<span data-ttu-id="2b991-255"> [Problembehandlung bei Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="2b991-255"> [Troubleshooting Procedures](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="2b991-256"> [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="2b991-256"> [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span></span>  
<span data-ttu-id="2b991-257"> [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md)</span><span class="sxs-lookup"><span data-stu-id="2b991-257"> [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md)</span></span>

