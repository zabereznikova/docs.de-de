---
title: Function-Anweisung
ms.date: 05/12/2018
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
ms.openlocfilehash: 8140c7e6267e66c69c20d413a11d04372400c581
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345920"
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="ff423-102">Function-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff423-102">Function Statement (Visual Basic)</span></span>

<span data-ttu-id="ff423-103">Deklariert den Namen, die Parameter und den Code, die eine `Function` Prozedur definieren.</span><span class="sxs-lookup"><span data-stu-id="ff423-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="ff423-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff423-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a><span data-ttu-id="ff423-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="ff423-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="ff423-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="ff423-106">Optional.</span></span> <span data-ttu-id="ff423-107">Siehe [Attribut Liste](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="ff423-107">See [Attribute List](attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="ff423-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="ff423-108">Optional.</span></span> <span data-ttu-id="ff423-109">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="ff423-109">Can be one of the following:</span></span>

  - [<span data-ttu-id="ff423-110">Public</span><span class="sxs-lookup"><span data-stu-id="ff423-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

  - [<span data-ttu-id="ff423-111">Protected</span><span class="sxs-lookup"><span data-stu-id="ff423-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)

  - [<span data-ttu-id="ff423-112">Friend</span><span class="sxs-lookup"><span data-stu-id="ff423-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

  - [<span data-ttu-id="ff423-113">Private</span><span class="sxs-lookup"><span data-stu-id="ff423-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

  - [<span data-ttu-id="ff423-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="ff423-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="ff423-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="ff423-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="ff423-116">Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ff423-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="ff423-117">Optional.</span><span class="sxs-lookup"><span data-stu-id="ff423-117">Optional.</span></span> <span data-ttu-id="ff423-118">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="ff423-118">Can be one of the following:</span></span>

  - [<span data-ttu-id="ff423-119">Overloads</span><span class="sxs-lookup"><span data-stu-id="ff423-119">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)

  - [<span data-ttu-id="ff423-120">Overrides</span><span class="sxs-lookup"><span data-stu-id="ff423-120">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)

  - [<span data-ttu-id="ff423-121">Overrides</span><span class="sxs-lookup"><span data-stu-id="ff423-121">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)

  - [<span data-ttu-id="ff423-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="ff423-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)

  - [<span data-ttu-id="ff423-123">MustOverride</span><span class="sxs-lookup"><span data-stu-id="ff423-123">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="ff423-124">Optional.</span><span class="sxs-lookup"><span data-stu-id="ff423-124">Optional.</span></span> <span data-ttu-id="ff423-125">Siehe [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="ff423-125">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="ff423-126">Optional.</span><span class="sxs-lookup"><span data-stu-id="ff423-126">Optional.</span></span> <span data-ttu-id="ff423-127">Siehe [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="ff423-127">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="ff423-128">Optional.</span><span class="sxs-lookup"><span data-stu-id="ff423-128">Optional.</span></span> <span data-ttu-id="ff423-129">Siehe [Async](../../../visual-basic/language-reference/modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="ff423-129">See [Async](../../../visual-basic/language-reference/modifiers/async.md).</span></span>

- `Iterator`

  <span data-ttu-id="ff423-130">Optional.</span><span class="sxs-lookup"><span data-stu-id="ff423-130">Optional.</span></span> <span data-ttu-id="ff423-131">Siehe [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="ff423-131">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="ff423-132">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="ff423-132">Required.</span></span> <span data-ttu-id="ff423-133">Der Name der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="ff423-133">Name of the procedure.</span></span> <span data-ttu-id="ff423-134">Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="ff423-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="ff423-135">Optional.</span><span class="sxs-lookup"><span data-stu-id="ff423-135">Optional.</span></span> <span data-ttu-id="ff423-136">Liste der Typparameter für eine generische Prozedur.</span><span class="sxs-lookup"><span data-stu-id="ff423-136">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="ff423-137">Siehe [Typliste](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="ff423-137">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="ff423-138">Optional.</span><span class="sxs-lookup"><span data-stu-id="ff423-138">Optional.</span></span> <span data-ttu-id="ff423-139">Liste der Namen der lokalen Variablen, die die Parameter dieser Prozedur darstellen.</span><span class="sxs-lookup"><span data-stu-id="ff423-139">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="ff423-140">Siehe [Parameter Liste](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="ff423-140">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="ff423-141">Erforderlich, wenn `Option Strict` `On`ist.</span><span class="sxs-lookup"><span data-stu-id="ff423-141">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="ff423-142">Datentyp des Werts, der von dieser Prozedur zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ff423-142">Data type of the value returned by this procedure.</span></span>

- `Implements`

  <span data-ttu-id="ff423-143">Optional.</span><span class="sxs-lookup"><span data-stu-id="ff423-143">Optional.</span></span> <span data-ttu-id="ff423-144">Gibt an, dass diese Prozedur mindestens eine `Function` Prozeduren implementiert, die in einer Schnittstelle definiert sind, die von der enthaltenden Klasse oder Struktur dieser Prozedur implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="ff423-144">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="ff423-145">Siehe [implementierende Anweisung](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ff423-145">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="ff423-146">Erforderlich, wenn `Implements` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ff423-146">Required if `Implements` is supplied.</span></span> <span data-ttu-id="ff423-147">Liste der zu implementierenden `Function`-Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="ff423-147">List of `Function` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="ff423-148">Jede `implementedprocedure` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="ff423-148">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="ff423-149">-Komponente</span><span class="sxs-lookup"><span data-stu-id="ff423-149">Part</span></span>|<span data-ttu-id="ff423-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff423-150">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="ff423-151">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="ff423-151">Required.</span></span> <span data-ttu-id="ff423-152">Der Name einer Schnittstelle, die von der enthaltenden Klasse oder Struktur dieser Prozedur implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="ff423-152">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="ff423-153">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="ff423-153">Required.</span></span> <span data-ttu-id="ff423-154">Name, wodurch die Prozedur in `interface` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ff423-154">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="ff423-155">Optional.</span><span class="sxs-lookup"><span data-stu-id="ff423-155">Optional.</span></span> <span data-ttu-id="ff423-156">Gibt an, dass diese Prozedur ein oder mehrere bestimmte Ereignisse verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="ff423-156">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="ff423-157">Siehe [Handles](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ff423-157">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="ff423-158">Erforderlich, wenn `Handles` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ff423-158">Required if `Handles` is supplied.</span></span> <span data-ttu-id="ff423-159">Die Liste der Ereignisse, die von dieser Prozedur behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="ff423-159">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="ff423-160">Jede `eventspecifier` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="ff423-160">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="ff423-161">-Komponente</span><span class="sxs-lookup"><span data-stu-id="ff423-161">Part</span></span>|<span data-ttu-id="ff423-162">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff423-162">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="ff423-163">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="ff423-163">Required.</span></span> <span data-ttu-id="ff423-164">Objekt Variable, die mit dem Datentyp der Klasse oder Struktur deklariert wurde, die das Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="ff423-164">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="ff423-165">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="ff423-165">Required.</span></span> <span data-ttu-id="ff423-166">Der Name des Ereignisses, das diese Prozedur behandelt.</span><span class="sxs-lookup"><span data-stu-id="ff423-166">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="ff423-167">Optional.</span><span class="sxs-lookup"><span data-stu-id="ff423-167">Optional.</span></span> <span data-ttu-id="ff423-168">Block von-Anweisungen, die innerhalb dieser Prozedur ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ff423-168">Block of statements to be executed within this procedure.</span></span>

- `End Function`

  <span data-ttu-id="ff423-169">Beendet die Definition dieser Prozedur.</span><span class="sxs-lookup"><span data-stu-id="ff423-169">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff423-170">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff423-170">Remarks</span></span>

<span data-ttu-id="ff423-171">Der gesamte ausführbare Code muss sich in einer Prozedur befinden.</span><span class="sxs-lookup"><span data-stu-id="ff423-171">All executable code must be inside a procedure.</span></span> <span data-ttu-id="ff423-172">Die einzelnen Prozeduren werden wiederum innerhalb einer Klasse, einer Struktur oder eines Moduls deklariert, das als enthaltende Klasse, Struktur oder Modul bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="ff423-172">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>

<span data-ttu-id="ff423-173">Um einen Wert an den aufrufenden Code zurückzugeben, verwenden Sie eine `Function` Prozedur. Verwenden Sie andernfalls eine `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="ff423-173">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>

## <a name="defining-a-function"></a><span data-ttu-id="ff423-174">Definieren einer Funktion</span><span class="sxs-lookup"><span data-stu-id="ff423-174">Defining a Function</span></span>

<span data-ttu-id="ff423-175">Sie können eine `Function` Prozedur nur auf Modulebene definieren.</span><span class="sxs-lookup"><span data-stu-id="ff423-175">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="ff423-176">Daher muss der Deklarations Kontext für eine Funktion eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein, und es kann sich nicht um eine Quelldatei, einen Namespace, eine Prozedur oder einen Block handeln.</span><span class="sxs-lookup"><span data-stu-id="ff423-176">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="ff423-177">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ff423-177">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="ff423-178">`Function` Prozeduren werden standardmäßig öffentlich zugänglich.</span><span class="sxs-lookup"><span data-stu-id="ff423-178">`Function` procedures default to public access.</span></span> <span data-ttu-id="ff423-179">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="ff423-179">You can adjust their access levels with the access modifiers.</span></span>

<span data-ttu-id="ff423-180">Eine `Function` Prozedur kann den Datentyp des Werts deklarieren, den die Prozedur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ff423-180">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="ff423-181">Sie können einen beliebigen Datentyp oder den Namen einer Enumeration, einer Struktur, einer Klasse oder einer Schnittstelle angeben.</span><span class="sxs-lookup"><span data-stu-id="ff423-181">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="ff423-182">Wenn Sie den `returntype`-Parameter nicht angeben, gibt die Prozedur `Object`zurück.</span><span class="sxs-lookup"><span data-stu-id="ff423-182">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>

<span data-ttu-id="ff423-183">Wenn in dieser Prozedur das `Implements`-Schlüsselwort verwendet wird, muss die enthaltende Klasse oder Struktur auch über eine `Implements` Anweisung verfügen, die direkt auf die `Class`-oder `Structure`-Anweisung folgt.</span><span class="sxs-lookup"><span data-stu-id="ff423-183">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="ff423-184">Die `Implements`-Anweisung muss jede in `implementslist`angegebene Schnittstelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="ff423-184">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="ff423-185">Der Name, mit dem eine Schnittstelle die `Function` definiert (in `definedname`), muss jedoch nicht mit dem Namen dieser Prozedur (in `name`) identisch sein.</span><span class="sxs-lookup"><span data-stu-id="ff423-185">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>

> [!NOTE]
> <span data-ttu-id="ff423-186">Sie können Lambda-Ausdrücke verwenden, um Funktions Ausdrücke Inline zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ff423-186">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="ff423-187">Weitere Informationen finden Sie unter [Funktions Ausdruck](../../../visual-basic/language-reference/operators/function-expression.md) und [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ff423-187">For more information, see [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md) and [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>

## <a name="returning-from-a-function"></a><span data-ttu-id="ff423-188">Zurückgeben von einer Funktion</span><span class="sxs-lookup"><span data-stu-id="ff423-188">Returning from a Function</span></span>

<span data-ttu-id="ff423-189">Wenn die `Function` Prozedur an den aufrufenden Code zurückgegeben wird, wird die Ausführung mit der Anweisung fortgesetzt, die der Anweisung folgt, die die Prozedur aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="ff423-189">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>

<span data-ttu-id="ff423-190">Wenn Sie einen Wert aus einer Funktion zurückgeben möchten, können Sie den Wert entweder dem Funktionsnamen zuweisen oder ihn in eine `Return` Anweisung einschließen.</span><span class="sxs-lookup"><span data-stu-id="ff423-190">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>

<span data-ttu-id="ff423-191">Die `Return`-Anweisung weist gleichzeitig den Rückgabewert zu und beendet die Funktion, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff423-191">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

<span data-ttu-id="ff423-192">Im folgenden Beispiel wird der Rückgabewert dem Funktionsnamen `myFunction` zugewiesen und dann die `Exit Function`-Anweisung verwendet, um zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="ff423-192">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

<span data-ttu-id="ff423-193">Die Anweisungen `Exit Function` und `Return` führen zu einem sofortigen Beenden einer `Function` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="ff423-193">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="ff423-194">Eine beliebige Anzahl von `Exit Function`-und `Return` Anweisungen kann an beliebiger Stelle in der Prozedur angezeigt werden, und Sie können `Exit Function`-und `Return`-Anweisungen mischen.</span><span class="sxs-lookup"><span data-stu-id="ff423-194">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>

<span data-ttu-id="ff423-195">Wenn Sie `Exit Function` verwenden, ohne `name`einen Wert zuzuweisen, gibt die Prozedur den Standardwert für den Datentyp zurück, der in `returntype`angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="ff423-195">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="ff423-196">Wenn `returntype` nicht angegeben wird, gibt die Prozedur `Nothing`zurück. Dies ist der Standardwert für `Object`.</span><span class="sxs-lookup"><span data-stu-id="ff423-196">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>

## <a name="calling-a-function"></a><span data-ttu-id="ff423-197">Aufrufen einer Funktion</span><span class="sxs-lookup"><span data-stu-id="ff423-197">Calling a Function</span></span>

<span data-ttu-id="ff423-198">Sie können eine `Function` Prozedur mit dem Prozedur Namen, gefolgt von der Argumentliste in Klammern, in einem Ausdruck aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="ff423-198">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="ff423-199">Sie können die Klammern nur weglassen, wenn Sie keine Argumente angeben.</span><span class="sxs-lookup"><span data-stu-id="ff423-199">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="ff423-200">Der Code ist jedoch besser lesbar, wenn Sie immer die Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="ff423-200">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="ff423-201">Sie können eine `Function` Prozedur auf die gleiche Weise wie eine beliebige Bibliotheksfunktion (z. b. `Sqrt`, `Cos`oder `ChrW`) aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="ff423-201">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>

<span data-ttu-id="ff423-202">Sie können eine Funktion auch mit dem `Call`-Schlüsselwort abrufen.</span><span class="sxs-lookup"><span data-stu-id="ff423-202">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="ff423-203">In diesem Fall wird der Rückgabewert ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ff423-203">In that case, the return value is ignored.</span></span> <span data-ttu-id="ff423-204">Die Verwendung des `Call`-Schlüssel Worts wird in den meisten Fällen nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="ff423-204">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="ff423-205">Weitere Informationen finden Sie unter [callananweisung](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ff423-205">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="ff423-206">Visual Basic ordnet arithmetische Ausdrücke manchmal neu an, um die interne Effizienz zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="ff423-206">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="ff423-207">Aus diesem Grund sollten Sie keine `Function` Prozedur in einem arithmetischen Ausdruck verwenden, wenn die Funktion den Wert von Variablen im gleichen Ausdruck ändert.</span><span class="sxs-lookup"><span data-stu-id="ff423-207">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>

## <a name="async-functions"></a><span data-ttu-id="ff423-208">Async-Funktionen</span><span class="sxs-lookup"><span data-stu-id="ff423-208">Async Functions</span></span>

<span data-ttu-id="ff423-209">Mit der *Async* -Funktion können Sie asynchrone Funktionen aufrufen, ohne explizite Rückrufe verwenden oder den Code manuell über mehrere Funktionen oder Lambda Ausdrücke aufteilen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="ff423-209">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="ff423-210">Wenn Sie eine Funktion mit dem [Async](../../../visual-basic/language-reference/modifiers/async.md) -Modifizierer markieren, können Sie den [Erwartungs Operator in](../../../visual-basic/language-reference/operators/await-operator.md) der Funktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff423-210">If you mark a function with the [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="ff423-211">Wenn die Steuerung einen `Await` Ausdruck in der `Async`-Funktion erreicht, wird die Steuerung an den Aufrufer zurückgegeben, und der Fortschritt in der Funktion wird angehalten, bis die erwartete Aufgabe abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="ff423-211">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="ff423-212">Wenn die Aufgabe vollständig ist, kann die Ausführung in der Funktion fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="ff423-212">When the task is complete, execution can resume in the function.</span></span>

> [!NOTE]
> <span data-ttu-id="ff423-213">Eine `Async` Prozedur wird an den Aufrufer zurückgegeben, wenn Sie entweder auf das erste erwartete Objekt trifft, das noch nicht abgeschlossen ist, oder bis zum Ende der `Async` Prozedur, je nachdem, welcher Wert zuerst auftritt.</span><span class="sxs-lookup"><span data-stu-id="ff423-213">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>

<span data-ttu-id="ff423-214">Eine `Async` Funktion kann den Rückgabetyp <xref:System.Threading.Tasks.Task%601> oder <xref:System.Threading.Tasks.Task>haben.</span><span class="sxs-lookup"><span data-stu-id="ff423-214">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="ff423-215">Im folgenden finden Sie ein Beispiel für eine `Async` Funktion mit dem Rückgabetyp <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="ff423-215">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>

<span data-ttu-id="ff423-216">Eine `Async` Funktion kann keine [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) -Parameter deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ff423-216">An `Async` function cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="ff423-217">Eine [Sub-Anweisung](sub-statement.md) kann auch mit dem `Async`-Modifizierer gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="ff423-217">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="ff423-218">Dies wird hauptsächlich für Ereignishandler verwendet, bei denen kein Wert zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="ff423-218">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="ff423-219">Eine `Async` `Sub` Prozedur kann nicht erwartet werden, und der Aufrufer einer `Async` `Sub` Prozedur kann keine Ausnahmen abfangen, die von der `Sub` Prozedur ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="ff423-219">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>

<span data-ttu-id="ff423-220">Weitere Informationen zu `Async` Funktionen finden Sie unter [asynchrone Programmierung mit Async und warten](../../../visual-basic/programming-guide/concepts/async/index.md), [Ablauf Steuerung in](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)asynchronen Programmen und asynchronen [Rückgabe Typen](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="ff423-220">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="iterator-functions"></a><span data-ttu-id="ff423-221">Iteratorfunktionen</span><span class="sxs-lookup"><span data-stu-id="ff423-221">Iterator Functions</span></span>

<span data-ttu-id="ff423-222">Eine *Iteratorfunktion* führt eine benutzerdefinierte iterierung für eine Auflistung aus, z. b. eine Liste oder ein Array.</span><span class="sxs-lookup"><span data-stu-id="ff423-222">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="ff423-223">Eine Iteratorfunktion verwendet die [Yield](yield-statement.md) -Anweisung, um jedes Element einzeln zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="ff423-223">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="ff423-224">Wenn eine [Yield](yield-statement.md) -Anweisung erreicht wird, wird die aktuelle Position im Code gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ff423-224">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="ff423-225">Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="ff423-225">Execution is restarted from that location the next time the iterator function is called.</span></span>

<span data-ttu-id="ff423-226">Sie verwenden einen Iterator aus dem Client Code, indem Sie eine [for each-... Next](for-each-next-statement.md) -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ff423-226">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>

<span data-ttu-id="ff423-227">Der Rückgabetyp einer Iteratorfunktion kann <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>oder <xref:System.Collections.Generic.IEnumerator%601>sein.</span><span class="sxs-lookup"><span data-stu-id="ff423-227">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="ff423-228">Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="ff423-228">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>

## <a name="example"></a><span data-ttu-id="ff423-229">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff423-229">Example</span></span>

<span data-ttu-id="ff423-230">Im folgenden Beispiel werden die `Function`-Anweisung verwendet, um den Namen, die Parameter und den Code zu deklarieren, die den Hauptteil einer `Function` Prozedur bilden.</span><span class="sxs-lookup"><span data-stu-id="ff423-230">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="ff423-231">Der `ParamArray` Modifizierer ermöglicht der Funktion, eine Variable Anzahl von Argumenten zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="ff423-231">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a><span data-ttu-id="ff423-232">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff423-232">Example</span></span>

<span data-ttu-id="ff423-233">Im folgenden Beispiel wird die Funktion aufgerufen, die im vorherigen Beispiel deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="ff423-233">The following example invokes the function declared in the preceding example.</span></span>

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a><span data-ttu-id="ff423-234">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff423-234">Example</span></span>

<span data-ttu-id="ff423-235">Im folgenden Beispiel ist `DelayAsync` eine `Async` `Function`, die den Rückgabetyp <xref:System.Threading.Tasks.Task%601>hat.</span><span class="sxs-lookup"><span data-stu-id="ff423-235">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="ff423-236">`DelayAsync` enthält eine `Return`-Anweisung, die eine ganze Zahl zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ff423-236">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="ff423-237">Daher muss die Funktionsdeklaration von `DelayAsync` den Rückgabetyp `Task(Of Integer)`haben.</span><span class="sxs-lookup"><span data-stu-id="ff423-237">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="ff423-238">Da der Rückgabetyp `Task(Of Integer)`ist, erzeugt die Auswertung des `Await` Ausdrucks in `DoSomethingAsync` eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="ff423-238">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="ff423-239">Dies wird in dieser Anweisung veranschaulicht: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="ff423-239">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="ff423-240">Das `startButton_Click`-Verfahren ist ein Beispiel für eine `Async Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="ff423-240">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="ff423-241">Da `DoSomethingAsync` eine `Async` Funktion ist, muss die Aufgabe für den `DoSomethingAsync`-aufrufsvorgang erwartet werden, wie die folgende Anweisung veranschaulicht: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="ff423-241">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="ff423-242">Die `startButton_Click` `Sub` Prozedur muss mit dem `Async`-Modifizierer definiert werden, da Sie einen `Await` Ausdruck aufweist.</span><span class="sxs-lookup"><span data-stu-id="ff423-242">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="ff423-243">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff423-243">See also</span></span>

- [<span data-ttu-id="ff423-244">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ff423-244">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="ff423-245">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="ff423-245">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="ff423-246">Parameterliste</span><span class="sxs-lookup"><span data-stu-id="ff423-246">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="ff423-247">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ff423-247">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="ff423-248">Call-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ff423-248">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="ff423-249">Of</span><span class="sxs-lookup"><span data-stu-id="ff423-249">Of</span></span>](of-clause.md)
- [<span data-ttu-id="ff423-250">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="ff423-250">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="ff423-251">Gewusst wie: Verwenden einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="ff423-251">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="ff423-252">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="ff423-252">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="ff423-253">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="ff423-253">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="ff423-254">Function Expression</span><span class="sxs-lookup"><span data-stu-id="ff423-254">Function Expression</span></span>](../../../visual-basic/language-reference/operators/function-expression.md)
