---
title: "Auswählen zwischen Klasse und Struktur"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- class library design guidelines [.NET Framework], classes
- structures [.NET Framework], vs. classes
- classes [.NET Framework], design guidelines
- type design guidelines, structures
- structures [.NET Framework], design guidelines
- classes [.NET Framework], vs. structures
- type design guidelines, classes
ms.assetid: f8b8ec9b-0ba7-4dea-aadf-a93395cd804f
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df6659853e9c410ece3233cfa630c9066303a871
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="choosing-between-class-and-struct"></a><span data-ttu-id="7f2c8-102">Auswählen zwischen Klasse und Struktur</span><span class="sxs-lookup"><span data-stu-id="7f2c8-102">Choosing Between Class and Struct</span></span>
<span data-ttu-id="7f2c8-103">Eine der grundlegenden Designentscheidungen, die jede Framework Designer portalclient ist, ob einen Typ als Klasse (ein Verweistyp) oder als eine Struktur (Werttyp) entworfen.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-103">One of the basic design decisions every framework designer faces is whether to design a type as a class (a reference type) or as a struct (a value type).</span></span> <span data-ttu-id="7f2c8-104">Die Kenntnis der Unterschiede im Verhalten von Verweistypen und Werttypen ist in dieser Auswahl entscheidend.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-104">Good understanding of the differences in the behavior of reference types and value types is crucial in making this choice.</span></span>  
  
 <span data-ttu-id="7f2c8-105">Die erste der Unterschied zwischen der Referenztypen und Werttypen, die wir in Betracht ziehen, besteht darin, dass die Verweistypen sind, auf dem Heap reserviert und Garbage Collection, wohingegen Werttypen entweder auf dem Stapel zugeordnet werden oder Inline im mit Typen und freigegeben, wenn der Stapel Entlädt oder wenn ihrem enthaltenden Typ Ruft die Zuordnung aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-105">The first difference between reference types and value types we will consider is that reference types are allocated on the heap and garbage-collected, whereas value types are allocated either on the stack or inline in containing types and deallocated when the stack unwinds or when their containing type gets deallocated.</span></span> <span data-ttu-id="7f2c8-106">Daher werden speicherzuordnungen und Aufhebungen von Werttypen im Allgemeinen günstiger als speicherzuordnungen und Aufhebungen von Verweistypen sind.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-106">Therefore, allocations and deallocations of value types are in general cheaper than allocations and deallocations of reference types.</span></span>  
  
 <span data-ttu-id="7f2c8-107">Als Nächstes Arrays von Typen sind Verweisdaten Out-of-Line, d. h. das Array, das Elemente sind nur Verweise auf Instanzen des Verweistyps befinden, auf dem Heap zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-107">Next, arrays of reference types are allocated out-of-line, meaning the array elements are just references to instances of the reference type residing on the heap.</span></span> <span data-ttu-id="7f2c8-108">Wert Typ Arrays sind Inline, was bedeutet, dass die Elemente des Arrays die eigentlichen Instanzen des Werttyps sind zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-108">Value type arrays are allocated inline, meaning that the array elements are the actual instances of the value type.</span></span> <span data-ttu-id="7f2c8-109">Aus diesem Grund werden speicherzuordnungen und Aufhebungen von Wert Typ Arrays weitaus günstigere als speicherzuordnungen und Aufhebungen von Verweis Typ Arrays.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-109">Therefore, allocations and deallocations of value type arrays are much cheaper than allocations and deallocations of reference type arrays.</span></span> <span data-ttu-id="7f2c8-110">Darüber hinaus weisen Wert Typ Arrays in den meisten Fällen wesentlich bessere Positionierung von Verweisen auf.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-110">In addition, in a majority of cases value type arrays exhibit much better locality of reference.</span></span>  
  
 <span data-ttu-id="7f2c8-111">Nächste Unterschied bezieht sich auf die speicherauslastung.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-111">The next difference is related to memory usage.</span></span> <span data-ttu-id="7f2c8-112">Werttypen Abrufen mittels Boxing konvertiert, wenn ein Verweistyp oder eine der Schnittstellen, die sie implementieren umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-112">Value types get boxed when cast to a reference type or one of the interfaces they implement.</span></span> <span data-ttu-id="7f2c8-113">Erhalten sie mittels Unboxing konvertiert Wenn wieder auf den Werttyp umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-113">They get unboxed when cast back to the value type.</span></span> <span data-ttu-id="7f2c8-114">Da sind Objekte, die auf dem Heap zugeordnet sind und Garbage Collection, viel mit Boxing und unboxing können sich negativ auf dem Heap der Garbage Collector und letztlich die Leistung der Anwendung verfügen.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-114">Because boxes are objects that are allocated on the heap and are garbage-collected, too much boxing and unboxing can have a negative impact on the heap, the garbage collector, and ultimately the performance of the application.</span></span>  <span data-ttu-id="7f2c8-115">Im Gegensatz dazu erfolgt keine solche Boxing wie Verweistypen umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-115">In contrast, no such boxing occurs as reference types are cast.</span></span>  
  
 <span data-ttu-id="7f2c8-116">Im nächsten Schritt kopieren Verweis Zuweisung den Verweis, während der Zuweisung Wert den gesamten Wert kopieren.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-116">Next, reference type assignments copy the reference, whereas value type assignments copy the entire value.</span></span> <span data-ttu-id="7f2c8-117">Daher sind Zuweisungen von großen Verweistypen günstiger als Zuweisungen von Datentypen mit umfangreichen Werten.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-117">Therefore, assignments of large reference types are cheaper than assignments of large value types.</span></span>  
  
 <span data-ttu-id="7f2c8-118">Schließlich werden die Verweistypen als Verweis übergeben, während Werttypen als Wert übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-118">Finally, reference types are passed by reference, whereas value types are passed by value.</span></span> <span data-ttu-id="7f2c8-119">Änderungen an den eine Instanz eines Verweistyps betreffen alle Verweise auf die Instanz verweist.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-119">Changes to an instance of a reference type affect all references pointing to the instance.</span></span> <span data-ttu-id="7f2c8-120">Wert von Typinstanzen werden kopiert, wenn sie als Wert übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-120">Value type instances are copied when they are passed by value.</span></span> <span data-ttu-id="7f2c8-121">Wenn eine Instanz eines Werttyps geändert wird, beeinflusst natürlich nicht seine Kopien.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-121">When an instance of a value type is changed, it of course does not affect any of its copies.</span></span> <span data-ttu-id="7f2c8-122">Da die Kopien werden nicht explizit vom Benutzer erstellt, aber es werden implizit erstellt, wenn Argumente übergeben oder zurückgeben Werte zurückgegeben werden, können Werttypen, die geändert werden können für viele Benutzer verwirrend sein.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-122">Because the copies are not created explicitly by the user but are implicitly created when arguments are passed or return values are returned, value types that can be changed can be confusing to many users.</span></span> <span data-ttu-id="7f2c8-123">Aus diesem Grund sollten Werttypen unveränderlich sein.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-123">Therefore, value types should be immutable.</span></span>  
  
 <span data-ttu-id="7f2c8-124">Als Faustregel gilt sollte die meisten Typen in einem Framework Klassen sein.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-124">As a rule of thumb, the majority of types in a framework should be classes.</span></span> <span data-ttu-id="7f2c8-125">Es gibt jedoch einige Situationen, in denen die Merkmale eines Werttyps besser geeignet ist, verwenden von Strukturen zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-125">There are, however, some situations in which the characteristics of a value type make it more appropriate to use structs.</span></span>  
  
 <span data-ttu-id="7f2c8-126">**✓ GGF.** eine Struktur anstelle einer Klasse definieren, wenn Instanzen des Typs klein und im Allgemeinen kurzlebig sind oder in anderen Objekten eingebettet sind.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-126">**✓ CONSIDER** defining a struct instead of a class if instances of the type are small and commonly short-lived or are commonly embedded in other objects.</span></span>  
  
 <span data-ttu-id="7f2c8-127">**X vermeiden** eine Struktur definieren, es sei denn, der Typ aller folgende Merkmale aufweist:</span><span class="sxs-lookup"><span data-stu-id="7f2c8-127">**X AVOID** defining a struct unless the type has all of the following characteristics:</span></span>  
  
-   <span data-ttu-id="7f2c8-128">Logisch stellt dar, einen einzelnen Wert, der ähnlich wie primitive Typen (`int`, `double`usw..).</span><span class="sxs-lookup"><span data-stu-id="7f2c8-128">It logically represents a single value, similar to primitive types (`int`, `double`, etc.).</span></span>  
  
-   <span data-ttu-id="7f2c8-129">Es wurde eine Instanzgröße unter 16 Bytes.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-129">It has an instance size under 16 bytes.</span></span>  
  
-   <span data-ttu-id="7f2c8-130">Er ist unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-130">It is immutable.</span></span>  
  
-   <span data-ttu-id="7f2c8-131">Es wird kein häufig geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-131">It will not have to be boxed frequently.</span></span>  
  
 <span data-ttu-id="7f2c8-132">In allen anderen Fällen sollten Sie die Typen als Klassen definieren.</span><span class="sxs-lookup"><span data-stu-id="7f2c8-132">In all other cases, you should define your types as classes.</span></span>  
  
 <span data-ttu-id="7f2c8-133">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="7f2c8-133">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="7f2c8-134">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="7f2c8-134">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f2c8-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f2c8-135">See Also</span></span>  
 [<span data-ttu-id="7f2c8-136">Typ-Entwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="7f2c8-136">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="7f2c8-137">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="7f2c8-137">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
