---
title: =-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 06/21/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 1277b35723777760deebb6606ddc90bd21e654ec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744116"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d68eb-102">=-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d68eb-102">= operator (C# reference)</span></span>

<span data-ttu-id="d68eb-103">Der Zuweisungsoperator `=` weist den Wert seines rechtsseitigen Operanden einer Variablen, einer [Eigenschaft](../../programming-guide/classes-and-structs/properties.md) oder einem, durch seinen linksseitigen Operanden angegebenen [Indexer](../../../csharp/programming-guide/indexers/index.md)-Element zu.</span><span class="sxs-lookup"><span data-stu-id="d68eb-103">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../../csharp/programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="d68eb-104">Das Ergebnis eines Zuweisungsausdrucks ist der Wert, der dem linksseitigen Operanden zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d68eb-104">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="d68eb-105">Der Typ des rechtsseitigen Operanden muss mit dem Typ des linksseitigen Operanden übereinstimmen oder implizit in ihn konvertierbar sein.</span><span class="sxs-lookup"><span data-stu-id="d68eb-105">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="d68eb-106">Der Zuweisungsoperator rechtsassoziativ, d.h. ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="d68eb-106">The assignment operator is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="d68eb-107">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="d68eb-107">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="d68eb-108">Das folgende Beispiel zeigt die Verwendung des Zuweisungsoperators mit einer lokalen Variablen, einer Eigenschaft und einem Indexerelement als linksseitigem Operanden:</span><span class="sxs-lookup"><span data-stu-id="d68eb-108">The following example demonstrates the usage of the assignment operator with a local variable, a property, and an indexer element as its left-hand operand:</span></span>

[!code-csharp-interactive[simple assignment](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="d68eb-109">ref-Zuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="d68eb-109">ref assignment operator</span></span>

<span data-ttu-id="d68eb-110">Ab C# 7.3 können Sie mit dem ref-Zuweisungsoperator `= ref` eine [ref local](../keywords/ref.md#ref-locals)- oder [ref readonly local](../keywords/ref.md#ref-readonly-locals)-Variable neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d68eb-110">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="d68eb-111">Im folgenden Beispiel wird die Verwendung des ref-Zuweisungsoperators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="d68eb-111">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#RefAssignment)]

<span data-ttu-id="d68eb-112">Im Fall des ref-Zuweisungsoperators muss der Typ beider Operanden identisch sein.</span><span class="sxs-lookup"><span data-stu-id="d68eb-112">In the case of the ref assignment operator, the type of both its operands must be the same.</span></span>

<span data-ttu-id="d68eb-113">Weitere Informationen finden Sie unter [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span><span class="sxs-lookup"><span data-stu-id="d68eb-113">For more information, see the [feature proposal note](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="d68eb-114">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="d68eb-114">Compound assignment</span></span>

<span data-ttu-id="d68eb-115">Bei einem binären Operator `op` entspricht ein Verbundzuweisungsausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="d68eb-115">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="d68eb-116">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="d68eb-116">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="d68eb-117">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="d68eb-117">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="d68eb-118">Verbundzuweisungen werden von [arithmetischen](arithmetic-operators.md#compound-assignment), [logischen booleschen](boolean-logical-operators.md#compound-assignment) und [bitweisen logischen und Verschiebungs-](bitwise-and-shift-operators.md#compound-assignment)-Operatoren unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d68eb-118">Compound assignment is supported by [arithmetic](arithmetic-operators.md#compound-assignment), [Boolean logical](boolean-logical-operators.md#compound-assignment), and [bitwise logical and shift](bitwise-and-shift-operators.md#compound-assignment) operators.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="d68eb-119">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="d68eb-119">Operator overloadability</span></span>

<span data-ttu-id="d68eb-120">Ein benutzerdefinierter Typ kann den Zuweisungsoperator nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="d68eb-120">A user-defined type cannot overload the assignment operator.</span></span> <span data-ttu-id="d68eb-121">Ein benutzerdefinierter Typ kann jedoch eine implizite Konvertierung in einen anderen Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="d68eb-121">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="d68eb-122">Auf diese Weise kann der Wert eines benutzerdefinierten Typs einer Variablen, einer Eigenschaft oder einem Indexerelement eines anderen Typs zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="d68eb-122">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="d68eb-123">Weitere Informationen finden Sie unter [Benutzerdefinierte Konvertierungsoperatoren](user-defined-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="d68eb-123">For more information, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d68eb-124">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="d68eb-124">C# language specification</span></span>

<span data-ttu-id="d68eb-125">Weitere Informationen finden Sie im Abschnitt [Zuweisungsoperatoren](~/_csharplang/spec/expressions.md#assignment-operators) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="d68eb-125">For more information, see the [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d68eb-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d68eb-126">See also</span></span>

- [<span data-ttu-id="d68eb-127">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d68eb-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d68eb-128">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="d68eb-128">C# operators</span></span>](index.md)
- [<span data-ttu-id="d68eb-129">ref (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d68eb-129">ref keyword</span></span>](../keywords/ref.md)
