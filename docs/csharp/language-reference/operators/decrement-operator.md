---
title: Operator -- (C#-Referenz)
ms.date: 11/26/2018
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
ms.openlocfilehash: 0858321d6fe192a55bc548f169c558542238a981
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153335"
---
# <a name="---operator-c-reference"></a><span data-ttu-id="126ad-102">Operator -- (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="126ad-102">-- Operator (C# Reference)</span></span>

<span data-ttu-id="126ad-103">Der unäre Dekrementoperator `--` verringert seinen Operanden um 1.</span><span class="sxs-lookup"><span data-stu-id="126ad-103">The unary decrement operator `--` decrements its operand by 1.</span></span> <span data-ttu-id="126ad-104">Er wird in zwei Formen unterstützt: der Postfix-Dekrementoperator `x--` und der Präfix-Dekrementoperator `--x`.</span><span class="sxs-lookup"><span data-stu-id="126ad-104">It's supported in two forms: the postfix decrement operator, `x--`, and the prefix decrement operator, `--x`.</span></span>

## <a name="postfix-decrement-operator"></a><span data-ttu-id="126ad-105">Postfix-Operator für Dekrement</span><span class="sxs-lookup"><span data-stu-id="126ad-105">Postfix decrement operator</span></span>

<span data-ttu-id="126ad-106">Das Ergebnis von `x--` ist der Wert von `x`  *vor* dem Vorgang, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="126ad-106">The result of `x--` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix decrement](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PostfixDecrement)]

## <a name="prefix-decrement-operator"></a><span data-ttu-id="126ad-107">Präfix-Dekrementoperator</span><span class="sxs-lookup"><span data-stu-id="126ad-107">Prefix decrement operator</span></span>

<span data-ttu-id="126ad-108">Das Ergebnis von `--x` ist der Wert von `x`  *nach* dem Vorgang, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="126ad-108">The result of `--x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix decrement](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PrefixDecrement)]

## <a name="remarks"></a><span data-ttu-id="126ad-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="126ad-109">Remarks</span></span>

<span data-ttu-id="126ad-110">Der Dekrementoperator ist für alle [integralen Datentypen](../keywords/integral-types-table.md) (einschließlich [char](../keywords/char.md)-Typ), [Gleitkommatypen](../keywords/floating-point-types-table.md), und alle [Enumerationstypen](../keywords/enum.md) vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="126ad-110">The decrement operator is predefined for all [integral types](../keywords/integral-types-table.md) (including the [char](../keywords/char.md) type), [floating-point types](../keywords/floating-point-types-table.md), and any [enum](../keywords/enum.md) type.</span></span>

<span data-ttu-id="126ad-111">Ein Operand des Dekrementoperators muss eine Variable, ein [Eigenschaftenzugriff](../../programming-guide/classes-and-structs/properties.md) oder ein [Indexzugriff](../../../csharp/programming-guide/indexers/index.md) sein.</span><span class="sxs-lookup"><span data-stu-id="126ad-111">An operand of the decrement operator must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../../csharp/programming-guide/indexers/index.md) access.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="126ad-112">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="126ad-112">Operator overloadability</span></span>

<span data-ttu-id="126ad-113">Benutzerdefinierte Typen können den Operator `--` [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="126ad-113">User-defined types can [overload](../keywords/operator.md) the `--` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="126ad-114">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="126ad-114">C# language specification</span></span>

<span data-ttu-id="126ad-115">Weitere Informationen finden Sie in den Abschnitten [Postfix-Inkrement- und Dekrementoperatoren](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) und [Präfix-Inkrement- und Dekrementoperatoren](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="126ad-115">For more information, see the [Postfix increment and decrement operators](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) and [Prefix increment and decrement operators](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="126ad-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="126ad-116">See also</span></span>

- [<span data-ttu-id="126ad-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="126ad-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="126ad-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="126ad-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="126ad-119">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="126ad-119">C# Operators</span></span>](index.md)
- [<span data-ttu-id="126ad-120">++-Operator</span><span class="sxs-lookup"><span data-stu-id="126ad-120">++ Operator</span></span>](increment-operator.md)
- [<span data-ttu-id="126ad-121">Gewusst wie: Inkrementieren und Dekrementieren von Zeigern</span><span class="sxs-lookup"><span data-stu-id="126ad-121">How to: increment and decrement pointers</span></span>](../../programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
