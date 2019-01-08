---
title: '!=-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 12/14/2018
f1_keywords:
- '!=_CSharpKeyword'
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
ms.openlocfilehash: 939b5664dba4345e62a43fb2f8d4d5379659d6aa
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610176"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="287f1-102">Operator != (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="287f1-102">!= Operator (C# Reference)</span></span>

<span data-ttu-id="287f1-103">Der Ungleichheitsoperator `!=` gibt `true` zurück, wenn die Operanden nicht gleich sind; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="287f1-103">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="287f1-104">Für die Operanden der [integrierten Typen](../keywords/built-in-types-table.md) führt der Ausdruck `x != y` zum selben Ergebnis wie der Ausdruck `!(x == y)`.</span><span class="sxs-lookup"><span data-stu-id="287f1-104">For the operands of the [built-in types](../keywords/built-in-types-table.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="287f1-105">Weitere Informationen finden Sie im Artikel [==-Operator](equality-comparison-operator.md).</span><span class="sxs-lookup"><span data-stu-id="287f1-105">For more information, see the [== Operator](equality-comparison-operator.md) article.</span></span>

<span data-ttu-id="287f1-106">Im folgenden Beispiel wird die Verwendung des `!=`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="287f1-106">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="287f1-107">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="287f1-107">Operator overloadability</span></span>

<span data-ttu-id="287f1-108">Benutzerdefinierte Typen können den Operator `!=` [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="287f1-108">User-defined types can [overload](../keywords/operator.md) the `!=` operator.</span></span> <span data-ttu-id="287f1-109">Wenn ein Typ den Ungleichheitsoperator `!=` überlädt, muss er auch den [Gleichheitsoperator](equality-comparison-operator.md) `==` überladen.</span><span class="sxs-lookup"><span data-stu-id="287f1-109">If a type overloads the inequality operator `!=`, it must also overload the [equality operator](equality-comparison-operator.md) `==`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="287f1-110">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="287f1-110">C# language specification</span></span>

<span data-ttu-id="287f1-111">Weitere Informationen finden Sie im Abschnitt [Relationale und Typtestoperatoren](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="287f1-111">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="287f1-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="287f1-112">See also</span></span>

- [<span data-ttu-id="287f1-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="287f1-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="287f1-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="287f1-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="287f1-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="287f1-115">C# Operators</span></span>](index.md)
- [<span data-ttu-id="287f1-116">Übereinstimmungsvergleiche</span><span class="sxs-lookup"><span data-stu-id="287f1-116">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
