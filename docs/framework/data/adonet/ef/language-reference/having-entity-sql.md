---
title: HAVING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
ms.openlocfilehash: a117f377b3f03b6a1a12e39426a24f3141aa40ff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204462"
---
# <a name="having-entity-sql"></a><span data-ttu-id="efdf9-102">HAVING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="efdf9-102">HAVING (Entity SQL)</span></span>

<span data-ttu-id="efdf9-103">Gibt eine Suchbedingung für eine Gruppe oder ein Aggregat an.</span><span class="sxs-lookup"><span data-stu-id="efdf9-103">Specifies a search condition for a group or an aggregate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efdf9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="efdf9-104">Syntax</span></span>  
  
```sql  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="efdf9-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="efdf9-105">Arguments</span></span>  

 `search_condition`  
 <span data-ttu-id="efdf9-106">Gibt die Suchbedingung für die Gruppe oder das Aggregat an.</span><span class="sxs-lookup"><span data-stu-id="efdf9-106">Specifies the search condition for the group or the aggregate to meet.</span></span> <span data-ttu-id="efdf9-107">Wenn HAVING mit GROUP BY ALL verwendet wird, setzt die HAVING-Klausel ALL außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="efdf9-107">When HAVING is used with GROUP BY ALL, the HAVING clause overrides ALL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efdf9-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="efdf9-108">Remarks</span></span>  

 <span data-ttu-id="efdf9-109">Mit der HAVING-Klausel kann für das Ergebnis einer Gruppierung eine zusätzliche Filterbedingung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="efdf9-109">The HAVING clause is used to specify an additional filtering condition on the result of a grouping.</span></span> <span data-ttu-id="efdf9-110">Wenn Sie im Abfrageausdruck keine GROUP BY-Klausel angeben, wird eine implizite einzelne Gruppe angenommen.</span><span class="sxs-lookup"><span data-stu-id="efdf9-110">If no GROUP BY clause is specified in the query expression, an implicit single-set group is assumed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="efdf9-111">Die Verwendung von kann nur mit der [Select](select-entity-sql.md) -Anweisung erfolgen.</span><span class="sxs-lookup"><span data-stu-id="efdf9-111">HAVING can be used only with the [SELECT](select-entity-sql.md) statement.</span></span> <span data-ttu-id="efdf9-112">Wenn [Group by](group-by-entity-sql.md) nicht verwendet wird, verhält sich wie eine WHERE-Klausel.</span><span class="sxs-lookup"><span data-stu-id="efdf9-112">When [GROUP BY](group-by-entity-sql.md) is not used, HAVING behaves like a WHERE clause.</span></span>  
  
<span data-ttu-id="efdf9-113">Die HAVING-Klausel funktioniert wie die WHERE-Klausel, mit dem Unterschied, dass sie nach dem GROUP BY-Vorgang angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="efdf9-113">The HAVING clause works like the WHERE clause except that it is applied after the GROUP BY operation.</span></span> <span data-ttu-id="efdf9-114">Dies bedeutet, dass die "have"-Klausel nur Verweise auf Gruppierungs Aliase und Aggregate erstellen kann, wie im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="efdf9-114">This means that the HAVING clause can only make references to grouping aliases and aggregates, as illustrated in the following example:</span></span>
  
```sql  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 <span data-ttu-id="efdf9-115">Im vorherigen Beispiel werden die Gruppen auf jene eingeschränkt, die mehrere Produkte umfassen.</span><span class="sxs-lookup"><span data-stu-id="efdf9-115">The previous restricts the groups to only those that include more than one product.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efdf9-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="efdf9-116">Example</span></span>  

 <span data-ttu-id="efdf9-117">In der folgenden Entity SQL-Abfrage wird mit dem HAVING-Operator und dem GROUP BY-Operator eine Suchbedingung für eine Gruppe oder ein Aggregat angegeben.</span><span class="sxs-lookup"><span data-stu-id="efdf9-117">The following Entity SQL query uses the HAVING and GROUP BY operators to specify a search condition for a group or an aggregate.</span></span> <span data-ttu-id="efdf9-118">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="efdf9-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="efdf9-119">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="efdf9-119">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="efdf9-120">Befolgen Sie das Verfahren unter Gewusst [wie: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="efdf9-120">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="efdf9-121">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="efdf9-121">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#HAVING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#having)]  
  
## <a name="see-also"></a><span data-ttu-id="efdf9-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="efdf9-122">See also</span></span>

- [<span data-ttu-id="efdf9-123">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="efdf9-123">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="efdf9-124">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="efdf9-124">Query Expressions</span></span>](query-expressions-entity-sql.md)
