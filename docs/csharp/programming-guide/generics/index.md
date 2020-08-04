---
title: Generics – C#-Programmierhandbuch
description: Hier erfahren Sie mehr über Generics. Generische Typen maximieren die Wiederverwendbarkeit des Codes, die Typsicherheit und die Leistung und werden häufig verwendet, um Sammlungsklassen zu erstellen.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: beef9c20e3ac62505bc7a4584b404637935de1dc
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299395"
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="1b588-104">Generics (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="1b588-104">Generics (C# Programming Guide)</span></span>

<span data-ttu-id="1b588-105">Generics führen in das Konzept der Typparameter in .NET ein, wodurch Sie Klassen und Methoden entwerfen können, die die Angabe mindestens eines Typs verzögern können, bis die Klasse oder Methode vom Clientcode deklariert und instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="1b588-105">Generics introduce the concept of type parameters to .NET, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="1b588-106">Indem Sie z. B. einen generischen Typparameter „`T`“ verwenden, können Sie eine einzelne Klasse schreiben, die von anderem Clientcode verwendet werden kann, ohne dass die Kosten und Risiken von Umwandlungen zur Laufzeit oder Boxingvorgängen anfallen, wie im Folgenden gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1b588-106">For example, by using a generic type parameter `T`, you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>

[!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]

<span data-ttu-id="1b588-107">Generische Klassen und Methoden vereinen Wiederverwendbarkeit, Typsicherheit und Effizienz auf eine Weise, wie es ihre nicht generischen Gegenstücke nicht können.</span><span class="sxs-lookup"><span data-stu-id="1b588-107">Generic classes and methods combine reusability, type safety, and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="1b588-108">Generics werden am häufigsten für Auflistungen und deren Methoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b588-108">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="1b588-109">Der Namespace <xref:System.Collections.Generic> enthält eine Reihe von auf Generics basierenden Auflistungsklassen.</span><span class="sxs-lookup"><span data-stu-id="1b588-109">The <xref:System.Collections.Generic> namespace contains several generic-based collection classes.</span></span> <span data-ttu-id="1b588-110">Die nicht generischen Auflistungen wie <xref:System.Collections.ArrayList> werden nicht empfohlen und wurden aus Kompatibilitätsgründen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="1b588-110">The non-generic collections, such as <xref:System.Collections.ArrayList> are not recommended and are maintained for compatibility purposes.</span></span> <span data-ttu-id="1b588-111">Weitere Informationen finden Sie unter [Generics in .NET](../../../standard/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="1b588-111">For more information, see [Generics in .NET](../../../standard/generics/index.md).</span></span>

<span data-ttu-id="1b588-112">Sie können selbstverständlich auch benutzerdefinierte generische Typen und Methoden erstellen, um Ihre eigenen typsicheren und effizienten Lösungen und Entwurfsmuster bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1b588-112">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="1b588-113">Das folgende Codebeispiel zeigt eine einfache generische linked-list-Klasse zur Veranschaulichung.</span><span class="sxs-lookup"><span data-stu-id="1b588-113">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="1b588-114">(In den meisten Fällen sollten Sie die Klasse <xref:System.Collections.Generic.List%601> verwenden, die von .NET bereitgestellt wird, anstatt eine eigene Klasse zu erstellen.) Der Typparameter `T` wird an mehreren Stellen verwendet, wo für gewöhnlich ein konkreter Typ verwendet werden würde, um den Typ des Elements anzugeben, das in der Liste gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="1b588-114">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by .NET instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="1b588-115">Er wird wie folgt verwendet:</span><span class="sxs-lookup"><span data-stu-id="1b588-115">It is used in the following ways:</span></span>

- <span data-ttu-id="1b588-116">Als Typ eines Methodenparameters in der Methode `AddHead`.</span><span class="sxs-lookup"><span data-stu-id="1b588-116">As the type of a method parameter in the `AddHead` method.</span></span>
- <span data-ttu-id="1b588-117">Als Rückgabetyp der Eigenschaft `Data` in der geschachtelten Klasse `Node`.</span><span class="sxs-lookup"><span data-stu-id="1b588-117">As the return type of the `Data` property in the nested `Node` class.</span></span>
- <span data-ttu-id="1b588-118">Als Typ des privaten Members `data` in der geschachtelten Klasse.</span><span class="sxs-lookup"><span data-stu-id="1b588-118">As the type of the private member `data` in the nested class.</span></span>

 <span data-ttu-id="1b588-119">Beachten Sie, dass `T` für die geschachtelte Klasse `Node` verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="1b588-119">Note that `T` is available to the nested `Node` class.</span></span> <span data-ttu-id="1b588-120">Wenn `GenericList<T>` mit einem konkreten Typ instanziiert wird, beispielsweise als `GenericList<int>`, wird jedes `T` durch `int` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="1b588-120">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>

[!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]

<span data-ttu-id="1b588-121">Das folgende Codebeispiel zeigt, wie Clientcode die generische Klasse `GenericList<T>` verwendet, um eine Ganzzahlliste zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1b588-121">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="1b588-122">Indem Sie einfach das Typargument ändern, kann der folgende Code ganz leicht so modifiziert werden, dass er Zeichenfolgenlisten oder jeden anderen benutzerdefinierten Typ erstellt:</span><span class="sxs-lookup"><span data-stu-id="1b588-122">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>

[!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]

## <a name="generics-overview"></a><span data-ttu-id="1b588-123">Übersicht über Generics</span><span class="sxs-lookup"><span data-stu-id="1b588-123">Generics overview</span></span>

- <span data-ttu-id="1b588-124">Verwenden Sie Generics, um die Wiederverwendung von Code, Typsicherheit und Leistung zu maximieren.</span><span class="sxs-lookup"><span data-stu-id="1b588-124">Use generic types to maximize code reuse, type safety, and performance.</span></span>
- <span data-ttu-id="1b588-125">Generics werden am häufigsten zur Erstellung von Auflistungsklassen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b588-125">The most common use of generics is to create collection classes.</span></span>
- <span data-ttu-id="1b588-126">Die .NET Framework-Klassenbibliothek enthält eine Reihe generischer Sammlungsklassen im <xref:System.Collections.Generic>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="1b588-126">The .NET class library contains several generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="1b588-127">Diese sollten wenn möglich anstatt Klassen wie z.B. <xref:System.Collections.ArrayList> im <xref:System.Collections>-Namespace verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b588-127">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>
- <span data-ttu-id="1b588-128">Sie können Ihre eigenen generischen Schnittstellen, Klassen, Methoden, Ereignisse und Delegaten erstellen.</span><span class="sxs-lookup"><span data-stu-id="1b588-128">You can create your own generic interfaces, classes, methods, events, and delegates.</span></span>
- <span data-ttu-id="1b588-129">Generische Klassen sind womöglich in der Aktivierung des Zugriffs auf Methoden für bestimmte Datentypen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="1b588-129">Generic classes may be constrained to enable access to methods on particular data types.</span></span>
- <span data-ttu-id="1b588-130">Informationen zu den Typen, die in einem generischen Datentyp verwendet werden, können zur Laufzeit unter Verwendung von Reflektion abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1b588-130">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>

## <a name="related-sections"></a><span data-ttu-id="1b588-131">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1b588-131">Related sections</span></span>

- [<span data-ttu-id="1b588-132">Generische Typparameter</span><span class="sxs-lookup"><span data-stu-id="1b588-132">Generic Type Parameters</span></span>](generic-type-parameters.md)
- [<span data-ttu-id="1b588-133">Einschränkungen für Typparameter</span><span class="sxs-lookup"><span data-stu-id="1b588-133">Constraints on Type Parameters</span></span>](constraints-on-type-parameters.md)
- [<span data-ttu-id="1b588-134">Generische Klassen</span><span class="sxs-lookup"><span data-stu-id="1b588-134">Generic Classes</span></span>](generic-classes.md)
- [<span data-ttu-id="1b588-135">Generische Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1b588-135">Generic Interfaces</span></span>](generic-interfaces.md)
- [<span data-ttu-id="1b588-136">Generische Methoden</span><span class="sxs-lookup"><span data-stu-id="1b588-136">Generic Methods</span></span>](generic-methods.md)
- [<span data-ttu-id="1b588-137">Generische Delegate</span><span class="sxs-lookup"><span data-stu-id="1b588-137">Generic Delegates</span></span>](generic-delegates.md)
- [<span data-ttu-id="1b588-138">Unterschiede zwischen C++-Vorlagen und C#-Generics</span><span class="sxs-lookup"><span data-stu-id="1b588-138">Differences Between C++ Templates and C# Generics</span></span>](differences-between-cpp-templates-and-csharp-generics.md)
- [<span data-ttu-id="1b588-139">Generics und Reflexion</span><span class="sxs-lookup"><span data-stu-id="1b588-139">Generics and Reflection</span></span>](generics-and-reflection.md)
- [<span data-ttu-id="1b588-140">Generics zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="1b588-140">Generics in the Run Time</span></span>](generics-in-the-run-time.md)

## <a name="c-language-specification"></a><span data-ttu-id="1b588-141">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="1b588-141">C# language specification</span></span>

<span data-ttu-id="1b588-142">Weitere Informationen erhalten Sie unter [C#-Sprachspezifikation](~/_csharplang/spec/types.md#constructed-types).</span><span class="sxs-lookup"><span data-stu-id="1b588-142">For more information, see the [C# Language Specification](~/_csharplang/spec/types.md#constructed-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="1b588-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b588-143">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="1b588-144">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1b588-144">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1b588-145">Typen</span><span class="sxs-lookup"><span data-stu-id="1b588-145">Types</span></span>](../types/index.md)
- [\<typeparam>](../xmldoc/typeparam.md)
- [\<typeparamref>](../xmldoc/typeparamref.md)
- [<span data-ttu-id="1b588-146">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="1b588-146">Generics in .NET</span></span>](../../../standard/generics/index.md)
