---
description: In diesem Artikel werden Werttypen, ihre Arten und die in C# integrierten Werttypen vorgestellt.
title: 'Werttypen: C#-Referenz'
ms.date: 01/22/2020
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 64c9e9eba2495531cfef8a603d53fb21c95c87a4
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599394"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="99549-103">Werttypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="99549-103">Value types (C# reference)</span></span>

<span data-ttu-id="99549-104">*Werttypen* und [Verweistypen](../keywords/reference-types.md) sind die beiden Hauptkategorien von C#-Typen.</span><span class="sxs-lookup"><span data-stu-id="99549-104">*Value types* and [reference types](../keywords/reference-types.md) are the two main categories of C# types.</span></span> <span data-ttu-id="99549-105">Eine Variable eines Werttyps enthält eine Instanz des Typs.</span><span class="sxs-lookup"><span data-stu-id="99549-105">A variable of a value type contains an instance of the type.</span></span> <span data-ttu-id="99549-106">Dies unterscheidet sich von einer Variablen eines Verweistyps, die einen Verweis auf eine Instanz des Typs enthält.</span><span class="sxs-lookup"><span data-stu-id="99549-106">This differs from a variable of a reference type, which contains a reference to an instance of the type.</span></span> <span data-ttu-id="99549-107">Standardmäßig werden die Variablenwerte bei der [Zuweisung](../operators/assignment-operator.md) kopiert, dabei handelt es sich um die Übergabe eines Arguments an eine Methode oder die Rückgabe eines Methodenergebnisses.</span><span class="sxs-lookup"><span data-stu-id="99549-107">By default, on [assignment](../operators/assignment-operator.md), passing an argument to a method, and returning a method result, variable values are copied.</span></span> <span data-ttu-id="99549-108">Im Fall von Werttypvariablen werden die entsprechenden Typinstanzen kopiert.</span><span class="sxs-lookup"><span data-stu-id="99549-108">In the case of value-type variables, the corresponding type instances are copied.</span></span> <span data-ttu-id="99549-109">Das folgende Beispiel veranschaulicht dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="99549-109">The following example demonstrates that behavior:</span></span>

[!code-csharp[copy of values](snippets/shared/ValueTypes.cs#ValueTypeCopied)]

<span data-ttu-id="99549-110">Wie das vorhergehende Beispiel zeigt, wirken sich Vorgänge auf eine Werttypvariable nur auf die in der Variable gespeicherte Instanz des Werttyps aus.</span><span class="sxs-lookup"><span data-stu-id="99549-110">As the preceding example shows, operations on a value-type variable affect only that instance of the value type, stored in the variable.</span></span>

<span data-ttu-id="99549-111">Wenn ein Werttyp einen Datenmember eines Verweistyps enthält, wird beim Kopieren einer Werttypinstanz nur der Verweis auf die Instanz des Verweistyps kopiert.</span><span class="sxs-lookup"><span data-stu-id="99549-111">If a value type contains a data member of a reference type, only the reference to the instance of the reference type is copied when a value-type instance is copied.</span></span> <span data-ttu-id="99549-112">Sowohl die kopierte als auch die ursprüngliche Werttypinstanz haben Zugriff auf dieselbe Verweistypinstanz.</span><span class="sxs-lookup"><span data-stu-id="99549-112">Both the copy and original value-type instance have access to the same reference-type instance.</span></span> <span data-ttu-id="99549-113">Das folgende Beispiel veranschaulicht dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="99549-113">The following example demonstrates that behavior:</span></span>

[!code-csharp[shallow copy](snippets/shared/ValueTypes.cs#ShallowCopy)]

> [!NOTE]
> <span data-ttu-id="99549-114">Definieren und verwenden Sie unveränderliche Werttypen, um Ihren Code weniger fehleranfällig und stabiler zu machen.</span><span class="sxs-lookup"><span data-stu-id="99549-114">To make your code less error-prone and more robust, define and use immutable value types.</span></span> <span data-ttu-id="99549-115">In diesem Artikel werden veränderbare Werttypen nur zur Veranschaulichung verwendet.</span><span class="sxs-lookup"><span data-stu-id="99549-115">This article uses mutable value types only for demonstration purposes.</span></span>

## <a name="kinds-of-value-types-and-type-constraints"></a><span data-ttu-id="99549-116">Arten von Werttypen und Typeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="99549-116">Kinds of value types and type constraints</span></span>

<span data-ttu-id="99549-117">Ein Werttyp kann einer der zwei folgenden Varianten sein:</span><span class="sxs-lookup"><span data-stu-id="99549-117">A value type can be one of the two following kinds:</span></span>

- <span data-ttu-id="99549-118">ein [Strukturtyp](struct.md), der Daten und zugehörige Funktionen einschließt</span><span class="sxs-lookup"><span data-stu-id="99549-118">a [structure type](struct.md), which encapsulates data and related functionality</span></span>
- <span data-ttu-id="99549-119">ein [Enumerationstyp](enum.md), der durch mehrere benannte Konstanten definiert wird und eine Auswahl oder Auswahlmöglichkeiten darstellt</span><span class="sxs-lookup"><span data-stu-id="99549-119">an [enumeration type](enum.md), which is defined by a set of named constants and represents a choice or a combination of choices</span></span>

<span data-ttu-id="99549-120">Ein [Werttyp, der NULL zulässt](nullable-value-types.md) wie `T?`, stellt alle Werte des zugrunde liegenden Werttyps `T` und einen zusätzlichen [NULL](../keywords/null.md)-Wert dar.</span><span class="sxs-lookup"><span data-stu-id="99549-120">A [nullable value type](nullable-value-types.md) `T?` represents all values of its underlying value type `T` and an additional [null](../keywords/null.md) value.</span></span> <span data-ttu-id="99549-121">Sie können einer Variablen eines Werttyps nicht `null` zuweisen, es sei denn, es handelt sich um einen Werttyp,der NULL zulässt.</span><span class="sxs-lookup"><span data-stu-id="99549-121">You cannot assign `null` to a variable of a value type, unless it's a nullable value type.</span></span>

<span data-ttu-id="99549-122">Sie können die [`struct`-Einschränkung](../../programming-guide/generics/constraints-on-type-parameters.md) verwenden, um anzugeben, dass ein Typparameter ein Non-Nullable-Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="99549-122">You can use the [`struct` constraint](../../programming-guide/generics/constraints-on-type-parameters.md) to specify that a type parameter is a non-nullable value type.</span></span> <span data-ttu-id="99549-123">Sowohl Struktur- als auch Enumerationstypen erfüllen die `struct`-Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="99549-123">Both structure and enumeration types satisfy the `struct` constraint.</span></span> <span data-ttu-id="99549-124">Ab C# 7.3 können Sie `System.Enum` in einer Basisklasseneinschränkung (die als [enum-Einschränkung](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints) bezeichnet wird) verwenden, um anzugeben, dass ein Typparameter ein Enumerationstyp ist.</span><span class="sxs-lookup"><span data-stu-id="99549-124">Beginning with C# 7.3, you can use `System.Enum` in a base class constraint (that is known as the [enum constraint](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)) to specify that a type parameter is an enumeration type.</span></span>

## <a name="built-in-value-types"></a><span data-ttu-id="99549-125">Integrierte Werttypen</span><span class="sxs-lookup"><span data-stu-id="99549-125">Built-in value types</span></span>

<span data-ttu-id="99549-126">C# bietet die folgenden integrierten Werttypen, die auch als *einfache Typen* bekannt sind:</span><span class="sxs-lookup"><span data-stu-id="99549-126">C# provides the following built-in value types, also known as *simple types*:</span></span>

- [<span data-ttu-id="99549-127">Integrale numerische Typen</span><span class="sxs-lookup"><span data-stu-id="99549-127">Integral numeric types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="99549-128">Numerische Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="99549-128">Floating-point numeric types</span></span>](floating-point-numeric-types.md)
- <span data-ttu-id="99549-129">[bool](bool.md), der einen booleschen Wert darstellt</span><span class="sxs-lookup"><span data-stu-id="99549-129">[bool](bool.md) that represents a Boolean value</span></span>
- <span data-ttu-id="99549-130">[char](char.md), der ein Unicode-Zeichen in UTF-16-Codierung darstellt</span><span class="sxs-lookup"><span data-stu-id="99549-130">[char](char.md) that represents a Unicode UTF-16 character</span></span>

<span data-ttu-id="99549-131">Alle einfachen Typen sind Strukturtypen und unterscheiden sich von anderen Strukturtypen dadurch, dass sie bestimmte zusätzliche Vorgänge erlauben:</span><span class="sxs-lookup"><span data-stu-id="99549-131">All simple types are structure types and differ from other structure types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="99549-132">Sie können Literale verwenden, um einen Wert eines einfachen Typs bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="99549-132">You can use literals to provide a value of a simple type.</span></span> <span data-ttu-id="99549-133">`'A'` ist beispielsweise ein Literal vom Typ `char`, und `2001` ist ein Literal vom Typ `int`.</span><span class="sxs-lookup"><span data-stu-id="99549-133">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="99549-134">Konstanten der einfachen Typen können Sie mit dem Schlüsselwort [const](../keywords/const.md) deklarieren.</span><span class="sxs-lookup"><span data-stu-id="99549-134">You can declare constants of the simple types with the [const](../keywords/const.md) keyword.</span></span> <span data-ttu-id="99549-135">Es ist nicht möglich, Konstanten anderer Strukturtypen zu haben.</span><span class="sxs-lookup"><span data-stu-id="99549-135">It's not possible to have constants of other structure types.</span></span>

- <span data-ttu-id="99549-136">Konstante Ausdrücke, deren Operanden alle Konstanten der einfachen Typen sind, werden zur Kompilierzeit ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="99549-136">Constant expressions, whose operands are all constants of the simple types, are evaluated at compile time.</span></span>

<span data-ttu-id="99549-137">Ab C# 7.0 unterstützt C# [Werttupel](value-tuples.md).</span><span class="sxs-lookup"><span data-stu-id="99549-137">Beginning with C# 7.0, C# supports [value tuples](value-tuples.md).</span></span> <span data-ttu-id="99549-138">Ein Werttupel ist ein Werttyp, aber kein einfacher Typ.</span><span class="sxs-lookup"><span data-stu-id="99549-138">A value tuple is a value type, but not a simple type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="99549-139">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="99549-139">C# language specification</span></span>

<span data-ttu-id="99549-140">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="99549-140">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="99549-141">Werttypen</span><span class="sxs-lookup"><span data-stu-id="99549-141">Value types</span></span>](~/_csharplang/spec/types.md#value-types)
- [<span data-ttu-id="99549-142">Einfache Typen</span><span class="sxs-lookup"><span data-stu-id="99549-142">Simple types</span></span>](~/_csharplang/spec/types.md#simple-types)
- [<span data-ttu-id="99549-143">Variablen</span><span class="sxs-lookup"><span data-stu-id="99549-143">Variables</span></span>](~/_csharplang/spec/variables.md)

## <a name="see-also"></a><span data-ttu-id="99549-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="99549-144">See also</span></span>

- [<span data-ttu-id="99549-145">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="99549-145">C# reference</span></span>](../index.md)
- <xref:System.ValueType?displayProperty=nameWithType>
- [<span data-ttu-id="99549-146">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="99549-146">Reference types</span></span>](../keywords/reference-types.md)
