---
title: Operator-Anweisung (Visual Basic)
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
ms.openlocfilehash: 69dea99cf71bd1e091116e54e244abfca291ffdb
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45589442"
---
# <a name="operator-statement"></a><span data-ttu-id="a13c5-102">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="a13c5-102">Operator Statement</span></span>
<span data-ttu-id="a13c5-103">Deklariert das Operatorsymbol, Operanden und Code, der eine Operatorprozedur für eine Klasse oder Struktur definieren.</span><span class="sxs-lookup"><span data-stu-id="a13c5-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a13c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a13c5-104">Syntax</span></span>  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## <a name="parts"></a><span data-ttu-id="a13c5-105">Teile</span><span class="sxs-lookup"><span data-stu-id="a13c5-105">Parts</span></span>  
 `attrlist`  
 <span data-ttu-id="a13c5-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a13c5-106">Optional.</span></span> <span data-ttu-id="a13c5-107">Finden Sie unter [Liste](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="a13c5-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `Public`  
 <span data-ttu-id="a13c5-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a13c5-108">Required.</span></span> <span data-ttu-id="a13c5-109">Gibt an, dass die Operatorprozedur [öffentliche](../../../visual-basic/language-reference/modifiers/public.md) Zugriff.</span><span class="sxs-lookup"><span data-stu-id="a13c5-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span>  
  
 `Overloads`  
 <span data-ttu-id="a13c5-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a13c5-110">Optional.</span></span> <span data-ttu-id="a13c5-111">Finden Sie unter [Überladungen](../../../visual-basic/language-reference/modifiers/overloads.md).</span><span class="sxs-lookup"><span data-stu-id="a13c5-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span></span>  
  
 `Shared`  
 <span data-ttu-id="a13c5-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a13c5-112">Required.</span></span> <span data-ttu-id="a13c5-113">Gibt an, dass die Operatorprozedur eine [Shared](../../../visual-basic/language-reference/modifiers/shared.md) Verfahren.</span><span class="sxs-lookup"><span data-stu-id="a13c5-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span></span>  
  
 `Shadows`  
 <span data-ttu-id="a13c5-114">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a13c5-114">Optional.</span></span> <span data-ttu-id="a13c5-115">Finden Sie unter [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="a13c5-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
 `Widening`  
 <span data-ttu-id="a13c5-116">Für einen Konvertierungsoperator erforderlich, es sei denn, Sie geben `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="a13c5-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="a13c5-117">Gibt an, dass die Operatorprozedur definiert eine [Widening](../../../visual-basic/language-reference/modifiers/widening.md) Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="a13c5-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span></span> <span data-ttu-id="a13c5-118">Finden Sie unter "Erweiterungskonvertierungen und einschränkende Konvertierungen", auf dieser Hilfeseite.</span><span class="sxs-lookup"><span data-stu-id="a13c5-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `Narrowing`  
 <span data-ttu-id="a13c5-119">Für einen Konvertierungsoperator erforderlich, es sei denn, Sie geben `Widening`.</span><span class="sxs-lookup"><span data-stu-id="a13c5-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="a13c5-120">Gibt an, dass die Operatorprozedur definiert eine [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="a13c5-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="a13c5-121">Finden Sie unter "Erweiterungskonvertierungen und einschränkende Konvertierungen", auf dieser Hilfeseite.</span><span class="sxs-lookup"><span data-stu-id="a13c5-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `operatorsymbol`  
 <span data-ttu-id="a13c5-122">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a13c5-122">Required.</span></span> <span data-ttu-id="a13c5-123">Das Symbol oder die ID des Operators, der die Operatorprozedur definiert.</span><span class="sxs-lookup"><span data-stu-id="a13c5-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>  
  
 `operand1`  
 <span data-ttu-id="a13c5-124">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a13c5-124">Required.</span></span> <span data-ttu-id="a13c5-125">Der Name und Typ der einzigen Operanden eines unären Operators (einschließlich eines Konvertierungsoperators) oder der linke Operand eines binären Operators.</span><span class="sxs-lookup"><span data-stu-id="a13c5-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>  
  
 `operand2`  
 <span data-ttu-id="a13c5-126">Für binäre Operatoren erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a13c5-126">Required for binary operators.</span></span> <span data-ttu-id="a13c5-127">Der Name und Typ des rechten Operanden eines binären Operators.</span><span class="sxs-lookup"><span data-stu-id="a13c5-127">The name and type of the right operand of a binary operator.</span></span>  
  
 <span data-ttu-id="a13c5-128">`operand1` und `operand2` haben die folgende Syntax und Bestandteile:</span><span class="sxs-lookup"><span data-stu-id="a13c5-128">`operand1` and `operand2` have the following syntax and parts:</span></span>  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|<span data-ttu-id="a13c5-129">Segment</span><span class="sxs-lookup"><span data-stu-id="a13c5-129">Part</span></span>|<span data-ttu-id="a13c5-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a13c5-130">Description</span></span>|  
|----------|-----------------|  
|`ByVal`|<span data-ttu-id="a13c5-131">Optional, doch dem Übergabemechanismus muss [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="a13c5-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>|  
|`operandname`|<span data-ttu-id="a13c5-132">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a13c5-132">Required.</span></span> <span data-ttu-id="a13c5-133">Name der Variablen, die diesen Operanden darstellt.</span><span class="sxs-lookup"><span data-stu-id="a13c5-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="a13c5-134">Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="a13c5-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`operandtype`|<span data-ttu-id="a13c5-135">Optional, wenn `Option Strict` ist `On`.</span><span class="sxs-lookup"><span data-stu-id="a13c5-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="a13c5-136">Der Datentyp dieses Operanden.</span><span class="sxs-lookup"><span data-stu-id="a13c5-136">Data type of this operand.</span></span>|  
  
 `type`  
 <span data-ttu-id="a13c5-137">Optional, wenn `Option Strict` ist `On`.</span><span class="sxs-lookup"><span data-stu-id="a13c5-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="a13c5-138">Datentyp des Werts die Operatorprozedur gibt.</span><span class="sxs-lookup"><span data-stu-id="a13c5-138">Data type of the value the operator procedure returns.</span></span>  
  
 `statements`  
 <span data-ttu-id="a13c5-139">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a13c5-139">Optional.</span></span> <span data-ttu-id="a13c5-140">Der Block von Anweisungen, die sich die Operatorprozedur ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a13c5-140">Block of statements that the operator procedure runs.</span></span>  
  
 `returnvalue`  
 <span data-ttu-id="a13c5-141">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a13c5-141">Required.</span></span> <span data-ttu-id="a13c5-142">Der Wert, den die Operatorprozedur an den aufrufenden Code zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a13c5-142">The value that the operator procedure returns to the calling code.</span></span>  
  
 <span data-ttu-id="a13c5-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="a13c5-143">`End` `Operator`</span></span>  
 <span data-ttu-id="a13c5-144">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a13c5-144">Required.</span></span> <span data-ttu-id="a13c5-145">Beendet die Definition die Operatorprozedur an.</span><span class="sxs-lookup"><span data-stu-id="a13c5-145">Terminates the definition of this operator procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a13c5-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a13c5-146">Remarks</span></span>  
 <span data-ttu-id="a13c5-147">Sie können `Operator` nur in einer Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="a13c5-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="a13c5-148">Dies bedeutet, dass die *Deklarationskontext* ein Operator kann nicht aus einer Quelldatei, Namespace, Modul, Schnittstelle, Prozedur oder Block sein.</span><span class="sxs-lookup"><span data-stu-id="a13c5-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="a13c5-149">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a13c5-149">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="a13c5-150">Alle Operatoren muss `Public Shared`.</span><span class="sxs-lookup"><span data-stu-id="a13c5-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="a13c5-151">Sie können keine angeben `ByRef`, `Optional`, oder `ParamArray` für beide Operanden.</span><span class="sxs-lookup"><span data-stu-id="a13c5-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>  
  
 <span data-ttu-id="a13c5-152">Sie können nicht das Symbol "Operator" oder einen Bezeichner verwenden, zum Speichern eines Werts zurück.</span><span class="sxs-lookup"><span data-stu-id="a13c5-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="a13c5-153">Verwenden Sie die `Return` -Anweisung, und sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="a13c5-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="a13c5-154">Eine beliebige Anzahl von `Return` Anweisungen können an beliebiger Stelle in der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="a13c5-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>  
  
 <span data-ttu-id="a13c5-155">Definieren einen Operator auf diese Weise wird aufgerufen, *operatorüberladung*, unabhängig davon, ob Sie verwenden die `Overloads` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="a13c5-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="a13c5-156">In der folgenden Tabelle sind die Operatoren aufgelistet, die Sie definieren können.</span><span class="sxs-lookup"><span data-stu-id="a13c5-156">The following table lists the operators you can define.</span></span>  
  
|<span data-ttu-id="a13c5-157">Typ</span><span class="sxs-lookup"><span data-stu-id="a13c5-157">Type</span></span>|<span data-ttu-id="a13c5-158">Operatoren</span><span class="sxs-lookup"><span data-stu-id="a13c5-158">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="a13c5-159">Unär</span><span class="sxs-lookup"><span data-stu-id="a13c5-159">Unary</span></span>|<span data-ttu-id="a13c5-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="a13c5-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="a13c5-161">Binär</span><span class="sxs-lookup"><span data-stu-id="a13c5-161">Binary</span></span>|<span data-ttu-id="a13c5-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="a13c5-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="a13c5-163">Konvertierung (unär)</span><span class="sxs-lookup"><span data-stu-id="a13c5-163">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="a13c5-164">Beachten Sie, dass die `=` Operator in der binären Liste wird der Vergleichsoperator, der nicht der Zuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="a13c5-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="a13c5-165">Beim Definieren von `CType`, geben Sie `Widening` oder `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="a13c5-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>  
  
## <a name="matched-pairs"></a><span data-ttu-id="a13c5-166">Passende Paare</span><span class="sxs-lookup"><span data-stu-id="a13c5-166">Matched Pairs</span></span>  
 <span data-ttu-id="a13c5-167">Sie müssen bestimmte Operatoren als zueinander passende Paare definieren.</span><span class="sxs-lookup"><span data-stu-id="a13c5-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="a13c5-168">Wenn Sie einen Operator eines solch ein paar definieren, müssen Sie die andere ebenfalls definieren.</span><span class="sxs-lookup"><span data-stu-id="a13c5-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="a13c5-169">Die übereinstimmende Paare lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a13c5-169">The matched pairs are the following:</span></span>  
  
-   <span data-ttu-id="a13c5-170">`=` und `<>`</span><span class="sxs-lookup"><span data-stu-id="a13c5-170">`=` and `<>`</span></span>  
  
-   <span data-ttu-id="a13c5-171">`>` und `<`</span><span class="sxs-lookup"><span data-stu-id="a13c5-171">`>` and `<`</span></span>  
  
-   <span data-ttu-id="a13c5-172">`>=` und `<=`</span><span class="sxs-lookup"><span data-stu-id="a13c5-172">`>=` and `<=`</span></span>  
  
-   <span data-ttu-id="a13c5-173">`IsTrue` und `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="a13c5-173">`IsTrue` and `IsFalse`</span></span>  
  
## <a name="data-type-restrictions"></a><span data-ttu-id="a13c5-174">Datentypeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="a13c5-174">Data Type Restrictions</span></span>  
 <span data-ttu-id="a13c5-175">Die Klasse oder Struktur, auf dem Sie sie definieren, muss jeder Operator, die Sie definieren umfassen.</span><span class="sxs-lookup"><span data-stu-id="a13c5-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="a13c5-176">Dies bedeutet, dass die Klasse oder Struktur mit dem Datentyp der folgenden angezeigt werden muss:</span><span class="sxs-lookup"><span data-stu-id="a13c5-176">This means that the class or structure must appear as the data type of the following:</span></span>  
  
-   <span data-ttu-id="a13c5-177">Der Operand eines unären Operators.</span><span class="sxs-lookup"><span data-stu-id="a13c5-177">The operand of a unary operator.</span></span>  
  
-   <span data-ttu-id="a13c5-178">Mindestens einer der Operanden des binären Operators.</span><span class="sxs-lookup"><span data-stu-id="a13c5-178">At least one of the operands of a binary operator.</span></span>  
  
-   <span data-ttu-id="a13c5-179">Der Operand oder der Rückgabetyp eines Konvertierungsoperators.</span><span class="sxs-lookup"><span data-stu-id="a13c5-179">Either the operand or the return type of a conversion operator.</span></span>  
  
 <span data-ttu-id="a13c5-180">Bestimmte Operatoren haben zusätzliche Daten, die Einschränkungen, geben Sie wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a13c5-180">Certain operators have additional data type restrictions, as follows:</span></span>  
  
-   <span data-ttu-id="a13c5-181">Wenn Sie definieren die `IsTrue` und `IsFalse` Operatoren müssen beide Zurückgeben der `Boolean` Typ.</span><span class="sxs-lookup"><span data-stu-id="a13c5-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>  
  
-   <span data-ttu-id="a13c5-182">Wenn Sie definieren die `<<` und `>>` Operatoren müssen beide angeben der `Integer` Geben Sie für die `operandtype` von `operand2`.</span><span class="sxs-lookup"><span data-stu-id="a13c5-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>  
  
 <span data-ttu-id="a13c5-183">Der Rückgabetyp muss nicht in den Typ der Operanden entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a13c5-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="a13c5-184">Angenommen, ein Vergleichsoperator z. B. `=` oder `<>` können zurückgeben `Boolean` auch, wenn keiner der Operanden ist `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="a13c5-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>  
  
## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="a13c5-185">Logische und bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="a13c5-185">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="a13c5-186">Die `And`, `Or`, `Not`, und `Xor` Operatoren können logische oder bitweise Operationen in Visual Basic durchführen.</span><span class="sxs-lookup"><span data-stu-id="a13c5-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="a13c5-187">Wenn Sie einen der folgenden Operatoren in einer Klasse oder Struktur definieren, können Sie jedoch nur die bitweise Operation definieren.</span><span class="sxs-lookup"><span data-stu-id="a13c5-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>  
  
 <span data-ttu-id="a13c5-188">Keine definieren die `AndAlso` Operator direkt mit einem `Operator` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a13c5-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="a13c5-189">Sie können jedoch `AndAlso` , wenn Sie die folgenden Bedingungen erfüllt haben:</span><span class="sxs-lookup"><span data-stu-id="a13c5-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>  
  
-   <span data-ttu-id="a13c5-190">Sie definiert haben `And` auf den gleichen Operandentypen, die Sie für die verwenden möchten `AndAlso`.</span><span class="sxs-lookup"><span data-stu-id="a13c5-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>  
  
-   <span data-ttu-id="a13c5-191">Die Definition der `And` gibt denselben Typ wie die Klasse oder Struktur, auf dem Sie es definiert haben.</span><span class="sxs-lookup"><span data-stu-id="a13c5-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>  
  
-   <span data-ttu-id="a13c5-192">Sie definiert haben die `IsFalse` Operator für die Klasse oder Struktur, auf dem Sie definiert haben `And`.</span><span class="sxs-lookup"><span data-stu-id="a13c5-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>  
  
 <span data-ttu-id="a13c5-193">Auf ähnliche Weise können Sie `OrElse` , wenn Sie definiert haben `Or` auf die gleichen Operanden, mit dem Rückgabetyp von der Klasse oder Struktur, und Sie haben definiert `IsTrue` für die Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="a13c5-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>  
  
## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="a13c5-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="a13c5-194">Widening and Narrowing Conversions</span></span>  
 <span data-ttu-id="a13c5-195">Ein *eine erweiternde Konvertierung* immer erfolgreich, zur Laufzeit, während eine *einschränkende Konvertierung* zur Laufzeit Fehler verursachen können.</span><span class="sxs-lookup"><span data-stu-id="a13c5-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="a13c5-196">Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="a13c5-196">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
 <span data-ttu-id="a13c5-197">Wenn Sie eine Konvertierungsprozedur deklarieren `Widening`, Ihren Prozedurcode muss keine Fehler generieren.</span><span class="sxs-lookup"><span data-stu-id="a13c5-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="a13c5-198">Dies bedeutet Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a13c5-198">This means the following:</span></span>  
  
-   <span data-ttu-id="a13c5-199">Sie muss immer einen gültigen Wert des Typs zurückgeben `type`.</span><span class="sxs-lookup"><span data-stu-id="a13c5-199">It must always return a valid value of type `type`.</span></span>  
  
-   <span data-ttu-id="a13c5-200">Sie müssen alle möglichen Ausnahmen und andere Fehler behandeln.</span><span class="sxs-lookup"><span data-stu-id="a13c5-200">It must handle all possible exceptions and other error conditions.</span></span>  
  
-   <span data-ttu-id="a13c5-201">Sie müssen jeden zurückgegebenen Fehler aus allen Prozeduren behandeln, die er aufruft.</span><span class="sxs-lookup"><span data-stu-id="a13c5-201">It must handle any error returns from any procedures it calls.</span></span>  
  
 <span data-ttu-id="a13c5-202">Wenn eine Möglichkeit besteht, die eine Konvertierungsprozedur nicht erfolgreich ausgeführt werden kann, oder die It dazu führen, eine nicht behandelte Ausnahme dass kann, müssen Sie es deklarieren `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="a13c5-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a13c5-203">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a13c5-203">Example</span></span>  
 <span data-ttu-id="a13c5-204">Im folgenden Codebeispiel wird die `Operator` Anweisung, um das Gerüst für eine Struktur definieren, die Operatorprozeduren für umfasst die `And`, `Or`, `IsFalse`, und `IsTrue` Operatoren.</span><span class="sxs-lookup"><span data-stu-id="a13c5-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="a13c5-205">`And` und `Or` akzeptieren jeweils zwei Operanden vom Typ `abc` und den Rückgabetyp `abc`.</span><span class="sxs-lookup"><span data-stu-id="a13c5-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="a13c5-206">`IsFalse` und `IsTrue` akzeptieren jeweils einen einzelnen Operanden vom Typ `abc` und zurückgeben `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="a13c5-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="a13c5-207">Diese Definitionen ermöglicht werden, den aufrufenden Code mit `And`, `AndAlso`, `Or`, und `OrElse` mit Operanden vom Typ `abc`.</span><span class="sxs-lookup"><span data-stu-id="a13c5-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>  
  
 [!code-vb[VbVbalrStatements#44](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/operator-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a13c5-208">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a13c5-208">See Also</span></span>  
 [<span data-ttu-id="a13c5-209">IsFalse-Operator</span><span class="sxs-lookup"><span data-stu-id="a13c5-209">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [<span data-ttu-id="a13c5-210">IsTrue-Operator</span><span class="sxs-lookup"><span data-stu-id="a13c5-210">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [<span data-ttu-id="a13c5-211">Widening</span><span class="sxs-lookup"><span data-stu-id="a13c5-211">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="a13c5-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="a13c5-212">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="a13c5-213">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="a13c5-213">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="a13c5-214">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="a13c5-214">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="a13c5-215">Gewusst wie: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="a13c5-215">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="a13c5-216">Gewusst wie: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="a13c5-216">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="a13c5-217">Gewusst wie: Aufrufen einer Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="a13c5-217">How to: Call an Operator Procedure</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="a13c5-218">Gewusst wie: Verwenden einer Klasse, die Operatoren definiert</span><span class="sxs-lookup"><span data-stu-id="a13c5-218">How to: Use a Class that Defines Operators</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
