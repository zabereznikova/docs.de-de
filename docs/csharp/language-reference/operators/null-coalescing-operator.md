---
title: '?? Operator „-“: C#-Referenz'
ms.custom: seodec18
ms.date: 06/07/2019
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: a19b5558da36ffb11dabd1b9bec419a3623a0f17
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2019
ms.locfileid: "67024987"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ab500-103">??</span><span class="sxs-lookup"><span data-stu-id="ab500-103">??</span></span> <span data-ttu-id="ab500-104">Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ab500-104">operator (C# reference)</span></span>

<span data-ttu-id="ab500-105">Der NULL-Zusammenfügungsoperator `??` gibt den Wert des linken Operanden zurück, wenn dieser nicht `null` ist. Andernfalls wertet der Operator den rechten Operanden aus und gibt dessen Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="ab500-105">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="ab500-106">Der `??`-Operator wertet seinen rechten Operanden nicht aus, wenn der linke Operand auf einen Wert ungleich NULL ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="ab500-106">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="ab500-107">Der NULL-Zusammenfügungsoperator ist rechtsassoziativ, d.h. ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="ab500-107">The null-coalescing operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ?? b ?? c
```

<span data-ttu-id="ab500-108">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="ab500-108">is evaluated as</span></span>

```csharp
a ?? (b ?? c)
```

<span data-ttu-id="ab500-109">Der `??`-Operator kann in den folgenden Szenarien nützlich sein:</span><span class="sxs-lookup"><span data-stu-id="ab500-109">The `??` operator can be useful in the following scenarios:</span></span>

- <span data-ttu-id="ab500-110">In Ausdrücken mit den [NULL-bedingten Operatoren „?.“ und „?[]“](member-access-operators.md#null-conditional-operators--and-) können Sie den NULL-Zusammenfügungsoperator verwenden, um einen alternativen Ausdruck zum Auswerten für den Fall bereitzustellen, dass das Ergebnis des NULL-bedingten Vorgangs `null` ist:</span><span class="sxs-lookup"><span data-stu-id="ab500-110">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="ab500-111">Wenn Sie mit [Nullable-Werttypen](../../programming-guide/nullable-types/index.md) arbeiten und den Wert eines zugrunde liegenden Werttyps bereitstellen müssen, verwenden Sie den NULL-Zusammenfügungsoperator, um den Wert für den Fall anzugeben, dass der Wert eines Nullable-Typs `null` ist:</span><span class="sxs-lookup"><span data-stu-id="ab500-111">When you work with [nullable value types](../../programming-guide/nullable-types/index.md) and need to provide a value of an underlying value type, use the null-coalescing operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="ab500-112">Verwenden Sie die <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>-Methode, wenn der Wert, der verwenden werden soll, falls der Wert des Nullable-Typs `null` lautet, der Standardwert des zugrunde liegenden Werttyps sein soll.</span><span class="sxs-lookup"><span data-stu-id="ab500-112">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="ab500-113">Ab C# 7.0 können Sie einen [`throw`Ausdruck](../keywords/throw.md#the-throw-expression) als rechten Operanden des NULL-Zusammenfügungsoperators verwenden, um den Code für die Überprüfung der Argumente präziser zu fassen:</span><span class="sxs-lookup"><span data-stu-id="ab500-113">Starting with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the null-coalescing operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="ab500-114">Das oben stehende Beispiel veranschaulicht auch, wie Sie [Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) verwenden, um eine Eigenschaft zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ab500-114">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="ab500-115">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="ab500-115">Operator overloadability</span></span>

<span data-ttu-id="ab500-116">Der NULL-Zusammenfügungsoperator kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="ab500-116">The null-coalescing operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ab500-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="ab500-117">C# language specification</span></span>

<span data-ttu-id="ab500-118">Weitere Informationen finden Sie unter [NULL-Zusammenfügungsoperator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) in der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="ab500-118">For more information, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ab500-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab500-119">See also</span></span>

- [<span data-ttu-id="ab500-120">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ab500-120">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ab500-121">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="ab500-121">C# operators</span></span>](index.md)
- <span data-ttu-id="ab500-122">[?.- und ?[]-Operatoren](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="ab500-122">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="ab500-123">?:-Operator</span><span class="sxs-lookup"><span data-stu-id="ab500-123">?: operator</span></span>](conditional-operator.md)
