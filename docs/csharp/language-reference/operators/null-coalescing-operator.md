---
description: ?? und ??= (Operatoren) – C#-Referenz
title: ?? und ??= (Operatoren) – C#-Referenz
ms.date: 09/10/2019
f1_keywords:
- ??_CSharpKeyword
- ??=_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
- null-coalescing assignment [C#]
- ??= operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 273bc6d3a4c65c09dc600621b435bf0d1baea9e4
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118285"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="efb9a-105">??</span><span class="sxs-lookup"><span data-stu-id="efb9a-105">??</span></span> <span data-ttu-id="efb9a-106">und ??= (Operatoren) – C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="efb9a-106">and ??= operators (C# reference)</span></span>

<span data-ttu-id="efb9a-107">Der NULL-Zusammenfügungsoperator `??` gibt den Wert des linken Operanden zurück, wenn dieser nicht `null` ist. Andernfalls wertet der Operator den rechten Operanden aus und gibt dessen Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="efb9a-107">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="efb9a-108">Der `??`-Operator wertet seinen rechten Operanden nicht aus, wenn der linke Operand auf einen Wert ungleich NULL ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="efb9a-108">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="efb9a-109">Ab C# 8.0 können Sie den NULL-Sammelzuweisungsoperator `??=` verwenden, um den Wert des rechten Operanden dem linken Operanden nur dann zuzuweisen, wenn die Auswertung des linken Operanden `null` ergibt.</span><span class="sxs-lookup"><span data-stu-id="efb9a-109">Available in C# 8.0 and later, the null-coalescing assignment operator `??=` assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="efb9a-110">Der `??=`-Operator wertet seinen rechten Operanden nicht aus, wenn der linke Operand auf einen Wert ungleich NULL ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="efb9a-110">The `??=` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

[!code-csharp[null-coalescing assignment](snippets/shared/NullCoalescingOperator.cs#Assignment)]

<span data-ttu-id="efb9a-111">Der linke Operand des `??=`-Operators muss eine Variable, eine [Eigenschaft](../../programming-guide/classes-and-structs/properties.md) oder ein [Indexer](../../programming-guide/indexers/index.md)-Element sein.</span><span class="sxs-lookup"><span data-stu-id="efb9a-111">The left-hand operand of the `??=` operator must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element.</span></span>

<span data-ttu-id="efb9a-112">In C# 7.3 und früheren Versionen muss der Typ des linken Operanden des `??`-Operators entweder ein [Verweistyp](../keywords/reference-types.md) oder ein [Nullable-Werttyp](../builtin-types/nullable-value-types.md) sein.</span><span class="sxs-lookup"><span data-stu-id="efb9a-112">In C# 7.3 and earlier, the type of the left-hand operand of the `??` operator must be either a [reference type](../keywords/reference-types.md) or a [nullable value type](../builtin-types/nullable-value-types.md).</span></span> <span data-ttu-id="efb9a-113">Ab C# 8.0 wird diese Anforderung durch Folgendes ersetzt: der Typ des linken Operanden der Operatoren `??` und `??=` kann kein Werttyp sein, der nicht auf NULL festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="efb9a-113">Beginning with C# 8.0, that requirement is replaced with the following: the type of the left-hand operand of the `??` and `??=` operators cannot be a non-nullable value type.</span></span> <span data-ttu-id="efb9a-114">Das heißt, Sie können ab C# 8.0 die NULL-Sammeloperatoren mit uneingeschränkten Typparametern verwenden:</span><span class="sxs-lookup"><span data-stu-id="efb9a-114">In particular, beginning with C# 8.0, you can use the null-coalescing operators with unconstrained type parameters:</span></span>

[!code-csharp[unconstrained type parameter](snippets/shared/NullCoalescingOperator.cs#UnconstrainedType)]

<span data-ttu-id="efb9a-115">Die NULL-Sammeloperatoren sind rechtsassoziativ.</span><span class="sxs-lookup"><span data-stu-id="efb9a-115">The null-coalescing operators are right-associative.</span></span> <span data-ttu-id="efb9a-116">Das heißt, Ausdrücke wie</span><span class="sxs-lookup"><span data-stu-id="efb9a-116">That is, expressions of the form</span></span>

```csharp
a ?? b ?? c
d ??= e ??= f
```

<span data-ttu-id="efb9a-117">werden wie folgt ausgewertet</span><span class="sxs-lookup"><span data-stu-id="efb9a-117">are evaluated as</span></span>

```csharp
a ?? (b ?? c)
d ??= (e ??= f)
```

## <a name="examples"></a><span data-ttu-id="efb9a-118">Beispiele</span><span class="sxs-lookup"><span data-stu-id="efb9a-118">Examples</span></span>

<span data-ttu-id="efb9a-119">Die Operatoren `??` und `??=` können in folgenden Szenarios nützlich sein:</span><span class="sxs-lookup"><span data-stu-id="efb9a-119">The `??` and `??=` operators can be useful in the following scenarios:</span></span>

- <span data-ttu-id="efb9a-120">In Ausdrücken mit den [NULL-bedingten Operatoren „?.“ und „?[]“](member-access-operators.md#null-conditional-operators--and-) können Sie den `??`-Operator verwenden, um einen alternativen Ausdruck zum Auswerten für den Fall bereitzustellen, dass das Ergebnis des NULL-bedingten Vorgangs `null` ist:</span><span class="sxs-lookup"><span data-stu-id="efb9a-120">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the `??` operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](snippets/shared/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="efb9a-121">Wenn Sie mit [Nullable-Werttypen](../builtin-types/nullable-value-types.md) arbeiten und den Wert eines zugrunde liegenden Werttyps bereitstellen müssen, verwenden Sie den `??`-Operator, um den Wert für den Fall anzugeben, dass der Wert eines Nullable-Typs `null` ist:</span><span class="sxs-lookup"><span data-stu-id="efb9a-121">When you work with [nullable value types](../builtin-types/nullable-value-types.md) and need to provide a value of an underlying value type, use the `??` operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](snippets/shared/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="efb9a-122">Verwenden Sie die <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>-Methode, wenn der Wert, der verwenden werden soll, falls der Wert des Nullable-Typs `null` lautet, der Standardwert des zugrunde liegenden Werttyps sein soll.</span><span class="sxs-lookup"><span data-stu-id="efb9a-122">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="efb9a-123">Ab C# 7.0 können Sie einen [`throw`Ausdruck](../keywords/throw.md#the-throw-expression) als rechten Operanden des `??`-Operators verwenden, um den Code für die Überprüfung der Argumente präziser zu fassen:</span><span class="sxs-lookup"><span data-stu-id="efb9a-123">Beginning with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the `??` operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](snippets/shared/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="efb9a-124">Das oben stehende Beispiel veranschaulicht auch, wie Sie [Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) verwenden, um eine Eigenschaft zu definieren.</span><span class="sxs-lookup"><span data-stu-id="efb9a-124">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

- <span data-ttu-id="efb9a-125">Ab C# 8.0 können Sie mit dem `??=`-Operator den Code</span><span class="sxs-lookup"><span data-stu-id="efb9a-125">Beginning with C# 8.0, you can use the `??=` operator to replace the code of the form</span></span>

  ```csharp
  if (variable is null)
  {
      variable = expression;
  }
  ```

  <span data-ttu-id="efb9a-126">durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="efb9a-126">with the following code:</span></span>

  ```csharp
  variable ??= expression;
  ```

## <a name="operator-overloadability"></a><span data-ttu-id="efb9a-127">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="efb9a-127">Operator overloadability</span></span>

<span data-ttu-id="efb9a-128">Die Operatoren `??` und `??=` können nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="efb9a-128">The operators `??` and `??=` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="efb9a-129">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="efb9a-129">C# language specification</span></span>

<span data-ttu-id="efb9a-130">Weitere Informationen über den `??`-Operator finden Sie im Abschnitt [NULL-Sammeloperatoren](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="efb9a-130">For more information about the `??` operator, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="efb9a-131">Weitere Informationen zum `??=`-Operator finden Sie unter [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span><span class="sxs-lookup"><span data-stu-id="efb9a-131">For more information about the `??=` operator, see the [feature proposal note](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="efb9a-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="efb9a-132">See also</span></span>

- [<span data-ttu-id="efb9a-133">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="efb9a-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="efb9a-134">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="efb9a-134">C# operators and expressions</span></span>](index.md)
- <span data-ttu-id="efb9a-135">[?.- und ?[]-Operatoren](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="efb9a-135">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="efb9a-136">?:-Operator</span><span class="sxs-lookup"><span data-stu-id="efb9a-136">?: operator</span></span>](conditional-operator.md)
