---
title: new-Operator – C#-Referenz
ms.date: 06/25/2019
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: beb55f0765e7f9090f0587f1d2a06cf03ea90ab8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712662"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="d21d5-102">new-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d21d5-102">new operator (C# reference)</span></span>

<span data-ttu-id="d21d5-103">Der `new`-Operator erstellt eine neue Instanz eines Typs.</span><span class="sxs-lookup"><span data-stu-id="d21d5-103">The `new` operator creates a new instance of a type.</span></span>

<span data-ttu-id="d21d5-104">Sie können das Schlüsselwort `new` auch als einen [Memberdeklarationsmodifizierer](../keywords/new-modifier.md) oder als [Einschränkung eines generischen Typs](../keywords/new-constraint.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="d21d5-104">You can also use the `new` keyword as a [member declaration modifier](../keywords/new-modifier.md) or a [generic type constraint](../keywords/new-constraint.md).</span></span>

## <a name="constructor-invocation"></a><span data-ttu-id="d21d5-105">Konstruktoraufruf</span><span class="sxs-lookup"><span data-stu-id="d21d5-105">Constructor invocation</span></span>

<span data-ttu-id="d21d5-106">Um eine neue Instanz eines Typs zu erstellen, rufen Sie in der Regel einen der [Konstruktoren](../../programming-guide/classes-and-structs/constructors.md) dieses Typs mit dem `new`-Operator auf:</span><span class="sxs-lookup"><span data-stu-id="d21d5-106">To create a new instance of a type, you typically invoke one of the [constructors](../../programming-guide/classes-and-structs/constructors.md) of that type using the `new` operator:</span></span>

[!code-csharp-interactive[invoke constructor](~/samples/csharp/language-reference/operators/NewOperator.cs#Constructor)]

<span data-ttu-id="d21d5-107">Sie können einen [Objekt- oder Auflistungsinitialisierer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) mit dem `new`-Operator verwenden, um ein Objekt in einer Anweisung zu instanziieren und zu initialisieren, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="d21d5-107">You can use an [object or collection initializer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) with the `new` operator to instantiate and initialize an object in one statement, as the following example shows:</span></span>

[!code-csharp-interactive[constructor with initializer](~/samples/csharp/language-reference/operators/NewOperator.cs#ConstructorWithInitializer)]

## <a name="array-creation"></a><span data-ttu-id="d21d5-108">Arrayerstellung</span><span class="sxs-lookup"><span data-stu-id="d21d5-108">Array creation</span></span>

<span data-ttu-id="d21d5-109">Sie können den `new`-Operator auch verwenden, um eine Arrayinstanz zu erstellen, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="d21d5-109">You also use the `new` operator to create an array instance, as the following example shows:</span></span>

[!code-csharp-interactive[create array](~/samples/csharp/language-reference/operators/NewOperator.cs#Array)]

<span data-ttu-id="d21d5-110">Verwenden Sie die Arrayinitialisierungssyntax, um eine Arrayinstanz zu erstellen und sie mit Elementen in einer Anweisung zu auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="d21d5-110">Use array initialization syntax to create an array instance and populate it with elements in one statement.</span></span> <span data-ttu-id="d21d5-111">Im folgenden Beispiel werden verschiedene Möglichkeiten dafür veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="d21d5-111">The following example shows various ways how you can do that:</span></span>

[!code-csharp-interactive[initialize array](~/samples/csharp/language-reference/operators/NewOperator.cs#ArrayInitialization)]

<span data-ttu-id="d21d5-112">Weitere Informationen zu Arrays finden Sie unter [Arrays](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="d21d5-112">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

## <a name="instantiation-of-anonymous-types"></a><span data-ttu-id="d21d5-113">Instanziierung von anonymen Typen</span><span class="sxs-lookup"><span data-stu-id="d21d5-113">Instantiation of anonymous types</span></span>

<span data-ttu-id="d21d5-114">Um eine Instanz eines [anonymen Typs](../../programming-guide/classes-and-structs/anonymous-types.md) zu erstellen, verwenden Sie die Syntax für die Initialisierung von `new`-Operatoren und -Objekten:</span><span class="sxs-lookup"><span data-stu-id="d21d5-114">To create an instance of an [anonymous type](../../programming-guide/classes-and-structs/anonymous-types.md), use the `new` operator and object initializer syntax:</span></span>

[!code-csharp-interactive[anonymous type](~/samples/csharp/language-reference/operators/NewOperator.cs#AnonymousType)]

## <a name="destruction-of-type-instances"></a><span data-ttu-id="d21d5-115">Zerstörung von Typinstanzen</span><span class="sxs-lookup"><span data-stu-id="d21d5-115">Destruction of type instances</span></span>

<span data-ttu-id="d21d5-116">Sie müssen keine zuvor angelegten Typinstanzen zerstören.</span><span class="sxs-lookup"><span data-stu-id="d21d5-116">You don't have to destroy earlier created type instances.</span></span> <span data-ttu-id="d21d5-117">Instanzen sowohl von Verweis- als auch von Werttypen werden automatisch zerstört.</span><span class="sxs-lookup"><span data-stu-id="d21d5-117">Instances of both reference and value types are destroyed automatically.</span></span> <span data-ttu-id="d21d5-118">Instanzen von Werttypen werden zerstört, sobald der sie enthaltende Kontext zerstört wird.</span><span class="sxs-lookup"><span data-stu-id="d21d5-118">Instances of value types are destroyed as soon as the context that contains them is destroyed.</span></span> <span data-ttu-id="d21d5-119">Instanzen von Verweistypen werden vom [Garbage Collector](../../../standard/garbage-collection/index.md) zu einem unbestimmten Zeitpunkt zerstört, nachdem der letzte Verweis auf sie entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="d21d5-119">Instances of reference types are destroyed by the [garbage collector](../../../standard/garbage-collection/index.md) at unspecified time after the last reference to them is removed.</span></span>

<span data-ttu-id="d21d5-120">Bei Typinstanzen, die nicht verwaltete Ressourcen wie beispielsweise ein Dateihandle enthalten, ist eine deterministische Bereinigung empfehlenswert, um sicherzustellen, dass die darin enthaltenen Ressourcen so bald wie möglich freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d21d5-120">For type instances that contain unmanaged resources, for example, a file handle, it's recommended to employ deterministic clean-up to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="d21d5-121">Weitere Informationen finden Sie im Artikel zum <xref:System.IDisposable?displayProperty=nameWithType>API-Verweis und der [using-Anweisung](../keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d21d5-121">For more information, see the <xref:System.IDisposable?displayProperty=nameWithType> API reference and the [using statement](../keywords/using-statement.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="d21d5-122">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="d21d5-122">Operator overloadability</span></span>

<span data-ttu-id="d21d5-123">Ein benutzerdefinierter Typ kann den `new`-Operator nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="d21d5-123">A user-defined type cannot overload the `new` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d21d5-124">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="d21d5-124">C# language specification</span></span>

<span data-ttu-id="d21d5-125">Weitere Informationen finden Sie im Abschnitt [Der new-Operator](~/_csharplang/spec/expressions.md#the-new-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="d21d5-125">For more information, see [The new operator](~/_csharplang/spec/expressions.md#the-new-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d21d5-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d21d5-126">See also</span></span>

- [<span data-ttu-id="d21d5-127">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d21d5-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d21d5-128">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="d21d5-128">C# operators</span></span>](index.md)
- [<span data-ttu-id="d21d5-129">Objekt- und Elementinitialisierer</span><span class="sxs-lookup"><span data-stu-id="d21d5-129">Object and collection initializers</span></span>](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)
