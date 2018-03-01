---
title: Sub-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0a2d0d5ffdca857a3a5ca58cd38b0930f254526f
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2017
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="3a179-102">Sub-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a179-102">Sub Statement (Visual Basic)</span></span>
<span data-ttu-id="3a179-103">Deklariert den Namen, Parameter und Code, definieren eine `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="3a179-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a179-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a179-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]  
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Sub ]  
    [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="3a179-105">Teile</span><span class="sxs-lookup"><span data-stu-id="3a179-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="3a179-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3a179-106">Optional.</span></span> <span data-ttu-id="3a179-107">Finden Sie unter [Attributliste](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="3a179-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `Partial`  
  
     <span data-ttu-id="3a179-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3a179-108">Optional.</span></span> <span data-ttu-id="3a179-109">Zeigt die Definition einer partiellen Methode.</span><span class="sxs-lookup"><span data-stu-id="3a179-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="3a179-110">Finden Sie unter [partielle Methoden](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="3a179-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="3a179-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3a179-111">Optional.</span></span> <span data-ttu-id="3a179-112">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="3a179-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="3a179-113">Public</span><span class="sxs-lookup"><span data-stu-id="3a179-113">Public</span></span>](../modifiers/public.md)  
  
    -   [<span data-ttu-id="3a179-114">Protected</span><span class="sxs-lookup"><span data-stu-id="3a179-114">Protected</span></span>](../modifiers/protected.md)  
  
    -   [<span data-ttu-id="3a179-115">Friend</span><span class="sxs-lookup"><span data-stu-id="3a179-115">Friend</span></span>](../modifiers/friend.md)  
  
    -   [<span data-ttu-id="3a179-116">Private</span><span class="sxs-lookup"><span data-stu-id="3a179-116">Private</span></span>](../modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="3a179-117">Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3a179-117">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="3a179-118">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3a179-118">Optional.</span></span> <span data-ttu-id="3a179-119">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="3a179-119">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="3a179-120">Overloads</span><span class="sxs-lookup"><span data-stu-id="3a179-120">Overloads</span></span>](../modifiers/overloads.md)  
  
    -   [<span data-ttu-id="3a179-121">Overrides</span><span class="sxs-lookup"><span data-stu-id="3a179-121">Overrides</span></span>](../modifiers/overrides.md)  
  
    -   [<span data-ttu-id="3a179-122">Overridable</span><span class="sxs-lookup"><span data-stu-id="3a179-122">Overridable</span></span>](../modifiers/overridable.md)  
  
    -   [<span data-ttu-id="3a179-123">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="3a179-123">NotOverridable</span></span>](../modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="3a179-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="3a179-124">MustOverride</span></span>](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="3a179-125">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3a179-125">Optional.</span></span> <span data-ttu-id="3a179-126">Finden Sie unter [freigegebene](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="3a179-126">See [Shared](../modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="3a179-127">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3a179-127">Optional.</span></span> <span data-ttu-id="3a179-128">Finden Sie unter [Schatten](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="3a179-128">See [Shadows](../modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="3a179-129">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3a179-129">Optional.</span></span> <span data-ttu-id="3a179-130">Finden Sie unter [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="3a179-130">See [Async](../modifiers/async.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="3a179-131">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3a179-131">Required.</span></span> <span data-ttu-id="3a179-132">Der Name der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="3a179-132">Name of the procedure.</span></span> <span data-ttu-id="3a179-133">Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="3a179-133">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="3a179-134">Um eine Konstruktorprozedur für eine Klasse zu erstellen, legen Sie den Namen des eine `Sub` Vorgehensweise der `New` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="3a179-134">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="3a179-135">Weitere Informationen finden Sie unter [Objektlebensdauer: wie Objekte erstellen und zerstören sind](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="3a179-135">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="3a179-136">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3a179-136">Optional.</span></span> <span data-ttu-id="3a179-137">Liste mit Typparametern für eine generische Prozedur.</span><span class="sxs-lookup"><span data-stu-id="3a179-137">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="3a179-138">Finden Sie unter [geben Liste](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="3a179-138">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="3a179-139">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3a179-139">Optional.</span></span> <span data-ttu-id="3a179-140">Liste der Namen lokaler Variablen, die die Parameter dieser Prozedur darstellt.</span><span class="sxs-lookup"><span data-stu-id="3a179-140">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="3a179-141">Finden Sie unter [Parameterliste](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="3a179-141">See [Parameter List](parameter-list.md).</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="3a179-142">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3a179-142">Optional.</span></span> <span data-ttu-id="3a179-143">Gibt an, dass dieses Verfahren eine oder mehrere implementiert `Sub` Prozeduren, die jeweils in einer Schnittstelle implementiert, die von dieser Prozedur enthaltenen Klasse oder Struktur definiert.</span><span class="sxs-lookup"><span data-stu-id="3a179-143">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="3a179-144">Finden Sie unter [Anweisung implementiert](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3a179-144">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="3a179-145">Erforderlich, wenn `Implements` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3a179-145">Required if `Implements` is supplied.</span></span> <span data-ttu-id="3a179-146">Liste der zu implementierenden `Sub`-Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="3a179-146">List of `Sub` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="3a179-147">Jede `implementedprocedure` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="3a179-147">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="3a179-148">Segment</span><span class="sxs-lookup"><span data-stu-id="3a179-148">Part</span></span>|<span data-ttu-id="3a179-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a179-149">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="3a179-150">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3a179-150">Required.</span></span> <span data-ttu-id="3a179-151">Name einer Schnittstelle implementiert, die von dieser Prozedur der enthaltenden Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="3a179-151">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="3a179-152">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3a179-152">Required.</span></span> <span data-ttu-id="3a179-153">Name, wodurch die Prozedur in `interface` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="3a179-153">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="3a179-154">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3a179-154">Optional.</span></span> <span data-ttu-id="3a179-155">Gibt an, dass dieses Verfahren eine oder mehrere bestimmte Ereignisse verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="3a179-155">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="3a179-156">Finden Sie unter [behandelt](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="3a179-156">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="3a179-157">Erforderlich, wenn `Handles` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3a179-157">Required if `Handles` is supplied.</span></span> <span data-ttu-id="3a179-158">Die Liste der Ereignisse, die diese Prozedur behandelt.</span><span class="sxs-lookup"><span data-stu-id="3a179-158">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="3a179-159">Jede `eventspecifier` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="3a179-159">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="3a179-160">Segment</span><span class="sxs-lookup"><span data-stu-id="3a179-160">Part</span></span>|<span data-ttu-id="3a179-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a179-161">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="3a179-162">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3a179-162">Required.</span></span> <span data-ttu-id="3a179-163">Mit dem Datentyp der Klasse oder Struktur, die das Ereignis auslöst deklarierte Objektvariable.</span><span class="sxs-lookup"><span data-stu-id="3a179-163">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="3a179-164">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3a179-164">Required.</span></span> <span data-ttu-id="3a179-165">Der Name des Ereignisses, das dieses Verfahren behandelt.</span><span class="sxs-lookup"><span data-stu-id="3a179-165">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="3a179-166">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3a179-166">Optional.</span></span> <span data-ttu-id="3a179-167">Der Block von Anweisungen in dieser Prozedur ausführen.</span><span class="sxs-lookup"><span data-stu-id="3a179-167">Block of statements to run within this procedure.</span></span>  
  
-   `End Sub`  
  
     <span data-ttu-id="3a179-168">Beendet die Definition dieses Verfahrens fort.</span><span class="sxs-lookup"><span data-stu-id="3a179-168">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a179-169">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3a179-169">Remarks</span></span>  
 <span data-ttu-id="3a179-170">Alle ausführbaren Code muss innerhalb einer Prozedur sein.</span><span class="sxs-lookup"><span data-stu-id="3a179-170">All executable code must be inside a procedure.</span></span> <span data-ttu-id="3a179-171">Verwenden einer `Sub` Prozedur, wenn Sie einen Wert an den aufrufenden Code zurückgeben möchten.</span><span class="sxs-lookup"><span data-stu-id="3a179-171">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="3a179-172">Verwenden einer `Function` Prozedur, wenn einen Wert zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="3a179-172">Use a `Function` procedure when you want to return a value.</span></span>  
  
## <a name="defining-a-sub-procedure"></a><span data-ttu-id="3a179-173">Definieren eine Subprozedur</span><span class="sxs-lookup"><span data-stu-id="3a179-173">Defining a Sub Procedure</span></span>  
 <span data-ttu-id="3a179-174">Sie können definieren, eine `Sub` Prozedur nur auf Modulebene.</span><span class="sxs-lookup"><span data-stu-id="3a179-174">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="3a179-175">Der Deklarationskontext für eine Subprozedur, daher muss eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle und nicht mit einer Quelldatei, einen Namespace, eine Prozedur oder eines Blocks.</span><span class="sxs-lookup"><span data-stu-id="3a179-175">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="3a179-176">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3a179-176">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="3a179-177">`Sub`Prozeduren standardmäßig öffentlichen Zugriff auf.</span><span class="sxs-lookup"><span data-stu-id="3a179-177">`Sub` procedures default to public access.</span></span> <span data-ttu-id="3a179-178">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="3a179-178">You can adjust their access levels by using the access modifiers.</span></span>  
  
 <span data-ttu-id="3a179-179">Wenn die Prozedur verwendet die `Implements` -Schlüsselwort, der enthaltenden Klasse oder Struktur benötigen eine `Implements` -Anweisung, die unmittelbar folgt seine `Class` oder `Structure` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="3a179-179">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="3a179-180">Die `Implements` -Anweisung muss jede Schnittstelle, die im angegebenen enthalten `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="3a179-180">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="3a179-181">Jedoch den Namen, die mit dem eine Schnittstelle definiert die `Sub` (in `definedname`) verfügt nicht über den Namen dieses Verfahrens entsprechend (in `name`).</span><span class="sxs-lookup"><span data-stu-id="3a179-181">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>  
  
## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="3a179-182">Rückgabe aus einer Subprozedur</span><span class="sxs-lookup"><span data-stu-id="3a179-182">Returning from a Sub Procedure</span></span>  
 <span data-ttu-id="3a179-183">Wenn eine `Sub` Prozedur werden an den aufrufenden Code zurückgibt, die Ausführung wird fortgeführt, mit der Anweisung nach der Anweisung, die diese aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="3a179-183">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>  
  
 <span data-ttu-id="3a179-184">Das folgende Beispiel zeigt eine Rückgabe aus einer `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="3a179-184">The following example shows a return from a `Sub` procedure.</span></span>  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 <span data-ttu-id="3a179-185">Die `Exit Sub` und `Return` Anweisungen bewirken, dass eine sofortige Beendigung von einem `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="3a179-185">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="3a179-186">Eine beliebige Anzahl von `Exit Sub` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie können kombinieren `Exit Sub` und `Return` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="3a179-186">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>  
  
## <a name="calling-a-sub-procedure"></a><span data-ttu-id="3a179-187">Aufrufen einer Subprozedur</span><span class="sxs-lookup"><span data-stu-id="3a179-187">Calling a Sub Procedure</span></span>  
 <span data-ttu-id="3a179-188">Rufen Sie eine `Sub` -Prozedur durch den Namen der Prozedur in einer Anweisung verwenden und dann folgen diesem Namen und die Argumentliste in Klammern.</span><span class="sxs-lookup"><span data-stu-id="3a179-188">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="3a179-189">Sie können die Klammern weglassen, nur, wenn Sie keine Argumente angeben.</span><span class="sxs-lookup"><span data-stu-id="3a179-189">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="3a179-190">Allerdings ist der Code besser lesbar, wenn Sie immer die Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="3a179-190">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="3a179-191">Ein `Sub` Prozedur und einen `Function` Prozedur über Parameter und eine Reihe von Anweisungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="3a179-191">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="3a179-192">Allerdings eine `Function` Prozedur gibt einen Wert und eine `Sub` Prozedur nicht.</span><span class="sxs-lookup"><span data-stu-id="3a179-192">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="3a179-193">Aus diesem Grund können keiner `Sub` Prozedur in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="3a179-193">Therefore, you can't use a `Sub` procedure in an expression.</span></span>  
  
 <span data-ttu-id="3a179-194">Können Sie die `Call` Schlüsselwort beim Aufrufen einer `Sub` Prozedur, aber dieses Schlüsselwort wird nicht empfohlen, für die meisten Zwecke.</span><span class="sxs-lookup"><span data-stu-id="3a179-194">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="3a179-195">Weitere Informationen finden Sie unter [-Anweisung Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3a179-195">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="3a179-196">Visual Basic werden manchmal neu angeordnet, arithmetische Ausdrücke, um die interne Effizienz steigern.</span><span class="sxs-lookup"><span data-stu-id="3a179-196">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="3a179-197">Aus diesem Grund Ihrer Typargumentliste Ausdrücke enthält, die anderen Prozeduren aufruft darf keine Sie davon ausgehen, dass diese Ausdrücke in einer bestimmten Reihenfolge aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3a179-197">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>  
  
## <a name="async-sub-procedures"></a><span data-ttu-id="3a179-198">Asynchrone Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="3a179-198">Async Sub Procedures</span></span>  
 <span data-ttu-id="3a179-199">Mithilfe der Async-Funktion können Sie asynchrone Funktionen aufrufen, ohne explizite Rückrufe verwenden oder manuell über mehrere Funktionen oder Lambda-Ausdrücke Teilen Codes zu müssen.</span><span class="sxs-lookup"><span data-stu-id="3a179-199">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="3a179-200">Wenn Sie eine Prozedur mit kennzeichnen die [Async](../modifiers/async.md) Modifizierer verwenden, können Sie die ["await"](../../../visual-basic/language-reference/operators/await-operator.md) Operator in der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="3a179-200">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="3a179-201">Wenn Steuerung erreicht eine `Await` Ausdruck in der `Async` Prozedur, Steuerung an den Aufrufer zurückgegeben und die Ausführung der Prozedur wird angehalten, bis die erwartete Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="3a179-201">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="3a179-202">Wenn die Aufgabe abgeschlossen ist, kann in der Prozedur die Ausführung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="3a179-202">When the task is complete, execution can resume in the procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a179-203">Ein `Async` Prozedur zurückgibt, an den Aufrufer, wenn entweder das erste erwartete Objekt, das noch nicht abgeschlossen wurde erkannt wird oder das Ende der `Async` Prozedur erreicht wird, welcher Vorgang zuerst ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a179-203">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>  
  
 <span data-ttu-id="3a179-204">Sie können auch markieren eine [Funktionsanweisung](function-statement.md) mit der `Async` Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="3a179-204">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="3a179-205">Ein `Async` Funktion kann den Rückgabetyp haben <xref:System.Threading.Tasks.Task%601> oder <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="3a179-205">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="3a179-206">Ein Beispiel weiter unten in diesem Thema wird ein `Async` -Funktion, die einen Rückgabetyp <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="3a179-206">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="3a179-207">`Async``Sub` Prozeduren werden in erster Linie zum Ereignishandler, in dem ein Wert kann nicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3a179-207">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="3a179-208">Ein `Async``Sub` Prozedur kann nicht abgewartet werden, und der Aufrufer eine `Async``Sub` Prozedur keine Ausnahmen auffangen, die die `Sub` Prozedur ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="3a179-208">An `Async``Sub` procedure can't be awaited, and the caller of an `Async``Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>  
  
 <span data-ttu-id="3a179-209">Ein `Async` Prozedur kann nicht deklariert werden alle [ByRef](../modifiers/byref.md) Parameter.</span><span class="sxs-lookup"><span data-stu-id="3a179-209">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="3a179-210">Weitere Informationen zu `Async` Verfahren finden Sie [asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Ablaufsteuerung in asynchronen Programmen](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), und [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="3a179-210">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a179-211">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3a179-211">Example</span></span>  
 <span data-ttu-id="3a179-212">Im folgenden Beispiel wird die `Sub` Anweisung, um den Namen, Parameter und Code, der den Text der form definieren eine `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="3a179-212">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#58](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="3a179-213">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3a179-213">Example</span></span>  
 <span data-ttu-id="3a179-214">Im folgenden Beispiel `DelayAsync` ist ein `Async``Function` , die einen Rückgabetyp hat <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="3a179-214">In the following example, `DelayAsync` is an `Async``Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="3a179-215">`DelayAsync` enthält eine `Return`-Anweisung, die eine ganze Zahl zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3a179-215">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="3a179-216">Aus diesem Grund die Funktionsdeklaration von `DelayAsync` benötigen einen Rückgabetyp von `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="3a179-216">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="3a179-217">Da der Rückgabetyp ist `Task(Of Integer)`, der Auswertung der `Await` Ausdruck in `DoSomethingAsync` erzeugt eine ganze Zahl, wie in der folgenden Anweisung dargestellt: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="3a179-217">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="3a179-218">Die `startButton_Click` Verfahren ist ein Beispiel für eine `Async Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="3a179-218">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="3a179-219">Da `DoSomethingAsync` ist ein `Async` -Funktion, die Aufgabe für den Aufruf von `DoSomethingAsync` abgewartet werden muss, wie in der folgenden Anweisung dargestellt: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="3a179-219">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="3a179-220">Die `startButton_Click``Sub` Prozedur muss definiert werden, mit der `Async` Modifizierer, da es wurde ein `Await` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="3a179-220">The `startButton_Click``Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3a179-221">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a179-221">See Also</span></span>  
 [<span data-ttu-id="3a179-222">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3a179-222">Implements Statement</span></span>](implements-statement.md)  
 [<span data-ttu-id="3a179-223">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3a179-223">Function Statement</span></span>](function-statement.md)  
 [<span data-ttu-id="3a179-224">Parameterliste</span><span class="sxs-lookup"><span data-stu-id="3a179-224">Parameter List</span></span>](parameter-list.md)  
 [<span data-ttu-id="3a179-225">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3a179-225">Dim Statement</span></span>](dim-statement.md)  
 [<span data-ttu-id="3a179-226">Call-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3a179-226">Call Statement</span></span>](call-statement.md)  
 [<span data-ttu-id="3a179-227">Of</span><span class="sxs-lookup"><span data-stu-id="3a179-227">Of</span></span>](of-clause.md)  
 [<span data-ttu-id="3a179-228">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="3a179-228">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [<span data-ttu-id="3a179-229">Gewusst wie: Verwenden einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="3a179-229">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="3a179-230">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="3a179-230">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [<span data-ttu-id="3a179-231">Partielle Methoden</span><span class="sxs-lookup"><span data-stu-id="3a179-231">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
