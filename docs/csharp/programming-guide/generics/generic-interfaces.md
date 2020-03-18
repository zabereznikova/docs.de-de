---
title: Generische Schnittstellen – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
ms.openlocfilehash: 4cce23da7579e30ecff80b3afb92a5a58795c1bd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712207"
---
# <a name="generic-interfaces-c-programming-guide"></a><span data-ttu-id="ecb15-102">Generische Schnittstellen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ecb15-102">Generic Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="ecb15-103">Es ist häufig sinnvoll, Schnittstellen entweder für generische Auflistungsklassen zu definieren oder für die generischen Klassen, die Elemente in der Auflistung darstellen.</span><span class="sxs-lookup"><span data-stu-id="ecb15-103">It is often useful to define interfaces either for generic collection classes, or for the generic classes that represent items in the collection.</span></span> <span data-ttu-id="ecb15-104">Die Einstellung für generische Klassen ist, dass generische Schnittstellen verwendet werden sollen, z.B. <xref:System.IComparable%601> anstelle von <xref:System.IComparable>. Dadurch werden Boxing- und Unboxingoperationen für Werttypen vermieden.</span><span class="sxs-lookup"><span data-stu-id="ecb15-104">The preference for generic classes is to use generic interfaces, such as <xref:System.IComparable%601> rather than <xref:System.IComparable>, in order to avoid boxing and unboxing operations on value types.</span></span> <span data-ttu-id="ecb15-105">Durch die Klassenbibliothek von .NET Framework werden einige generische Schnittstellen definiert, die zusammen mit den Auflistungsklassen im Namespace <xref:System.Collections.Generic> verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ecb15-105">The .NET Framework class library defines several generic interfaces for use with the collection classes in the <xref:System.Collections.Generic> namespace.</span></span>  
  
 <span data-ttu-id="ecb15-106">Wenn als Einschränkung für einen Typparameter eine Schnittstelle angegeben ist, können nur Typen verwendet werden, die diese Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="ecb15-106">When an interface is specified as a constraint on a type parameter, only types that implement the interface can be used.</span></span> <span data-ttu-id="ecb15-107">Der folgende Code zeigt eine Klasse `SortedList<T>`, die von der Klasse `GenericList<T>` abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="ecb15-107">The following code example shows a `SortedList<T>` class that derives from the `GenericList<T>` class.</span></span> <span data-ttu-id="ecb15-108">Weitere Informationen finden Sie unter [Introduction to Generics (Einführung in Generika)](./index.md).</span><span class="sxs-lookup"><span data-stu-id="ecb15-108">For more information, see [Introduction to Generics](./index.md).</span></span> <span data-ttu-id="ecb15-109">`SortedList<T>` fügt die Einschränkung `where T : IComparable<T>` hinzu.</span><span class="sxs-lookup"><span data-stu-id="ecb15-109">`SortedList<T>` adds the constraint `where T : IComparable<T>`.</span></span> <span data-ttu-id="ecb15-110">Dadurch kann die Methode `BubbleSort` in `SortedList<T>` die generische Methode <xref:System.IComparable%601.CompareTo%2A> für Listenelemente verwenden.</span><span class="sxs-lookup"><span data-stu-id="ecb15-110">This enables the `BubbleSort` method in `SortedList<T>` to use the generic <xref:System.IComparable%601.CompareTo%2A> method on list elements.</span></span> <span data-ttu-id="ecb15-111">In diesem Beispiel sind Listenelemente eine einfache Klasse, `Person`, die `IComparable<Person>` implementiert.</span><span class="sxs-lookup"><span data-stu-id="ecb15-111">In this example, list elements are a simple class, `Person`, that implements `IComparable<Person>`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics2.cs#29)]  
  
 <span data-ttu-id="ecb15-112">Mehrere Schnittstellen können als Einschränkungen für einen einzelnen Typ wie folgt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="ecb15-112">Multiple interfaces can be specified as constraints on a single type, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#30)]  
  
 <span data-ttu-id="ecb15-113">Eine Schnittstelle kann mehr als einen Typparameter wie folgt definieren:</span><span class="sxs-lookup"><span data-stu-id="ecb15-113">An interface can define more than one type parameter, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#31)]  
  
 <span data-ttu-id="ecb15-114">Für Klassen gelten die gleichen Vererbungsregeln wie für Schnittstellen:</span><span class="sxs-lookup"><span data-stu-id="ecb15-114">The rules of inheritance that apply to classes also apply to interfaces:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#32)]  
  
 <span data-ttu-id="ecb15-115">Generische Schnittstellen können von nicht generischen Schnittstellen erben, sofern die generische Schnittstelle kontravariant ist, also die generische Schnittstelle ausschließlich den eigenen Typparameter als Rückgabewert verwendet.</span><span class="sxs-lookup"><span data-stu-id="ecb15-115">Generic interfaces can inherit from non-generic interfaces if the generic interface is contravariant, which means it only uses its type parameter as a return value.</span></span> <span data-ttu-id="ecb15-116">In der Klassenbibliothek von .NET Framework erbt <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Collections.IEnumerable>, da <xref:System.Collections.Generic.IEnumerable%601> nur `T` im Rückgabewert von <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> und in der Funktion zum Abrufen der Eigenschaft <xref:System.Collections.Generic.IEnumerator%601.Current%2A> verwendet.</span><span class="sxs-lookup"><span data-stu-id="ecb15-116">In the .NET Framework class library, <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable> because <xref:System.Collections.Generic.IEnumerable%601> only uses `T` in the return value of <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> and in the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property getter.</span></span>  
  
 <span data-ttu-id="ecb15-117">Konkrete Klassen können geschlossene konstruierte Schnittstellen wie folgt implementieren:</span><span class="sxs-lookup"><span data-stu-id="ecb15-117">Concrete classes can implement closed constructed interfaces, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#33)]  
  
 <span data-ttu-id="ecb15-118">Generische Klassen können generische Schnittstellen oder geschlossene konstruierte Schnittstellen implementieren, sofern die Klassenparameterliste wie nachfolgend gezeigt sämtliche Argumente bereitstellt, die von der Schnittstelle benötigt werden:</span><span class="sxs-lookup"><span data-stu-id="ecb15-118">Generic classes can implement generic interfaces or closed constructed interfaces as long as the class parameter list supplies all arguments required by the interface, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#34)]  
  
 <span data-ttu-id="ecb15-119">Die Regeln, die das Überladen von Methoden steuern, sind für die Methoden innerhalb von generischen Klassen, generischen Strukturen oder generischen Schnittstellen gleich.</span><span class="sxs-lookup"><span data-stu-id="ecb15-119">The rules that control method overloading are the same for methods within generic classes, generic structs, or generic interfaces.</span></span> <span data-ttu-id="ecb15-120">Weitere Informationen finden Sie unter [Generic Methods (Generische Methoden)](./generic-methods.md).</span><span class="sxs-lookup"><span data-stu-id="ecb15-120">For more information, see [Generic Methods](./generic-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecb15-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ecb15-121">See also</span></span>

- [<span data-ttu-id="ecb15-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ecb15-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ecb15-123">Einführung in Generics</span><span class="sxs-lookup"><span data-stu-id="ecb15-123">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="ecb15-124">interface</span><span class="sxs-lookup"><span data-stu-id="ecb15-124">interface</span></span>](../../language-reference/keywords/interface.md)
- [<span data-ttu-id="ecb15-125">Generics</span><span class="sxs-lookup"><span data-stu-id="ecb15-125">Generics</span></span>](../../../standard/generics/index.md)
