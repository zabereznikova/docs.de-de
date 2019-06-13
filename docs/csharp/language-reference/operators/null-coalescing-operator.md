---
title: ?? -Operator – C#-Referenz
ms.custom: seodec18
ms.date: 06/07/2019
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 8ca97261b348b7813ab179abbc1f2c5f535966a1
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816012"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="21aa2-103">??</span><span class="sxs-lookup"><span data-stu-id="21aa2-103">??</span></span> <span data-ttu-id="21aa2-104">operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="21aa2-104">operator (C# Reference)</span></span>

<span data-ttu-id="21aa2-105">Der Null-Sammeloperator `??` Wert des linken Operanden zurückgegeben, falls dies nicht der Fall `null`ist, andernfalls es der Rechte Operand ausgewertet wird und das Ergebnis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="21aa2-105">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="21aa2-106">Die `??` Operator nicht seines rechtsseitigen Operanden ausgewertet, wenn der linke Operand ungleich Null ergibt.</span><span class="sxs-lookup"><span data-stu-id="21aa2-106">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="21aa2-107">Der Null-Sammeloperator ist rechtsassoziativ, d. h. ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="21aa2-107">The null-coalescing operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ?? b ?? c
```

<span data-ttu-id="21aa2-108">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="21aa2-108">is evaluated as</span></span>

```csharp
a ?? (b ?? c)
```

<span data-ttu-id="21aa2-109">Die `??` Operator kann in den folgenden Szenarien nützlich sein:</span><span class="sxs-lookup"><span data-stu-id="21aa2-109">The `??` operator can be useful in the following scenarios:</span></span>

- <span data-ttu-id="21aa2-110">In Ausdrücken, mit der [nullbedingten Operatoren?. und?] ](member-access-operators.md#null-conditional-operators--and-), können Sie die Null-Sammeloperator, geben Sie einen alternativen Ausdruck zum Auswerten der Fall, dass das Ergebnis des Ausdrucks mit Null-bedingten Vorgängen `null`:</span><span class="sxs-lookup"><span data-stu-id="21aa2-110">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="21aa2-111">Beim Arbeiten mit [auf NULL festlegbare Werttypen](../../programming-guide/nullable-types/index.md) und müssen einen Wert, der eine zugrunde liegende Werttyp Geben Sie mithilfe der Null-Sammeloperator Geben Sie den Wert aus, um anzugeben, falls ein nullable-Typ-Wert ist `null`:</span><span class="sxs-lookup"><span data-stu-id="21aa2-111">When you work with [nullable value types](../../programming-guide/nullable-types/index.md) and need to provide a value of an underlying value type, use the null-coalescing operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="21aa2-112">Verwenden der <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> Methode Wenn der Wert, der verwendet werden, wenn ein nullable-Typ-Wert ist `null` sollte der Standardwert der zugrunde liegende Werttyp sein.</span><span class="sxs-lookup"><span data-stu-id="21aa2-112">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="21aa2-113">Beginnend mit C# 7.0 können Sie eine [ `throw` Ausdruck](../keywords/throw.md#the-throw-expression) als der Rechte Operand des Operators, der die Argument-Überprüfen von Code präziser werden, Null-Sammeloperator:</span><span class="sxs-lookup"><span data-stu-id="21aa2-113">Starting with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the null-coalescing operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="21aa2-114">Im vorherigen Beispiel wird auch veranschaulicht, wie [ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) eine Eigenschaft definieren.</span><span class="sxs-lookup"><span data-stu-id="21aa2-114">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="21aa2-115">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="21aa2-115">Operator overloadability</span></span>

<span data-ttu-id="21aa2-116">Der Null-Sammeloperator werden nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="21aa2-116">The null-coalescing operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="21aa2-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="21aa2-117">C# language specification</span></span>

<span data-ttu-id="21aa2-118">Weitere Informationen finden Sie unter [der null-Sammeloperator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) Teil der [ C# Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="21aa2-118">For more information, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="21aa2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21aa2-119">See also</span></span>

- [<span data-ttu-id="21aa2-120">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="21aa2-120">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="21aa2-121">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="21aa2-121">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="21aa2-122">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="21aa2-122">C# operators</span></span>](index.md)
- <span data-ttu-id="21aa2-123">[?.- und ?[]-Operatoren](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="21aa2-123">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="21aa2-124">?:-Operator</span><span class="sxs-lookup"><span data-stu-id="21aa2-124">?: operator</span></span>](conditional-operator.md)
