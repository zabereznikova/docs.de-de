---
title: Generische Auflistungen in .NET
ms.date: 02/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET], collections
- generic collections [.NET]
- generic types [.NET]
ms.assetid: 5b646751-6ab7-465c-916c-b1a76aefa9f5
ms.openlocfilehash: 956db9ace4ae00062accdd6e80c7911aaac7523f
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93064248"
---
# <a name="generic-collections-in-net"></a><span data-ttu-id="01705-102">Generische Sammlungen in .NET</span><span class="sxs-lookup"><span data-stu-id="01705-102">Generic collections in .NET</span></span>

 <span data-ttu-id="01705-103">Die Klassenbibliothek von .NET enthält eine Reihe generischer Auflistungsklassen in den Namespaces <xref:System.Collections.Generic> und <xref:System.Collections.ObjectModel>.</span><span class="sxs-lookup"><span data-stu-id="01705-103">The .NET class library provides a number of generic collection classes in the <xref:System.Collections.Generic> and <xref:System.Collections.ObjectModel> namespaces.</span></span> <span data-ttu-id="01705-104">Ausführliche Informationen zu diesen Klassen finden Sie unter [Häufig verwendete Auflistungstypen](../collections/commonly-used-collection-types.md).</span><span class="sxs-lookup"><span data-stu-id="01705-104">For more detailed information about these classes, see [Commonly Used Collection Types](../collections/commonly-used-collection-types.md).</span></span>  
  
## <a name="systemcollectionsgeneric"></a><span data-ttu-id="01705-105">System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="01705-105">System.Collections.Generic</span></span>

 <span data-ttu-id="01705-106">Viele der generischen Auflistungstypen sind direkte Entsprechungen nicht generischer Typen.</span><span class="sxs-lookup"><span data-stu-id="01705-106">Many of the generic collection types are direct analogs of nongeneric types.</span></span> <span data-ttu-id="01705-107"><xref:System.Collections.Generic.Dictionary%602> ist eine generische Version von <xref:System.Collections.Hashtable>. Sie verwendet die generische Struktur <xref:System.Collections.Generic.KeyValuePair%602> für die Enumeration anstelle von <xref:System.Collections.DictionaryEntry>.</span><span class="sxs-lookup"><span data-stu-id="01705-107"><xref:System.Collections.Generic.Dictionary%602> is a generic version of <xref:System.Collections.Hashtable>; it uses the generic structure <xref:System.Collections.Generic.KeyValuePair%602> for enumeration instead of <xref:System.Collections.DictionaryEntry>.</span></span>  
  
 <span data-ttu-id="01705-108"><xref:System.Collections.Generic.List%601> ist eine generische Version von <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="01705-108"><xref:System.Collections.Generic.List%601> is a generic version of <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="01705-109">Es gibt die generischen Klassen <xref:System.Collections.Generic.Queue%601> und <xref:System.Collections.Generic.Stack%601>, die nicht generischen Versionen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="01705-109">There are generic <xref:System.Collections.Generic.Queue%601> and <xref:System.Collections.Generic.Stack%601> classes that correspond to the nongeneric versions.</span></span>  
  
 <span data-ttu-id="01705-110">Es gibt generische und nicht generische Versionen von <xref:System.Collections.Generic.SortedList%602>.</span><span class="sxs-lookup"><span data-stu-id="01705-110">There are generic and nongeneric versions of <xref:System.Collections.Generic.SortedList%602>.</span></span> <span data-ttu-id="01705-111">Beide Versionen sind eine Mischung aus einem Wörterbuch und einer Liste.</span><span class="sxs-lookup"><span data-stu-id="01705-111">Both versions are hybrids of a dictionary and a list.</span></span> <span data-ttu-id="01705-112">Die generische <xref:System.Collections.Generic.SortedDictionary%602>-Klasse ist ein reines Wörterbuch und hat keine nicht generische Entsprechung.</span><span class="sxs-lookup"><span data-stu-id="01705-112">The <xref:System.Collections.Generic.SortedDictionary%602> generic class is a pure dictionary and has no nongeneric counterpart.</span></span>  
  
 <span data-ttu-id="01705-113">Die generische <xref:System.Collections.Generic.LinkedList%601>-Klasse ist eine echte verknüpfte Liste.</span><span class="sxs-lookup"><span data-stu-id="01705-113">The <xref:System.Collections.Generic.LinkedList%601> generic class is a true linked list.</span></span> <span data-ttu-id="01705-114">Sie hat keine nicht generische Entsprechung.</span><span class="sxs-lookup"><span data-stu-id="01705-114">It has no nongeneric counterpart.</span></span>  
  
## <a name="systemcollectionsobjectmodel"></a><span data-ttu-id="01705-115">System.Collections.ObjectModel</span><span class="sxs-lookup"><span data-stu-id="01705-115">System.Collections.ObjectModel</span></span>

 <span data-ttu-id="01705-116">Die generische <xref:System.Collections.ObjectModel.Collection%601>-Klasse stellt eine Basisklasse bereit, aus der Sie Ihre eigenen generischen Auflistungstypen ableiten können.</span><span class="sxs-lookup"><span data-stu-id="01705-116">The <xref:System.Collections.ObjectModel.Collection%601> generic class provides a base class for deriving your own generic collection types.</span></span> <span data-ttu-id="01705-117">Die <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>-Klasse bietet eine einfache Möglichkeit, eine schreibgeschützte Auflistung von jedem beliebigen Typ abzuleiten, der die generische <xref:System.Collections.Generic.IList%601>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="01705-117">The <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class provides an easy way to produce a read-only collection from any type that implements the <xref:System.Collections.Generic.IList%601> generic interface.</span></span> <span data-ttu-id="01705-118">Die generische <xref:System.Collections.ObjectModel.KeyedCollection%602>-Klasse bietet eine Möglichkeit, Objekte zu speichern, die ihre eigenen Schlüssel enthalten.</span><span class="sxs-lookup"><span data-stu-id="01705-118">The <xref:System.Collections.ObjectModel.KeyedCollection%602> generic class provides a way to store objects that contain their own keys.</span></span>  
  
## <a name="other-generic-types"></a><span data-ttu-id="01705-119">Andere generische Typen</span><span class="sxs-lookup"><span data-stu-id="01705-119">Other generic types</span></span>

 <span data-ttu-id="01705-120">Die generische <xref:System.Nullable%601>Struktur ermöglicht es Ihnen, die Werttypen so zu verwenden, als ob ihnen `null` zugewiesen werden könnte.</span><span class="sxs-lookup"><span data-stu-id="01705-120">The <xref:System.Nullable%601> generic structure allows you to use value types as if they could be assigned `null`.</span></span> <span data-ttu-id="01705-121">Dies kann nützlich sein, wenn Datenbankabfragen verwendet werden, für die möglicherweise Felder fehlen, die Werttypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="01705-121">This can be useful when working with database queries, where fields that contain value types can be missing.</span></span> <span data-ttu-id="01705-122">Der generische Typparameter kann ein beliebiger Werttyp sein.</span><span class="sxs-lookup"><span data-stu-id="01705-122">The generic type parameter can be any value type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01705-123">In C# und Visual Basic muss <xref:System.Nullable%601> nicht explizit verwendet werden, weil die Sprache eine Syntax für NULL-fähige Typen umfasst.</span><span class="sxs-lookup"><span data-stu-id="01705-123">In C# and Visual Basic, it is not necessary to use <xref:System.Nullable%601> explicitly because the language has syntax for nullable types.</span></span> <span data-ttu-id="01705-124">Siehe [Nullable-Werttypen (C#-Referenz)](../../csharp/language-reference/builtin-types/nullable-value-types.md) und [Nullwerte zulassende Werttypen (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="01705-124">See [Nullable value types (C# reference)](../../csharp/language-reference/builtin-types/nullable-value-types.md) and [Nullable value types (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span></span>
  
 <span data-ttu-id="01705-125">Die generische <xref:System.ArraySegment%601>-Struktur bietet eine Möglichkeit, einen Bereich von Elementen in einem eindimensionalen nullbasierten Array eines beliebigen Typs abzugrenzen.</span><span class="sxs-lookup"><span data-stu-id="01705-125">The <xref:System.ArraySegment%601> generic structure provides a way to delimit a range of elements within a one-dimensional, zero-based array of any type.</span></span> <span data-ttu-id="01705-126">Der generische Typparameter ist der Typ der Elemente des Arrays.</span><span class="sxs-lookup"><span data-stu-id="01705-126">The generic type parameter is the type of the array's elements.</span></span>  
  
 <span data-ttu-id="01705-127">Wird der generische <xref:System.EventHandler%601>-Delegat verwendet, muss kein Delegattyp zum Behandeln von Ereignissen mehr deklariert werden, wenn das Ereignis dem von .NET verwendeten Muster für die Ereignisbehandlung folgt.</span><span class="sxs-lookup"><span data-stu-id="01705-127">The <xref:System.EventHandler%601> generic delegate eliminates the need to declare a delegate type to handle events, if your event follows the event-handling pattern used by .NET.</span></span> <span data-ttu-id="01705-128">Angenommen, Sie haben die von <xref:System.EventArgs> abgeleitete `MyEventArgs`-Klasse erstellt, um die Daten für das Ereignis zu speichern.</span><span class="sxs-lookup"><span data-stu-id="01705-128">For example, suppose you have created a `MyEventArgs` class, derived from <xref:System.EventArgs>, to hold the data for your event.</span></span> <span data-ttu-id="01705-129">Sie können das Ereignis dann wie folgt deklarieren:</span><span class="sxs-lookup"><span data-stu-id="01705-129">You can then declare the event as follows:</span></span>  
  
 [!code-cpp[Conceptual.Generics.Overview#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Generics.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source2.cs#7)]
 [!code-vb[Conceptual.Generics.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="01705-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01705-130">See also</span></span>

- <xref:System.Collections.Generic?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel?displayProperty=nameWithType>
- [<span data-ttu-id="01705-131">Generics</span><span class="sxs-lookup"><span data-stu-id="01705-131">Generics</span></span>](index.md)
- [<span data-ttu-id="01705-132">Generische Delegaten zum Bearbeiten von Arrays und Listen</span><span class="sxs-lookup"><span data-stu-id="01705-132">Generic Delegates for Manipulating Arrays and Lists</span></span>](delegates-for-manipulating-arrays-and-lists.md)
- [<span data-ttu-id="01705-133">Generische Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="01705-133">Generic Interfaces</span></span>](interfaces.md)
