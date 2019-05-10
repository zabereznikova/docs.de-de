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
ms.openlocfilehash: 4162f7cb5d8b89a1e5e8e7db429cf4e8dd9b700a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64583596"
---
# <a name="operator-statement"></a><span data-ttu-id="5d501-102">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="5d501-102">Operator Statement</span></span>
<span data-ttu-id="5d501-103">Deklariert das Operatorsymbol, Operanden und Code, der eine Operatorprozedur für eine Klasse oder Struktur definieren.</span><span class="sxs-lookup"><span data-stu-id="5d501-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d501-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d501-104">Syntax</span></span>  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## <a name="parts"></a><span data-ttu-id="5d501-105">Teile</span><span class="sxs-lookup"><span data-stu-id="5d501-105">Parts</span></span>  
 `attrlist`  
 <span data-ttu-id="5d501-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="5d501-106">Optional.</span></span> <span data-ttu-id="5d501-107">Finden Sie unter [Liste](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="5d501-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `Public`  
 <span data-ttu-id="5d501-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5d501-108">Required.</span></span> <span data-ttu-id="5d501-109">Gibt an, dass die Operatorprozedur [öffentliche](../../../visual-basic/language-reference/modifiers/public.md) Zugriff.</span><span class="sxs-lookup"><span data-stu-id="5d501-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span>  
  
 `Overloads`  
 <span data-ttu-id="5d501-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="5d501-110">Optional.</span></span> <span data-ttu-id="5d501-111">Finden Sie unter [Überladungen](../../../visual-basic/language-reference/modifiers/overloads.md).</span><span class="sxs-lookup"><span data-stu-id="5d501-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span></span>  
  
 `Shared`  
 <span data-ttu-id="5d501-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5d501-112">Required.</span></span> <span data-ttu-id="5d501-113">Gibt an, dass die Operatorprozedur eine [Shared](../../../visual-basic/language-reference/modifiers/shared.md) Verfahren.</span><span class="sxs-lookup"><span data-stu-id="5d501-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span></span>  
  
 `Shadows`  
 <span data-ttu-id="5d501-114">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="5d501-114">Optional.</span></span> <span data-ttu-id="5d501-115">Finden Sie unter [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="5d501-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
 `Widening`  
 <span data-ttu-id="5d501-116">Für einen Konvertierungsoperator erforderlich, es sei denn, Sie geben `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="5d501-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="5d501-117">Gibt an, dass die Operatorprozedur definiert eine [Widening](../../../visual-basic/language-reference/modifiers/widening.md) Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="5d501-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span></span> <span data-ttu-id="5d501-118">Finden Sie unter "Erweiterungskonvertierungen und einschränkende Konvertierungen", auf dieser Hilfeseite.</span><span class="sxs-lookup"><span data-stu-id="5d501-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `Narrowing`  
 <span data-ttu-id="5d501-119">Für einen Konvertierungsoperator erforderlich, es sei denn, Sie geben `Widening`.</span><span class="sxs-lookup"><span data-stu-id="5d501-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="5d501-120">Gibt an, dass die Operatorprozedur definiert eine [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="5d501-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="5d501-121">Finden Sie unter "Erweiterungskonvertierungen und einschränkende Konvertierungen", auf dieser Hilfeseite.</span><span class="sxs-lookup"><span data-stu-id="5d501-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `operatorsymbol`  
 <span data-ttu-id="5d501-122">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5d501-122">Required.</span></span> <span data-ttu-id="5d501-123">Das Symbol oder die ID des Operators, der die Operatorprozedur definiert.</span><span class="sxs-lookup"><span data-stu-id="5d501-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>  
  
 `operand1`  
 <span data-ttu-id="5d501-124">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5d501-124">Required.</span></span> <span data-ttu-id="5d501-125">Der Name und Typ der einzigen Operanden eines unären Operators (einschließlich eines Konvertierungsoperators) oder der linke Operand eines binären Operators.</span><span class="sxs-lookup"><span data-stu-id="5d501-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>  
  
 `operand2`  
 <span data-ttu-id="5d501-126">Für binäre Operatoren erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5d501-126">Required for binary operators.</span></span> <span data-ttu-id="5d501-127">Der Name und Typ des rechten Operanden eines binären Operators.</span><span class="sxs-lookup"><span data-stu-id="5d501-127">The name and type of the right operand of a binary operator.</span></span>  
  
 <span data-ttu-id="5d501-128">`operand1` und `operand2` haben die folgende Syntax und Bestandteile:</span><span class="sxs-lookup"><span data-stu-id="5d501-128">`operand1` and `operand2` have the following syntax and parts:</span></span>  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|<span data-ttu-id="5d501-129">Segment</span><span class="sxs-lookup"><span data-stu-id="5d501-129">Part</span></span>|<span data-ttu-id="5d501-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d501-130">Description</span></span>|  
|----------|-----------------|  
|`ByVal`|<span data-ttu-id="5d501-131">Optional, doch dem Übergabemechanismus muss [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="5d501-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>|  
|`operandname`|<span data-ttu-id="5d501-132">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5d501-132">Required.</span></span> <span data-ttu-id="5d501-133">Name der Variablen, die diesen Operanden darstellt.</span><span class="sxs-lookup"><span data-stu-id="5d501-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="5d501-134">Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="5d501-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`operandtype`|<span data-ttu-id="5d501-135">Optional, wenn `Option Strict` ist `On`.</span><span class="sxs-lookup"><span data-stu-id="5d501-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="5d501-136">Der Datentyp dieses Operanden.</span><span class="sxs-lookup"><span data-stu-id="5d501-136">Data type of this operand.</span></span>|  
  
 `type`  
 <span data-ttu-id="5d501-137">Optional, wenn `Option Strict` ist `On`.</span><span class="sxs-lookup"><span data-stu-id="5d501-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="5d501-138">Datentyp des Werts die Operatorprozedur gibt.</span><span class="sxs-lookup"><span data-stu-id="5d501-138">Data type of the value the operator procedure returns.</span></span>  
  
 `statements`  
 <span data-ttu-id="5d501-139">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="5d501-139">Optional.</span></span> <span data-ttu-id="5d501-140">Der Block von Anweisungen, die sich die Operatorprozedur ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5d501-140">Block of statements that the operator procedure runs.</span></span>  
  
 `returnvalue`  
 <span data-ttu-id="5d501-141">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5d501-141">Required.</span></span> <span data-ttu-id="5d501-142">Der Wert, den die Operatorprozedur an den aufrufenden Code zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5d501-142">The value that the operator procedure returns to the calling code.</span></span>  
  
 <span data-ttu-id="5d501-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="5d501-143">`End` `Operator`</span></span>  
 <span data-ttu-id="5d501-144">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5d501-144">Required.</span></span> <span data-ttu-id="5d501-145">Beendet die Definition die Operatorprozedur an.</span><span class="sxs-lookup"><span data-stu-id="5d501-145">Terminates the definition of this operator procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d501-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d501-146">Remarks</span></span>  
 <span data-ttu-id="5d501-147">Sie können `Operator` nur in einer Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="5d501-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="5d501-148">Dies bedeutet, dass die *Deklarationskontext* ein Operator kann nicht aus einer Quelldatei, Namespace, Modul, Schnittstelle, Prozedur oder Block sein.</span><span class="sxs-lookup"><span data-stu-id="5d501-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="5d501-149">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="5d501-149">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="5d501-150">Alle Operatoren muss `Public Shared`.</span><span class="sxs-lookup"><span data-stu-id="5d501-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="5d501-151">Sie können keine angeben `ByRef`, `Optional`, oder `ParamArray` für beide Operanden.</span><span class="sxs-lookup"><span data-stu-id="5d501-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>  
  
 <span data-ttu-id="5d501-152">Sie können nicht das Symbol "Operator" oder einen Bezeichner verwenden, zum Speichern eines Werts zurück.</span><span class="sxs-lookup"><span data-stu-id="5d501-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="5d501-153">Verwenden Sie die `Return` -Anweisung, und sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="5d501-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="5d501-154">Eine beliebige Anzahl von `Return` Anweisungen können an beliebiger Stelle in der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="5d501-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>  
  
 <span data-ttu-id="5d501-155">Definieren einen Operator auf diese Weise wird aufgerufen, *operatorüberladung*, unabhängig davon, ob Sie verwenden die `Overloads` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="5d501-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="5d501-156">In der folgenden Tabelle sind die Operatoren aufgelistet, die Sie definieren können.</span><span class="sxs-lookup"><span data-stu-id="5d501-156">The following table lists the operators you can define.</span></span>  
  
|<span data-ttu-id="5d501-157">Typ</span><span class="sxs-lookup"><span data-stu-id="5d501-157">Type</span></span>|<span data-ttu-id="5d501-158">Operatoren</span><span class="sxs-lookup"><span data-stu-id="5d501-158">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="5d501-159">Unär</span><span class="sxs-lookup"><span data-stu-id="5d501-159">Unary</span></span>|<span data-ttu-id="5d501-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="5d501-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="5d501-161">Binär</span><span class="sxs-lookup"><span data-stu-id="5d501-161">Binary</span></span>|<span data-ttu-id="5d501-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="5d501-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="5d501-163">Konvertierung (unär)</span><span class="sxs-lookup"><span data-stu-id="5d501-163">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="5d501-164">Beachten Sie, dass die `=` Operator in der binären Liste wird der Vergleichsoperator, der nicht der Zuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="5d501-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="5d501-165">Beim Definieren von `CType`, geben Sie `Widening` oder `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="5d501-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>  
  
## <a name="matched-pairs"></a><span data-ttu-id="5d501-166">Passende Paare</span><span class="sxs-lookup"><span data-stu-id="5d501-166">Matched Pairs</span></span>  
 <span data-ttu-id="5d501-167">Sie müssen bestimmte Operatoren als zueinander passende Paare definieren.</span><span class="sxs-lookup"><span data-stu-id="5d501-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="5d501-168">Wenn Sie einen Operator eines solch ein paar definieren, müssen Sie die andere ebenfalls definieren.</span><span class="sxs-lookup"><span data-stu-id="5d501-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="5d501-169">Die übereinstimmende Paare lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5d501-169">The matched pairs are the following:</span></span>  
  
- <span data-ttu-id="5d501-170">`=` und `<>`</span><span class="sxs-lookup"><span data-stu-id="5d501-170">`=` and `<>`</span></span>  
  
- <span data-ttu-id="5d501-171">`>` und `<`</span><span class="sxs-lookup"><span data-stu-id="5d501-171">`>` and `<`</span></span>  
  
- <span data-ttu-id="5d501-172">`>=` und `<=`</span><span class="sxs-lookup"><span data-stu-id="5d501-172">`>=` and `<=`</span></span>  
  
- <span data-ttu-id="5d501-173">`IsTrue` und `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="5d501-173">`IsTrue` and `IsFalse`</span></span>  
  
## <a name="data-type-restrictions"></a><span data-ttu-id="5d501-174">Datentypeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="5d501-174">Data Type Restrictions</span></span>  
 <span data-ttu-id="5d501-175">Die Klasse oder Struktur, auf dem Sie sie definieren, muss jeder Operator, die Sie definieren umfassen.</span><span class="sxs-lookup"><span data-stu-id="5d501-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="5d501-176">Dies bedeutet, dass die Klasse oder Struktur mit dem Datentyp der folgenden angezeigt werden muss:</span><span class="sxs-lookup"><span data-stu-id="5d501-176">This means that the class or structure must appear as the data type of the following:</span></span>  
  
- <span data-ttu-id="5d501-177">Der Operand eines unären Operators.</span><span class="sxs-lookup"><span data-stu-id="5d501-177">The operand of a unary operator.</span></span>  
  
- <span data-ttu-id="5d501-178">Mindestens einer der Operanden des binären Operators.</span><span class="sxs-lookup"><span data-stu-id="5d501-178">At least one of the operands of a binary operator.</span></span>  
  
- <span data-ttu-id="5d501-179">Der Operand oder der Rückgabetyp eines Konvertierungsoperators.</span><span class="sxs-lookup"><span data-stu-id="5d501-179">Either the operand or the return type of a conversion operator.</span></span>  
  
 <span data-ttu-id="5d501-180">Bestimmte Operatoren haben zusätzliche Daten, die Einschränkungen, geben Sie wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5d501-180">Certain operators have additional data type restrictions, as follows:</span></span>  
  
- <span data-ttu-id="5d501-181">Wenn Sie definieren die `IsTrue` und `IsFalse` Operatoren müssen beide Zurückgeben der `Boolean` Typ.</span><span class="sxs-lookup"><span data-stu-id="5d501-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>  
  
- <span data-ttu-id="5d501-182">Wenn Sie definieren die `<<` und `>>` Operatoren müssen beide angeben der `Integer` Geben Sie für die `operandtype` von `operand2`.</span><span class="sxs-lookup"><span data-stu-id="5d501-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>  
  
 <span data-ttu-id="5d501-183">Der Rückgabetyp muss nicht in den Typ der Operanden entsprechen.</span><span class="sxs-lookup"><span data-stu-id="5d501-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="5d501-184">Angenommen, ein Vergleichsoperator z. B. `=` oder `<>` können zurückgeben `Boolean` auch, wenn keiner der Operanden ist `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5d501-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>  
  
## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="5d501-185">Logische und bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="5d501-185">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="5d501-186">Die `And`, `Or`, `Not`, und `Xor` Operatoren können logische oder bitweise Operationen in Visual Basic durchführen.</span><span class="sxs-lookup"><span data-stu-id="5d501-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="5d501-187">Wenn Sie einen der folgenden Operatoren in einer Klasse oder Struktur definieren, können Sie jedoch nur die bitweise Operation definieren.</span><span class="sxs-lookup"><span data-stu-id="5d501-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>  
  
 <span data-ttu-id="5d501-188">Keine definieren die `AndAlso` Operator direkt mit einem `Operator` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="5d501-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="5d501-189">Sie können jedoch `AndAlso` , wenn Sie die folgenden Bedingungen erfüllt haben:</span><span class="sxs-lookup"><span data-stu-id="5d501-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>  
  
- <span data-ttu-id="5d501-190">Sie definiert haben `And` auf den gleichen Operandentypen, die Sie für die verwenden möchten `AndAlso`.</span><span class="sxs-lookup"><span data-stu-id="5d501-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>  
  
- <span data-ttu-id="5d501-191">Die Definition der `And` gibt denselben Typ wie die Klasse oder Struktur, auf dem Sie es definiert haben.</span><span class="sxs-lookup"><span data-stu-id="5d501-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>  
  
- <span data-ttu-id="5d501-192">Sie definiert haben die `IsFalse` Operator für die Klasse oder Struktur, auf dem Sie definiert haben `And`.</span><span class="sxs-lookup"><span data-stu-id="5d501-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>  
  
 <span data-ttu-id="5d501-193">Auf ähnliche Weise können Sie `OrElse` , wenn Sie definiert haben `Or` auf die gleichen Operanden, mit dem Rückgabetyp von der Klasse oder Struktur, und Sie haben definiert `IsTrue` für die Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="5d501-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>  
  
## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="5d501-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="5d501-194">Widening and Narrowing Conversions</span></span>  
 <span data-ttu-id="5d501-195">Ein *eine erweiternde Konvertierung* immer erfolgreich, zur Laufzeit, während eine *einschränkende Konvertierung* zur Laufzeit Fehler verursachen können.</span><span class="sxs-lookup"><span data-stu-id="5d501-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="5d501-196">Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="5d501-196">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
 <span data-ttu-id="5d501-197">Wenn Sie eine Konvertierungsprozedur deklarieren `Widening`, Ihren Prozedurcode muss keine Fehler generieren.</span><span class="sxs-lookup"><span data-stu-id="5d501-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="5d501-198">Dies bedeutet Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5d501-198">This means the following:</span></span>  
  
- <span data-ttu-id="5d501-199">Sie muss immer einen gültigen Wert des Typs zurückgeben `type`.</span><span class="sxs-lookup"><span data-stu-id="5d501-199">It must always return a valid value of type `type`.</span></span>  
  
- <span data-ttu-id="5d501-200">Sie müssen alle möglichen Ausnahmen und andere Fehler behandeln.</span><span class="sxs-lookup"><span data-stu-id="5d501-200">It must handle all possible exceptions and other error conditions.</span></span>  
  
- <span data-ttu-id="5d501-201">Sie müssen jeden zurückgegebenen Fehler aus allen Prozeduren behandeln, die er aufruft.</span><span class="sxs-lookup"><span data-stu-id="5d501-201">It must handle any error returns from any procedures it calls.</span></span>  
  
 <span data-ttu-id="5d501-202">Wenn eine Möglichkeit besteht, die eine Konvertierungsprozedur nicht erfolgreich ausgeführt werden kann, oder die It dazu führen, eine nicht behandelte Ausnahme dass kann, müssen Sie es deklarieren `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="5d501-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d501-203">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d501-203">Example</span></span>  
 <span data-ttu-id="5d501-204">Im folgenden Codebeispiel wird die `Operator` Anweisung, um das Gerüst für eine Struktur definieren, die Operatorprozeduren für umfasst die `And`, `Or`, `IsFalse`, und `IsTrue` Operatoren.</span><span class="sxs-lookup"><span data-stu-id="5d501-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="5d501-205">`And` und `Or` akzeptieren jeweils zwei Operanden vom Typ `abc` und den Rückgabetyp `abc`.</span><span class="sxs-lookup"><span data-stu-id="5d501-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="5d501-206">`IsFalse` und `IsTrue` akzeptieren jeweils einen einzelnen Operanden vom Typ `abc` und zurückgeben `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5d501-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="5d501-207">Diese Definitionen ermöglicht werden, den aufrufenden Code mit `And`, `AndAlso`, `Or`, und `OrElse` mit Operanden vom Typ `abc`.</span><span class="sxs-lookup"><span data-stu-id="5d501-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>  
  
 [!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]  
  
## <a name="see-also"></a><span data-ttu-id="5d501-208">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d501-208">See also</span></span>

- [<span data-ttu-id="5d501-209">IsFalse-Operator</span><span class="sxs-lookup"><span data-stu-id="5d501-209">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="5d501-210">IsTrue-Operator</span><span class="sxs-lookup"><span data-stu-id="5d501-210">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="5d501-211">Widening</span><span class="sxs-lookup"><span data-stu-id="5d501-211">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="5d501-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="5d501-212">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="5d501-213">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="5d501-213">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="5d501-214">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="5d501-214">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="5d501-215">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="5d501-215">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="5d501-216">Vorgehensweise: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="5d501-216">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="5d501-217">Vorgehensweise: Aufrufen einer Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="5d501-217">How to: Call an Operator Procedure</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="5d501-218">Vorgehensweise: Verwenden Sie eine Klasse, die Operatoren definiert</span><span class="sxs-lookup"><span data-stu-id="5d501-218">How to: Use a Class that Defines Operators</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
