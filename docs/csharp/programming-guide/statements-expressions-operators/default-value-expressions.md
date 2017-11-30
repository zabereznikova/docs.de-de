---
title: "Standardwertausdrücke (C#-Programmierhandbuch)"
description: "Standardwertausdrücke erzeugen den Standardwert für jeden Verweistyp oder Werttyp."
ms.date: 08/23/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c2bb1c269e5347d615c47ab828506aef538c4761
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="default-value-expressions-c-programming-guide"></a><span data-ttu-id="f7da8-103">Standardwertausdrücke (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="f7da8-103">default value expressions (C# programming guide)</span></span>

<span data-ttu-id="f7da8-104">Ein Standardwertausdruck erzeugt den Standardwert für einen Typ.</span><span class="sxs-lookup"><span data-stu-id="f7da8-104">A default value expression produces the default value for a type.</span></span> <span data-ttu-id="f7da8-105">Standardwertausdrücke sind besonders nützlich in generischen Klassen und Methoden.</span><span class="sxs-lookup"><span data-stu-id="f7da8-105">Default value expressions are particularly useful in generic classes and methods.</span></span> <span data-ttu-id="f7da8-106">Das Zuweisen eines Standardwerts zu einem parametrisierten Typ `T` wird beim Verwenden von Generika erschwert, wenn folgende Punkte im Voraus noch unklar sind:</span><span class="sxs-lookup"><span data-stu-id="f7da8-106">One issue that arises using generics is how to assign a default value to a parameterized type `T` when you do not know the following in advance:</span></span>

- <span data-ttu-id="f7da8-107">Ob `T` ein Verweistyp oder ein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="f7da8-107">Whether `T` is a reference type or a value type.</span></span>
- <span data-ttu-id="f7da8-108">Wenn `T` ein Werttyp ist, ob es dabei um einen numerischen Wert oder eine benutzerdefinierte Struktur handelt.</span><span class="sxs-lookup"><span data-stu-id="f7da8-108">If `T` is a value type, whether is a numeric value or a user-defined struct.</span></span>

 <span data-ttu-id="f7da8-109">Angenommen, dass eine Variable `t` vom parametrisierten Typ `T` vorliegt, ist die Anweisung `t = null` nur gültig, wenn `T` ein Verweistyp ist.</span><span class="sxs-lookup"><span data-stu-id="f7da8-109">Given a variable `t` of a parameterized type `T`, the statement `t = null` is only valid if `T` is a reference type.</span></span> <span data-ttu-id="f7da8-110">Die Zuweisung `t = 0` funktioniert nur für numerische Werttypen, nicht aber für Strukturen.</span><span class="sxs-lookup"><span data-stu-id="f7da8-110">The assignment `t = 0` only works for numeric value types but not for structs.</span></span> <span data-ttu-id="f7da8-111">Die Lösung besteht im Verwenden eines Standardwertausdrucks, der `null` für Verweistypen (Klassentypen und Schnittstellentypen) und 0 für numerische Werttypen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f7da8-111">The solution is to use a default value expression, which returns `null` for reference types (class types and interface types) and zero for numeric value types.</span></span> <span data-ttu-id="f7da8-112">Bei benutzerdefinierten Strukturen gibt er die Struktur zurück, die mit dem 0-Bitmuster initialisiert wurde. Dieses erzeugt 0 oder `null` für jeden Member, je nachdem, ob es sich beim entsprechenden Member um einen Werttyp oder um einen Verweistyp handelt.</span><span class="sxs-lookup"><span data-stu-id="f7da8-112">For user-defined structs, it returns the struct initialized to the zero bit pattern, which produces 0 or `null` for each member depending on whether that member is a value or reference type.</span></span> <span data-ttu-id="f7da8-113">Bei auf NULL festlegbaren Werttypen gibt `default` <xref:System.Nullable%601?displayProperty=nameWithType> zurück, die Initialisierung erfolgt analog zu allen anderen Strukturen.</span><span class="sxs-lookup"><span data-stu-id="f7da8-113">For nullable value types, `default` returns a <xref:System.Nullable%601?displayProperty=nameWithType>, which is initialized like any struct.</span></span>

<span data-ttu-id="f7da8-114">Der Ausdruck `default(T)` ist nicht auf generische Klassen und Methoden beschränkt.</span><span class="sxs-lookup"><span data-stu-id="f7da8-114">The `default(T)` expression is not limited to generic classes and methods.</span></span> <span data-ttu-id="f7da8-115">Standardwertausdrücke können mit jedem verwalteten Typ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f7da8-115">Default value expressions can be used with any managed type.</span></span> <span data-ttu-id="f7da8-116">Jeder der folgenden Ausdrücke ist gültig:</span><span class="sxs-lookup"><span data-stu-id="f7da8-116">Any of these expressions are valid:</span></span>

 [!code-csharp[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]

 <span data-ttu-id="f7da8-117">Im folgenden Beispiel aus der Klasse `GenericList<T>` wird die Verwendung des Operators `default(T)` in einer generischen Klasse veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f7da8-117">The following example from the `GenericList<T>` class shows how to use the `default(T)` operator in a generic class.</span></span> <span data-ttu-id="f7da8-118">Weitere Informationen finden Sie unter [Einführung in Generika](../generics/introduction-to-generics.md).</span><span class="sxs-lookup"><span data-stu-id="f7da8-118">For more information, see [Generics Overview](../generics/introduction-to-generics.md).</span></span>

 [!code-csharp[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]

## <a name="default-literal-and-type-inference"></a><span data-ttu-id="f7da8-119">Standardliterale und Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="f7da8-119">default literal and type inference</span></span>

<span data-ttu-id="f7da8-120">Ab C# 7.1 kann das `default`-Literal für Standardwertausdrücke verwendet werden, wenn der Compiler den Typ des Ausdrucks ableiten kann.</span><span class="sxs-lookup"><span data-stu-id="f7da8-120">Beginning with C# 7.1, the `default` literal can be used for default value expressions when the compiler can infer the type of the expression.</span></span> <span data-ttu-id="f7da8-121">Das `default`-Literal erzeugt die gleichen Werte wie das entsprechende `default(T)`, bei dem `T` der abgeleitete Typ ist.</span><span class="sxs-lookup"><span data-stu-id="f7da8-121">The `default` literal produces the same value as the equivalent `default(T)` where `T` is the inferred type.</span></span> <span data-ttu-id="f7da8-122">Dadurch kann der Code präziser werden, indem Redundanzen durch das mehrmalige Deklarieren eines Typs reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="f7da8-122">This can make code more concise by reducing the redundancy of declaring a type more than once.</span></span> <span data-ttu-id="f7da8-123">Das `default`-Literal kann in jeder der folgenden Positionen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="f7da8-123">The `default` literal can be used in any of the following locations:</span></span>

- <span data-ttu-id="f7da8-124">Variableninitialisierer</span><span class="sxs-lookup"><span data-stu-id="f7da8-124">variable initializer</span></span>
- <span data-ttu-id="f7da8-125">Variablenzuweisung</span><span class="sxs-lookup"><span data-stu-id="f7da8-125">variable assignment</span></span>
- <span data-ttu-id="f7da8-126">Deklarieren des Standardwerts für einen optionalen Parameter</span><span class="sxs-lookup"><span data-stu-id="f7da8-126">declaring the default value for an optional parameter</span></span>
- <span data-ttu-id="f7da8-127">Bereitstellen des Werts für ein Methodenaufrufargument</span><span class="sxs-lookup"><span data-stu-id="f7da8-127">providing the value for a method call argument</span></span>
- <span data-ttu-id="f7da8-128">Zurückgeben einer Anweisung (oder eines Ausdrucks in einem Ausdruckskörpermember)</span><span class="sxs-lookup"><span data-stu-id="f7da8-128">return statement (or expression in an expression bodied member)</span></span>

<span data-ttu-id="f7da8-129">Das folgende Beispiel demonstriert die Verwendung des `default`-Literals in einem Standardwertausdruck:</span><span class="sxs-lookup"><span data-stu-id="f7da8-129">The following example shows many usages of the `default` literal in a default value expression:</span></span>

[!code-csharp[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]

## <a name="see-also"></a><span data-ttu-id="f7da8-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7da8-130">See also</span></span>

 <span data-ttu-id="f7da8-131"><xref:System.Collections.Generic>[C#-Programmierhandbuch](../index.md)</span><span class="sxs-lookup"><span data-stu-id="f7da8-131"><xref:System.Collections.Generic> [C# Programming Guide](../index.md)</span></span>  
 [<span data-ttu-id="f7da8-132">Generika</span><span class="sxs-lookup"><span data-stu-id="f7da8-132">Generics</span></span>](../generics/index.md)  
 [<span data-ttu-id="f7da8-133">Generische Methoden</span><span class="sxs-lookup"><span data-stu-id="f7da8-133">Generic Methods</span></span>](../generics/generic-methods.md)  
 [<span data-ttu-id="f7da8-134">Generika</span><span class="sxs-lookup"><span data-stu-id="f7da8-134">Generics</span></span>](~/docs/standard/generics/index.md)  
