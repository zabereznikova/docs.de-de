---
title: SKIP (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1578a5817e43943d5b4257e76c7706155504fc86
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="skip-entity-sql"></a><span data-ttu-id="c197b-102">SKIP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c197b-102">SKIP (Entity SQL)</span></span>
<span data-ttu-id="c197b-103">Physisches Paging kann mithilfe der SKIP-Unterklausel in der ORDER BY-Klausel durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c197b-103">You can perform physical paging by using the SKIP sub-clause in the ORDER BY clause.</span></span> <span data-ttu-id="c197b-104">SKIP kann nicht ohne die ORDER BY-Klausel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c197b-104">SKIP cannot be used separately from the ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c197b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c197b-105">Syntax</span></span>  
  
```  
[ SKIP n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c197b-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="c197b-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="c197b-107">Die Anzahl zu überspringender Elemente.</span><span class="sxs-lookup"><span data-stu-id="c197b-107">The number of items to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c197b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c197b-108">Remarks</span></span>  
 <span data-ttu-id="c197b-109">Wenn eine ORDER BY-Klausel den Ausdruck SKIP als Unterklausel enthält, werden die Ergebnisse den Sortierangaben entsprechend sortiert, und das Resultset enthält die Zeilen, die auf den SKIP-Ausdruck folgen.</span><span class="sxs-lookup"><span data-stu-id="c197b-109">If a SKIP expression sub-clause is present in an ORDER BY clause, the results will be sorted according the sort specification and the result set will include rows starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="c197b-110">Mit SKIP 5 werden beispielsweise die ersten fünf Zeilen übersprungen und nur die Zeilen ab der sechsten Zeile zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c197b-110">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c197b-111">Eine [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage ist ungültig, wenn im selben Abfrageausdruck sowohl ein TOP-Modifizierer als auch eine SKIP-Unterklausel vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c197b-111">An [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query is invalid if both the TOP modifier and the SKIP sub-clause are present in the same query expression.</span></span> <span data-ttu-id="c197b-112">In der Abfrage sollte der TOP-Ausdruck in einen LIMIT-Ausdruck geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c197b-112">The query should be rewritten by changing the TOP expression to the LIMIT expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c197b-113">Die Verwendung von SKIP mit ORDER BY für Nichtschlüsselspalten kann in [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)]zu falschen Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="c197b-113">In [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)], using SKIP with ORDER BY on non-key columns might return incorrect results.</span></span> <span data-ttu-id="c197b-114">Es kann vorkommen, dass mehr als die angegebene Anzahl von Zeilen übersprungen wird, wenn die Nichtschlüsselspalte Daten doppelt enthält.</span><span class="sxs-lookup"><span data-stu-id="c197b-114">More than the specified number of rows might be skipped if the non-key column has duplicate data in it.</span></span> <span data-ttu-id="c197b-115">Der Grund dafür ist die Übersetzung von SKIP für [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c197b-115">This is due to how SKIP is translated for [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="c197b-116">Im folgenden Code können beispielsweise mehr als fünf Zeilen übersprungen werden, wenn `E.NonKeyColumn` Werte doppelt enthält:</span><span class="sxs-lookup"><span data-stu-id="c197b-116">For example, in the following code more than five rows might be skipped if `E.NonKeyColumn` has duplicate values:</span></span>  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 <span data-ttu-id="c197b-117">In der  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage in [diesem](https://msdn.microsoft.com/library/bb738702\(v=vs.100\).aspx#_ESQL) Beispiel wird der ORDER BY-Operator mit SKIP verwendet, um für die von der SELECT-Anweisung zurückgegebenen Objekte die zu verwendende Sortierreihenfolge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c197b-117">The  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query in [this](https://msdn.microsoft.com/library/bb738702\(v=vs.100\).aspx#_ESQL) example uses the ORDER BY operator with SKIP to specify the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c197b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c197b-118">See Also</span></span>  
 [<span data-ttu-id="c197b-119">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="c197b-119">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [<span data-ttu-id="c197b-120">Vorgehensweise: seitenweise durch Abfrageresultate navigieren</span><span class="sxs-lookup"><span data-stu-id="c197b-120">How to: Page Through Query Results</span></span>](http://msdn.microsoft.com/en-us/ffc0f920-e7de-42e0-9b12-ef356421d030)  
 [<span data-ttu-id="c197b-121">Paging</span><span class="sxs-lookup"><span data-stu-id="c197b-121">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
 [<span data-ttu-id="c197b-122">TOP</span><span class="sxs-lookup"><span data-stu-id="c197b-122">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
