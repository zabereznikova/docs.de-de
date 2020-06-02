---
title: Generics – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: a3ed3aa412c7d9c9d6b705dba80b527057c647fa
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241668"
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="a4b37-102">Generics (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a4b37-102">Generics (C# Programming Guide)</span></span>

<span data-ttu-id="a4b37-103">Generics führen in das Konzept der Typparameter in .NET ein, wodurch Sie Klassen und Methoden entwerfen können, die die Angabe mindestens eines Typs verzögern können, bis die Klasse oder Methode vom Clientcode deklariert und instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="a4b37-103">Generics introduce the concept of type parameters to .NET, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="a4b37-104">Indem Sie z. B. einen generischen Typparameter „`T`“ verwenden, können Sie eine einzelne Klasse schreiben, die von anderem Clientcode verwendet werden kann, ohne dass die Kosten und Risiken von Umwandlungen zur Laufzeit oder Boxingvorgängen anfallen, wie im Folgenden gezeigt:</span><span class="sxs-lookup"><span data-stu-id="a4b37-104">For example, by using a generic type parameter `T`, you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>

[!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]

<span data-ttu-id="a4b37-105">Generische Klassen und Methoden vereinen Wiederverwendbarkeit, Typsicherheit und Effizienz auf eine Weise, wie es ihre nicht generischen Gegenstücke nicht können.</span><span class="sxs-lookup"><span data-stu-id="a4b37-105">Generic classes and methods combine reusability, type safety, and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="a4b37-106">Generics werden am häufigsten für Auflistungen und deren Methoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="a4b37-106">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="a4b37-107">Der Namespace <xref:System.Collections.Generic> enthält eine Reihe von auf Generics basierenden Auflistungsklassen.</span><span class="sxs-lookup"><span data-stu-id="a4b37-107">The <xref:System.Collections.Generic> namespace contains several generic-based collection classes.</span></span> <span data-ttu-id="a4b37-108">Die nicht generischen Auflistungen wie <xref:System.Collections.ArrayList> werden nicht empfohlen und wurden aus Kompatibilitätsgründen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a4b37-108">The non-generic collections, such as <xref:System.Collections.ArrayList> are not recommended and are maintained for compatibility purposes.</span></span> <span data-ttu-id="a4b37-109">Weitere Informationen finden Sie unter [Generics in .NET](../../../standard/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="a4b37-109">For more information, see [Generics in .NET](../../../standard/generics/index.md).</span></span>

<span data-ttu-id="a4b37-110">Sie können selbstverständlich auch benutzerdefinierte generische Typen und Methoden erstellen, um Ihre eigenen typsicheren und effizienten Lösungen und Entwurfsmuster bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a4b37-110">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="a4b37-111">Das folgende Codebeispiel zeigt eine einfache generische linked-list-Klasse zur Veranschaulichung.</span><span class="sxs-lookup"><span data-stu-id="a4b37-111">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="a4b37-112">(In den meisten Fällen sollten Sie die Klasse <xref:System.Collections.Generic.List%601> verwenden, die von .NET bereitgestellt wird, anstatt eine eigene Klasse zu erstellen.) Der Typparameter `T` wird an mehreren Stellen verwendet, wo für gewöhnlich ein konkreter Typ verwendet werden würde, um den Typ des Elements anzugeben, das in der Liste gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="a4b37-112">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by .NET instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="a4b37-113">Er wird wie folgt verwendet:</span><span class="sxs-lookup"><span data-stu-id="a4b37-113">It is used in the following ways:</span></span>

- <span data-ttu-id="a4b37-114">Als Typ eines Methodenparameters in der Methode `AddHead`.</span><span class="sxs-lookup"><span data-stu-id="a4b37-114">As the type of a method parameter in the `AddHead` method.</span></span>
- <span data-ttu-id="a4b37-115">Als Rückgabetyp der Eigenschaft `Data` in der geschachtelten Klasse `Node`.</span><span class="sxs-lookup"><span data-stu-id="a4b37-115">As the return type of the `Data` property in the nested `Node` class.</span></span>
- <span data-ttu-id="a4b37-116">Als Typ des privaten Members `data` in der geschachtelten Klasse.</span><span class="sxs-lookup"><span data-stu-id="a4b37-116">As the type of the private member `data` in the nested class.</span></span>

 <span data-ttu-id="a4b37-117">Beachten Sie, dass `T` für die geschachtelte Klasse `Node` verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a4b37-117">Note that `T` is available to the nested `Node` class.</span></span> <span data-ttu-id="a4b37-118">Wenn `GenericList<T>` mit einem konkreten Typ instanziiert wird, beispielsweise als `GenericList<int>`, wird jedes `T` durch `int` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="a4b37-118">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>

[!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]

<span data-ttu-id="a4b37-119">Das folgende Codebeispiel zeigt, wie Clientcode die generische Klasse `GenericList<T>` verwendet, um eine Ganzzahlliste zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a4b37-119">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="a4b37-120">Indem Sie einfach das Typargument ändern, kann der folgende Code ganz leicht so modifiziert werden, dass er Zeichenfolgenlisten oder jeden anderen benutzerdefinierten Typ erstellt:</span><span class="sxs-lookup"><span data-stu-id="a4b37-120">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>

[!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]

## <a name="generics-overview"></a><span data-ttu-id="a4b37-121">Übersicht über Generics</span><span class="sxs-lookup"><span data-stu-id="a4b37-121">Generics overview</span></span>

- <span data-ttu-id="a4b37-122">Verwenden Sie Generics, um die Wiederverwendung von Code, Typsicherheit und Leistung zu maximieren.</span><span class="sxs-lookup"><span data-stu-id="a4b37-122">Use generic types to maximize code reuse, type safety, and performance.</span></span>
- <span data-ttu-id="a4b37-123">Generics werden am häufigsten zur Erstellung von Auflistungsklassen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a4b37-123">The most common use of generics is to create collection classes.</span></span>
- <span data-ttu-id="a4b37-124">Die .NET Framework-Klassenbibliothek enthält eine Reihe generischer Sammlungsklassen im <xref:System.Collections.Generic>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="a4b37-124">The .NET class library contains several generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="a4b37-125">Diese sollten wenn möglich anstatt Klassen wie z.B. <xref:System.Collections.ArrayList> im <xref:System.Collections>-Namespace verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4b37-125">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>
- <span data-ttu-id="a4b37-126">Sie können Ihre eigenen generischen Schnittstellen, Klassen, Methoden, Ereignisse und Delegaten erstellen.</span><span class="sxs-lookup"><span data-stu-id="a4b37-126">You can create your own generic interfaces, classes, methods, events, and delegates.</span></span>
- <span data-ttu-id="a4b37-127">Generische Klassen sind womöglich in der Aktivierung des Zugriffs auf Methoden für bestimmte Datentypen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="a4b37-127">Generic classes may be constrained to enable access to methods on particular data types.</span></span>
- <span data-ttu-id="a4b37-128">Informationen zu den Typen, die in einem generischen Datentyp verwendet werden, können zur Laufzeit unter Verwendung von Reflektion abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a4b37-128">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>

## <a name="related-sections"></a><span data-ttu-id="a4b37-129">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="a4b37-129">Related sections</span></span>

- [<span data-ttu-id="a4b37-130">Generische Typparameter</span><span class="sxs-lookup"><span data-stu-id="a4b37-130">Generic Type Parameters</span></span>](generic-type-parameters.md)
- [<span data-ttu-id="a4b37-131">Einschränkungen für Typparameter</span><span class="sxs-lookup"><span data-stu-id="a4b37-131">Constraints on Type Parameters</span></span>](constraints-on-type-parameters.md)
- [<span data-ttu-id="a4b37-132">Generische Klassen</span><span class="sxs-lookup"><span data-stu-id="a4b37-132">Generic Classes</span></span>](generic-classes.md)
- [<span data-ttu-id="a4b37-133">Generische Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a4b37-133">Generic Interfaces</span></span>](generic-interfaces.md)
- [<span data-ttu-id="a4b37-134">Generische Methoden</span><span class="sxs-lookup"><span data-stu-id="a4b37-134">Generic Methods</span></span>](generic-methods.md)
- [<span data-ttu-id="a4b37-135">Generische Delegate</span><span class="sxs-lookup"><span data-stu-id="a4b37-135">Generic Delegates</span></span>](generic-delegates.md)
- [<span data-ttu-id="a4b37-136">Unterschiede zwischen C++-Vorlagen und C#-Generics</span><span class="sxs-lookup"><span data-stu-id="a4b37-136">Differences Between C++ Templates and C# Generics</span></span>](differences-between-cpp-templates-and-csharp-generics.md)
- [<span data-ttu-id="a4b37-137">Generics und Reflexion</span><span class="sxs-lookup"><span data-stu-id="a4b37-137">Generics and Reflection</span></span>](generics-and-reflection.md)
- [<span data-ttu-id="a4b37-138">Generics zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a4b37-138">Generics in the Run Time</span></span>](generics-in-the-run-time.md)

## <a name="c-language-specification"></a><span data-ttu-id="a4b37-139">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="a4b37-139">C# language specification</span></span>

<span data-ttu-id="a4b37-140">Weitere Informationen erhalten Sie unter [C#-Sprachspezifikation](~/_csharplang/spec/types.md#constructed-types).</span><span class="sxs-lookup"><span data-stu-id="a4b37-140">For more information, see the [C# Language Specification](~/_csharplang/spec/types.md#constructed-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="a4b37-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4b37-141">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="a4b37-142">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a4b37-142">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a4b37-143">Typen</span><span class="sxs-lookup"><span data-stu-id="a4b37-143">Types</span></span>](../types/index.md)
- [\<typeparam>](../xmldoc/typeparam.md)
- [\<typeparamref>](../xmldoc/typeparamref.md)
- [<span data-ttu-id="a4b37-144">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="a4b37-144">Generics in .NET</span></span>](../../../standard/generics/index.md)
