---
title: Standardwertausdrücke (C#-Programmierhandbuch)
description: Standardwertausdrücke erzeugen den Standardwert für jeden Verweistyp oder Werttyp.
ms.date: 04/25/2018
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.openlocfilehash: 94866f22fb3ad921a834cffb16fe17e44cef5965
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44222291"
---
# <a name="default-value-expressions-c-programming-guide"></a><span data-ttu-id="4c3b3-103">Standardwertausdrücke (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="4c3b3-103">default value expressions (C# programming guide)</span></span>

<span data-ttu-id="4c3b3-104">Ein Standardwertausdruck `default(T)` erzeugt den Standardwert für einen Typ `T`.</span><span class="sxs-lookup"><span data-stu-id="4c3b3-104">A default value expression `default(T)` produces the default value of a type `T`.</span></span> <span data-ttu-id="4c3b3-105">In der folgenden Tabelle wird dargestellt, welche Werte für verschiedene Typen erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="4c3b3-105">The following table shows which values are produced for various types:</span></span>

|<span data-ttu-id="4c3b3-106">Typ</span><span class="sxs-lookup"><span data-stu-id="4c3b3-106">Type</span></span>|<span data-ttu-id="4c3b3-107">Standardwert</span><span class="sxs-lookup"><span data-stu-id="4c3b3-107">Default value</span></span>|
|---------|---------|
|<span data-ttu-id="4c3b3-108">Verweistyp</span><span class="sxs-lookup"><span data-stu-id="4c3b3-108">Any reference type</span></span>|`null`|
|<span data-ttu-id="4c3b3-109">Numerischer Werttyp</span><span class="sxs-lookup"><span data-stu-id="4c3b3-109">Numeric value type</span></span>|<span data-ttu-id="4c3b3-110">Zero</span><span class="sxs-lookup"><span data-stu-id="4c3b3-110">Zero</span></span>|
|[<span data-ttu-id="4c3b3-111">bool</span><span class="sxs-lookup"><span data-stu-id="4c3b3-111">bool</span></span>](../../language-reference/keywords/bool.md)|`false`|
|[<span data-ttu-id="4c3b3-112">char</span><span class="sxs-lookup"><span data-stu-id="4c3b3-112">char</span></span>](../../language-reference/keywords/char.md)|`'\0'`|
|[<span data-ttu-id="4c3b3-113">enum</span><span class="sxs-lookup"><span data-stu-id="4c3b3-113">enum</span></span>](../../language-reference/keywords/enum.md)|<span data-ttu-id="4c3b3-114">Der Wert, der vom Ausdruck `(E)0` erzeugt wird, bei dem `E` der Enumerationsbezeichner ist.</span><span class="sxs-lookup"><span data-stu-id="4c3b3-114">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="4c3b3-115">struct</span><span class="sxs-lookup"><span data-stu-id="4c3b3-115">struct</span></span>](../../language-reference/keywords/struct.md)|<span data-ttu-id="4c3b3-116">Der Wert, der erzeugt wird, indem alle Werttypfelder auf ihre Standardwerte und alle Verweistypfelder auf `null` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4c3b3-116">The value produced by setting all value type fields to their default value and all reference type fields to `null`.</span></span>|
|<span data-ttu-id="4c3b3-117">Nullable-Typ</span><span class="sxs-lookup"><span data-stu-id="4c3b3-117">Nullable type</span></span>|<span data-ttu-id="4c3b3-118">Eine Instanz, für die die <xref:System.Nullable%601.HasValue%2A>-Eigenschaft `false` und die <xref:System.Nullable%601.Value%2A>-Eigenschaft nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="4c3b3-118">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span>|

<span data-ttu-id="4c3b3-119">Standardwertausdrücke sind besonders nützlich in generischen Klassen und Methoden.</span><span class="sxs-lookup"><span data-stu-id="4c3b3-119">Default value expressions are particularly useful in generic classes and methods.</span></span> <span data-ttu-id="4c3b3-120">Das Zuweisen eines Standardwerts zu einem parametrisierten Typ `T` wird beim Verwenden von Generika erschwert, wenn folgende Punkte im Voraus noch unklar sind:</span><span class="sxs-lookup"><span data-stu-id="4c3b3-120">One issue that arises using generics is how to assign a default value of a parameterized type `T` when you don't know the following in advance:</span></span>

- <span data-ttu-id="4c3b3-121">Ob `T` ein Verweistyp oder ein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="4c3b3-121">Whether `T` is a reference type or a value type.</span></span>
- <span data-ttu-id="4c3b3-122">Wenn `T` ein Werttyp ist, unabhängig davon, ob es ein numerischer Wert oder eine Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="4c3b3-122">If `T` is a value type, whether it's a numeric value or a struct.</span></span>

 <span data-ttu-id="4c3b3-123">Angenommen, dass eine Variable `t` vom parametrisierten Typ `T` vorliegt, ist die Anweisung `t = null` nur gültig, wenn `T` ein Verweistyp ist.</span><span class="sxs-lookup"><span data-stu-id="4c3b3-123">Given a variable `t` of a parameterized type `T`, the statement `t = null` is only valid if `T` is a reference type.</span></span> <span data-ttu-id="4c3b3-124">Die Zuweisung `t = 0` funktioniert nur für numerische Werttypen, nicht aber für Strukturen.</span><span class="sxs-lookup"><span data-stu-id="4c3b3-124">The assignment `t = 0` only works for numeric value types but not for structs.</span></span> <span data-ttu-id="4c3b3-125">Verwenden Sie einen Standardwertausdruck, um dieses Problem zu lösen:</span><span class="sxs-lookup"><span data-stu-id="4c3b3-125">To solve that, use a default value expression:</span></span>

```csharp
T t = default(T);
```

<span data-ttu-id="4c3b3-126">Der Ausdruck `default(T)` ist nicht auf generische Klassen und Methoden beschränkt.</span><span class="sxs-lookup"><span data-stu-id="4c3b3-126">The `default(T)` expression is not limited to generic classes and methods.</span></span> <span data-ttu-id="4c3b3-127">Standardwertausdrücke können mit jedem verwalteten Typ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4c3b3-127">Default value expressions can be used with any managed type.</span></span> <span data-ttu-id="4c3b3-128">Jeder der folgenden Ausdrücke ist gültig:</span><span class="sxs-lookup"><span data-stu-id="4c3b3-128">Any of these expressions are valid:</span></span>

 [!code-csharp[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]

 <span data-ttu-id="4c3b3-129">Im folgenden Beispiel aus der Klasse `GenericList<T>` wird die Verwendung des Operators `default(T)` in einer generischen Klasse veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4c3b3-129">The following example from the `GenericList<T>` class shows how to use the `default(T)` operator in a generic class.</span></span> <span data-ttu-id="4c3b3-130">Weitere Informationen finden Sie unter [Introduction to Generics (Einführung in Generika)](../generics/introduction-to-generics.md).</span><span class="sxs-lookup"><span data-stu-id="4c3b3-130">For more information, see [Introduction to Generics](../generics/introduction-to-generics.md).</span></span>

 [!code-csharp[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]

## <a name="default-literal-and-type-inference"></a><span data-ttu-id="4c3b3-131">Standardliterale und Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="4c3b3-131">default literal and type inference</span></span>

<span data-ttu-id="4c3b3-132">Ab C# 7.1 kann das `default`-Literal für Standardwertausdrücke verwendet werden, wenn der Compiler den Typ des Ausdrucks ableiten kann.</span><span class="sxs-lookup"><span data-stu-id="4c3b3-132">Beginning with C# 7.1, the `default` literal can be used for default value expressions when the compiler can infer the type of the expression.</span></span> <span data-ttu-id="4c3b3-133">Das `default`-Literal erzeugt die gleichen Werte wie das entsprechende `default(T)`, bei dem `T` der abgeleitete Typ ist.</span><span class="sxs-lookup"><span data-stu-id="4c3b3-133">The `default` literal produces the same value as the equivalent `default(T)` where `T` is the inferred type.</span></span> <span data-ttu-id="4c3b3-134">Dadurch kann der Code präziser werden, indem Redundanzen durch das mehrmalige Deklarieren eines Typs reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="4c3b3-134">This can make code more concise by reducing the redundancy of declaring a type more than once.</span></span> <span data-ttu-id="4c3b3-135">Das `default`-Literal kann in jeder der folgenden Positionen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="4c3b3-135">The `default` literal can be used in any of the following locations:</span></span>

- <span data-ttu-id="4c3b3-136">Variableninitialisierer</span><span class="sxs-lookup"><span data-stu-id="4c3b3-136">variable initializer</span></span>
- <span data-ttu-id="4c3b3-137">Variablenzuweisung</span><span class="sxs-lookup"><span data-stu-id="4c3b3-137">variable assignment</span></span>
- <span data-ttu-id="4c3b3-138">Deklarieren des Standardwerts für einen optionalen Parameter</span><span class="sxs-lookup"><span data-stu-id="4c3b3-138">declaring the default value for an optional parameter</span></span>
- <span data-ttu-id="4c3b3-139">Bereitstellen des Werts für ein Methodenaufrufargument</span><span class="sxs-lookup"><span data-stu-id="4c3b3-139">providing the value for a method call argument</span></span>
- <span data-ttu-id="4c3b3-140">Zurückgeben einer Anweisung (oder eines Ausdrucks in einem Ausdruckskörpermember)</span><span class="sxs-lookup"><span data-stu-id="4c3b3-140">return statement (or expression in an expression bodied member)</span></span>

<span data-ttu-id="4c3b3-141">Das folgende Beispiel demonstriert die Verwendung des `default`-Literals in einem Standardwertausdruck:</span><span class="sxs-lookup"><span data-stu-id="4c3b3-141">The following example shows many usages of the `default` literal in a default value expression:</span></span>

[!code-csharp[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]

## <a name="see-also"></a><span data-ttu-id="4c3b3-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c3b3-142">See Also</span></span>

- <xref:System.Collections.Generic>  
- [<span data-ttu-id="4c3b3-143">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4c3b3-143">C# Programming Guide</span></span>](../index.md)  
- [<span data-ttu-id="4c3b3-144">Generika (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="4c3b3-144">Generics (C# Programming Guide)</span></span>](../generics/index.md)  
- [<span data-ttu-id="4c3b3-145">Generische Methoden</span><span class="sxs-lookup"><span data-stu-id="4c3b3-145">Generic Methods</span></span>](../generics/generic-methods.md)  
- [<span data-ttu-id="4c3b3-146">Generika in .NET</span><span class="sxs-lookup"><span data-stu-id="4c3b3-146">Generics in .NET</span></span>](~/docs/standard/generics/index.md)  
- [<span data-ttu-id="4c3b3-147">Tabelle für Standardwerte</span><span class="sxs-lookup"><span data-stu-id="4c3b3-147">Default values table</span></span>](../../language-reference/keywords/default-values-table.md)
