---
title: 'Logische boolesche Operatoren: C#-Referenz'
description: Erfahren Sie mehr über C#-Operatoren, die logische Negation, Konjunktion (AND), inklusive und exklusive Disjunktion (OR) mit booleschen Operanden durchführen.
ms.date: 06/29/2020
author: pkulikov
f1_keywords:
- '!_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
- '&&_CSharpKeyword'
- '||_CSharpKeyword'
- '|=_CSharpKeyword'
- ^=_CSharpKeyword
- '&=_CSharpKeyword'
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
ms.openlocfilehash: 00b1523029ed6562fda6947415029cd3b7a9b405
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916893"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="049bc-103">Logische boolesche Operatoren (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="049bc-103">Boolean logical operators (C# reference)</span></span>

<span data-ttu-id="049bc-104">Die folgenden Operatoren führen logische Vorgänge mit [bool](../builtin-types/bool.md)-Operanden durch:</span><span class="sxs-lookup"><span data-stu-id="049bc-104">The following operators perform logical operations with [bool](../builtin-types/bool.md) operands:</span></span>

- <span data-ttu-id="049bc-105">Unärer [`!` (logische Negation)](#logical-negation-operator-) Operator.</span><span class="sxs-lookup"><span data-stu-id="049bc-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="049bc-106">Binäre [`&` (logisch AND)](#logical-and-operator-), [`|` (logisch OR)](#logical-or-operator-) und [`^` (logisch exklusiv OR)](#logical-exclusive-or-operator-) Operatoren.</span><span class="sxs-lookup"><span data-stu-id="049bc-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="049bc-107">Diese Operatoren werten immer beide Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="049bc-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="049bc-108">Binäre [`&&` (bedingt logisch AND)](#conditional-logical-and-operator-) und [`||` (bedingt logisch OR)](#conditional-logical-or-operator-) Operatoren.</span><span class="sxs-lookup"><span data-stu-id="049bc-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="049bc-109">Diese Operatoren werten den rechten Operanden nur dann aus, wenn es notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="049bc-109">Those operators evaluate the right-hand operand only if it's necessary.</span></span>

<span data-ttu-id="049bc-110">Für Operanden der [integralen numerischen Typen](../builtin-types/integral-numeric-types.md) führen die Operatoren `&`, `|` und `^` bitweise logische Operationen durch.</span><span class="sxs-lookup"><span data-stu-id="049bc-110">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="049bc-111">Weitere Informationen finden Sie unter [Bitweise und Schiebeoperatoren](bitwise-and-shift-operators.md).</span><span class="sxs-lookup"><span data-stu-id="049bc-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="049bc-112">Logischer Negationsoperator: !</span><span class="sxs-lookup"><span data-stu-id="049bc-112">Logical negation operator !</span></span>

<span data-ttu-id="049bc-113">Der unäre Präfix-Operator `!` berechnet die logische Negation seines Operanden.</span><span class="sxs-lookup"><span data-stu-id="049bc-113">The unary prefix `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="049bc-114">Das heißt., er erzeugt `true`, wenn der Operand als `false` ausgewertet wird, und `false`, wenn der Operand als `true` ausgewertet wird:</span><span class="sxs-lookup"><span data-stu-id="049bc-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](snippets/shared/BooleanLogicalOperators.cs#Negation)]

<span data-ttu-id="049bc-115">Ab C# 8.0 ist der unäre Postfix-Operator `!` der [NULL-tolerante Operator](null-forgiving.md).</span><span class="sxs-lookup"><span data-stu-id="049bc-115">Beginning with C# 8.0, the unary postfix `!` operator is the [null-forgiving operator](null-forgiving.md).</span></span>

## <a name="logical-and-operator-amp"></a><a name="logical-and-operator-"></a> <span data-ttu-id="049bc-116">Logischer AND-Operator &amp;</span><span class="sxs-lookup"><span data-stu-id="049bc-116">Logical AND operator &amp;</span></span>

<span data-ttu-id="049bc-117">Der `&`-Operator berechnet die logische AND-Operation des Operanden.</span><span class="sxs-lookup"><span data-stu-id="049bc-117">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="049bc-118">Das Ergebnis von `x & y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="049bc-118">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="049bc-119">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="049bc-119">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="049bc-120">Der `&`-Operator wertet beide Operanden aus, selbst wenn der linke Operand als `false` ausgewertet wird, sodass das Ergebnis des Vorgangs unabhängig vom Wert des rechten Operanden `false` ist.</span><span class="sxs-lookup"><span data-stu-id="049bc-120">The `&` operator evaluates both operands even if the left-hand operand evaluates to `false`, so that the operation result is `false` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="049bc-121">Im folgenden Beispiel ist der rechte Operand des `&`-Operators ein Methodenaufruf, der unabhängig vom Wert des linken Operanden ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="049bc-121">In the following example, the right-hand operand of the `&` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical AND](snippets/shared/BooleanLogicalOperators.cs#And)]

<span data-ttu-id="049bc-122">Der [bedingte logische AND-Operator](#conditional-logical-and-operator-) `&&` berechnet auch die logische AND-Operation der Operanden, wertet den rechten Operanden aber nicht aus, wenn der linke Operand `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="049bc-122">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `false`.</span></span>

<span data-ttu-id="049bc-123">Für Operanden der [integralen numerischen Typen](../builtin-types/integral-numeric-types.md) berechnet der Operator `&`[bitweises logisches UND](bitwise-and-shift-operators.md#logical-and-operator-) für seine Operanden.</span><span class="sxs-lookup"><span data-stu-id="049bc-123">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="049bc-124">Der unäre `&`-Operator ist der [address-of-Operator](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="049bc-124">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="049bc-125">Logischer exklusiver OR-Operator: ^</span><span class="sxs-lookup"><span data-stu-id="049bc-125">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="049bc-126">Die `^`-Operator berechnet das logische exklusive OR, auch als logischer XOR bezeichnet, seiner Operanden.</span><span class="sxs-lookup"><span data-stu-id="049bc-126">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="049bc-127">Das Ergebnis von `x ^ y` ist `true`, wenn `x``true` ergibt und `y``false`ergibt, oder `x``false` ergibt und `y``true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="049bc-127">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="049bc-128">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="049bc-128">Otherwise, the result is `false`.</span></span> <span data-ttu-id="049bc-129">Das heißt, für die `bool`-Operanden berechnet der `^`-Operator das gleiche Ergebnis wie der [Ungleichheitsoperator](equality-operators.md#inequality-operator-) `!=`.</span><span class="sxs-lookup"><span data-stu-id="049bc-129">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](snippets/shared/BooleanLogicalOperators.cs#Xor)]

<span data-ttu-id="049bc-130">Für Operanden der [integralen numerischen Typen](../builtin-types/integral-numeric-types.md) berechnet der Operator `^`[bitweises logisches exklusives ODER](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) für seine Operanden.</span><span class="sxs-lookup"><span data-stu-id="049bc-130">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="049bc-131">Logischer OR-Operator: |</span><span class="sxs-lookup"><span data-stu-id="049bc-131">Logical OR operator |</span></span>

<span data-ttu-id="049bc-132">Der `|`-Operator berechnet die logische OR-Operation des Operanden.</span><span class="sxs-lookup"><span data-stu-id="049bc-132">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="049bc-133">Das Ergebnis von `x | y` ist `true`, wenn entweder `x` oder `y``true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="049bc-133">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="049bc-134">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="049bc-134">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="049bc-135">Der `|`-Operator wertet beide Operanden aus, selbst wenn der linke Operand als `true` ausgewertet wird, sodass das Ergebnis des Vorgangs unabhängig vom Wert des rechten Operanden `true` ist.</span><span class="sxs-lookup"><span data-stu-id="049bc-135">The `|` operator evaluates both operands even if the left-hand operand evaluates to `true`, so that the operation result is `true` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="049bc-136">Im folgenden Beispiel ist der rechte Operand des `|`-Operators ein Methodenaufruf, der unabhängig vom Wert des linken Operanden ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="049bc-136">In the following example, the right-hand operand of the `|` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical OR](snippets/shared/BooleanLogicalOperators.cs#Or)]

<span data-ttu-id="049bc-137">Der [bedingte logische OR-Operator](#conditional-logical-or-operator-) `||` berechnet auch die logische OR-Operation der Operanden, wertet den rechten Operanden aber nicht aus, wenn der linke Operand `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="049bc-137">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `true`.</span></span>

<span data-ttu-id="049bc-138">Für Operanden der [integralen numerischen Typen](../builtin-types/integral-numeric-types.md) berechnet der Operator `|`[bitweises logisches ODER](bitwise-and-shift-operators.md#logical-or-operator-) für seine Operanden.</span><span class="sxs-lookup"><span data-stu-id="049bc-138">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-ampamp"></a><a name="conditional-logical-and-operator-"></a> <span data-ttu-id="049bc-139">Bedingter logischer AND-Operator &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="049bc-139">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="049bc-140">Der bedingte logische AND-Operator `&&`, auch bekannt als der "kurzschließender" logischer AND-Operator bezeichnet, berechnet die logische AND-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="049bc-140">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="049bc-141">Das Ergebnis von `x && y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="049bc-141">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="049bc-142">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="049bc-142">Otherwise, the result is `false`.</span></span> <span data-ttu-id="049bc-143">Wenn `x` als `false` ausgewertet wird, wird `y` nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="049bc-143">If `x` evaluates to `false`, `y` is not evaluated.</span></span>

<span data-ttu-id="049bc-144">Im folgenden Beispiel ist der rechte Operand des `&&`-Operators ein Methodenaufruf, der nicht ausgeführt wird, wenn der linke Operand `false` ergibt:</span><span class="sxs-lookup"><span data-stu-id="049bc-144">In the following example, the right-hand operand of the `&&` operator is a method call, which isn't performed if the left-hand operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](snippets/shared/BooleanLogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="049bc-145">Der [logische AND-Operator](#logical-and-operator-) `&` berechnet auch die logische AND-Operation der Operanden, es werden jedoch immer beide Operanden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="049bc-145">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="049bc-146">Bedingter logischer OR-Operator ||</span><span class="sxs-lookup"><span data-stu-id="049bc-146">Conditional logical OR operator ||</span></span>

<span data-ttu-id="049bc-147">Der bedingte logische OR-Operator `||`, auch bekannt als der "kurzschließender" logischer OR-Operator bezeichnet, berechnet die logische OR-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="049bc-147">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="049bc-148">Das Ergebnis von `x || y` ist `true`, wenn entweder `x` oder `y``true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="049bc-148">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="049bc-149">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="049bc-149">Otherwise, the result is `false`.</span></span> <span data-ttu-id="049bc-150">Wenn `x` als `true` ausgewertet wird, wird `y` nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="049bc-150">If `x` evaluates to `true`, `y` is not evaluated.</span></span>

<span data-ttu-id="049bc-151">Im folgenden Beispiel ist der rechte Operand des `||`-Operators ein Methodenaufruf, der nicht ausgeführt wird, wenn der linke Operand `true` ergibt:</span><span class="sxs-lookup"><span data-stu-id="049bc-151">In the following example, the right-hand operand of the `||` operator is a method call, which isn't performed if the left-hand operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](snippets/shared/BooleanLogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="049bc-152">Der [logische OR-Operator](#logical-or-operator-) `|` berechnet auch die logische OR-Operation der Operanden, es werden jedoch immer beide Operanden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="049bc-152">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="049bc-153">Logische boolesche Operatoren, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="049bc-153">Nullable Boolean logical operators</span></span>

<span data-ttu-id="049bc-154">Für `bool?`-Operanden unterstützen die Operatoren [`&` (logisches UND)](#logical-and-operator-) und [`|` (logisches ODER)](#logical-or-operator-) die dreiwertige Logik wie folgt:</span><span class="sxs-lookup"><span data-stu-id="049bc-154">For `bool?` operands, the [`&` (logical AND)](#logical-and-operator-) and [`|` (logical OR)](#logical-or-operator-) operators support the three-valued logic as follows:</span></span>

- <span data-ttu-id="049bc-155">Für den Operator `&` wird nur `true` zurückgegeben, wenn auch beide seiner Operanden `true` ergeben.</span><span class="sxs-lookup"><span data-stu-id="049bc-155">The `&` operator produces `true` only if both its operands evaluate to `true`.</span></span> <span data-ttu-id="049bc-156">Wenn für `x` und `y` `false` zurückgegeben wird, ergibt `x & y` `false` (auch wenn ein anderer Operand `null` ergibt).</span><span class="sxs-lookup"><span data-stu-id="049bc-156">If either `x` or `y` evaluates to `false`, `x & y` produces `false` (even if another operand evaluates to `null`).</span></span> <span data-ttu-id="049bc-157">Andernfalls ist das Ergebnis von `x & y` `null`.</span><span class="sxs-lookup"><span data-stu-id="049bc-157">Otherwise, the result of `x & y` is `null`.</span></span>

- <span data-ttu-id="049bc-158">Für den Operator `|` wird nur `false` zurückgegeben, wenn auch beide seiner Operanden `false` ergeben.</span><span class="sxs-lookup"><span data-stu-id="049bc-158">The `|` operator produces `false` only if both its operands evaluate to `false`.</span></span> <span data-ttu-id="049bc-159">Wenn für `x` und `y` `true` zurückgegeben wird, ergibt `x | y` `true` (auch wenn ein anderer Operand `null` ergibt).</span><span class="sxs-lookup"><span data-stu-id="049bc-159">If either `x` or `y` evaluates to `true`, `x | y` produces `true` (even if another operand evaluates to `null`).</span></span> <span data-ttu-id="049bc-160">Andernfalls ist das Ergebnis von `x | y` `null`.</span><span class="sxs-lookup"><span data-stu-id="049bc-160">Otherwise, the result of `x | y` is `null`.</span></span>

<span data-ttu-id="049bc-161">Der folgenden Tabelle können Sie die Semantik entnehmen:</span><span class="sxs-lookup"><span data-stu-id="049bc-161">The following table presents that semantics:</span></span>

|<span data-ttu-id="049bc-162">w</span><span class="sxs-lookup"><span data-stu-id="049bc-162">x</span></span>|<span data-ttu-id="049bc-163">y</span><span class="sxs-lookup"><span data-stu-id="049bc-163">y</span></span>|<span data-ttu-id="049bc-164">x&y</span><span class="sxs-lookup"><span data-stu-id="049bc-164">x&y</span></span>|<span data-ttu-id="049bc-165">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="049bc-165">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="049bc-166">true</span><span class="sxs-lookup"><span data-stu-id="049bc-166">true</span></span>|<span data-ttu-id="049bc-167">true</span><span class="sxs-lookup"><span data-stu-id="049bc-167">true</span></span>|<span data-ttu-id="049bc-168">true</span><span class="sxs-lookup"><span data-stu-id="049bc-168">true</span></span>|<span data-ttu-id="049bc-169">true</span><span class="sxs-lookup"><span data-stu-id="049bc-169">true</span></span>|  
|<span data-ttu-id="049bc-170">true</span><span class="sxs-lookup"><span data-stu-id="049bc-170">true</span></span>|<span data-ttu-id="049bc-171">False</span><span class="sxs-lookup"><span data-stu-id="049bc-171">false</span></span>|<span data-ttu-id="049bc-172">false</span><span class="sxs-lookup"><span data-stu-id="049bc-172">false</span></span>|<span data-ttu-id="049bc-173">true</span><span class="sxs-lookup"><span data-stu-id="049bc-173">true</span></span>|  
|<span data-ttu-id="049bc-174">true</span><span class="sxs-lookup"><span data-stu-id="049bc-174">true</span></span>|<span data-ttu-id="049bc-175">NULL</span><span class="sxs-lookup"><span data-stu-id="049bc-175">null</span></span>|<span data-ttu-id="049bc-176">NULL</span><span class="sxs-lookup"><span data-stu-id="049bc-176">null</span></span>|<span data-ttu-id="049bc-177">true</span><span class="sxs-lookup"><span data-stu-id="049bc-177">true</span></span>|  
|<span data-ttu-id="049bc-178">False</span><span class="sxs-lookup"><span data-stu-id="049bc-178">false</span></span>|<span data-ttu-id="049bc-179">true</span><span class="sxs-lookup"><span data-stu-id="049bc-179">true</span></span>|<span data-ttu-id="049bc-180">False</span><span class="sxs-lookup"><span data-stu-id="049bc-180">false</span></span>|<span data-ttu-id="049bc-181">true</span><span class="sxs-lookup"><span data-stu-id="049bc-181">true</span></span>|  
|<span data-ttu-id="049bc-182">False</span><span class="sxs-lookup"><span data-stu-id="049bc-182">false</span></span>|<span data-ttu-id="049bc-183">False</span><span class="sxs-lookup"><span data-stu-id="049bc-183">false</span></span>|<span data-ttu-id="049bc-184">False</span><span class="sxs-lookup"><span data-stu-id="049bc-184">false</span></span>|<span data-ttu-id="049bc-185">False</span><span class="sxs-lookup"><span data-stu-id="049bc-185">false</span></span>|  
|<span data-ttu-id="049bc-186">False</span><span class="sxs-lookup"><span data-stu-id="049bc-186">false</span></span>|<span data-ttu-id="049bc-187">NULL</span><span class="sxs-lookup"><span data-stu-id="049bc-187">null</span></span>|<span data-ttu-id="049bc-188">False</span><span class="sxs-lookup"><span data-stu-id="049bc-188">false</span></span>|<span data-ttu-id="049bc-189">NULL</span><span class="sxs-lookup"><span data-stu-id="049bc-189">null</span></span>|  
|<span data-ttu-id="049bc-190">NULL</span><span class="sxs-lookup"><span data-stu-id="049bc-190">null</span></span>|<span data-ttu-id="049bc-191">true</span><span class="sxs-lookup"><span data-stu-id="049bc-191">true</span></span>|<span data-ttu-id="049bc-192">NULL</span><span class="sxs-lookup"><span data-stu-id="049bc-192">null</span></span>|<span data-ttu-id="049bc-193">true</span><span class="sxs-lookup"><span data-stu-id="049bc-193">true</span></span>|  
|<span data-ttu-id="049bc-194">NULL</span><span class="sxs-lookup"><span data-stu-id="049bc-194">null</span></span>|<span data-ttu-id="049bc-195">False</span><span class="sxs-lookup"><span data-stu-id="049bc-195">false</span></span>|<span data-ttu-id="049bc-196">False</span><span class="sxs-lookup"><span data-stu-id="049bc-196">false</span></span>|<span data-ttu-id="049bc-197">NULL</span><span class="sxs-lookup"><span data-stu-id="049bc-197">null</span></span>|  
|<span data-ttu-id="049bc-198">NULL</span><span class="sxs-lookup"><span data-stu-id="049bc-198">null</span></span>|<span data-ttu-id="049bc-199">NULL</span><span class="sxs-lookup"><span data-stu-id="049bc-199">null</span></span>|<span data-ttu-id="049bc-200">NULL</span><span class="sxs-lookup"><span data-stu-id="049bc-200">null</span></span>|<span data-ttu-id="049bc-201">NULL</span><span class="sxs-lookup"><span data-stu-id="049bc-201">null</span></span>|  

<span data-ttu-id="049bc-202">Das Verhalten dieser Operatoren unterscheidet sich vom typischen Operatorverhalten bei Typen, die NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="049bc-202">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="049bc-203">In der Regel kann ein Operator, der für Operanden eines Werttyps definiert ist, auch mit Operanden des entsprechenden Nullable-Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="049bc-203">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="049bc-204">Ein solcher Operator generiert `null`, wenn einer seiner Operanden in `null` ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="049bc-204">Such an operator produces `null` if any of its operands evaluates to `null`.</span></span> <span data-ttu-id="049bc-205">Die `&`- und `|`-Operatoren können jedoch Nicht-NULL-Werte erzeugen, auch wenn einer der Operanden in `null` ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="049bc-205">However, the `&` and `|` operators can produce non-null even if one of the operands evaluates to `null`.</span></span> <span data-ttu-id="049bc-206">Weitere Informationen zum Operatorverhalten bei Nullable-Werttypen finden Sie im Abschnitt [„Lifted“ Operatoren](../builtin-types/nullable-value-types.md#lifted-operators) des Artikels [Nullable-Werttypen](../builtin-types/nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="049bc-206">For more information about the operator behavior with nullable value types, see the [Lifted operators](../builtin-types/nullable-value-types.md#lifted-operators) section of the [Nullable value types](../builtin-types/nullable-value-types.md) article.</span></span>

<span data-ttu-id="049bc-207">Sie können auch die `!`- und `^`- Operatoren mit `bool?`-Operanden verwenden, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="049bc-207">You can also use the `!` and `^` operators with `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](snippets/shared/BooleanLogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="049bc-208">Die bedingten logischen Operatoren `&&` und `||` unterstützen keine `bool?`-Operanden.</span><span class="sxs-lookup"><span data-stu-id="049bc-208">The conditional logical operators `&&` and `||` don't support `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="049bc-209">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="049bc-209">Compound assignment</span></span>

<span data-ttu-id="049bc-210">Bei einem binären Operator `op` entspricht ein Verbundzuweisungsausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="049bc-210">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="049bc-211">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="049bc-211">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="049bc-212">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="049bc-212">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="049bc-213">Die `&`-, `|`- und `^`-Operatoren unterstützen die Verbundzuweisung, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="049bc-213">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](snippets/shared/BooleanLogicalOperators.cs#CompoundAssignment)]

> [!NOTE]
> <span data-ttu-id="049bc-214">Die bedingten logischen Operatoren `&&` und `||` unterstützen nicht die Verbundzuweisung.</span><span class="sxs-lookup"><span data-stu-id="049bc-214">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="049bc-215">Operatorrangfolge</span><span class="sxs-lookup"><span data-stu-id="049bc-215">Operator precedence</span></span>

<span data-ttu-id="049bc-216">In der folgenden Liste sind die logischen Operatoren beginnend mit dem höchsten Rangfolgenoperator absteigend sortiert:</span><span class="sxs-lookup"><span data-stu-id="049bc-216">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="049bc-217">Logischer Negationsoperator `!`</span><span class="sxs-lookup"><span data-stu-id="049bc-217">Logical negation operator `!`</span></span>
- <span data-ttu-id="049bc-218">Logischer AND-Operator `&`</span><span class="sxs-lookup"><span data-stu-id="049bc-218">Logical AND operator `&`</span></span>
- <span data-ttu-id="049bc-219">Logischer exklusiver OR-Operator `^`</span><span class="sxs-lookup"><span data-stu-id="049bc-219">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="049bc-220">Logischer OR-Operator `|`</span><span class="sxs-lookup"><span data-stu-id="049bc-220">Logical OR operator `|`</span></span>
- <span data-ttu-id="049bc-221">Bedingter logischer AND-Operator `&&`</span><span class="sxs-lookup"><span data-stu-id="049bc-221">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="049bc-222">Bedingter logischer OR-Operator `||`</span><span class="sxs-lookup"><span data-stu-id="049bc-222">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="049bc-223">Verwenden Sie Klammern `()`, wenn Sie die Reihenfolge der Auswertung ändern möchten, die durch Operatorrangfolge festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="049bc-223">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](snippets/shared/BooleanLogicalOperators.cs#Precedence)]

<span data-ttu-id="049bc-224">Die vollständige Liste der nach Rangfolgenebene sortierten C#-Operatoren finden Sie im Abschnitt [Operatorrangfolge](index.md#operator-precedence) im Artikel [C#-Operatoren](index.md).</span><span class="sxs-lookup"><span data-stu-id="049bc-224">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="049bc-225">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="049bc-225">Operator overloadability</span></span>

<span data-ttu-id="049bc-226">Ein benutzerdefinierter Typ kann die Operatoren `!`, `&`, `|` und `^`[überladen](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="049bc-226">A user-defined type can [overload](operator-overloading.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="049bc-227">Wenn ein binärer Operator überladen ist, wird der zugehörige Verbundzuweisungsoperator implizit auch überladen.</span><span class="sxs-lookup"><span data-stu-id="049bc-227">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="049bc-228">Ein benutzerdefinierter Typ kann einen Verbundzuweisungsoperator nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="049bc-228">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="049bc-229">Ein benutzerdefinierter Typ kann die bedingten logischen Operatoren `&&` und `||` nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="049bc-229">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="049bc-230">Wenn jedoch ein benutzerdefinierter Typ die [„true“ und „false“-Operatoren](true-false-operators.md) und den `&`- oder `|`-Operator in einer bestimmten Weise überlädt, kann die `&&`- bzw. `||`-Operation für die Operanden dieses Typs ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="049bc-230">However, if a user-defined type overloads the [true and false operators](true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="049bc-231">Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte bedingte logische Operatoren](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="049bc-231">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="049bc-232">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="049bc-232">C# language specification</span></span>

<span data-ttu-id="049bc-233">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="049bc-233">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="049bc-234">Logischer Negationsoperator</span><span class="sxs-lookup"><span data-stu-id="049bc-234">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="049bc-235">Logical operators (Logische Operatoren)</span><span class="sxs-lookup"><span data-stu-id="049bc-235">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="049bc-236">Conditional logical operators (Bedingte logische Operatoren)</span><span class="sxs-lookup"><span data-stu-id="049bc-236">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="049bc-237">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="049bc-237">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="049bc-238">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="049bc-238">See also</span></span>

- [<span data-ttu-id="049bc-239">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="049bc-239">C# reference</span></span>](../index.md)
- [<span data-ttu-id="049bc-240">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="049bc-240">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="049bc-241">Bitweise und Schiebeoperatoren</span><span class="sxs-lookup"><span data-stu-id="049bc-241">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
