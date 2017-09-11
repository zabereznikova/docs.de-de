---
title: "Übereinstimmungsvergleiche (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- object equality [C#]
ms.assetid: 10b865ea-4e7b-4127-9242-c9b8f57d9f04
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 948bbc1b5b8535cc31ea362497fa69a816b43edc
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="equality-comparisons-c-programming-guide"></a><span data-ttu-id="b363b-102">Übereinstimmungsvergleiche (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b363b-102">Equality Comparisons (C# Programming Guide)</span></span>
<span data-ttu-id="b363b-103">Unter bestimmten Umständen ist es erforderlich, die Gleichheit zweier Werte zu prüfen.</span><span class="sxs-lookup"><span data-stu-id="b363b-103">It is sometimes necessary to compare two values for equality.</span></span> <span data-ttu-id="b363b-104">In einigen Fällen prüfen Sie die *Wertgleichheit*, die auch als *Äquivalenz* bezeichnet wird. Das bedeutet, Sie prüfen, ob die in zwei Variablen enthaltenen Werte gleich sind.</span><span class="sxs-lookup"><span data-stu-id="b363b-104">In some cases, you are testing for *value equality*, also known as *equivalence*, which means that the values that are contained by the two variables are equal.</span></span> <span data-ttu-id="b363b-105">In anderen Fällen müssen Sie ermitteln, ob zwei Variablen auf das gleiche zugrunde liegende Objekt im Arbeitsspeicher verweisen.</span><span class="sxs-lookup"><span data-stu-id="b363b-105">In other cases, you have to determine whether two variables refer to the same underlying object in memory.</span></span> <span data-ttu-id="b363b-106">Diese Art von Gleichheit wird als *Verweisgleichheit* oder *Identität* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b363b-106">This type of equality is called *reference equality*, or *identity*.</span></span> <span data-ttu-id="b363b-107">In diesem Thema werden diese zwei Arten der Gleichheit beschrieben. Außerdem finden Sie hier Links zu verwandten Themen mit weiteren Informationen.</span><span class="sxs-lookup"><span data-stu-id="b363b-107">This topic describes these two kinds of equality and provides links to other topics for more information.</span></span>  
  
## <a name="reference-equality"></a><span data-ttu-id="b363b-108">Verweisgleichheit</span><span class="sxs-lookup"><span data-stu-id="b363b-108">Reference Equality</span></span>  
 <span data-ttu-id="b363b-109">Verweisgleichheit ist gegeben, wenn zwei Objektverweise auf dasselbe zugrunde liegende Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="b363b-109">Reference equality means that two object references refer to the same underlying object.</span></span> <span data-ttu-id="b363b-110">Die Ursache hierfür kann eine einfache Zuweisung sein, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b363b-110">This can occur through simple assignment, as shown in the following example.</span></span>  
  
 <span data-ttu-id="b363b-111">[!code-cs[csProgGuideStatements#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/equality-comparisons_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b363b-111">[!code-cs[csProgGuideStatements#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/equality-comparisons_1.cs)]</span></span>  
  
 <span data-ttu-id="b363b-112">In diesem Code werden zwei Objekte erstellt, nach der Zuweisungsanweisung verweisen jedoch beide Verweise auf das gleiche Objekt.</span><span class="sxs-lookup"><span data-stu-id="b363b-112">In this code, two objects are created, but after the assignment statement, both references refer to the same object.</span></span> <span data-ttu-id="b363b-113">Es liegt eine Verweisgleichheit vor.</span><span class="sxs-lookup"><span data-stu-id="b363b-113">Therefore they have reference equality.</span></span> <span data-ttu-id="b363b-114">Verwenden Sie die <xref:System.Object.ReferenceEquals%2A>-Methode, um zu ermitteln, ob zwei Verweise auf das gleiche Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="b363b-114">Use the <xref:System.Object.ReferenceEquals%2A> method to determine whether two references refer to the same object.</span></span>  
  
 <span data-ttu-id="b363b-115">Das Konzept der Verweisgleichheit gilt nur für Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="b363b-115">The concept of reference equality applies only to reference types.</span></span> <span data-ttu-id="b363b-116">Bei Werttypobjekten kann keine Verweisgleichheit vorliegen, da bei Zuweisung einer Werttypinstanz zu einer Variablen eine Kopie des Werts erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b363b-116">Value type objects cannot have reference equality because when an instance of a value type is assigned to a variable, a copy of the value is made.</span></span> <span data-ttu-id="b363b-117">Aus diesem Grund ist es unmöglich, dass zwei nicht geschachtelte Strukturen vorhanden sind, die auf die gleiche Position im Arbeitsspeicher verweisen.</span><span class="sxs-lookup"><span data-stu-id="b363b-117">Therefore you can never have two unboxed structs that refer to the same location in memory.</span></span> <span data-ttu-id="b363b-118">Wenn Sie zwei Werttypen mit der <xref:System.Object.ReferenceEquals%2A>-Methode vergleichen, ist das Ergebnis immer `false`, selbst wenn die in den Objekten enthaltenen Werte alle identisch sind.</span><span class="sxs-lookup"><span data-stu-id="b363b-118">Furthermore, if you use <xref:System.Object.ReferenceEquals%2A> to compare two value types, the result will always be `false`, even if the values that are contained in the objects are all identical.</span></span> <span data-ttu-id="b363b-119">Der Grund hierfür ist, dass jede Variable in einer eigenen Objektinstanz geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="b363b-119">This is because each variable is boxed into a separate object instance.</span></span> <span data-ttu-id="b363b-120">Weitere Informationen finden Sie unter [Vorgehensweise: Überprüfen auf Verweisgleichheit (Identität)](../../../csharp/programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md).</span><span class="sxs-lookup"><span data-stu-id="b363b-120">For more information, see [How to: Test for Reference Equality (Identity)](../../../csharp/programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md).</span></span>  
  
## <a name="value-equality"></a><span data-ttu-id="b363b-121">Wertgleichheit</span><span class="sxs-lookup"><span data-stu-id="b363b-121">Value Equality</span></span>  
 <span data-ttu-id="b363b-122">Eine Wertgleichheit liegt dann vor, wenn zwei Objekte den gleichen Wert bzw. die gleichen Werte enthalten.</span><span class="sxs-lookup"><span data-stu-id="b363b-122">Value equality means that two objects contain the same value or values.</span></span> <span data-ttu-id="b363b-123">Die Prüfung auf Wertgleichheit für primitive Werttypen wie [int](../../../csharp/language-reference/keywords/int.md) oder [bool](../../../csharp/language-reference/keywords/bool.md) ist einfach.</span><span class="sxs-lookup"><span data-stu-id="b363b-123">For primitive value types such as [int](../../../csharp/language-reference/keywords/int.md) or [bool](../../../csharp/language-reference/keywords/bool.md), tests for value equality are straightforward.</span></span> <span data-ttu-id="b363b-124">Sie können den [==](../../../csharp/language-reference/operators/equality-comparison-operator.md)-Operator verwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b363b-124">You can use the [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) operator, as shown in the following example.</span></span>  
  
```csharp  
int a = GetOriginalValue();  
int b = GetCurrentValue();  
  
// Test for value equality.   
if( b == a)   
{  
    // The two integers are equal.  
}  
```  
  
 <span data-ttu-id="b363b-125">Für die meisten anderen Typen ist die Prüfung auf Wertgleichheit komplexer, da es darauf ankommt, wie die Wertgleichheit für den jeweiligen Typ definiert wird.</span><span class="sxs-lookup"><span data-stu-id="b363b-125">For most other types, testing for value equality is more complex because it requires that you understand how the type defines it.</span></span> <span data-ttu-id="b363b-126">Für Klassen und Strukturen mit mehreren Feldern oder Eigenschaften wird Wertgleichheit oft so definiert, dass alle Felder oder Eigenschaften den gleichen Wert aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b363b-126">For classes and structs that have multiple fields or properties, value equality is often defined to mean that all fields or properties have the same value.</span></span> <span data-ttu-id="b363b-127">Zwei `Point`-Objekte werden z. B. als äquivalent definiert, wenn pointA.X gleich pointB.X und pointA.Y gleich pointB.Y ist.</span><span class="sxs-lookup"><span data-stu-id="b363b-127">For example, two `Point` objects might be defined to be equivalent if pointA.X is equal to pointB.X and pointA.Y is equal to pointB.Y.</span></span>  
  
 <span data-ttu-id="b363b-128">Die Äquivalenz muss jedoch nicht unbedingt auf allen Feldern in einem Typ basieren.</span><span class="sxs-lookup"><span data-stu-id="b363b-128">However, there is no requirement that equivalence be based on all the fields in a type.</span></span> <span data-ttu-id="b363b-129">Die Basis kann auch eine Teilmenge sein.</span><span class="sxs-lookup"><span data-stu-id="b363b-129">It can be based on a subset.</span></span> <span data-ttu-id="b363b-130">Wenn Sie Typen von einem anderen Besitzer vergleichen, vergewissern Sie sich, wie die Gleichheit für den jeweiligen Typ definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b363b-130">When you compare types that you do not own, you should make sure to understand specifically how equivalence is defined for that type.</span></span> <span data-ttu-id="b363b-131">Informationen zum Definieren von Wertgleichheit für Ihre eigenen Klassen und Strukturen finden Sie unter [Vorgehensweise: Definieren von Wertgleichheit für einen Typ](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md).</span><span class="sxs-lookup"><span data-stu-id="b363b-131">For more information about how to define value equality in your own classes and structs, see [How to: Define Value Equality for a Type](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md).</span></span>  
  
### <a name="value-equality-for-floating-point-values"></a><span data-ttu-id="b363b-132">Wertgleichheit für Gleitkommawerte</span><span class="sxs-lookup"><span data-stu-id="b363b-132">Value Equality for Floating Point Values</span></span>  
 <span data-ttu-id="b363b-133">Die Übereinstimmungsprüfung für Gleitkommawerte ([double](../../../csharp/language-reference/keywords/double.md) und [float](../../../csharp/language-reference/keywords/float.md)) ist aufgrund der Ungenauigkeit der Gleitkommaarithmetik auf Computern mit Binärlogik problematisch.</span><span class="sxs-lookup"><span data-stu-id="b363b-133">Equality comparisons of floating point values ([double](../../../csharp/language-reference/keywords/double.md) and [float](../../../csharp/language-reference/keywords/float.md)) are problematic because of the imprecision of floating point arithmetic on binary computers.</span></span> <span data-ttu-id="b363b-134">Weitere Informationen finden Sie in den Hinweisen im Thema <xref:System.Double?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="b363b-134">For more information, see the remarks in the topic <xref:System.Double?displayProperty=fullName>.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="b363b-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b363b-135">Related Topics</span></span>  
  
|<span data-ttu-id="b363b-136">Titel</span><span class="sxs-lookup"><span data-stu-id="b363b-136">Title</span></span>|<span data-ttu-id="b363b-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b363b-137">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b363b-138">Gewusst wie: Überprüfen auf Verweisgleichheit (Identität)</span><span class="sxs-lookup"><span data-stu-id="b363b-138">How to: Test for Reference Equality (Identity)</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md)|<span data-ttu-id="b363b-139">Beschreibt, wie zwei Variablen auf Verweisgleichheit geprüft werden.</span><span class="sxs-lookup"><span data-stu-id="b363b-139">Describes how to determine whether two variables have reference equality.</span></span>|  
|[<span data-ttu-id="b363b-140">Gewusst wie: Definieren von Wertgleichheit für einen Typ</span><span class="sxs-lookup"><span data-stu-id="b363b-140">How to: Define Value Equality for a Type</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md)|<span data-ttu-id="b363b-141">Beschreibt, wie eine benutzerdefinierte Definition der Wertgleichheit für einen Typ erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b363b-141">Describes how to provide a custom definition of value equality for a type.</span></span>|  
|[<span data-ttu-id="b363b-142">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b363b-142">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)|<span data-ttu-id="b363b-143">Links zu ausführlichen Informationen zu wichtigen Funktionen der C#-Sprache sowie zu Funktionen, die über .NET Framework für C# verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b363b-143">Provides links to detailed information about important C# language features and features that are available to C# through the .NET Framework.</span></span>|  
|[<span data-ttu-id="b363b-144">Typen</span><span class="sxs-lookup"><span data-stu-id="b363b-144">Types</span></span>](../../../csharp/programming-guide/types/index.md)|<span data-ttu-id="b363b-145">Informationen zum C#-Typsystem und Links zu weiteren Informationen.</span><span class="sxs-lookup"><span data-stu-id="b363b-145">Provides information about the C# type system and links to additional information.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b363b-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b363b-146">See Also</span></span>  
 [<span data-ttu-id="b363b-147">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b363b-147">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

