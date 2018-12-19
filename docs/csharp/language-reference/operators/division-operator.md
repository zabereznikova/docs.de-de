---
title: /-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 12/13/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: 45bcd64b60e7d13f389064faefeda815ea1f32c9
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286532"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="7c71c-102">Operator / (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7c71c-102">/ Operator (C# Reference)</span></span>

<span data-ttu-id="7c71c-103">Der Divisionsoperator `/` dividiert den ersten Operanden durch den zweiten Operanden.</span><span class="sxs-lookup"><span data-stu-id="7c71c-103">The division operator `/` divides its first operand by its second operand.</span></span> <span data-ttu-id="7c71c-104">Alle numerischen Typen unterstützen den Divisionsoperator.</span><span class="sxs-lookup"><span data-stu-id="7c71c-104">All numeric types support the division operator.</span></span>

## <a name="integer-division"></a><span data-ttu-id="7c71c-105">Ganzzahldivision</span><span class="sxs-lookup"><span data-stu-id="7c71c-105">Integer division</span></span>

<span data-ttu-id="7c71c-106">Für die Operanden von Ganzzahltypen weist das Ergebnis des `/`-Operators einen Ganzzahltyp auf und ist gleich dem Quotienten der beiden Operanden, gerundet auf Null:</span><span class="sxs-lookup"><span data-stu-id="7c71c-106">For the operands of integer types, the result of the `/` operator is of an integer type and equals the quotient of the two operands rounded towards zero:</span></span>

[!code-csharp-interactive[integer division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#Integer)]

<span data-ttu-id="7c71c-107">Um den Quotienten der beiden Operanden als Gleitkommazahl abzurufen, verwenden Sie den Typ `float`, `double` oder `decimal`:</span><span class="sxs-lookup"><span data-stu-id="7c71c-107">To obtain the quotient of the two operands as a floating-point number, use the `float`, `double`, or `decimal` type:</span></span>

[!code-csharp-interactive[integer as floating-point division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#IntegerAsFloatingPoint)]

## <a name="floating-point-division"></a><span data-ttu-id="7c71c-108">Gleitkommadivision</span><span class="sxs-lookup"><span data-stu-id="7c71c-108">Floating-point division</span></span>

<span data-ttu-id="7c71c-109">Für die Typen `float`, `double` oder `decimal` ist das Ergebnis des `/`-Operators der Quotient der beiden Operanden:</span><span class="sxs-lookup"><span data-stu-id="7c71c-109">For the `float`, `double`, and `decimal` types, the result of the `/` operator is the quotient of the two operands:</span></span>

[!code-csharp-interactive[floating-point division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#FloatingPoint)]

<span data-ttu-id="7c71c-110">Wenn einer der Operanden `decimal` lautet, kann ein anderer Operand weder `float` noch `double` sein, weil weder `float` noch `double` implizit zu `decimal` konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="7c71c-110">If one of the operands is `decimal`, another operand can be neither `float` nor `double`, because neither `float` nor `double` is implicitly convertible to `decimal`.</span></span> <span data-ttu-id="7c71c-111">Sie müssen den Operanden `float` oder `double` explizit zum Typ `decimal` konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7c71c-111">You must explicitly convert the `float` or `double` operand to the `decimal` type.</span></span> <span data-ttu-id="7c71c-112">Weitere Informationen zu impliziten Konvertierungen zwischen numerischen Typen finden Sie unter [Tabelle für implizite numerische Konvertierungen](../keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="7c71c-112">For more information about implicit conversions between numeric types, see [Implicit numeric conversions table](../keywords/implicit-numeric-conversions-table.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="7c71c-113">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="7c71c-113">Operator overloadability</span></span>

<span data-ttu-id="7c71c-114">Benutzerdefinierte Typen können den Operator `/` [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="7c71c-114">User-defined types can [overload](../keywords/operator.md) the `/` operator.</span></span> <span data-ttu-id="7c71c-115">Wenn der `/`-Operator überladen ist, wird der [Divisionszuweisungsoperator](division-assignment-operator.md) `/=` auch implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="7c71c-115">When the `/` operator is overloaded, the [division assignment operator](division-assignment-operator.md) `/=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7c71c-116">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="7c71c-116">C# language specification</span></span>

<span data-ttu-id="7c71c-117">Weitere Informationen finden Sie im Abschnitt [Divisionsoperator](~/_csharplang/spec/expressions.md#division-operator) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="7c71c-117">For more information, see the [Division operator](~/_csharplang/spec/expressions.md#division-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7c71c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c71c-118">See also</span></span>

- [<span data-ttu-id="7c71c-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="7c71c-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7c71c-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7c71c-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7c71c-121">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="7c71c-121">C# Operators</span></span>](index.md)
- [<span data-ttu-id="7c71c-122">%-Operator</span><span class="sxs-lookup"><span data-stu-id="7c71c-122">% Operator</span></span>](remainder-operator.md)
