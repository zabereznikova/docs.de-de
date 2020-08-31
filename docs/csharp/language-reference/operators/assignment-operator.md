---
description: Zuweisungsoperatoren (C#-Referenz)
title: Zuweisungsoperatoren (C#-Referenz)
ms.date: 09/10/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 3df118143b692cc8655de31cce23af41f7da125c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89117882"
---
# <a name="assignment-operators-c-reference"></a><span data-ttu-id="5b0e2-103">Zuweisungsoperatoren (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="5b0e2-103">Assignment operators (C# reference)</span></span>

<span data-ttu-id="5b0e2-104">Der Zuweisungsoperator `=` weist den Wert seines rechtsseitigen Operanden einer Variablen, einer [Eigenschaft](../../programming-guide/classes-and-structs/properties.md) oder einem, durch seinen linksseitigen Operanden angegebenen [Indexer](../../programming-guide/indexers/index.md)-Element zu.</span><span class="sxs-lookup"><span data-stu-id="5b0e2-104">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="5b0e2-105">Das Ergebnis eines Zuweisungsausdrucks ist der Wert, der dem linksseitigen Operanden zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5b0e2-105">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="5b0e2-106">Der Typ des rechtsseitigen Operanden muss mit dem Typ des linksseitigen Operanden übereinstimmen oder implizit in ihn konvertierbar sein.</span><span class="sxs-lookup"><span data-stu-id="5b0e2-106">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="5b0e2-107">Der Zuweisungsoperator `=` ist rechtsassoziativ, d. h. ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="5b0e2-107">The assignment operator `=` is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="5b0e2-108">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="5b0e2-108">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="5b0e2-109">Das folgende Beispiel zeigt die Verwendung des Zuweisungsoperators mit einer lokalen Variablen, einer Eigenschaft und einem Indexerelement als linksseitigem Operanden:</span><span class="sxs-lookup"><span data-stu-id="5b0e2-109">The following example demonstrates the usage of the assignment operator with a local variable, a property, and an indexer element as its left-hand operand:</span></span>

[!code-csharp-interactive[simple assignment](snippets/shared/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="5b0e2-110">ref-Zuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="5b0e2-110">ref assignment operator</span></span>

<span data-ttu-id="5b0e2-111">Ab C# 7.3 können Sie mit dem ref-Zuweisungsoperator `= ref` eine [ref local](../keywords/ref.md#ref-locals)- oder [ref readonly local](../keywords/ref.md#ref-readonly-locals)-Variable neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5b0e2-111">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="5b0e2-112">Im folgenden Beispiel wird die Verwendung des ref-Zuweisungsoperators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="5b0e2-112">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](snippets/shared/AssignmentOperator.cs#RefAssignment)]

<span data-ttu-id="5b0e2-113">Im Fall des REF-Zuweisungsoperators müssen beide Operanden vom gleichen Typ sein.</span><span class="sxs-lookup"><span data-stu-id="5b0e2-113">In the case of the ref assignment operator, the both of its operands must be of the same type.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="5b0e2-114">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="5b0e2-114">Compound assignment</span></span>

<span data-ttu-id="5b0e2-115">Bei einem binären Operator `op` entspricht ein Verbundzuweisungsausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="5b0e2-115">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="5b0e2-116">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="5b0e2-116">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="5b0e2-117">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="5b0e2-117">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="5b0e2-118">Verbundzuweisungen werden von [arithmetischen](arithmetic-operators.md#compound-assignment), [logischen booleschen](boolean-logical-operators.md#compound-assignment) und [bitweisen logischen und Verschiebungs-](bitwise-and-shift-operators.md#compound-assignment)-Operatoren unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5b0e2-118">Compound assignment is supported by [arithmetic](arithmetic-operators.md#compound-assignment), [Boolean logical](boolean-logical-operators.md#compound-assignment), and [bitwise logical and shift](bitwise-and-shift-operators.md#compound-assignment) operators.</span></span>

## <a name="null-coalescing-assignment"></a><span data-ttu-id="5b0e2-119">NULL-Coalescing-Zuweisung</span><span class="sxs-lookup"><span data-stu-id="5b0e2-119">Null-coalescing assignment</span></span>

<span data-ttu-id="5b0e2-120">Sie können ab C# 8.0 den NULL-Coalescing-Zuweisungsoperator `??=` verwenden, um den Wert des rechten Operanden dem linken Operanden nur dann zuzuweisen, wenn die Auswertung des linken Operanden `null` ergibt.</span><span class="sxs-lookup"><span data-stu-id="5b0e2-120">Beginning with C# 8.0, you can use the null-coalescing assignment operator `??=` to assign the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="5b0e2-121">Weitere Informationen finden Sie im Artikel zu den Operatoren [?? und ??=](null-coalescing-operator.md).</span><span class="sxs-lookup"><span data-stu-id="5b0e2-121">For more information, see the [?? and ??= operators](null-coalescing-operator.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="5b0e2-122">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="5b0e2-122">Operator overloadability</span></span>

<span data-ttu-id="5b0e2-123">Ein benutzerdefinierter Typ kann den Zuweisungsoperator [nicht überladen](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="5b0e2-123">A user-defined type cannot [overload](operator-overloading.md) the assignment operator.</span></span> <span data-ttu-id="5b0e2-124">Ein benutzerdefinierter Typ kann jedoch eine implizite Konvertierung in einen anderen Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="5b0e2-124">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="5b0e2-125">Auf diese Weise kann der Wert eines benutzerdefinierten Typs einer Variablen, einer Eigenschaft oder einem Indexerelement eines anderen Typs zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="5b0e2-125">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="5b0e2-126">Weitere Informationen finden Sie unter [Benutzerdefinierte Konvertierungsoperatoren](user-defined-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="5b0e2-126">For more information, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

<span data-ttu-id="5b0e2-127">Ein benutzerdefinierter Typ kann einen Verbundzuweisungsoperator nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="5b0e2-127">A user-defined type cannot explicitly overload a compound assignment operator.</span></span> <span data-ttu-id="5b0e2-128">Wenn jedoch ein benutzerdefinierter Typ einen binären `op`-Operator überlädt, wird der `op=`-Operator, sofern vorhanden, ebenfalls implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="5b0e2-128">However, if a user-defined type overloads a binary operator `op`, the `op=` operator, if it exists, is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5b0e2-129">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="5b0e2-129">C# language specification</span></span>

<span data-ttu-id="5b0e2-130">Weitere Informationen finden Sie im Abschnitt [Zuweisungsoperatoren](~/_csharplang/spec/expressions.md#assignment-operators) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="5b0e2-130">For more information, see the [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="5b0e2-131">Weitere Informationen zum REF-Zuweiseungsoperator `= ref` finden Sie unter [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span><span class="sxs-lookup"><span data-stu-id="5b0e2-131">For more information about the ref assignment operator `= ref`, see the [feature proposal note](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5b0e2-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b0e2-132">See also</span></span>

- [<span data-ttu-id="5b0e2-133">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="5b0e2-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5b0e2-134">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="5b0e2-134">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="5b0e2-135">ref (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="5b0e2-135">ref keyword</span></span>](../keywords/ref.md)
