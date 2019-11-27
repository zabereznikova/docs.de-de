---
title: Sub-Anweisung
ms.date: 05/12/2018
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
ms.openlocfilehash: da498a5e0a3633eb98882aaed145fcd21ab169fd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346441"
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="eda1f-102">Sub-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eda1f-102">Sub Statement (Visual Basic)</span></span>

<span data-ttu-id="eda1f-103">Deklariert den Namen, die Parameter und den Code, die eine `Sub` Prozedur definieren.</span><span class="sxs-lookup"><span data-stu-id="eda1f-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="eda1f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eda1f-104">Syntax</span></span>

```vb
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a><span data-ttu-id="eda1f-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="eda1f-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="eda1f-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="eda1f-106">Optional.</span></span> <span data-ttu-id="eda1f-107">Siehe [Attribut Liste](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="eda1f-107">See [Attribute List](attribute-list.md).</span></span>

- `Partial`

  <span data-ttu-id="eda1f-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="eda1f-108">Optional.</span></span> <span data-ttu-id="eda1f-109">Gibt die Definition einer partiellen Methode an.</span><span class="sxs-lookup"><span data-stu-id="eda1f-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="eda1f-110">Siehe [partielle Methoden](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="eda1f-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="eda1f-111">Optional.</span><span class="sxs-lookup"><span data-stu-id="eda1f-111">Optional.</span></span> <span data-ttu-id="eda1f-112">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="eda1f-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="eda1f-113">Public</span><span class="sxs-lookup"><span data-stu-id="eda1f-113">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="eda1f-114">Protected</span><span class="sxs-lookup"><span data-stu-id="eda1f-114">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="eda1f-115">Friend</span><span class="sxs-lookup"><span data-stu-id="eda1f-115">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="eda1f-116">Private</span><span class="sxs-lookup"><span data-stu-id="eda1f-116">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="eda1f-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="eda1f-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="eda1f-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="eda1f-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="eda1f-119">Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="eda1f-119">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="eda1f-120">Optional.</span><span class="sxs-lookup"><span data-stu-id="eda1f-120">Optional.</span></span> <span data-ttu-id="eda1f-121">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="eda1f-121">Can be one of the following:</span></span>

  - [<span data-ttu-id="eda1f-122">Overloads</span><span class="sxs-lookup"><span data-stu-id="eda1f-122">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="eda1f-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="eda1f-123">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="eda1f-124">Overrides</span><span class="sxs-lookup"><span data-stu-id="eda1f-124">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="eda1f-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="eda1f-125">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="eda1f-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="eda1f-126">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="eda1f-127">Optional.</span><span class="sxs-lookup"><span data-stu-id="eda1f-127">Optional.</span></span> <span data-ttu-id="eda1f-128">Siehe [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="eda1f-128">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="eda1f-129">Optional.</span><span class="sxs-lookup"><span data-stu-id="eda1f-129">Optional.</span></span> <span data-ttu-id="eda1f-130">Siehe [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="eda1f-130">See [Shadows](../modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="eda1f-131">Optional.</span><span class="sxs-lookup"><span data-stu-id="eda1f-131">Optional.</span></span> <span data-ttu-id="eda1f-132">Siehe [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="eda1f-132">See [Async](../modifiers/async.md).</span></span>

- `name`

  <span data-ttu-id="eda1f-133">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="eda1f-133">Required.</span></span> <span data-ttu-id="eda1f-134">Der Name der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="eda1f-134">Name of the procedure.</span></span> <span data-ttu-id="eda1f-135">Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="eda1f-135">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="eda1f-136">Wenn Sie eine konstruktorprozedur für eine Klasse erstellen möchten, legen Sie den Namen einer `Sub` Prozedur auf das `New`-Schlüsselwort fest.</span><span class="sxs-lookup"><span data-stu-id="eda1f-136">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="eda1f-137">Weitere Informationen finden Sie unter [Objekt Lebensdauer: Erstellen und zerstören von Objekten](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="eda1f-137">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="eda1f-138">Optional.</span><span class="sxs-lookup"><span data-stu-id="eda1f-138">Optional.</span></span> <span data-ttu-id="eda1f-139">Liste der Typparameter für eine generische Prozedur.</span><span class="sxs-lookup"><span data-stu-id="eda1f-139">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="eda1f-140">Siehe [Typliste](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="eda1f-140">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="eda1f-141">Optional.</span><span class="sxs-lookup"><span data-stu-id="eda1f-141">Optional.</span></span> <span data-ttu-id="eda1f-142">Liste der Namen der lokalen Variablen, die die Parameter dieser Prozedur darstellen.</span><span class="sxs-lookup"><span data-stu-id="eda1f-142">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="eda1f-143">Siehe [Parameter Liste](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="eda1f-143">See [Parameter List](parameter-list.md).</span></span>

- `Implements`

  <span data-ttu-id="eda1f-144">Optional.</span><span class="sxs-lookup"><span data-stu-id="eda1f-144">Optional.</span></span> <span data-ttu-id="eda1f-145">Gibt an, dass diese Prozedur mindestens eine `Sub` Prozeduren implementiert, die in einer Schnittstelle definiert sind, die von der enthaltenden Klasse oder Struktur dieser Prozedur implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="eda1f-145">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="eda1f-146">Siehe [implementierende Anweisung](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="eda1f-146">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="eda1f-147">Erforderlich, wenn `Implements` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="eda1f-147">Required if `Implements` is supplied.</span></span> <span data-ttu-id="eda1f-148">Liste der zu implementierenden `Sub`-Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="eda1f-148">List of `Sub` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="eda1f-149">Jede `implementedprocedure` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="eda1f-149">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="eda1f-150">-Komponente</span><span class="sxs-lookup"><span data-stu-id="eda1f-150">Part</span></span>|<span data-ttu-id="eda1f-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eda1f-151">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="eda1f-152">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="eda1f-152">Required.</span></span> <span data-ttu-id="eda1f-153">Der Name einer Schnittstelle, die von der enthaltenden Klasse oder Struktur dieser Prozedur implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="eda1f-153">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="eda1f-154">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="eda1f-154">Required.</span></span> <span data-ttu-id="eda1f-155">Name, wodurch die Prozedur in `interface` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="eda1f-155">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="eda1f-156">Optional.</span><span class="sxs-lookup"><span data-stu-id="eda1f-156">Optional.</span></span> <span data-ttu-id="eda1f-157">Gibt an, dass diese Prozedur ein oder mehrere bestimmte Ereignisse verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="eda1f-157">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="eda1f-158">Siehe [Handles](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="eda1f-158">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="eda1f-159">Erforderlich, wenn `Handles` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="eda1f-159">Required if `Handles` is supplied.</span></span> <span data-ttu-id="eda1f-160">Die Liste der Ereignisse, die von dieser Prozedur behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="eda1f-160">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="eda1f-161">Jede `eventspecifier` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="eda1f-161">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="eda1f-162">-Komponente</span><span class="sxs-lookup"><span data-stu-id="eda1f-162">Part</span></span>|<span data-ttu-id="eda1f-163">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eda1f-163">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="eda1f-164">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="eda1f-164">Required.</span></span> <span data-ttu-id="eda1f-165">Objekt Variable, die mit dem Datentyp der Klasse oder Struktur deklariert wurde, die das Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="eda1f-165">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="eda1f-166">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="eda1f-166">Required.</span></span> <span data-ttu-id="eda1f-167">Der Name des Ereignisses, das diese Prozedur behandelt.</span><span class="sxs-lookup"><span data-stu-id="eda1f-167">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="eda1f-168">Optional.</span><span class="sxs-lookup"><span data-stu-id="eda1f-168">Optional.</span></span> <span data-ttu-id="eda1f-169">Block von-Anweisungen, die in dieser Prozedur ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="eda1f-169">Block of statements to run within this procedure.</span></span>

- `End Sub`

  <span data-ttu-id="eda1f-170">Beendet die Definition dieser Prozedur.</span><span class="sxs-lookup"><span data-stu-id="eda1f-170">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="eda1f-171">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eda1f-171">Remarks</span></span>

<span data-ttu-id="eda1f-172">Der gesamte ausführbare Code muss sich in einer Prozedur befinden.</span><span class="sxs-lookup"><span data-stu-id="eda1f-172">All executable code must be inside a procedure.</span></span> <span data-ttu-id="eda1f-173">Verwenden Sie eine `Sub` Prozedur, wenn Sie keinen Wert an den aufrufenden Code zurückgeben möchten.</span><span class="sxs-lookup"><span data-stu-id="eda1f-173">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="eda1f-174">Verwenden Sie eine `Function` Prozedur, wenn Sie einen Wert zurückgeben möchten.</span><span class="sxs-lookup"><span data-stu-id="eda1f-174">Use a `Function` procedure when you want to return a value.</span></span>

## <a name="defining-a-sub-procedure"></a><span data-ttu-id="eda1f-175">Definieren einer unter Prozedur</span><span class="sxs-lookup"><span data-stu-id="eda1f-175">Defining a Sub Procedure</span></span>

<span data-ttu-id="eda1f-176">Sie können eine `Sub` Prozedur nur auf Modulebene definieren.</span><span class="sxs-lookup"><span data-stu-id="eda1f-176">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="eda1f-177">Der Deklarations Kontext für eine unter Prozedur muss daher eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein, und es darf sich nicht um eine Quelldatei, einen Namespace, eine Prozedur oder einen Block handeln.</span><span class="sxs-lookup"><span data-stu-id="eda1f-177">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="eda1f-178">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="eda1f-178">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="eda1f-179">`Sub` Prozeduren werden standardmäßig öffentlich zugänglich.</span><span class="sxs-lookup"><span data-stu-id="eda1f-179">`Sub` procedures default to public access.</span></span> <span data-ttu-id="eda1f-180">Sie können Ihre Zugriffsebenen anpassen, indem Sie die Zugriffsmodifizierer verwenden.</span><span class="sxs-lookup"><span data-stu-id="eda1f-180">You can adjust their access levels by using the access modifiers.</span></span>

<span data-ttu-id="eda1f-181">Wenn die Prozedur das `Implements`-Schlüsselwort verwendet, muss die enthaltende Klasse oder Struktur über eine `Implements` Anweisung verfügen, die direkt auf die `Class`-oder `Structure`-Anweisung folgt.</span><span class="sxs-lookup"><span data-stu-id="eda1f-181">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="eda1f-182">Die `Implements`-Anweisung muss jede in `implementslist`angegebene Schnittstelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="eda1f-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="eda1f-183">Der Name, mit dem eine Schnittstelle die `Sub` definiert (in `definedname`), muss jedoch nicht mit dem Namen dieser Prozedur (in `name`) identisch sein.</span><span class="sxs-lookup"><span data-stu-id="eda1f-183">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>

## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="eda1f-184">Zurückgeben aus einer unter Prozedur</span><span class="sxs-lookup"><span data-stu-id="eda1f-184">Returning from a Sub Procedure</span></span>

<span data-ttu-id="eda1f-185">Wenn eine `Sub` Prozedur an den aufrufenden Code zurückgegeben wird, wird die Ausführung mit der Anweisung nach der Anweisung fortgesetzt, die Sie aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="eda1f-185">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>

<span data-ttu-id="eda1f-186">Das folgende Beispiel zeigt eine Rückgabe einer `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="eda1f-186">The following example shows a return from a `Sub` procedure.</span></span>

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

<span data-ttu-id="eda1f-187">Die Anweisungen `Exit Sub` und `Return` führen zu einem sofortigen Beenden einer `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="eda1f-187">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="eda1f-188">Eine beliebige Anzahl von `Exit Sub`-und `Return` Anweisungen kann an beliebiger Stelle in der Prozedur angezeigt werden, und Sie können `Exit Sub`-und `Return`-Anweisungen mischen.</span><span class="sxs-lookup"><span data-stu-id="eda1f-188">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>

## <a name="calling-a-sub-procedure"></a><span data-ttu-id="eda1f-189">Aufrufen einer unter Prozedur</span><span class="sxs-lookup"><span data-stu-id="eda1f-189">Calling a Sub Procedure</span></span>

<span data-ttu-id="eda1f-190">Sie führen eine `Sub` Prozedur aus, indem Sie den Prozedur Namen in einer-Anweisung verwenden und dann den Namen mit seiner Argumentliste in Klammern befolgen.</span><span class="sxs-lookup"><span data-stu-id="eda1f-190">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="eda1f-191">Sie können die Klammern nur weglassen, wenn Sie keine Argumente angeben.</span><span class="sxs-lookup"><span data-stu-id="eda1f-191">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="eda1f-192">Der Code ist jedoch besser lesbar, wenn Sie immer die Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="eda1f-192">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="eda1f-193">Eine `Sub` Prozedur und eine `Function` Prozedur können über Parameter verfügen und eine Reihe von-Anweisungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="eda1f-193">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="eda1f-194">Eine `Function` Prozedur gibt jedoch einen Wert zurück, und eine `Sub` Prozedur ist nicht.</span><span class="sxs-lookup"><span data-stu-id="eda1f-194">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="eda1f-195">Daher können Sie keine `Sub` Prozedur in einem Ausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="eda1f-195">Therefore, you can't use a `Sub` procedure in an expression.</span></span>

<span data-ttu-id="eda1f-196">Sie können das `Call`-Schlüsselwort verwenden, wenn Sie eine `Sub` Prozedur aufzurufen, aber dieses Schlüsselwort wird für die meisten Verwendungen nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="eda1f-196">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="eda1f-197">Weitere Informationen finden Sie unter [callananweisung](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="eda1f-197">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="eda1f-198">Visual Basic ordnet arithmetische Ausdrücke manchmal neu an, um die interne Effizienz zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="eda1f-198">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="eda1f-199">Wenn Ihre Argumentliste Ausdrücke enthält, die andere Prozeduren aufrufen, sollten Sie daher nicht davon ausgehen, dass diese Ausdrücke in einer bestimmten Reihenfolge aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="eda1f-199">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>

## <a name="async-sub-procedures"></a><span data-ttu-id="eda1f-200">Async-unter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="eda1f-200">Async Sub Procedures</span></span>

<span data-ttu-id="eda1f-201">Mithilfe der Async-Funktion können Sie asynchrone Funktionen aufrufen, ohne explizite Rückrufe zu verwenden oder den Code manuell über mehrere Funktionen oder Lambda-Ausdrücke aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="eda1f-201">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="eda1f-202">Wenn Sie eine Prozedur mit dem [Async](../modifiers/async.md) -Modifizierer markieren, können Sie den [Erwartungs Operator in](../../../visual-basic/language-reference/operators/await-operator.md) der Prozedur verwenden.</span><span class="sxs-lookup"><span data-stu-id="eda1f-202">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="eda1f-203">Wenn das Steuerelement einen `Await` Ausdruck in der `Async` Prozedur erreicht, wird die Steuerung an den Aufrufer zurückgegeben, und der Status der Prozedur wird angehalten, bis die erwartete Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="eda1f-203">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="eda1f-204">Wenn die Aufgabe vollständig ist, kann die Ausführung in der Prozedur fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="eda1f-204">When the task is complete, execution can resume in the procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="eda1f-205">Eine `Async` Prozedur wird an den Aufrufer zurückgegeben, wenn entweder das erste erwartete Objekt, das noch nicht abgeschlossen ist, gefunden wird oder das Ende der `Async` Prozedur erreicht wird, je nachdem, welcher Wert zuerst auftritt.</span><span class="sxs-lookup"><span data-stu-id="eda1f-205">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>

<span data-ttu-id="eda1f-206">Sie können auch eine [Function-Anweisung](function-statement.md) mit dem `Async` Modifizierer markieren.</span><span class="sxs-lookup"><span data-stu-id="eda1f-206">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="eda1f-207">Eine `Async` Funktion kann den Rückgabetyp <xref:System.Threading.Tasks.Task%601> oder <xref:System.Threading.Tasks.Task>haben.</span><span class="sxs-lookup"><span data-stu-id="eda1f-207">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="eda1f-208">Ein Beispiel weiter unten in diesem Thema zeigt eine `Async` Funktion mit dem Rückgabetyp <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="eda1f-208">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="eda1f-209">`Async` `Sub` Prozeduren werden hauptsächlich für Ereignishandler verwendet, bei denen ein Wert nicht zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="eda1f-209">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="eda1f-210">Eine `Async` `Sub` Prozedur kann nicht erwartet werden, und der Aufrufer einer `Async` `Sub` Prozedur kann keine Ausnahmen abfangen, die von der `Sub` Prozedur ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="eda1f-210">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>

<span data-ttu-id="eda1f-211">Ein `Async` Prozedur kann keine [ByRef](../modifiers/byref.md) -Parameter deklarieren.</span><span class="sxs-lookup"><span data-stu-id="eda1f-211">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="eda1f-212">Weitere Informationen zu `Async` Prozeduren finden Sie unter [asynchrone Programmierung mit Async und warten](../../../visual-basic/programming-guide/concepts/async/index.md), [Ablauf Steuerung in](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)asynchronen Programmen und asynchronen [Rückgabe Typen](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="eda1f-212">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="example"></a><span data-ttu-id="eda1f-213">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eda1f-213">Example</span></span>

<span data-ttu-id="eda1f-214">Im folgenden Beispiel wird die `Sub`-Anweisung verwendet, um den Namen, die Parameter und den Code zu definieren, die den Hauptteil einer `Sub` Prozedur bilden.</span><span class="sxs-lookup"><span data-stu-id="eda1f-214">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a><span data-ttu-id="eda1f-215">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eda1f-215">Example</span></span>

<span data-ttu-id="eda1f-216">Im folgenden Beispiel ist `DelayAsync` eine `Async` `Function`, die den Rückgabetyp <xref:System.Threading.Tasks.Task%601>hat.</span><span class="sxs-lookup"><span data-stu-id="eda1f-216">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="eda1f-217">`DelayAsync` enthält eine `Return`-Anweisung, die eine ganze Zahl zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="eda1f-217">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="eda1f-218">Daher muss die Funktionsdeklaration von `DelayAsync` den Rückgabetyp `Task(Of Integer)`haben.</span><span class="sxs-lookup"><span data-stu-id="eda1f-218">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="eda1f-219">Da der Rückgabetyp `Task(Of Integer)`ist, erzeugt die Auswertung des `Await` Ausdrucks in `DoSomethingAsync` eine ganze Zahl, wie die folgende Anweisung zeigt: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="eda1f-219">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="eda1f-220">Das `startButton_Click`-Verfahren ist ein Beispiel für eine `Async Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="eda1f-220">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="eda1f-221">Da `DoSomethingAsync` eine `Async` Funktion ist, muss die Aufgabe für den `DoSomethingAsync`-erwartet werden, wie die folgende-Anweisung zeigt: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="eda1f-221">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="eda1f-222">Die `startButton_Click` `Sub` Prozedur muss mit dem `Async`-Modifizierer definiert werden, da Sie einen `Await` Ausdruck aufweist.</span><span class="sxs-lookup"><span data-stu-id="eda1f-222">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="eda1f-223">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eda1f-223">See also</span></span>

- [<span data-ttu-id="eda1f-224">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="eda1f-224">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="eda1f-225">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="eda1f-225">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="eda1f-226">Parameterliste</span><span class="sxs-lookup"><span data-stu-id="eda1f-226">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="eda1f-227">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="eda1f-227">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="eda1f-228">Call-Anweisung</span><span class="sxs-lookup"><span data-stu-id="eda1f-228">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="eda1f-229">Of</span><span class="sxs-lookup"><span data-stu-id="eda1f-229">Of</span></span>](of-clause.md)
- [<span data-ttu-id="eda1f-230">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="eda1f-230">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="eda1f-231">Gewusst wie: Verwenden einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="eda1f-231">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="eda1f-232">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="eda1f-232">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="eda1f-233">Partielle Methoden</span><span class="sxs-lookup"><span data-stu-id="eda1f-233">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
