---
title: HAVING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
ms.openlocfilehash: 97ed6e06241804bf2f576c910a2235b0cb570bbb
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833729"
---
# <a name="having-entity-sql"></a><span data-ttu-id="5fe7c-102">HAVING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5fe7c-102">HAVING (Entity SQL)</span></span>
<span data-ttu-id="5fe7c-103">Gibt eine Suchbedingung für eine Gruppe oder ein Aggregat an.</span><span class="sxs-lookup"><span data-stu-id="5fe7c-103">Specifies a search condition for a group or an aggregate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fe7c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5fe7c-104">Syntax</span></span>  
  
```sql  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="5fe7c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="5fe7c-105">Arguments</span></span>  
 `search_condition`  
 <span data-ttu-id="5fe7c-106">Gibt die Suchbedingung für die zu erfüllende Gruppe oder das Aggregat an.</span><span class="sxs-lookup"><span data-stu-id="5fe7c-106">Specifies the search condition for the group or the aggregate to meet.</span></span> <span data-ttu-id="5fe7c-107">Wenn HAVING mit GROUP BY ALL verwendet wird, setzt die HAVING-Klausel ALL außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="5fe7c-107">When HAVING is used with GROUP BY ALL, the HAVING clause overrides ALL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fe7c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5fe7c-108">Remarks</span></span>  
 <span data-ttu-id="5fe7c-109">Mit der HAVING-Klausel kann für das Ergebnis einer Gruppierung eine zusätzliche Filterbedingung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5fe7c-109">The HAVING clause is used to specify an additional filtering condition on the result of a grouping.</span></span> <span data-ttu-id="5fe7c-110">Wenn Sie im Abfrageausdruck keine GROUP BY-Klausel angeben, wird eine implizite einzelne Gruppe angenommen.</span><span class="sxs-lookup"><span data-stu-id="5fe7c-110">If no GROUP BY clause is specified in the query expression, an implicit single-set group is assumed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5fe7c-111">Die Verwendung von kann nur mit der [Select](select-entity-sql.md) -Anweisung erfolgen.</span><span class="sxs-lookup"><span data-stu-id="5fe7c-111">HAVING can be used only with the [SELECT](select-entity-sql.md) statement.</span></span> <span data-ttu-id="5fe7c-112">Wenn [Group by](group-by-entity-sql.md) nicht verwendet wird, verhält sich wie eine WHERE-Klausel.</span><span class="sxs-lookup"><span data-stu-id="5fe7c-112">When [GROUP BY](group-by-entity-sql.md) is not used, HAVING behaves like a WHERE clause.</span></span>  
  
<span data-ttu-id="5fe7c-113">Die HAVING-Klausel funktioniert wie die WHERE-Klausel, mit dem Unterschied, dass sie nach dem GROUP BY-Vorgang angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="5fe7c-113">The HAVING clause works like the WHERE clause except that it is applied after the GROUP BY operation.</span></span> <span data-ttu-id="5fe7c-114">Dies bedeutet, dass die "have"-Klausel nur Verweise auf Gruppierungs Aliase und Aggregate erstellen kann, wie im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="5fe7c-114">This means that the HAVING clause can only make references to grouping aliases and aggregates, as illustrated in the following example:</span></span>
  
```sql  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 <span data-ttu-id="5fe7c-115">Im vorherigen Beispiel werden die Gruppen auf jene eingeschränkt, die mehrere Produkte umfassen.</span><span class="sxs-lookup"><span data-stu-id="5fe7c-115">The previous restricts the groups to only those that include more than one product.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fe7c-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5fe7c-116">Example</span></span>  
 <span data-ttu-id="5fe7c-117">In der folgenden Entity SQL-Abfrage wird mit dem HAVING-Operator und dem GROUP BY-Operator eine Suchbedingung für eine Gruppe oder ein Aggregat angegeben.</span><span class="sxs-lookup"><span data-stu-id="5fe7c-117">The following Entity SQL query uses the HAVING and GROUP BY operators to specify a search condition for a group or an aggregate.</span></span> <span data-ttu-id="5fe7c-118">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="5fe7c-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5fe7c-119">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="5fe7c-119">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="5fe7c-120">Befolgen Sie das Verfahren unter Gewusst [wie: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="5fe7c-120">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="5fe7c-121">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="5fe7c-121">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#HAVING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#having)]  
  
## <a name="see-also"></a><span data-ttu-id="5fe7c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5fe7c-122">See also</span></span>

- [<span data-ttu-id="5fe7c-123">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="5fe7c-123">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="5fe7c-124">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="5fe7c-124">Query Expressions</span></span>](query-expressions-entity-sql.md)
