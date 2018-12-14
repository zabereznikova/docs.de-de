---
title: Operator ++ (C#-Referenz)
ms.date: 11/26/2018
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: b29f4f1ab00c0f8026f118cb72b090e3b728bfc5
ms.sourcegitcommit: 6ae7cdd0437a32884556dd4826ca90e957b7a4e3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2018
ms.locfileid: "48030469"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="56fa4-102">Operator ++ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="56fa4-102">++ Operator (C# Reference)</span></span>

<span data-ttu-id="56fa4-103">Der unäre Inkrementoperator (`++`) erhöht seinen Operanden um 1.</span><span class="sxs-lookup"><span data-stu-id="56fa4-103">The unary increment operator `++` increments its operand by 1.</span></span> <span data-ttu-id="56fa4-104">Er wird in zwei Formen unterstützt: der Postfix-Inkrementoperator `x++` und der Präfix-Inkrementoperator `++x`.</span><span class="sxs-lookup"><span data-stu-id="56fa4-104">It's supported in two forms: the postfix increment operator, `x++`, and the prefix increment operator, `++x`.</span></span>

## <a name="postfix-increment-operator"></a><span data-ttu-id="56fa4-105">Postfix-Operator für Inkrement</span><span class="sxs-lookup"><span data-stu-id="56fa4-105">Postfix increment operator</span></span>

<span data-ttu-id="56fa4-106">Das Ergebnis von `x++` ist der Wert von `x`  *vor* dem Vorgang, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="56fa4-106">The result of `x++` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix increment](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PostfixIncrement)]

## <a name="prefix-increment-operator"></a><span data-ttu-id="56fa4-107">Präfixinkrement-Operator</span><span class="sxs-lookup"><span data-stu-id="56fa4-107">Prefix increment operator</span></span>

<span data-ttu-id="56fa4-108">Das Ergebnis von `++x` ist der Wert von `x`  *nach* dem Vorgang, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="56fa4-108">The result of `++x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix increment](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PrefixIncrement)]

## <a name="remarks"></a><span data-ttu-id="56fa4-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="56fa4-109">Remarks</span></span>

<span data-ttu-id="56fa4-110">Der Inkrementoperator ist für alle [integralen Datentypen](../keywords/integral-types-table.md) (einschließlich [char](../keywords/char.md)-Typ), [Gleitkommatypen](../keywords/floating-point-types-table.md) und alle [Enumerationstypen](../keywords/enum.md) vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="56fa4-110">The increment operator is predefined for all [integral types](../keywords/integral-types-table.md) (including the [char](../keywords/char.md) type), [floating-point types](../keywords/floating-point-types-table.md), and any [enum](../keywords/enum.md) type.</span></span>

<span data-ttu-id="56fa4-111">Ein Operand des Inkrementoperators muss eine Variable, ein [Eigenschaftenzugriff](../../programming-guide/classes-and-structs/properties.md) oder ein [Indexzugriff](../../../csharp/programming-guide/indexers/index.md) sein.</span><span class="sxs-lookup"><span data-stu-id="56fa4-111">An operand of the increment operator must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../../csharp/programming-guide/indexers/index.md) access.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="56fa4-112">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="56fa4-112">Operator overloadability</span></span>

<span data-ttu-id="56fa4-113">Benutzerdefinierte Typen können den Operator `++` [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="56fa4-113">User-defined types can [overload](../keywords/operator.md) the `++` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="56fa4-114">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="56fa4-114">C# language specification</span></span>

<span data-ttu-id="56fa4-115">Weitere Informationen finden Sie in den Abschnitten [Postfix-Inkrement- und Dekrementoperatoren](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) und [Präfix-Inkrement- und Dekrementoperatoren](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="56fa4-115">For more information, see the [Postfix increment and decrement operators](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) and [Prefix increment and decrement operators](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="56fa4-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56fa4-116">See also</span></span>

- [<span data-ttu-id="56fa4-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="56fa4-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="56fa4-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="56fa4-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="56fa4-119">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="56fa4-119">C# Operators</span></span>](index.md)
- [<span data-ttu-id="56fa4-120">-- Operator</span><span class="sxs-lookup"><span data-stu-id="56fa4-120">-- Operator</span></span>](decrement-operator.md)
- [<span data-ttu-id="56fa4-121">Gewusst wie: Inkrementieren und Dekrementieren von Zeigern</span><span class="sxs-lookup"><span data-stu-id="56fa4-121">How to: increment and decrement pointers</span></span>](../../programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
