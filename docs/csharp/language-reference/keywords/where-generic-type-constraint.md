---
title: where (Einschränkung des generischen Typs) – C#-Referenz
ms.custom: seodec18
ms.date: 04/12/2018
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.openlocfilehash: bccc22f5362b22540dadf08e6b21a07cbc578327
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433871"
---
# <a name="where-generic-type-constraint-c-reference"></a><span data-ttu-id="48579-102">where (Einschränkung des generischen Typs) (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="48579-102">where (generic type constraint) (C# Reference)</span></span>

<span data-ttu-id="48579-103">In einer generischen Typdefinition wird die `where`-Klausel verwendet, um Einschränkungen für Typen anzugeben, die als Argumente für einen Typenparameter in generischen Typen, Methoden, Delegaten oder lokalen Funktionen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="48579-103">The `where` clause in a generic definition specifies constraints on the types that are used as arguments for type parameters in a generic type, method, delegate, or local function.</span></span> <span data-ttu-id="48579-104">Einschränkungen können Schnittstellen und Basisklassen angeben oder erfordern einen generischen Typ als Verweis, Wert oder nicht verwalteten Typ.</span><span class="sxs-lookup"><span data-stu-id="48579-104">Constraints can specify interfaces, base classes, or require a generic type to be a reference, value or unmanaged type.</span></span> <span data-ttu-id="48579-105">Sie deklarieren die Funktionen, die das Typargument besitzen muss.</span><span class="sxs-lookup"><span data-stu-id="48579-105">They declare capabilities that the type argument must possess.</span></span>

<span data-ttu-id="48579-106">So können Sie beispielsweise eine generische Klasse erstellen, `MyGenericClass`, deren Typparameter `T` die Schnittstelle <xref:System.IComparable%601> implementiert:</span><span class="sxs-lookup"><span data-stu-id="48579-106">For example, you can declare a generic class, `MyGenericClass`, such that the type parameter `T` implements the <xref:System.IComparable%601> interface:</span></span>

[!code-csharp[using an interface constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#1)]

> [!NOTE]
> <span data-ttu-id="48579-107">Weitere Informationen über die where-Klausel in einem Abfrageausdruck finden Sie unter [where-Klausel](where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="48579-107">For more information on the where clause in a query expression, see [where clause](where-clause.md).</span></span>

<span data-ttu-id="48579-108">Die `where`-Klausel kann auch eine Basisklasseneinschränkung enthalten.</span><span class="sxs-lookup"><span data-stu-id="48579-108">The `where` clause can also include a base class constraint.</span></span> <span data-ttu-id="48579-109">Die Basisklasseneinschränkung gibt an, dass ein Typ, der als Typargument für den generischen Typ verwendet wird, über die angegebene Klasse als Basisklasse verfügen muss (oder diese Basisklasse sein muss), um als Typargument für diesen generischen Typ verwendet werden zu können.</span><span class="sxs-lookup"><span data-stu-id="48579-109">The base class constraint states that a type to be used as a type argument for that generic type has the specified class as a base class (or is that base class) to be used as a type argument for that generic type.</span></span> <span data-ttu-id="48579-110">Wenn eine Basisklasseneinschränkung verwendet wird, muss sie vor jeder anderen Einschränkung für den Typparameter angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="48579-110">If the base class constraint is used, it must appear before any other constraints on that type parameter.</span></span> <span data-ttu-id="48579-111">Einige Typen sind nicht als Basisklasseneinschränkungen zulässig: <xref:System.Object>, <xref:System.Array> und <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="48579-111">Some types are disallowed as a base class constraint: <xref:System.Object>, <xref:System.Array>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="48579-112">Vor C# 7.3 waren <xref:System.Enum>, <xref:System.Delegate> und <xref:System.MulticastDelegate> ebenfalls nicht als Basisklasseneinschränkungen zulässig.</span><span class="sxs-lookup"><span data-stu-id="48579-112">Prior to C# 7.3, <xref:System.Enum>, <xref:System.Delegate>, and <xref:System.MulticastDelegate> were also disallowed as base class constraints.</span></span> <span data-ttu-id="48579-113">Das folgende Beispiel zeigt die Typen, die jetzt als Basisklasse angegeben werden können:</span><span class="sxs-lookup"><span data-stu-id="48579-113">The following example shows the types that can now be specified as a base class:</span></span>

[!code-csharp[using an interface constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#2)]

<span data-ttu-id="48579-114">Die `where`-Klausel kann angeben, ob der Typ `class` oder `struct` ist.</span><span class="sxs-lookup"><span data-stu-id="48579-114">The `where` clause can specify that the type is a `class` or a `struct`.</span></span> <span data-ttu-id="48579-115">Aufgrund der `struct`-Einschränkung ist die Angabe einer Basisklasseneinschränkung von `System.ValueType` nicht notwendig.</span><span class="sxs-lookup"><span data-stu-id="48579-115">The `struct` constraint removes the need to specify a base class constraint of `System.ValueType`.</span></span> <span data-ttu-id="48579-116">Der `System.ValueType`-Typ darf nicht als Basisklasseneinschränkung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="48579-116">The `System.ValueType` type may not be used as a base class constraint.</span></span> <span data-ttu-id="48579-117">Im folgenden Beispiel werden die `class`- und `struct`-Einschränkungen dargestellt:</span><span class="sxs-lookup"><span data-stu-id="48579-117">The following example shows both the `class` and `struct` constraints:</span></span>

[!code-csharp[using the class and struct constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#3)]

<span data-ttu-id="48579-118">Die `where`-Klausel kann auch eine `unmanaged`-Einschränkung einschließen.</span><span class="sxs-lookup"><span data-stu-id="48579-118">The `where` clause may also include an `unmanaged` constraint.</span></span> <span data-ttu-id="48579-119">Die `unmanaged`-Einschränkung schränkt den Typparameter auf Typen ein, die als [nicht verwaltete Typen](../builtin-types/unmanaged-types.md) bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="48579-119">The `unmanaged` constraint limits the type parameter to types known as [unmanaged types](../builtin-types/unmanaged-types.md).</span></span> <span data-ttu-id="48579-120">Die `unmanaged`-Einschränkung erleichtert das Schreiben von Interop-Code in C# auf niedriger Ebene.</span><span class="sxs-lookup"><span data-stu-id="48579-120">The `unmanaged` constraint makes it easier to write low-level interop code in C#.</span></span> <span data-ttu-id="48579-121">Diese Einschränkung ermöglicht wiederverwendbare Routinen für alle nicht verwalteten Typen.</span><span class="sxs-lookup"><span data-stu-id="48579-121">This constraint enables reusable routines across all unmanaged types.</span></span> <span data-ttu-id="48579-122">Die `unmanaged`-Einschränkung kann nicht mit der `class`- oder `struct`-Einschränkung kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="48579-122">The `unmanaged` constraint can't be combined with the `class` or `struct` constraint.</span></span> <span data-ttu-id="48579-123">Die `unmanaged`-Einschränkung erzwingt, dass der Typ `struct` sein muss:</span><span class="sxs-lookup"><span data-stu-id="48579-123">The `unmanaged` constraint enforces that the type must be a `struct`:</span></span>

[!code-csharp[using the unmanaged constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#4)]

<span data-ttu-id="48579-124">Die `where`-Klausel kann auch eine `new()`-Konstruktoreinschränkung einschließen.</span><span class="sxs-lookup"><span data-stu-id="48579-124">The `where` clause may also include a constructor constraint, `new()`.</span></span> <span data-ttu-id="48579-125">Diese Einschränkung ermöglicht das Erstellen einer Instanz eines Typparameters unter Verwendung des `new`-Operators.</span><span class="sxs-lookup"><span data-stu-id="48579-125">That constraint makes it possible to create an instance of a type parameter using the `new` operator.</span></span> <span data-ttu-id="48579-126">Die [new()-Einschränkung](new-constraint.md) informiert den Compiler, dass jedes angegebene Typargument über einen zugänglichen parameterlosen oder Standardkonstruktor verfügen muss.</span><span class="sxs-lookup"><span data-stu-id="48579-126">The [new() Constraint](new-constraint.md) lets the compiler know that any type argument supplied must have an accessible parameterless--or default-- constructor.</span></span> <span data-ttu-id="48579-127">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="48579-127">For example:</span></span>

[!code-csharp[using the new constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#5)]

<span data-ttu-id="48579-128">Die `new()`-Einschränkung wird in der `where`-Klausel als Letztes angezeigt.</span><span class="sxs-lookup"><span data-stu-id="48579-128">The `new()` constraint appears last in the `where` clause.</span></span> <span data-ttu-id="48579-129">Die `new()`-Einschränkung kann nicht mit der `struct`- oder `unmanaged`-Einschränkung kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="48579-129">The `new()` constraint can't be combined with the `struct` or `unmanaged` constraints.</span></span> <span data-ttu-id="48579-130">Alle Typen, die diese Einschränkungen erfüllen, müssen einen zugänglichen parameterlosen Konstruktor aufweisen, wodurch die `new()`-Einschränkung redundant wird.</span><span class="sxs-lookup"><span data-stu-id="48579-130">All types satisfying those constraints must have an accessible parameterless constructor, making the `new()` constraint redundant.</span></span>

<span data-ttu-id="48579-131">Bei mehreren Typparametern müssen Sie für jeden davon eine eigene `where`-Klausel verwenden, z.B.:</span><span class="sxs-lookup"><span data-stu-id="48579-131">With multiple type parameters, use one `where` clause for each type parameter, for example:</span></span>

[!code-csharp[using multiple where constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#6)]

<span data-ttu-id="48579-132">Sie können auch Einschränkungen wie folgt an Typparameter generischer Methoden anfügen:</span><span class="sxs-lookup"><span data-stu-id="48579-132">You can also attach constraints to type parameters of generic methods, as shown in the following example:</span></span>

[!code-csharp[where constraints with generic methods](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#7)]

<span data-ttu-id="48579-133">Beachten Sie, dass die Syntax zum Beschreiben der Parametereinschränkungen für Delegaten mit der Syntax von Methoden identisch ist:</span><span class="sxs-lookup"><span data-stu-id="48579-133">Notice that the syntax to describe type parameter constraints on delegates is the same as that of methods:</span></span>

[!code-csharp[where constraints with generic methods](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#8)]

<span data-ttu-id="48579-134">Informationen zu generischen Delegaten finden Sie unter [Generic Delegates (Generische Delegaten)](../../../csharp/programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="48579-134">For information on generic delegates, see [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>

<span data-ttu-id="48579-135">Weitere Informationen zur Syntax und der Verwendung von Einschränkungen finden Sie unter [Einschränkungen für Typparameter](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="48579-135">For details on the syntax and use of constraints, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="48579-136">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="48579-136">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="48579-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48579-137">See also</span></span>

- [<span data-ttu-id="48579-138">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="48579-138">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="48579-139">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="48579-139">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="48579-140">Einführung in Generics</span><span class="sxs-lookup"><span data-stu-id="48579-140">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
- [<span data-ttu-id="48579-141">new-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="48579-141">new Constraint</span></span>](../../../csharp/language-reference/keywords/new-constraint.md)
- [<span data-ttu-id="48579-142">Einschränkungen für Typparameter</span><span class="sxs-lookup"><span data-stu-id="48579-142">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)
