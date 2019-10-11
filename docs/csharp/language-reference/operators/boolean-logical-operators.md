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
ms.openlocfilehash: cc25d4bfd444dc0acb30fc1c6e6c3c9918af537c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698682"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="81eda-103">Logische boolesche Operatoren (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="81eda-103">Boolean logical operators (C# reference)</span></span>

<span data-ttu-id="81eda-104">Die folgenden Operatoren führen logische Vorgänge mit den [bool](../keywords/bool.md)-Operanden durch:</span><span class="sxs-lookup"><span data-stu-id="81eda-104">The following operators perform logical operations with the [bool](../keywords/bool.md) operands:</span></span>

- <span data-ttu-id="81eda-105">Unärer [`!` (logische Negation)](#logical-negation-operator-) Operator.</span><span class="sxs-lookup"><span data-stu-id="81eda-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="81eda-106">Binäre [`&` (logisch AND)](#logical-and-operator-), [`|` (logisch OR)](#logical-or-operator-) und [`^` (logisch exklusiv OR)](#logical-exclusive-or-operator-) Operatoren.</span><span class="sxs-lookup"><span data-stu-id="81eda-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="81eda-107">Diese Operatoren werten immer beide Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="81eda-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="81eda-108">Binäre [ `&&` (bedingt logisch AND)](#conditional-logical-and-operator-) und [ `||` (bedingt logisch OR)](#conditional-logical-or-operator-) Operatoren.</span><span class="sxs-lookup"><span data-stu-id="81eda-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="81eda-109">Diese Operatoren werten den rechten Operanden nur dann aus, wenn es notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="81eda-109">Those operators evaluate the right-hand operand only if it's necessary.</span></span>

<span data-ttu-id="81eda-110">Für die Operanden der [integralen](../builtin-types/integral-numeric-types.md) Typen führen die Operatoren `&`, `|` und `^` bitweise logische Operationen durch.</span><span class="sxs-lookup"><span data-stu-id="81eda-110">For the operands of the [integral](../builtin-types/integral-numeric-types.md) types, the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="81eda-111">Weitere Informationen finden Sie unter [Bitweise und Schiebeoperatoren](bitwise-and-shift-operators.md).</span><span class="sxs-lookup"><span data-stu-id="81eda-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="81eda-112">Logischer Negationsoperator: !</span><span class="sxs-lookup"><span data-stu-id="81eda-112">Logical negation operator !</span></span>

<span data-ttu-id="81eda-113">Der `!`-Operator berechnet die logische Negation des Operanden.</span><span class="sxs-lookup"><span data-stu-id="81eda-113">The `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="81eda-114">Das heißt., er erzeugt `true`, wenn der Operand als `false` ausgewertet wird, und `false`, wenn der Operand als `true` ausgewertet wird:</span><span class="sxs-lookup"><span data-stu-id="81eda-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Negation)]

<span data-ttu-id="81eda-115">Ab C# 8.0 ist der unäre Postfixoperator `!` ein NULL-toleranter Operator.</span><span class="sxs-lookup"><span data-stu-id="81eda-115">Starting with C# 8.0, the unary postfix `!` operator is a null-forgiving operator.</span></span> <span data-ttu-id="81eda-116">In einem Kontext, in dem NULL-Werte für Anmerkungen zulässig sind, geben Sie mit diesem Operator an, dass der Ausdruck `x` eines Referenztyps, der NULL-Werte zulässt, nicht NULL ist: `x!`.</span><span class="sxs-lookup"><span data-stu-id="81eda-116">In an enabled nullable annotation context, you use it to declare that expression `x` of a nullable reference type isn't null: `x!`.</span></span> <span data-ttu-id="81eda-117">Weitere Informationen finden Sie unter [Nullable-Verweistypen](../../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="81eda-117">For more information, see [Nullable reference types](../../nullable-references.md).</span></span>

## <a name="logical-and-operator-"></a> <span data-ttu-id="81eda-118">Logischer AND-Operator &amp;</span><span class="sxs-lookup"><span data-stu-id="81eda-118">Logical AND operator &amp;</span></span>

<span data-ttu-id="81eda-119">Der `&`-Operator berechnet die logische AND-Operation des Operanden.</span><span class="sxs-lookup"><span data-stu-id="81eda-119">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="81eda-120">Das Ergebnis von `x & y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="81eda-120">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="81eda-121">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="81eda-121">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="81eda-122">Der `&`-Operator wertet beide Operanden aus, selbst wenn der linke Operand als `false` ausgewertet wird, sodass das Ergebnis unabhängig vom Wert des rechten Operanden `false` sein muss.</span><span class="sxs-lookup"><span data-stu-id="81eda-122">The `&` operator evaluates both operands even if the left-hand operand evaluates to `false`, so that the result must be `false` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="81eda-123">Im folgenden Beispiel ist der rechte Operand des `&`-Operators ein Methodenaufruf, der unabhängig vom Wert des linken Operanden ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="81eda-123">In the following example, the right-hand operand of the `&` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#And)]

<span data-ttu-id="81eda-124">Der [bedingte logische AND-Operator](#conditional-logical-and-operator-) `&&` berechnet auch die logische AND-Operation der Operanden, wertet den rechten Operanden aber nicht aus, wenn der linke Operand `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="81eda-124">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `false`.</span></span>

<span data-ttu-id="81eda-125">Für die Operanden der integralen Typen berechnet der Operator `&` [bitweises logisches UND](bitwise-and-shift-operators.md#logical-and-operator-) für seine Operanden.</span><span class="sxs-lookup"><span data-stu-id="81eda-125">For the operands of the integral types, the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="81eda-126">Der unäre `&`-Operator ist der [address-of-Operator](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="81eda-126">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="81eda-127">Logischer exklusiver OR-Operator: ^</span><span class="sxs-lookup"><span data-stu-id="81eda-127">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="81eda-128">Die `^`-Operator berechnet das logische exklusive OR, auch als logischer XOR bezeichnet, seiner Operanden.</span><span class="sxs-lookup"><span data-stu-id="81eda-128">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="81eda-129">Das Ergebnis von `x ^ y` ist `true`, wenn `x` `true` ergibt und `y` `false`ergibt, oder `x` `false` ergibt und `y` `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="81eda-129">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="81eda-130">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="81eda-130">Otherwise, the result is `false`.</span></span> <span data-ttu-id="81eda-131">Das heißt, für die `bool`-Operanden berechnet der `^`-Operator das gleiche Ergebnis wie der [Ungleichheitsoperator](equality-operators.md#inequality-operator-) `!=`.</span><span class="sxs-lookup"><span data-stu-id="81eda-131">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Xor)]

<span data-ttu-id="81eda-132">Für die Operanden der integralen Typen berechnet der Operator `^` [bitweises logisches exklusives ODER](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) für seine Operanden.</span><span class="sxs-lookup"><span data-stu-id="81eda-132">For the operands of the integral types, the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="81eda-133">Logischer OR-Operator: |</span><span class="sxs-lookup"><span data-stu-id="81eda-133">Logical OR operator |</span></span>

<span data-ttu-id="81eda-134">Der `|`-Operator berechnet die logische OR-Operation des Operanden.</span><span class="sxs-lookup"><span data-stu-id="81eda-134">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="81eda-135">Das Ergebnis von `x | y` ist `true`, wenn entweder `x` oder `y` `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="81eda-135">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="81eda-136">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="81eda-136">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="81eda-137">Der `|`-Operator wertet beide Operanden aus, selbst wenn der linke Operand als `true` ausgewertet wird, sodass das Ergebnis unabhängig vom Wert des rechten Operanden `true` sein muss.</span><span class="sxs-lookup"><span data-stu-id="81eda-137">The `|` operator evaluates both operands even if the left-hand operand evaluates to `true`, so that the result must be `true` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="81eda-138">Im folgenden Beispiel ist der rechte Operand des `|`-Operators ein Methodenaufruf, der unabhängig vom Wert des linken Operanden ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="81eda-138">In the following example, the right-hand operand of the `|` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Or)]

<span data-ttu-id="81eda-139">Der [bedingte logische OR-Operator](#conditional-logical-or-operator-) `||` berechnet auch die logische OR-Operation der Operanden, wertet den rechten Operanden aber nicht aus, wenn der linke Operand `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="81eda-139">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `true`.</span></span>

<span data-ttu-id="81eda-140">Für die Operanden der integralen Typen berechnet der Operator `|` [bitweises logisches ODER](bitwise-and-shift-operators.md#logical-or-operator-) für seine Operanden.</span><span class="sxs-lookup"><span data-stu-id="81eda-140">For the operands of the integral types, the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-"></a> <span data-ttu-id="81eda-141">Bedingter logischer AND-Operator &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="81eda-141">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="81eda-142">Der bedingte logische AND-Operator `&&`, auch bekannt als der "kurzschließender" logischer AND-Operator bezeichnet, berechnet die logische AND-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="81eda-142">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="81eda-143">Das Ergebnis von `x && y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="81eda-143">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="81eda-144">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="81eda-144">Otherwise, the result is `false`.</span></span> <span data-ttu-id="81eda-145">Wenn `x` als `false` ausgewertet wird, wird `y` nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="81eda-145">If `x` evaluates to `false`, `y` is not evaluated.</span></span>

<span data-ttu-id="81eda-146">Im folgenden Beispiel ist der rechte Operand des `&&`-Operators ein Methodenaufruf, der nicht ausgeführt wird, wenn der linke Operand `false` ergibt:</span><span class="sxs-lookup"><span data-stu-id="81eda-146">In the following example, the right-hand operand of the `&&` operator is a method call, which isn't performed if the left-hand operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="81eda-147">Der [logische AND-Operator](#logical-and-operator-) `&` berechnet auch die logische AND-Operation der Operanden, es werden jedoch immer beide Operanden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="81eda-147">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="81eda-148">Bedingter logischer OR-Operator ||</span><span class="sxs-lookup"><span data-stu-id="81eda-148">Conditional logical OR operator ||</span></span>

<span data-ttu-id="81eda-149">Der bedingte logische OR-Operator `||`, auch bekannt als der "kurzschließender" logischer OR-Operator bezeichnet, berechnet die logische OR-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="81eda-149">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="81eda-150">Das Ergebnis von `x || y` ist `true`, wenn entweder `x` oder `y` `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="81eda-150">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="81eda-151">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="81eda-151">Otherwise, the result is `false`.</span></span> <span data-ttu-id="81eda-152">Wenn `x` als `true` ausgewertet wird, wird `y` nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="81eda-152">If `x` evaluates to `true`, `y` is not evaluated.</span></span>

<span data-ttu-id="81eda-153">Im folgenden Beispiel ist der rechte Operand des `||`-Operators ein Methodenaufruf, der nicht ausgeführt wird, wenn der linke Operand `true` ergibt:</span><span class="sxs-lookup"><span data-stu-id="81eda-153">In the following example, the right-hand operand of the `||` operator is a method call, which isn't performed if the left-hand operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="81eda-154">Der [logische OR-Operator](#logical-or-operator-) `|` berechnet auch die logische OR-Operation der Operanden, es werden jedoch immer beide Operanden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="81eda-154">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="81eda-155">Logische boolesche Operatoren, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="81eda-155">Nullable Boolean logical operators</span></span>

<span data-ttu-id="81eda-156">Für die `bool?`-Operanden unterstützen die `&`- und `|`-Operatoren die dreiwertige Logik.</span><span class="sxs-lookup"><span data-stu-id="81eda-156">For the `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="81eda-157">Die Semantik dieser Operatoren ist in der folgenden Tabelle definiert:</span><span class="sxs-lookup"><span data-stu-id="81eda-157">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="81eda-158">x</span><span class="sxs-lookup"><span data-stu-id="81eda-158">x</span></span>|<span data-ttu-id="81eda-159">y</span><span class="sxs-lookup"><span data-stu-id="81eda-159">y</span></span>|<span data-ttu-id="81eda-160">x&y</span><span class="sxs-lookup"><span data-stu-id="81eda-160">x&y</span></span>|<span data-ttu-id="81eda-161">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="81eda-161">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="81eda-162">true</span><span class="sxs-lookup"><span data-stu-id="81eda-162">true</span></span>|<span data-ttu-id="81eda-163">true</span><span class="sxs-lookup"><span data-stu-id="81eda-163">true</span></span>|<span data-ttu-id="81eda-164">true</span><span class="sxs-lookup"><span data-stu-id="81eda-164">true</span></span>|<span data-ttu-id="81eda-165">true</span><span class="sxs-lookup"><span data-stu-id="81eda-165">true</span></span>|  
|<span data-ttu-id="81eda-166">true</span><span class="sxs-lookup"><span data-stu-id="81eda-166">true</span></span>|<span data-ttu-id="81eda-167">false</span><span class="sxs-lookup"><span data-stu-id="81eda-167">false</span></span>|<span data-ttu-id="81eda-168">false</span><span class="sxs-lookup"><span data-stu-id="81eda-168">false</span></span>|<span data-ttu-id="81eda-169">true</span><span class="sxs-lookup"><span data-stu-id="81eda-169">true</span></span>|  
|<span data-ttu-id="81eda-170">true</span><span class="sxs-lookup"><span data-stu-id="81eda-170">true</span></span>|<span data-ttu-id="81eda-171">null</span><span class="sxs-lookup"><span data-stu-id="81eda-171">null</span></span>|<span data-ttu-id="81eda-172">null</span><span class="sxs-lookup"><span data-stu-id="81eda-172">null</span></span>|<span data-ttu-id="81eda-173">true</span><span class="sxs-lookup"><span data-stu-id="81eda-173">true</span></span>|  
|<span data-ttu-id="81eda-174">false</span><span class="sxs-lookup"><span data-stu-id="81eda-174">false</span></span>|<span data-ttu-id="81eda-175">true</span><span class="sxs-lookup"><span data-stu-id="81eda-175">true</span></span>|<span data-ttu-id="81eda-176">false</span><span class="sxs-lookup"><span data-stu-id="81eda-176">false</span></span>|<span data-ttu-id="81eda-177">true</span><span class="sxs-lookup"><span data-stu-id="81eda-177">true</span></span>|  
|<span data-ttu-id="81eda-178">false</span><span class="sxs-lookup"><span data-stu-id="81eda-178">false</span></span>|<span data-ttu-id="81eda-179">false</span><span class="sxs-lookup"><span data-stu-id="81eda-179">false</span></span>|<span data-ttu-id="81eda-180">false</span><span class="sxs-lookup"><span data-stu-id="81eda-180">false</span></span>|<span data-ttu-id="81eda-181">false</span><span class="sxs-lookup"><span data-stu-id="81eda-181">false</span></span>|  
|<span data-ttu-id="81eda-182">false</span><span class="sxs-lookup"><span data-stu-id="81eda-182">false</span></span>|<span data-ttu-id="81eda-183">null</span><span class="sxs-lookup"><span data-stu-id="81eda-183">null</span></span>|<span data-ttu-id="81eda-184">false</span><span class="sxs-lookup"><span data-stu-id="81eda-184">false</span></span>|<span data-ttu-id="81eda-185">NULL</span><span class="sxs-lookup"><span data-stu-id="81eda-185">null</span></span>|  
|<span data-ttu-id="81eda-186">null</span><span class="sxs-lookup"><span data-stu-id="81eda-186">null</span></span>|<span data-ttu-id="81eda-187">true</span><span class="sxs-lookup"><span data-stu-id="81eda-187">true</span></span>|<span data-ttu-id="81eda-188">null</span><span class="sxs-lookup"><span data-stu-id="81eda-188">null</span></span>|<span data-ttu-id="81eda-189">true</span><span class="sxs-lookup"><span data-stu-id="81eda-189">true</span></span>|  
|<span data-ttu-id="81eda-190">null</span><span class="sxs-lookup"><span data-stu-id="81eda-190">null</span></span>|<span data-ttu-id="81eda-191">false</span><span class="sxs-lookup"><span data-stu-id="81eda-191">false</span></span>|<span data-ttu-id="81eda-192">false</span><span class="sxs-lookup"><span data-stu-id="81eda-192">false</span></span>|<span data-ttu-id="81eda-193">NULL</span><span class="sxs-lookup"><span data-stu-id="81eda-193">null</span></span>|  
|<span data-ttu-id="81eda-194">null</span><span class="sxs-lookup"><span data-stu-id="81eda-194">null</span></span>|<span data-ttu-id="81eda-195">null</span><span class="sxs-lookup"><span data-stu-id="81eda-195">null</span></span>|<span data-ttu-id="81eda-196">null</span><span class="sxs-lookup"><span data-stu-id="81eda-196">null</span></span>|<span data-ttu-id="81eda-197">null</span><span class="sxs-lookup"><span data-stu-id="81eda-197">null</span></span>|  

<span data-ttu-id="81eda-198">Das Verhalten dieser Operatoren unterscheidet sich vom typischen Operatorverhalten bei Typen, die NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="81eda-198">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="81eda-199">In der Regel kann ein Operator, der für Operanden eines Werttyps definiert ist, auch mit Operanden des entsprechenden Nullable-Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="81eda-199">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="81eda-200">Ein solcher Operator erzeugt `null`, wenn einer seiner Operanden `null` ist.</span><span class="sxs-lookup"><span data-stu-id="81eda-200">Such an operator produces `null` if any of its operands is `null`.</span></span> <span data-ttu-id="81eda-201">Die `&`- und `|`-Operatoren können jedoch Nicht-NULL-Werte erzeugen, auch wenn einer der Operanden `null` ist.</span><span class="sxs-lookup"><span data-stu-id="81eda-201">However, the `&` and `|` operators can produce non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="81eda-202">Weitere Informationen zum Operatorverhalten bei Typen, die NULL-Werte zulassen, finden Sie im Abschnitt [Operatoren](../../programming-guide/nullable-types/using-nullable-types.md#operators) des Artikels [Verwenden von Nullable-Werttypen](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="81eda-202">For more information about the operator behavior with nullable value types, see the [Operators](../../programming-guide/nullable-types/using-nullable-types.md#operators) section of the [Using nullable value types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="81eda-203">Sie können auch die `!`- und `^`- Operatoren mit den `bool?`-Operanden verwenden, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="81eda-203">You can also use the `!` and `^` operators with the `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="81eda-204">Die bedingten logischen Operatoren `&&` und `||` unterstützen nicht die `bool?`-Operanden.</span><span class="sxs-lookup"><span data-stu-id="81eda-204">The conditional logical operators `&&` and `||` don't support the `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="81eda-205">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="81eda-205">Compound assignment</span></span>

<span data-ttu-id="81eda-206">Bei einem binären Operator `op` entspricht ein Verbundzuweisungsausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="81eda-206">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="81eda-207">entspricht</span><span class="sxs-lookup"><span data-stu-id="81eda-207">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="81eda-208">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="81eda-208">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="81eda-209">Die `&`-, `|`- und `^`-Operatoren unterstützen die Verbundzuweisung, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="81eda-209">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="81eda-210">Die bedingten logischen Operatoren `&&` und `||` unterstützen nicht die Verbundzuweisung.</span><span class="sxs-lookup"><span data-stu-id="81eda-210">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="81eda-211">Operatorrangfolge</span><span class="sxs-lookup"><span data-stu-id="81eda-211">Operator precedence</span></span>

<span data-ttu-id="81eda-212">In der folgenden Liste sind die logischen Operatoren beginnend mit dem höchsten Rangfolgenoperator absteigend sortiert:</span><span class="sxs-lookup"><span data-stu-id="81eda-212">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="81eda-213">Logischer Negationsoperator `!`</span><span class="sxs-lookup"><span data-stu-id="81eda-213">Logical negation operator `!`</span></span>
- <span data-ttu-id="81eda-214">Logischer AND-Operator `&`</span><span class="sxs-lookup"><span data-stu-id="81eda-214">Logical AND operator `&`</span></span>
- <span data-ttu-id="81eda-215">Logischer exklusiver OR-Operator `^`</span><span class="sxs-lookup"><span data-stu-id="81eda-215">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="81eda-216">Logischer OR-Operator `|`</span><span class="sxs-lookup"><span data-stu-id="81eda-216">Logical OR operator `|`</span></span>
- <span data-ttu-id="81eda-217">Bedingter logischer AND-Operator `&&`</span><span class="sxs-lookup"><span data-stu-id="81eda-217">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="81eda-218">Bedingter logischer OR-Operator `||`</span><span class="sxs-lookup"><span data-stu-id="81eda-218">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="81eda-219">Verwenden Sie Klammern `()`, wenn Sie die Reihenfolge der Auswertung ändern möchten, die durch Operatorrangfolge festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="81eda-219">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Precedence)]

<span data-ttu-id="81eda-220">Die vollständige Liste der nach Rangfolgenebene sortierten C#-Operatoren finden Sie unter [C#-Operatoren](index.md).</span><span class="sxs-lookup"><span data-stu-id="81eda-220">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="81eda-221">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="81eda-221">Operator overloadability</span></span>

<span data-ttu-id="81eda-222">Ein benutzerdefinierter Typ kann die Operatoren `!`, `&`, `|` und `^` [überladen](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="81eda-222">A user-defined type can [overload](operator-overloading.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="81eda-223">Wenn ein binärer Operator überladen ist, wird der zugehörige Verbundzuweisungsoperator implizit auch überladen.</span><span class="sxs-lookup"><span data-stu-id="81eda-223">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="81eda-224">Ein benutzerdefinierter Typ kann einen Verbundzuweisungsoperator nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="81eda-224">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="81eda-225">Ein benutzerdefinierter Typ kann die bedingten logischen Operatoren `&&` und `||` nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="81eda-225">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="81eda-226">Wenn jedoch ein benutzerdefinierter Typ die [„true“ und „false“-Operatoren](true-false-operators.md) und den `&`- oder `|`-Operator in einer bestimmten Weise überlädt, kann die `&&`- bzw. `||`-Operation für die Operanden dieses Typs ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="81eda-226">However, if a user-defined type overloads the [true and false operators](true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="81eda-227">Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte bedingte logische Operatoren](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="81eda-227">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="81eda-228">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="81eda-228">C# language specification</span></span>

<span data-ttu-id="81eda-229">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="81eda-229">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="81eda-230">Logischer Negationsoperator</span><span class="sxs-lookup"><span data-stu-id="81eda-230">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="81eda-231">Logical operators (Logische Operatoren)</span><span class="sxs-lookup"><span data-stu-id="81eda-231">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="81eda-232">Conditional logical operators (Bedingte logische Operatoren)</span><span class="sxs-lookup"><span data-stu-id="81eda-232">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="81eda-233">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="81eda-233">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="81eda-234">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81eda-234">See also</span></span>

- [<span data-ttu-id="81eda-235">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="81eda-235">C# reference</span></span>](../index.md)
- [<span data-ttu-id="81eda-236">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="81eda-236">C# operators</span></span>](index.md)
- [<span data-ttu-id="81eda-237">Bitweise und Schiebeoperatoren</span><span class="sxs-lookup"><span data-stu-id="81eda-237">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
