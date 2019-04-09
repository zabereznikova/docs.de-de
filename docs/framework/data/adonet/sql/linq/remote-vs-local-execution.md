---
title: Remoteausführung im Vergleich zu lokaler Ausführung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ee50e943-9349-4c84-ab1c-c35d3ada1a9c
ms.openlocfilehash: 02d0417bc05f8585dc469d365089c8123d395f64
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164514"
---
# <a name="remote-vs-local-execution"></a><span data-ttu-id="f47d6-102">Remoteausführung im Vergleich zu lokaler Ausführung</span><span class="sxs-lookup"><span data-stu-id="f47d6-102">Remote vs. Local Execution</span></span>
<span data-ttu-id="f47d6-103">Sie können festlegen, ob Ihre Abfragen remote (die Datenbank-Engine führt eine Abfrage mit der Datenbank aus ) oder lokal ([!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] führt die Abfrage mit einem lokalen Cache aus) erfolgen sollen.</span><span class="sxs-lookup"><span data-stu-id="f47d6-103">You can decide to execute your queries either remotely (that is, the database engine executes the query against the database) or locally ([!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] executes the query against a local cache).</span></span>  
  
## <a name="remote-execution"></a><span data-ttu-id="f47d6-104">Remoteausführung</span><span class="sxs-lookup"><span data-stu-id="f47d6-104">Remote Execution</span></span>  
 <span data-ttu-id="f47d6-105">Betrachten Sie die folgende Abfrage:</span><span class="sxs-lookup"><span data-stu-id="f47d6-105">Consider the following query:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#7)]
 [!code-vb[DLinqQueryConcepts#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#7)]  
  
 <span data-ttu-id="f47d6-106">Wenn Ihre Datenbank Tausende von Zeilen mit Bestellungen aufweist, möchten Sie diese nicht alle abrufen müssen, um eine kleinere Teilmenge zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="f47d6-106">If your database has thousands of rows of orders, you do not want to retrieve them all to process a small subset.</span></span> <span data-ttu-id="f47d6-107">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] implementiert die <xref:System.Data.Linq.EntitySet%601>-Klasse die <xref:System.Linq.IQueryable>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f47d6-107">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Data.Linq.EntitySet%601> class implements the <xref:System.Linq.IQueryable> interface.</span></span> <span data-ttu-id="f47d6-108">Dieser Ansatz stellt sicher, dass solche Abfragen remote ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="f47d6-108">This approach makes sure that such queries can be executed remotely.</span></span> <span data-ttu-id="f47d6-109">Aus dieser Technik ergeben sich zwei wesentliche Vorteile:</span><span class="sxs-lookup"><span data-stu-id="f47d6-109">Two major benefits flow from this technique:</span></span>  
  
-   <span data-ttu-id="f47d6-110">Unnötige Daten werden nicht abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f47d6-110">Unnecessary data is not retrieved.</span></span>  
  
-   <span data-ttu-id="f47d6-111">Eine von der Datenbank-Engine ausgeführte Abfrage ist aufgrund der Datenbankindizes oft effizienter.</span><span class="sxs-lookup"><span data-stu-id="f47d6-111">A query executed by the database engine is often more efficient because of the database indexes.</span></span>  
  
## <a name="local-execution"></a><span data-ttu-id="f47d6-112">lokaler Ausführung</span><span class="sxs-lookup"><span data-stu-id="f47d6-112">Local Execution</span></span>  
 <span data-ttu-id="f47d6-113">In anderen Situationen möchten Sie ggf. alle verbundenen Entitäten in den lokalen Cache übertragen.</span><span class="sxs-lookup"><span data-stu-id="f47d6-113">In other situations, you might want to have the complete set of related entities in the local cache.</span></span> <span data-ttu-id="f47d6-114">Zu diesem Zweck stellt <xref:System.Data.Linq.EntitySet%601> die <xref:System.Data.Linq.EntitySet%601.Load%2A>-Methode bereit, um explizit alle Member von <xref:System.Data.Linq.EntitySet%601> zu laden.</span><span class="sxs-lookup"><span data-stu-id="f47d6-114">For this purpose, <xref:System.Data.Linq.EntitySet%601> provides the <xref:System.Data.Linq.EntitySet%601.Load%2A> method to explicitly load all the members of the <xref:System.Data.Linq.EntitySet%601>.</span></span>  
  
 <span data-ttu-id="f47d6-115">Wenn ein <xref:System.Data.Linq.EntitySet%601> bereits geladen ist, werden nachfolgende Abfragen lokal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f47d6-115">If an <xref:System.Data.Linq.EntitySet%601> is already loaded, subsequent queries are executed locally.</span></span> <span data-ttu-id="f47d6-116">Dieser Ansatz unterstützt Sie auf zwei Arten:</span><span class="sxs-lookup"><span data-stu-id="f47d6-116">This approach helps in two ways:</span></span>  
  
-   <span data-ttu-id="f47d6-117">Wenn der gesamte Satz lokal oder mehrmals verwendet werden muss, können Sie Remoteabfragen und die zugehörige Latenz vermeiden.</span><span class="sxs-lookup"><span data-stu-id="f47d6-117">If the complete set must be used locally or multiple times, you can avoid remote queries and associated latencies.</span></span>  
  
-   <span data-ttu-id="f47d6-118">Die Entität kann als vollständige Entität serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f47d6-118">The entity can be serialized as a complete entity.</span></span>  
  
 <span data-ttu-id="f47d6-119">Das folgende Codefragment zeigt, wie die lokale Ausführung erreicht werden kann:</span><span class="sxs-lookup"><span data-stu-id="f47d6-119">The following code fragment illustrates how local execution can be obtained:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#8)]
 [!code-vb[DLinqQueryConcepts#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#8)]  
  
## <a name="comparison"></a><span data-ttu-id="f47d6-120">Vergleich</span><span class="sxs-lookup"><span data-stu-id="f47d6-120">Comparison</span></span>  
 <span data-ttu-id="f47d6-121">Diese beiden Möglichkeiten bieten eine leistungsfähige Kombination aus Optionen: Remoteausführung für große Auflistungen und lokale Ausführung für kleine Auflistungen bzw. wenn die gesamte Auflistung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="f47d6-121">These two capabilities provide a powerful combination of options: remote execution for large collections and local execution for small collections or where the complete collection is needed.</span></span> <span data-ttu-id="f47d6-122">Die Remoteausführung wird mit <xref:System.Linq.IQueryable> implementiert, die lokale Ausführung mit einer <xref:System.Collections.Generic.IEnumerable%601>-Auflistung im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="f47d6-122">You implement remote execution through <xref:System.Linq.IQueryable>, and local execution against an in-memory <xref:System.Collections.Generic.IEnumerable%601> collection.</span></span> <span data-ttu-id="f47d6-123">Um die lokalen Ausführung erzwingen (d. h. <xref:System.Collections.Generic.IEnumerable%601>), finden Sie unter [Konvertieren eines Typs in eine generische "IEnumerable"](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md).</span><span class="sxs-lookup"><span data-stu-id="f47d6-123">To force local execution (that is, <xref:System.Collections.Generic.IEnumerable%601>), see [Convert a Type to a Generic IEnumerable](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md).</span></span>  
  
### <a name="queries-against-unordered-sets"></a><span data-ttu-id="f47d6-124">Abfragen von ungeordneten Sätzen</span><span class="sxs-lookup"><span data-stu-id="f47d6-124">Queries Against Unordered Sets</span></span>  
 <span data-ttu-id="f47d6-125">Beachten Sie den wichtigen Unterschied zwischen einer lokalen Auflistung mit Implementierung <xref:System.Collections.Generic.List%601> und eine Auflistung, die Remoteabfragen mit bietet *ungeordneten Sätzen* in einer relationalen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f47d6-125">Note the important difference between a local collection that implements <xref:System.Collections.Generic.List%601> and a collection that provides remote queries executed against *unordered sets* in a relational database.</span></span> <xref:System.Collections.Generic.List%601> <span data-ttu-id="f47d6-126">-Methoden wie jene, die Indexwerte verwenden, erfordern Listensemantik, die in der Regel durch eine Remoteabfrage mit einem ungeordneten Satz erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="f47d6-126">methods such as those that use index values require list semantics, which typically cannot be obtained through a remote query against an unordered set.</span></span> <span data-ttu-id="f47d6-127">Aus diesem Grund laden diese Methoden implizit den <xref:System.Data.Linq.EntitySet%601>, um die lokale Ausführung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f47d6-127">For this reason, such methods implicitly load the <xref:System.Data.Linq.EntitySet%601> to allow local execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f47d6-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f47d6-128">See also</span></span>

- [<span data-ttu-id="f47d6-129">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="f47d6-129">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
