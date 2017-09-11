---
title: "Verzögerte Ausführung und Auswertung in LINQ to XML (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 8683d1b4-b7ec-407b-be12-906ebe958a09
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 10ecebc2563df5a12b71a743727b1be21b19b671
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-c"></a><span data-ttu-id="09aff-102">Verzögerte Ausführung und Auswertung in LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="09aff-102">Deferred Execution and Lazy Evaluation in LINQ to XML (C#)</span></span>
<span data-ttu-id="09aff-103">Abfrage- und Achsenoperationen werden oft so implementiert, dass sie die verzögerte Ausführung (Deferred Execution) verwenden.</span><span class="sxs-lookup"><span data-stu-id="09aff-103">Query and axis operations are often implemented to use deferred execution.</span></span> <span data-ttu-id="09aff-104">In diesem Thema werden die Voraussetzungen und die Vorteile der verzögerten Ausführung erläutert und einige Überlegungen zur Implementierung angestellt.</span><span class="sxs-lookup"><span data-stu-id="09aff-104">This topic explains the requirements and advantages of deferred execution, and some implementation considerations.</span></span>  
  
## <a name="deferred-execution"></a><span data-ttu-id="09aff-105">Verzögerte Ausführung</span><span class="sxs-lookup"><span data-stu-id="09aff-105">Deferred Execution</span></span>  
 <span data-ttu-id="09aff-106">Verzögerte Ausführung bedeutet, dass die Auswertung eines Ausdrucks so lange hinausgezögert wird, bis dessen *realisierter* Wert tatsächlich benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="09aff-106">Deferred execution means that the evaluation of an expression is delayed until its *realized* value is actually required.</span></span> <span data-ttu-id="09aff-107">Dort, wo große Datensammlungen bearbeitet werden müssen, vor allem in Programmen, die eine Reihe von verketteten Abfragen oder Manipulationen enthalten, kann die verzögerte Ausführung die Arbeitsgeschwindigkeit der Anwendung signifikant erhöhen.</span><span class="sxs-lookup"><span data-stu-id="09aff-107">Deferred execution can greatly improve performance when you have to manipulate large data collections, especially in programs that contain a series of chained queries or manipulations.</span></span> <span data-ttu-id="09aff-108">Im besten Fall muss bei der verzögerten Ausführung lediglich ein Durchlauf durch die Quellauflistung erfolgen.</span><span class="sxs-lookup"><span data-stu-id="09aff-108">In the best case, deferred execution enables only a single iteration through the source collection.</span></span>  
  
 <span data-ttu-id="09aff-109">Die LINQ-Technologien machen von der verzögerten Ausführung umfangreichen Gebrauch, und dies sowohl bei den Membern der <xref:System.Linq?displayProperty=fullName>-Kernklassen als auch bei den Erweiterungsmethoden in den verschiedenen LINQ-Namespaces, z. B. <xref:System.Xml.Linq.Extensions?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="09aff-109">The LINQ technologies make extensive use of deferred execution in both the members of core <xref:System.Linq?displayProperty=fullName> classes and in the extension methods in the various LINQ namespaces, such as <xref:System.Xml.Linq.Extensions?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="09aff-110">Die verzögerte Auswertung wird in der C#-Sprache direkt durch das [yield](../../../../csharp/language-reference/keywords/yield.md)-Schlüsselwort (in Form der `yield-return`-Anweisung) im Iteratorblock unterstützt.</span><span class="sxs-lookup"><span data-stu-id="09aff-110">Deferred execution is supported directly in the C# language by the [yield](../../../../csharp/language-reference/keywords/yield.md) keyword (in the form of the `yield-return` statement) when used within an iterator block.</span></span> <span data-ttu-id="09aff-111">So ein Iterator muss eine Auflistung des Typs <xref:System.Collections.IEnumerator> oder <xref:System.Collections.Generic.IEnumerator%601> (oder eines abgeleiteten Typs) zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="09aff-111">Such an iterator must return a collection of type <xref:System.Collections.IEnumerator> or <xref:System.Collections.Generic.IEnumerator%601> (or a derived type).</span></span>  
  
## <a name="eager-vs-lazy-evaluation"></a><span data-ttu-id="09aff-112">Vergleich von sofortiger Auswertung und verzögerter Auswertung</span><span class="sxs-lookup"><span data-stu-id="09aff-112">Eager vs. Lazy Evaluation</span></span>  
 <span data-ttu-id="09aff-113">Beim Schreiben einer Methode, die die verzögerte Ausführung implementiert, können Sie sich auch überlegen, ob die Methode mit verzögerter Auswertung (Lazy Evaluation) oder sofortiger Auswertung (Eager Evaluation) implementiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="09aff-113">When you write a method that implements deferred execution, you also have to decide whether to implement the method using lazy evaluation or eager evaluation.</span></span>  
  
-   <span data-ttu-id="09aff-114">Bei der *verzögerten Auswertung* wird bei jedem Aufruf des Iterators jeweils ein Element der Quellauflistung verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="09aff-114">In *lazy evaluation*, a single element of the source collection is processed during each call to the iterator.</span></span> <span data-ttu-id="09aff-115">Dies ist die übliche Art und Weise, in der Iteratoren implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="09aff-115">This is the typical way in which iterators are implemented.</span></span>  
  
-   <span data-ttu-id="09aff-116">Bei der *sofortigen Auswertung* wird beim ersten Aufruf des Iterators die gesamte Auflistung verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="09aff-116">In *eager evaluation*, the first call to the iterator will result in the entire collection being processed.</span></span> <span data-ttu-id="09aff-117">Eventuell ist auch eine temporäre Kopie der Quellauflistung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="09aff-117">A temporary copy of the source collection might also be required.</span></span> <span data-ttu-id="09aff-118">So muss z. B. die <xref:System.Linq.Enumerable.OrderBy%2A>-Methode die gesamte Auflistung erst sortieren, bevor sie das erste Element zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="09aff-118">For example, the <xref:System.Linq.Enumerable.OrderBy%2A> method has to sort the entire collection before it returns the first element.</span></span>  
  
 <span data-ttu-id="09aff-119">Die verzögerte Auswertung hat in der Regel eine höhere Arbeitsgeschwindigkeit zur Folge, weil die Verarbeitung des Mehraufwands gleichmäßig auf die Auswertung der Auflistung verteilt und die Verwendung temporärer Daten minimiert wird.</span><span class="sxs-lookup"><span data-stu-id="09aff-119">Lazy evaluation usually yields better performance because it distributes overhead processing evenly throughout the evaluation of the collection and minimizes the use of temporary data.</span></span> <span data-ttu-id="09aff-120">Bei einigen Operationen führt aber natürlich kein Weg an der Materialisierung der Zwischenergebnisse vorbei.</span><span class="sxs-lookup"><span data-stu-id="09aff-120">Of course, for some operations, there is no other option than to materialize intermediate results.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="09aff-121">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="09aff-121">Next Steps</span></span>  
 <span data-ttu-id="09aff-122">Die verzögerte Ausführung ist Gegenstand des nächsten Themas dieses Lernprogramms:</span><span class="sxs-lookup"><span data-stu-id="09aff-122">The next topic in this tutorial illustrates deferred execution:</span></span>  
  
-   [<span data-ttu-id="09aff-123">Beispiel für eine verzögerte Ausführung (C#)</span><span class="sxs-lookup"><span data-stu-id="09aff-123">Deferred Execution Example (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/deferred-execution-example.md)  
  
## <a name="see-also"></a><span data-ttu-id="09aff-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09aff-124">See Also</span></span>  
 <span data-ttu-id="09aff-125">[Tutorial: Verketten von Abfragen (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md) </span><span class="sxs-lookup"><span data-stu-id="09aff-125">[Tutorial: Chaining Queries Together (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md) </span></span>  
 <span data-ttu-id="09aff-126">[Konzepte und Terminologie (funktionale Transformation) (C#)](../../../../csharp/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="09aff-126">[Concepts and Terminology (Functional Transformation) (C#)](../../../../csharp/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md) </span></span>  
 <span data-ttu-id="09aff-127">[Aggregationsvorgänge (C#)](../../../../csharp/programming-guide/concepts/linq/aggregation-operations.md) </span><span class="sxs-lookup"><span data-stu-id="09aff-127">[Aggregation Operations (C#)](../../../../csharp/programming-guide/concepts/linq/aggregation-operations.md) </span></span>  
 [<span data-ttu-id="09aff-128">yield</span><span class="sxs-lookup"><span data-stu-id="09aff-128">yield</span></span>](../../../../csharp/language-reference/keywords/yield.md)

