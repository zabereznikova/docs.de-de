---
title: Sub-Anweisung (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Sub
dev_langs:
- VB
helpviewer_keywords:
- Public keyword, Sub statements
- procedures, creating
- declaring procedures, Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword, Sub statements
- Optional keyword, Sub statements
- declarations, procedures
- Sub keyword
- Handles keyword, Sub statements
- Protected Friend keyword
- ParamArray keyword, Sub statements
- Implements keyword, Sub statements
- Sub statement
- subroutines
- ByRef keyword, Sub statements
- Sub procedures, Sub statement
- recursive procedures
- Private keyword, Sub statements
- Friend keyword, Sub statements
- Exit statement, Sub statements
- procedures, Sub
- End keyword, Sub statements
- ByVal keyword, Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
caps.latest.revision: 52
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
ms.openlocfilehash: 61853a4f2321837683997b8e4241b688bc9f622c
ms.contentlocale: de-de
ms.lasthandoff: 05/15/2017

---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="7bbe9-102">Sub-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7bbe9-102">Sub Statement (Visual Basic)</span></span>
<span data-ttu-id="7bbe9-103">Deklariert den Namen, Parameter und Code, definieren ein `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bbe9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7bbe9-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]  
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Sub ]  
    [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="7bbe9-105">Teile</span><span class="sxs-lookup"><span data-stu-id="7bbe9-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="7bbe9-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-106">Optional.</span></span> <span data-ttu-id="7bbe9-107">Finden Sie unter [Attributliste](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="7bbe9-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `Partial`  
  
     <span data-ttu-id="7bbe9-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-108">Optional.</span></span> <span data-ttu-id="7bbe9-109">Zeigt die Definition einer partiellen Methode.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="7bbe9-110">Finden Sie unter [partielle Methoden](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="7bbe9-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="7bbe9-111">Optional.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-111">Optional.</span></span> <span data-ttu-id="7bbe9-112">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="7bbe9-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="7bbe9-113">Public</span><span class="sxs-lookup"><span data-stu-id="7bbe9-113">Public</span></span>](../modifiers/public.md)  
  
    -   [<span data-ttu-id="7bbe9-114">Protected</span><span class="sxs-lookup"><span data-stu-id="7bbe9-114">Protected</span></span>](../modifiers/protected.md)  
  
    -   [<span data-ttu-id="7bbe9-115">Friend</span><span class="sxs-lookup"><span data-stu-id="7bbe9-115">Friend</span></span>](../modifiers/friend.md)  
  
    -   [<span data-ttu-id="7bbe9-116">Private</span><span class="sxs-lookup"><span data-stu-id="7bbe9-116">Private</span></span>](../modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="7bbe9-117">Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="7bbe9-117">See [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="7bbe9-118">Optional.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-118">Optional.</span></span> <span data-ttu-id="7bbe9-119">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="7bbe9-119">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="7bbe9-120">Overloads</span><span class="sxs-lookup"><span data-stu-id="7bbe9-120">Overloads</span></span>](../modifiers/overloads.md)  
  
    -   [<span data-ttu-id="7bbe9-121">Overrides</span><span class="sxs-lookup"><span data-stu-id="7bbe9-121">Overrides</span></span>](../modifiers/overrides.md)  
  
    -   [<span data-ttu-id="7bbe9-122">Overridable</span><span class="sxs-lookup"><span data-stu-id="7bbe9-122">Overridable</span></span>](../modifiers/overridable.md)  
  
    -   [<span data-ttu-id="7bbe9-123">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="7bbe9-123">NotOverridable</span></span>](../modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="7bbe9-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="7bbe9-124">MustOverride</span></span>](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="7bbe9-125">Optional.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-125">Optional.</span></span> <span data-ttu-id="7bbe9-126">Finden Sie unter [freigegebenen](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="7bbe9-126">See [Shared](../modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="7bbe9-127">Optional.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-127">Optional.</span></span> <span data-ttu-id="7bbe9-128">Finden Sie unter [Schatten](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="7bbe9-128">See [Shadows](../modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="7bbe9-129">Optional.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-129">Optional.</span></span> <span data-ttu-id="7bbe9-130">Finden Sie unter [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="7bbe9-130">See [Async](../modifiers/async.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="7bbe9-131">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-131">Required.</span></span> <span data-ttu-id="7bbe9-132">Der Name der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-132">Name of the procedure.</span></span> <span data-ttu-id="7bbe9-133">Finden Sie unter [deklarierten Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="7bbe9-133">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="7bbe9-134">Um eine Konstruktorprozedur für eine Klasse zu erstellen, legen Sie den Namen des ein `Sub` Verfahren, um die `New` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-134">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="7bbe9-135">Weitere Informationen finden Sie unter [Objektlebensdauer: wie Objekte erstellen und zerstören sind](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="7bbe9-135">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="7bbe9-136">Optional.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-136">Optional.</span></span> <span data-ttu-id="7bbe9-137">Liste mit Typparametern für eine generische Prozedur.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-137">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="7bbe9-138">Finden Sie unter [Liste](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="7bbe9-138">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="7bbe9-139">Optional.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-139">Optional.</span></span> <span data-ttu-id="7bbe9-140">Die Liste der Namen lokaler Variablen, die die Parameter dieser Prozedur darstellt.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-140">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="7bbe9-141">Finden Sie unter [Parameterliste](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="7bbe9-141">See [Parameter List](parameter-list.md).</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="7bbe9-142">Optional.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-142">Optional.</span></span> <span data-ttu-id="7bbe9-143">Gibt an, dass diese Prozedur eine oder mehrere implementiert `Sub` Prozeduren, die jeweils in einer Schnittstelle, die von der enthaltenden Klasse oder Struktur dieser Prozedur implementiert definiert.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-143">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="7bbe9-144">Finden Sie unter [Anweisung implementiert](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7bbe9-144">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="7bbe9-145">Erforderlich, wenn `Implements` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-145">Required if `Implements` is supplied.</span></span> <span data-ttu-id="7bbe9-146">Liste der zu implementierenden `Sub`-Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-146">List of `Sub` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="7bbe9-147">Jede `implementedprocedure` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="7bbe9-147">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="7bbe9-148">Segment</span><span class="sxs-lookup"><span data-stu-id="7bbe9-148">Part</span></span>|<span data-ttu-id="7bbe9-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7bbe9-149">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="7bbe9-150">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-150">Required.</span></span> <span data-ttu-id="7bbe9-151">Name der Schnittstelle implementiert, die von dieser Prozedur der enthaltenden Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-151">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="7bbe9-152">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-152">Required.</span></span> <span data-ttu-id="7bbe9-153">Name, wodurch die Prozedur in `interface` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-153">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="7bbe9-154">Optional.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-154">Optional.</span></span> <span data-ttu-id="7bbe9-155">Gibt an, dass diese Prozedur eine oder mehrere bestimmte Ereignisse behandeln kann.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-155">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="7bbe9-156">Finden Sie unter [behandelt](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="7bbe9-156">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="7bbe9-157">Erforderlich, wenn `Handles` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-157">Required if `Handles` is supplied.</span></span> <span data-ttu-id="7bbe9-158">Die Liste der Ereignisse, die diese Prozedur behandelt.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-158">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="7bbe9-159">Jede `eventspecifier` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="7bbe9-159">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="7bbe9-160">Segment</span><span class="sxs-lookup"><span data-stu-id="7bbe9-160">Part</span></span>|<span data-ttu-id="7bbe9-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7bbe9-161">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="7bbe9-162">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-162">Required.</span></span> <span data-ttu-id="7bbe9-163">Objektvariable deklariert, die mit dem Datentyp der Klasse oder Struktur, die das Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-163">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="7bbe9-164">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-164">Required.</span></span> <span data-ttu-id="7bbe9-165">Der Name des Ereignisses, die diese Prozedur behandelt.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-165">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="7bbe9-166">Optional.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-166">Optional.</span></span> <span data-ttu-id="7bbe9-167">Der Block von Anweisungen in dieser Prozedur ausführen.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-167">Block of statements to run within this procedure.</span></span>  
  
-   `End Sub`  
  
     <span data-ttu-id="7bbe9-168">Beendet die Definition dieser Prozedur.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-168">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bbe9-169">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7bbe9-169">Remarks</span></span>  
 <span data-ttu-id="7bbe9-170">Der gesamte ausführbare Code muss innerhalb einer Prozedur sein.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-170">All executable code must be inside a procedure.</span></span> <span data-ttu-id="7bbe9-171">Verwenden einer `Sub` Prozedur, wenn Sie einen Wert an den aufrufenden Code zurückgeben möchten.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-171">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="7bbe9-172">Verwenden einer `Function` Prozedur, wenn einen Wert zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-172">Use a `Function` procedure when you want to return a value.</span></span>  
  
## <a name="defining-a-sub-procedure"></a><span data-ttu-id="7bbe9-173">Definieren eine Sub-Prozedur</span><span class="sxs-lookup"><span data-stu-id="7bbe9-173">Defining a Sub Procedure</span></span>  
 <span data-ttu-id="7bbe9-174">Sie können eine `Sub` Prozedur nur auf Modulebene.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-174">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="7bbe9-175">Der Deklarationskontext für eine Sub-Prozedur, daher muss eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle und eine Quelldatei, einen Namespace, eine Prozedur oder einen Block nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-175">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="7bbe9-176">Weitere Informationen finden Sie unter [Deklarationskontexte und Zugriffsebenen standardmäßig](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="7bbe9-176">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="7bbe9-177">`Sub`-Prozeduren weisen standardmäßig öffentlichen Zugriff.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-177">`Sub` procedures default to public access.</span></span> <span data-ttu-id="7bbe9-178">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-178">You can adjust their access levels by using the access modifiers.</span></span>  
  
 <span data-ttu-id="7bbe9-179">Wenn die Prozedur verwendet die `Implements` -Schlüsselwort, der enthaltenden Klasse oder Struktur benötigen eine `Implements` Anweisung unmittelbar nach seiner `Class` oder `Structure` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-179">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="7bbe9-180">Die `Implements` -Anweisung muss jede Schnittstelle, die im angegebenen enthalten `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-180">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="7bbe9-181">Allerdings den Namen, mit dem eine Schnittstelle definiert, die `Sub` (in `definedname`) keine mit dem Namen dieser Prozedur übereinstimmen (in `name`).</span><span class="sxs-lookup"><span data-stu-id="7bbe9-181">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>  
  
## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="7bbe9-182">Rückgabe aus einer Subprozedur</span><span class="sxs-lookup"><span data-stu-id="7bbe9-182">Returning from a Sub Procedure</span></span>  
 <span data-ttu-id="7bbe9-183">Wenn ein `Sub` -Prozedur zum aufrufenden Code zurückkehrt, die Ausführung wird fortgesetzt, mit der Anweisung nach der Anweisung, die diese aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-183">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>  
  
 <span data-ttu-id="7bbe9-184">Das folgende Beispiel zeigt eine Rückgabe aus einer `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-184">The following example shows a return from a `Sub` procedure.</span></span>  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 <span data-ttu-id="7bbe9-185">Die `Exit Sub` und `Return` -Anweisung führen zur unmittelbare Beendigung einer `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-185">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="7bbe9-186">Eine beliebige Anzahl von `Exit Sub` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie kombinieren können `Exit Sub` und `Return` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-186">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>  
  
## <a name="calling-a-sub-procedure"></a><span data-ttu-id="7bbe9-187">Aufrufen einer Subprozedur</span><span class="sxs-lookup"><span data-stu-id="7bbe9-187">Calling a Sub Procedure</span></span>  
 <span data-ttu-id="7bbe9-188">Rufen Sie eine `Sub` -Prozedur durch den Namen der Prozedur in einer Anweisung verwenden und dann folgen diesem Namen und die Argumentliste in Klammern.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-188">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="7bbe9-189">Sie können die Klammern weglassen, nur, wenn Sie Argumente angeben.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-189">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="7bbe9-190">Allerdings ist der Code besser lesbar, wenn Sie immer die Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-190">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="7bbe9-191">Ein `Sub` Prozedur und einer `Function` Prozedur über Parameter und eine Reihe von Anweisungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-191">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="7bbe9-192">Allerdings eine `Function` Prozedur gibt einen Wert und eine `Sub` Prozedur nicht.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-192">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="7bbe9-193">Daher können keiner `Sub` Prozedur in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-193">Therefore, you can't use a `Sub` procedure in an expression.</span></span>  
  
 <span data-ttu-id="7bbe9-194">Können Sie die `Call` Schlüsselwort beim Aufruf einer `Sub` Prozedur, aber dieses Schlüsselwort wird nicht empfohlen, für die meisten Verwendungen.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-194">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="7bbe9-195">Weitere Informationen finden Sie unter [Call-Anweisung](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7bbe9-195">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="7bbe9-196">Visual Basic werden manchmal neu angeordnet, arithmetische Ausdrücke, um die interne Effizienz zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-196">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="7bbe9-197">Aus diesem Grund Wenn Argumentliste Ausdrücke enthält, die andere Prozeduren aufrufen darf keine Sie davon ausgehen, dass die Ausdrücke in einer bestimmten Reihenfolge aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-197">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>  
  
## <a name="async-sub-procedures"></a><span data-ttu-id="7bbe9-198">Async Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="7bbe9-198">Async Sub Procedures</span></span>  
 <span data-ttu-id="7bbe9-199">Mithilfe der Async-Funktion können Sie die asynchrone Funktionen aufrufen, ohne explizite Rückrufe verwenden oder den Code manuell über mehrere Funktionen oder Lambda-Ausdrücke teilen.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-199">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="7bbe9-200">Markieren Sie eine Prozedur mit der [Async](../modifiers/async.md) -Modifizierer können Sie die ["await"](../../../visual-basic/language-reference/operators/await-operator.md) Operator in der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-200">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="7bbe9-201">Wenn das Steuerelement erreicht eine `Await` Ausdruck in der `Async` Prozedur die Steuerung an den Aufrufer zurückgegeben und Fortschritt in der Prozedur wird unterbrochen, bis die Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-201">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="7bbe9-202">Wenn der Vorgang abgeschlossen ist, können in der Prozedur die Ausführung fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-202">When the task is complete, execution can resume in the procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bbe9-203">Ein `Async` Prozedur zurückgibt, an den Aufrufer, wenn entweder das erste await-Objekt, das noch nicht abgeschlossen ist, aufgetreten ist oder das Ende der `Async` Prozedur erreicht wird, welches Ereignis zuerst eintritt.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-203">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>  
  
 <span data-ttu-id="7bbe9-204">Sie können auch Markieren einer [Function-Anweisung](function-statement.md) mit der `Async` Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-204">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="7bbe9-205">Ein `Async` Funktion kann keinen Rückgabetyp aufweisen oder <xref:System.Threading.Tasks.Task%601> <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="7bbe9-205">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="7bbe9-206">Ein Beispiel weiter unten in diesem Thema wird ein `Async` -Funktion, die einen Rückgabetyp <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> hat</span><span class="sxs-lookup"><span data-stu-id="7bbe9-206">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="7bbe9-207">`Async``Sub` Prozeduren werden hauptsächlich für Ereignishandler, kann ein Wert zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-207">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="7bbe9-208">Ein `Async``Sub` Prozedur kann nicht abgewartet werden, und der Aufrufer eine `Async``Sub` Prozedur keine Ausnahmen auffangen, die `Sub` Prozedur ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-208">An `Async``Sub` procedure can't be awaited, and the caller of an `Async``Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>  
  
 <span data-ttu-id="7bbe9-209">Ein `Async` Prozedur kann nicht deklariert werden, keine [ByRef](../modifiers/byref.md) Parameter.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-209">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="7bbe9-210">Weitere Informationen zu `Async` Verfahren finden Sie [asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Ablaufsteuerung in asynchronen Programmen](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), und [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="7bbe9-210">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bbe9-211">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7bbe9-211">Example</span></span>  
 <span data-ttu-id="7bbe9-212">Im folgenden Beispiel wird die `Sub` -Anweisung für die Definition der Name, Parameter und Code, der den Text der form einer `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-212">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>  
  
 <span data-ttu-id="7bbe9-213">[!code-vb[VbVbalrStatements&#58;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7bbe9-213">[!code-vb[VbVbalrStatements#58](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bbe9-214">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7bbe9-214">Example</span></span>  
 <span data-ttu-id="7bbe9-215">Im folgenden Beispiel `DelayAsync` ist ein ein `Async``Function` , bei dem Rückgabetyp <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="7bbe9-215">In the following example, `DelayAsync` is an an `Async``Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="7bbe9-216">`DelayAsync` enthält eine `Return`-Anweisung, die eine ganze Zahl zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-216">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="7bbe9-217">Aus diesem Grund der Deklaration des `DelayAsync` müssen einen Rückgabetyp von `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-217">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="7bbe9-218">Da der Rückgabetyp ist `Task(Of Integer)`, die Auswertung der `Await` Ausdruck in `DoSomethingAsync` erzeugt eine ganze Zahl, wie in der folgenden Anweisung dargestellt: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-218">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="7bbe9-219">Die `startButton_Click` Verfahren ist ein Beispiel für ein `Async Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-219">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="7bbe9-220">Da `DoSomethingAsync` ist ein `Async` -Funktion, die die Aufgabe für den Aufruf von `DoSomethingAsync` gewartet werden muss, wie in der folgenden Anweisung dargestellt: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-220">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="7bbe9-221">Die `startButton_Click``Sub` Prozedur muss definiert werden, mit der `Async` Modifizierer, weil sie verfügt über eine `Await` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="7bbe9-221">The `startButton_Click``Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 <span data-ttu-id="7bbe9-222">[!code-vb[CsAsyncMethod&#1;](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="7bbe9-222">[!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bbe9-223">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7bbe9-223">See Also</span></span>  
 <span data-ttu-id="7bbe9-224">[Implements-Anweisung](implements-statement.md) </span><span class="sxs-lookup"><span data-stu-id="7bbe9-224">[Implements Statement](implements-statement.md) </span></span>  
<span data-ttu-id="7bbe9-225"> [Function-Anweisung](function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="7bbe9-225"> [Function Statement](function-statement.md) </span></span>  
<span data-ttu-id="7bbe9-226"> [Parameterliste](parameter-list.md) </span><span class="sxs-lookup"><span data-stu-id="7bbe9-226"> [Parameter List](parameter-list.md) </span></span>  
<span data-ttu-id="7bbe9-227"> [Dim-Anweisung](dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="7bbe9-227"> [Dim Statement](dim-statement.md) </span></span>  
<span data-ttu-id="7bbe9-228"> [Call-Anweisung](call-statement.md) </span><span class="sxs-lookup"><span data-stu-id="7bbe9-228"> [Call Statement](call-statement.md) </span></span>  
<span data-ttu-id="7bbe9-229"> [Of](of-clause.md) </span><span class="sxs-lookup"><span data-stu-id="7bbe9-229"> [Of](of-clause.md) </span></span>  
<span data-ttu-id="7bbe9-230"> [Parameterarrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="7bbe9-230"> [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md) </span></span>  
<span data-ttu-id="7bbe9-231"> [Gewusst wie: Verwenden einer generischen Klasse](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md) </span><span class="sxs-lookup"><span data-stu-id="7bbe9-231"> [How to: Use a Generic Class](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md) </span></span>  
<span data-ttu-id="7bbe9-232"> [Problembehandlung bei Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="7bbe9-232"> [Troubleshooting Procedures](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="7bbe9-233"> [Partielle Methoden](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)</span><span class="sxs-lookup"><span data-stu-id="7bbe9-233"> [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)</span></span>

