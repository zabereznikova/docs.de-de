---
title: Vorteile von Generika (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], benefits
ms.assetid: 80f037cd-9ea7-48be-bfc1-219bfb2d4277
caps.latest.revision: 23
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
ms.openlocfilehash: 8b05a3a695064764618564293e6ccd92e2ce60be
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="benefits-of-generics-c-programming-guide"></a><span data-ttu-id="8e839-102">Vorteile von Generika (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8e839-102">Benefits of Generics (C# Programming Guide)</span></span>
<span data-ttu-id="8e839-103">Generika bieten die Lösung für eine Einschränkung in früheren Versionen der Common Language Runtime und der C#-Sprache, bei der Generalisierung durch die Umwandlung von Typen in den und aus dem universellen Basistyp <xref:System.Object> erfolgt.</span><span class="sxs-lookup"><span data-stu-id="8e839-103">Generics provide the solution to a limitation in earlier versions of the common language runtime and the C# language in which generalization is accomplished by casting types to and from the universal base type <xref:System.Object>.</span></span> <span data-ttu-id="8e839-104">Durch Erstellen einer generischen Klasse können Sie eine Auflistung erstellen, die zur Kompilierzeit typsicher ist.</span><span class="sxs-lookup"><span data-stu-id="8e839-104">By creating a generic class, you can create a collection that is type-safe at compile-time.</span></span>  
  
 <span data-ttu-id="8e839-105">Die Einschränkungen bei der Verwendung nicht generischer Auflistungsklassen können durch das Schreiben eines kurzen Programms veranschaulicht werden, das die Auflistungsklasse <xref:System.Collections.ArrayList> aus der .NET Framework-Klassenbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="8e839-105">The limitations of using non-generic collection classes can be demonstrated by writing a short program that uses the <xref:System.Collections.ArrayList> collection class from the .NET Framework class library.</span></span> <span data-ttu-id="8e839-106"><xref:System.Collections.ArrayList> ist eine äußerst praktische Auflistungsklasse, die unverändert verwendet werden kann, um einen beliebigen Verweis- oder Werttyp zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8e839-106"><xref:System.Collections.ArrayList> is a highly convenient collection class that can be used without modification to store any reference or value type.</span></span>  
  
 <span data-ttu-id="8e839-107">[!code-cs[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8e839-107">[!code-cs[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]</span></span>  
  
 <span data-ttu-id="8e839-108">Aber diese Vereinfachung ist mit Nachteilen verbunden.</span><span class="sxs-lookup"><span data-stu-id="8e839-108">But this convenience comes at a cost.</span></span> <span data-ttu-id="8e839-109">Jeder Verweis- oder Werttyp, der zu einem <xref:System.Collections.ArrayList>-Objekt hinzugefügt wird, wird implizit nach oben in <xref:System.Object> umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="8e839-109">Any reference or value type that is added to an <xref:System.Collections.ArrayList> is implicitly upcast to <xref:System.Object>.</span></span> <span data-ttu-id="8e839-110">Wenn es sich bei den Elementen um Werttypen handelt, müssen Sie mittels Boxing geschachtelt werden, wenn sie zur Liste hinzugefügt werden, und mittels Unboxing wieder entpackt werden, wenn sie abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8e839-110">If the items are value types, they must be boxed when they are added to the list, and unboxed when they are retrieved.</span></span> <span data-ttu-id="8e839-111">Sowohl die Umwandlung von Typen als auch das Boxing und Unboxing beeinträchtigen die Leistung; die Auswirkung von Boxing und Unboxing kann sehr groß sein, wenn Sie lange Auflistungen durchlaufen müssen.</span><span class="sxs-lookup"><span data-stu-id="8e839-111">Both the casting and the boxing and unboxing operations decrease performance; the effect of boxing and unboxing can be very significant in scenarios where you must iterate over large collections.</span></span>  
  
 <span data-ttu-id="8e839-112">Die andere Einschränkung ist die fehlende Typüberprüfung zur Kompilierzeit; da ein <xref:System.Collections.ArrayList>-Objekt alles in <xref:System.Object> umwandelt, kann zur Kompilierzeit nicht vermieden werden, dass der Clientcode etwas wie das Folgende macht:</span><span class="sxs-lookup"><span data-stu-id="8e839-112">The other limitation is lack of compile-time type checking; because an <xref:System.Collections.ArrayList> casts everything to <xref:System.Object>, there is no way at compile-time to prevent client code from doing something such as this:</span></span>  
  
 <span data-ttu-id="8e839-113">[!code-cs[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8e839-113">[!code-cs[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]</span></span>  
  
 <span data-ttu-id="8e839-114">Zwar ist das Erstellen einer heterogenen Auflistung durchaus akzeptabel und manchmal beabsichtigt, aber das Kombinieren von Zeichenfolgen und `ints` in einem einzigen <xref:System.Collections.ArrayList>-Objekt ist meist eher ein Programmierfehler, der bis zur Laufzeit nicht erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="8e839-114">Although perfectly acceptable and sometimes intentional if you are creating a heterogeneous collection, combining strings and `ints` in a single <xref:System.Collections.ArrayList> is more likely to be a programming error, and this error will not be detected until runtime.</span></span>  
  
 <span data-ttu-id="8e839-115">In den Versionen 1.0 und 1.1 der C#-Sprache können Sie generalisierten Code in der Auflistung der .NET Framework-Basisklassenbibliothek nur vermeiden, wenn Sie Ihre eigenen typspezifischen Auflistungen schreiben.</span><span class="sxs-lookup"><span data-stu-id="8e839-115">In versions 1.0 and 1.1 of the C# language, you could avoid the dangers of generalized code in the .NET Framework base class library collection classes only by writing your own type specific collections.</span></span> <span data-ttu-id="8e839-116">Da eine solche Klasse nur für einen Datentyp verwendet werden kann, verlieren Sie so aber die Vorteile der Generalisierung und müssen die Klasse für jeden Typ, der gespeichert wird, umschreiben.</span><span class="sxs-lookup"><span data-stu-id="8e839-116">Of course, because such a class is not reusable for more than one data type, you lose the benefits of generalization, and you have to rewrite the class for each type that will be stored.</span></span>  
  
 <span data-ttu-id="8e839-117">Was <xref:System.Collections.ArrayList> und ähnliche Klassen eigentlich benötigen, ist eine Möglichkeit für den Clientcode, instanzweise den zu verwendenden Datentyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8e839-117">What <xref:System.Collections.ArrayList> and other similar classes really need is a way for client code to specify, on a per-instance basis, the particular data type that they intend to use.</span></span> <span data-ttu-id="8e839-118">Dann wäre keine Typumwandlung nach oben zu `T:System.Object` mehr nötig, und der Compiler könnte eine Typüberprüfung durchführen.</span><span class="sxs-lookup"><span data-stu-id="8e839-118">That would eliminate the need for the upcast to `T:System.Object` and would also make it possible for the compiler to do type checking.</span></span> <span data-ttu-id="8e839-119">Das heißt, dass <xref:System.Collections.ArrayList> einen Typparameter benötigt.</span><span class="sxs-lookup"><span data-stu-id="8e839-119">In other words, <xref:System.Collections.ArrayList> needs a type parameter.</span></span> <span data-ttu-id="8e839-120">Genau das bieten Generika.</span><span class="sxs-lookup"><span data-stu-id="8e839-120">That is exactly what generics provide.</span></span> <span data-ttu-id="8e839-121">In der generischen <xref:System.Collections.Generic.List%601>-Auflistung im `N:System.Collections.Generic`-Namespace sieht der gleiche Vorgang des Hinzufügens von Elementen zur Auflistung ungefähr so aus:</span><span class="sxs-lookup"><span data-stu-id="8e839-121">In the generic <xref:System.Collections.Generic.List%601> collection, in the `N:System.Collections.Generic` namespace, the same operation of adding items to the collection resembles this:</span></span>  
  
 <span data-ttu-id="8e839-122">[!code-cs[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="8e839-122">[!code-cs[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]</span></span>  
  
 <span data-ttu-id="8e839-123">Bei Clientcode ist im Vergleich von <xref:System.Collections.Generic.List%601> mit <xref:System.Collections.ArrayList> als Syntax lediglich das Typargument in der Deklaration und Instanziierung hinzugekommen.</span><span class="sxs-lookup"><span data-stu-id="8e839-123">For client code, the only added syntax with <xref:System.Collections.Generic.List%601> compared to <xref:System.Collections.ArrayList> is the type argument in the declaration and instantiation.</span></span> <span data-ttu-id="8e839-124">Zwar ist die Codierung etwas komplexer, aber dafür können Sie eine Liste erstellen, die nicht nur sicherer als <xref:System.Collections.ArrayList> ist, sondern auch bedeutend schneller, vor allem wenn es sich bei den Listenelementen um Werttypen handelt.</span><span class="sxs-lookup"><span data-stu-id="8e839-124">In return for this slightly more coding complexity, you can create a list that is not only safer than <xref:System.Collections.ArrayList>, but also significantly faster, especially when the list items are value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e839-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e839-125">See Also</span></span>  
 <span data-ttu-id="8e839-126"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="8e839-126"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="8e839-127">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8e839-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8e839-128">[Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="8e839-128">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 <span data-ttu-id="8e839-129">[Boxing und Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md) </span><span class="sxs-lookup"><span data-stu-id="8e839-129">[Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md) </span></span>  
 [<span data-ttu-id="8e839-130">Best Practices für Auflistungen</span><span class="sxs-lookup"><span data-stu-id="8e839-130">Collections Best Practices</span></span>](http://go.microsoft.com/fwlink/?LinkId=112403)

