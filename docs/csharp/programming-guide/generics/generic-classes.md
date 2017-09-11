---
title: Generische Klassen (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, generic classes
- generics [C#], classes
ms.assetid: 27d6f256-cd61-41e3-bc6e-b990a53b0224
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 17ec9f5d26c01b7f7f7f95026bfdfaa88d709b60
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="generic-classes-c-programming-guide"></a><span data-ttu-id="3459e-102">Generische Klassen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="3459e-102">Generic Classes (C# Programming Guide)</span></span>
<span data-ttu-id="3459e-103">Generische Klassen kapseln Operationen, die nicht spezifisch für einen bestimmten Datentyp sind.</span><span class="sxs-lookup"><span data-stu-id="3459e-103">Generic classes encapsulate operations that are not specific to a particular data type.</span></span> <span data-ttu-id="3459e-104">Generische Klassen werden am häufigsten bei Auflistungen verwendet, z.B. bei verknüpften Listen, Hashtabellen, Stapeln, Warteschlangen, Strukturen usw.</span><span class="sxs-lookup"><span data-stu-id="3459e-104">The most common use for generic classes is with collections like linked lists, hash tables, stacks, queues, trees, and so on.</span></span> <span data-ttu-id="3459e-105">Vorgänge wie das Hinzufügen oder Entfernen von Elementen aus der Auflistung werden nahezu auf die gleiche Art und Weise ausgeführt, unabhängig vom Typ der gespeicherten Daten.</span><span class="sxs-lookup"><span data-stu-id="3459e-105">Operations such as adding and removing items from the collection are performed in basically the same way regardless of the type of data being stored.</span></span>  
  
 <span data-ttu-id="3459e-106">Für die meisten Szenarios, die Auflistungsklassen erfordern, wird empfohlen, die in der Klassenbibliothek von .NET Framework bereitgestellten Auflistungsklassen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3459e-106">For most scenarios that require collection classes, the recommended approach is to use the ones provided in the .NET Framework class library.</span></span> <span data-ttu-id="3459e-107">Weitere Informationen zur Verwendung dieser Klassen finden Sie unter [Generics in the .NET Framework Class Library (Generika in der .NET Framework-Klassenbibliothek)](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).</span><span class="sxs-lookup"><span data-stu-id="3459e-107">For more information about using these classes, see [Generics in the .NET Framework Class Library](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).</span></span>  
  
 <span data-ttu-id="3459e-108">In der Regel erstellen Sie generische Klassen, indem Sie von einer vorhandenen konkreten Klasse ausgehen und Typen in Typparameter ändern (einen nach dem anderen), bis das optimale Verhältnis zwischen Verallgemeinerung und Verwendbarkeit gefunden ist.</span><span class="sxs-lookup"><span data-stu-id="3459e-108">Typically, you create generic classes by starting with an existing concrete class, and changing types into type parameters one at a time until you reach the optimal balance of generalization and usability.</span></span> <span data-ttu-id="3459e-109">Wenn Sie eigene generische Klassen erstellen möchten, sollten Sie die folgenden wichtigen Aspekte beachten:</span><span class="sxs-lookup"><span data-stu-id="3459e-109">When creating your own generic classes, important considerations include the following:</span></span>  
  
-   <span data-ttu-id="3459e-110">Welche Typen sollen in Typparameter verallgemeinert werden.</span><span class="sxs-lookup"><span data-stu-id="3459e-110">Which types to generalize into type parameters.</span></span>  
  
     <span data-ttu-id="3459e-111">Im Allgemeinen gilt: Je mehr Typen Sie parametrisieren können, umso flexibler und besser wiederverwendbar ist Ihr Code.</span><span class="sxs-lookup"><span data-stu-id="3459e-111">As a rule, the more types you can parameterize, the more flexible and reusable your code becomes.</span></span> <span data-ttu-id="3459e-112">Jedoch kann ein Zuviel an Verallgemeinerung zu Code führen, der von anderen Entwicklern nur schwer gelesen oder verstanden wird.</span><span class="sxs-lookup"><span data-stu-id="3459e-112">However, too much generalization can create code that is difficult for other developers to read or understand.</span></span>  
  
-   <span data-ttu-id="3459e-113">Welche Einschränkungen sollen ggf. auf die Typparameter angewendet werden (siehe [Constraints on Type Parameters (Einschränkungen für Typparameter)](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)).</span><span class="sxs-lookup"><span data-stu-id="3459e-113">What constraints, if any, to apply to the type parameters (See [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)).</span></span>  
  
     <span data-ttu-id="3459e-114">Es empfiehlt sich, alle Einschränkungen anzuwenden, die maximal möglich sind, und bei denen Sie dennoch sämtliche Typen, die Sie behandeln müssen, auch behandeln können.</span><span class="sxs-lookup"><span data-stu-id="3459e-114">A good rule is to apply the maximum constraints possible that will still let you handle the types you must handle.</span></span> <span data-ttu-id="3459e-115">Wenn Sie zum Beispiel wissen, dass die generische Klasse nur mit Referenztypen verwendet werden soll, dann können Sie die Klasseneinschränkung anwenden.</span><span class="sxs-lookup"><span data-stu-id="3459e-115">For example, if you know that your generic class is intended for use only with reference types, apply the class constraint.</span></span> <span data-ttu-id="3459e-116">Dadurch wird verhindert, dass die Klasse unbeabsichtigt mit Werttypen verwendet wird. Gleichzeitig können Sie den Operator `as` für `T` verwenden und nach NULL-Werten suchen.</span><span class="sxs-lookup"><span data-stu-id="3459e-116">That will prevent unintended use of your class with value types, and will enable you to use the `as` operator on `T`, and check for null values.</span></span>  
  
-   <span data-ttu-id="3459e-117">Ob das generische Verhalten in Basisklassen und Unterklassen zerlegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3459e-117">Whether to factor generic behavior into base classes and subclasses.</span></span>  
  
     <span data-ttu-id="3459e-118">Da generische Klassen als Basisklassen dienen können, sind hier beim Entwurf die gleichen Aspekte zu berücksichtigen wie bei nicht generischen Klassen.</span><span class="sxs-lookup"><span data-stu-id="3459e-118">Because generic classes can serve as base classes, the same design considerations apply here as with non-generic classes.</span></span> <span data-ttu-id="3459e-119">Weitere Informationen bieten die Regeln zum Erben von generischen Basisklassen weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="3459e-119">See the rules about inheriting from generic base classes later in this topic.</span></span>  
  
-   <span data-ttu-id="3459e-120">Ob eine oder mehrere generische Schnittstellen implementiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="3459e-120">Whether to implement one or more generic interfaces.</span></span>  
  
     <span data-ttu-id="3459e-121">Wenn Sie beispielsweise eine Klasse entwerfen, die zum Erstellen von Elementen in einer generisch basierten Auflistung verwendet wird, müssen Sie unter Umständen eine Schnittstelle implementieren, z.B. <xref:System.IComparable%601>, wobei `T` der Typ Ihrer Klasse ist.</span><span class="sxs-lookup"><span data-stu-id="3459e-121">For example, if you are designing a class that will be used to create items in a generics-based collection, you may have to implement an interface such as <xref:System.IComparable%601> where `T` is the type of your class.</span></span>  
  
 <span data-ttu-id="3459e-122">Ein Beispiel für eine einfache generische Klasse finden Sie unter [Introduction to Generics (Einführung in Generika)](../../../csharp/programming-guide/generics/introduction-to-generics.md).</span><span class="sxs-lookup"><span data-stu-id="3459e-122">For an example of a simple generic class, see [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md).</span></span>  
  
 <span data-ttu-id="3459e-123">Die Regeln für Einschränkungen und Typparameter haben eine Reihe von Auswirkungen auf das Verhalten einer generischen Klasse, besonders im Hinblick auf Vererbung und Zugriff der Member.</span><span class="sxs-lookup"><span data-stu-id="3459e-123">The rules for type parameters and constraints have several implications for generic class behavior, especially regarding inheritance and member accessibility.</span></span> <span data-ttu-id="3459e-124">Bevor Sie fortfahren, sollten Sie einige Begriffe verstehen.</span><span class="sxs-lookup"><span data-stu-id="3459e-124">Before proceeding, you should understand some terms.</span></span> <span data-ttu-id="3459e-125">Bei einer generischen Klasse kann der Clientcode `Node<T>,` auf die Klasse verweisen, indem er ein Typargument angibt, um einen geschlossenen konstruierten Typ (`Node<int>`) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3459e-125">For a generic class `Node<T>,` client code can reference the class either by specifying a type argument, to create a closed constructed type (`Node<int>`).</span></span> <span data-ttu-id="3459e-126">Die Alternative besteht darin, den Typparameter nicht anzugeben, z.B. wenn Sie eine generische Basisklasse angeben, um einen offenen konstruierten Typ (`Node<T>`) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3459e-126">Alternatively, it can leave the type parameter unspecified, for example when you specify a generic base class, to create an open constructed type (`Node<T>`).</span></span> <span data-ttu-id="3459e-127">Generische Klassen können von konkreten, geschlossenen konstruierten oder offenen konstruierten Basisklassen erben:</span><span class="sxs-lookup"><span data-stu-id="3459e-127">Generic classes can inherit from concrete, closed constructed, or open constructed base classes:</span></span>  
  
 <span data-ttu-id="3459e-128">[!code-cs[csProgGuideGenerics#16](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3459e-128">[!code-cs[csProgGuideGenerics#16](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_1.cs)]</span></span>  
  
 <span data-ttu-id="3459e-129">Nicht generische, also konkrete Klassen können von geschlossenen konstruierten Basisklassen erben, aber nicht von offenen konstruierten Klassen oder Typparametern, denn während der Laufzeit ist es für den Clientcode nicht möglich, das erforderliche Typargument bereitzustellen, das zum Instanziieren der Basisklasse benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="3459e-129">Non-generic, in other words, concrete, classes can inherit from closed constructed base classes, but not from open constructed classes or from type parameters because there is no way at run time for client code to supply the type argument required to instantiate the base class.</span></span>  
  
 <span data-ttu-id="3459e-130">[!code-cs[csProgGuideGenerics#17](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3459e-130">[!code-cs[csProgGuideGenerics#17](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_2.cs)]</span></span>  
  
 <span data-ttu-id="3459e-131">Generische Klassen, die von offenen konstruierten Typen erben, müssen für sämtliche Basisklassen-Typparameter, die von der erbenden Klasse nicht verwendet werden, Typargumente bereitstellen. Der folgende Code stellt ein Beispiel dafür dar:</span><span class="sxs-lookup"><span data-stu-id="3459e-131">Generic classes that inherit from open constructed types must supply type arguments for any base class type parameters that are not shared by the inheriting class, as demonstrated in the following code:</span></span>  
  
 <span data-ttu-id="3459e-132">[!code-cs[csProgGuideGenerics#18](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="3459e-132">[!code-cs[csProgGuideGenerics#18](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_3.cs)]</span></span>  
  
 <span data-ttu-id="3459e-133">Generische Klassen, die von offenen konstruierten Typen erben, müssen Einschränkungen angeben, die den Einschränkungen des Basistyps übergeordnet sind oder diese implizieren:</span><span class="sxs-lookup"><span data-stu-id="3459e-133">Generic classes that inherit from open constructed types must specify constraints that are a superset of, or imply, the constraints on the base type:</span></span>  
  
 <span data-ttu-id="3459e-134">[!code-cs[csProgGuideGenerics#19](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="3459e-134">[!code-cs[csProgGuideGenerics#19](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_4.cs)]</span></span>  
  
 <span data-ttu-id="3459e-135">Generische Typen können mehrere Typparameter und Einschränkungen wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="3459e-135">Generic types can use multiple type parameters and constraints, as follows:</span></span>  
  
 <span data-ttu-id="3459e-136">[!code-cs[csProgGuideGenerics#20](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="3459e-136">[!code-cs[csProgGuideGenerics#20](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_5.cs)]</span></span>  
  
 <span data-ttu-id="3459e-137">Offene konstruierte und geschlossene konstruierte Typen können als Methodenparameter verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="3459e-137">Open constructed and closed constructed types can be used as method parameters:</span></span>  
  
 <span data-ttu-id="3459e-138">[!code-cs[csProgGuideGenerics#21](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="3459e-138">[!code-cs[csProgGuideGenerics#21](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_6.cs)]</span></span>  
  
 <span data-ttu-id="3459e-139">Wenn eine generische Klasse eine Schnittstelle implementiert, können alle Instanzen dieser Klasse in diese Schnittstelle umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="3459e-139">If a generic class implements an interface, all instances of that class can be cast to that interface.</span></span>  
  
 <span data-ttu-id="3459e-140">Generische Klassen sind unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="3459e-140">Generic classes are invariant.</span></span> <span data-ttu-id="3459e-141">Wenn also ein Eingabeparameter eine `List<BaseClass>` angibt, wird Ihnen ein Kompilierungsfehler angezeigt, falls Sie versuchen, eine `List<DerivedClass>` bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3459e-141">In other words, if an input parameter specifies a `List<BaseClass>`, you will get a compile-time error if you try to provide a `List<DerivedClass>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3459e-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3459e-142">See Also</span></span>  
 <span data-ttu-id="3459e-143"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="3459e-143"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="3459e-144">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3459e-144">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3459e-145">[Generika](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="3459e-145">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 <span data-ttu-id="3459e-146">[Saving the State of Enumerators (Speichern des Zustands von Enumeratoren)](http://go.microsoft.com/fwlink/?LinkId=112390) </span><span class="sxs-lookup"><span data-stu-id="3459e-146">[Saving the State of Enumerators](http://go.microsoft.com/fwlink/?LinkId=112390) </span></span>  
 [<span data-ttu-id="3459e-147">An Inheritance Puzzle, Part One (Ein Vererbungs-Puzzle, Teil 1)</span><span class="sxs-lookup"><span data-stu-id="3459e-147">An Inheritance Puzzle, Part One</span></span>](http://go.microsoft.com/fwlink/?LinkId=112380)

