---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 68f54dc5118e09d78f98c687e8a44def43b45c7d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540991"
---
# <a name="skip-entity-sql"></a><span data-ttu-id="cac07-102">SKIP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cac07-102">SKIP (Entity SQL)</span></span>

<span data-ttu-id="cac07-103">Physisches Paging kann mithilfe der SKIP-Unterklausel in der ORDER BY-Klausel durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cac07-103">You can perform physical paging by using the SKIP sub-clause in the ORDER BY clause.</span></span> <span data-ttu-id="cac07-104">SKIP kann nicht ohne die ORDER BY-Klausel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cac07-104">SKIP cannot be used separately from the ORDER BY clause.</span></span>

## <a name="syntax"></a><span data-ttu-id="cac07-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cac07-105">Syntax</span></span>

```sql
[ SKIP n ]
```

## <a name="arguments"></a><span data-ttu-id="cac07-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="cac07-106">Arguments</span></span>

`n` \
<span data-ttu-id="cac07-107">Die Anzahl zu überspringender Elemente.</span><span class="sxs-lookup"><span data-stu-id="cac07-107">The number of items to skip.</span></span>

## <a name="remarks"></a><span data-ttu-id="cac07-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cac07-108">Remarks</span></span>

<span data-ttu-id="cac07-109">Wenn eine ORDER BY-Klausel den Ausdruck SKIP als Unterklausel enthält, werden die Ergebnisse den Sortierangaben entsprechend sortiert, und das Resultset enthält die Zeilen, die auf den SKIP-Ausdruck folgen.</span><span class="sxs-lookup"><span data-stu-id="cac07-109">If a SKIP expression sub-clause is present in an ORDER BY clause, the results will be sorted according the sort specification and the result set will include rows starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="cac07-110">Mit SKIP 5 werden beispielsweise die ersten fünf Zeilen übersprungen und nur die Zeilen ab der sechsten Zeile zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cac07-110">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span>

> [!NOTE]
> <span data-ttu-id="cac07-111">Eine [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage ist ungültig, wenn im selben Abfrageausdruck sowohl ein TOP-Modifizierer als auch eine SKIP-Unterklausel vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="cac07-111">An [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query is invalid if both the TOP modifier and the SKIP sub-clause are present in the same query expression.</span></span> <span data-ttu-id="cac07-112">In der Abfrage sollte der TOP-Ausdruck in einen LIMIT-Ausdruck geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cac07-112">The query should be rewritten by changing the TOP expression to the LIMIT expression.</span></span>

> [!NOTE]
> <span data-ttu-id="cac07-113">In SQL Server 2000 werden bei Verwendung von Skip mit Order by für nicht Schlüssel Spalten möglicherweise falsche Ergebnisse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cac07-113">In SQL Server 2000, using SKIP with ORDER BY on non-key columns might return incorrect results.</span></span> <span data-ttu-id="cac07-114">Es kann vorkommen, dass mehr als die angegebene Anzahl von Zeilen übersprungen wird, wenn die Nichtschlüsselspalte Daten doppelt enthält.</span><span class="sxs-lookup"><span data-stu-id="cac07-114">More than the specified number of rows might be skipped if the non-key column has duplicate data in it.</span></span> <span data-ttu-id="cac07-115">Dies liegt daran, wie Skip für SQL Server 2000 übersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="cac07-115">This is due to how SKIP is translated for SQL Server 2000.</span></span> <span data-ttu-id="cac07-116">Im folgenden Code können beispielsweise mehr als fünf Zeilen übersprungen werden, wenn `E.NonKeyColumn` Werte doppelt enthält:</span><span class="sxs-lookup"><span data-stu-id="cac07-116">For example, in the following code more than five rows might be skipped if `E.NonKeyColumn` has duplicate values:</span></span>
>
> ```sql
> SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L
> ```

<span data-ttu-id="cac07-117">Die [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Abfrage in Gewusst [wie: seitenweise durch Abfrageergebnisse](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) verwendet den Order by-Operator mit Skip, um die Sortierreihenfolge für Objekte anzugeben, die in einer SELECT-Anweisung zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cac07-117">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query in [How to: Page Through Query Results](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) uses the ORDER BY operator with SKIP to specify the sort order used on objects returned in a SELECT statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="cac07-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cac07-118">See also</span></span>

- [<span data-ttu-id="cac07-119">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="cac07-119">ORDER BY</span></span>](order-by-entity-sql.md)
- <span data-ttu-id="cac07-120">[Gewusst wie: Seitenweise durch Abfrageresultate navigieren](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cac07-120">[How to: Page Through Query Results](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="cac07-121">Paging</span><span class="sxs-lookup"><span data-stu-id="cac07-121">Paging</span></span>](paging-entity-sql.md)
- [<span data-ttu-id="cac07-122">TOP</span><span class="sxs-lookup"><span data-stu-id="cac07-122">TOP</span></span>](top-entity-sql.md)
