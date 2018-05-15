---
title: Ausführen von Left Outer Joins
description: So führen Sie Left Outer Joins aus.
ms.date: 12/1/2016
ms.assetid: f542cee6-3169-4dcf-a631-3a6a79ccd473
ms.openlocfilehash: aacab1ac6f4ab2c10b393cf0b2c578a13d9b9306
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="perform-left-outer-joins"></a><span data-ttu-id="c1016-103">Ausführen von Left Outer Joins</span><span class="sxs-lookup"><span data-stu-id="c1016-103">Perform left outer joins</span></span>
<span data-ttu-id="c1016-104">Ein Left Outer Join ist eine Verknüpfung, die jedes Element der ersten Auflistung zurückgibt, unabhängig davon, ob es entsprechende Elemente in der zweiten Auflistung gibt.</span><span class="sxs-lookup"><span data-stu-id="c1016-104">A left outer join is a join in which each element of the first collection is returned, regardless of whether it has any correlated elements in the second collection.</span></span> <span data-ttu-id="c1016-105">Sie können LINQ verwenden, um eine linke äußere Verknüpfung auszuführen, indem die Methode <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> bei den Ergebnissen einer Gruppenverknüpfung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c1016-105">You can use LINQ to perform a left outer join by calling the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1016-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c1016-106">Example</span></span>  
 <span data-ttu-id="c1016-107">Im folgenden Beispiel wird veranschaulicht, wie die Methode <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> bei den Ergebnissen einer Gruppenverknüpfung verwendet wird, um eine linke äußere Verknüpfung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c1016-107">The following example demonstrates how to use the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join to perform a left outer join.</span></span>  
  
 <span data-ttu-id="c1016-108">Der erste Schritt zum Erstellen eines Left Outer Join von zwei Auflistungen besteht darin, eine innere Verknüpfung durch Gruppenverknüpfung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c1016-108">The first step in producing a left outer join of two collections is to perform an inner join by using a group join.</span></span> <span data-ttu-id="c1016-109">(Siehe [Ausführen innerer Verknüpfungen](perform-inner-joins.md) für eine Erläuterung dieses Vorgangs.) In diesem Beispiel wird die Liste der `Person`-Objekte mit der Liste der `Pet`-Objekte anhand eines `Person`-Objekts, das mit `Pet.Owner` übereinstimmt, von innen verknüpft.</span><span class="sxs-lookup"><span data-stu-id="c1016-109">(See [Perform inner joins](perform-inner-joins.md) for an explanation of this process.) In this example, the list of `Person` objects is inner-joined to the list of `Pet` objects based on a `Person` object that matches `Pet.Owner`.</span></span>  
  
 <span data-ttu-id="c1016-110">Der zweite Schritt besteht darin, jedes Element der ersten (linken) Liste in den Ergebnissatz einzuschließen, selbst wenn das Element in der rechten Auflistung keine Übereinstimmungen hat.</span><span class="sxs-lookup"><span data-stu-id="c1016-110">The second step is to include each element of the first (left) collection in the result set even if that element has no matches in the right collection.</span></span> <span data-ttu-id="c1016-111">Dies wird durch den Aufruf von <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> für jede Sequenz von übereinstimmenden Elementen aus der Gruppenverknüpfung erreicht.</span><span class="sxs-lookup"><span data-stu-id="c1016-111">This is accomplished by calling <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> on each sequence of matching elements from the group join.</span></span> <span data-ttu-id="c1016-112">In diesem Beispiel wird <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> für jede Sequenz von übereinstimmenden `Pet`-Objekten aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c1016-112">In this example, <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> is called on each sequence of matching `Pet` objects.</span></span> <span data-ttu-id="c1016-113">Diese Methode gibt eine Auflistung zurück, die einen einzelnen Standardwert enthält, wenn die Sequenz von übereinstimmenden `Pet`-Objekten für jedes `Person`-Objekt leer ist, womit die Methode sicherstellt, dass jedes `Person`-Objekt in der Ergebnisauflistung dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c1016-113">The method returns a collection that contains a single, default value if the sequence of matching `Pet` objects is empty for any `Person` object, thereby ensuring that each `Person` object is represented in the result collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1016-114">Der Standardwert für einen Verweistyp ist `null`; deshalb wird im Beispiel nach einem NULL-Verweis gesucht, bevor auf jedes Element jeder `Pet`-Auflistung zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="c1016-114">The default value for a reference type is `null`; therefore, the example checks for a null reference before accessing each element of each `Pet` collection.</span></span>  
  
 [!code-csharp[CsLINQProgJoining#7](../../../samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]  
 
## <a name="see-also"></a><span data-ttu-id="c1016-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1016-115">See also</span></span>  
 <xref:System.Linq.Enumerable.Join%2A>  
 <xref:System.Linq.Enumerable.GroupJoin%2A>  
 [<span data-ttu-id="c1016-116">Ausführen innerer Verknüpfungen</span><span class="sxs-lookup"><span data-stu-id="c1016-116">Perform inner joins</span></span>](perform-inner-joins.md)  
 [<span data-ttu-id="c1016-117">Ausführen von Gruppenverknüpfungen</span><span class="sxs-lookup"><span data-stu-id="c1016-117">Perform grouped joins</span></span>](perform-grouped-joins.md)  
 [<span data-ttu-id="c1016-118">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="c1016-118">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)  
 
