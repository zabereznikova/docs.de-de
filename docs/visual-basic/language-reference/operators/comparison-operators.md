---
title: Vergleichsoperatoren
ms.date: 07/20/2015
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basic
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: ea7604626ede66da818e4bc22fe4922bc752dc2c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336085"
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="069d0-102">Vergleichsoperatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="069d0-102">Comparison Operators (Visual Basic)</span></span>
<span data-ttu-id="069d0-103">The following are the comparison operators defined in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="069d0-103">The following are the comparison operators defined in Visual Basic.</span></span>

 <span data-ttu-id="069d0-104">`<` operator</span><span class="sxs-lookup"><span data-stu-id="069d0-104">`<` operator</span></span>

 <span data-ttu-id="069d0-105">`<=` operator</span><span class="sxs-lookup"><span data-stu-id="069d0-105">`<=` operator</span></span>

 <span data-ttu-id="069d0-106">`>` operator</span><span class="sxs-lookup"><span data-stu-id="069d0-106">`>` operator</span></span>

 <span data-ttu-id="069d0-107">`>=` operator</span><span class="sxs-lookup"><span data-stu-id="069d0-107">`>=` operator</span></span>

 <span data-ttu-id="069d0-108">`=` operator</span><span class="sxs-lookup"><span data-stu-id="069d0-108">`=` operator</span></span>

 <span data-ttu-id="069d0-109">`<>` operator</span><span class="sxs-lookup"><span data-stu-id="069d0-109">`<>` operator</span></span>

 [<span data-ttu-id="069d0-110">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="069d0-110">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)

 [<span data-ttu-id="069d0-111">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="069d0-111">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)

 [<span data-ttu-id="069d0-112">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="069d0-112">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)

 <span data-ttu-id="069d0-113">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span><span class="sxs-lookup"><span data-stu-id="069d0-113">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="069d0-114">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span><span class="sxs-lookup"><span data-stu-id="069d0-114">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="069d0-115">The relational comparison operators are discussed in detail on this page.</span><span class="sxs-lookup"><span data-stu-id="069d0-115">The relational comparison operators are discussed in detail on this page.</span></span>

## <a name="syntax"></a><span data-ttu-id="069d0-116">Syntax</span><span class="sxs-lookup"><span data-stu-id="069d0-116">Syntax</span></span>
  
```vb
result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="069d0-117">Teile</span><span class="sxs-lookup"><span data-stu-id="069d0-117">Parts</span></span>
 `result`  
 <span data-ttu-id="069d0-118">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="069d0-118">Required.</span></span> <span data-ttu-id="069d0-119">A `Boolean` value representing the result of the comparison.</span><span class="sxs-lookup"><span data-stu-id="069d0-119">A `Boolean` value representing the result of the comparison.</span></span>

 <span data-ttu-id="069d0-120">`expression1`, `expression2`</span><span class="sxs-lookup"><span data-stu-id="069d0-120">`expression1`, `expression2`</span></span>  
 <span data-ttu-id="069d0-121">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="069d0-121">Required.</span></span> <span data-ttu-id="069d0-122">Beliebiger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="069d0-122">Any expression.</span></span>

 `comparisonoperator`  
 <span data-ttu-id="069d0-123">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="069d0-123">Required.</span></span> <span data-ttu-id="069d0-124">Any relational comparison operator.</span><span class="sxs-lookup"><span data-stu-id="069d0-124">Any relational comparison operator.</span></span>

 <span data-ttu-id="069d0-125">`object1`, `object2`</span><span class="sxs-lookup"><span data-stu-id="069d0-125">`object1`, `object2`</span></span>  
 <span data-ttu-id="069d0-126">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="069d0-126">Required.</span></span> <span data-ttu-id="069d0-127">Any reference object names.</span><span class="sxs-lookup"><span data-stu-id="069d0-127">Any reference object names.</span></span>

 `string`  
 <span data-ttu-id="069d0-128">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="069d0-128">Required.</span></span> <span data-ttu-id="069d0-129">Beliebiger `String` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="069d0-129">Any `String` expression.</span></span>

 `pattern`  
 <span data-ttu-id="069d0-130">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="069d0-130">Required.</span></span> <span data-ttu-id="069d0-131">Any `String` expression or range of characters.</span><span class="sxs-lookup"><span data-stu-id="069d0-131">Any `String` expression or range of characters.</span></span>

## <a name="remarks"></a><span data-ttu-id="069d0-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="069d0-132">Remarks</span></span>
 <span data-ttu-id="069d0-133">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span><span class="sxs-lookup"><span data-stu-id="069d0-133">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>

|<span data-ttu-id="069d0-134">Operator</span><span class="sxs-lookup"><span data-stu-id="069d0-134">Operator</span></span>|<span data-ttu-id="069d0-135">`True`, wenn</span><span class="sxs-lookup"><span data-stu-id="069d0-135">`True` if</span></span>|<span data-ttu-id="069d0-136">`False`, wenn</span><span class="sxs-lookup"><span data-stu-id="069d0-136">`False` if</span></span>|
|--------------|---------------|----------------|
|<span data-ttu-id="069d0-137">`<` (Less than)</span><span class="sxs-lookup"><span data-stu-id="069d0-137">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|
|<span data-ttu-id="069d0-138">`<=` (Less than or equal to)</span><span class="sxs-lookup"><span data-stu-id="069d0-138">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|
|<span data-ttu-id="069d0-139">`>` (Greater than)</span><span class="sxs-lookup"><span data-stu-id="069d0-139">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|
|<span data-ttu-id="069d0-140">`>=` (Greater than or equal to)</span><span class="sxs-lookup"><span data-stu-id="069d0-140">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|
|<span data-ttu-id="069d0-141">`=` (Equal to)</span><span class="sxs-lookup"><span data-stu-id="069d0-141">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|
|<span data-ttu-id="069d0-142">`<>` (Not equal to)</span><span class="sxs-lookup"><span data-stu-id="069d0-142">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|

> [!NOTE]
> <span data-ttu-id="069d0-143">The [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) is also used as an assignment operator.</span><span class="sxs-lookup"><span data-stu-id="069d0-143">The [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) is also used as an assignment operator.</span></span>

 <span data-ttu-id="069d0-144">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span><span class="sxs-lookup"><span data-stu-id="069d0-144">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>

## <a name="comparing-numbers"></a><span data-ttu-id="069d0-145">Comparing Numbers</span><span class="sxs-lookup"><span data-stu-id="069d0-145">Comparing Numbers</span></span>
 <span data-ttu-id="069d0-146">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span><span class="sxs-lookup"><span data-stu-id="069d0-146">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="069d0-147">This behavior is opposite to the behavior found in Visual Basic 6.</span><span class="sxs-lookup"><span data-stu-id="069d0-147">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>

 <span data-ttu-id="069d0-148">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span><span class="sxs-lookup"><span data-stu-id="069d0-148">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="069d0-149">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span><span class="sxs-lookup"><span data-stu-id="069d0-149">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="069d0-150">Such fractional value loss may cause two values to compare as equal when they are not.</span><span class="sxs-lookup"><span data-stu-id="069d0-150">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="069d0-151">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span><span class="sxs-lookup"><span data-stu-id="069d0-151">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="069d0-152">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span><span class="sxs-lookup"><span data-stu-id="069d0-152">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>

### <a name="floating-point-imprecision"></a><span data-ttu-id="069d0-153">Floating-point Imprecision</span><span class="sxs-lookup"><span data-stu-id="069d0-153">Floating-point Imprecision</span></span>
 <span data-ttu-id="069d0-154">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span><span class="sxs-lookup"><span data-stu-id="069d0-154">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="069d0-155">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](../../../visual-basic/language-reference/operators/mod-operator.md).</span><span class="sxs-lookup"><span data-stu-id="069d0-155">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](../../../visual-basic/language-reference/operators/mod-operator.md).</span></span> <span data-ttu-id="069d0-156">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="069d0-156">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

## <a name="comparing-strings"></a><span data-ttu-id="069d0-157">Vergleichen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="069d0-157">Comparing Strings</span></span>
 <span data-ttu-id="069d0-158">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span><span class="sxs-lookup"><span data-stu-id="069d0-158">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>

 <span data-ttu-id="069d0-159">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span><span class="sxs-lookup"><span data-stu-id="069d0-159">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="069d0-160">The sort order is determined by the code page.</span><span class="sxs-lookup"><span data-stu-id="069d0-160">The sort order is determined by the code page.</span></span> <span data-ttu-id="069d0-161">The following example shows a typical binary sort order.</span><span class="sxs-lookup"><span data-stu-id="069d0-161">The following example shows a typical binary sort order.</span></span>

 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

 <span data-ttu-id="069d0-162">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span><span class="sxs-lookup"><span data-stu-id="069d0-162">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="069d0-163">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span><span class="sxs-lookup"><span data-stu-id="069d0-163">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>

 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`

### <a name="locale-dependence"></a><span data-ttu-id="069d0-164">Locale Dependence</span><span class="sxs-lookup"><span data-stu-id="069d0-164">Locale Dependence</span></span>
 <span data-ttu-id="069d0-165">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span><span class="sxs-lookup"><span data-stu-id="069d0-165">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="069d0-166">Two characters might compare as equal in one locale but not in another.</span><span class="sxs-lookup"><span data-stu-id="069d0-166">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="069d0-167">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span><span class="sxs-lookup"><span data-stu-id="069d0-167">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="069d0-168">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span><span class="sxs-lookup"><span data-stu-id="069d0-168">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>

## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="069d0-169">Typeless Programming with Relational Comparison Operators</span><span class="sxs-lookup"><span data-stu-id="069d0-169">Typeless Programming with Relational Comparison Operators</span></span>
 <span data-ttu-id="069d0-170">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span><span class="sxs-lookup"><span data-stu-id="069d0-170">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="069d0-171">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span><span class="sxs-lookup"><span data-stu-id="069d0-171">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="069d0-172">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span><span class="sxs-lookup"><span data-stu-id="069d0-172">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>

|<span data-ttu-id="069d0-173">If operands are</span><span class="sxs-lookup"><span data-stu-id="069d0-173">If operands are</span></span>|<span data-ttu-id="069d0-174">Comparison is</span><span class="sxs-lookup"><span data-stu-id="069d0-174">Comparison is</span></span>|
|---------------------|-------------------|
|<span data-ttu-id="069d0-175">Both `String`</span><span class="sxs-lookup"><span data-stu-id="069d0-175">Both `String`</span></span>|<span data-ttu-id="069d0-176">Sort comparison based on string sorting characteristics.</span><span class="sxs-lookup"><span data-stu-id="069d0-176">Sort comparison based on string sorting characteristics.</span></span>|
|<span data-ttu-id="069d0-177">Both numeric</span><span class="sxs-lookup"><span data-stu-id="069d0-177">Both numeric</span></span>|<span data-ttu-id="069d0-178">Objects converted to `Double`, numeric comparison.</span><span class="sxs-lookup"><span data-stu-id="069d0-178">Objects converted to `Double`, numeric comparison.</span></span>|
|<span data-ttu-id="069d0-179">One numeric and one `String`</span><span class="sxs-lookup"><span data-stu-id="069d0-179">One numeric and one `String`</span></span>|<span data-ttu-id="069d0-180">The `String` is converted to a `Double` and numeric comparison is performed.</span><span class="sxs-lookup"><span data-stu-id="069d0-180">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="069d0-181">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span><span class="sxs-lookup"><span data-stu-id="069d0-181">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|
|<span data-ttu-id="069d0-182">Either or both are reference types other than `String`</span><span class="sxs-lookup"><span data-stu-id="069d0-182">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="069d0-183">Es wird eine <xref:System.InvalidCastException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="069d0-183">An <xref:System.InvalidCastException> is thrown.</span></span>|

 <span data-ttu-id="069d0-184">Numeric comparisons treat `Nothing` as 0.</span><span class="sxs-lookup"><span data-stu-id="069d0-184">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="069d0-185">String comparisons treat `Nothing` as `""` (an empty string).</span><span class="sxs-lookup"><span data-stu-id="069d0-185">String comparisons treat `Nothing` as `""` (an empty string).</span></span>

## <a name="overloading"></a><span data-ttu-id="069d0-186">Überladen</span><span class="sxs-lookup"><span data-stu-id="069d0-186">Overloading</span></span>
 <span data-ttu-id="069d0-187">The relational comparison operators (`<`.</span><span class="sxs-lookup"><span data-stu-id="069d0-187">The relational comparison operators (`<`.</span></span> <span data-ttu-id="069d0-188">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span><span class="sxs-lookup"><span data-stu-id="069d0-188">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="069d0-189">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span><span class="sxs-lookup"><span data-stu-id="069d0-189">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="069d0-190">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="069d0-190">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

 <span data-ttu-id="069d0-191">Notice that the [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span><span class="sxs-lookup"><span data-stu-id="069d0-191">Notice that the [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>

## <a name="example"></a><span data-ttu-id="069d0-192">Beispiel</span><span class="sxs-lookup"><span data-stu-id="069d0-192">Example</span></span>
 <span data-ttu-id="069d0-193">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span><span class="sxs-lookup"><span data-stu-id="069d0-193">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="069d0-194">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span><span class="sxs-lookup"><span data-stu-id="069d0-194">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="069d0-195">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span><span class="sxs-lookup"><span data-stu-id="069d0-195">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="069d0-196">This order can be dependent on your locale setting.</span><span class="sxs-lookup"><span data-stu-id="069d0-196">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="069d0-197">Whether the sort is case-sensitive or not depends on the [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) setting.</span><span class="sxs-lookup"><span data-stu-id="069d0-197">Whether the sort is case-sensitive or not depends on the [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) setting.</span></span>

 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]

 <span data-ttu-id="069d0-198">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span><span class="sxs-lookup"><span data-stu-id="069d0-198">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>

## <a name="see-also"></a><span data-ttu-id="069d0-199">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="069d0-199">See also</span></span>

- <xref:System.InvalidCastException>
- [<span data-ttu-id="069d0-200">=-Operator</span><span class="sxs-lookup"><span data-stu-id="069d0-200">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [<span data-ttu-id="069d0-201">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="069d0-201">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="069d0-202">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="069d0-202">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="069d0-203">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="069d0-203">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="069d0-204">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="069d0-204">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
