---
title: "Ausführen von Left Outer Joins"
description: "So führen Sie Left Outer Joins aus."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: f542cee6-3169-4dcf-a631-3a6a79ccd473
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d81f6e9df228dc6eec985253f53b70a95493ed42
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="perform-left-outer-joins"></a><span data-ttu-id="6df03-104">Ausführen von Left Outer Joins</span><span class="sxs-lookup"><span data-stu-id="6df03-104">Perform left outer joins</span></span>
<span data-ttu-id="6df03-105">Ein Left Outer Join ist eine Verknüpfung, die jedes Element der ersten Auflistung zurückgibt, unabhängig davon, ob es entsprechende Elemente in der zweiten Auflistung gibt.</span><span class="sxs-lookup"><span data-stu-id="6df03-105">A left outer join is a join in which each element of the first collection is returned, regardless of whether it has any correlated elements in the second collection.</span></span> <span data-ttu-id="6df03-106">Sie können LINQ verwenden, um eine linke äußere Verknüpfung auszuführen, indem die Methode <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> bei den Ergebnissen einer Gruppenverknüpfung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="6df03-106">You can use LINQ to perform a left outer join by calling the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6df03-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6df03-107">Example</span></span>  
 <span data-ttu-id="6df03-108">Im folgenden Beispiel wird veranschaulicht, wie die Methode <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> bei den Ergebnissen einer Gruppenverknüpfung verwendet wird, um eine linke äußere Verknüpfung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6df03-108">The following example demonstrates how to use the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join to perform a left outer join.</span></span>  
  
 <span data-ttu-id="6df03-109">Der erste Schritt zum Erstellen eines Left Outer Join von zwei Auflistungen besteht darin, eine innere Verknüpfung durch Gruppenverknüpfung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6df03-109">The first step in producing a left outer join of two collections is to perform an inner join by using a group join.</span></span> <span data-ttu-id="6df03-110">(Siehe [Ausführen innerer Verknüpfungen](perform-inner-joins.md) für eine Erläuterung dieses Vorgangs.) In diesem Beispiel wird die Liste der `Person`-Objekte mit der Liste der `Pet`-Objekte anhand eines `Person`-Objekts, das mit `Pet.Owner` übereinstimmt, von innen verknüpft.</span><span class="sxs-lookup"><span data-stu-id="6df03-110">(See [Perform inner joins](perform-inner-joins.md) for an explanation of this process.) In this example, the list of `Person` objects is inner-joined to the list of `Pet` objects based on a `Person` object that matches `Pet.Owner`.</span></span>  
  
 <span data-ttu-id="6df03-111">Der zweite Schritt besteht darin, jedes Element der ersten (linken) Liste in den Ergebnissatz einzuschließen, selbst wenn das Element in der rechten Auflistung keine Übereinstimmungen hat.</span><span class="sxs-lookup"><span data-stu-id="6df03-111">The second step is to include each element of the first (left) collection in the result set even if that element has no matches in the right collection.</span></span> <span data-ttu-id="6df03-112">Dies wird durch den Aufruf von <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> für jede Sequenz von übereinstimmenden Elementen aus der Gruppenverknüpfung erreicht.</span><span class="sxs-lookup"><span data-stu-id="6df03-112">This is accomplished by calling <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> on each sequence of matching elements from the group join.</span></span> <span data-ttu-id="6df03-113">In diesem Beispiel wird <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> für jede Sequenz von übereinstimmenden `Pet`-Objekten aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="6df03-113">In this example, <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> is called on each sequence of matching `Pet` objects.</span></span> <span data-ttu-id="6df03-114">Diese Methode gibt eine Auflistung zurück, die einen einzelnen Standardwert enthält, wenn die Sequenz von übereinstimmenden `Pet`-Objekten für jedes `Person`-Objekt leer ist, womit die Methode sicherstellt, dass jedes `Person`-Objekt in der Ergebnisauflistung dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6df03-114">The method returns a collection that contains a single, default value if the sequence of matching `Pet` objects is empty for any `Person` object, thereby ensuring that each `Person` object is represented in the result collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6df03-115">Der Standardwert für einen Verweistyp ist `null`; deshalb wird im Beispiel nach einem NULL-Verweis gesucht, bevor auf jedes Element jeder `Pet`-Auflistung zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="6df03-115">The default value for a reference type is `null`; therefore, the example checks for a null reference before accessing each element of each `Pet` collection.</span></span>  
  
 <span data-ttu-id="6df03-116">[!code-cs[CsLINQProgJoining#7](../../../samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6df03-116">[!code-cs[CsLINQProgJoining#7](../../../samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="6df03-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6df03-117">See also</span></span>  
 <span data-ttu-id="6df03-118"><xref:System.Linq.Enumerable.Join%2A></span><span class="sxs-lookup"><span data-stu-id="6df03-118"><xref:System.Linq.Enumerable.Join%2A></span></span>   
 <span data-ttu-id="6df03-119"><xref:System.Linq.Enumerable.GroupJoin%2A></span><span class="sxs-lookup"><span data-stu-id="6df03-119"><xref:System.Linq.Enumerable.GroupJoin%2A></span></span>   
 <span data-ttu-id="6df03-120">[Ausführen innerer Verknüpfungen](perform-inner-joins.md) </span><span class="sxs-lookup"><span data-stu-id="6df03-120">[Perform inner joins](perform-inner-joins.md) </span></span>  
 <span data-ttu-id="6df03-121">[Ausführen von Gruppenverknüpfungen](perform-grouped-joins.md) </span><span class="sxs-lookup"><span data-stu-id="6df03-121">[Perform grouped joins](perform-grouped-joins.md) </span></span>  
 [<span data-ttu-id="6df03-122">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="6df03-122">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)   
 

