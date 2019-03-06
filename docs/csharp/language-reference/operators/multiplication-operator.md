---
title: '* -Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: a5e120d26614f1e38cc2f2db02949552140b594e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977343"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="9ec01-102">\*-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9ec01-102">\* operator (C# Reference)</span></span>

<span data-ttu-id="9ec01-103">Der Operator `*` wird in zwei Formen unterstützt: als unärer Zeigerdereferenzierungsoperator oder als binärer Multiplikationsoperator.</span><span class="sxs-lookup"><span data-stu-id="9ec01-103">The `*` operator is supported in two forms: a unary pointer indirection operator or a binary multiplication operator.</span></span>

## <a name="pointer-indirection-operator"></a><span data-ttu-id="9ec01-104">Zeigerdereferenzierungsoperator</span><span class="sxs-lookup"><span data-stu-id="9ec01-104">Pointer indirection operator</span></span>

<span data-ttu-id="9ec01-105">Verwenden Sie den unären `*`-Operator, um die Variable zu erhalten, auf die ein Operand vom Typ „Zeiger“ verweist.</span><span class="sxs-lookup"><span data-stu-id="9ec01-105">Use the unary `*` operator to obtain the variable to which an operand of a pointer type points.</span></span> <span data-ttu-id="9ec01-106">Weitere Informationen finden Sie unter [Gewusst wie: Abrufen des Werts einer Zeigervariablen](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md).</span><span class="sxs-lookup"><span data-stu-id="9ec01-106">For more information, see [How to: obtain the value of a pointer variable](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md).</span></span>

<span data-ttu-id="9ec01-107">Der Zeigerdereferenzierungsoperator `*` erfordert einen [unsicheren](../keywords/unsafe.md) Kontext.</span><span class="sxs-lookup"><span data-stu-id="9ec01-107">The pointer indirection operator `*` requires [unsafe](../keywords/unsafe.md) context.</span></span>

## <a name="multiplication-operator"></a><span data-ttu-id="9ec01-108">Multiplikationsoperator</span><span class="sxs-lookup"><span data-stu-id="9ec01-108">Multiplication operator</span></span>

<span data-ttu-id="9ec01-109">Für numerische Typen berechnet der `*`-Operator das Produkt seiner Operanden:</span><span class="sxs-lookup"><span data-stu-id="9ec01-109">For numeric types, the `*` operator computes the product of its operands:</span></span>

[!code-csharp-interactive[multiplication](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#Multiply)]

## <a name="operator-overloadability"></a><span data-ttu-id="9ec01-110">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="9ec01-110">Operator overloadability</span></span>

<span data-ttu-id="9ec01-111">Benutzerdefinierte Typen können einen binären `*`-Operator [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="9ec01-111">User-defined types can [overload](../keywords/operator.md) a binary `*` operator.</span></span> <span data-ttu-id="9ec01-112">Wenn ein binärer `*`-Operator überladen ist, wird der [Multiplikationszuweisungsoperator](multiplication-assignment-operator.md) `*=`auch implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="9ec01-112">When a binary `*` operator is overloaded, the [multiplication assignment operator](multiplication-assignment-operator.md) `*=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9ec01-113">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="9ec01-113">C# language specification</span></span>

<span data-ttu-id="9ec01-114">Weitere Informationen finden Sie unter [C#-Sprachspezifikation](../language-specification/index.md) in den Abschnitten [Zeigerdereferenzierung](~/_csharplang/spec/unsafe-code.md#pointer-indirection) und [Multiplikationsoperator](~/_csharplang/spec/expressions.md#multiplication-operator).</span><span class="sxs-lookup"><span data-stu-id="9ec01-114">For more information, see the [Pointer indirection](~/_csharplang/spec/unsafe-code.md#pointer-indirection) and [Multiplication operator](~/_csharplang/spec/expressions.md#multiplication-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9ec01-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ec01-115">See also</span></span>

- [<span data-ttu-id="9ec01-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="9ec01-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9ec01-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9ec01-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9ec01-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="9ec01-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="9ec01-119">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="9ec01-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)