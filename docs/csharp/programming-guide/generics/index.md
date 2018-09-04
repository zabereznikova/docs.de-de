---
title: Generika (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: 638612a0ece8e701b088c97e5dfc49362e6d6419
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506080"
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="f02ed-102">Generika (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="f02ed-102">Generics (C# Programming Guide)</span></span>
<span data-ttu-id="f02ed-103">Generika wurden zur Version 2.0 der Sprache C# und der Common Language Runtime (CLR) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f02ed-103">Generics were added to version 2.0 of the C# language and the common language runtime (CLR).</span></span> <span data-ttu-id="f02ed-104">Generika führen in .NET Framework das Konzept der Typparameter ein, wodurch Sie Klassen und Methoden entwerfen können, die die Spezialisierung einer oder mehr Typen verzögern können, bis die Klasse oder Methode vom Clientcode deklariert und instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="f02ed-104">Generics introduce to the .NET Framework the concept of type parameters, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="f02ed-105">Indem Sie z.B. einen generischen Parameter „T“ verwenden, können Sie eine einzelne Klasse schreiben, die anderer Clientcode verwenden kann, ohne die Kosten und Risiken von Umwandlungen zur Laufzeit oder Boxingvorgängen einzugehen, wie folgendermaßen gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="f02ed-105">For example, by using a generic type parameter T you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#1](../../../csharp/programming-guide/generics/codesnippet/CSharp/index_1.cs)]  
  
## <a name="generics-overview"></a><span data-ttu-id="f02ed-106">Übersicht über Generika</span><span class="sxs-lookup"><span data-stu-id="f02ed-106">Generics Overview</span></span>  
  
-   <span data-ttu-id="f02ed-107">Verwenden Sie Generika, um die Wiederverwendung von Code, Typsicherheit und Leistung zu maximieren.</span><span class="sxs-lookup"><span data-stu-id="f02ed-107">Use generic types to maximize code reuse, type safety, and performance.</span></span>  
  
-   <span data-ttu-id="f02ed-108">Generika werden am häufigsten zur Erstellung von Auflistungsklassen verwendet.</span><span class="sxs-lookup"><span data-stu-id="f02ed-108">The most common use of generics is to create collection classes.</span></span>  
  
-   <span data-ttu-id="f02ed-109">Die Klassenbibliothek von .NET Framework enthält eine Reihe generischer Auflistungsklassen im <xref:System.Collections.Generic>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="f02ed-109">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="f02ed-110">Diese sollten wenn möglich anstatt Klassen wie z.B. <xref:System.Collections.ArrayList> im <xref:System.Collections>-Namespace verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f02ed-110">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>  
  
-   <span data-ttu-id="f02ed-111">Sie können Ihre eigenen generischen Schnittstellen, Klassen, Methoden, Ereignisse und Delegaten erstellen.</span><span class="sxs-lookup"><span data-stu-id="f02ed-111">You can create your own generic interfaces, classes, methods, events and delegates.</span></span>  
  
-   <span data-ttu-id="f02ed-112">Generische Klassen sind womöglich in der Aktivierung des Zugriffs auf Methoden für bestimmte Datentypen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="f02ed-112">Generic classes may be constrained to enable access to methods on particular data types.</span></span>  
  
-   <span data-ttu-id="f02ed-113">Informationen zu den Typen, die in einem generischen Datentyp verwendet werden, können zur Laufzeit unter Verwendung von Reflektion abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f02ed-113">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f02ed-114">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="f02ed-114">Related Sections</span></span>  
 <span data-ttu-id="f02ed-115">Weitere Informationen finden Sie unter: </span><span class="sxs-lookup"><span data-stu-id="f02ed-115">For more information:</span></span>  
  
-   [<span data-ttu-id="f02ed-116">Einführung in Generika</span><span class="sxs-lookup"><span data-stu-id="f02ed-116">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
-   [<span data-ttu-id="f02ed-117">Vorteile von Generika</span><span class="sxs-lookup"><span data-stu-id="f02ed-117">Benefits of Generics</span></span>](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
-   [<span data-ttu-id="f02ed-118">Generische Typparameter</span><span class="sxs-lookup"><span data-stu-id="f02ed-118">Generic Type Parameters</span></span>](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
-   [<span data-ttu-id="f02ed-119">Einschränkungen für Typparameter</span><span class="sxs-lookup"><span data-stu-id="f02ed-119">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
-   [<span data-ttu-id="f02ed-120">Generische Klassen</span><span class="sxs-lookup"><span data-stu-id="f02ed-120">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
  
-   [<span data-ttu-id="f02ed-121">Generische Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f02ed-121">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
-   [<span data-ttu-id="f02ed-122">Generische Methoden</span><span class="sxs-lookup"><span data-stu-id="f02ed-122">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)  
  
-   [<span data-ttu-id="f02ed-123">Generische Delegate</span><span class="sxs-lookup"><span data-stu-id="f02ed-123">Generic Delegates</span></span>](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
-   [<span data-ttu-id="f02ed-124">Unterschiede zwischen C++-Vorlagen und C#-Generika</span><span class="sxs-lookup"><span data-stu-id="f02ed-124">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
-   [<span data-ttu-id="f02ed-125">Generika und Reflexion</span><span class="sxs-lookup"><span data-stu-id="f02ed-125">Generics and Reflection</span></span>](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
-   [<span data-ttu-id="f02ed-126">Generika zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="f02ed-126">Generics in the Run Time</span></span>](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="f02ed-127">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="f02ed-127">C# Language Specification</span></span>  
 <span data-ttu-id="f02ed-128">Weitere Informationen erhalten Sie unter [C#-Sprachspezifikation](../../../csharp/language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="f02ed-128">For more information, see the [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f02ed-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f02ed-129">See Also</span></span>

- <xref:System.Collections.Generic>  
- [<span data-ttu-id="f02ed-130">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f02ed-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f02ed-131">Typen</span><span class="sxs-lookup"><span data-stu-id="f02ed-131">Types</span></span>](../../../csharp/programming-guide/types/index.md)  
- [<span data-ttu-id="f02ed-132">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="f02ed-132">\<typeparam></span></span>](../../../csharp/programming-guide/xmldoc/typeparam.md)  
- [<span data-ttu-id="f02ed-133">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="f02ed-133">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)  
- [<span data-ttu-id="f02ed-134">Generika in .NET</span><span class="sxs-lookup"><span data-stu-id="f02ed-134">Generics in .NET</span></span>](../../../standard/generics/index.md)  