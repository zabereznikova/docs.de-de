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
ms.openlocfilehash: 5f85b88236c2e643f97453c64173a3f4f7159a35
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795000"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="f04a5-103">Logische boolesche Operatoren (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f04a5-103">Boolean logical operators (C# reference)</span></span>

<span data-ttu-id="f04a5-104">Die folgenden Operatoren führen logische Vorgänge mit [bool](../builtin-types/bool.md)-Operanden durch:</span><span class="sxs-lookup"><span data-stu-id="f04a5-104">The following operators perform logical operations with [bool](../builtin-types/bool.md) operands:</span></span>

- <span data-ttu-id="f04a5-105">Unärer [`!` (logische Negation)](#logical-negation-operator-) Operator.</span><span class="sxs-lookup"><span data-stu-id="f04a5-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="f04a5-106">Binäre [`&` (logisch AND)](#logical-and-operator-), [`|` (logisch OR)](#logical-or-operator-) und [`^` (logisch exklusiv OR)](#logical-exclusive-or-operator-) Operatoren.</span><span class="sxs-lookup"><span data-stu-id="f04a5-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="f04a5-107">Diese Operatoren werten immer beide Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="f04a5-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="f04a5-108">Binäre [`&&` (bedingt logisch AND)](#conditional-logical-and-operator-) und [`||` (bedingt logisch OR)](#conditional-logical-or-operator-) Operatoren.</span><span class="sxs-lookup"><span data-stu-id="f04a5-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="f04a5-109">Diese Operatoren werten den rechten Operanden nur dann aus, wenn es notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="f04a5-109">Those operators evaluate the right-hand operand only if it's necessary.</span></span>

<span data-ttu-id="f04a5-110">Für Operanden der [integralen numerischen Typen](../builtin-types/integral-numeric-types.md) führen die Operatoren `&`, `|` und `^` bitweise logische Operationen durch.</span><span class="sxs-lookup"><span data-stu-id="f04a5-110">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="f04a5-111">Weitere Informationen finden Sie unter [Bitweise und Schiebeoperatoren](bitwise-and-shift-operators.md).</span><span class="sxs-lookup"><span data-stu-id="f04a5-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="f04a5-112">Logischer Negationsoperator: !</span><span class="sxs-lookup"><span data-stu-id="f04a5-112">Logical negation operator !</span></span>

<span data-ttu-id="f04a5-113">Der unäre Präfix-Operator `!` berechnet die logische Negation seines Operanden.</span><span class="sxs-lookup"><span data-stu-id="f04a5-113">The unary prefix `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="f04a5-114">Das heißt., er erzeugt `true`, wenn der Operand als `false` ausgewertet wird, und `false`, wenn der Operand als `true` ausgewertet wird:</span><span class="sxs-lookup"><span data-stu-id="f04a5-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](snippets/BooleanLogicalOperators.cs#Negation)]

<span data-ttu-id="f04a5-115">Ab C# 8.0 ist der unäre Postfix-Operator `!` der [NULL-tolerante Operator](null-forgiving.md).</span><span class="sxs-lookup"><span data-stu-id="f04a5-115">Beginning with C# 8.0, the unary postfix `!` operator is the [null-forgiving operator](null-forgiving.md).</span></span>

## <a name="logical-and-operator-amp"></a><a name="logical-and-operator-"></a> <span data-ttu-id="f04a5-116">Logischer AND-Operator &amp;</span><span class="sxs-lookup"><span data-stu-id="f04a5-116">Logical AND operator &amp;</span></span>

<span data-ttu-id="f04a5-117">Der `&`-Operator berechnet die logische AND-Operation des Operanden.</span><span class="sxs-lookup"><span data-stu-id="f04a5-117">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="f04a5-118">Das Ergebnis von `x & y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="f04a5-118">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="f04a5-119">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="f04a5-119">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="f04a5-120">Der `&`-Operator wertet beide Operanden aus, selbst wenn der linke Operand als `false` ausgewertet wird, sodass das Ergebnis des Vorgangs unabhängig vom Wert des rechten Operanden `false` ist.</span><span class="sxs-lookup"><span data-stu-id="f04a5-120">The `&` operator evaluates both operands even if the left-hand operand evaluates to `false`, so that the operation result is `false` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="f04a5-121">Im folgenden Beispiel ist der rechte Operand des `&`-Operators ein Methodenaufruf, der unabhängig vom Wert des linken Operanden ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="f04a5-121">In the following example, the right-hand operand of the `&` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical AND](snippets/BooleanLogicalOperators.cs#And)]

<span data-ttu-id="f04a5-122">Der [bedingte logische AND-Operator](#conditional-logical-and-operator-) `&&` berechnet auch die logische AND-Operation der Operanden, wertet den rechten Operanden aber nicht aus, wenn der linke Operand `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="f04a5-122">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `false`.</span></span>

<span data-ttu-id="f04a5-123">Für Operanden der [integralen numerischen Typen](../builtin-types/integral-numeric-types.md) berechnet der Operator `&`[bitweises logisches UND](bitwise-and-shift-operators.md#logical-and-operator-) für seine Operanden.</span><span class="sxs-lookup"><span data-stu-id="f04a5-123">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="f04a5-124">Der unäre `&`-Operator ist der [address-of-Operator](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="f04a5-124">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="f04a5-125">Logischer exklusiver OR-Operator: ^</span><span class="sxs-lookup"><span data-stu-id="f04a5-125">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="f04a5-126">Die `^`-Operator berechnet das logische exklusive OR, auch als logischer XOR bezeichnet, seiner Operanden.</span><span class="sxs-lookup"><span data-stu-id="f04a5-126">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="f04a5-127">Das Ergebnis von `x ^ y` ist `true`, wenn `x``true` ergibt und `y``false`ergibt, oder `x``false` ergibt und `y``true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="f04a5-127">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="f04a5-128">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="f04a5-128">Otherwise, the result is `false`.</span></span> <span data-ttu-id="f04a5-129">Das heißt, für die `bool`-Operanden berechnet der `^`-Operator das gleiche Ergebnis wie der [Ungleichheitsoperator](equality-operators.md#inequality-operator-) `!=`.</span><span class="sxs-lookup"><span data-stu-id="f04a5-129">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](snippets/BooleanLogicalOperators.cs#Xor)]

<span data-ttu-id="f04a5-130">Für Operanden der [integralen numerischen Typen](../builtin-types/integral-numeric-types.md) berechnet der Operator `^`[bitweises logisches exklusives ODER](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) für seine Operanden.</span><span class="sxs-lookup"><span data-stu-id="f04a5-130">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="f04a5-131">Logischer OR-Operator: |</span><span class="sxs-lookup"><span data-stu-id="f04a5-131">Logical OR operator |</span></span>

<span data-ttu-id="f04a5-132">Der `|`-Operator berechnet die logische OR-Operation des Operanden.</span><span class="sxs-lookup"><span data-stu-id="f04a5-132">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="f04a5-133">Das Ergebnis von `x | y` ist `true`, wenn entweder `x` oder `y``true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="f04a5-133">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="f04a5-134">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="f04a5-134">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="f04a5-135">Der `|`-Operator wertet beide Operanden aus, selbst wenn der linke Operand als `true` ausgewertet wird, sodass das Ergebnis des Vorgangs unabhängig vom Wert des rechten Operanden `true` ist.</span><span class="sxs-lookup"><span data-stu-id="f04a5-135">The `|` operator evaluates both operands even if the left-hand operand evaluates to `true`, so that the operation result is `true` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="f04a5-136">Im folgenden Beispiel ist der rechte Operand des `|`-Operators ein Methodenaufruf, der unabhängig vom Wert des linken Operanden ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="f04a5-136">In the following example, the right-hand operand of the `|` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical OR](snippets/BooleanLogicalOperators.cs#Or)]

<span data-ttu-id="f04a5-137">Der [bedingte logische OR-Operator](#conditional-logical-or-operator-) `||` berechnet auch die logische OR-Operation der Operanden, wertet den rechten Operanden aber nicht aus, wenn der linke Operand `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="f04a5-137">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `true`.</span></span>

<span data-ttu-id="f04a5-138">Für Operanden der [integralen numerischen Typen](../builtin-types/integral-numeric-types.md) berechnet der Operator `|`[bitweises logisches ODER](bitwise-and-shift-operators.md#logical-or-operator-) für seine Operanden.</span><span class="sxs-lookup"><span data-stu-id="f04a5-138">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-ampamp"></a><a name="conditional-logical-and-operator-"></a> <span data-ttu-id="f04a5-139">Bedingter logischer AND-Operator &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="f04a5-139">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="f04a5-140">Der bedingte logische AND-Operator `&&`, auch bekannt als der "kurzschließender" logischer AND-Operator bezeichnet, berechnet die logische AND-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="f04a5-140">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="f04a5-141">Das Ergebnis von `x && y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="f04a5-141">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="f04a5-142">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="f04a5-142">Otherwise, the result is `false`.</span></span> <span data-ttu-id="f04a5-143">Wenn `x` als `false` ausgewertet wird, wird `y` nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="f04a5-143">If `x` evaluates to `false`, `y` is not evaluated.</span></span>

<span data-ttu-id="f04a5-144">Im folgenden Beispiel ist der rechte Operand des `&&`-Operators ein Methodenaufruf, der nicht ausgeführt wird, wenn der linke Operand `false` ergibt:</span><span class="sxs-lookup"><span data-stu-id="f04a5-144">In the following example, the right-hand operand of the `&&` operator is a method call, which isn't performed if the left-hand operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](snippets/BooleanLogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="f04a5-145">Der [logische AND-Operator](#logical-and-operator-) `&` berechnet auch die logische AND-Operation der Operanden, es werden jedoch immer beide Operanden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="f04a5-145">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="f04a5-146">Bedingter logischer OR-Operator ||</span><span class="sxs-lookup"><span data-stu-id="f04a5-146">Conditional logical OR operator ||</span></span>

<span data-ttu-id="f04a5-147">Der bedingte logische OR-Operator `||`, auch bekannt als der "kurzschließender" logischer OR-Operator bezeichnet, berechnet die logische OR-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="f04a5-147">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="f04a5-148">Das Ergebnis von `x || y` ist `true`, wenn entweder `x` oder `y``true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="f04a5-148">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="f04a5-149">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="f04a5-149">Otherwise, the result is `false`.</span></span> <span data-ttu-id="f04a5-150">Wenn `x` als `true` ausgewertet wird, wird `y` nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="f04a5-150">If `x` evaluates to `true`, `y` is not evaluated.</span></span>

<span data-ttu-id="f04a5-151">Im folgenden Beispiel ist der rechte Operand des `||`-Operators ein Methodenaufruf, der nicht ausgeführt wird, wenn der linke Operand `true` ergibt:</span><span class="sxs-lookup"><span data-stu-id="f04a5-151">In the following example, the right-hand operand of the `||` operator is a method call, which isn't performed if the left-hand operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](snippets/BooleanLogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="f04a5-152">Der [logische OR-Operator](#logical-or-operator-) `|` berechnet auch die logische OR-Operation der Operanden, es werden jedoch immer beide Operanden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="f04a5-152">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="f04a5-153">Logische boolesche Operatoren, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="f04a5-153">Nullable Boolean logical operators</span></span>

<span data-ttu-id="f04a5-154">Für `bool?`-Operanden unterstützen die `&`- und `|`-Operatoren dreiwertige Logik.</span><span class="sxs-lookup"><span data-stu-id="f04a5-154">For `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="f04a5-155">Die Semantik dieser Operatoren ist in der folgenden Tabelle definiert:</span><span class="sxs-lookup"><span data-stu-id="f04a5-155">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="f04a5-156">w</span><span class="sxs-lookup"><span data-stu-id="f04a5-156">x</span></span>|<span data-ttu-id="f04a5-157">y</span><span class="sxs-lookup"><span data-stu-id="f04a5-157">y</span></span>|<span data-ttu-id="f04a5-158">x&y</span><span class="sxs-lookup"><span data-stu-id="f04a5-158">x&y</span></span>|<span data-ttu-id="f04a5-159">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="f04a5-159">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="f04a5-160">true</span><span class="sxs-lookup"><span data-stu-id="f04a5-160">true</span></span>|<span data-ttu-id="f04a5-161">true</span><span class="sxs-lookup"><span data-stu-id="f04a5-161">true</span></span>|<span data-ttu-id="f04a5-162">true</span><span class="sxs-lookup"><span data-stu-id="f04a5-162">true</span></span>|<span data-ttu-id="f04a5-163">true</span><span class="sxs-lookup"><span data-stu-id="f04a5-163">true</span></span>|  
|<span data-ttu-id="f04a5-164">true</span><span class="sxs-lookup"><span data-stu-id="f04a5-164">true</span></span>|<span data-ttu-id="f04a5-165">False</span><span class="sxs-lookup"><span data-stu-id="f04a5-165">false</span></span>|<span data-ttu-id="f04a5-166">false</span><span class="sxs-lookup"><span data-stu-id="f04a5-166">false</span></span>|<span data-ttu-id="f04a5-167">true</span><span class="sxs-lookup"><span data-stu-id="f04a5-167">true</span></span>|  
|<span data-ttu-id="f04a5-168">true</span><span class="sxs-lookup"><span data-stu-id="f04a5-168">true</span></span>|<span data-ttu-id="f04a5-169">NULL</span><span class="sxs-lookup"><span data-stu-id="f04a5-169">null</span></span>|<span data-ttu-id="f04a5-170">NULL</span><span class="sxs-lookup"><span data-stu-id="f04a5-170">null</span></span>|<span data-ttu-id="f04a5-171">true</span><span class="sxs-lookup"><span data-stu-id="f04a5-171">true</span></span>|  
|<span data-ttu-id="f04a5-172">False</span><span class="sxs-lookup"><span data-stu-id="f04a5-172">false</span></span>|<span data-ttu-id="f04a5-173">true</span><span class="sxs-lookup"><span data-stu-id="f04a5-173">true</span></span>|<span data-ttu-id="f04a5-174">False</span><span class="sxs-lookup"><span data-stu-id="f04a5-174">false</span></span>|<span data-ttu-id="f04a5-175">true</span><span class="sxs-lookup"><span data-stu-id="f04a5-175">true</span></span>|  
|<span data-ttu-id="f04a5-176">False</span><span class="sxs-lookup"><span data-stu-id="f04a5-176">false</span></span>|<span data-ttu-id="f04a5-177">False</span><span class="sxs-lookup"><span data-stu-id="f04a5-177">false</span></span>|<span data-ttu-id="f04a5-178">False</span><span class="sxs-lookup"><span data-stu-id="f04a5-178">false</span></span>|<span data-ttu-id="f04a5-179">False</span><span class="sxs-lookup"><span data-stu-id="f04a5-179">false</span></span>|  
|<span data-ttu-id="f04a5-180">False</span><span class="sxs-lookup"><span data-stu-id="f04a5-180">false</span></span>|<span data-ttu-id="f04a5-181">NULL</span><span class="sxs-lookup"><span data-stu-id="f04a5-181">null</span></span>|<span data-ttu-id="f04a5-182">False</span><span class="sxs-lookup"><span data-stu-id="f04a5-182">false</span></span>|<span data-ttu-id="f04a5-183">NULL</span><span class="sxs-lookup"><span data-stu-id="f04a5-183">null</span></span>|  
|<span data-ttu-id="f04a5-184">NULL</span><span class="sxs-lookup"><span data-stu-id="f04a5-184">null</span></span>|<span data-ttu-id="f04a5-185">true</span><span class="sxs-lookup"><span data-stu-id="f04a5-185">true</span></span>|<span data-ttu-id="f04a5-186">NULL</span><span class="sxs-lookup"><span data-stu-id="f04a5-186">null</span></span>|<span data-ttu-id="f04a5-187">true</span><span class="sxs-lookup"><span data-stu-id="f04a5-187">true</span></span>|  
|<span data-ttu-id="f04a5-188">NULL</span><span class="sxs-lookup"><span data-stu-id="f04a5-188">null</span></span>|<span data-ttu-id="f04a5-189">False</span><span class="sxs-lookup"><span data-stu-id="f04a5-189">false</span></span>|<span data-ttu-id="f04a5-190">False</span><span class="sxs-lookup"><span data-stu-id="f04a5-190">false</span></span>|<span data-ttu-id="f04a5-191">NULL</span><span class="sxs-lookup"><span data-stu-id="f04a5-191">null</span></span>|  
|<span data-ttu-id="f04a5-192">NULL</span><span class="sxs-lookup"><span data-stu-id="f04a5-192">null</span></span>|<span data-ttu-id="f04a5-193">NULL</span><span class="sxs-lookup"><span data-stu-id="f04a5-193">null</span></span>|<span data-ttu-id="f04a5-194">NULL</span><span class="sxs-lookup"><span data-stu-id="f04a5-194">null</span></span>|<span data-ttu-id="f04a5-195">NULL</span><span class="sxs-lookup"><span data-stu-id="f04a5-195">null</span></span>|  

<span data-ttu-id="f04a5-196">Das Verhalten dieser Operatoren unterscheidet sich vom typischen Operatorverhalten bei Typen, die NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="f04a5-196">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="f04a5-197">In der Regel kann ein Operator, der für Operanden eines Werttyps definiert ist, auch mit Operanden des entsprechenden Nullable-Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f04a5-197">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="f04a5-198">Ein solcher Operator generiert `null`, wenn einer seiner Operanden in `null` ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="f04a5-198">Such an operator produces `null` if any of its operands evaluates to `null`.</span></span> <span data-ttu-id="f04a5-199">Die `&`- und `|`-Operatoren können jedoch Nicht-NULL-Werte erzeugen, auch wenn einer der Operanden in `null` ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="f04a5-199">However, the `&` and `|` operators can produce non-null even if one of the operands evaluates to `null`.</span></span> <span data-ttu-id="f04a5-200">Weitere Informationen zum Operatorverhalten bei Nullable-Werttypen finden Sie im Abschnitt [„Lifted“ Operatoren](../builtin-types/nullable-value-types.md#lifted-operators) des Artikels [Nullable-Werttypen](../builtin-types/nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="f04a5-200">For more information about the operator behavior with nullable value types, see the [Lifted operators](../builtin-types/nullable-value-types.md#lifted-operators) section of the [Nullable value types](../builtin-types/nullable-value-types.md) article.</span></span>

<span data-ttu-id="f04a5-201">Sie können auch die `!`- und `^`- Operatoren mit `bool?`-Operanden verwenden, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="f04a5-201">You can also use the `!` and `^` operators with `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](snippets/BooleanLogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="f04a5-202">Die bedingten logischen Operatoren `&&` und `||` unterstützen keine `bool?`-Operanden.</span><span class="sxs-lookup"><span data-stu-id="f04a5-202">The conditional logical operators `&&` and `||` don't support `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="f04a5-203">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="f04a5-203">Compound assignment</span></span>

<span data-ttu-id="f04a5-204">Bei einem binären Operator `op` entspricht ein Verbundzuweisungsausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="f04a5-204">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="f04a5-205">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="f04a5-205">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="f04a5-206">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="f04a5-206">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="f04a5-207">Die `&`-, `|`- und `^`-Operatoren unterstützen die Verbundzuweisung, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="f04a5-207">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](snippets/BooleanLogicalOperators.cs#CompoundAssignment)]

> [!NOTE]
> <span data-ttu-id="f04a5-208">Die bedingten logischen Operatoren `&&` und `||` unterstützen nicht die Verbundzuweisung.</span><span class="sxs-lookup"><span data-stu-id="f04a5-208">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="f04a5-209">Operatorrangfolge</span><span class="sxs-lookup"><span data-stu-id="f04a5-209">Operator precedence</span></span>

<span data-ttu-id="f04a5-210">In der folgenden Liste sind die logischen Operatoren beginnend mit dem höchsten Rangfolgenoperator absteigend sortiert:</span><span class="sxs-lookup"><span data-stu-id="f04a5-210">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="f04a5-211">Logischer Negationsoperator `!`</span><span class="sxs-lookup"><span data-stu-id="f04a5-211">Logical negation operator `!`</span></span>
- <span data-ttu-id="f04a5-212">Logischer AND-Operator `&`</span><span class="sxs-lookup"><span data-stu-id="f04a5-212">Logical AND operator `&`</span></span>
- <span data-ttu-id="f04a5-213">Logischer exklusiver OR-Operator `^`</span><span class="sxs-lookup"><span data-stu-id="f04a5-213">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="f04a5-214">Logischer OR-Operator `|`</span><span class="sxs-lookup"><span data-stu-id="f04a5-214">Logical OR operator `|`</span></span>
- <span data-ttu-id="f04a5-215">Bedingter logischer AND-Operator `&&`</span><span class="sxs-lookup"><span data-stu-id="f04a5-215">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="f04a5-216">Bedingter logischer OR-Operator `||`</span><span class="sxs-lookup"><span data-stu-id="f04a5-216">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="f04a5-217">Verwenden Sie Klammern `()`, wenn Sie die Reihenfolge der Auswertung ändern möchten, die durch Operatorrangfolge festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="f04a5-217">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](snippets/BooleanLogicalOperators.cs#Precedence)]

<span data-ttu-id="f04a5-218">Die vollständige Liste der nach Rangfolgenebene sortierten C#-Operatoren finden Sie im Abschnitt [Operatorrangfolge](index.md#operator-precedence) im Artikel [C#-Operatoren](index.md).</span><span class="sxs-lookup"><span data-stu-id="f04a5-218">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="f04a5-219">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="f04a5-219">Operator overloadability</span></span>

<span data-ttu-id="f04a5-220">Ein benutzerdefinierter Typ kann die Operatoren `!`, `&`, `|` und `^`[überladen](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="f04a5-220">A user-defined type can [overload](operator-overloading.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="f04a5-221">Wenn ein binärer Operator überladen ist, wird der zugehörige Verbundzuweisungsoperator implizit auch überladen.</span><span class="sxs-lookup"><span data-stu-id="f04a5-221">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="f04a5-222">Ein benutzerdefinierter Typ kann einen Verbundzuweisungsoperator nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="f04a5-222">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="f04a5-223">Ein benutzerdefinierter Typ kann die bedingten logischen Operatoren `&&` und `||` nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="f04a5-223">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="f04a5-224">Wenn jedoch ein benutzerdefinierter Typ die [„true“ und „false“-Operatoren](true-false-operators.md) und den `&`- oder `|`-Operator in einer bestimmten Weise überlädt, kann die `&&`- bzw. `||`-Operation für die Operanden dieses Typs ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="f04a5-224">However, if a user-defined type overloads the [true and false operators](true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="f04a5-225">Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte bedingte logische Operatoren](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="f04a5-225">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f04a5-226">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="f04a5-226">C# language specification</span></span>

<span data-ttu-id="f04a5-227">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="f04a5-227">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="f04a5-228">Logischer Negationsoperator</span><span class="sxs-lookup"><span data-stu-id="f04a5-228">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="f04a5-229">Logical operators (Logische Operatoren)</span><span class="sxs-lookup"><span data-stu-id="f04a5-229">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="f04a5-230">Conditional logical operators (Bedingte logische Operatoren)</span><span class="sxs-lookup"><span data-stu-id="f04a5-230">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="f04a5-231">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="f04a5-231">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="f04a5-232">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f04a5-232">See also</span></span>

- [<span data-ttu-id="f04a5-233">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f04a5-233">C# reference</span></span>](../index.md)
- [<span data-ttu-id="f04a5-234">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="f04a5-234">C# operators</span></span>](index.md)
- [<span data-ttu-id="f04a5-235">Bitweise und Schiebeoperatoren</span><span class="sxs-lookup"><span data-stu-id="f04a5-235">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
