---
title: "Standardwertausdrücke (C#-Programmierhandbuch)"
description: "Standardwertausdrücke erzeugen den Standardwert für jeden Verweistyp oder Werttyp."
ms.date: 2017-08-23
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 0dc2fcee3903b80816c98bab47e2b9a2e5ef78b0
ms.openlocfilehash: 7b5b53d7ed92c6f6377a3e494daf1d02a4cf0934
ms.contentlocale: de-de
ms.lasthandoff: 08/28/2017

---
# <a name="default-value-expressions-c-programming-guide"></a><span data-ttu-id="510c4-103">Standardwertausdrücke (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="510c4-103">default value expressions (C# programming guide)</span></span>

<span data-ttu-id="510c4-104">Ein Standardwertausdruck erzeugt den Standardwert für einen Typ.</span><span class="sxs-lookup"><span data-stu-id="510c4-104">A default value expression produces the default value for a type.</span></span> <span data-ttu-id="510c4-105">Standardwertausdrücke sind besonders nützlich in generischen Klassen und Methoden.</span><span class="sxs-lookup"><span data-stu-id="510c4-105">Default value expressions are particularly useful in generic classes and methods.</span></span> <span data-ttu-id="510c4-106">Das Zuweisen eines Standardwerts zu einem parametrisierten Typ `T` wird beim Verwenden von Generika erschwert, wenn folgende Punkte im Voraus noch unklar sind:</span><span class="sxs-lookup"><span data-stu-id="510c4-106">One issue that arises using generics is how to assign a default value to a parameterized type `T` when you do not know the following in advance:</span></span>

- <span data-ttu-id="510c4-107">Ob `T` ein Verweistyp oder ein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="510c4-107">Whether `T` is a reference type or a value type.</span></span>
- <span data-ttu-id="510c4-108">Wenn `T` ein Werttyp ist, ob es dabei um einen numerischen Wert oder eine benutzerdefinierte Struktur handelt.</span><span class="sxs-lookup"><span data-stu-id="510c4-108">If `T` is a value type, whether is a numeric value or a user-defined struct.</span></span>

 <span data-ttu-id="510c4-109">Angenommen, dass eine Variable `t` vom parametrisierten Typ `T` vorliegt, ist die Anweisung `t = null` nur gültig, wenn `T` ein Verweistyp ist.</span><span class="sxs-lookup"><span data-stu-id="510c4-109">Given a variable `t` of a parameterized type `T`, the statement `t = null` is only valid if `T` is a reference type.</span></span> <span data-ttu-id="510c4-110">Die Zuweisung `t = 0` funktioniert nur für numerische Werttypen, nicht aber für Strukturen.</span><span class="sxs-lookup"><span data-stu-id="510c4-110">The assignment `t = 0` only works for numeric value types but not for structs.</span></span> <span data-ttu-id="510c4-111">Die Lösung besteht im Verwenden eines Standardwertausdrucks, der `null` für Verweistypen (Klassentypen und Schnittstellentypen) und 0 für numerische Werttypen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="510c4-111">The solution is to use a default value expression, which returns `null` for reference types (class types and interface types) and zero for numeric value types.</span></span> <span data-ttu-id="510c4-112">Bei benutzerdefinierten Strukturen gibt er die Struktur zurück, die mit dem 0-Bitmuster initialisiert wurde. Dieses erzeugt 0 oder `null` für jeden Member, je nachdem, ob es sich beim entsprechenden Member um einen Werttyp oder um einen Verweistyp handelt.</span><span class="sxs-lookup"><span data-stu-id="510c4-112">For user-defined structs, it returns the struct initialized to the zero bit pattern, which produces 0 or `null` for each member depending on whether that member is a value or reference type.</span></span> <span data-ttu-id="510c4-113">Bei auf NULL festlegbaren Werttypen gibt `default` <xref:System.Nullable%601?displayProperty=fullName> zurück, die Initialisierung erfolgt analog zu allen anderen Strukturen.</span><span class="sxs-lookup"><span data-stu-id="510c4-113">For nullable value types, `default` returns a <xref:System.Nullable%601?displayProperty=fullName>, which is initialized like any struct.</span></span>

<span data-ttu-id="510c4-114">Der Ausdruck `default(T)` ist nicht auf generische Klassen und Methoden beschränkt.</span><span class="sxs-lookup"><span data-stu-id="510c4-114">The `default(T)` expression is not limited to generic classes and methods.</span></span> <span data-ttu-id="510c4-115">Standardwertausdrücke können mit jedem verwalteten Typ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="510c4-115">Default value expressions can be used with any managed type.</span></span> <span data-ttu-id="510c4-116">Jeder der folgenden Ausdrücke ist gültig:</span><span class="sxs-lookup"><span data-stu-id="510c4-116">Any of these expressions are valid:</span></span>

 <span data-ttu-id="510c4-117">[!code-cs[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]</span><span class="sxs-lookup"><span data-stu-id="510c4-117">[!code-cs[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]</span></span>

 <span data-ttu-id="510c4-118">Im folgenden Beispiel aus der Klasse `GenericList<T>` wird die Verwendung des Operators `default(T)` in einer generischen Klasse veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="510c4-118">The following example from the `GenericList<T>` class shows how to use the `default(T)` operator in a generic class.</span></span> <span data-ttu-id="510c4-119">Weitere Informationen finden Sie unter [Einführung in Generika](../generics/introduction-to-generics.md).</span><span class="sxs-lookup"><span data-stu-id="510c4-119">For more information, see [Generics Overview](../generics/introduction-to-generics.md).</span></span>

 <span data-ttu-id="510c4-120">[!code-cs[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]</span><span class="sxs-lookup"><span data-stu-id="510c4-120">[!code-cs[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]</span></span>

## <a name="default-literal-and-type-inference"></a><span data-ttu-id="510c4-121">Standardliterale und Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="510c4-121">default literal and type inference</span></span>

<span data-ttu-id="510c4-122">Ab C# 7.1 kann das `default`-Literal für Standardwertausdrücke verwendet werden, wenn der Compiler den Typ des Ausdrucks ableiten kann.</span><span class="sxs-lookup"><span data-stu-id="510c4-122">Beginning with C# 7.1, the `default` literal can be used for default value expressions when the compiler can infer the type of the expression.</span></span> <span data-ttu-id="510c4-123">Das `default`-Literal erzeugt die gleichen Werte wie das entsprechende `default(T)`, bei dem `T` der abgeleitete Typ ist.</span><span class="sxs-lookup"><span data-stu-id="510c4-123">The `default` literal produces the same value as the equivalent `default(T)` where `T` is the inferred type.</span></span> <span data-ttu-id="510c4-124">Dadurch kann der Code präziser werden, indem Redundanzen durch das mehrmalige Deklarieren eines Typs reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="510c4-124">This can make code more concise by reducing the redundancy of declaring a type more than once.</span></span> <span data-ttu-id="510c4-125">Das `default`-Literal kann in jeder der folgenden Positionen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="510c4-125">The `default` literal can be used in any of the following locations:</span></span>

- <span data-ttu-id="510c4-126">Variableninitialisierer</span><span class="sxs-lookup"><span data-stu-id="510c4-126">variable initializer</span></span>
- <span data-ttu-id="510c4-127">Variablenzuweisung</span><span class="sxs-lookup"><span data-stu-id="510c4-127">variable assignment</span></span>
- <span data-ttu-id="510c4-128">Deklarieren des Standardwerts für einen optionalen Parameter</span><span class="sxs-lookup"><span data-stu-id="510c4-128">declaring the default value for an optional parameter</span></span>
- <span data-ttu-id="510c4-129">Bereitstellen des Werts für ein Methodenaufrufargument</span><span class="sxs-lookup"><span data-stu-id="510c4-129">providing the value for a method call argument</span></span>
- <span data-ttu-id="510c4-130">Zurückgeben einer Anweisung (oder eines Ausdrucks in einem Ausdruckskörpermember)</span><span class="sxs-lookup"><span data-stu-id="510c4-130">return statement (or expression in an expression bodied member)</span></span>

<span data-ttu-id="510c4-131">Das folgende Beispiel demonstriert die Verwendung des `default`-Literals in einem Standardwertausdruck:</span><span class="sxs-lookup"><span data-stu-id="510c4-131">The following example shows many usages of the `default` literal in a default value expression:</span></span>

<span data-ttu-id="510c4-132">[!code-cs[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]</span><span class="sxs-lookup"><span data-stu-id="510c4-132">[!code-cs[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]</span></span>

## <a name="see-also"></a><span data-ttu-id="510c4-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="510c4-133">See also</span></span>

 <span data-ttu-id="510c4-134"><xref:System.Collections.Generic> [C#-Programmierhandbuch](../index.md) </span><span class="sxs-lookup"><span data-stu-id="510c4-134"><xref:System.Collections.Generic> [C# Programming Guide](../index.md) </span></span>  
 <span data-ttu-id="510c4-135">[Generika](../generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="510c4-135">[Generics](../generics/index.md) </span></span>  
 <span data-ttu-id="510c4-136">[Generische Methoden](../generics/generic-methods.md) </span><span class="sxs-lookup"><span data-stu-id="510c4-136">[Generic Methods](../generics/generic-methods.md) </span></span>  
 [<span data-ttu-id="510c4-137">Generika</span><span class="sxs-lookup"><span data-stu-id="510c4-137">Generics</span></span>](~/docs/standard/generics/index.md)   

