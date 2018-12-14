---
title: Operator = (C#-Referenz)
ms.date: 11/26/2018
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 123674f37d17db6dcfe6ae9d45c7176bdff1eda7
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149223"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="22b72-102">Operator = (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="22b72-102">= Operator (C# Reference)</span></span>

<span data-ttu-id="22b72-103">Der Zuweisungsoperator `=` weist den Wert seines rechtsseitigen Operanden einer Variablen, einer [Eigenschaft](../../programming-guide/classes-and-structs/properties.md) oder einem, durch seinen linksseitigen Operanden angegebenen [Indexer](../../../csharp/programming-guide/indexers/index.md)-Element zu.</span><span class="sxs-lookup"><span data-stu-id="22b72-103">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../../csharp/programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="22b72-104">Das Ergebnis eines Zuweisungsausdrucks ist der Wert, der dem linksseitigen Operanden zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="22b72-104">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="22b72-105">Der Typ des rechtsseitigen Operanden muss mit dem Typ des linksseitigen Operanden übereinstimmen oder implizit in ihn konvertierbar sein.</span><span class="sxs-lookup"><span data-stu-id="22b72-105">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="22b72-106">Der Zuweisungsoperator rechtsassoziativ, d.h. ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="22b72-106">The assignment operator is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="22b72-107">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="22b72-107">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="22b72-108">Das folgende Beispiel zeigt die Verwendung des Zuweisungsoperators, um einer lokalen Variablen, einer Eigenschaft und einem Indexerelement Werte zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="22b72-108">The following example demonstrates the usage of the assignment operator to assign values to a local variable, a property, and an indexer element:</span></span>

[!code-csharp-interactive[assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#Assignments)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="22b72-109">ref-Zuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="22b72-109">ref assignment operator</span></span>

<span data-ttu-id="22b72-110">Ab C# 7.3 können Sie mit dem ref-Zuweisungsoperator `= ref` eine [ref local](../keywords/ref.md#ref-locals)- oder [ref readonly local](../keywords/ref.md#ref-readonly-locals)-Variable neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="22b72-110">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="22b72-111">Im folgenden Beispiel wird die Verwendung des ref-Zuweisungsoperators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="22b72-111">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#RefAssignment)]

<span data-ttu-id="22b72-112">Im Fall des ref-Zuweisungsoperators der Typ des linken und des rechten Operanden identisch sein.</span><span class="sxs-lookup"><span data-stu-id="22b72-112">In the case of the ref assignment operator, the type of the left operand and the right operand must be the same.</span></span>

<span data-ttu-id="22b72-113">Weitere Informationen finden Sie unter [Hinweis zum Featurevorschlag](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.3/ref-local-reassignment.md).</span><span class="sxs-lookup"><span data-stu-id="22b72-113">For more information, see the [feature proposal note](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="22b72-114">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="22b72-114">Operator overloadability</span></span>

<span data-ttu-id="22b72-115">Ein benutzerdefinierter Typ kann den Zuweisungsoperator nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="22b72-115">A user-defined type cannot overload the assignment operator.</span></span> <span data-ttu-id="22b72-116">Ein benutzerdefinierter Typ kann jedoch eine implizite Konvertierung in einen anderen Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="22b72-116">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="22b72-117">Auf diese Weise kann der Wert eines benutzerdefinierten Typs einer Variablen, einer Eigenschaft oder einem Indexerelement eines anderen Typs zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="22b72-117">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="22b72-118">Weitere Informationen finden Sie im Artikel [Schlüsselwort „implicit“](../keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="22b72-118">For more information, see the [implicit](../keywords/implicit.md) keyword article.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="22b72-119">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="22b72-119">C# language specification</span></span>

<span data-ttu-id="22b72-120">Weitere Informationen finden Sie im Abschnitt [Einfache Zuweisung](~/_csharplang/spec/expressions.md#simple-assignment) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="22b72-120">For more information, see the [Simple assignment](~/_csharplang/spec/expressions.md#simple-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="22b72-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22b72-121">See also</span></span>

- [<span data-ttu-id="22b72-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="22b72-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="22b72-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="22b72-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="22b72-124">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="22b72-124">C# Operators</span></span>](index.md)
- [<span data-ttu-id="22b72-125">ref (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="22b72-125">ref keyword</span></span>](../keywords/ref.md)
