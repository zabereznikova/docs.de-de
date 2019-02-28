---
title: Sub-Anweisung (Visual Basic)
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
ms.openlocfilehash: 6984e7e9f8695ff5bccdde01171733e740a5d6a7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965955"
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="59223-102">Sub-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59223-102">Sub Statement (Visual Basic)</span></span>
<span data-ttu-id="59223-103">Deklariert den Namen, Parameter und Code, definieren eine `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="59223-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59223-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="59223-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]  
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Sub ]  
    [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="59223-105">Teile</span><span class="sxs-lookup"><span data-stu-id="59223-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="59223-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="59223-106">Optional.</span></span> <span data-ttu-id="59223-107">Finden Sie unter [Liste](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="59223-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `Partial`  
  
     <span data-ttu-id="59223-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="59223-108">Optional.</span></span> <span data-ttu-id="59223-109">Gibt die Definition einer partiellen Methode.</span><span class="sxs-lookup"><span data-stu-id="59223-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="59223-110">Finden Sie unter [partielle Methoden](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="59223-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="59223-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="59223-111">Optional.</span></span> <span data-ttu-id="59223-112">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="59223-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="59223-113">Public</span><span class="sxs-lookup"><span data-stu-id="59223-113">Public</span></span>](../modifiers/public.md)  
  
    -   [<span data-ttu-id="59223-114">Protected</span><span class="sxs-lookup"><span data-stu-id="59223-114">Protected</span></span>](../modifiers/protected.md)  
  
    -   [<span data-ttu-id="59223-115">Friend</span><span class="sxs-lookup"><span data-stu-id="59223-115">Friend</span></span>](../modifiers/friend.md)  
  
    -   [<span data-ttu-id="59223-116">Private</span><span class="sxs-lookup"><span data-stu-id="59223-116">Private</span></span>](../modifiers/private.md)  
  
    - [<span data-ttu-id="59223-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="59223-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

    - [<span data-ttu-id="59223-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="59223-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)
  
     <span data-ttu-id="59223-119">Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="59223-119">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="59223-120">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="59223-120">Optional.</span></span> <span data-ttu-id="59223-121">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="59223-121">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="59223-122">Overloads</span><span class="sxs-lookup"><span data-stu-id="59223-122">Overloads</span></span>](../modifiers/overloads.md)  
  
    -   [<span data-ttu-id="59223-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="59223-123">Overrides</span></span>](../modifiers/overrides.md)  
  
    -   [<span data-ttu-id="59223-124">Overridable</span><span class="sxs-lookup"><span data-stu-id="59223-124">Overridable</span></span>](../modifiers/overridable.md)  
  
    -   [<span data-ttu-id="59223-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="59223-125">NotOverridable</span></span>](../modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="59223-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="59223-126">MustOverride</span></span>](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="59223-127">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="59223-127">Optional.</span></span> <span data-ttu-id="59223-128">Finden Sie unter [freigegebene](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="59223-128">See [Shared](../modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="59223-129">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="59223-129">Optional.</span></span> <span data-ttu-id="59223-130">Finden Sie unter [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="59223-130">See [Shadows](../modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="59223-131">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="59223-131">Optional.</span></span> <span data-ttu-id="59223-132">Finden Sie unter [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="59223-132">See [Async](../modifiers/async.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="59223-133">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="59223-133">Required.</span></span> <span data-ttu-id="59223-134">Der Name der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="59223-134">Name of the procedure.</span></span> <span data-ttu-id="59223-135">Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="59223-135">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="59223-136">Um eine Konstruktorprozedur für eine Klasse zu erstellen, legen Sie den Namen des eine `Sub` Vorgehensweise die `New` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="59223-136">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="59223-137">Weitere Informationen finden Sie unter [Object Lifetime: Wie die Objekte erstellt und zerstört werden](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="59223-137">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="59223-138">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="59223-138">Optional.</span></span> <span data-ttu-id="59223-139">Liste der Parameter vom Typ für eine generische Prozedur.</span><span class="sxs-lookup"><span data-stu-id="59223-139">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="59223-140">Finden Sie unter [Liste](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="59223-140">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="59223-141">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="59223-141">Optional.</span></span> <span data-ttu-id="59223-142">Liste der Namen lokaler Variablen, die die Parameter dieser Prozedur darstellt.</span><span class="sxs-lookup"><span data-stu-id="59223-142">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="59223-143">Finden Sie unter [Parameterliste](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="59223-143">See [Parameter List](parameter-list.md).</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="59223-144">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="59223-144">Optional.</span></span> <span data-ttu-id="59223-145">Gibt an, dass diese Prozedur, eine oder mehrere implementiert `Sub` Prozeduren, die jeweils in einer Schnittstelle implementiert, die von dieser Prozedur enthaltenen Klasse oder Struktur definiert.</span><span class="sxs-lookup"><span data-stu-id="59223-145">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="59223-146">Finden Sie unter [Anweisung implementiert](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="59223-146">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="59223-147">Erforderlich, wenn `Implements` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="59223-147">Required if `Implements` is supplied.</span></span> <span data-ttu-id="59223-148">Liste der zu implementierenden `Sub`-Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="59223-148">List of `Sub` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="59223-149">Jede `implementedprocedure` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="59223-149">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="59223-150">Segment</span><span class="sxs-lookup"><span data-stu-id="59223-150">Part</span></span>|<span data-ttu-id="59223-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59223-151">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="59223-152">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="59223-152">Required.</span></span> <span data-ttu-id="59223-153">Name einer Schnittstelle implementiert, die von dieser Prozedur der enthaltenden Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="59223-153">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="59223-154">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="59223-154">Required.</span></span> <span data-ttu-id="59223-155">Name, wodurch die Prozedur in `interface` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="59223-155">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="59223-156">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="59223-156">Optional.</span></span> <span data-ttu-id="59223-157">Gibt an, dass dieses Verfahren auf eine oder mehrere bestimmte Ereignisse verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="59223-157">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="59223-158">Finden Sie unter [behandelt](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="59223-158">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="59223-159">Erforderlich, wenn `Handles` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="59223-159">Required if `Handles` is supplied.</span></span> <span data-ttu-id="59223-160">Liste der Ereignisse, die diese Prozedur verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="59223-160">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="59223-161">Jede `eventspecifier` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="59223-161">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="59223-162">Segment</span><span class="sxs-lookup"><span data-stu-id="59223-162">Part</span></span>|<span data-ttu-id="59223-163">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59223-163">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="59223-164">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="59223-164">Required.</span></span> <span data-ttu-id="59223-165">Die Objektvariable deklariert mit dem Datentyp der Klasse oder Struktur, die das Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="59223-165">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="59223-166">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="59223-166">Required.</span></span> <span data-ttu-id="59223-167">Der Name des Ereignisses, die diese Prozedur verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="59223-167">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="59223-168">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="59223-168">Optional.</span></span> <span data-ttu-id="59223-169">Der Block von Anweisungen, die in dieser Prozedur ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="59223-169">Block of statements to run within this procedure.</span></span>  
  
-   `End Sub`  
  
     <span data-ttu-id="59223-170">Beendet die Definition dieses Verfahrens.</span><span class="sxs-lookup"><span data-stu-id="59223-170">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59223-171">Hinweise</span><span class="sxs-lookup"><span data-stu-id="59223-171">Remarks</span></span>  
 <span data-ttu-id="59223-172">Der gesamte ausführbarer Code muss innerhalb einer Prozedur sein.</span><span class="sxs-lookup"><span data-stu-id="59223-172">All executable code must be inside a procedure.</span></span> <span data-ttu-id="59223-173">Verwenden einer `Sub` Prozedur, wenn Sie keinen Wert an den aufrufenden Code zurückgeben möchten.</span><span class="sxs-lookup"><span data-stu-id="59223-173">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="59223-174">Verwenden einer `Function` Prozedur, wenn einen Wert zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="59223-174">Use a `Function` procedure when you want to return a value.</span></span>  
  
## <a name="defining-a-sub-procedure"></a><span data-ttu-id="59223-175">Definieren eine Sub-Prozedur</span><span class="sxs-lookup"><span data-stu-id="59223-175">Defining a Sub Procedure</span></span>  
 <span data-ttu-id="59223-176">Sie können definieren, eine `Sub` Prozedur nur auf Modulebene.</span><span class="sxs-lookup"><span data-stu-id="59223-176">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="59223-177">Der Deklarationskontext für eine Sub-Prozedur, daher muss eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle und eine Quelldatei, einem Namespace, eine Prozedur oder einen Block nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="59223-177">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="59223-178">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="59223-178">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="59223-179">`Sub` Prozeduren standardmäßig öffentlichen Zugriff auf.</span><span class="sxs-lookup"><span data-stu-id="59223-179">`Sub` procedures default to public access.</span></span> <span data-ttu-id="59223-180">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="59223-180">You can adjust their access levels by using the access modifiers.</span></span>  
  
 <span data-ttu-id="59223-181">Wenn die Prozedur verwendet die `Implements` -Schlüsselwort, die enthaltende Klasse oder Struktur benötigen eine `Implements` Anweisung sofort nach der `Class` oder `Structure` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="59223-181">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="59223-182">Die `Implements` -Anweisung muss jede Schnittstelle, die im angegebenen enthalten `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="59223-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="59223-183">Jedoch den Namen, die mit dem eine Schnittstelle definiert die `Sub` (in `definedname`) verfügt nicht über mit dem Namen dieses Verfahrens übereinstimmen (im `name`).</span><span class="sxs-lookup"><span data-stu-id="59223-183">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>  
  
## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="59223-184">Zurückgeben aus eine Sub-Prozedur</span><span class="sxs-lookup"><span data-stu-id="59223-184">Returning from a Sub Procedure</span></span>  
 <span data-ttu-id="59223-185">Wenn eine `Sub` Prozedur werden an den aufrufenden Code zurückgibt, die Ausführung wird fortgesetzt, mit der Anweisung nach der Anweisung, die diese aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="59223-185">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>  
  
 <span data-ttu-id="59223-186">Das folgende Beispiel zeigt eine Rückgabe aus einer `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="59223-186">The following example shows a return from a `Sub` procedure.</span></span>  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 <span data-ttu-id="59223-187">Die `Exit Sub` und `Return` Anweisungen bewirken, dass eine sofortige Beendigung aus einem `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="59223-187">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="59223-188">Eine beliebige Anzahl von `Exit Sub` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie können kombinieren `Exit Sub` und `Return` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="59223-188">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>  
  
## <a name="calling-a-sub-procedure"></a><span data-ttu-id="59223-189">Aufrufen einer Subprozedur</span><span class="sxs-lookup"><span data-stu-id="59223-189">Calling a Sub Procedure</span></span>  
 <span data-ttu-id="59223-190">Rufen Sie eine `Sub` Verfahren verwenden den Namen der Prozedur in einer Anweisung, und klicken Sie dann nach diesem Namen mit der Liste der Argumente in Klammern.</span><span class="sxs-lookup"><span data-stu-id="59223-190">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="59223-191">Sie können die Klammern weglassen, nur, wenn Sie Argumente angeben.</span><span class="sxs-lookup"><span data-stu-id="59223-191">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="59223-192">Allerdings ist der Code besser lesbar, wenn Sie immer die Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="59223-192">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="59223-193">Ein `Sub` Prozedur und ein `Function` Prozedur über Parameter und eine Reihe von Anweisungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="59223-193">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="59223-194">Allerdings eine `Function` Prozedur gibt einen Wert und einen `Sub` Prozedur nicht.</span><span class="sxs-lookup"><span data-stu-id="59223-194">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="59223-195">Aus diesem Grund können keine `Sub` Prozedur in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="59223-195">Therefore, you can't use a `Sub` procedure in an expression.</span></span>  
  
 <span data-ttu-id="59223-196">Können Sie die `Call` Schlüsselwort beim Aufrufen einer `Sub` Prozedur, aber dieses Schlüsselwort wird nicht empfohlen, für die meisten Verwendungen.</span><span class="sxs-lookup"><span data-stu-id="59223-196">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="59223-197">Weitere Informationen finden Sie unter [Call-Anweisung](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="59223-197">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="59223-198">Visual Basic werden manchmal neu angeordnet, arithmetische Ausdrücke, um die interne Effizienz steigern.</span><span class="sxs-lookup"><span data-stu-id="59223-198">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="59223-199">Aus diesem Grund Ihrer Typargumentliste Ausdrücke enthält, die anderen Prozeduren aufgerufen werden sollte nicht Sie davon ausgehen, dass diese Ausdrücke in einer bestimmten Reihenfolge aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="59223-199">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>  
  
## <a name="async-sub-procedures"></a><span data-ttu-id="59223-200">Async Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="59223-200">Async Sub Procedures</span></span>  
 <span data-ttu-id="59223-201">Mithilfe der Async-Funktion zu verwenden, können Sie die asynchrone Funktionen aufrufen, ohne explizite Rückrufe oder den Code manuell über mehrere Funktionen oder Lambdaausdrücke teilen.</span><span class="sxs-lookup"><span data-stu-id="59223-201">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="59223-202">Wenn Sie eine Prozedur mit kennzeichnen die [Async](../modifiers/async.md) Modifizierer verwenden, können Sie die ["await"](../../../visual-basic/language-reference/operators/await-operator.md) Operator in der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="59223-202">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="59223-203">Wenn Steuerung erreicht eine `Await` Ausdruck in der `Async` Prozedur die Steuerung an den Aufrufer zurückgegeben und Ausführung der Prozedur wird angehalten, bis die erwartete Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="59223-203">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="59223-204">Wenn die Aufgabe abgeschlossen ist, kann in der Prozedur die Ausführung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="59223-204">When the task is complete, execution can resume in the procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59223-205">Ein `Async` Prozedur zurückgibt, an den Aufrufer, wenn entweder das erste erwartete Objekt, das noch nicht abgeschlossen ist, erreicht wird oder das Ende der `Async` Prozedur erreicht wird, welches Ereignis zuerst eintritt.</span><span class="sxs-lookup"><span data-stu-id="59223-205">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>  
  
 <span data-ttu-id="59223-206">Sie können auch Markieren einer [Function-Anweisung](function-statement.md) mit der `Async` Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="59223-206">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="59223-207">Ein `Async` Funktion kann einen Rückgabetyp haben <xref:System.Threading.Tasks.Task%601> oder <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="59223-207">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="59223-208">Ein Beispiel weiter unten in diesem Thema wird gezeigt, eine `Async` Funktion, die einen Rückgabetyp hat <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="59223-208">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="59223-209">`Async` `Sub` Prozeduren werden in erster Linie für Ereignishandler verwendet, in dem ein Wert kann nicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="59223-209">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="59223-210">Ein `Async` `Sub` Prozedur kann nicht abgewartet werden, und der Aufrufer eine `Async` `Sub` Prozedur keine Ausnahmen auffangen, die die `Sub` Prozedur löst.</span><span class="sxs-lookup"><span data-stu-id="59223-210">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>  
  
 <span data-ttu-id="59223-211">Ein `Async` Prozedur kann nicht deklariert keine [ByRef](../modifiers/byref.md) Parameter.</span><span class="sxs-lookup"><span data-stu-id="59223-211">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="59223-212">Weitere Informationen zu `Async` Verfahren finden Sie [asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Ablaufsteuerung in asynchronen Programmen](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), und [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="59223-212">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="59223-213">Beispiel</span><span class="sxs-lookup"><span data-stu-id="59223-213">Example</span></span>  
 <span data-ttu-id="59223-214">Im folgenden Beispiel wird die `Sub` -Anweisung für die Definition der Name, Parameter und Code, der den Text der form einer `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="59223-214">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="59223-215">Beispiel</span><span class="sxs-lookup"><span data-stu-id="59223-215">Example</span></span>  
 <span data-ttu-id="59223-216">Im folgenden Beispiel `DelayAsync` ist ein `Async` `Function` , die einen Rückgabetyp hat <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="59223-216">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="59223-217">`DelayAsync` enthält eine `Return` -Anweisung, die eine ganze Zahl zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="59223-217">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="59223-218">Aus diesem Grund der Deklaration der `DelayAsync` müssen einen Rückgabetyp von `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="59223-218">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="59223-219">Da der Rückgabetyp ist `Task(Of Integer)`, die Auswertung der `Await` Ausdruck in `DoSomethingAsync` erzeugt eine ganze Zahl, wie in der folgenden Anweisung dargestellt: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="59223-219">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="59223-220">Die `startButton_Click` Verfahren ist ein Beispiel für eine `Async Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="59223-220">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="59223-221">Da `DoSomethingAsync` ist ein `Async` -Funktion, die Aufgabe für den Aufruf von `DoSomethingAsync` gewartet werden muss, wie in der folgenden Anweisung dargestellt: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="59223-221">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="59223-222">Die `startButton_Click` `Sub` Prozedur muss definiert werden, mit der `Async` Modifizierer, da sie verfügt über eine `Await` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="59223-222">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 [!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="59223-223">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59223-223">See also</span></span>
- [<span data-ttu-id="59223-224">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59223-224">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="59223-225">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59223-225">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="59223-226">Parameterliste</span><span class="sxs-lookup"><span data-stu-id="59223-226">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="59223-227">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59223-227">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="59223-228">Call-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59223-228">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="59223-229">Of</span><span class="sxs-lookup"><span data-stu-id="59223-229">Of</span></span>](of-clause.md)
- [<span data-ttu-id="59223-230">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="59223-230">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="59223-231">Vorgehensweise: Verwenden einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="59223-231">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="59223-232">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="59223-232">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="59223-233">Partielle Methoden</span><span class="sxs-lookup"><span data-stu-id="59223-233">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
