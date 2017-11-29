---
title: LIMIT (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c890bf6950f94c04350902276193f5a43239f63f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="limit-entity-sql"></a><span data-ttu-id="862db-102">LIMIT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="862db-102">LIMIT (Entity SQL)</span></span>
<span data-ttu-id="862db-103">Das physische Paging kann mit LIMIT-Unterklauseln in der ORDER BY-Klausel durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="862db-103">Physical paging can be performed by using LIMIT sub-clause in ORDER BY clause.</span></span> <span data-ttu-id="862db-104">LIMIT kann nicht ohne ORDER BY-Klausel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="862db-104">LIMIT can not be used separately from ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="862db-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="862db-105">Syntax</span></span>  
  
```  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="862db-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="862db-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="862db-107">Die Anzahl der auszuwählenden Elemente.</span><span class="sxs-lookup"><span data-stu-id="862db-107">The number of items that will be selected.</span></span>  
  
 <span data-ttu-id="862db-108">Wenn eine ORDER BY-Klausel den Ausdruck LIMIT als Unterklausel enthält, wird das Abfrageergebnis den Sortierangaben entsprechend sortiert, und die Anzahl der zurückgegebenen Zeilen wird durch den LIMIT-Ausdruck begrenzt.</span><span class="sxs-lookup"><span data-stu-id="862db-108">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="862db-109">LIMIT 5 z. B. begrenzt das Resultset auf fünf Instanzen oder Zeilen.</span><span class="sxs-lookup"><span data-stu-id="862db-109">For instance, LIMIT 5 will restrict the result set to 5 instances or rows.</span></span> <span data-ttu-id="862db-110">Die Funktionsweise von LIMIT entspricht der von TOP, mit dem Unterschied, dass LIMIT nur mit einer ORDER BY-Klausel verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="862db-110">LIMIT is functionally equivalent to TOP with the exception that LIMIT requires ORDER BY clause to be present.</span></span> <span data-ttu-id="862db-111">SKIP und LIMIT können zusammen mit einer ORDER BY-Klausel voneinander unabhängig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="862db-111">SKIP and LIMIT can be used independently along with ORDER BY clause.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="862db-112">Eine Entity Sql-Abfrage gilt als ungültig, wenn im selben Abfrageausdruck ein TOP-Modifizierer und eine SKIP-Unterklausel vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="862db-112">An Entity Sql query will be considered invalid if TOP modifier and SKIP sub-clause is present in the same query expression.</span></span> <span data-ttu-id="862db-113">Die Abfrage sollte umgeschrieben werden, indem der TOP-Ausdruck in einen LIMIT-Ausdruck geändert wird.</span><span class="sxs-lookup"><span data-stu-id="862db-113">The query should be rewritten by changing TOP expression to LIMIT expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="862db-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="862db-114">Example</span></span>  
 <span data-ttu-id="862db-115">In der folgenden Entity SQL-Abfrage wird der ORDER BY-Operator mit LIMIT verwendet, um für die von der SELECT-Anweisung zurückgegebenen Objekte die zu verwendende Sortierreihenfolge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="862db-115">The following Entity SQL query uses the ORDER BY operator with LIMIT to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="862db-116">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="862db-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="862db-117">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="862db-117">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="862db-118">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="862db-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="862db-119">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="862db-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LIMIT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#limit)]  
  
## <a name="see-also"></a><span data-ttu-id="862db-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="862db-120">See Also</span></span>  
 [<span data-ttu-id="862db-121">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="862db-121">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [<span data-ttu-id="862db-122">Vorgehensweise: seitenweise durch Abfrageresultate navigieren</span><span class="sxs-lookup"><span data-stu-id="862db-122">How to: Page Through Query Results</span></span>](http://msdn.microsoft.com/en-us/ffc0f920-e7de-42e0-9b12-ef356421d030)  
 [<span data-ttu-id="862db-123">Paging</span><span class="sxs-lookup"><span data-stu-id="862db-123">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
 [<span data-ttu-id="862db-124">NACH OBEN</span><span class="sxs-lookup"><span data-stu-id="862db-124">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
