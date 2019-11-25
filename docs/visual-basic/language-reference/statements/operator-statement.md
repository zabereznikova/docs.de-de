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
ms.openlocfilehash: aa6ae3977977ded05e47d12dabe72f09251f262d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353797"
---
# <a name="operator-statement"></a><span data-ttu-id="72546-102">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="72546-102">Operator Statement</span></span>

<span data-ttu-id="72546-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span><span class="sxs-lookup"><span data-stu-id="72546-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="72546-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72546-104">Syntax</span></span>

```vb
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]
    [ statements ]
    [ statements ]
    Return returnvalue
    [ statements ]
End Operator
```

## <a name="parts"></a><span data-ttu-id="72546-105">Teile</span><span class="sxs-lookup"><span data-stu-id="72546-105">Parts</span></span>

`attrlist`  
<span data-ttu-id="72546-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="72546-106">Optional.</span></span> <span data-ttu-id="72546-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="72546-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>

`Public`  
<span data-ttu-id="72546-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="72546-108">Required.</span></span> <span data-ttu-id="72546-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span><span class="sxs-lookup"><span data-stu-id="72546-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span>

`Overloads`  
<span data-ttu-id="72546-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="72546-110">Optional.</span></span> <span data-ttu-id="72546-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span><span class="sxs-lookup"><span data-stu-id="72546-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span></span>

`Shared`  
<span data-ttu-id="72546-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="72546-112">Required.</span></span> <span data-ttu-id="72546-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span><span class="sxs-lookup"><span data-stu-id="72546-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span></span>

`Shadows`  
<span data-ttu-id="72546-114">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="72546-114">Optional.</span></span> <span data-ttu-id="72546-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="72546-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

`Widening`  
<span data-ttu-id="72546-116">Required for a conversion operator unless you specify `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="72546-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="72546-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span><span class="sxs-lookup"><span data-stu-id="72546-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span></span> <span data-ttu-id="72546-118">See "Widening and Narrowing Conversions" on this Help page.</span><span class="sxs-lookup"><span data-stu-id="72546-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`Narrowing`  
<span data-ttu-id="72546-119">Required for a conversion operator unless you specify `Widening`.</span><span class="sxs-lookup"><span data-stu-id="72546-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="72546-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span><span class="sxs-lookup"><span data-stu-id="72546-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="72546-121">See "Widening and Narrowing Conversions" on this Help page.</span><span class="sxs-lookup"><span data-stu-id="72546-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`operatorsymbol`  
<span data-ttu-id="72546-122">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="72546-122">Required.</span></span> <span data-ttu-id="72546-123">The symbol or identifier of the operator that this operator procedure defines.</span><span class="sxs-lookup"><span data-stu-id="72546-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>

`operand1`  
<span data-ttu-id="72546-124">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="72546-124">Required.</span></span> <span data-ttu-id="72546-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span><span class="sxs-lookup"><span data-stu-id="72546-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>

`operand2`  
<span data-ttu-id="72546-126">Required for binary operators.</span><span class="sxs-lookup"><span data-stu-id="72546-126">Required for binary operators.</span></span> <span data-ttu-id="72546-127">The name and type of the right operand of a binary operator.</span><span class="sxs-lookup"><span data-stu-id="72546-127">The name and type of the right operand of a binary operator.</span></span>

<span data-ttu-id="72546-128">`operand1` and `operand2` have the following syntax and parts:</span><span class="sxs-lookup"><span data-stu-id="72546-128">`operand1` and `operand2` have the following syntax and parts:</span></span>

`[ ByVal ] operandname [ As operandtype ]`

|<span data-ttu-id="72546-129">Segment</span><span class="sxs-lookup"><span data-stu-id="72546-129">Part</span></span>|<span data-ttu-id="72546-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72546-130">Description</span></span>|
|----------|-----------------|
|`ByVal`|<span data-ttu-id="72546-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="72546-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>|
|`operandname`|<span data-ttu-id="72546-132">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="72546-132">Required.</span></span> <span data-ttu-id="72546-133">Name of the variable representing this operand.</span><span class="sxs-lookup"><span data-stu-id="72546-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="72546-134">Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="72546-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
|`operandtype`|<span data-ttu-id="72546-135">Optional unless `Option Strict` is `On`.</span><span class="sxs-lookup"><span data-stu-id="72546-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="72546-136">Data type of this operand.</span><span class="sxs-lookup"><span data-stu-id="72546-136">Data type of this operand.</span></span>|

`type`  
<span data-ttu-id="72546-137">Optional unless `Option Strict` is `On`.</span><span class="sxs-lookup"><span data-stu-id="72546-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="72546-138">Data type of the value the operator procedure returns.</span><span class="sxs-lookup"><span data-stu-id="72546-138">Data type of the value the operator procedure returns.</span></span>

`statements`  
<span data-ttu-id="72546-139">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="72546-139">Optional.</span></span> <span data-ttu-id="72546-140">Block of statements that the operator procedure runs.</span><span class="sxs-lookup"><span data-stu-id="72546-140">Block of statements that the operator procedure runs.</span></span>

`returnvalue`  
<span data-ttu-id="72546-141">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="72546-141">Required.</span></span> <span data-ttu-id="72546-142">The value that the operator procedure returns to the calling code.</span><span class="sxs-lookup"><span data-stu-id="72546-142">The value that the operator procedure returns to the calling code.</span></span>

<span data-ttu-id="72546-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="72546-143">`End` `Operator`</span></span>  
<span data-ttu-id="72546-144">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="72546-144">Required.</span></span> <span data-ttu-id="72546-145">Terminates the definition of this operator procedure.</span><span class="sxs-lookup"><span data-stu-id="72546-145">Terminates the definition of this operator procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="72546-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="72546-146">Remarks</span></span>

<span data-ttu-id="72546-147">You can use `Operator` only in a class or structure.</span><span class="sxs-lookup"><span data-stu-id="72546-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="72546-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span><span class="sxs-lookup"><span data-stu-id="72546-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="72546-149">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="72546-149">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="72546-150">All operators must be `Public Shared`.</span><span class="sxs-lookup"><span data-stu-id="72546-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="72546-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span><span class="sxs-lookup"><span data-stu-id="72546-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>

<span data-ttu-id="72546-152">You cannot use the operator symbol or identifier to hold a return value.</span><span class="sxs-lookup"><span data-stu-id="72546-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="72546-153">You must use the `Return` statement, and it must specify a value.</span><span class="sxs-lookup"><span data-stu-id="72546-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="72546-154">Any number of `Return` statements can appear anywhere in the procedure.</span><span class="sxs-lookup"><span data-stu-id="72546-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>

<span data-ttu-id="72546-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span><span class="sxs-lookup"><span data-stu-id="72546-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="72546-156">In der folgenden Tabelle sind die Operatoren aufgelistet, die Sie definieren können.</span><span class="sxs-lookup"><span data-stu-id="72546-156">The following table lists the operators you can define.</span></span>

|<span data-ttu-id="72546-157">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="72546-157">Type</span></span>|<span data-ttu-id="72546-158">Operatoren</span><span class="sxs-lookup"><span data-stu-id="72546-158">Operators</span></span>|
|----------|---------------|
|<span data-ttu-id="72546-159">Unär</span><span class="sxs-lookup"><span data-stu-id="72546-159">Unary</span></span>|<span data-ttu-id="72546-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="72546-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|
|<span data-ttu-id="72546-161">Binär</span><span class="sxs-lookup"><span data-stu-id="72546-161">Binary</span></span>|<span data-ttu-id="72546-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="72546-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|
|<span data-ttu-id="72546-163">Konvertierung (unär)</span><span class="sxs-lookup"><span data-stu-id="72546-163">Conversion (unary)</span></span>|`CType`|

<span data-ttu-id="72546-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span><span class="sxs-lookup"><span data-stu-id="72546-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>

<span data-ttu-id="72546-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="72546-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>

## <a name="matched-pairs"></a><span data-ttu-id="72546-166">Matched Pairs</span><span class="sxs-lookup"><span data-stu-id="72546-166">Matched Pairs</span></span>

<span data-ttu-id="72546-167">You must define certain operators as matched pairs.</span><span class="sxs-lookup"><span data-stu-id="72546-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="72546-168">If you define either operator of such a pair, you must define the other as well.</span><span class="sxs-lookup"><span data-stu-id="72546-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="72546-169">The matched pairs are the following:</span><span class="sxs-lookup"><span data-stu-id="72546-169">The matched pairs are the following:</span></span>

- <span data-ttu-id="72546-170">`=` und `<>`</span><span class="sxs-lookup"><span data-stu-id="72546-170">`=` and `<>`</span></span>

- <span data-ttu-id="72546-171">`>` und `<`</span><span class="sxs-lookup"><span data-stu-id="72546-171">`>` and `<`</span></span>

- <span data-ttu-id="72546-172">`>=` und `<=`</span><span class="sxs-lookup"><span data-stu-id="72546-172">`>=` and `<=`</span></span>

- <span data-ttu-id="72546-173">`IsTrue` und `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="72546-173">`IsTrue` and `IsFalse`</span></span>

## <a name="data-type-restrictions"></a><span data-ttu-id="72546-174">Data Type Restrictions</span><span class="sxs-lookup"><span data-stu-id="72546-174">Data Type Restrictions</span></span>

<span data-ttu-id="72546-175">Every operator you define must involve the class or structure on which you define it.</span><span class="sxs-lookup"><span data-stu-id="72546-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="72546-176">This means that the class or structure must appear as the data type of the following:</span><span class="sxs-lookup"><span data-stu-id="72546-176">This means that the class or structure must appear as the data type of the following:</span></span>

- <span data-ttu-id="72546-177">The operand of a unary operator.</span><span class="sxs-lookup"><span data-stu-id="72546-177">The operand of a unary operator.</span></span>

- <span data-ttu-id="72546-178">At least one of the operands of a binary operator.</span><span class="sxs-lookup"><span data-stu-id="72546-178">At least one of the operands of a binary operator.</span></span>

- <span data-ttu-id="72546-179">Either the operand or the return type of a conversion operator.</span><span class="sxs-lookup"><span data-stu-id="72546-179">Either the operand or the return type of a conversion operator.</span></span>

 <span data-ttu-id="72546-180">Certain operators have additional data type restrictions, as follows:</span><span class="sxs-lookup"><span data-stu-id="72546-180">Certain operators have additional data type restrictions, as follows:</span></span>

- <span data-ttu-id="72546-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span><span class="sxs-lookup"><span data-stu-id="72546-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>

- <span data-ttu-id="72546-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span><span class="sxs-lookup"><span data-stu-id="72546-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>

<span data-ttu-id="72546-183">The return type does not have to correspond to the type of either operand.</span><span class="sxs-lookup"><span data-stu-id="72546-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="72546-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="72546-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>

## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="72546-185">Logische und bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="72546-185">Logical and Bitwise Operators</span></span>

<span data-ttu-id="72546-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="72546-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="72546-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span><span class="sxs-lookup"><span data-stu-id="72546-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>

<span data-ttu-id="72546-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span><span class="sxs-lookup"><span data-stu-id="72546-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="72546-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span><span class="sxs-lookup"><span data-stu-id="72546-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>

- <span data-ttu-id="72546-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span><span class="sxs-lookup"><span data-stu-id="72546-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>

- <span data-ttu-id="72546-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span><span class="sxs-lookup"><span data-stu-id="72546-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>

- <span data-ttu-id="72546-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span><span class="sxs-lookup"><span data-stu-id="72546-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>

<span data-ttu-id="72546-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span><span class="sxs-lookup"><span data-stu-id="72546-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>

## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="72546-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="72546-194">Widening and Narrowing Conversions</span></span>

<span data-ttu-id="72546-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span><span class="sxs-lookup"><span data-stu-id="72546-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="72546-196">Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="72546-196">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="72546-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span><span class="sxs-lookup"><span data-stu-id="72546-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="72546-198">Dies bedeutet Folgendes:</span><span class="sxs-lookup"><span data-stu-id="72546-198">This means the following:</span></span>

- <span data-ttu-id="72546-199">It must always return a valid value of type `type`.</span><span class="sxs-lookup"><span data-stu-id="72546-199">It must always return a valid value of type `type`.</span></span>

- <span data-ttu-id="72546-200">It must handle all possible exceptions and other error conditions.</span><span class="sxs-lookup"><span data-stu-id="72546-200">It must handle all possible exceptions and other error conditions.</span></span>

- <span data-ttu-id="72546-201">It must handle any error returns from any procedures it calls.</span><span class="sxs-lookup"><span data-stu-id="72546-201">It must handle any error returns from any procedures it calls.</span></span>

<span data-ttu-id="72546-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="72546-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>

## <a name="example"></a><span data-ttu-id="72546-203">Beispiel</span><span class="sxs-lookup"><span data-stu-id="72546-203">Example</span></span>

<span data-ttu-id="72546-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span><span class="sxs-lookup"><span data-stu-id="72546-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="72546-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span><span class="sxs-lookup"><span data-stu-id="72546-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="72546-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="72546-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="72546-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span><span class="sxs-lookup"><span data-stu-id="72546-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a><span data-ttu-id="72546-208">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72546-208">See also</span></span>

- [<span data-ttu-id="72546-209">IsFalse-Operator</span><span class="sxs-lookup"><span data-stu-id="72546-209">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="72546-210">IsTrue-Operator</span><span class="sxs-lookup"><span data-stu-id="72546-210">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="72546-211">Widening</span><span class="sxs-lookup"><span data-stu-id="72546-211">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="72546-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="72546-212">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="72546-213">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="72546-213">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="72546-214">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="72546-214">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="72546-215">Gewusst wie: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="72546-215">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="72546-216">Gewusst wie: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="72546-216">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="72546-217">Gewusst wie: Aufrufen einer Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="72546-217">How to: Call an Operator Procedure</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="72546-218">Gewusst wie: Verwenden einer Klasse, die Operatoren definiert</span><span class="sxs-lookup"><span data-stu-id="72546-218">How to: Use a Class that Defines Operators</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
