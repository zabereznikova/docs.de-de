---
title: 'Operator ?: (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 3e45ff6eaaefa5829c3ed9415abe1a12b7a1d069
ms.sourcegitcommit: 4bca8f7e172fd019ef437a4803bf5895c6bc4781
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2018
ms.locfileid: "50980621"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="25782-102">Operator ?: (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="25782-102">?: Operator (C# Reference)</span></span>

<span data-ttu-id="25782-103">Der bedingte Operator (`?:`), gemeinhin als ternärer bedingter Operator bekannt, gibt abhängig vom Wert eines booleschen Ausdrucks einen von zwei Werten zurück.</span><span class="sxs-lookup"><span data-stu-id="25782-103">The conditional operator (`?:`), commonly known as the ternary conditional operator, returns one of two values depending on the value of a Boolean expression.</span></span> <span data-ttu-id="25782-104">Nachfolgend ist die Syntax für den bedingten Operator aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="25782-104">Following is the syntax for the conditional operator.</span></span>  

```csharp
condition ? first_expression : second_expression;  
```

<span data-ttu-id="25782-105">Beginnend mit C# 7.2 können `first_expression` und `second_expression` [`ref`-Ausdrücke sein](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md):</span><span class="sxs-lookup"><span data-stu-id="25782-105">Beginning with C# 7.2, the `first_expression` and `second_expression` my be [`ref` expressions](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md):</span></span>

```csharp
ref condition ? ref first_expression : ref second_expression;  
```

<span data-ttu-id="25782-106">Das Ergebnis kann einer `ref`- oder `ref readonly`-Variablen oder einer Variable mit keinem der beiden Modifizierer zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="25782-106">The result may be assigned to a `ref` or `ref readonly` variable, or to a variable with neither modifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="25782-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25782-107">Remarks</span></span>

<span data-ttu-id="25782-108">`condition` muss mit `true` oder `false` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="25782-108">The `condition` must evaluate to `true` or `false`.</span></span> <span data-ttu-id="25782-109">Wenn `condition` den Wert `true` hat, wird `first_expression` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="25782-109">If `condition` is `true`, `first_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="25782-110">Wenn `condition` den Wert `false` hat, wird `second_expression` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="25782-110">If `condition` is `false`, `second_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="25782-111">Nur einer der beiden Ausdrücke wird ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="25782-111">Only one of the two expressions is evaluated.</span></span> <span data-ttu-id="25782-112">Dies ist besonders wichtig für Ausdrücke, deren Ergebnis ein `ref` ist, da Folgendes gilt:</span><span class="sxs-lookup"><span data-stu-id="25782-112">This is particularly important for expressions where the result is a `ref`, as the following is valid:</span></span>

```csharp
ref (storage != null) ? ref storage[3] : ref defaultValue;
```

<span data-ttu-id="25782-113">Der Verweis auf `storage` wird nicht ausgewertet, wenn `storage` null ist.</span><span class="sxs-lookup"><span data-stu-id="25782-113">The reference to `storage` is not evaluated when `storage` is null.</span></span>

<span data-ttu-id="25782-114">Wenn das Ergebnis ein Wert ist, muss der Typ von `first_expression` und `second_expression` identisch sein, oder es muss eine implizite Konvertierung von einem Typ in einen anderen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="25782-114">When the result is a value, the type of `first_expression` and `second_expression` must be the same, or there must be an implicit conversion from one type to the other.</span></span> <span data-ttu-id="25782-115">Wenn das Ergebnis ein `ref` ist, muss der Typ von `first_expression` und `second_expression` identisch sein.</span><span class="sxs-lookup"><span data-stu-id="25782-115">When the result is a `ref`, the type of `first_expression` and `second_expression` must be the same.</span></span>

<span data-ttu-id="25782-116">Sie können mithilfe des bedingten Operators Berechnungen präziser ausdrücken, die andernfalls möglicherweise eine `if-else`-Konstruktion benötigen.</span><span class="sxs-lookup"><span data-stu-id="25782-116">You can express calculations that might otherwise require an `if-else` construction more concisely by using the conditional operator.</span></span> <span data-ttu-id="25782-117">Im folgenden Code wird z. B. zuerst eine `if`-Anweisung und anschließend ein bedingter Operator verwendet, um eine ganze Zahl als positiv oder negativ zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="25782-117">For example, the following code uses first an `if` statement and then a conditional operator to classify an integer as positive or negative.</span></span>

```csharp
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```

<span data-ttu-id="25782-118">Der bedingte Operator ist rechtsassoziativ.</span><span class="sxs-lookup"><span data-stu-id="25782-118">The conditional operator is right-associative.</span></span> <span data-ttu-id="25782-119">Der Ausdruck `a ? b : c ? d : e` wird als `a ? b : (c ? d : e)` und nicht als `(a ? b : c) ? d : e` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="25782-119">The expression `a ? b : c ? d : e` is evaluated as `a ? b : (c ? d : e)`, not as `(a ? b : c) ? d : e`.</span></span>  
  
<span data-ttu-id="25782-120">Der bedingte Operator kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="25782-120">The conditional operator cannot be overloaded.</span></span>
  
## <a name="example"></a><span data-ttu-id="25782-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="25782-121">Example</span></span>

<span data-ttu-id="25782-122">Das folgende Beispiel zeigt den bedingten Operator, dessen Ergebnis ein Wert ist:</span><span class="sxs-lookup"><span data-stu-id="25782-122">The following example shows the conditional operator whose result is a value:</span></span>

[!code-csharp[csRefOperators?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

<span data-ttu-id="25782-123">Die folgende Alternative zeigt den bedingten Operator, dessen Ergebnis ein Verweis ist:</span><span class="sxs-lookup"><span data-stu-id="25782-123">The following alternative shows the conditional operator where the result is a reference:</span></span>

[!code-csharp[csRefOperatorsRef?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

## <a name="see-also"></a><span data-ttu-id="25782-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25782-124">See Also</span></span>

- [<span data-ttu-id="25782-125">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="25782-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="25782-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="25782-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="25782-127">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="25782-127">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="25782-128">if-else</span><span class="sxs-lookup"><span data-stu-id="25782-128">if-else</span></span>](../../../csharp/language-reference/keywords/if-else.md)  
- <span data-ttu-id="25782-129">[?.- und ?[]-Operatoren](../../../csharp/language-reference/operators/null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="25782-129">[?. and ?[] Operators](../../../csharp/language-reference/operators/null-conditional-operators.md)</span></span>  
- [<span data-ttu-id="25782-130">?? Operator</span><span class="sxs-lookup"><span data-stu-id="25782-130">?? Operator</span></span>](../../../csharp/language-reference/operators/null-coalescing-operator.md)
