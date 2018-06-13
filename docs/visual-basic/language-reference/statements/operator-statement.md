---
title: Operator Statement
ms.date: 07/20/2015
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
ms.openlocfilehash: cb7fe7929e4b6e61ca3b39be5615e09182f2fe0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605497"
---
# <a name="operator-statement"></a><span data-ttu-id="77ab6-102">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="77ab6-102">Operator Statement</span></span>
<span data-ttu-id="77ab6-103">Deklariert das Symbol "Operator", die Operanden und den Code, die eine Operatorprozedur für eine Klasse oder Struktur definieren.</span><span class="sxs-lookup"><span data-stu-id="77ab6-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77ab6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="77ab6-104">Syntax</span></span>  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## <a name="parts"></a><span data-ttu-id="77ab6-105">Teile</span><span class="sxs-lookup"><span data-stu-id="77ab6-105">Parts</span></span>  
 `attrlist`  
 <span data-ttu-id="77ab6-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="77ab6-106">Optional.</span></span> <span data-ttu-id="77ab6-107">Finden Sie unter [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="77ab6-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `Public`  
 <span data-ttu-id="77ab6-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="77ab6-108">Required.</span></span> <span data-ttu-id="77ab6-109">Gibt an, dass die Operatorprozedur hat [öffentlichen](../../../visual-basic/language-reference/modifiers/public.md) Zugriff.</span><span class="sxs-lookup"><span data-stu-id="77ab6-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span>  
  
 `Overloads`  
 <span data-ttu-id="77ab6-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="77ab6-110">Optional.</span></span> <span data-ttu-id="77ab6-111">Finden Sie unter [überlädt](../../../visual-basic/language-reference/modifiers/overloads.md).</span><span class="sxs-lookup"><span data-stu-id="77ab6-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span></span>  
  
 `Shared`  
 <span data-ttu-id="77ab6-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="77ab6-112">Required.</span></span> <span data-ttu-id="77ab6-113">Gibt an, dass die Operatorprozedur eine [Shared](../../../visual-basic/language-reference/modifiers/shared.md) Prozedur.</span><span class="sxs-lookup"><span data-stu-id="77ab6-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span></span>  
  
 `Shadows`  
 <span data-ttu-id="77ab6-114">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="77ab6-114">Optional.</span></span> <span data-ttu-id="77ab6-115">Finden Sie unter [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="77ab6-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
 `Widening`  
 <span data-ttu-id="77ab6-116">Für einen Konvertierungsoperator erforderlich, es sei denn, Sie geben `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="77ab6-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="77ab6-117">Gibt an, dass die Operatorprozedur definiert eine [Widening](../../../visual-basic/language-reference/modifiers/widening.md) Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="77ab6-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span></span> <span data-ttu-id="77ab6-118">Siehe "Erweiternde und eingrenzende Konvertierungen" auf dieser Hilfeseite an.</span><span class="sxs-lookup"><span data-stu-id="77ab6-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `Narrowing`  
 <span data-ttu-id="77ab6-119">Für einen Konvertierungsoperator erforderlich, es sei denn, Sie geben `Widening`.</span><span class="sxs-lookup"><span data-stu-id="77ab6-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="77ab6-120">Gibt an, dass die Operatorprozedur definiert eine [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="77ab6-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="77ab6-121">Siehe "Erweiternde und eingrenzende Konvertierungen" auf dieser Hilfeseite an.</span><span class="sxs-lookup"><span data-stu-id="77ab6-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `operatorsymbol`  
 <span data-ttu-id="77ab6-122">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="77ab6-122">Required.</span></span> <span data-ttu-id="77ab6-123">Das Symbol oder die ID des Operators, der die Operatorprozedur definiert.</span><span class="sxs-lookup"><span data-stu-id="77ab6-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>  
  
 `operand1`  
 <span data-ttu-id="77ab6-124">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="77ab6-124">Required.</span></span> <span data-ttu-id="77ab6-125">Der Name und Typ der einzelnen Operanden aus, der ein unäroperator (einschließlich eines Konvertierungsoperators) oder der linke Operand eines binären Operators.</span><span class="sxs-lookup"><span data-stu-id="77ab6-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>  
  
 `operand2`  
 <span data-ttu-id="77ab6-126">Für binäre Operatoren erforderlich.</span><span class="sxs-lookup"><span data-stu-id="77ab6-126">Required for binary operators.</span></span> <span data-ttu-id="77ab6-127">Der Name und Typ des rechten Operanden des binären Operators.</span><span class="sxs-lookup"><span data-stu-id="77ab6-127">The name and type of the right operand of a binary operator.</span></span>  
  
 <span data-ttu-id="77ab6-128">`operand1` und `operand2` haben die folgende Syntax und Bestandteile:</span><span class="sxs-lookup"><span data-stu-id="77ab6-128">`operand1` and `operand2` have the following syntax and parts:</span></span>  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|<span data-ttu-id="77ab6-129">Segment</span><span class="sxs-lookup"><span data-stu-id="77ab6-129">Part</span></span>|<span data-ttu-id="77ab6-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77ab6-130">Description</span></span>|  
|----------|-----------------|  
|`ByVal`|<span data-ttu-id="77ab6-131">Optional, doch dem Übergabemechanismus muss [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="77ab6-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>|  
|`operandname`|<span data-ttu-id="77ab6-132">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="77ab6-132">Required.</span></span> <span data-ttu-id="77ab6-133">Der Name der Variablen, die diesen Operanden darstellt.</span><span class="sxs-lookup"><span data-stu-id="77ab6-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="77ab6-134">Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="77ab6-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`operandtype`|<span data-ttu-id="77ab6-135">Dies ist optional, wenn `Option Strict` ist `On`.</span><span class="sxs-lookup"><span data-stu-id="77ab6-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="77ab6-136">Der Datentyp dieses Operanden.</span><span class="sxs-lookup"><span data-stu-id="77ab6-136">Data type of this operand.</span></span>|  
  
 `type`  
 <span data-ttu-id="77ab6-137">Dies ist optional, wenn `Option Strict` ist `On`.</span><span class="sxs-lookup"><span data-stu-id="77ab6-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="77ab6-138">Datentyp des Werts die Operatorprozedur gibt.</span><span class="sxs-lookup"><span data-stu-id="77ab6-138">Data type of the value the operator procedure returns.</span></span>  
  
 `statements`  
 <span data-ttu-id="77ab6-139">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="77ab6-139">Optional.</span></span> <span data-ttu-id="77ab6-140">Der Block von Anweisungen, die die Operatorprozedur ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="77ab6-140">Block of statements that the operator procedure runs.</span></span>  
  
 `returnvalue`  
 <span data-ttu-id="77ab6-141">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="77ab6-141">Required.</span></span> <span data-ttu-id="77ab6-142">Der Wert, den die Operatorprozedur an den aufrufenden Code zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="77ab6-142">The value that the operator procedure returns to the calling code.</span></span>  
  
 <span data-ttu-id="77ab6-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="77ab6-143">`End` `Operator`</span></span>  
 <span data-ttu-id="77ab6-144">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="77ab6-144">Required.</span></span> <span data-ttu-id="77ab6-145">Beendet die Definition dieser Operatorprozedur an.</span><span class="sxs-lookup"><span data-stu-id="77ab6-145">Terminates the definition of this operator procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77ab6-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="77ab6-146">Remarks</span></span>  
 <span data-ttu-id="77ab6-147">Sie können `Operator` nur in einer Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="77ab6-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="77ab6-148">Dies bedeutet, dass die *Deklarationskontext* für ein Operator darf keine Quelldatei, Namespace, Modul, Schnittstelle, Prozedur oder Block sein.</span><span class="sxs-lookup"><span data-stu-id="77ab6-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="77ab6-149">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="77ab6-149">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="77ab6-150">Alle Operatoren muss `Public Shared`.</span><span class="sxs-lookup"><span data-stu-id="77ab6-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="77ab6-151">Sie können keine angeben `ByRef`, `Optional`, oder `ParamArray` für beide Operanden.</span><span class="sxs-lookup"><span data-stu-id="77ab6-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>  
  
 <span data-ttu-id="77ab6-152">Sie können nicht das Symbol "Operator" oder der Bezeichner verwenden, um einen Rückgabewert zu speichern.</span><span class="sxs-lookup"><span data-stu-id="77ab6-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="77ab6-153">Verwenden Sie die `Return` -Anweisung, und sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="77ab6-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="77ab6-154">Eine beliebige Anzahl von `Return` Anweisungen können an beliebiger Stelle in der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="77ab6-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>  
  
 <span data-ttu-id="77ab6-155">Definieren einen Operator auf diese Weise wird aufgerufen, *operatorüberladung*, unabhängig davon, ob Sie verwenden die `Overloads` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="77ab6-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="77ab6-156">In der folgenden Tabelle sind die Operatoren aufgelistet, die Sie definieren können.</span><span class="sxs-lookup"><span data-stu-id="77ab6-156">The following table lists the operators you can define.</span></span>  
  
|<span data-ttu-id="77ab6-157">Typ</span><span class="sxs-lookup"><span data-stu-id="77ab6-157">Type</span></span>|<span data-ttu-id="77ab6-158">Operatoren</span><span class="sxs-lookup"><span data-stu-id="77ab6-158">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="77ab6-159">Unär</span><span class="sxs-lookup"><span data-stu-id="77ab6-159">Unary</span></span>|<span data-ttu-id="77ab6-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="77ab6-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="77ab6-161">Binär</span><span class="sxs-lookup"><span data-stu-id="77ab6-161">Binary</span></span>|<span data-ttu-id="77ab6-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="77ab6-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="77ab6-163">Konvertierung (unär)</span><span class="sxs-lookup"><span data-stu-id="77ab6-163">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="77ab6-164">Beachten Sie, dass die `=` in der Liste binärer Operator wird der Vergleichsoperator, der nicht der Zuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="77ab6-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="77ab6-165">Wenn Sie definieren `CType`, geben Sie `Widening` oder `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="77ab6-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>  
  
## <a name="matched-pairs"></a><span data-ttu-id="77ab6-166">Passende Paare</span><span class="sxs-lookup"><span data-stu-id="77ab6-166">Matched Pairs</span></span>  
 <span data-ttu-id="77ab6-167">Sie müssen bestimmte Operatoren als zueinander passende Paare definieren.</span><span class="sxs-lookup"><span data-stu-id="77ab6-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="77ab6-168">Wenn Sie einen Operator eines solch ein paar definieren, müssen Sie den anderen ebenso definieren.</span><span class="sxs-lookup"><span data-stu-id="77ab6-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="77ab6-169">Die passende Paare lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="77ab6-169">The matched pairs are the following:</span></span>  
  
-   <span data-ttu-id="77ab6-170">`=` und `<>`</span><span class="sxs-lookup"><span data-stu-id="77ab6-170">`=` and `<>`</span></span>  
  
-   <span data-ttu-id="77ab6-171">`>` und `<`</span><span class="sxs-lookup"><span data-stu-id="77ab6-171">`>` and `<`</span></span>  
  
-   <span data-ttu-id="77ab6-172">`>=` und `<=`</span><span class="sxs-lookup"><span data-stu-id="77ab6-172">`>=` and `<=`</span></span>  
  
-   <span data-ttu-id="77ab6-173">`IsTrue` und `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="77ab6-173">`IsTrue` and `IsFalse`</span></span>  
  
## <a name="data-type-restrictions"></a><span data-ttu-id="77ab6-174">Datentypeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="77ab6-174">Data Type Restrictions</span></span>  
 <span data-ttu-id="77ab6-175">Jeder Operator, den Sie definieren muss umfassen, die Klasse oder Struktur, auf dem Sie definieren.</span><span class="sxs-lookup"><span data-stu-id="77ab6-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="77ab6-176">Dies bedeutet, dass die Klasse oder Struktur mit dem Datentyp der folgenden angezeigt werden muss:</span><span class="sxs-lookup"><span data-stu-id="77ab6-176">This means that the class or structure must appear as the data type of the following:</span></span>  
  
-   <span data-ttu-id="77ab6-177">Der Operand eines unären Operators.</span><span class="sxs-lookup"><span data-stu-id="77ab6-177">The operand of a unary operator.</span></span>  
  
-   <span data-ttu-id="77ab6-178">Mindestens einer der Operanden des binären Operators.</span><span class="sxs-lookup"><span data-stu-id="77ab6-178">At least one of the operands of a binary operator.</span></span>  
  
-   <span data-ttu-id="77ab6-179">Der Operand oder der Rückgabetyp eines Konvertierungsoperators.</span><span class="sxs-lookup"><span data-stu-id="77ab6-179">Either the operand or the return type of a conversion operator.</span></span>  
  
 <span data-ttu-id="77ab6-180">Bestimmte Operatoren aufweisen Datentyp, zusätzliche Einschränkungen, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="77ab6-180">Certain operators have additional data type restrictions, as follows:</span></span>  
  
-   <span data-ttu-id="77ab6-181">Wenn Sie definieren die `IsTrue` und `IsFalse` Operatoren müssen beide Zurückgeben der `Boolean` Typ.</span><span class="sxs-lookup"><span data-stu-id="77ab6-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>  
  
-   <span data-ttu-id="77ab6-182">Wenn Sie definieren die `<<` und `>>` Operatoren müssen beide angeben der `Integer` Geben Sie für die `operandtype` von `operand2`.</span><span class="sxs-lookup"><span data-stu-id="77ab6-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>  
  
 <span data-ttu-id="77ab6-183">Der Rückgabetyp ist keine der beiden Operanden entsprechen.</span><span class="sxs-lookup"><span data-stu-id="77ab6-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="77ab6-184">Angenommen, ein Vergleichsoperator z. B. `=` oder `<>` zurückgeben können `Boolean` auch, wenn keiner der Operanden ist `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="77ab6-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>  
  
## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="77ab6-185">Logische und bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="77ab6-185">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="77ab6-186">Die `And`, `Or`, `Not`, und `Xor` Operatoren können in Visual Basic logische oder bitweise Operationen durchführen.</span><span class="sxs-lookup"><span data-stu-id="77ab6-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="77ab6-187">Wenn Sie einer dieser Operatoren für eine Klasse oder Struktur definieren, können Sie nur die bitweise Operation definieren.</span><span class="sxs-lookup"><span data-stu-id="77ab6-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>  
  
 <span data-ttu-id="77ab6-188">Keine definieren die `AndAlso` Operator direkt mit einem `Operator` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="77ab6-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="77ab6-189">Sie können jedoch `AndAlso` , wenn Sie die folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="77ab6-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>  
  
-   <span data-ttu-id="77ab6-190">Sie haben definiert `And` auf den gleichen Operandentypen, die Sie verwenden möchten `AndAlso`.</span><span class="sxs-lookup"><span data-stu-id="77ab6-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>  
  
-   <span data-ttu-id="77ab6-191">Die Definition der `And` gibt denselben Typ wie die Klasse oder Struktur, auf dem Sie sie definiert haben.</span><span class="sxs-lookup"><span data-stu-id="77ab6-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>  
  
-   <span data-ttu-id="77ab6-192">Sie haben definiert die `IsFalse` Operator für die Klasse oder Struktur, auf dem Sie definiert haben `And`.</span><span class="sxs-lookup"><span data-stu-id="77ab6-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>  
  
 <span data-ttu-id="77ab6-193">Auf ähnliche Weise können Sie `OrElse` Wenn Sie definiert haben `Or` auf die gleichen Operanden mit dem Rückgabetyp der Klasse oder Struktur, und Sie definiertes `IsTrue` für die Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="77ab6-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>  
  
## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="77ab6-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="77ab6-194">Widening and Narrowing Conversions</span></span>  
 <span data-ttu-id="77ab6-195">Ein *erweiternde Konvertierung* ist zur Laufzeit immer erfolgreich, während eine *einschränkende Konvertierung* kann zur Laufzeit fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="77ab6-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="77ab6-196">Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="77ab6-196">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
 <span data-ttu-id="77ab6-197">Wenn Sie eine Konvertierungsprozedur deklarieren `Widening`, Prozedurcode muss keine Fehler generieren.</span><span class="sxs-lookup"><span data-stu-id="77ab6-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="77ab6-198">Dies bedeutet Folgendes:</span><span class="sxs-lookup"><span data-stu-id="77ab6-198">This means the following:</span></span>  
  
-   <span data-ttu-id="77ab6-199">Sie muss immer einen gültigen Wert des Typs zurückgeben `type`.</span><span class="sxs-lookup"><span data-stu-id="77ab6-199">It must always return a valid value of type `type`.</span></span>  
  
-   <span data-ttu-id="77ab6-200">Es muss alle möglichen Ausnahmen und andere fehlerbedingungen behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="77ab6-200">It must handle all possible exceptions and other error conditions.</span></span>  
  
-   <span data-ttu-id="77ab6-201">Sie müssen jeden zurückgegebenen Fehler von alle Prozeduren behandeln, die aufruft.</span><span class="sxs-lookup"><span data-stu-id="77ab6-201">It must handle any error returns from any procedures it calls.</span></span>  
  
 <span data-ttu-id="77ab6-202">Wenn eine Möglichkeit besteht, die eine Konvertierungsprozedur nicht erfolgreich ausgeführt werden kann, oder die It dazu führen, eine nicht behandelte Ausnahme dass kann, müssen Sie deklarieren, werden `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="77ab6-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77ab6-203">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77ab6-203">Example</span></span>  
 <span data-ttu-id="77ab6-204">Im folgenden Codebeispiel wird mit der `Operator` Anweisung, um das Gerüst für eine Struktur definieren, die Operatorprozeduren für enthält die `And`, `Or`, `IsFalse`, und `IsTrue` Operatoren.</span><span class="sxs-lookup"><span data-stu-id="77ab6-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="77ab6-205">`And` und `Or` akzeptieren jeweils zwei Operanden vom Typ `abc` und dem Rückgabetyp `abc`.</span><span class="sxs-lookup"><span data-stu-id="77ab6-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="77ab6-206">`IsFalse` und `IsTrue` akzeptieren jeweils einen einzelnen Operanden vom Typ `abc` und zurückgeben `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="77ab6-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="77ab6-207">Diese Definitionen ermöglicht werden, den aufrufenden Code mit `And`, `AndAlso`, `Or`, und `OrElse` mit Operanden vom Typ `abc`.</span><span class="sxs-lookup"><span data-stu-id="77ab6-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>  
  
 [!code-vb[VbVbalrStatements#44](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/operator-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="77ab6-208">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77ab6-208">See Also</span></span>  
 [<span data-ttu-id="77ab6-209">IsFalse-Operator</span><span class="sxs-lookup"><span data-stu-id="77ab6-209">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [<span data-ttu-id="77ab6-210">IsTrue-Operator</span><span class="sxs-lookup"><span data-stu-id="77ab6-210">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [<span data-ttu-id="77ab6-211">Widening</span><span class="sxs-lookup"><span data-stu-id="77ab6-211">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="77ab6-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="77ab6-212">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="77ab6-213">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="77ab6-213">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="77ab6-214">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="77ab6-214">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="77ab6-215">Gewusst wie: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="77ab6-215">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="77ab6-216">Gewusst wie: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="77ab6-216">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="77ab6-217">Gewusst wie: Aufrufen einer Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="77ab6-217">How to: Call an Operator Procedure</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="77ab6-218">Gewusst wie: Verwenden einer Klasse, die Operatoren definiert</span><span class="sxs-lookup"><span data-stu-id="77ab6-218">How to: Use a Class that Defines Operators</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
