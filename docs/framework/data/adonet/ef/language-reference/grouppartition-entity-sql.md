---
title: GROUPPARTITION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d0482e9b-086c-451c-9dfa-ccb024a9efb6
ms.openlocfilehash: 11abebeac682fed9e3a007986bb2f5c7bdb80f16
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204475"
---
# <a name="grouppartition-entity-sql"></a><span data-ttu-id="f1fbf-102">GROUPPARTITION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f1fbf-102">GROUPPARTITION (Entity SQL)</span></span>

<span data-ttu-id="f1fbf-103">Gibt eine Auflistung von Argumentwerten zurück, die für die aktuelle Gruppenpartition projiziert werden, auf die sich das Aggregat bezieht.</span><span class="sxs-lookup"><span data-stu-id="f1fbf-103">Returns a collection of argument values that are projected off the current group partition to which the aggregate is related.</span></span> <span data-ttu-id="f1fbf-104">Das `GroupPartition` -Aggregat ist ein gruppenbasiertes Aggregat und weist kein auflistungsbasiertes Formular auf.</span><span class="sxs-lookup"><span data-stu-id="f1fbf-104">The `GroupPartition` aggregate is a group-based aggregate and has no collection-based form.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1fbf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1fbf-105">Syntax</span></span>  
  
```sql  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="f1fbf-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="f1fbf-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="f1fbf-107">Beliebiger [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="f1fbf-107">Any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1fbf-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f1fbf-108">Remarks</span></span>  

 <span data-ttu-id="f1fbf-109">Die folgende Abfrage erzeugt eine Liste von Produkten und eine Auflistung von Reihenfolgenzeilenmengen für jedes Produkt:</span><span class="sxs-lookup"><span data-stu-id="f1fbf-109">The following query produces a list of products and a collection of order line quantities per each product:</span></span>  
  
```sql  
SELECT p, GroupPartition(ol.Quantity) FROM LOB.OrderLines AS ol
  GROUP BY ol.Product AS p
```  
  
 <span data-ttu-id="f1fbf-110">Die folgenden zwei Abfragen stimmen semantisch überein:</span><span class="sxs-lookup"><span data-stu-id="f1fbf-110">The following two queries are semantically equal:</span></span>  
  
```sql  
SELECT p, Sum(GroupPartition(ol.Quantity)) FROM LOB.OrderLines AS ol
  GROUP BY ol.Product AS p
SELET p, Sum(ol.Quantity) FROM LOB.OrderLines AS ol
  group by ol.Product as p  
```  
  
 <span data-ttu-id="f1fbf-111">Der `GROUPPARTITION` -Operator kann in Verbindung mit benutzerdefinierten Aggregatfunktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f1fbf-111">The `GROUPPARTITION` operator can be used in conjunction with user-defined aggregate functions.</span></span>  
  
<span data-ttu-id="f1fbf-112">`GROUPPARTITION` ist ein besonderer Aggregatoperator, der einen Verweis auf den gruppierten Eingabesatz beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="f1fbf-112">`GROUPPARTITION` is a special aggregate operator that holds a reference to the grouped input set.</span></span> <span data-ttu-id="f1fbf-113">Dieser Verweis kann an einer beliebigen Stelle in der Abfrage verwendet werden, an der sich GROUP BY innerhalb des Bereichs befindet.</span><span class="sxs-lookup"><span data-stu-id="f1fbf-113">This reference can be used anywhere in the query where GROUP BY is in scope.</span></span> <span data-ttu-id="f1fbf-114">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f1fbf-114">For example:</span></span>
  
```sql  
SELECT p, GroupPartition(ol.Quantity) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
```  
  
 <span data-ttu-id="f1fbf-115">Bei einem regulären `GROUP BY` werden die Ergebnisse der Gruppierung ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="f1fbf-115">With a regular `GROUP BY`, the results of the grouping are hidden.</span></span> <span data-ttu-id="f1fbf-116">Sie können die Ergebnisse nur in einer Aggregatfunktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1fbf-116">You can only use the results in an aggregate function.</span></span> <span data-ttu-id="f1fbf-117">Zum Anzeigen der Ergebnisse des Gruppiervorgangs müssen die Ergebnisse des Gruppiervorgangs und des Eingabesets mithilfe einer Unterabfrage korreliert werden.</span><span class="sxs-lookup"><span data-stu-id="f1fbf-117">In order to see the results of the grouping, you have to correlate the results of the grouping and the input set by using a subquery.</span></span> <span data-ttu-id="f1fbf-118">Die folgenden beiden Abfragen sind gleichwertig:</span><span class="sxs-lookup"><span data-stu-id="f1fbf-118">The following two queries are equivalent:</span></span>  
  
```sql  
SELET p, (SELECT q FROM GroupPartition(ol.Quantity) AS q) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
SELECT p, (SELECT ol.Quantity AS q FROM LOB.OrderLines AS ol2 WHERE ol2.Product = p) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
```  
  
 <span data-ttu-id="f1fbf-119">Wie im Beispiel gezeigt, wird durch den GROUPPARTITION-Aggregatoperator das Abrufen einen Verweises auf den Eingabesatz nach dem Gruppiervorgang vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="f1fbf-119">As seen from the example, the GROUPPARTITION aggregate operator makes it easier to get a reference to the input set after the grouping.</span></span>  
  
 <span data-ttu-id="f1fbf-120">Der GROUPPARTITION-Operator kann bei Verwendung des [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Parameters einen beliebigen `expression` -Ausdruck im Operator angeben.</span><span class="sxs-lookup"><span data-stu-id="f1fbf-120">The GROUPPARTITION operator can specify any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression in the operator input when you use the `expression` parameter.</span></span>  
  
 <span data-ttu-id="f1fbf-121">Zum Beispiel sind die folgenden Eingabeausdrücke für die Gruppenpartition gültig:</span><span class="sxs-lookup"><span data-stu-id="f1fbf-121">For instance all of the following input expressions to the group partition are valid:</span></span>  
  
```sql  
SELECT groupkey, GroupPartition(b) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition(1) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition(a + b) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition({a + b}) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
SELECT groupkey, GroupPartition({42}) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
SELECT groupkey, GroupPartition(b > a) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
```  
  
## <a name="example"></a><span data-ttu-id="f1fbf-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f1fbf-122">Example</span></span>  

 <span data-ttu-id="f1fbf-123">Im folgenden Beispiel wird gezeigt, wie die GROUPPARTITION-Klausel mit der GROUP BY-Klausel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f1fbf-123">The following example shows how to use the GROUPPARTITION clause with the GROUP BY clause.</span></span> <span data-ttu-id="f1fbf-124">Die GROUP BY-Klausel gruppiert `SalesOrderHeader` -Entitäten nach `Contact`.</span><span class="sxs-lookup"><span data-stu-id="f1fbf-124">The GROUP BY clause groups `SalesOrderHeader` entities by their `Contact`.</span></span> <span data-ttu-id="f1fbf-125">Die GROUPPARTITION-Klausel projiziert dann für jede Gruppe die `TotalDue` -Eigenschaft, woraus sich eine Auflistung von Dezimalwerten ergibt.</span><span class="sxs-lookup"><span data-stu-id="f1fbf-125">The GROUPPARTITION clause then projects the `TotalDue` property for each group, resulting in a collection of decimals.</span></span>  
  
 [!code-sql[DP EntityServices Concepts#Collection_GroupPartition](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#collection_grouppartition)]
