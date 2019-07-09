---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 88d4c9c987f451e9a653d5b9c213e7158670ed4b
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662139"
---
# <a name="skip-entity-sql"></a><span data-ttu-id="40cee-102">SKIP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="40cee-102">SKIP (Entity SQL)</span></span>
<span data-ttu-id="40cee-103">Physisches Paging kann mithilfe der SKIP-Unterklausel in der ORDER BY-Klausel durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="40cee-103">You can perform physical paging by using the SKIP sub-clause in the ORDER BY clause.</span></span> <span data-ttu-id="40cee-104">SKIP kann nicht ohne die ORDER BY-Klausel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="40cee-104">SKIP cannot be used separately from the ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40cee-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="40cee-105">Syntax</span></span>  
  
```  
[ SKIP n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="40cee-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="40cee-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="40cee-107">Die Anzahl zu überspringender Elemente.</span><span class="sxs-lookup"><span data-stu-id="40cee-107">The number of items to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40cee-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="40cee-108">Remarks</span></span>  
 <span data-ttu-id="40cee-109">Wenn eine ORDER BY-Klausel den Ausdruck SKIP als Unterklausel enthält, werden die Ergebnisse den Sortierangaben entsprechend sortiert, und das Resultset enthält die Zeilen, die auf den SKIP-Ausdruck folgen.</span><span class="sxs-lookup"><span data-stu-id="40cee-109">If a SKIP expression sub-clause is present in an ORDER BY clause, the results will be sorted according the sort specification and the result set will include rows starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="40cee-110">Mit SKIP 5 werden beispielsweise die ersten fünf Zeilen übersprungen und nur die Zeilen ab der sechsten Zeile zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="40cee-110">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40cee-111">Eine [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage ist ungültig, wenn im selben Abfrageausdruck sowohl ein TOP-Modifizierer als auch eine SKIP-Unterklausel vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="40cee-111">An [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query is invalid if both the TOP modifier and the SKIP sub-clause are present in the same query expression.</span></span> <span data-ttu-id="40cee-112">In der Abfrage sollte der TOP-Ausdruck in einen LIMIT-Ausdruck geändert werden.</span><span class="sxs-lookup"><span data-stu-id="40cee-112">The query should be rewritten by changing the TOP expression to the LIMIT expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40cee-113">In SQL Server 2000 möglicherweise die Verwendung von SKIP mit ORDER BY auf Nichtschlüsselspalten falsche Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="40cee-113">In SQL Server 2000, using SKIP with ORDER BY on non-key columns might return incorrect results.</span></span> <span data-ttu-id="40cee-114">Es kann vorkommen, dass mehr als die angegebene Anzahl von Zeilen übersprungen wird, wenn die Nichtschlüsselspalte Daten doppelt enthält.</span><span class="sxs-lookup"><span data-stu-id="40cee-114">More than the specified number of rows might be skipped if the non-key column has duplicate data in it.</span></span> <span data-ttu-id="40cee-115">Dies liegt an der Übersetzung von SKIP für SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="40cee-115">This is due to how SKIP is translated for SQL Server 2000.</span></span> <span data-ttu-id="40cee-116">Im folgenden Code können beispielsweise mehr als fünf Zeilen übersprungen werden, wenn `E.NonKeyColumn` Werte doppelt enthält:</span><span class="sxs-lookup"><span data-stu-id="40cee-116">For example, in the following code more than five rows might be skipped if `E.NonKeyColumn` has duplicate values:</span></span>  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 <span data-ttu-id="40cee-117">Die [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage im [Vorgehensweise: Seite über Abfrageergebnisse](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) den ORDER BY-Operator mit SKIP verwendet, um die in einer SELECT-Anweisung zurückgegebenen Objekte zu verwendende Sortierreihenfolge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="40cee-117">The  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query in [How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) uses the ORDER BY operator with SKIP to specify the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40cee-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40cee-118">See also</span></span>

- [<span data-ttu-id="40cee-119">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="40cee-119">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- <span data-ttu-id="40cee-120">[Vorgehensweise: Seitenweise Abfrageresultate durch Navigieren](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="40cee-120">[How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="40cee-121">Paging</span><span class="sxs-lookup"><span data-stu-id="40cee-121">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [<span data-ttu-id="40cee-122">TOP</span><span class="sxs-lookup"><span data-stu-id="40cee-122">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
