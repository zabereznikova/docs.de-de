---
title: ()-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 01/15/2019
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 8f7382a49c81b6fd8e104b864ffc2f70db7fe4a6
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758111"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="0e3c9-102">()-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0e3c9-102">() operator (C# Reference)</span></span>

<span data-ttu-id="0e3c9-103">Klammern „`()`“ werden in der Regel für den Methoden- oder Delegataufruf oder in Cast-Ausdrücken verwendet.</span><span class="sxs-lookup"><span data-stu-id="0e3c9-103">Parentheses, `()`, are typically used for method or delegate invocation or in cast expressions.</span></span>

<span data-ttu-id="0e3c9-104">Mit Klammern geben Sie auch die Reihenfolge an, in der Vorgänge in einem Ausdruck ausgewertet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0e3c9-104">You also use parentheses to specify the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="0e3c9-105">Weitere Informationen finden Sie im Abschnitt [Hinzufügen von Klammern](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) des Artikels [Operatoren (C#-Programmierhandbuch)](../../programming-guide/statements-expressions-operators/operators.md).</span><span class="sxs-lookup"><span data-stu-id="0e3c9-105">For more information, see the [Adding parentheses](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) section of the [Operators](../../programming-guide/statements-expressions-operators/operators.md) article.</span></span> <span data-ttu-id="0e3c9-106">Die Liste der Operatoren ist nach der Rangfolge sortiert, siehe [C#-Operatoren](index.md).</span><span class="sxs-lookup"><span data-stu-id="0e3c9-106">For the list of operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="method-invocation"></a><span data-ttu-id="0e3c9-107">Methodenaufruf</span><span class="sxs-lookup"><span data-stu-id="0e3c9-107">Method invocation</span></span>

<span data-ttu-id="0e3c9-108">Im folgenden Beispiel wird der Aufruf einer Methode mit oder ohne Argumente sowie eines Delegaten veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="0e3c9-108">The following example demonstrates how to invoke a method, with or without arguments, and a delegate:</span></span>

[!code-csharp-interactive[use for invocation](~/samples/csharp/language-reference/operators/InvocationOperatorExamples.cs#Invocation)]

<span data-ttu-id="0e3c9-109">Klammern verwenden Sie auch beim Aufrufen eines [Konstruktors](../../programming-guide/classes-and-structs/constructors.md) mit einem [ `new` ](../keywords/new-operator.md)-Operator.</span><span class="sxs-lookup"><span data-stu-id="0e3c9-109">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with a [`new`](../keywords/new-operator.md) operator.</span></span>

<span data-ttu-id="0e3c9-110">Weitere Informationen über Methoden finden Sie unter [Methoden](../../programming-guide/classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="0e3c9-110">For more information about methods, see [Methods](../../programming-guide/classes-and-structs/methods.md).</span></span> <span data-ttu-id="0e3c9-111">Weitere Informationen über Delegaten finden Sie unter [Delegaten](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="0e3c9-111">For more information about delegates, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="cast-expression"></a><span data-ttu-id="0e3c9-112">Cast-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="0e3c9-112">Cast expression</span></span>

<span data-ttu-id="0e3c9-113">Ein Cast-Ausdruck der Form `(T)E` ruft einen Konvertierungsoperator zum Konvertieren des Werts des Ausdrucks `E` in Typ `T` auf.</span><span class="sxs-lookup"><span data-stu-id="0e3c9-113">A cast expression of the form `(T)E` invokes a conversion operator to convert the value of expression `E` to type `T`.</span></span> <span data-ttu-id="0e3c9-114">Wenn keine explizite Konvertierung von Typ `E` in Typ `T` möglich ist, tritt ein Fehler während der Kompilierung auf.</span><span class="sxs-lookup"><span data-stu-id="0e3c9-114">If no explicit conversion exists from the type of `E` to type `T`, a compile-time error occurs.</span></span> <span data-ttu-id="0e3c9-115">Weitere Informationen zum Definieren von Konvertierungsoperatoren finden Sie in den Schlüsselwortartikeln [explicit (C#-Referenz)](../keywords/explicit.md) und [implicit (C#-Referenz)](../keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="0e3c9-115">For information about how to define a conversion operator, see the [explicit](../keywords/explicit.md) and [implicit](../keywords/implicit.md) keyword articles.</span></span>

<span data-ttu-id="0e3c9-116">Das folgende Beispiel veranschaulicht die Typenkonvertierung zwischen numerischen Typen:</span><span class="sxs-lookup"><span data-stu-id="0e3c9-116">The following example demonstrates type conversion between numeric types:</span></span>

[!code-csharp-interactive[use for cast](~/samples/csharp/language-reference/operators/InvocationOperatorExamples.cs#Cast)]

<span data-ttu-id="0e3c9-117">Weitere Informationen zu vordefinierten expliziten Konvertierungen zwischen numerischen Typen finden Sie unter [Tabelle für explizite numerische Konvertierungen](../keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="0e3c9-117">For more information about predefined explicit conversions between numeric types, see [Explicit numeric conversions table](../keywords/explicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="0e3c9-118">Weitere Informationen finden Sie unter [Umwandlung und Typkonvertierungen (C#-Programmierhandbuch)](../../programming-guide/types/casting-and-type-conversions.md) und [Konvertierungsoperatoren (C#-Programmierhandbuch)](../../programming-guide/statements-expressions-operators/conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="0e3c9-118">For more information, see [Casting and type conversions](../../programming-guide/types/casting-and-type-conversions.md) and [Conversion operators](../../programming-guide/statements-expressions-operators/conversion-operators.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="0e3c9-119">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="0e3c9-119">Operator overloadability</span></span>

<span data-ttu-id="0e3c9-120">Der Operator `()` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="0e3c9-120">The operator `()` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0e3c9-121">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="0e3c9-121">C# language specification</span></span>

<span data-ttu-id="0e3c9-122">Weitere Informationen finden Sie in den Abschnitten [Aufrufausdrücke](~/_csharplang/spec/expressions.md#invocation-expressions) und [CAST-Ausdrücke](~/_csharplang/spec/expressions.md#cast-expressions) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="0e3c9-122">For more information, see the [Invocation expressions](~/_csharplang/spec/expressions.md#invocation-expressions) and [Cast expressions](~/_csharplang/spec/expressions.md#cast-expressions) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0e3c9-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e3c9-123">See also</span></span>

- [<span data-ttu-id="0e3c9-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="0e3c9-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0e3c9-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0e3c9-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0e3c9-126">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="0e3c9-126">C# Operators</span></span>](index.md)
