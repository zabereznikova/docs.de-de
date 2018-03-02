---
title: Generische Auflistungen in .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET Framework], collections
- generic collections [.NET Framework]
ms.assetid: 5b646751-6ab7-465c-916c-b1a76aefa9f5
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d7e7d11446c14cffbef1e5cade5f082874187636
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="generic-collections-in-the-net-framework"></a><span data-ttu-id="85b27-102">Generische Auflistungen in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="85b27-102">Generic Collections in the .NET Framework</span></span>
<span data-ttu-id="85b27-103">Dieses Thema enthält eine Übersicht über die generischen Auflistungsklassen und andere generischen Typen in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="85b27-103">This topic provides an overview of the generic collection classes and other generic types in the .NET Framework.</span></span>  
  
## <a name="generic-collections-in-the-net-framework"></a><span data-ttu-id="85b27-104">Generische Auflistungen in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="85b27-104">Generic Collections in the .NET Framework</span></span>  
 <span data-ttu-id="85b27-105">Die Klassenbibliothek von .NET Framework enthält eine Reihe generischer Auflistungsklassen im <xref:System.Collections.Generic>- und im <xref:System.Collections.ObjectModel>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="85b27-105">The .NET Framework class library provides a number of generic collection classes in the <xref:System.Collections.Generic> and <xref:System.Collections.ObjectModel> namespaces.</span></span> <span data-ttu-id="85b27-106">Weitere Informationen zu diesen Klassen finden Sie unter [Häufig verwendete Auflistungstypen](../../../docs/standard/collections/commonly-used-collection-types.md).</span><span class="sxs-lookup"><span data-stu-id="85b27-106">For more information about these classes, see [Commonly Used Collection Types](../../../docs/standard/collections/commonly-used-collection-types.md).</span></span>  
  
### <a name="systemcollectionsgeneric"></a><span data-ttu-id="85b27-107">System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="85b27-107">System.Collections.Generic</span></span>  
 <span data-ttu-id="85b27-108">Viele der generischen Auflistungstypen sind direkte Entsprechungen nicht generischer Typen.</span><span class="sxs-lookup"><span data-stu-id="85b27-108">Many of the generic collection types are direct analogs of nongeneric types.</span></span> <span data-ttu-id="85b27-109"><xref:System.Collections.Generic.Dictionary%602> ist eine generische Version von <xref:System.Collections.Hashtable>. Sie verwendet die generische Struktur <xref:System.Collections.Generic.KeyValuePair%602> für die Enumeration anstelle von <xref:System.Collections.DictionaryEntry>.</span><span class="sxs-lookup"><span data-stu-id="85b27-109"><xref:System.Collections.Generic.Dictionary%602> is a generic version of <xref:System.Collections.Hashtable>; it uses the generic structure <xref:System.Collections.Generic.KeyValuePair%602> for enumeration instead of <xref:System.Collections.DictionaryEntry>.</span></span>  
  
 <span data-ttu-id="85b27-110"><xref:System.Collections.Generic.List%601> ist eine generische Version von <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="85b27-110"><xref:System.Collections.Generic.List%601> is a generic version of <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="85b27-111">Es gibt die generischen Klassen <xref:System.Collections.Generic.Queue%601> und <xref:System.Collections.Generic.Stack%601>, die nicht generischen Versionen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="85b27-111">There are generic <xref:System.Collections.Generic.Queue%601> and <xref:System.Collections.Generic.Stack%601> classes that correspond to the nongeneric versions.</span></span>  
  
 <span data-ttu-id="85b27-112">Es gibt generische und nicht generische Versionen von <xref:System.Collections.Generic.SortedList%602>.</span><span class="sxs-lookup"><span data-stu-id="85b27-112">There are generic and nongeneric versions of <xref:System.Collections.Generic.SortedList%602>.</span></span> <span data-ttu-id="85b27-113">Beide Versionen sind eine Mischung aus einem Wörterbuch und einer Liste.</span><span class="sxs-lookup"><span data-stu-id="85b27-113">Both versions are hybrids of a dictionary and a list.</span></span> <span data-ttu-id="85b27-114">Die generische <xref:System.Collections.Generic.SortedDictionary%602>-Klasse ist ein reines Wörterbuch und hat keine nicht generische Entsprechung.</span><span class="sxs-lookup"><span data-stu-id="85b27-114">The <xref:System.Collections.Generic.SortedDictionary%602> generic class is a pure dictionary and has no nongeneric counterpart.</span></span>  
  
 <span data-ttu-id="85b27-115">Die generische <xref:System.Collections.Generic.LinkedList%601>-Klasse ist eine echte verknüpfte Liste.</span><span class="sxs-lookup"><span data-stu-id="85b27-115">The <xref:System.Collections.Generic.LinkedList%601> generic class is a true linked list.</span></span> <span data-ttu-id="85b27-116">Sie hat keine nicht generische Entsprechung.</span><span class="sxs-lookup"><span data-stu-id="85b27-116">It has no nongeneric counterpart.</span></span>  
  
### <a name="systemcollectionsobjectmodel"></a><span data-ttu-id="85b27-117">System.Collections.ObjectModel</span><span class="sxs-lookup"><span data-stu-id="85b27-117">System.Collections.ObjectModel</span></span>  
 <span data-ttu-id="85b27-118">Die generische <xref:System.Collections.ObjectModel.Collection%601>-Klasse stellt eine Basisklasse bereit, aus der Sie Ihre eigenen generischen Auflistungstypen ableiten können.</span><span class="sxs-lookup"><span data-stu-id="85b27-118">The <xref:System.Collections.ObjectModel.Collection%601> generic class provides a base class for deriving your own generic collection types.</span></span> <span data-ttu-id="85b27-119">Die <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>-Klasse bietet eine einfache Möglichkeit, eine schreibgeschützte Auflistung von jedem beliebigen Typ abzuleiten, der die generische <xref:System.Collections.Generic.IList%601>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="85b27-119">The <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class provides an easy way to produce a read-only collection from any type that implements the <xref:System.Collections.Generic.IList%601> generic interface.</span></span> <span data-ttu-id="85b27-120">Die generische <xref:System.Collections.ObjectModel.KeyedCollection%602>-Klasse bietet eine Möglichkeit, Objekte zu speichern, die ihre eigenen Schlüssel enthalten.</span><span class="sxs-lookup"><span data-stu-id="85b27-120">The <xref:System.Collections.ObjectModel.KeyedCollection%602> generic class provides a way to store objects that contain their own keys.</span></span>  
  
## <a name="other-generic-types"></a><span data-ttu-id="85b27-121">Weitere generische Typen</span><span class="sxs-lookup"><span data-stu-id="85b27-121">Other Generic Types</span></span>  
 <span data-ttu-id="85b27-122">Die generische <xref:System.Nullable%601>Struktur ermöglicht es Ihnen, die Werttypen so zu verwenden, als ob ihnen `null` zugewiesen werden könnte.</span><span class="sxs-lookup"><span data-stu-id="85b27-122">The <xref:System.Nullable%601> generic structure allows you to use value types as if they could be assigned `null`.</span></span> <span data-ttu-id="85b27-123">Dies kann nützlich sein, wenn Datenbankabfragen verwendet werden, für die möglicherweise Felder fehlen, die Werttypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="85b27-123">This can be useful when working with database queries, where fields that contain value types can be missing.</span></span> <span data-ttu-id="85b27-124">Der generische Typparameter kann ein beliebiger Werttyp sein.</span><span class="sxs-lookup"><span data-stu-id="85b27-124">The generic type parameter can be any value type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85b27-125">In C# muss <xref:System.Nullable%601> nicht explizit verwendet werden, da die Sprache eine Syntax für NULL-fähige Typen hat.</span><span class="sxs-lookup"><span data-stu-id="85b27-125">In C# it is not necessary to use <xref:System.Nullable%601> explicitly because the language has syntax for nullable types.</span></span>  
  
 <span data-ttu-id="85b27-126">Die generische <xref:System.ArraySegment%601>-Struktur bietet eine Möglichkeit, einen Bereich von Elementen in einem eindimensionalen nullbasierten Array eines beliebigen Typs abzugrenzen.</span><span class="sxs-lookup"><span data-stu-id="85b27-126">The <xref:System.ArraySegment%601> generic structure provides a way to delimit a range of elements within a one-dimensional, zero-based array of any type.</span></span> <span data-ttu-id="85b27-127">Der generische Typparameter ist der Typ der Elemente des Arrays.</span><span class="sxs-lookup"><span data-stu-id="85b27-127">The generic type parameter is the type of the array's elements.</span></span>  
  
 <span data-ttu-id="85b27-128">Wird der generische <xref:System.EventHandler%601>-Delegat verwendet, muss kein Delegattyp zum Behandeln von Ereignissen mehr deklariert werden, wenn das Ereignis dem von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] verwendeten Muster für die Ereignisbehandlung folgt.</span><span class="sxs-lookup"><span data-stu-id="85b27-128">The <xref:System.EventHandler%601> generic delegate eliminates the need to declare a delegate type to handle events, if your event follows the event-handling pattern used by the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="85b27-129">Angenommen, Sie haben die von <xref:System.EventArgs> abgeleitete `MyEventArgs`-Klasse erstellt, um die Daten für das Ereignis zu speichern.</span><span class="sxs-lookup"><span data-stu-id="85b27-129">For example, suppose you have created a `MyEventArgs` class, derived from <xref:System.EventArgs>, to hold the data for your event.</span></span> <span data-ttu-id="85b27-130">Sie können das Ereignis dann wie folgt deklarieren:</span><span class="sxs-lookup"><span data-stu-id="85b27-130">You can then declare the event as follows:</span></span>  
  
 [!code-cpp[Conceptual.Generics.Overview#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Generics.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source2.cs#7)]
 [!code-vb[Conceptual.Generics.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="85b27-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85b27-131">See Also</span></span>  
 <xref:System.Collections.Generic?displayProperty=nameWithType>  
 <xref:System.Collections.ObjectModel?displayProperty=nameWithType>  
 [<span data-ttu-id="85b27-132">Generika</span><span class="sxs-lookup"><span data-stu-id="85b27-132">Generics</span></span>](../../../docs/standard/generics/index.md)  
 [<span data-ttu-id="85b27-133">Generische Delegaten zum Bearbeiten von Arrays und Listen</span><span class="sxs-lookup"><span data-stu-id="85b27-133">Generic Delegates for Manipulating Arrays and Lists</span></span>](../../../docs/standard/generics/delegates-for-manipulating-arrays-and-lists.md)  
 [<span data-ttu-id="85b27-134">Generische Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="85b27-134">Generic Interfaces</span></span>](../../../docs/standard/generics/interfaces.md)
