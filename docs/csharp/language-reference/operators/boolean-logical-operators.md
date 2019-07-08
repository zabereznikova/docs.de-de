---
title: 'Logische boolesche Operatoren: C#-Referenz'
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
ms.openlocfilehash: b2c3553f527e9fec8856297c7424a081b5b31db0
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2019
ms.locfileid: "67609925"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="e63d0-103">Logische boolesche Operatoren (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e63d0-103">Boolean logical operators (C# reference)</span></span>

<span data-ttu-id="e63d0-104">Die folgenden Operatoren führen logische Vorgänge mit den [bool](../keywords/bool.md)-Operanden durch:</span><span class="sxs-lookup"><span data-stu-id="e63d0-104">The following operators perform logical operations with the [bool](../keywords/bool.md) operands:</span></span>

- <span data-ttu-id="e63d0-105">Unärer [`!` (logische Negation)](#logical-negation-operator-) Operator.</span><span class="sxs-lookup"><span data-stu-id="e63d0-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="e63d0-106">Binäre [`&` (logisch AND)](#logical-and-operator-), [`|` (logisch OR)](#logical-or-operator-) und [`^` (logisch exklusiv OR)](#logical-exclusive-or-operator-) Operatoren.</span><span class="sxs-lookup"><span data-stu-id="e63d0-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="e63d0-107">Diese Operatoren werten immer beide Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="e63d0-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="e63d0-108">Binäre [ `&&` (bedingt logisch AND)](#conditional-logical-and-operator-) und [ `||` (bedingt logisch OR)](#conditional-logical-or-operator-) Operatoren.</span><span class="sxs-lookup"><span data-stu-id="e63d0-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="e63d0-109">Diese Operatoren werten den rechten Operanden nur dann aus, wenn es notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="e63d0-109">Those operators evaluate the right-hand operand only if it's necessary.</span></span>

<span data-ttu-id="e63d0-110">Für die Operanden der [integralen](../builtin-types/integral-numeric-types.md) Typen führen die Operatoren `&`, `|` und `^` bitweise logische Operationen durch.</span><span class="sxs-lookup"><span data-stu-id="e63d0-110">For the operands of the [integral](../builtin-types/integral-numeric-types.md) types, the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="e63d0-111">Weitere Informationen finden Sie unter [Bitweise und Schiebeoperatoren](bitwise-and-shift-operators.md).</span><span class="sxs-lookup"><span data-stu-id="e63d0-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="e63d0-112">Logischer Negationsoperator: !</span><span class="sxs-lookup"><span data-stu-id="e63d0-112">Logical negation operator !</span></span>

<span data-ttu-id="e63d0-113">Der `!`-Operator berechnet die logische Negation des Operanden.</span><span class="sxs-lookup"><span data-stu-id="e63d0-113">The `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="e63d0-114">Das heißt., er erzeugt `true`, wenn der Operand als `false` ausgewertet wird, und `false`, wenn der Operand als `true` ausgewertet wird:</span><span class="sxs-lookup"><span data-stu-id="e63d0-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Negation)]

## <a name="logical-and-operator-"></a> <span data-ttu-id="e63d0-115">Logischer AND-Operator &amp;</span><span class="sxs-lookup"><span data-stu-id="e63d0-115">Logical AND operator &amp;</span></span>

<span data-ttu-id="e63d0-116">Der `&`-Operator berechnet die logische AND-Operation des Operanden.</span><span class="sxs-lookup"><span data-stu-id="e63d0-116">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="e63d0-117">Das Ergebnis von `x & y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="e63d0-117">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="e63d0-118">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="e63d0-118">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="e63d0-119">Der `&`-Operator wertet beide Operanden aus, selbst wenn der linke Operand als `false` ausgewertet wird, sodass das Ergebnis unabhängig vom Wert des rechten Operanden `false` sein muss.</span><span class="sxs-lookup"><span data-stu-id="e63d0-119">The `&` operator evaluates both operands even if the left-hand operand evaluates to `false`, so that the result must be `false` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="e63d0-120">Im folgenden Beispiel ist der rechte Operand des `&`-Operators ein Methodenaufruf, der unabhängig vom Wert des linken Operanden ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="e63d0-120">In the following example, the right-hand operand of the `&` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#And)]

<span data-ttu-id="e63d0-121">Der [bedingte logische AND-Operator](#conditional-logical-and-operator-) `&&` berechnet auch die logische AND-Operation der Operanden, wertet den rechten Operanden aber nicht aus, wenn der linke Operand `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="e63d0-121">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `false`.</span></span>

<span data-ttu-id="e63d0-122">Für die Operanden der integralen Typen berechnet der Operator `&` [bitweises logisches UND](bitwise-and-shift-operators.md#logical-and-operator-) für seine Operanden.</span><span class="sxs-lookup"><span data-stu-id="e63d0-122">For the operands of the integral types, the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="e63d0-123">Der unäre `&`-Operator ist der [address-of-Operator](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="e63d0-123">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="e63d0-124">Logischer exklusiver OR-Operator: ^</span><span class="sxs-lookup"><span data-stu-id="e63d0-124">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="e63d0-125">Die `^`-Operator berechnet das logische exklusive OR, auch als logischer XOR bezeichnet, seiner Operanden.</span><span class="sxs-lookup"><span data-stu-id="e63d0-125">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="e63d0-126">Das Ergebnis von `x ^ y` ist `true`, wenn `x` `true` ergibt und `y` `false`ergibt, oder `x` `false` ergibt und `y` `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="e63d0-126">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="e63d0-127">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="e63d0-127">Otherwise, the result is `false`.</span></span> <span data-ttu-id="e63d0-128">Das heißt, für die `bool`-Operanden berechnet der `^`-Operator das gleiche Ergebnis wie der [Ungleichheitsoperator](equality-operators.md#inequality-operator-) `!=`.</span><span class="sxs-lookup"><span data-stu-id="e63d0-128">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Xor)]

<span data-ttu-id="e63d0-129">Für die Operanden der integralen Typen berechnet der Operator `^` [bitweises logisches exklusives ODER](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) für seine Operanden.</span><span class="sxs-lookup"><span data-stu-id="e63d0-129">For the operands of the integral types, the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="e63d0-130">Logischer OR-Operator: |</span><span class="sxs-lookup"><span data-stu-id="e63d0-130">Logical OR operator |</span></span>

<span data-ttu-id="e63d0-131">Der `|`-Operator berechnet die logische OR-Operation des Operanden.</span><span class="sxs-lookup"><span data-stu-id="e63d0-131">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="e63d0-132">Das Ergebnis von `x | y` ist `true`, wenn entweder `x` oder `y` `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="e63d0-132">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="e63d0-133">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="e63d0-133">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="e63d0-134">Der `|`-Operator wertet beide Operanden aus, selbst wenn der linke Operand als `true` ausgewertet wird, sodass das Ergebnis unabhängig vom Wert des rechten Operanden `true` sein muss.</span><span class="sxs-lookup"><span data-stu-id="e63d0-134">The `|` operator evaluates both operands even if the left-hand operand evaluates to `true`, so that the result must be `true` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="e63d0-135">Im folgenden Beispiel ist der rechte Operand des `|`-Operators ein Methodenaufruf, der unabhängig vom Wert des linken Operanden ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="e63d0-135">In the following example, the right-hand operand of the `|` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Or)]

<span data-ttu-id="e63d0-136">Der [bedingte logische OR-Operator](#conditional-logical-or-operator-) `||` berechnet auch die logische OR-Operation der Operanden, wertet den rechten Operanden aber nicht aus, wenn der linke Operand `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="e63d0-136">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `true`.</span></span>

<span data-ttu-id="e63d0-137">Für die Operanden der integralen Typen berechnet der Operator `|` [bitweises logisches ODER](bitwise-and-shift-operators.md#logical-or-operator-) für seine Operanden.</span><span class="sxs-lookup"><span data-stu-id="e63d0-137">For the operands of the integral types, the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-"></a> <span data-ttu-id="e63d0-138">Bedingter logischer AND-Operator &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="e63d0-138">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="e63d0-139">Der bedingte logische AND-Operator `&&`, auch bekannt als der "kurzschließender" logischer AND-Operator bezeichnet, berechnet die logische AND-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="e63d0-139">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="e63d0-140">Das Ergebnis von `x && y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="e63d0-140">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="e63d0-141">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="e63d0-141">Otherwise, the result is `false`.</span></span> <span data-ttu-id="e63d0-142">Wenn `x` als `false` ausgewertet wird, wird `y` nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="e63d0-142">If `x` evaluates to `false`, `y` is not evaluated.</span></span>

<span data-ttu-id="e63d0-143">Im folgenden Beispiel ist der rechte Operand des `&&`-Operators ein Methodenaufruf, der nicht ausgeführt wird, wenn der linke Operand `false` ergibt:</span><span class="sxs-lookup"><span data-stu-id="e63d0-143">In the following example, the right-hand operand of the `&&` operator is a method call, which isn't performed if the left-hand operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="e63d0-144">Der [logische AND-Operator](#logical-and-operator-) `&` berechnet auch die logische AND-Operation der Operanden, es werden jedoch immer beide Operanden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="e63d0-144">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="e63d0-145">Bedingter logischer OR-Operator ||</span><span class="sxs-lookup"><span data-stu-id="e63d0-145">Conditional logical OR operator ||</span></span>

<span data-ttu-id="e63d0-146">Der bedingte logische OR-Operator `||`, auch bekannt als der "kurzschließender" logischer OR-Operator bezeichnet, berechnet die logische OR-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="e63d0-146">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="e63d0-147">Das Ergebnis von `x || y` ist `true`, wenn entweder `x` oder `y` `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="e63d0-147">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="e63d0-148">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="e63d0-148">Otherwise, the result is `false`.</span></span> <span data-ttu-id="e63d0-149">Wenn `x` als `true` ausgewertet wird, wird `y` nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="e63d0-149">If `x` evaluates to `true`, `y` is not evaluated.</span></span>

<span data-ttu-id="e63d0-150">Im folgenden Beispiel ist der rechte Operand des `||`-Operators ein Methodenaufruf, der nicht ausgeführt wird, wenn der linke Operand `true` ergibt:</span><span class="sxs-lookup"><span data-stu-id="e63d0-150">In the following example, the right-hand operand of the `||` operator is a method call, which isn't performed if the left-hand operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="e63d0-151">Der [logische OR-Operator](#logical-or-operator-) `|` berechnet auch die logische OR-Operation der Operanden, es werden jedoch immer beide Operanden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="e63d0-151">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="e63d0-152">Logische boolesche Operatoren, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="e63d0-152">Nullable Boolean logical operators</span></span>

<span data-ttu-id="e63d0-153">Für die `bool?`-Operanden unterstützen die `&`- und `|`-Operatoren die dreiwertige Logik.</span><span class="sxs-lookup"><span data-stu-id="e63d0-153">For the `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="e63d0-154">Die Semantik dieser Operatoren ist in der folgenden Tabelle definiert:</span><span class="sxs-lookup"><span data-stu-id="e63d0-154">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="e63d0-155">w</span><span class="sxs-lookup"><span data-stu-id="e63d0-155">x</span></span>|<span data-ttu-id="e63d0-156">y</span><span class="sxs-lookup"><span data-stu-id="e63d0-156">y</span></span>|<span data-ttu-id="e63d0-157">x&y</span><span class="sxs-lookup"><span data-stu-id="e63d0-157">x&y</span></span>|<span data-ttu-id="e63d0-158">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="e63d0-158">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="e63d0-159">true</span><span class="sxs-lookup"><span data-stu-id="e63d0-159">true</span></span>|<span data-ttu-id="e63d0-160">true</span><span class="sxs-lookup"><span data-stu-id="e63d0-160">true</span></span>|<span data-ttu-id="e63d0-161">true</span><span class="sxs-lookup"><span data-stu-id="e63d0-161">true</span></span>|<span data-ttu-id="e63d0-162">true</span><span class="sxs-lookup"><span data-stu-id="e63d0-162">true</span></span>|  
|<span data-ttu-id="e63d0-163">true</span><span class="sxs-lookup"><span data-stu-id="e63d0-163">true</span></span>|<span data-ttu-id="e63d0-164">False</span><span class="sxs-lookup"><span data-stu-id="e63d0-164">false</span></span>|<span data-ttu-id="e63d0-165">false</span><span class="sxs-lookup"><span data-stu-id="e63d0-165">false</span></span>|<span data-ttu-id="e63d0-166">true</span><span class="sxs-lookup"><span data-stu-id="e63d0-166">true</span></span>|  
|<span data-ttu-id="e63d0-167">true</span><span class="sxs-lookup"><span data-stu-id="e63d0-167">true</span></span>|<span data-ttu-id="e63d0-168">NULL</span><span class="sxs-lookup"><span data-stu-id="e63d0-168">null</span></span>|<span data-ttu-id="e63d0-169">NULL</span><span class="sxs-lookup"><span data-stu-id="e63d0-169">null</span></span>|<span data-ttu-id="e63d0-170">true</span><span class="sxs-lookup"><span data-stu-id="e63d0-170">true</span></span>|  
|<span data-ttu-id="e63d0-171">False</span><span class="sxs-lookup"><span data-stu-id="e63d0-171">false</span></span>|<span data-ttu-id="e63d0-172">true</span><span class="sxs-lookup"><span data-stu-id="e63d0-172">true</span></span>|<span data-ttu-id="e63d0-173">False</span><span class="sxs-lookup"><span data-stu-id="e63d0-173">false</span></span>|<span data-ttu-id="e63d0-174">true</span><span class="sxs-lookup"><span data-stu-id="e63d0-174">true</span></span>|  
|<span data-ttu-id="e63d0-175">False</span><span class="sxs-lookup"><span data-stu-id="e63d0-175">false</span></span>|<span data-ttu-id="e63d0-176">False</span><span class="sxs-lookup"><span data-stu-id="e63d0-176">false</span></span>|<span data-ttu-id="e63d0-177">False</span><span class="sxs-lookup"><span data-stu-id="e63d0-177">false</span></span>|<span data-ttu-id="e63d0-178">False</span><span class="sxs-lookup"><span data-stu-id="e63d0-178">false</span></span>|  
|<span data-ttu-id="e63d0-179">False</span><span class="sxs-lookup"><span data-stu-id="e63d0-179">false</span></span>|<span data-ttu-id="e63d0-180">NULL</span><span class="sxs-lookup"><span data-stu-id="e63d0-180">null</span></span>|<span data-ttu-id="e63d0-181">False</span><span class="sxs-lookup"><span data-stu-id="e63d0-181">false</span></span>|<span data-ttu-id="e63d0-182">NULL</span><span class="sxs-lookup"><span data-stu-id="e63d0-182">null</span></span>|  
|<span data-ttu-id="e63d0-183">NULL</span><span class="sxs-lookup"><span data-stu-id="e63d0-183">null</span></span>|<span data-ttu-id="e63d0-184">true</span><span class="sxs-lookup"><span data-stu-id="e63d0-184">true</span></span>|<span data-ttu-id="e63d0-185">NULL</span><span class="sxs-lookup"><span data-stu-id="e63d0-185">null</span></span>|<span data-ttu-id="e63d0-186">true</span><span class="sxs-lookup"><span data-stu-id="e63d0-186">true</span></span>|  
|<span data-ttu-id="e63d0-187">NULL</span><span class="sxs-lookup"><span data-stu-id="e63d0-187">null</span></span>|<span data-ttu-id="e63d0-188">False</span><span class="sxs-lookup"><span data-stu-id="e63d0-188">false</span></span>|<span data-ttu-id="e63d0-189">False</span><span class="sxs-lookup"><span data-stu-id="e63d0-189">false</span></span>|<span data-ttu-id="e63d0-190">NULL</span><span class="sxs-lookup"><span data-stu-id="e63d0-190">null</span></span>|  
|<span data-ttu-id="e63d0-191">NULL</span><span class="sxs-lookup"><span data-stu-id="e63d0-191">null</span></span>|<span data-ttu-id="e63d0-192">NULL</span><span class="sxs-lookup"><span data-stu-id="e63d0-192">null</span></span>|<span data-ttu-id="e63d0-193">NULL</span><span class="sxs-lookup"><span data-stu-id="e63d0-193">null</span></span>|<span data-ttu-id="e63d0-194">NULL</span><span class="sxs-lookup"><span data-stu-id="e63d0-194">null</span></span>|  

<span data-ttu-id="e63d0-195">Das Verhalten dieser Operatoren unterscheidet sich vom typischen Operatorverhalten bei Typen, die NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="e63d0-195">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="e63d0-196">In der Regel kann ein Operator, der für Operanden eines Werttyps definiert ist, auch mit Operanden des entsprechenden Nullable-Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e63d0-196">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="e63d0-197">Ein solcher Operator erzeugt `null`, wenn einer seiner Operanden `null` ist.</span><span class="sxs-lookup"><span data-stu-id="e63d0-197">Such an operator produces `null` if any of its operands is `null`.</span></span> <span data-ttu-id="e63d0-198">Die `&`- und `|`-Operatoren können jedoch Nicht-NULL-Werte erzeugen, auch wenn einer der Operanden `null` ist.</span><span class="sxs-lookup"><span data-stu-id="e63d0-198">However, the `&` and `|` operators can produce non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="e63d0-199">Weitere Informationen zum Operatorverhalten bei Typen, die NULL-Werte zulassen, finden Sie im Abschnitt [Operatoren](../../programming-guide/nullable-types/using-nullable-types.md#operators) des Artikels [Verwenden von Nullable-Typen](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="e63d0-199">For more information about the operator behavior with nullable value types, see the [Operators](../../programming-guide/nullable-types/using-nullable-types.md#operators) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="e63d0-200">Sie können auch die `!`- und `^`- Operatoren mit den `bool?`-Operanden verwenden, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="e63d0-200">You can also use the `!` and `^` operators with the `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="e63d0-201">Die bedingten logischen Operatoren `&&` und `||` unterstützen nicht die `bool?`-Operanden.</span><span class="sxs-lookup"><span data-stu-id="e63d0-201">The conditional logical operators `&&` and `||` don't support the `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="e63d0-202">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="e63d0-202">Compound assignment</span></span>

<span data-ttu-id="e63d0-203">Bei einem binären Operator `op` entspricht ein Verbundzuweisungsausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="e63d0-203">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="e63d0-204">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="e63d0-204">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="e63d0-205">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="e63d0-205">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="e63d0-206">Die `&`-, `|`- und `^`-Operatoren unterstützen die Verbundzuweisung, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="e63d0-206">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="e63d0-207">Die bedingten logischen Operatoren `&&` und `||` unterstützen nicht die Verbundzuweisung.</span><span class="sxs-lookup"><span data-stu-id="e63d0-207">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="e63d0-208">Operatorrangfolge</span><span class="sxs-lookup"><span data-stu-id="e63d0-208">Operator precedence</span></span>

<span data-ttu-id="e63d0-209">In der folgenden Liste sind die logischen Operatoren beginnend mit dem höchsten Rangfolgenoperator absteigend sortiert:</span><span class="sxs-lookup"><span data-stu-id="e63d0-209">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="e63d0-210">Logischer Negationsoperator `!`</span><span class="sxs-lookup"><span data-stu-id="e63d0-210">Logical negation operator `!`</span></span>
- <span data-ttu-id="e63d0-211">Logischer AND-Operator `&`</span><span class="sxs-lookup"><span data-stu-id="e63d0-211">Logical AND operator `&`</span></span>
- <span data-ttu-id="e63d0-212">Logischer exklusiver OR-Operator `^`</span><span class="sxs-lookup"><span data-stu-id="e63d0-212">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="e63d0-213">Logischer OR-Operator `|`</span><span class="sxs-lookup"><span data-stu-id="e63d0-213">Logical OR operator `|`</span></span>
- <span data-ttu-id="e63d0-214">Bedingter logischer AND-Operator `&&`</span><span class="sxs-lookup"><span data-stu-id="e63d0-214">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="e63d0-215">Bedingter logischer OR-Operator `||`</span><span class="sxs-lookup"><span data-stu-id="e63d0-215">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="e63d0-216">Verwenden Sie Klammern `()`, wenn Sie die Reihenfolge der Auswertung ändern möchten, die durch Operatorrangfolge festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="e63d0-216">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Precedence)]

<span data-ttu-id="e63d0-217">Die vollständige Liste der nach Rangfolgenebene sortierten C#-Operatoren finden Sie unter [C#-Operatoren](index.md).</span><span class="sxs-lookup"><span data-stu-id="e63d0-217">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="e63d0-218">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="e63d0-218">Operator overloadability</span></span>

<span data-ttu-id="e63d0-219">Ein benutzerdefinierter Typ kann die Operatoren `!`, `&`, `|` und `^` [überladen](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="e63d0-219">A user-defined type can [overload](operator-overloading.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="e63d0-220">Wenn ein binärer Operator überladen ist, wird der zugehörige Verbundzuweisungsoperator implizit auch überladen.</span><span class="sxs-lookup"><span data-stu-id="e63d0-220">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="e63d0-221">Ein benutzerdefinierter Typ kann einen Verbundzuweisungsoperator nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="e63d0-221">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="e63d0-222">Ein benutzerdefinierter Typ kann die bedingten logischen Operatoren `&&` und `||` nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="e63d0-222">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="e63d0-223">Wenn jedoch ein benutzerdefinierter Typ die [„true“ und „false“-Operatoren](true-false-operators.md) und den `&`- oder `|`-Operator in einer bestimmten Weise überlädt, kann die `&&`- bzw. `||`-Operation für die Operanden dieses Typs ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="e63d0-223">However, if a user-defined type overloads the [true and false operators](true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="e63d0-224">Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte bedingte logische Operatoren](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="e63d0-224">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e63d0-225">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="e63d0-225">C# language specification</span></span>

<span data-ttu-id="e63d0-226">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="e63d0-226">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="e63d0-227">Logischer Negationsoperator</span><span class="sxs-lookup"><span data-stu-id="e63d0-227">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="e63d0-228">Logical operators (Logische Operatoren)</span><span class="sxs-lookup"><span data-stu-id="e63d0-228">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="e63d0-229">Conditional logical operators (Bedingte logische Operatoren)</span><span class="sxs-lookup"><span data-stu-id="e63d0-229">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="e63d0-230">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="e63d0-230">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="e63d0-231">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e63d0-231">See also</span></span>

- [<span data-ttu-id="e63d0-232">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e63d0-232">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e63d0-233">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="e63d0-233">C# operators</span></span>](index.md)
- [<span data-ttu-id="e63d0-234">Bitweise und Schiebeoperatoren</span><span class="sxs-lookup"><span data-stu-id="e63d0-234">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
