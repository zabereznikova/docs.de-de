---
title: Aggregatfunktionen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: acfd3149-f519-4c6e-8fe1-b21d243a0e58
ms.openlocfilehash: 308670f04b9a04b1fff77ece08deb39c8c4081d1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198079"
---
# <a name="aggregate-functions-entity-sql"></a><span data-ttu-id="0725e-102">Aggregatfunktionen (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0725e-102">Aggregate Functions (Entity SQL)</span></span>

<span data-ttu-id="0725e-103">Ein Aggregat ist ein Sprachkonstrukt, das eine Auflistung als Teil einer Gruppenoperation zu einem Skalar zusammenfasst.</span><span class="sxs-lookup"><span data-stu-id="0725e-103">An aggregate is a language construct that condenses a collection into a scalar as a part of a group operation.</span></span> <span data-ttu-id="0725e-104">Es gibt zwei Arten von [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Aggregaten:</span><span class="sxs-lookup"><span data-stu-id="0725e-104">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] aggregates come in two forms:</span></span>  
  
- [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="0725e-105">Sammlungs Funktionen, die an beliebiger Stelle in einem Ausdruck verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="0725e-105">collection functions that may be used anywhere in an expression.</span></span> <span data-ttu-id="0725e-106">Hierzu gehört auch die Verwendung von Aggregatfunktionen in Projektionen und Prädikate, die auf Auflistungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0725e-106">This includes using aggregate functions in projections and predicates that act on collections.</span></span> <span data-ttu-id="0725e-107">Auflistungsfunktionen sind der bevorzugte Modus zum Angeben von Aggregaten in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0725e-107">Collection functions are the preferred mode of specifying aggregates in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
- <span data-ttu-id="0725e-108">Gruppenaggregate in Abfrageausdrücken, die über eine GROUP BY-Klausel verfügen.</span><span class="sxs-lookup"><span data-stu-id="0725e-108">Group aggregates in query expressions that have a GROUP BY clause.</span></span> <span data-ttu-id="0725e-109">Wie bei Transact-SQL akzeptieren Gruppen Aggregate unterschiedliche und alle-modifiziererer für die Aggregat Eingabe.</span><span class="sxs-lookup"><span data-stu-id="0725e-109">As in Transact-SQL, group aggregates accept DISTINCT and ALL as modifiers to the aggregate input.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="0725e-110">versucht zunächst, einen Ausdruck als Auflistungs Funktion zu interpretieren, und wenn sich der Ausdruck im Kontext eines SELECT-Ausdrucks befindet, interpretiert er ihn als Gruppen Aggregat.</span><span class="sxs-lookup"><span data-stu-id="0725e-110">first tries to interpret an expression as a collection function and if the expression is in the context of a SELECT expression it interprets it as a group aggregate.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="0725e-111">definiert einen speziellen Aggregat Operator mit dem Namen [GroupPartition](grouppartition-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="0725e-111">defines a special aggregate operator called [GROUPPARTITION](grouppartition-entity-sql.md).</span></span> <span data-ttu-id="0725e-112">Mit diesem Operator können Sie einen Verweis auf den gruppierten Eingabesatz abrufen.</span><span class="sxs-lookup"><span data-stu-id="0725e-112">This operator enables you to get a reference to the grouped input set.</span></span> <span data-ttu-id="0725e-113">Dies ermöglicht erweiterte Gruppierungsabfragen, wobei die Ergebnisse der GROUP BY-Klausel an anderen Stellen als Gruppenaggregat- oder Auflistungsfunktionen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="0725e-113">This allows more advanced grouping queries, where the results of the GROUP BY clause can be used in places other than group aggregate or collection functions.</span></span>  
  
## <a name="collection-functions"></a><span data-ttu-id="0725e-114">Auflistungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="0725e-114">Collection Functions</span></span>  

 <span data-ttu-id="0725e-115">Auflistungsfunktionen verarbeiten Auflistungen und geben einen Skalarwert zurück.</span><span class="sxs-lookup"><span data-stu-id="0725e-115">Collection functions operate on collections and return a scalar value.</span></span> <span data-ttu-id="0725e-116">Wenn beispielsweise `orders` eine Auflistung aller `orders` bezeichnet, können Sie das früheste Lieferdatum mit dem folgenden Ausdruck berechnen:</span><span class="sxs-lookup"><span data-stu-id="0725e-116">For example, if `orders` is a collection of all `orders`, you can calculate the earliest ship date with the following expression:</span></span>  
  
 `min(select value o.ShipDate from LOB.Orders as o)`  
  
## <a name="group-aggregates"></a><span data-ttu-id="0725e-117">Gruppenaggregate</span><span class="sxs-lookup"><span data-stu-id="0725e-117">Group Aggregates</span></span>  

 <span data-ttu-id="0725e-118">Gruppenaggregate werden nach einem Gruppenergebnis berechnet, das von einer GROUP BY-Klausel definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="0725e-118">Group aggregates are calculated over a group result as defined by the GROUP BY clause.</span></span> <span data-ttu-id="0725e-119">Die GROUP BY-Klausel teilt Daten in Gruppen ein.</span><span class="sxs-lookup"><span data-stu-id="0725e-119">The GROUP BY clause partitions data  into groups.</span></span> <span data-ttu-id="0725e-120">Für jede Gruppe im Ergebnis wird die Aggregatfunktion angewendet, und ein separates Aggregat wird berechnet, indem die Elemente in jeder Gruppe als Eingaben zur Aggregatberechnung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0725e-120">For each group in the result, the aggregate function is applied and a separate aggregate is calculated by using the elements in each group as inputs to the aggregate calculation.</span></span> <span data-ttu-id="0725e-121">Wird eine GROUP BY-Klausel in einem SELECT-Ausdruck verwendet, dürfen sich in der Projektion, der HAVING- oder ORDER BY-Klausel nur die Namen von Gruppierungsausdrücken, Aggregate oder konstante Ausdrücke befinden.</span><span class="sxs-lookup"><span data-stu-id="0725e-121">When a GROUP BY clause is used in a SELECT expression, only grouping expression names, aggregates, or constant expressions may be present in the projection, HAVING, or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="0725e-122">Im folgenden Beispiel wird die durchschnittlich bestellte Anzahl für jedes Produkt berechnet.</span><span class="sxs-lookup"><span data-stu-id="0725e-122">The following example calculates the average quantity ordered for each product.</span></span>  
  
 `select p, avg(ol.Quantity) from LOB.OrderLines as ol`  
  
 `group by ol.Product as p`  
  
 <span data-ttu-id="0725e-123">Gruppenaggregate können im SELECT-Ausdruck ohne explizite GROUP BY-Klausel vorkommen.</span><span class="sxs-lookup"><span data-stu-id="0725e-123">It is possible to have a group aggregate without an explicit GROUP BY clause in the SELECT expression.</span></span> <span data-ttu-id="0725e-124">Alle Elemente werden als einzelne Gruppe behandelt, die der Angabe einer Gruppe auf Grundlage einer Konstante entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0725e-124">All elements will be treated as a single group, equivalent to the case of specifying a grouping based on a constant.</span></span>  
  
 `select avg(ol.Quantity) from LOB.OrderLines as ol`  
  
 `select avg(ol.Quantity) from LOB.OrderLines as ol group by 1`  
  
 <span data-ttu-id="0725e-125">Ausdrücke, die in der GROUP BY-Klausel verwendet werden, werden mit dem gleichen Namensauflösungsbereich ausgewertet, der für den WHERE-Klauselausdruck sichtbar wäre.</span><span class="sxs-lookup"><span data-stu-id="0725e-125">Expressions used in the GROUP BY clause are evaluated by using the same name-resolution scope that would be visible to the WHERE clause expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0725e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0725e-126">See also</span></span>

- [<span data-ttu-id="0725e-127">Funktionen</span><span class="sxs-lookup"><span data-stu-id="0725e-127">Functions</span></span>](functions-entity-sql.md)
