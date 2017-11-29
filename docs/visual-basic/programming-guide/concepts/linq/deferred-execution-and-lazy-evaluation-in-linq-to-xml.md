---
title: "Verzögerte Ausführung und verzögerte Auswertung in LINQ to XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31998eed-b95e-47fb-a865-9de1f337d1fb
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3a465c4448157505a42db57202298cb18e44a562
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-visual-basic"></a><span data-ttu-id="131ae-102">Verzögerte Ausführung und verzögerte Auswertung in LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="131ae-102">Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)</span></span>
<span data-ttu-id="131ae-103">Abfrage- und Achsenoperationen werden oft so implementiert, dass sie die verzögerte Ausführung (Deferred Execution) verwenden.</span><span class="sxs-lookup"><span data-stu-id="131ae-103">Query and axis operations are often implemented to use deferred execution.</span></span> <span data-ttu-id="131ae-104">In diesem Thema werden die Voraussetzungen und die Vorteile der verzögerten Ausführung erläutert und einige Überlegungen zur Implementierung angestellt.</span><span class="sxs-lookup"><span data-stu-id="131ae-104">This topic explains the requirements and advantages of deferred execution, and some implementation considerations.</span></span>  
  
## <a name="deferred-execution"></a><span data-ttu-id="131ae-105">Verzögerte Ausführung</span><span class="sxs-lookup"><span data-stu-id="131ae-105">Deferred Execution</span></span>  
 <span data-ttu-id="131ae-106">Verzögerte Ausführung bedeutet, dass die Auswertung eines Ausdrucks so lange hinausgezögert wird, bis dessen *realisierter* Wert tatsächlich benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="131ae-106">Deferred execution means that the evaluation of an expression is delayed until its *realized* value is actually required.</span></span> <span data-ttu-id="131ae-107">Dort, wo große Datensammlungen bearbeitet werden müssen, vor allem in Programmen, die eine Reihe von verketteten Abfragen oder Manipulationen enthalten, kann die verzögerte Ausführung die Arbeitsgeschwindigkeit der Anwendung signifikant erhöhen.</span><span class="sxs-lookup"><span data-stu-id="131ae-107">Deferred execution can greatly improve performance when you have to manipulate large data collections, especially in programs that contain a series of chained queries or manipulations.</span></span> <span data-ttu-id="131ae-108">Im besten Fall muss bei der verzögerten Ausführung lediglich ein Durchlauf durch die Quellauflistung erfolgen.</span><span class="sxs-lookup"><span data-stu-id="131ae-108">In the best case, deferred execution enables only a single iteration through the source collection.</span></span>  
  
 <span data-ttu-id="131ae-109">Die LINQ-Technologien machen von der verzögerten Ausführung umfangreichen Gebrauch, und dies sowohl bei den Membern der <xref:System.Linq?displayProperty=nameWithType>-Kernklassen als auch bei den Erweiterungsmethoden in den verschiedenen LINQ-Namespaces, z. B. <xref:System.Xml.Linq.Extensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="131ae-109">The LINQ technologies make extensive use of deferred execution in both the members of core <xref:System.Linq?displayProperty=nameWithType> classes and in the extension methods in the various LINQ namespaces, such as <xref:System.Xml.Linq.Extensions?displayProperty=nameWithType>.</span></span>  
  
## <a name="eager-vs-lazy-evaluation"></a><span data-ttu-id="131ae-110">Vergleich von sofortiger Auswertung und verzögerter Auswertung</span><span class="sxs-lookup"><span data-stu-id="131ae-110">Eager vs. Lazy Evaluation</span></span>  
 <span data-ttu-id="131ae-111">Beim Schreiben einer Methode, die die verzögerte Ausführung implementiert, können Sie sich auch überlegen, ob die Methode mit verzögerter Auswertung (Lazy Evaluation) oder sofortiger Auswertung (Eager Evaluation) implementiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="131ae-111">When you write a method that implements deferred execution, you also have to decide whether to implement the method using lazy evaluation or eager evaluation.</span></span>  
  
-   <span data-ttu-id="131ae-112">Bei der *verzögerten Auswertung* wird bei jedem Aufruf des Iterators jeweils ein Element der Quellauflistung verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="131ae-112">In *lazy evaluation*, a single element of the source collection is processed during each call to the iterator.</span></span> <span data-ttu-id="131ae-113">Dies ist die übliche Art und Weise, in der Iteratoren implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="131ae-113">This is the typical way in which iterators are implemented.</span></span>  
  
-   <span data-ttu-id="131ae-114">Bei der *sofortigen Auswertung* wird beim ersten Aufruf des Iterators die gesamte Auflistung verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="131ae-114">In *eager evaluation*, the first call to the iterator will result in the entire collection being processed.</span></span> <span data-ttu-id="131ae-115">Eventuell ist auch eine temporäre Kopie der Quellauflistung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="131ae-115">A temporary copy of the source collection might also be required.</span></span> <span data-ttu-id="131ae-116">So muss z. B. die <xref:System.Linq.Enumerable.OrderBy%2A>-Methode die gesamte Auflistung erst sortieren, bevor sie das erste Element zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="131ae-116">For example, the <xref:System.Linq.Enumerable.OrderBy%2A> method has to sort the entire collection before it returns the first element.</span></span>  
  
 <span data-ttu-id="131ae-117">Die verzögerte Auswertung hat in der Regel eine höhere Arbeitsgeschwindigkeit zur Folge, weil die Verarbeitung des Mehraufwands gleichmäßig auf die Auswertung der Auflistung verteilt und die Verwendung temporärer Daten minimiert wird.</span><span class="sxs-lookup"><span data-stu-id="131ae-117">Lazy evaluation usually yields better performance because it distributes overhead processing evenly throughout the evaluation of the collection and minimizes the use of temporary data.</span></span> <span data-ttu-id="131ae-118">Bei einigen Operationen führt aber natürlich kein Weg an der Materialisierung der Zwischenergebnisse vorbei.</span><span class="sxs-lookup"><span data-stu-id="131ae-118">Of course, for some operations, there is no other option than to materialize intermediate results.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="131ae-119">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="131ae-119">Next Steps</span></span>  
 <span data-ttu-id="131ae-120">Die verzögerte Ausführung ist Gegenstand des nächsten Themas dieses Lernprogramms:</span><span class="sxs-lookup"><span data-stu-id="131ae-120">The next topic in this tutorial illustrates deferred execution:</span></span>  
  
-   [<span data-ttu-id="131ae-121">Beispiel für die verzögerte Ausführung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="131ae-121">Deferred Execution Example (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-example.md)  
  
## <a name="see-also"></a><span data-ttu-id="131ae-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="131ae-122">See Also</span></span>  
 [<span data-ttu-id="131ae-123">Lernprogramm: Verzögerte Ausführung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="131ae-123">Tutorial: Deferred Execution (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)  
 [<span data-ttu-id="131ae-124">Konzepte und Terminologie (funktionale Transformation) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="131ae-124">Concepts and Terminology (Functional Transformation) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md)  
 [<span data-ttu-id="131ae-125">Aggregationsvorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="131ae-125">Aggregation Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)
