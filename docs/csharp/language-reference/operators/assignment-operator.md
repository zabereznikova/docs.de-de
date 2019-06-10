---
title: =-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 85182acb84ea79cb00a9edb315c3954f440305f4
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758354"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="39f1b-102">Operator = (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="39f1b-102">= Operator (C# Reference)</span></span>

<span data-ttu-id="39f1b-103">Der Zuweisungsoperator `=` weist den Wert seines rechtsseitigen Operanden einer Variablen, einer [Eigenschaft](../../programming-guide/classes-and-structs/properties.md) oder einem, durch seinen linksseitigen Operanden angegebenen [Indexer](../../../csharp/programming-guide/indexers/index.md)-Element zu.</span><span class="sxs-lookup"><span data-stu-id="39f1b-103">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../../csharp/programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="39f1b-104">Das Ergebnis eines Zuweisungsausdrucks ist der Wert, der dem linksseitigen Operanden zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="39f1b-104">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="39f1b-105">Der Typ des rechtsseitigen Operanden muss mit dem Typ des linksseitigen Operanden übereinstimmen oder implizit in ihn konvertierbar sein.</span><span class="sxs-lookup"><span data-stu-id="39f1b-105">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="39f1b-106">Der Zuweisungsoperator rechtsassoziativ, d.h. ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="39f1b-106">The assignment operator is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="39f1b-107">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="39f1b-107">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="39f1b-108">Das folgende Beispiel zeigt die Verwendung des Zuweisungsoperators, um einer lokalen Variablen, einer Eigenschaft und einem Indexerelement Werte zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="39f1b-108">The following example demonstrates the usage of the assignment operator to assign values to a local variable, a property, and an indexer element:</span></span>

[!code-csharp-interactive[assignment operator](~/samples/csharp/language-reference/operators/AssignmentExamples.cs#Assignments)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="39f1b-109">ref-Zuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="39f1b-109">ref assignment operator</span></span>

<span data-ttu-id="39f1b-110">Ab C# 7.3 können Sie mit dem ref-Zuweisungsoperator `= ref` eine [ref local](../keywords/ref.md#ref-locals)- oder [ref readonly local](../keywords/ref.md#ref-readonly-locals)-Variable neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="39f1b-110">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="39f1b-111">Im folgenden Beispiel wird die Verwendung des ref-Zuweisungsoperators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="39f1b-111">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](~/samples/csharp/language-reference/operators/AssignmentExamples.cs#RefAssignment)]

<span data-ttu-id="39f1b-112">Im Fall des ref-Zuweisungsoperators der Typ des linken und des rechten Operanden identisch sein.</span><span class="sxs-lookup"><span data-stu-id="39f1b-112">In the case of the ref assignment operator, the type of the left operand and the right operand must be the same.</span></span>

<span data-ttu-id="39f1b-113">Weitere Informationen finden Sie unter [Hinweis zum Featurevorschlag](../../../../_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span><span class="sxs-lookup"><span data-stu-id="39f1b-113">For more information, see the [feature proposal note](../../../../_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="39f1b-114">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="39f1b-114">Operator overloadability</span></span>

<span data-ttu-id="39f1b-115">Ein benutzerdefinierter Typ kann den Zuweisungsoperator nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="39f1b-115">A user-defined type cannot overload the assignment operator.</span></span> <span data-ttu-id="39f1b-116">Ein benutzerdefinierter Typ kann jedoch eine implizite Konvertierung in einen anderen Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="39f1b-116">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="39f1b-117">Auf diese Weise kann der Wert eines benutzerdefinierten Typs einer Variablen, einer Eigenschaft oder einem Indexerelement eines anderen Typs zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="39f1b-117">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="39f1b-118">Weitere Informationen finden Sie im Artikel [Schlüsselwort „implicit“](../keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="39f1b-118">For more information, see the [implicit](../keywords/implicit.md) keyword article.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="39f1b-119">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="39f1b-119">C# language specification</span></span>

<span data-ttu-id="39f1b-120">Weitere Informationen finden Sie im Abschnitt [Einfache Zuweisung](~/_csharplang/spec/expressions.md#simple-assignment) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="39f1b-120">For more information, see the [Simple assignment](~/_csharplang/spec/expressions.md#simple-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="39f1b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39f1b-121">See also</span></span>

- [<span data-ttu-id="39f1b-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="39f1b-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="39f1b-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="39f1b-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="39f1b-124">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="39f1b-124">C# Operators</span></span>](index.md)
- [<span data-ttu-id="39f1b-125">ref (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="39f1b-125">ref keyword</span></span>](../keywords/ref.md)
