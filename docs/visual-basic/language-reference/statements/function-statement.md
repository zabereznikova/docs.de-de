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
ms.openlocfilehash: 49cf4fead2c5594b7ac6815f82fea0dc995ea436
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404627"
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="683f6-102">Function-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="683f6-102">Function Statement (Visual Basic)</span></span>

<span data-ttu-id="683f6-103">Deklariert den Namen, die Parameter und den Code, die eine `Function` Prozedur definieren.</span><span class="sxs-lookup"><span data-stu-id="683f6-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="683f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="683f6-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a><span data-ttu-id="683f6-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="683f6-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="683f6-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="683f6-106">Optional.</span></span> <span data-ttu-id="683f6-107">Siehe [Attribut Liste](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="683f6-107">See [Attribute List](attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="683f6-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="683f6-108">Optional.</span></span> <span data-ttu-id="683f6-109">Kann eines der folgenden Elemente sein:</span><span class="sxs-lookup"><span data-stu-id="683f6-109">Can be one of the following:</span></span>

  - [<span data-ttu-id="683f6-110">Öffentlich</span><span class="sxs-lookup"><span data-stu-id="683f6-110">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="683f6-111">Gebieten</span><span class="sxs-lookup"><span data-stu-id="683f6-111">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="683f6-112">Kollegen</span><span class="sxs-lookup"><span data-stu-id="683f6-112">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="683f6-113">Privat</span><span class="sxs-lookup"><span data-stu-id="683f6-113">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="683f6-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="683f6-114">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="683f6-115">Privat geschützt</span><span class="sxs-lookup"><span data-stu-id="683f6-115">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="683f6-116">Siehe [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="683f6-116">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="683f6-117">Optional.</span><span class="sxs-lookup"><span data-stu-id="683f6-117">Optional.</span></span> <span data-ttu-id="683f6-118">Kann eines der folgenden Elemente sein:</span><span class="sxs-lookup"><span data-stu-id="683f6-118">Can be one of the following:</span></span>

  - [<span data-ttu-id="683f6-119">Overloads</span><span class="sxs-lookup"><span data-stu-id="683f6-119">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="683f6-120">Überschreibt</span><span class="sxs-lookup"><span data-stu-id="683f6-120">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="683f6-121">Overrides</span><span class="sxs-lookup"><span data-stu-id="683f6-121">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="683f6-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="683f6-122">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="683f6-123">MustOverride</span><span class="sxs-lookup"><span data-stu-id="683f6-123">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="683f6-124">Optional.</span><span class="sxs-lookup"><span data-stu-id="683f6-124">Optional.</span></span> <span data-ttu-id="683f6-125">Siehe [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="683f6-125">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="683f6-126">Optional.</span><span class="sxs-lookup"><span data-stu-id="683f6-126">Optional.</span></span> <span data-ttu-id="683f6-127">Siehe [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="683f6-127">See [Shadows](../modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="683f6-128">Optional.</span><span class="sxs-lookup"><span data-stu-id="683f6-128">Optional.</span></span> <span data-ttu-id="683f6-129">Siehe [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="683f6-129">See [Async](../modifiers/async.md).</span></span>

- `Iterator`

  <span data-ttu-id="683f6-130">Optional.</span><span class="sxs-lookup"><span data-stu-id="683f6-130">Optional.</span></span> <span data-ttu-id="683f6-131">Siehe [Iterator](../modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="683f6-131">See [Iterator](../modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="683f6-132">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="683f6-132">Required.</span></span> <span data-ttu-id="683f6-133">Der Name der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="683f6-133">Name of the procedure.</span></span> <span data-ttu-id="683f6-134">Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="683f6-134">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="683f6-135">Optional.</span><span class="sxs-lookup"><span data-stu-id="683f6-135">Optional.</span></span> <span data-ttu-id="683f6-136">Liste der Typparameter für eine generische Prozedur.</span><span class="sxs-lookup"><span data-stu-id="683f6-136">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="683f6-137">Siehe [Typliste](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="683f6-137">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="683f6-138">Optional.</span><span class="sxs-lookup"><span data-stu-id="683f6-138">Optional.</span></span> <span data-ttu-id="683f6-139">Liste der Namen der lokalen Variablen, die die Parameter dieser Prozedur darstellen.</span><span class="sxs-lookup"><span data-stu-id="683f6-139">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="683f6-140">Siehe [Parameter Liste](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="683f6-140">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="683f6-141">Erforderlich, wenn `Option Strict` ist `On` .</span><span class="sxs-lookup"><span data-stu-id="683f6-141">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="683f6-142">Datentyp des Werts, der von dieser Prozedur zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="683f6-142">Data type of the value returned by this procedure.</span></span>

- `Implements`

  <span data-ttu-id="683f6-143">Optional.</span><span class="sxs-lookup"><span data-stu-id="683f6-143">Optional.</span></span> <span data-ttu-id="683f6-144">Gibt an, dass diese Prozedur eine oder mehrere `Function` Prozeduren implementiert, die in einer Schnittstelle definiert sind, die von der enthaltenden Klasse oder Struktur dieser Prozedur implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="683f6-144">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="683f6-145">Siehe [implementierende Anweisung](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="683f6-145">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="683f6-146">Erforderlich, wenn `Implements` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="683f6-146">Required if `Implements` is supplied.</span></span> <span data-ttu-id="683f6-147">Liste der zu implementierenden `Function`-Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="683f6-147">List of `Function` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="683f6-148">Jede `implementedprocedure` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="683f6-148">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="683f6-149">Teil</span><span class="sxs-lookup"><span data-stu-id="683f6-149">Part</span></span>|<span data-ttu-id="683f6-150">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="683f6-150">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="683f6-151">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="683f6-151">Required.</span></span> <span data-ttu-id="683f6-152">Der Name einer Schnittstelle, die von der enthaltenden Klasse oder Struktur dieser Prozedur implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="683f6-152">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="683f6-153">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="683f6-153">Required.</span></span> <span data-ttu-id="683f6-154">Name, wodurch die Prozedur in `interface` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="683f6-154">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="683f6-155">Optional.</span><span class="sxs-lookup"><span data-stu-id="683f6-155">Optional.</span></span> <span data-ttu-id="683f6-156">Gibt an, dass diese Prozedur ein oder mehrere bestimmte Ereignisse verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="683f6-156">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="683f6-157">Siehe [Handles](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="683f6-157">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="683f6-158">Erforderlich, wenn `Handles` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="683f6-158">Required if `Handles` is supplied.</span></span> <span data-ttu-id="683f6-159">Die Liste der Ereignisse, die von dieser Prozedur behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="683f6-159">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="683f6-160">Jede `eventspecifier` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="683f6-160">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="683f6-161">Teil</span><span class="sxs-lookup"><span data-stu-id="683f6-161">Part</span></span>|<span data-ttu-id="683f6-162">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="683f6-162">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="683f6-163">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="683f6-163">Required.</span></span> <span data-ttu-id="683f6-164">Objekt Variable, die mit dem Datentyp der Klasse oder Struktur deklariert wurde, die das Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="683f6-164">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="683f6-165">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="683f6-165">Required.</span></span> <span data-ttu-id="683f6-166">Der Name des Ereignisses, das diese Prozedur behandelt.</span><span class="sxs-lookup"><span data-stu-id="683f6-166">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="683f6-167">Optional.</span><span class="sxs-lookup"><span data-stu-id="683f6-167">Optional.</span></span> <span data-ttu-id="683f6-168">Block von-Anweisungen, die innerhalb dieser Prozedur ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="683f6-168">Block of statements to be executed within this procedure.</span></span>

- `End Function`

  <span data-ttu-id="683f6-169">Beendet die Definition dieser Prozedur.</span><span class="sxs-lookup"><span data-stu-id="683f6-169">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="683f6-170">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="683f6-170">Remarks</span></span>

<span data-ttu-id="683f6-171">Der gesamte ausführbare Code muss sich in einer Prozedur befinden.</span><span class="sxs-lookup"><span data-stu-id="683f6-171">All executable code must be inside a procedure.</span></span> <span data-ttu-id="683f6-172">Die einzelnen Prozeduren werden wiederum innerhalb einer Klasse, einer Struktur oder eines Moduls deklariert, das als enthaltende Klasse, Struktur oder Modul bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="683f6-172">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>

<span data-ttu-id="683f6-173">Um einen Wert an den aufrufenden Code zurückzugeben, verwenden Sie eine- `Function` Prozedur; andernfalls verwenden Sie eine- `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="683f6-173">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>

## <a name="defining-a-function"></a><span data-ttu-id="683f6-174">Definieren einer Funktion</span><span class="sxs-lookup"><span data-stu-id="683f6-174">Defining a Function</span></span>

<span data-ttu-id="683f6-175">Sie können eine `Function` Prozedur nur auf Modulebene definieren.</span><span class="sxs-lookup"><span data-stu-id="683f6-175">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="683f6-176">Daher muss der Deklarations Kontext für eine Funktion eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein, und es kann sich nicht um eine Quelldatei, einen Namespace, eine Prozedur oder einen Block handeln.</span><span class="sxs-lookup"><span data-stu-id="683f6-176">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="683f6-177">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="683f6-177">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="683f6-178">`Function`Prozeduren werden standardmäßig öffentlich zugänglich.</span><span class="sxs-lookup"><span data-stu-id="683f6-178">`Function` procedures default to public access.</span></span> <span data-ttu-id="683f6-179">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="683f6-179">You can adjust their access levels with the access modifiers.</span></span>

<span data-ttu-id="683f6-180">Eine `Function` Prozedur kann den Datentyp des Werts deklarieren, den die Prozedur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="683f6-180">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="683f6-181">Sie können einen beliebigen Datentyp oder den Namen einer Enumeration, einer Struktur, einer Klasse oder einer Schnittstelle angeben.</span><span class="sxs-lookup"><span data-stu-id="683f6-181">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="683f6-182">Wenn Sie den-Parameter nicht angeben `returntype` , gibt die Prozedur zurück `Object` .</span><span class="sxs-lookup"><span data-stu-id="683f6-182">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>

<span data-ttu-id="683f6-183">Wenn diese Prozedur das `Implements` Schlüsselwort verwendet, muss die enthaltende Klasse oder Struktur auch über eine- `Implements` Anweisung verfügen, die direkt auf die- `Class` oder-Anweisung folgt `Structure` .</span><span class="sxs-lookup"><span data-stu-id="683f6-183">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="683f6-184">Die `Implements` -Anweisung muss jede Schnittstelle enthalten, die in angegeben ist `implementslist` .</span><span class="sxs-lookup"><span data-stu-id="683f6-184">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="683f6-185">Der Name, mit dem eine Schnittstelle `Function` (in) definiert, `definedname` muss jedoch nicht mit dem Namen dieser Prozedur (in `name` ) identisch sein.</span><span class="sxs-lookup"><span data-stu-id="683f6-185">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>

> [!NOTE]
> <span data-ttu-id="683f6-186">Sie können Lambda-Ausdrücke verwenden, um Funktions Ausdrücke Inline zu definieren.</span><span class="sxs-lookup"><span data-stu-id="683f6-186">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="683f6-187">Weitere Informationen finden Sie unter [Funktions Ausdruck](../operators/function-expression.md) und [Lambda-Ausdrücke](../../programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="683f6-187">For more information, see [Function Expression](../operators/function-expression.md) and [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>

## <a name="returning-from-a-function"></a><span data-ttu-id="683f6-188">Zurückgeben von einer Funktion</span><span class="sxs-lookup"><span data-stu-id="683f6-188">Returning from a Function</span></span>

<span data-ttu-id="683f6-189">Wenn die `Function` Prozedur an den aufrufenden Code zurückgegeben wird, wird die Ausführung mit der Anweisung fortgesetzt, die der Anweisung folgt, die die Prozedur aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="683f6-189">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>

<span data-ttu-id="683f6-190">Wenn Sie einen Wert aus einer Funktion zurückgeben möchten, können Sie den Wert entweder dem Funktionsnamen zuweisen oder ihn in eine- `Return` Anweisung einschließen.</span><span class="sxs-lookup"><span data-stu-id="683f6-190">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>

<span data-ttu-id="683f6-191">Die `Return` -Anweisung weist den Rückgabewert gleichzeitig zu und beendet die-Funktion, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="683f6-191">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

<span data-ttu-id="683f6-192">Im folgenden Beispiel wird der Rückgabewert dem Funktionsnamen zugewiesen, `myFunction` und anschließend wird die- `Exit Function` Anweisung verwendet, um zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="683f6-192">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

<span data-ttu-id="683f6-193">Die `Exit Function` -und- `Return` Anweisungen verursachen einen sofortigen Abbruch einer `Function` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="683f6-193">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="683f6-194">Eine beliebige Anzahl von `Exit Function` -und- `Return` Anweisungen kann an beliebiger Stelle in der Prozedur angezeigt werden, und Sie können die `Exit Function` -und- `Return` Anweisungen</span><span class="sxs-lookup"><span data-stu-id="683f6-194">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>

<span data-ttu-id="683f6-195">Wenn Sie verwenden `Exit Function` , ohne einen Wert zuzuweisen `name` , gibt die Prozedur den Standardwert für den Datentyp zurück, der in angegeben ist `returntype` .</span><span class="sxs-lookup"><span data-stu-id="683f6-195">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="683f6-196">Wenn `returntype` nicht angegeben wird, gibt die Prozedur zurück `Nothing` . Dies ist der Standardwert für `Object` .</span><span class="sxs-lookup"><span data-stu-id="683f6-196">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>

## <a name="calling-a-function"></a><span data-ttu-id="683f6-197">Aufrufen einer Funktion</span><span class="sxs-lookup"><span data-stu-id="683f6-197">Calling a Function</span></span>

<span data-ttu-id="683f6-198">Sie können eine `Function` Prozedur mit dem Prozedur Namen, gefolgt von der Argumentliste in Klammern, in einem Ausdruck aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="683f6-198">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="683f6-199">Sie können die Klammern nur weglassen, wenn Sie keine Argumente angeben.</span><span class="sxs-lookup"><span data-stu-id="683f6-199">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="683f6-200">Der Code ist jedoch besser lesbar, wenn Sie immer die Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="683f6-200">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="683f6-201">Sie können eine `Function` Prozedur auf dieselbe Weise wie eine beliebige Bibliotheksfunktion (z `Sqrt` . b `Cos` ., oder) aufzurufen `ChrW` .</span><span class="sxs-lookup"><span data-stu-id="683f6-201">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>

<span data-ttu-id="683f6-202">Sie können eine Funktion auch mit dem- `Call` Schlüsselwort abrufen.</span><span class="sxs-lookup"><span data-stu-id="683f6-202">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="683f6-203">In diesem Fall wird der Rückgabewert ignoriert.</span><span class="sxs-lookup"><span data-stu-id="683f6-203">In that case, the return value is ignored.</span></span> <span data-ttu-id="683f6-204">Die Verwendung des- `Call` Schlüssel Worts ist in den meisten Fällen nicht empfehlenswert.</span><span class="sxs-lookup"><span data-stu-id="683f6-204">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="683f6-205">Weitere Informationen finden Sie unter [callananweisung](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="683f6-205">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="683f6-206">Visual Basic ordnet arithmetische Ausdrücke manchmal neu an, um die interne Effizienz zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="683f6-206">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="683f6-207">Aus diesem Grund sollten Sie keine `Function` Prozedur in einem arithmetischen Ausdruck verwenden, wenn die Funktion den Wert von Variablen im gleichen Ausdruck ändert.</span><span class="sxs-lookup"><span data-stu-id="683f6-207">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>

## <a name="async-functions"></a><span data-ttu-id="683f6-208">Async-Funktionen</span><span class="sxs-lookup"><span data-stu-id="683f6-208">Async Functions</span></span>

<span data-ttu-id="683f6-209">Mit der *Async* -Funktion können Sie asynchrone Funktionen aufrufen, ohne explizite Rückrufe verwenden oder den Code manuell über mehrere Funktionen oder Lambda Ausdrücke aufteilen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="683f6-209">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="683f6-210">Wenn Sie eine Funktion mit dem [Async](../modifiers/async.md) -Modifizierer markieren, können Sie den [Erwartungs Operator in](../operators/await-operator.md) der Funktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="683f6-210">If you mark a function with the [Async](../modifiers/async.md) modifier, you can use the [Await](../operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="683f6-211">Wenn das Steuerelement einen `Await` Ausdruck in der `Async` Funktion erreicht, wird die Steuerung an den Aufrufer zurückgegeben, und der Status der Funktion wird angehalten, bis die erwartete Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="683f6-211">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="683f6-212">Wenn die Aufgabe vollständig ist, kann die Ausführung in der Funktion fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="683f6-212">When the task is complete, execution can resume in the function.</span></span>

> [!NOTE]
> <span data-ttu-id="683f6-213">Eine `Async` Prozedur wird an den Aufrufer zurückgegeben, wenn Sie entweder auf das erste erwartete Objekt trifft, das noch nicht abgeschlossen ist, oder bis zum Ende der `Async` Prozedur, je nachdem, welcher Wert zuerst auftritt.</span><span class="sxs-lookup"><span data-stu-id="683f6-213">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>

<span data-ttu-id="683f6-214">Eine `Async` Funktion kann den Rückgabetyp <xref:System.Threading.Tasks.Task%601> oder aufweisen <xref:System.Threading.Tasks.Task> .</span><span class="sxs-lookup"><span data-stu-id="683f6-214">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="683f6-215">Ein Beispiel für eine `Async` Funktion mit dem Rückgabetyp <xref:System.Threading.Tasks.Task%601> wird unten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="683f6-215">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>

<span data-ttu-id="683f6-216">Eine `Async` Funktion kann keine [ByRef](../modifiers/byref.md) -Parameter deklarieren.</span><span class="sxs-lookup"><span data-stu-id="683f6-216">An `Async` function cannot declare any [ByRef](../modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="683f6-217">Eine [Sub-Anweisung](sub-statement.md) kann auch mit dem- `Async` Modifizierer gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="683f6-217">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="683f6-218">Dies wird hauptsächlich für Ereignishandler verwendet, bei denen kein Wert zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="683f6-218">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="683f6-219">Eine `Async` `Sub` Prozedur kann nicht erwartet werden, und der Aufrufer einer `Async` `Sub` Prozedur kann keine Ausnahmen abfangen, die von der Prozedur ausgelöst werden `Sub` .</span><span class="sxs-lookup"><span data-stu-id="683f6-219">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>

<span data-ttu-id="683f6-220">Weitere Informationen zu `Async` -Funktionen finden Sie [unter asynchrone Programmierung mit Async und warten](../../programming-guide/concepts/async/index.md), [Ablauf Steuerung in](../../programming-guide/concepts/async/control-flow-in-async-programs.md)asynchronen Programmen und [Async-Rückgabe Typen](../../programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="683f6-220">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="iterator-functions"></a><span data-ttu-id="683f6-221">Iteratorfunktionen</span><span class="sxs-lookup"><span data-stu-id="683f6-221">Iterator Functions</span></span>

<span data-ttu-id="683f6-222">Eine *Iteratorfunktion* führt eine benutzerdefinierte iterierung für eine Auflistung aus, z. b. eine Liste oder ein Array.</span><span class="sxs-lookup"><span data-stu-id="683f6-222">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="683f6-223">Eine Iteratorfunktion verwendet die [Yield](yield-statement.md) -Anweisung, um jedes Element einzeln zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="683f6-223">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="683f6-224">Wenn eine [Yield](yield-statement.md) -Anweisung erreicht wird, wird die aktuelle Position im Code gespeichert.</span><span class="sxs-lookup"><span data-stu-id="683f6-224">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="683f6-225">Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="683f6-225">Execution is restarted from that location the next time the iterator function is called.</span></span>

<span data-ttu-id="683f6-226">Sie verwenden einen Iterator aus dem Client Code, indem Sie eine [for each-... Next](for-each-next-statement.md) -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="683f6-226">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>

<span data-ttu-id="683f6-227">Der Rückgabetyp einer Iteratorfunktion kann <xref:System.Collections.IEnumerable> , <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Collections.IEnumerator> oder sein <xref:System.Collections.Generic.IEnumerator%601> .</span><span class="sxs-lookup"><span data-stu-id="683f6-227">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="683f6-228">Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="683f6-228">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>

## <a name="example"></a><span data-ttu-id="683f6-229">Beispiel</span><span class="sxs-lookup"><span data-stu-id="683f6-229">Example</span></span>

<span data-ttu-id="683f6-230">Im folgenden Beispiel wird die- `Function` Anweisung verwendet, um den Namen, die Parameter und den Code, die den Text einer Prozedur bilden, zu deklarieren `Function` .</span><span class="sxs-lookup"><span data-stu-id="683f6-230">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="683f6-231">Der- `ParamArray` Modifizierer ermöglicht der-Funktion, eine Variable Anzahl von Argumenten zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="683f6-231">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a><span data-ttu-id="683f6-232">Beispiel</span><span class="sxs-lookup"><span data-stu-id="683f6-232">Example</span></span>

<span data-ttu-id="683f6-233">Im folgenden Beispiel wird die Funktion aufgerufen, die im vorherigen Beispiel deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="683f6-233">The following example invokes the function declared in the preceding example.</span></span>

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a><span data-ttu-id="683f6-234">Beispiel</span><span class="sxs-lookup"><span data-stu-id="683f6-234">Example</span></span>

<span data-ttu-id="683f6-235">Im folgenden Beispiel ist ein-Wert, `DelayAsync` `Async` `Function` der den Rückgabetyp aufweist <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="683f6-235">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="683f6-236">`DelayAsync` enthält eine `Return` -Anweisung, die eine ganze Zahl zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="683f6-236">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="683f6-237">Daher muss die Funktionsdeklaration von den `DelayAsync` Rückgabetyp aufweisen `Task(Of Integer)` .</span><span class="sxs-lookup"><span data-stu-id="683f6-237">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="683f6-238">Da der Rückgabetyp ist `Task(Of Integer)` , erzeugt die Auswertung des `Await` Ausdrucks in `DoSomethingAsync` eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="683f6-238">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="683f6-239">Dies wird in dieser-Anweisung veranschaulicht: `Dim result As Integer = Await delayTask` .</span><span class="sxs-lookup"><span data-stu-id="683f6-239">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="683f6-240">Das `startButton_Click` Verfahren ist ein Beispiel für eine `Async Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="683f6-240">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="683f6-241">Da `DoSomethingAsync` eine `Async` Funktion ist, muss die Aufgabe für den-Aufrufvorgang `DoSomethingAsync` erwartet werden, wie die folgende Anweisung veranschaulicht: `Await DoSomethingAsync()` .</span><span class="sxs-lookup"><span data-stu-id="683f6-241">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="683f6-242">Die `startButton_Click` `Sub` Prozedur muss mit dem- `Async` Modifizierer definiert werden, da Sie über einen `Await` Ausdruck verfügt.</span><span class="sxs-lookup"><span data-stu-id="683f6-242">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="683f6-243">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="683f6-243">See also</span></span>

- [<span data-ttu-id="683f6-244">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="683f6-244">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="683f6-245">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="683f6-245">Function Procedures</span></span>](../../programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="683f6-246">Parameterliste</span><span class="sxs-lookup"><span data-stu-id="683f6-246">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="683f6-247">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="683f6-247">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="683f6-248">Call-Anweisung</span><span class="sxs-lookup"><span data-stu-id="683f6-248">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="683f6-249">Natürlich</span><span class="sxs-lookup"><span data-stu-id="683f6-249">Of</span></span>](of-clause.md)
- [<span data-ttu-id="683f6-250">Parameter Arrays</span><span class="sxs-lookup"><span data-stu-id="683f6-250">Parameter Arrays</span></span>](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="683f6-251">Vorgehensweise: Verwenden einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="683f6-251">How to: Use a Generic Class</span></span>](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="683f6-252">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="683f6-252">Troubleshooting Procedures</span></span>](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="683f6-253">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="683f6-253">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="683f6-254">Funktions Ausdruck</span><span class="sxs-lookup"><span data-stu-id="683f6-254">Function Expression</span></span>](../operators/function-expression.md)
