---
description: new-Operator – C#-Referenz
title: new-Operator – C#-Referenz
ms.date: 10/02/2020
f1_keywords:
- new_CSharpKeyword
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 3125f3d2c694dcfc5682ee482f3f76072ac3726d
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609381"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="8688c-103">new-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="8688c-103">new operator (C# reference)</span></span>

<span data-ttu-id="8688c-104">Der `new`-Operator erstellt eine neue Instanz eines Typs.</span><span class="sxs-lookup"><span data-stu-id="8688c-104">The `new` operator creates a new instance of a type.</span></span>

<span data-ttu-id="8688c-105">Sie können das Schlüsselwort `new` auch als einen [Memberdeklarationsmodifizierer](../keywords/new-modifier.md) oder als [Einschränkung eines generischen Typs](../keywords/new-constraint.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="8688c-105">You can also use the `new` keyword as a [member declaration modifier](../keywords/new-modifier.md) or a [generic type constraint](../keywords/new-constraint.md).</span></span>

## <a name="constructor-invocation"></a><span data-ttu-id="8688c-106">Konstruktoraufruf</span><span class="sxs-lookup"><span data-stu-id="8688c-106">Constructor invocation</span></span>

<span data-ttu-id="8688c-107">Um eine neue Instanz eines Typs zu erstellen, rufen Sie in der Regel einen der [Konstruktoren](../../programming-guide/classes-and-structs/constructors.md) dieses Typs mit dem `new`-Operator auf:</span><span class="sxs-lookup"><span data-stu-id="8688c-107">To create a new instance of a type, you typically invoke one of the [constructors](../../programming-guide/classes-and-structs/constructors.md) of that type using the `new` operator:</span></span>

[!code-csharp-interactive[invoke constructor](snippets/shared/NewOperator.cs#Constructor)]

<span data-ttu-id="8688c-108">Sie können einen [Objekt- oder Auflistungsinitialisierer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) mit dem `new`-Operator verwenden, um ein Objekt in einer Anweisung zu instanziieren und zu initialisieren, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="8688c-108">You can use an [object or collection initializer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) with the `new` operator to instantiate and initialize an object in one statement, as the following example shows:</span></span>

[!code-csharp-interactive[constructor with initializer](snippets/shared/NewOperator.cs#ConstructorWithInitializer)]

<span data-ttu-id="8688c-109">Ab C# 9.0 sind Konstruktoraufforderungsausdrücke als Ziel typisiert.</span><span class="sxs-lookup"><span data-stu-id="8688c-109">Beginning with C# 9.0, constructor invocation expressions are target-typed.</span></span> <span data-ttu-id="8688c-110">Das heißt, wenn der Zieltyp eines Ausdrucks bekannt ist, können Sie einen Typnamen wie im folgenden Beispiel weglassen:</span><span class="sxs-lookup"><span data-stu-id="8688c-110">That is, if a target type of an expression is known, you can omit a type name, as the following example shows:</span></span>

:::code language="csharp" source="snippets/shared/NewOperator.cs" id="SnippetTargetTyped":::

<span data-ttu-id="8688c-111">Wie das vorherige Beispiel zeigt, verwenden Sie immer Klammern in einem zieltypisierten `new`-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8688c-111">As the preceding example shows, you always use parentheses in a target-typed `new` expression.</span></span>

<span data-ttu-id="8688c-112">Wenn der Zieltyp eines `new`-Ausdrucks unbekannt ist (beispielsweise, wenn Sie das Schlüsselwort [`var`](../keywords/var.md) verwenden), müssen Sie einen Typnamen angeben.</span><span class="sxs-lookup"><span data-stu-id="8688c-112">If a target type of a `new` expression is unknown (for example, when you use the [`var`](../keywords/var.md) keyword), you must specify a type name.</span></span>

## <a name="array-creation"></a><span data-ttu-id="8688c-113">Arrayerstellung</span><span class="sxs-lookup"><span data-stu-id="8688c-113">Array creation</span></span>

<span data-ttu-id="8688c-114">Sie können den `new`-Operator auch verwenden, um eine Arrayinstanz zu erstellen, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="8688c-114">You also use the `new` operator to create an array instance, as the following example shows:</span></span>

[!code-csharp-interactive[create array](snippets/shared/NewOperator.cs#Array)]

<span data-ttu-id="8688c-115">Verwenden Sie die Arrayinitialisierungssyntax, um eine Arrayinstanz zu erstellen und sie mit Elementen in einer Anweisung zu auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="8688c-115">Use array initialization syntax to create an array instance and populate it with elements in one statement.</span></span> <span data-ttu-id="8688c-116">Im folgenden Beispiel werden verschiedene Möglichkeiten dafür veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="8688c-116">The following example shows various ways how you can do that:</span></span>

[!code-csharp-interactive[initialize array](snippets/shared/NewOperator.cs#ArrayInitialization)]

<span data-ttu-id="8688c-117">Weitere Informationen zu Arrays finden Sie unter [Arrays](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="8688c-117">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

## <a name="instantiation-of-anonymous-types"></a><span data-ttu-id="8688c-118">Instanziierung von anonymen Typen</span><span class="sxs-lookup"><span data-stu-id="8688c-118">Instantiation of anonymous types</span></span>

<span data-ttu-id="8688c-119">Um eine Instanz eines [anonymen Typs](../../programming-guide/classes-and-structs/anonymous-types.md) zu erstellen, verwenden Sie die Syntax für die Initialisierung von `new`-Operatoren und -Objekten:</span><span class="sxs-lookup"><span data-stu-id="8688c-119">To create an instance of an [anonymous type](../../programming-guide/classes-and-structs/anonymous-types.md), use the `new` operator and object initializer syntax:</span></span>

[!code-csharp-interactive[anonymous type](snippets/shared/NewOperator.cs#AnonymousType)]

## <a name="destruction-of-type-instances"></a><span data-ttu-id="8688c-120">Zerstörung von Typinstanzen</span><span class="sxs-lookup"><span data-stu-id="8688c-120">Destruction of type instances</span></span>

<span data-ttu-id="8688c-121">Sie müssen keine zuvor angelegten Typinstanzen zerstören.</span><span class="sxs-lookup"><span data-stu-id="8688c-121">You don't have to destroy earlier created type instances.</span></span> <span data-ttu-id="8688c-122">Instanzen sowohl von Verweis- als auch von Werttypen werden automatisch zerstört.</span><span class="sxs-lookup"><span data-stu-id="8688c-122">Instances of both reference and value types are destroyed automatically.</span></span> <span data-ttu-id="8688c-123">Instanzen von Werttypen werden zerstört, sobald der sie enthaltende Kontext zerstört wird.</span><span class="sxs-lookup"><span data-stu-id="8688c-123">Instances of value types are destroyed as soon as the context that contains them is destroyed.</span></span> <span data-ttu-id="8688c-124">Instanzen von Verweistypen werden vom [Garbage Collector](../../../standard/garbage-collection/index.md) zu einem unbestimmten Zeitpunkt zerstört, nachdem der letzte Verweis auf sie entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="8688c-124">Instances of reference types are destroyed by the [garbage collector](../../../standard/garbage-collection/index.md) at some unspecified time after the last reference to them is removed.</span></span>

<span data-ttu-id="8688c-125">Bei Typinstanzen, die nicht verwaltete Ressourcen wie beispielsweise ein Dateihandle enthalten, ist eine deterministische Bereinigung empfehlenswert, um sicherzustellen, dass die darin enthaltenen Ressourcen so bald wie möglich freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8688c-125">For type instances that contain unmanaged resources, for example, a file handle, it's recommended to employ deterministic clean-up to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="8688c-126">Weitere Informationen finden Sie im Artikel zum <xref:System.IDisposable?displayProperty=nameWithType>API-Verweis und der [using-Anweisung](../keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8688c-126">For more information, see the <xref:System.IDisposable?displayProperty=nameWithType> API reference and the [using statement](../keywords/using-statement.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="8688c-127">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="8688c-127">Operator overloadability</span></span>

<span data-ttu-id="8688c-128">Ein benutzerdefinierter Typ kann den `new`-Operator nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="8688c-128">A user-defined type cannot overload the `new` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8688c-129">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="8688c-129">C# language specification</span></span>

<span data-ttu-id="8688c-130">Weitere Informationen finden Sie im Abschnitt [Der new-Operator](~/_csharplang/spec/expressions.md#the-new-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="8688c-130">For more information, see [The new operator](~/_csharplang/spec/expressions.md#the-new-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="8688c-131">Weitere Informationen zum zieltypisierten `new`-Ausdruck finden Sie unter [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-9.0/target-typed-new.md).</span><span class="sxs-lookup"><span data-stu-id="8688c-131">For more information about a target-typed `new` expression, see the [feature proposal note](~/_csharplang/proposals/csharp-9.0/target-typed-new.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8688c-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8688c-132">See also</span></span>

- [<span data-ttu-id="8688c-133">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="8688c-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8688c-134">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="8688c-134">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="8688c-135">Objekt- und Elementinitialisierer</span><span class="sxs-lookup"><span data-stu-id="8688c-135">Object and collection initializers</span></span>](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)
