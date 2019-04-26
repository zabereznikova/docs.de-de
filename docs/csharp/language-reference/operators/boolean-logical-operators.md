---
title: Logische boolesche Operatoren – C#-Referenz
description: Erfahren Sie mehr über C#-Operatoren, die logische Negation, Konjunktion (AND), inklusive und exklusive Disjunktion (OR) mit booleschen Operanden durchführen.
ms.date: 04/08/2019
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
ms.openlocfilehash: de621b26334bbc9679ba7e48a9d5a0cbaec67eab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59427317"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="5ecdc-103">Logische boolesche Operatoren – C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="5ecdc-103">Boolean logical operators (C# Reference)</span></span>

<span data-ttu-id="5ecdc-104">Die folgenden Operatoren führen logische Vorgänge mit den [bool](../keywords/bool.md)-Operanden durch:</span><span class="sxs-lookup"><span data-stu-id="5ecdc-104">The following operators perform logical operations with the [bool](../keywords/bool.md) operands:</span></span>

- <span data-ttu-id="5ecdc-105">Unärer [`!` (logische Negation)](#logical-negation-operator-) Operator.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="5ecdc-106">Binäre [`&` (logisch AND)](#logical-and-operator-), [`|` (logisch OR)](#logical-or-operator-) und [`^` (logisch exklusiv OR)](#logical-exclusive-or-operator-) Operatoren.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="5ecdc-107">Diese Operatoren werten immer beide Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="5ecdc-108">Binäre [ `&&` (bedingt logisch AND)](#conditional-logical-and-operator-) und [ `||` (bedingt logisch OR)](#conditional-logical-or-operator-) Operatoren.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="5ecdc-109">Diese Operatoren werten den zweiten Operanden nur dann aus, wenn es notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-109">Those operators evaluate the second operand only if it's necessary.</span></span>

<span data-ttu-id="5ecdc-110">Für die Operanden der [ganzzahligen](../keywords/integral-types-table.md) Typen führen die Operatoren `&`, `|` und `^` bitweise logische Operationen durch.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-110">For the operands of [integral](../keywords/integral-types-table.md) types, the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="5ecdc-111">Logischer Negationsoperator: !</span><span class="sxs-lookup"><span data-stu-id="5ecdc-111">Logical negation operator !</span></span>

<span data-ttu-id="5ecdc-112">Der `!`-Operator berechnet die logische Negation des Operanden.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-112">The `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="5ecdc-113">Das heißt., er erzeugt `true`, wenn der Operand als `false` ausgewertet wird, und `false`, wenn der Operand als `true` ausgewertet wird:</span><span class="sxs-lookup"><span data-stu-id="5ecdc-113">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Negation)]

## <a name="logical-and-operator-amp"></a><span data-ttu-id="5ecdc-114">Logischer AND-Operator &amp;</span><span class="sxs-lookup"><span data-stu-id="5ecdc-114">Logical AND operator &amp;</span></span>

<span data-ttu-id="5ecdc-115">Der `&`-Operator berechnet die logische AND-Operation des Operanden.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-115">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="5ecdc-116">Das Ergebnis von `x & y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-116">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="5ecdc-117">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-117">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="5ecdc-118">Der `&`-Operator wertet beide Operanden aus, selbst wenn der erste Operand als `false` ausgewertet wird, sodass das Ergebnis unabhängig vom Wert des zweiten Operanden `false` sein muss.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-118">The `&` operator evaluates both operands even if the first operand evaluates to `false`, so that the result must be `false` regardless of the value of the second operand.</span></span>

<span data-ttu-id="5ecdc-119">Im folgenden Beispiel ist der zweite Operand des `&`-Operators ein Methodenaufruf, der unabhängig vom Wert des ersten Operanden durchgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="5ecdc-119">In the following example, the second operand of the `&` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#And)]

<span data-ttu-id="5ecdc-120">Der [bedingte logische AND-Operator](#conditional-logical-and-operator-) `&&` berechnet auch die logische AND-Operation der Operanden, wertet den zweiten Operanden aber nicht aus, wenn der erste Operand `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-120">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the second operand if the first operand evaluates to `false`.</span></span>

<span data-ttu-id="5ecdc-121">Für die Operanden von ganzzahligen Typen berechnet der `&`-Operator [bitweise logische AND](and-operator.md#integer-logical-bitwise-and-operator)-Operationen seiner Operanden.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-121">For the operands of integral types, the `&` operator computes [bitwise logical AND](and-operator.md#integer-logical-bitwise-and-operator) of its operands.</span></span> <span data-ttu-id="5ecdc-122">Der unäre `&`-Operator ist der [address-of-Operator](and-operator.md#unary-address-of-operator).</span><span class="sxs-lookup"><span data-stu-id="5ecdc-122">The unary `&` operator is the [address-of operator](and-operator.md#unary-address-of-operator).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="5ecdc-123">Logischer exklusiver OR-Operator: ^</span><span class="sxs-lookup"><span data-stu-id="5ecdc-123">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="5ecdc-124">Die `^`-Operator berechnet das logische exklusive OR, auch als logischer XOR bezeichnet, seiner Operanden.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-124">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="5ecdc-125">Das Ergebnis von `x ^ y` ist `true`, wenn `x` `true` ergibt und `y` `false`ergibt, oder `x` `false` ergibt und `y` `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-125">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="5ecdc-126">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-126">Otherwise, the result is `false`.</span></span> <span data-ttu-id="5ecdc-127">Das heißt, für die `bool`-Operanden berechnet der `^`-Operator das gleiche Ergebnis wie der [Ungleichheitsoperator](equality-operators.md#inequality-operator-) `!=`.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-127">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Xor)]

<span data-ttu-id="5ecdc-128">Für die Operanden von ganzzahligen Typen berechnet der `^`-Operator [bitweise logische exklusive OR](xor-operator.md)-Operationen seiner Operanden.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-128">For the operands of integral types, the `^` operator computes [bitwise logical exclusive OR](xor-operator.md) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="5ecdc-129">Logischer OR-Operator: |</span><span class="sxs-lookup"><span data-stu-id="5ecdc-129">Logical OR operator |</span></span>

<span data-ttu-id="5ecdc-130">Der `|`-Operator berechnet die logische OR-Operation des Operanden.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-130">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="5ecdc-131">Das Ergebnis von `x | y` ist `true`, wenn entweder `x` oder `y` `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-131">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="5ecdc-132">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-132">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="5ecdc-133">Der `|`-Operator wertet beide Operanden aus, selbst wenn der erste Operand als `true` ausgewertet wird, sodass das Ergebnis unabhängig vom Wert des zweiten Operanden `true` sein muss.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-133">The `|` operator evaluates both operands even if the first operand evaluates to `true`, so that the result must be `true` regardless of the value of the second operand.</span></span>

<span data-ttu-id="5ecdc-134">Im folgenden Beispiel ist der zweite Operand des `|`-Operators ein Methodenaufruf, der unabhängig vom Wert des ersten Operanden durchgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="5ecdc-134">In the following example, the second operand of the `|` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Or)]

<span data-ttu-id="5ecdc-135">Der [bedingte logische OR-Operator](#conditional-logical-or-operator-) `||` berechnet auch die logische OR-Operation der Operanden, wertet den zweiten Operanden aber nicht aus, wenn der erste Operand `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-135">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the second operand if the first operand evaluates to `true`.</span></span>

<span data-ttu-id="5ecdc-136">Für die Operanden von ganzzahligen Typen berechnet der `|`-Operator [bitweise logische OR](or-operator.md)-Operationen seiner Operanden.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-136">For the operands of integral types, the `|` operator computes [bitwise logical OR](or-operator.md) of its operands.</span></span>

## <a name="conditional-logical-and-operator-ampamp"></a><span data-ttu-id="5ecdc-137">Bedingter logischer AND-Operator &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="5ecdc-137">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="5ecdc-138">Der bedingte logische AND-Operator `&&`, auch bekannt als der "kurzschließender" logischer AND-Operator bezeichnet, berechnet die logische AND-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-138">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="5ecdc-139">Das Ergebnis von `x && y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-139">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="5ecdc-140">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-140">Otherwise, the result is `false`.</span></span> <span data-ttu-id="5ecdc-141">Wenn der erste Operand als `false` ausgewertet wird, wird der zweite Operand nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-141">If the first operand evaluates to `false`, the second operand is not evaluated.</span></span>

<span data-ttu-id="5ecdc-142">Im folgenden Beispiel ist der zweite Operand des `&&`-Operators ein Methodenaufruf, der nicht durchgeführt wird, wenn der erste Operand `false` ergibt:</span><span class="sxs-lookup"><span data-stu-id="5ecdc-142">In the following example, the second operand of the `&&` operator is a method call, which isn't performed if the first operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="5ecdc-143">Der [logische AND-Operator](#logical-and-operator-) `&` berechnet auch die logische AND-Operation der Operanden, es werden jedoch immer beide Operanden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-143">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="5ecdc-144">Bedingter logischer OR-Operator ||</span><span class="sxs-lookup"><span data-stu-id="5ecdc-144">Conditional logical OR operator ||</span></span>

<span data-ttu-id="5ecdc-145">Der bedingte logische OR-Operator `||`, auch bekannt als der "kurzschließender" logischer OR-Operator bezeichnet, berechnet die logische OR-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-145">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="5ecdc-146">Das Ergebnis von `x || y` ist `true`, wenn entweder `x` oder `y` `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-146">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="5ecdc-147">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-147">Otherwise, the result is `false`.</span></span> <span data-ttu-id="5ecdc-148">Wenn der erste Operand als `true` ausgewertet wird, wird der zweite Operand nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-148">If the first operand evaluates to `true`, the second operand is not evaluated.</span></span>

<span data-ttu-id="5ecdc-149">Im folgenden Beispiel ist der zweite Operand des `||`-Operators ein Methodenaufruf, der nicht durchgeführt wird, wenn der erste Operand `true` ergibt:</span><span class="sxs-lookup"><span data-stu-id="5ecdc-149">In the following example, the second operand of the `||` operator is a method call, which isn't performed if the first operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="5ecdc-150">Der [logische OR-Operator](#logical-or-operator-) `|` berechnet auch die logische OR-Operation der Operanden, es werden jedoch immer beide Operanden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-150">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="5ecdc-151">Logische boolesche Operatoren, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="5ecdc-151">Nullable Boolean logical operators</span></span>

<span data-ttu-id="5ecdc-152">Für die `bool?`-Operanden unterstützen die `&`- und `|`-Operatoren die dreiwertige Logik.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-152">For the `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="5ecdc-153">Die Semantik dieser Operatoren ist in der folgenden Tabelle definiert:</span><span class="sxs-lookup"><span data-stu-id="5ecdc-153">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="5ecdc-154">w</span><span class="sxs-lookup"><span data-stu-id="5ecdc-154">x</span></span>|<span data-ttu-id="5ecdc-155">y</span><span class="sxs-lookup"><span data-stu-id="5ecdc-155">y</span></span>|<span data-ttu-id="5ecdc-156">x&y</span><span class="sxs-lookup"><span data-stu-id="5ecdc-156">x&y</span></span>|<span data-ttu-id="5ecdc-157">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="5ecdc-157">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="5ecdc-158">true</span><span class="sxs-lookup"><span data-stu-id="5ecdc-158">true</span></span>|<span data-ttu-id="5ecdc-159">true</span><span class="sxs-lookup"><span data-stu-id="5ecdc-159">true</span></span>|<span data-ttu-id="5ecdc-160">true</span><span class="sxs-lookup"><span data-stu-id="5ecdc-160">true</span></span>|<span data-ttu-id="5ecdc-161">true</span><span class="sxs-lookup"><span data-stu-id="5ecdc-161">true</span></span>|  
|<span data-ttu-id="5ecdc-162">true</span><span class="sxs-lookup"><span data-stu-id="5ecdc-162">true</span></span>|<span data-ttu-id="5ecdc-163">False</span><span class="sxs-lookup"><span data-stu-id="5ecdc-163">false</span></span>|<span data-ttu-id="5ecdc-164">false</span><span class="sxs-lookup"><span data-stu-id="5ecdc-164">false</span></span>|<span data-ttu-id="5ecdc-165">true</span><span class="sxs-lookup"><span data-stu-id="5ecdc-165">true</span></span>|  
|<span data-ttu-id="5ecdc-166">true</span><span class="sxs-lookup"><span data-stu-id="5ecdc-166">true</span></span>|<span data-ttu-id="5ecdc-167">NULL</span><span class="sxs-lookup"><span data-stu-id="5ecdc-167">null</span></span>|<span data-ttu-id="5ecdc-168">NULL</span><span class="sxs-lookup"><span data-stu-id="5ecdc-168">null</span></span>|<span data-ttu-id="5ecdc-169">true</span><span class="sxs-lookup"><span data-stu-id="5ecdc-169">true</span></span>|  
|<span data-ttu-id="5ecdc-170">False</span><span class="sxs-lookup"><span data-stu-id="5ecdc-170">false</span></span>|<span data-ttu-id="5ecdc-171">true</span><span class="sxs-lookup"><span data-stu-id="5ecdc-171">true</span></span>|<span data-ttu-id="5ecdc-172">False</span><span class="sxs-lookup"><span data-stu-id="5ecdc-172">false</span></span>|<span data-ttu-id="5ecdc-173">true</span><span class="sxs-lookup"><span data-stu-id="5ecdc-173">true</span></span>|  
|<span data-ttu-id="5ecdc-174">False</span><span class="sxs-lookup"><span data-stu-id="5ecdc-174">false</span></span>|<span data-ttu-id="5ecdc-175">False</span><span class="sxs-lookup"><span data-stu-id="5ecdc-175">false</span></span>|<span data-ttu-id="5ecdc-176">False</span><span class="sxs-lookup"><span data-stu-id="5ecdc-176">false</span></span>|<span data-ttu-id="5ecdc-177">False</span><span class="sxs-lookup"><span data-stu-id="5ecdc-177">false</span></span>|  
|<span data-ttu-id="5ecdc-178">False</span><span class="sxs-lookup"><span data-stu-id="5ecdc-178">false</span></span>|<span data-ttu-id="5ecdc-179">NULL</span><span class="sxs-lookup"><span data-stu-id="5ecdc-179">null</span></span>|<span data-ttu-id="5ecdc-180">False</span><span class="sxs-lookup"><span data-stu-id="5ecdc-180">false</span></span>|<span data-ttu-id="5ecdc-181">NULL</span><span class="sxs-lookup"><span data-stu-id="5ecdc-181">null</span></span>|  
|<span data-ttu-id="5ecdc-182">NULL</span><span class="sxs-lookup"><span data-stu-id="5ecdc-182">null</span></span>|<span data-ttu-id="5ecdc-183">true</span><span class="sxs-lookup"><span data-stu-id="5ecdc-183">true</span></span>|<span data-ttu-id="5ecdc-184">NULL</span><span class="sxs-lookup"><span data-stu-id="5ecdc-184">null</span></span>|<span data-ttu-id="5ecdc-185">true</span><span class="sxs-lookup"><span data-stu-id="5ecdc-185">true</span></span>|  
|<span data-ttu-id="5ecdc-186">NULL</span><span class="sxs-lookup"><span data-stu-id="5ecdc-186">null</span></span>|<span data-ttu-id="5ecdc-187">False</span><span class="sxs-lookup"><span data-stu-id="5ecdc-187">false</span></span>|<span data-ttu-id="5ecdc-188">False</span><span class="sxs-lookup"><span data-stu-id="5ecdc-188">false</span></span>|<span data-ttu-id="5ecdc-189">NULL</span><span class="sxs-lookup"><span data-stu-id="5ecdc-189">null</span></span>|  
|<span data-ttu-id="5ecdc-190">NULL</span><span class="sxs-lookup"><span data-stu-id="5ecdc-190">null</span></span>|<span data-ttu-id="5ecdc-191">NULL</span><span class="sxs-lookup"><span data-stu-id="5ecdc-191">null</span></span>|<span data-ttu-id="5ecdc-192">NULL</span><span class="sxs-lookup"><span data-stu-id="5ecdc-192">null</span></span>|<span data-ttu-id="5ecdc-193">NULL</span><span class="sxs-lookup"><span data-stu-id="5ecdc-193">null</span></span>|  

<span data-ttu-id="5ecdc-194">Das Verhalten dieser Operatoren unterscheidet sich vom typischen Operatorverhalten bei Typen, die NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-194">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="5ecdc-195">In der Regel kann ein Operator, der für Operanden eines Werttyps definiert ist, auch mit Operanden des entsprechenden Nullable-Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-195">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="5ecdc-196">Ein solcher Operator erzeugt `null`, wenn einer seiner Operanden `null` ist.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-196">Such an operator produces `null` if any of its operands is `null`.</span></span> <span data-ttu-id="5ecdc-197">Die `&`- und `|`-Operatoren können jedoch Nicht-NULL-Werte erzeugen, auch wenn einer der Operanden `null` ist.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-197">However, the `&` and `|` operators can produce non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="5ecdc-198">Weitere Informationen zum Operatorverhalten bei Typen, die NULL-Werte zulassen, finden Sie im Abschnitt [Operatoren](../../programming-guide/nullable-types/using-nullable-types.md#operators) des Artikels [Verwenden von Nullable-Typen](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="5ecdc-198">For more information about the operator behavior with nullable value types, see the [Operators](../../programming-guide/nullable-types/using-nullable-types.md#operators) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="5ecdc-199">Sie können auch die `!`- und `^`- Operatoren mit den `bool?`-Operanden verwenden, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="5ecdc-199">You can also use the `!` and `^` operators with the `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="5ecdc-200">Die bedingten logischen Operatoren `&&` und `||` unterstützen nicht die `bool?`-Operanden.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-200">The conditional logical operators `&&` and `||` don't support the `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="5ecdc-201">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="5ecdc-201">Compound assignment</span></span>

<span data-ttu-id="5ecdc-202">Bei einem binären Operator `op` entspricht ein Verbundzuweisungsausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="5ecdc-202">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="5ecdc-203">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="5ecdc-203">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="5ecdc-204">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-204">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="5ecdc-205">Die `&`-, `|`- und `^`-Operatoren unterstützen die Verbundzuweisung, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="5ecdc-205">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="5ecdc-206">Die bedingten logischen Operatoren `&&` und `||` unterstützen nicht die Verbundzuweisung.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-206">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="5ecdc-207">Operatorrangfolge</span><span class="sxs-lookup"><span data-stu-id="5ecdc-207">Operator precedence</span></span>

<span data-ttu-id="5ecdc-208">In der folgenden Liste sind die logischen Operatoren beginnend mit dem höchsten Rangfolgenoperator absteigend sortiert:</span><span class="sxs-lookup"><span data-stu-id="5ecdc-208">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="5ecdc-209">Logischer Negationsoperator `!`</span><span class="sxs-lookup"><span data-stu-id="5ecdc-209">Logical negation operator `!`</span></span>
- <span data-ttu-id="5ecdc-210">Logischer AND-Operator `&`</span><span class="sxs-lookup"><span data-stu-id="5ecdc-210">Logical AND operator `&`</span></span>
- <span data-ttu-id="5ecdc-211">Logischer exklusiver OR-Operator `^`</span><span class="sxs-lookup"><span data-stu-id="5ecdc-211">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="5ecdc-212">Logischer OR-Operator `|`</span><span class="sxs-lookup"><span data-stu-id="5ecdc-212">Logical OR operator `|`</span></span>
- <span data-ttu-id="5ecdc-213">Bedingter logischer AND-Operator `&&`</span><span class="sxs-lookup"><span data-stu-id="5ecdc-213">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="5ecdc-214">Bedingter logischer OR-Operator `||`</span><span class="sxs-lookup"><span data-stu-id="5ecdc-214">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="5ecdc-215">Verwenden Sie Klammern `()`, wenn Sie die Reihenfolge der Auswertung ändern möchten, die durch Operatorrangfolge festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="5ecdc-215">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Precedence)]

<span data-ttu-id="5ecdc-216">Die vollständige Liste der nach Rangfolgenebene sortierten C#-Operatoren finden Sie unter [C#-Operatoren](index.md).</span><span class="sxs-lookup"><span data-stu-id="5ecdc-216">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="5ecdc-217">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="5ecdc-217">Operator overloadability</span></span>

<span data-ttu-id="5ecdc-218">Ein benutzerdefinierter Typ kann die Operatoren `!`, `&`, `|` und `^` [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="5ecdc-218">A user-defined type can [overload](../keywords/operator.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="5ecdc-219">Wenn ein binärer Operator überladen ist, wird der zugehörige Verbundzuweisungsoperator implizit auch überladen.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-219">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="5ecdc-220">Ein benutzerdefinierter Typ kann einen Verbundzuweisungsoperator nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-220">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="5ecdc-221">Ein benutzerdefinierter Typ kann die bedingten logischen Operatoren `&&` und `||` nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-221">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="5ecdc-222">Wenn jedoch ein benutzerdefinierter Typ die [„true“ und „false“-Operatoren](../keywords/true-false-operators.md) und den `&`- oder `|`-Operator in einer bestimmten Weise überlädt, kann die `&&`- bzw. `||`-Operation für die Operanden dieses Typs ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="5ecdc-222">However, if a user-defined type overloads the [true and false operators](../keywords/true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="5ecdc-223">Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte bedingte logische Operatoren](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) der [C#-Programmiersprachenspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="5ecdc-223">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5ecdc-224">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="5ecdc-224">C# language specification</span></span>

<span data-ttu-id="5ecdc-225">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Programmiersprachenspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="5ecdc-225">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="5ecdc-226">Logischer Negationsoperator</span><span class="sxs-lookup"><span data-stu-id="5ecdc-226">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="5ecdc-227">Logische Operatoren</span><span class="sxs-lookup"><span data-stu-id="5ecdc-227">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="5ecdc-228">Bedingte logische Operatoren</span><span class="sxs-lookup"><span data-stu-id="5ecdc-228">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)

## <a name="see-also"></a><span data-ttu-id="5ecdc-229">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ecdc-229">See also</span></span>

- [<span data-ttu-id="5ecdc-230">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="5ecdc-230">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5ecdc-231">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5ecdc-231">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5ecdc-232">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="5ecdc-232">C# Operators</span></span>](index.md)
