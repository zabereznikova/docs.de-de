---
title: 'Logische boolesche Operatoren: C#-Referenz'
description: Erfahren Sie mehr über C#-Operatoren, die logische Negation, Konjunktion (AND), inklusive und exklusive Disjunktion (OR) mit booleschen Operanden durchführen.
ms.date: 09/27/2019
author: pkulikov
f1_keywords:
- '!_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
- '&&_CSharpKeyword'
- '||_CSharpKeyword'
helpviewer_keywords:
- logical operators [C#]
- short-circuiting operators [C#]
- logical negation operator [C#]
- NOT operator [C#]
- '! operator [C#]'
- AND operator [C#]
- ampersand operator [C#]
- conjunction operator [C#]
- '& operator [C#]'
- exclusive OR operator [C#]
- XOR operator [C#]
- ^ operator [C#]
- OR operator [C#]
- disjunction operator [C#]
- '| operator [C#]'
- conditional AND operator [C#]
- short-circuiting AND operator [C#]
- '&& operator [C#]'
- conditional OR operator [C#]
- short-circuiting OR operator [C#]
- '|| operator [C#]'
ms.openlocfilehash: e355a89e27ea5bd6e4335b39c4e669610c4b0553
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319105"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="92234-103">Logische boolesche Operatoren (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="92234-103">Boolean logical operators (C# reference)</span></span>

<span data-ttu-id="92234-104">Die folgenden Operatoren führen logische Vorgänge mit den [bool](../keywords/bool.md)-Operanden durch:</span><span class="sxs-lookup"><span data-stu-id="92234-104">The following operators perform logical operations with the [bool](../keywords/bool.md) operands:</span></span>

- <span data-ttu-id="92234-105">Unärer [`!` (logische Negation)](#logical-negation-operator-) Operator.</span><span class="sxs-lookup"><span data-stu-id="92234-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="92234-106">Binäre [`&` (logisch AND)](#logical-and-operator-), [`|` (logisch OR)](#logical-or-operator-) und [`^` (logisch exklusiv OR)](#logical-exclusive-or-operator-) Operatoren.</span><span class="sxs-lookup"><span data-stu-id="92234-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="92234-107">Diese Operatoren werten immer beide Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="92234-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="92234-108">Binäre [ `&&` (bedingt logisch AND)](#conditional-logical-and-operator-) und [ `||` (bedingt logisch OR)](#conditional-logical-or-operator-) Operatoren.</span><span class="sxs-lookup"><span data-stu-id="92234-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="92234-109">Diese Operatoren werten den rechten Operanden nur dann aus, wenn es notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="92234-109">Those operators evaluate the right-hand operand only if it's necessary.</span></span>

<span data-ttu-id="92234-110">Für die Operanden der [integralen](../builtin-types/integral-numeric-types.md) Typen führen die Operatoren `&`, `|` und `^` bitweise logische Operationen durch.</span><span class="sxs-lookup"><span data-stu-id="92234-110">For the operands of the [integral](../builtin-types/integral-numeric-types.md) types, the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="92234-111">Weitere Informationen finden Sie unter [Bitweise und Schiebeoperatoren](bitwise-and-shift-operators.md).</span><span class="sxs-lookup"><span data-stu-id="92234-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="92234-112">Logischer Negationsoperator: !</span><span class="sxs-lookup"><span data-stu-id="92234-112">Logical negation operator !</span></span>

<span data-ttu-id="92234-113">Der unäre Präfix-Operator `!` berechnet die logische Negation seines Operanden.</span><span class="sxs-lookup"><span data-stu-id="92234-113">The unary prefix `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="92234-114">Das heißt., er erzeugt `true`, wenn der Operand als `false` ausgewertet wird, und `false`, wenn der Operand als `true` ausgewertet wird:</span><span class="sxs-lookup"><span data-stu-id="92234-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Negation)]

<span data-ttu-id="92234-115">Ab C# 8.0 ist der unäre Postfix-Operator `!` der [NULL-tolerante Operator](null-forgiving.md).</span><span class="sxs-lookup"><span data-stu-id="92234-115">Starting with C# 8.0, the unary postfix `!` operator is the [null-forgiving operator](null-forgiving.md).</span></span>

## <a name="logical-and-operator-"></a> <span data-ttu-id="92234-116">Logischer AND-Operator &amp;</span><span class="sxs-lookup"><span data-stu-id="92234-116">Logical AND operator &amp;</span></span>

<span data-ttu-id="92234-117">Der `&`-Operator berechnet die logische AND-Operation des Operanden.</span><span class="sxs-lookup"><span data-stu-id="92234-117">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="92234-118">Das Ergebnis von `x & y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="92234-118">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="92234-119">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="92234-119">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="92234-120">Der `&`-Operator wertet beide Operanden aus, selbst wenn der linke Operand als `false` ausgewertet wird, sodass das Ergebnis unabhängig vom Wert des rechten Operanden `false` sein muss.</span><span class="sxs-lookup"><span data-stu-id="92234-120">The `&` operator evaluates both operands even if the left-hand operand evaluates to `false`, so that the result must be `false` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="92234-121">Im folgenden Beispiel ist der rechte Operand des `&`-Operators ein Methodenaufruf, der unabhängig vom Wert des linken Operanden ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="92234-121">In the following example, the right-hand operand of the `&` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#And)]

<span data-ttu-id="92234-122">Der [bedingte logische AND-Operator](#conditional-logical-and-operator-) `&&` berechnet auch die logische AND-Operation der Operanden, wertet den rechten Operanden aber nicht aus, wenn der linke Operand `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="92234-122">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `false`.</span></span>

<span data-ttu-id="92234-123">Für die Operanden der integralen Typen berechnet der Operator `&` [bitweises logisches UND](bitwise-and-shift-operators.md#logical-and-operator-) für seine Operanden.</span><span class="sxs-lookup"><span data-stu-id="92234-123">For the operands of the integral types, the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="92234-124">Der unäre `&`-Operator ist der [address-of-Operator](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="92234-124">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="92234-125">Logischer exklusiver OR-Operator: ^</span><span class="sxs-lookup"><span data-stu-id="92234-125">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="92234-126">Die `^`-Operator berechnet das logische exklusive OR, auch als logischer XOR bezeichnet, seiner Operanden.</span><span class="sxs-lookup"><span data-stu-id="92234-126">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="92234-127">Das Ergebnis von `x ^ y` ist `true`, wenn `x` `true` ergibt und `y` `false`ergibt, oder `x` `false` ergibt und `y` `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="92234-127">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="92234-128">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="92234-128">Otherwise, the result is `false`.</span></span> <span data-ttu-id="92234-129">Das heißt, für die `bool`-Operanden berechnet der `^`-Operator das gleiche Ergebnis wie der [Ungleichheitsoperator](equality-operators.md#inequality-operator-) `!=`.</span><span class="sxs-lookup"><span data-stu-id="92234-129">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Xor)]

<span data-ttu-id="92234-130">Für die Operanden der integralen Typen berechnet der Operator `^` [bitweises logisches exklusives ODER](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) für seine Operanden.</span><span class="sxs-lookup"><span data-stu-id="92234-130">For the operands of the integral types, the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="92234-131">Logischer OR-Operator: |</span><span class="sxs-lookup"><span data-stu-id="92234-131">Logical OR operator |</span></span>

<span data-ttu-id="92234-132">Der `|`-Operator berechnet die logische OR-Operation des Operanden.</span><span class="sxs-lookup"><span data-stu-id="92234-132">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="92234-133">Das Ergebnis von `x | y` ist `true`, wenn entweder `x` oder `y` `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="92234-133">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="92234-134">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="92234-134">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="92234-135">Der `|`-Operator wertet beide Operanden aus, selbst wenn der linke Operand als `true` ausgewertet wird, sodass das Ergebnis unabhängig vom Wert des rechten Operanden `true` sein muss.</span><span class="sxs-lookup"><span data-stu-id="92234-135">The `|` operator evaluates both operands even if the left-hand operand evaluates to `true`, so that the result must be `true` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="92234-136">Im folgenden Beispiel ist der rechte Operand des `|`-Operators ein Methodenaufruf, der unabhängig vom Wert des linken Operanden ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="92234-136">In the following example, the right-hand operand of the `|` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Or)]

<span data-ttu-id="92234-137">Der [bedingte logische OR-Operator](#conditional-logical-or-operator-) `||` berechnet auch die logische OR-Operation der Operanden, wertet den rechten Operanden aber nicht aus, wenn der linke Operand `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="92234-137">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `true`.</span></span>

<span data-ttu-id="92234-138">Für die Operanden der integralen Typen berechnet der Operator `|` [bitweises logisches ODER](bitwise-and-shift-operators.md#logical-or-operator-) für seine Operanden.</span><span class="sxs-lookup"><span data-stu-id="92234-138">For the operands of the integral types, the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-"></a> <span data-ttu-id="92234-139">Bedingter logischer AND-Operator &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="92234-139">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="92234-140">Der bedingte logische AND-Operator `&&`, auch bekannt als der "kurzschließender" logischer AND-Operator bezeichnet, berechnet die logische AND-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="92234-140">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="92234-141">Das Ergebnis von `x && y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="92234-141">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="92234-142">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="92234-142">Otherwise, the result is `false`.</span></span> <span data-ttu-id="92234-143">Wenn `x` als `false` ausgewertet wird, wird `y` nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="92234-143">If `x` evaluates to `false`, `y` is not evaluated.</span></span>

<span data-ttu-id="92234-144">Im folgenden Beispiel ist der rechte Operand des `&&`-Operators ein Methodenaufruf, der nicht ausgeführt wird, wenn der linke Operand `false` ergibt:</span><span class="sxs-lookup"><span data-stu-id="92234-144">In the following example, the right-hand operand of the `&&` operator is a method call, which isn't performed if the left-hand operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="92234-145">Der [logische AND-Operator](#logical-and-operator-) `&` berechnet auch die logische AND-Operation der Operanden, es werden jedoch immer beide Operanden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="92234-145">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="92234-146">Bedingter logischer OR-Operator ||</span><span class="sxs-lookup"><span data-stu-id="92234-146">Conditional logical OR operator ||</span></span>

<span data-ttu-id="92234-147">Der bedingte logische OR-Operator `||`, auch bekannt als der "kurzschließender" logischer OR-Operator bezeichnet, berechnet die logische OR-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="92234-147">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="92234-148">Das Ergebnis von `x || y` ist `true`, wenn entweder `x` oder `y` `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="92234-148">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="92234-149">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="92234-149">Otherwise, the result is `false`.</span></span> <span data-ttu-id="92234-150">Wenn `x` als `true` ausgewertet wird, wird `y` nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="92234-150">If `x` evaluates to `true`, `y` is not evaluated.</span></span>

<span data-ttu-id="92234-151">Im folgenden Beispiel ist der rechte Operand des `||`-Operators ein Methodenaufruf, der nicht ausgeführt wird, wenn der linke Operand `true` ergibt:</span><span class="sxs-lookup"><span data-stu-id="92234-151">In the following example, the right-hand operand of the `||` operator is a method call, which isn't performed if the left-hand operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="92234-152">Der [logische OR-Operator](#logical-or-operator-) `|` berechnet auch die logische OR-Operation der Operanden, es werden jedoch immer beide Operanden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="92234-152">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="92234-153">Logische boolesche Operatoren, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="92234-153">Nullable Boolean logical operators</span></span>

<span data-ttu-id="92234-154">Für die `bool?`-Operanden unterstützen die `&`- und `|`-Operatoren die dreiwertige Logik.</span><span class="sxs-lookup"><span data-stu-id="92234-154">For the `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="92234-155">Die Semantik dieser Operatoren ist in der folgenden Tabelle definiert:</span><span class="sxs-lookup"><span data-stu-id="92234-155">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="92234-156">w</span><span class="sxs-lookup"><span data-stu-id="92234-156">x</span></span>|<span data-ttu-id="92234-157">y</span><span class="sxs-lookup"><span data-stu-id="92234-157">y</span></span>|<span data-ttu-id="92234-158">x&y</span><span class="sxs-lookup"><span data-stu-id="92234-158">x&y</span></span>|<span data-ttu-id="92234-159">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="92234-159">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="92234-160">true</span><span class="sxs-lookup"><span data-stu-id="92234-160">true</span></span>|<span data-ttu-id="92234-161">true</span><span class="sxs-lookup"><span data-stu-id="92234-161">true</span></span>|<span data-ttu-id="92234-162">true</span><span class="sxs-lookup"><span data-stu-id="92234-162">true</span></span>|<span data-ttu-id="92234-163">true</span><span class="sxs-lookup"><span data-stu-id="92234-163">true</span></span>|  
|<span data-ttu-id="92234-164">true</span><span class="sxs-lookup"><span data-stu-id="92234-164">true</span></span>|<span data-ttu-id="92234-165">False</span><span class="sxs-lookup"><span data-stu-id="92234-165">false</span></span>|<span data-ttu-id="92234-166">false</span><span class="sxs-lookup"><span data-stu-id="92234-166">false</span></span>|<span data-ttu-id="92234-167">true</span><span class="sxs-lookup"><span data-stu-id="92234-167">true</span></span>|  
|<span data-ttu-id="92234-168">true</span><span class="sxs-lookup"><span data-stu-id="92234-168">true</span></span>|<span data-ttu-id="92234-169">NULL</span><span class="sxs-lookup"><span data-stu-id="92234-169">null</span></span>|<span data-ttu-id="92234-170">NULL</span><span class="sxs-lookup"><span data-stu-id="92234-170">null</span></span>|<span data-ttu-id="92234-171">true</span><span class="sxs-lookup"><span data-stu-id="92234-171">true</span></span>|  
|<span data-ttu-id="92234-172">False</span><span class="sxs-lookup"><span data-stu-id="92234-172">false</span></span>|<span data-ttu-id="92234-173">true</span><span class="sxs-lookup"><span data-stu-id="92234-173">true</span></span>|<span data-ttu-id="92234-174">False</span><span class="sxs-lookup"><span data-stu-id="92234-174">false</span></span>|<span data-ttu-id="92234-175">true</span><span class="sxs-lookup"><span data-stu-id="92234-175">true</span></span>|  
|<span data-ttu-id="92234-176">False</span><span class="sxs-lookup"><span data-stu-id="92234-176">false</span></span>|<span data-ttu-id="92234-177">False</span><span class="sxs-lookup"><span data-stu-id="92234-177">false</span></span>|<span data-ttu-id="92234-178">False</span><span class="sxs-lookup"><span data-stu-id="92234-178">false</span></span>|<span data-ttu-id="92234-179">False</span><span class="sxs-lookup"><span data-stu-id="92234-179">false</span></span>|  
|<span data-ttu-id="92234-180">False</span><span class="sxs-lookup"><span data-stu-id="92234-180">false</span></span>|<span data-ttu-id="92234-181">NULL</span><span class="sxs-lookup"><span data-stu-id="92234-181">null</span></span>|<span data-ttu-id="92234-182">False</span><span class="sxs-lookup"><span data-stu-id="92234-182">false</span></span>|<span data-ttu-id="92234-183">NULL</span><span class="sxs-lookup"><span data-stu-id="92234-183">null</span></span>|  
|<span data-ttu-id="92234-184">NULL</span><span class="sxs-lookup"><span data-stu-id="92234-184">null</span></span>|<span data-ttu-id="92234-185">true</span><span class="sxs-lookup"><span data-stu-id="92234-185">true</span></span>|<span data-ttu-id="92234-186">NULL</span><span class="sxs-lookup"><span data-stu-id="92234-186">null</span></span>|<span data-ttu-id="92234-187">true</span><span class="sxs-lookup"><span data-stu-id="92234-187">true</span></span>|  
|<span data-ttu-id="92234-188">NULL</span><span class="sxs-lookup"><span data-stu-id="92234-188">null</span></span>|<span data-ttu-id="92234-189">False</span><span class="sxs-lookup"><span data-stu-id="92234-189">false</span></span>|<span data-ttu-id="92234-190">False</span><span class="sxs-lookup"><span data-stu-id="92234-190">false</span></span>|<span data-ttu-id="92234-191">NULL</span><span class="sxs-lookup"><span data-stu-id="92234-191">null</span></span>|  
|<span data-ttu-id="92234-192">NULL</span><span class="sxs-lookup"><span data-stu-id="92234-192">null</span></span>|<span data-ttu-id="92234-193">NULL</span><span class="sxs-lookup"><span data-stu-id="92234-193">null</span></span>|<span data-ttu-id="92234-194">NULL</span><span class="sxs-lookup"><span data-stu-id="92234-194">null</span></span>|<span data-ttu-id="92234-195">NULL</span><span class="sxs-lookup"><span data-stu-id="92234-195">null</span></span>|  

<span data-ttu-id="92234-196">Das Verhalten dieser Operatoren unterscheidet sich vom typischen Operatorverhalten bei Typen, die NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="92234-196">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="92234-197">In der Regel kann ein Operator, der für Operanden eines Werttyps definiert ist, auch mit Operanden des entsprechenden Nullable-Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="92234-197">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="92234-198">Ein solcher Operator erzeugt `null`, wenn einer seiner Operanden `null` ist.</span><span class="sxs-lookup"><span data-stu-id="92234-198">Such an operator produces `null` if any of its operands is `null`.</span></span> <span data-ttu-id="92234-199">Die `&`- und `|`-Operatoren können jedoch Nicht-NULL-Werte erzeugen, auch wenn einer der Operanden `null` ist.</span><span class="sxs-lookup"><span data-stu-id="92234-199">However, the `&` and `|` operators can produce non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="92234-200">Weitere Informationen zum Operatorverhalten bei Typen, die NULL-Werte zulassen, finden Sie im Abschnitt [Operatoren](../../programming-guide/nullable-types/using-nullable-types.md#operators) des Artikels [Verwenden von Nullable-Werttypen](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="92234-200">For more information about the operator behavior with nullable value types, see the [Operators](../../programming-guide/nullable-types/using-nullable-types.md#operators) section of the [Using nullable value types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="92234-201">Sie können auch die `!`- und `^`- Operatoren mit den `bool?`-Operanden verwenden, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="92234-201">You can also use the `!` and `^` operators with the `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="92234-202">Die bedingten logischen Operatoren `&&` und `||` unterstützen nicht die `bool?`-Operanden.</span><span class="sxs-lookup"><span data-stu-id="92234-202">The conditional logical operators `&&` and `||` don't support the `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="92234-203">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="92234-203">Compound assignment</span></span>

<span data-ttu-id="92234-204">Bei einem binären Operator `op` entspricht ein Verbundzuweisungsausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="92234-204">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="92234-205">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="92234-205">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="92234-206">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="92234-206">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="92234-207">Die `&`-, `|`- und `^`-Operatoren unterstützen die Verbundzuweisung, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="92234-207">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="92234-208">Die bedingten logischen Operatoren `&&` und `||` unterstützen nicht die Verbundzuweisung.</span><span class="sxs-lookup"><span data-stu-id="92234-208">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="92234-209">Operatorrangfolge</span><span class="sxs-lookup"><span data-stu-id="92234-209">Operator precedence</span></span>

<span data-ttu-id="92234-210">In der folgenden Liste sind die logischen Operatoren beginnend mit dem höchsten Rangfolgenoperator absteigend sortiert:</span><span class="sxs-lookup"><span data-stu-id="92234-210">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="92234-211">Logischer Negationsoperator `!`</span><span class="sxs-lookup"><span data-stu-id="92234-211">Logical negation operator `!`</span></span>
- <span data-ttu-id="92234-212">Logischer AND-Operator `&`</span><span class="sxs-lookup"><span data-stu-id="92234-212">Logical AND operator `&`</span></span>
- <span data-ttu-id="92234-213">Logischer exklusiver OR-Operator `^`</span><span class="sxs-lookup"><span data-stu-id="92234-213">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="92234-214">Logischer OR-Operator `|`</span><span class="sxs-lookup"><span data-stu-id="92234-214">Logical OR operator `|`</span></span>
- <span data-ttu-id="92234-215">Bedingter logischer AND-Operator `&&`</span><span class="sxs-lookup"><span data-stu-id="92234-215">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="92234-216">Bedingter logischer OR-Operator `||`</span><span class="sxs-lookup"><span data-stu-id="92234-216">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="92234-217">Verwenden Sie Klammern `()`, wenn Sie die Reihenfolge der Auswertung ändern möchten, die durch Operatorrangfolge festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="92234-217">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Precedence)]

<span data-ttu-id="92234-218">Die vollständige Liste der nach Rangfolgenebene sortierten C#-Operatoren finden Sie unter [C#-Operatoren](index.md).</span><span class="sxs-lookup"><span data-stu-id="92234-218">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="92234-219">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="92234-219">Operator overloadability</span></span>

<span data-ttu-id="92234-220">Ein benutzerdefinierter Typ kann die Operatoren `!`, `&`, `|` und `^` [überladen](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="92234-220">A user-defined type can [overload](operator-overloading.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="92234-221">Wenn ein binärer Operator überladen ist, wird der zugehörige Verbundzuweisungsoperator implizit auch überladen.</span><span class="sxs-lookup"><span data-stu-id="92234-221">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="92234-222">Ein benutzerdefinierter Typ kann einen Verbundzuweisungsoperator nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="92234-222">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="92234-223">Ein benutzerdefinierter Typ kann die bedingten logischen Operatoren `&&` und `||` nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="92234-223">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="92234-224">Wenn jedoch ein benutzerdefinierter Typ die [„true“ und „false“-Operatoren](true-false-operators.md) und den `&`- oder `|`-Operator in einer bestimmten Weise überlädt, kann die `&&`- bzw. `||`-Operation für die Operanden dieses Typs ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="92234-224">However, if a user-defined type overloads the [true and false operators](true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="92234-225">Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte bedingte logische Operatoren](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="92234-225">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="92234-226">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="92234-226">C# language specification</span></span>

<span data-ttu-id="92234-227">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="92234-227">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="92234-228">Logischer Negationsoperator</span><span class="sxs-lookup"><span data-stu-id="92234-228">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="92234-229">Logical operators (Logische Operatoren)</span><span class="sxs-lookup"><span data-stu-id="92234-229">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="92234-230">Conditional logical operators (Bedingte logische Operatoren)</span><span class="sxs-lookup"><span data-stu-id="92234-230">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="92234-231">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="92234-231">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="92234-232">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92234-232">See also</span></span>

- [<span data-ttu-id="92234-233">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="92234-233">C# reference</span></span>](../index.md)
- [<span data-ttu-id="92234-234">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="92234-234">C# operators</span></span>](index.md)
- [<span data-ttu-id="92234-235">Bitweise und Schiebeoperatoren</span><span class="sxs-lookup"><span data-stu-id="92234-235">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
