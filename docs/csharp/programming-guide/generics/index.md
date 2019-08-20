---
title: Generics – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: 7d212aeaa7d7a8c3f152f8610a7ef3fe5de0fe23
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589592"
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="3aa80-102">Generics (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="3aa80-102">Generics (C# Programming Guide)</span></span>
<span data-ttu-id="3aa80-103">Generics wurden zur Version 2.0 der Sprache C# und der Common Language Runtime (CLR) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3aa80-103">Generics were added to version 2.0 of the C# language and the common language runtime (CLR).</span></span> <span data-ttu-id="3aa80-104">Generics führen in .NET Framework das Konzept der Typparameter ein, wodurch Sie Klassen und Methoden entwerfen können, die die Spezialisierung einer oder mehr Typen verzögern können, bis die Klasse oder Methode vom Clientcode deklariert und instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="3aa80-104">Generics introduce to the .NET Framework the concept of type parameters, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="3aa80-105">Indem Sie z.B. einen generischen Parameter „T“ verwenden, können Sie eine einzelne Klasse schreiben, die anderer Clientcode verwenden kann, ohne die Kosten und Risiken von Umwandlungen zur Laufzeit oder Boxingvorgängen einzugehen, wie folgendermaßen gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="3aa80-105">For example, by using a generic type parameter T you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]  

<span data-ttu-id="3aa80-106">Generische Klassen und Methoden vereinen Wiederverwendbarkeit, Typsicherheit und Effizienz so, wie es ihre nicht generischen Gegenstücke nicht können.</span><span class="sxs-lookup"><span data-stu-id="3aa80-106">Generic classes and methods combine reusability, type safety and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="3aa80-107">Generics werden am häufigsten für Auflistungen und deren Methoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="3aa80-107">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="3aa80-108">Version 2.0 der .NET Framework-Klassenbibliothek bietet einen neuen Namespace, <xref:System.Collections.Generic>, der mehrere neue generikabasierte Auflistungsklassen enthält.</span><span class="sxs-lookup"><span data-stu-id="3aa80-108">Version 2.0 of the .NET Framework class library provides a new namespace, <xref:System.Collections.Generic>, which contains several new generic-based collection classes.</span></span> <span data-ttu-id="3aa80-109">Es wird empfohlen, dass alle Anwendungen für .NET Framework 2.0 und höher die neue generische Auflistungsklasse statt der älteren nicht generischen Gegenstücke wie etwa <xref:System.Collections.ArrayList> verwenden.</span><span class="sxs-lookup"><span data-stu-id="3aa80-109">It is recommended that all applications that target the .NET Framework 2.0 and later use the new generic collection classes instead of the older non-generic counterparts such as <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="3aa80-110">Weitere Informationen finden Sie unter [Generics in .NET](../../../standard/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="3aa80-110">For more information, see [Generics in .NET](../../../standard/generics/index.md).</span></span>  
  
 <span data-ttu-id="3aa80-111">Sie können selbstverständlich auch benutzerdefinierte generische Typen und Methoden erstellen, um Ihre eigenen typsicheren und effizienten Lösungen und Entwurfsmuster bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3aa80-111">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="3aa80-112">Das folgende Codebeispiel zeigt eine einfache generische linked-list-Klasse zur Veranschaulichung.</span><span class="sxs-lookup"><span data-stu-id="3aa80-112">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="3aa80-113">(In den meisten Fällen sollten Sie die Klasse <xref:System.Collections.Generic.List%601> verwenden., die von der .NET Framework-Klassenbibliothek bereitgestellt wird, statt Ihre eigene zu erstellen.) Der Typparameter `T` wird an mehreren Stellen verwendet, wo für gewöhnlich ein konkreter Typ verwendet werden würde, um den Typ des Elements anzugeben, das in der Liste gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="3aa80-113">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by the .NET Framework class library instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="3aa80-114">Er wird wie folgt verwendet:</span><span class="sxs-lookup"><span data-stu-id="3aa80-114">It is used in the following ways:</span></span>  
  
- <span data-ttu-id="3aa80-115">Als Typ eines Methodenparameters in der Methode `AddHead`.</span><span class="sxs-lookup"><span data-stu-id="3aa80-115">As the type of a method parameter in the `AddHead` method.</span></span>  
  
- <span data-ttu-id="3aa80-116">Als Rückgabetyp der Eigenschaft `Data` in der geschachtelten Klasse `Node`.</span><span class="sxs-lookup"><span data-stu-id="3aa80-116">As the return type of the `Data` property in the nested `Node` class.</span></span>  
  
- <span data-ttu-id="3aa80-117">Als Typ des privaten Members `data` in der geschachtelten Klasse.</span><span class="sxs-lookup"><span data-stu-id="3aa80-117">As the type of the private member `data` in the nested class.</span></span>  
  
 <span data-ttu-id="3aa80-118">Beachten Sie, dass T für die geschachtelte Klasse `Node` zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="3aa80-118">Note that T is available to the nested `Node` class.</span></span> <span data-ttu-id="3aa80-119">Wenn `GenericList<T>` mit einem konkreten Typ instanziiert wird, beispielsweise als `GenericList<int>`, wird jedes `T` durch `int` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="3aa80-119">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]  
  
 <span data-ttu-id="3aa80-120">Das folgende Codebeispiel zeigt, wie Clientcode die generische Klasse `GenericList<T>` verwendet, um eine Ganzzahlliste zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3aa80-120">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="3aa80-121">Indem Sie einfach das Typargument ändern, kann der folgende Code ganz leicht so modifiziert werden, dass er Zeichenfolgenlisten oder jeden anderen benutzerdefinierten Typ erstellt:</span><span class="sxs-lookup"><span data-stu-id="3aa80-121">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]  
  
## <a name="generics-overview"></a><span data-ttu-id="3aa80-122">Übersicht über Generics</span><span class="sxs-lookup"><span data-stu-id="3aa80-122">Generics Overview</span></span>  
  
- <span data-ttu-id="3aa80-123">Verwenden Sie Generics, um die Wiederverwendung von Code, Typsicherheit und Leistung zu maximieren.</span><span class="sxs-lookup"><span data-stu-id="3aa80-123">Use generic types to maximize code reuse, type safety, and performance.</span></span>  
  
- <span data-ttu-id="3aa80-124">Generics werden am häufigsten zur Erstellung von Auflistungsklassen verwendet.</span><span class="sxs-lookup"><span data-stu-id="3aa80-124">The most common use of generics is to create collection classes.</span></span>  
  
- <span data-ttu-id="3aa80-125">Die Klassenbibliothek von .NET Framework enthält eine Reihe generischer Auflistungsklassen im <xref:System.Collections.Generic>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="3aa80-125">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="3aa80-126">Diese sollten wenn möglich anstatt Klassen wie z.B. <xref:System.Collections.ArrayList> im <xref:System.Collections>-Namespace verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3aa80-126">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>  
  
- <span data-ttu-id="3aa80-127">Sie können Ihre eigenen generischen Schnittstellen, Klassen, Methoden, Ereignisse und Delegaten erstellen.</span><span class="sxs-lookup"><span data-stu-id="3aa80-127">You can create your own generic interfaces, classes, methods, events and delegates.</span></span>  
  
- <span data-ttu-id="3aa80-128">Generische Klassen sind womöglich in der Aktivierung des Zugriffs auf Methoden für bestimmte Datentypen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="3aa80-128">Generic classes may be constrained to enable access to methods on particular data types.</span></span>  
  
- <span data-ttu-id="3aa80-129">Informationen zu den Typen, die in einem generischen Datentyp verwendet werden, können zur Laufzeit unter Verwendung von Reflektion abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3aa80-129">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3aa80-130">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="3aa80-130">Related Sections</span></span>  
 <span data-ttu-id="3aa80-131">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="3aa80-131">For more information:</span></span>  
  
- [<span data-ttu-id="3aa80-132">Generische Typparameter</span><span class="sxs-lookup"><span data-stu-id="3aa80-132">Generic Type Parameters</span></span>](./generic-type-parameters.md)  
  
- [<span data-ttu-id="3aa80-133">Einschränkungen für Typparameter</span><span class="sxs-lookup"><span data-stu-id="3aa80-133">Constraints on Type Parameters</span></span>](./constraints-on-type-parameters.md)  
  
- [<span data-ttu-id="3aa80-134">Generische Klassen</span><span class="sxs-lookup"><span data-stu-id="3aa80-134">Generic Classes</span></span>](./generic-classes.md)  
  
- [<span data-ttu-id="3aa80-135">Generische Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3aa80-135">Generic Interfaces</span></span>](./generic-interfaces.md)  
  
- [<span data-ttu-id="3aa80-136">Generische Methoden</span><span class="sxs-lookup"><span data-stu-id="3aa80-136">Generic Methods</span></span>](./generic-methods.md)  
  
- [<span data-ttu-id="3aa80-137">Generische Delegate</span><span class="sxs-lookup"><span data-stu-id="3aa80-137">Generic Delegates</span></span>](./generic-delegates.md)  
  
- [<span data-ttu-id="3aa80-138">Unterschiede zwischen C++-Vorlagen und C#-Generics</span><span class="sxs-lookup"><span data-stu-id="3aa80-138">Differences Between C++ Templates and C# Generics</span></span>](./differences-between-cpp-templates-and-csharp-generics.md)  
  
- [<span data-ttu-id="3aa80-139">Generics und Reflexion</span><span class="sxs-lookup"><span data-stu-id="3aa80-139">Generics and Reflection</span></span>](./generics-and-reflection.md)  
  
- [<span data-ttu-id="3aa80-140">Generics zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="3aa80-140">Generics in the Run Time</span></span>](./generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="3aa80-141">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="3aa80-141">C# Language Specification</span></span>  
 <span data-ttu-id="3aa80-142">Weitere Informationen erhalten Sie unter [C#-Sprachspezifikation](~/_csharplang/spec/types.md#constructed-types).</span><span class="sxs-lookup"><span data-stu-id="3aa80-142">For more information, see the [C# Language Specification](~/_csharplang/spec/types.md#constructed-types).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aa80-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3aa80-143">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="3aa80-144">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3aa80-144">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3aa80-145">Typen</span><span class="sxs-lookup"><span data-stu-id="3aa80-145">Types</span></span>](../types/index.md)
- [<span data-ttu-id="3aa80-146">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="3aa80-146">\<typeparam></span></span>](../xmldoc/typeparam.md)
- [<span data-ttu-id="3aa80-147">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="3aa80-147">\<typeparamref></span></span>](../xmldoc/typeparamref.md)
- [<span data-ttu-id="3aa80-148">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="3aa80-148">Generics in .NET</span></span>](../../../standard/generics/index.md)
