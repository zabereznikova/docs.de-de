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
ms.openlocfilehash: 6fb33ad2eb3f6a5e8f6506527f3807f31bf33fdc
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471650"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="088d2-103">Werttypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="088d2-103">Value types (C# reference)</span></span>

<span data-ttu-id="088d2-104">*Werttypen* und [Verweistypen](../keywords/reference-types.md) sind die beiden Hauptkategorien von C#-Typen.</span><span class="sxs-lookup"><span data-stu-id="088d2-104">*Value types* and [reference types](../keywords/reference-types.md) are the two main categories of C# types.</span></span> <span data-ttu-id="088d2-105">Eine Variable eines Werttyps enthält eine Instanz des Typs.</span><span class="sxs-lookup"><span data-stu-id="088d2-105">A variable of a value type contains an instance of the type.</span></span> <span data-ttu-id="088d2-106">Dies unterscheidet sich von einer Variablen eines Verweistyps, die einen Verweis auf eine Instanz des Typs enthält.</span><span class="sxs-lookup"><span data-stu-id="088d2-106">This differs from a variable of a reference type, which contains a reference to an instance of the type.</span></span> <span data-ttu-id="088d2-107">Standardmäßig werden die Variablenwerte bei der [Zuweisung](../operators/assignment-operator.md) kopiert, dabei handelt es sich um die Übergabe eines Arguments an eine Methode oder die Rückgabe eines Methodenergebnisses.</span><span class="sxs-lookup"><span data-stu-id="088d2-107">By default, on [assignment](../operators/assignment-operator.md), passing an argument to a method, and returning a method result, variable values are copied.</span></span> <span data-ttu-id="088d2-108">Im Fall von Werttypvariablen werden die entsprechenden Typinstanzen kopiert.</span><span class="sxs-lookup"><span data-stu-id="088d2-108">In the case of value-type variables, the corresponding type instances are copied.</span></span> <span data-ttu-id="088d2-109">Das folgende Beispiel veranschaulicht dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="088d2-109">The following example demonstrates that behavior:</span></span>

[!code-csharp[copy of values](snippets/shared/ValueTypes.cs#ValueTypeCopied)]

<span data-ttu-id="088d2-110">Wie das vorhergehende Beispiel zeigt, wirken sich Vorgänge auf eine Werttypvariable nur auf die in der Variable gespeicherte Instanz des Werttyps aus.</span><span class="sxs-lookup"><span data-stu-id="088d2-110">As the preceding example shows, operations on a value-type variable affect only that instance of the value type, stored in the variable.</span></span>

<span data-ttu-id="088d2-111">Wenn ein Werttyp einen Datenmember eines Verweistyps enthält, wird beim Kopieren einer Werttypinstanz nur der Verweis auf die Instanz des Verweistyps kopiert.</span><span class="sxs-lookup"><span data-stu-id="088d2-111">If a value type contains a data member of a reference type, only the reference to the instance of the reference type is copied when a value-type instance is copied.</span></span> <span data-ttu-id="088d2-112">Sowohl die kopierte als auch die ursprüngliche Werttypinstanz haben Zugriff auf dieselbe Verweistypinstanz.</span><span class="sxs-lookup"><span data-stu-id="088d2-112">Both the copy and original value-type instance have access to the same reference-type instance.</span></span> <span data-ttu-id="088d2-113">Das folgende Beispiel veranschaulicht dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="088d2-113">The following example demonstrates that behavior:</span></span>

[!code-csharp[shallow copy](snippets/shared/ValueTypes.cs#ShallowCopy)]

> [!NOTE]
> <span data-ttu-id="088d2-114">Definieren und verwenden Sie unveränderliche Werttypen, um Ihren Code weniger fehleranfällig und stabiler zu machen.</span><span class="sxs-lookup"><span data-stu-id="088d2-114">To make your code less error-prone and more robust, define and use immutable value types.</span></span> <span data-ttu-id="088d2-115">In diesem Artikel werden veränderbare Werttypen nur zur Veranschaulichung verwendet.</span><span class="sxs-lookup"><span data-stu-id="088d2-115">This article uses mutable value types only for demonstration purposes.</span></span>

## <a name="kinds-of-value-types"></a><span data-ttu-id="088d2-116">Varianten von Werttypen</span><span class="sxs-lookup"><span data-stu-id="088d2-116">Kinds of value types</span></span>

<span data-ttu-id="088d2-117">Ein Werttyp kann einer der zwei folgenden Varianten sein:</span><span class="sxs-lookup"><span data-stu-id="088d2-117">A value type can be one of the two following kinds:</span></span>

- <span data-ttu-id="088d2-118">ein [Strukturtyp](struct.md), der Daten und zugehörige Funktionen einschließt</span><span class="sxs-lookup"><span data-stu-id="088d2-118">a [structure type](struct.md), which encapsulates data and related functionality</span></span>
- <span data-ttu-id="088d2-119">ein [Enumerationstyp](enum.md), der durch mehrere benannte Konstanten definiert wird und eine Auswahl oder Auswahlmöglichkeiten darstellt</span><span class="sxs-lookup"><span data-stu-id="088d2-119">an [enumeration type](enum.md), which is defined by a set of named constants and represents a choice or a combination of choices</span></span>

<span data-ttu-id="088d2-120">Ein [Werttyp, der NULL zulässt](nullable-value-types.md) wie `T?`, stellt alle Werte des zugrunde liegenden Werttyps `T` und einen zusätzlichen [NULL](../keywords/null.md)-Wert dar.</span><span class="sxs-lookup"><span data-stu-id="088d2-120">A [nullable value type](nullable-value-types.md) `T?` represents all values of its underlying value type `T` and an additional [null](../keywords/null.md) value.</span></span> <span data-ttu-id="088d2-121">Sie können einer Variablen eines Werttyps nicht `null` zuweisen, es sei denn, es handelt sich um einen Werttyp,der NULL zulässt.</span><span class="sxs-lookup"><span data-stu-id="088d2-121">You cannot assign `null` to a variable of a value type, unless it's a nullable value type.</span></span>

## <a name="built-in-value-types"></a><span data-ttu-id="088d2-122">Integrierte Werttypen</span><span class="sxs-lookup"><span data-stu-id="088d2-122">Built-in value types</span></span>

<span data-ttu-id="088d2-123">C# bietet die folgenden integrierten Werttypen, die auch als *einfache Typen* bekannt sind:</span><span class="sxs-lookup"><span data-stu-id="088d2-123">C# provides the following built-in value types, also known as *simple types* :</span></span>

- [<span data-ttu-id="088d2-124">Integrale numerische Typen</span><span class="sxs-lookup"><span data-stu-id="088d2-124">Integral numeric types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="088d2-125">Numerische Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="088d2-125">Floating-point numeric types</span></span>](floating-point-numeric-types.md)
- <span data-ttu-id="088d2-126">[bool](bool.md), der einen booleschen Wert darstellt</span><span class="sxs-lookup"><span data-stu-id="088d2-126">[bool](bool.md) that represents a Boolean value</span></span>
- <span data-ttu-id="088d2-127">[char](char.md), der ein Unicode-Zeichen in UTF-16-Codierung darstellt</span><span class="sxs-lookup"><span data-stu-id="088d2-127">[char](char.md) that represents a Unicode UTF-16 character</span></span>

<span data-ttu-id="088d2-128">Alle einfachen Typen sind Strukturtypen und unterscheiden sich von anderen Strukturtypen dadurch, dass sie bestimmte zusätzliche Vorgänge erlauben:</span><span class="sxs-lookup"><span data-stu-id="088d2-128">All simple types are structure types and differ from other structure types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="088d2-129">Sie können Literale verwenden, um einen Wert eines einfachen Typs bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="088d2-129">You can use literals to provide a value of a simple type.</span></span> <span data-ttu-id="088d2-130">`'A'` ist beispielsweise ein Literal vom Typ `char`, und `2001` ist ein Literal vom Typ `int`.</span><span class="sxs-lookup"><span data-stu-id="088d2-130">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="088d2-131">Konstanten der einfachen Typen können Sie mit dem Schlüsselwort [const](../keywords/const.md) deklarieren.</span><span class="sxs-lookup"><span data-stu-id="088d2-131">You can declare constants of the simple types with the [const](../keywords/const.md) keyword.</span></span> <span data-ttu-id="088d2-132">Es ist nicht möglich, Konstanten anderer Strukturtypen zu haben.</span><span class="sxs-lookup"><span data-stu-id="088d2-132">It's not possible to have constants of other structure types.</span></span>

- <span data-ttu-id="088d2-133">Konstante Ausdrücke, deren Operanden alle Konstanten der einfachen Typen sind, werden zur Kompilierzeit ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="088d2-133">Constant expressions, whose operands are all constants of the simple types, are evaluated at compile time.</span></span>

<span data-ttu-id="088d2-134">Ab C# 7.0 unterstützt C# [Werttupel](value-tuples.md).</span><span class="sxs-lookup"><span data-stu-id="088d2-134">Beginning with C# 7.0, C# supports [value tuples](value-tuples.md).</span></span> <span data-ttu-id="088d2-135">Ein Werttupel ist ein Werttyp, aber kein einfacher Typ.</span><span class="sxs-lookup"><span data-stu-id="088d2-135">A value tuple is a value type, but not a simple type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="088d2-136">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="088d2-136">C# language specification</span></span>

<span data-ttu-id="088d2-137">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="088d2-137">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="088d2-138">Werttypen</span><span class="sxs-lookup"><span data-stu-id="088d2-138">Value types</span></span>](~/_csharplang/spec/types.md#value-types)
- [<span data-ttu-id="088d2-139">Einfache Typen</span><span class="sxs-lookup"><span data-stu-id="088d2-139">Simple types</span></span>](~/_csharplang/spec/types.md#simple-types)
- [<span data-ttu-id="088d2-140">Variablen</span><span class="sxs-lookup"><span data-stu-id="088d2-140">Variables</span></span>](~/_csharplang/spec/variables.md)

## <a name="see-also"></a><span data-ttu-id="088d2-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="088d2-141">See also</span></span>

- [<span data-ttu-id="088d2-142">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="088d2-142">C# reference</span></span>](../index.md)
- <xref:System.ValueType?displayProperty=nameWithType>
- [<span data-ttu-id="088d2-143">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="088d2-143">Reference types</span></span>](../keywords/reference-types.md)
