---
title: FROM (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff3e3048-0d5d-4502-ae5c-9187fcbd0514
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 51f65896cb54a65756558d846e1fc940de5b9470
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="from-entity-sql"></a><span data-ttu-id="1e385-102">FROM (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1e385-102">FROM (Entity SQL)</span></span>
<span data-ttu-id="1e385-103">Gibt die Auflistung in verwendet [wählen](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="1e385-103">Specifies the collection used in [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) statements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e385-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e385-104">Syntax</span></span>  
  
```  
FROM expression [ ,...n ] as C  
```  
  
## <a name="arguments"></a><span data-ttu-id="1e385-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="1e385-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="1e385-106">Jeder gültige, eine Auflistung zurückgebende Abfrageausdruck, die als Quelle in einer `SELECT`-Anweisung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1e385-106">Any valid query expression that yields a collection to use as a source in a `SELECT` statement.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e385-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1e385-107">Remarks</span></span>  
 <span data-ttu-id="1e385-108">Eine `FROM`-Klausel ist eine durch Kommas getrennte Liste von einem oder mehreren `FROM`-Klauselelementen.</span><span class="sxs-lookup"><span data-stu-id="1e385-108">A `FROM` clause is a comma-separated list of one or more `FROM` clause items.</span></span> <span data-ttu-id="1e385-109">Die `FROM`-Klausel kann verwendet werden, um eine oder mehrere Quellen für eine `SELECT`-Anweisung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1e385-109">The `FROM` clause can be used to specify one or more sources for a `SELECT` statement.</span></span> <span data-ttu-id="1e385-110">Die einfachste Form einer `FROM`-Klausel ist ein einzelner, eine Auflistung und ein Alias festlegender Abfrageausdruck, der als Quelle in einer `SELECT`-Anweisung verwendet wird, wie im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1e385-110">The simplest form of a `FROM` clause is a single query expression that identifies a collection and an alias used as the source in a `SELECT` statement, as illustrated in the following example:</span></span>  
  
 `FROM C as c`  
  
## <a name="from-clause-items"></a><span data-ttu-id="1e385-111">FROM-Klauselelemente</span><span class="sxs-lookup"><span data-stu-id="1e385-111">FROM Clause Items</span></span>  
 <span data-ttu-id="1e385-112">Jedes `FROM`-Klauselelement verweist auf eine Quellauflistung in der [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="1e385-112">Each `FROM` clause item refers to a source collection in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="1e385-113"> unterstützt die folgenden Klassen von `FROM`-Klauselelementen: einfache `FROM`-Klauselelemente, `JOIN FROM`-Klauselelemente und `APPLY FROM`-Klauselelemente.</span><span class="sxs-lookup"><span data-stu-id="1e385-113"> supports the following classes of `FROM` clause items: simple `FROM` clause items, `JOIN FROM` clause items, and `APPLY FROM` clause items.</span></span> <span data-ttu-id="1e385-114">Jedes dieser `FROM`-Klauselelemente wird in den folgenden Abschnitten ausführlicher beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1e385-114">Each of these `FROM` clause items is described in more detail in the following sections.</span></span>  
  
### <a name="simple-from-clause-item"></a><span data-ttu-id="1e385-115">Einfaches FROM-Klauselelement</span><span class="sxs-lookup"><span data-stu-id="1e385-115">Simple FROM Clause Item</span></span>  
 <span data-ttu-id="1e385-116">Das einfachste `FROM`-Klauselelement ist ein einzelner Ausdruck, der eine Auflistung und einen Alias identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1e385-116">The simplest `FROM` clause item is a single expression that identifies a collection and an alias.</span></span> <span data-ttu-id="1e385-117">Bei dem Ausdruck kann es sich einfach um eine Entitätenmenge, eine Unterabfrage oder um einen anderen Ausdruck vom Auflistungstyp handeln.</span><span class="sxs-lookup"><span data-stu-id="1e385-117">The expression can simply be an entity set, or a subquery, or any other expression that is a collection type.</span></span> <span data-ttu-id="1e385-118">Im Folgenden finden Sie ein Beispiel dazu:</span><span class="sxs-lookup"><span data-stu-id="1e385-118">The following is an example:</span></span>  
  
```  
LOB.Customers as c  
```  
  
 <span data-ttu-id="1e385-119">Die Aliasspezifikation ist optional.</span><span class="sxs-lookup"><span data-stu-id="1e385-119">The alias specification is optional.</span></span> <span data-ttu-id="1e385-120">Eine alternative Spezifikation vom oben erwähnten FROM-Klauselelement finden Sie im Folgenden:</span><span class="sxs-lookup"><span data-stu-id="1e385-120">An alternate specification of the above from clause item could be the following:</span></span>  
  
```  
LOB.Customers  
```  
  
 <span data-ttu-id="1e385-121">Wenn kein Alias angegeben wird, erzeugt [!INCLUDE[esql](../../../../../../includes/esql-md.md)] auf der Grundlage des Auflistungsausdrucks einen Alias.</span><span class="sxs-lookup"><span data-stu-id="1e385-121">If no alias is specified, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] attempts to generate an alias based on the collection expression.</span></span>  
  
### <a name="join-from-clause-item"></a><span data-ttu-id="1e385-122">JOIN FROM-Klauselelement</span><span class="sxs-lookup"><span data-stu-id="1e385-122">JOIN FROM Clause Item</span></span>  
 <span data-ttu-id="1e385-123">Ein `JOIN FROM`-Klauselelement stellt einen Join zwischen zwei `FROM`-Klauselelementen dar.</span><span class="sxs-lookup"><span data-stu-id="1e385-123">A `JOIN FROM` clause item represents a join between two `FROM` clause items.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="1e385-124"> unterstützt Kreuzjoins, innere Joins, linke und rechte äußere Verknüpfungen und vollständige äußere Joins.</span><span class="sxs-lookup"><span data-stu-id="1e385-124"> supports cross joins, inner joins, left and right outer joins, and full outer joins.</span></span> <span data-ttu-id="1e385-125">Diese Verknüpfungen werden alle auf ähnliche Weise unterstützt wie in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e385-125">All these joins are supported similar to the way that they are supported in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1e385-126">Wie in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] müssen die beiden für `FROM` verwendeten `JOIN`-Klauselelemente unabhängig sein.</span><span class="sxs-lookup"><span data-stu-id="1e385-126">As in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], the two `FROM` clause items involved in the `JOIN` must be independent.</span></span> <span data-ttu-id="1e385-127">Sie können demnach nicht korreliert werden.</span><span class="sxs-lookup"><span data-stu-id="1e385-127">That is, they cannot be correlated.</span></span> <span data-ttu-id="1e385-128">Für diese Fälle kann `CROSS APPLY` oder `OUTER APPLY` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1e385-128">A `CROSS APPLY` or `OUTER APPLY` can be used for these cases.</span></span>  
  
#### <a name="cross-joins"></a><span data-ttu-id="1e385-129">Cross Joins</span><span class="sxs-lookup"><span data-stu-id="1e385-129">Cross Joins</span></span>  
 <span data-ttu-id="1e385-130">Ein `CROSS JOIN`-Abfrageausdruck erzeugt das kartesische Produkt der beiden Auflistungen, wie im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1e385-130">A `CROSS JOIN` query expression produces the Cartesian product of the two collections, as illustrated in the following example:</span></span>  
  
 `FROM C AS c CROSS JOIN D as d`  
  
#### <a name="inner-joins"></a><span data-ttu-id="1e385-131">Inner Joins</span><span class="sxs-lookup"><span data-stu-id="1e385-131">Inner Joins</span></span>  
 <span data-ttu-id="1e385-132">`INNER JOIN` erzeugt ein eingeschränktes kartesisches Produkt der beiden Auflistungen, wie im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1e385-132">An `INNER JOIN` produces a constrained Cartesian product of the two collections, as illustrated in the following example:</span></span>  
  
 `FROM C AS c [INNER] JOIN D AS d ON e`  
  
 <span data-ttu-id="1e385-133">Der vorige Abfrageausdruck verarbeitet eine Kombination aller Elemente der linken Auflistung gepaart mit jedem Element der rechten Auflistung, wenn die `ON`-Bedingung "true" ist.</span><span class="sxs-lookup"><span data-stu-id="1e385-133">The previous query expression processes a combination of every element of the collection on the left paired against every element of the collection on the right, where the `ON` condition is true.</span></span> <span data-ttu-id="1e385-134">Wenn keine `ON`-Bedingung angegeben wird, degeneriert ein `INNER JOIN` zu einem `CROSS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="1e385-134">If no `ON` condition is specified, an `INNER JOIN` degenerates to a `CROSS JOIN`.</span></span>  
  
#### <a name="left-outer-joins-and-right-outer-joins"></a><span data-ttu-id="1e385-135">Linke äußere Verknüpfungen und rechte äußere Verknüpfungen</span><span class="sxs-lookup"><span data-stu-id="1e385-135">Left Outer Joins and Right Outer Joins</span></span>  
 <span data-ttu-id="1e385-136">Ein `OUTER JOIN`-Abfrageausdruck erzeugt ein eingeschränktes kartesisches Produkt der beiden Auflistungen, wie im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1e385-136">An `OUTER JOIN` query expression produces a constrained Cartesian product of the two collections, as illustrated in the following example:</span></span>  
  
 `FROM C AS c LEFT OUTER JOIN D AS d ON e`  
  
 <span data-ttu-id="1e385-137">Der vorige Abfrageausdruck verarbeitet eine Kombination aller Elemente der linken Auflistung gepaart mit jedem Element der rechten Auflistung, wenn die `ON`-Bedingung "true" ist.</span><span class="sxs-lookup"><span data-stu-id="1e385-137">The previous query expression processes a combination of every element of the collection on the left paired against every element of the collection on the right, where the `ON` condition is true.</span></span> <span data-ttu-id="1e385-138">Wenn die `ON`-Bedingung "false" ist, verarbeitet der Ausdruck eine einzelne Instanz des linken Elements gepaart mit dem rechten Element mit dem Wert Null.</span><span class="sxs-lookup"><span data-stu-id="1e385-138">If the `ON` condition is false, the expression still processes a single instance of the element on the left paired against the element on the right, with the value null.</span></span>  
  
 <span data-ttu-id="1e385-139">Ein `RIGHT OUTER JOIN` kann auf eine ähnliche Weise ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="1e385-139">A `RIGHT OUTER JOIN` may be expressed in a similar manner.</span></span>  
  
#### <a name="full-outer-joins"></a><span data-ttu-id="1e385-140">Full Outer Joins</span><span class="sxs-lookup"><span data-stu-id="1e385-140">Full Outer Joins</span></span>  
 <span data-ttu-id="1e385-141">Ein expliziter `FULL OUTER JOIN` erzeugt ein eingeschränktes kartesisches Produkt der beiden Auflistungen, wie im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1e385-141">An explicit `FULL OUTER JOIN` produces a constrained Cartesian product of the two collections as illustrated in the following example:</span></span>  
  
 `FROM C AS c FULL OUTER JOIN D AS d ON e`  
  
 <span data-ttu-id="1e385-142">Der vorige Abfrageausdruck verarbeitet eine Kombination aller Elemente der linken Auflistung gepaart mit jedem Element der rechten Auflistung, wenn die `ON`-Bedingung "true" ist.</span><span class="sxs-lookup"><span data-stu-id="1e385-142">The previous query expression processes a combination of every element of the collection on the left paired against every element of the collection on the right, where the `ON` condition is true.</span></span> <span data-ttu-id="1e385-143">Wenn die `ON`-Bedingung "false" ist, verarbeitet der Ausdruck eine Instanz des linken Elements gepaart mit dem rechten Element mit dem Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="1e385-143">If the `ON` condition is false, the expression still processes one instance of the element on the left paired against the element on the right, with the value null.</span></span> <span data-ttu-id="1e385-144">Außerdem wird eine Instanz des rechten Elements gepaart mit dem linken Element mit dem Wert NULL verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="1e385-144">It also processes one instance of the element on the right paired against the element on the left, with the value null.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e385-145">In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] ist das OUTER-Schlüsselwort optional, um die Kompatibilität mit SQL-92 beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="1e385-145">To preserve compatibility with SQL-92, in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] the OUTER keyword is optional.</span></span> <span data-ttu-id="1e385-146">`LEFT JOIN`, `RIGHT JOIN` und `FULL JOIN` sind daher Synonyme für `LEFT OUTER JOIN`, `RIGHT OUTER JOIN` und `FULL OUTER JOIN`.</span><span class="sxs-lookup"><span data-stu-id="1e385-146">Therefore, `LEFT JOIN`, `RIGHT JOIN`, and `FULL JOIN` are synonyms for `LEFT OUTER JOIN`, `RIGHT OUTER JOIN`, and `FULL OUTER JOIN`.</span></span>  
  
### <a name="apply-clause-item"></a><span data-ttu-id="1e385-147">APPLY-Klauselelement</span><span class="sxs-lookup"><span data-stu-id="1e385-147">APPLY Clause Item</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="1e385-148"> unterstützt zwei Arten von `APPLY`: `CROSS APPLY` und `OUTER APPLY`.</span><span class="sxs-lookup"><span data-stu-id="1e385-148"> supports two kinds of `APPLY`: `CROSS APPLY` and `OUTER APPLY`.</span></span>  
  
 <span data-ttu-id="1e385-149">Ein `CROSS APPLY` erzeugt eine eindeutige Kombination aller Elemente der linken Auflistung mit einem Element der rechten Auflistung, indem der rechte Ausdruck ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="1e385-149">A `CROSS APPLY` produces a unique pairing of each element of the collection on the left with an element of the collection produced by evaluating the expression on the right.</span></span> <span data-ttu-id="1e385-150">Mit `CROSS APPLY` ist der rechte Ausdruck funktional abhängig vom linken Element, wie das folgende Beispiel für eine zugeordnete Auflistung veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1e385-150">With a `CROSS APPLY`, the expression on the right is functionally dependent on the element on the left, as illustrated in the following associated collection example:</span></span>  
  
 `SELECT c, f FROM C AS c CROSS APPLY c.Assoc AS f`  
  
 <span data-ttu-id="1e385-151">Das Verhalten von `CROSS APPLY` ähnelt der Verknüpfungsliste.</span><span class="sxs-lookup"><span data-stu-id="1e385-151">The behavior of `CROSS APPLY` is similar to the join list.</span></span> <span data-ttu-id="1e385-152">Wenn der rechte Ausdruck als leere Auflistung ausgewertet wird, erzeugt `CROSS APPLY` für diese Instanz des linken Elements keine Paarungen.</span><span class="sxs-lookup"><span data-stu-id="1e385-152">If the expression on the right evaluates to an empty collection, the `CROSS APPLY` produces no pairings for that instance of the element on the left.</span></span>  
  
 <span data-ttu-id="1e385-153">`OUTER APPLY` ähnelt `CROSS APPLY`, abgesehen davon, dass eine Paarung auch dann erzeugt wird, wenn der rechte Ausdruck als leere Auflistung ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="1e385-153">An `OUTER APPLY` resembles a `CROSS APPLY`, except a pairing is still produced even when the expression on the right evaluates to an empty collection.</span></span> <span data-ttu-id="1e385-154">Im Folgenden finden Sie ein Beispiel für ein `OUTER APPLY`.</span><span class="sxs-lookup"><span data-stu-id="1e385-154">The following is an example of an `OUTER APPLY`:</span></span>  
  
 `SELECT c, f FROM C AS c OUTER APPLY c.Assoc AS f`  
  
> [!NOTE]
>  <span data-ttu-id="1e385-155">Im Unterschied zu [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] ist in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kein unnest-Schritt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1e385-155">Unlike in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], there is no need for an explicit unnest step in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e385-156">`CROSS`- und `OUTER APPLY`-Operatoren wurden in [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)] eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1e385-156">`CROSS` and `OUTER APPLY` operators were introduced in [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="1e385-157">In einigen Fällen kann die Abfragepipeline Transact-SQL erzeugen, die `CROSS APPLY`- und/oder `OUTER APPLY`-Operatoren enthält.</span><span class="sxs-lookup"><span data-stu-id="1e385-157">In some cases, the query pipeline might produce Transact-SQL that contains `CROSS APPLY` and/or `OUTER APPLY` operators.</span></span> <span data-ttu-id="1e385-158">Da einige Back-End-Anbieter, einschließlich [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)]-Versionen, die älter sind als [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)], diese Operatoren nicht unterstützen, können solche Abfragen auf diesen Back-End-Anbietern nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1e385-158">Because some backend providers, including versions of [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] earlier than [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)], do not support these operators, such queries cannot be executed on these backend providers.</span></span>  
>   
>  <span data-ttu-id="1e385-159">Typische Szenarios, in denen `CROSS APPLY`- und/oder `OUTER APPLY`-Operatoren in der Ausgabeabfrage vorhanden sein können, sind beispielsweise korrelierte Unterabfragen mit Paging, AnyElement über einer korrelierten Unterabfrage oder über einer durch Navigation erzeugten Auflistung, LINQ-Abfragen, die Elementselektoren akzeptierende Gruppierungsmethoden verwenden, Abfragen, für die ein `CROSS APPLY` oder ein `OUTER APPLY` explizit angegeben wurden oder Abfragen, die ein `DEREF`-Konstrukt über einem `REF`-Konstrukt enthalten.</span><span class="sxs-lookup"><span data-stu-id="1e385-159">Some typical scenarios that might lead to the presence of `CROSS APPLY` and/or `OUTER APPLY` operators in the output query are the following: a correlated subquery with paging; AnyElement over a correlated subquery or over a collection produced by navigation; LINQ queries that use grouping methods that accept an element selector; a query in which a `CROSS APPLY` or an `OUTER APPLY` are explicitly specified; a query that has a `DEREF` construct over a `REF` construct.</span></span>  
  
## <a name="multiple-collections-in-the-from-clause"></a><span data-ttu-id="1e385-160">Mehrere Auflistungen in der FROM-Klausel</span><span class="sxs-lookup"><span data-stu-id="1e385-160">Multiple Collections in the FROM Clause</span></span>  
 <span data-ttu-id="1e385-161">Die `FROM`-Klausel kann mehrere durch Kommas getrennte Auflistungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="1e385-161">The `FROM` clause can contain more than one collection separated by commas.</span></span> <span data-ttu-id="1e385-162">In diesem Fall wird davon ausgegangen, dass die Auflistungen verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="1e385-162">In these cases, the collections are assumed to be joined together.</span></span> <span data-ttu-id="1e385-163">Dies ist vergleichbar mit einem n-fachen CROSS JOIN.</span><span class="sxs-lookup"><span data-stu-id="1e385-163">Think of these as an n-way CROSS JOIN.</span></span>  
  
 <span data-ttu-id="1e385-164">Im folgenden Beispiel `C` und `D` unabhängige Auflistungen, aber `c.Names` ist abhängig von `C`.</span><span class="sxs-lookup"><span data-stu-id="1e385-164">In the following example, `C` and `D` are independent collections, but `c.Names` is dependent on `C`.</span></span>  
  
```  
FROM C AS c, D AS d, c.Names AS e  
```  
  
 <span data-ttu-id="1e385-165">Das vorherige Beispiel ist mit dem folgenden Beispiel logisch äquivalent:</span><span class="sxs-lookup"><span data-stu-id="1e385-165">The previous example is logically equivalent to the following example:</span></span>  
  
 `FROM (C AS c JOIN D AS d) CROSS APPLY c.Names AS e`  
  
## <a name="left-correlation"></a><span data-ttu-id="1e385-166">Linke Korrelation</span><span class="sxs-lookup"><span data-stu-id="1e385-166">Left Correlation</span></span>  
 <span data-ttu-id="1e385-167">Elemente in der `FROM`-Klausel können auf in früheren Klauseln angegebene Elemente verweisen.</span><span class="sxs-lookup"><span data-stu-id="1e385-167">Items in the `FROM` clause can refer to items specified in earlier clauses.</span></span> <span data-ttu-id="1e385-168">Im folgenden Beispiel sind `C` und `D` unabhängige Auflistungen, `c.Names` ist jedoch von `C` abhängig:</span><span class="sxs-lookup"><span data-stu-id="1e385-168">In the following example, `C` and `D` are independent collections, but `c.Names` is dependent on `C`:</span></span>  
  
```  
from C as c, D as d, c.Names as e  
```  
  
 <span data-ttu-id="1e385-169">Dies ist logisch äquivalent zu:</span><span class="sxs-lookup"><span data-stu-id="1e385-169">This is logically equivalent to:</span></span>  
  
```  
from (C as c join D as d) cross apply c.Names as e  
```  
  
## <a name="semantics"></a><span data-ttu-id="1e385-170">Semantik</span><span class="sxs-lookup"><span data-stu-id="1e385-170">Semantics</span></span>  
 <span data-ttu-id="1e385-171">Es wird logisch davon ausgegangen, dass die Auflistungen in der `FROM`-Klausel zu einem `n`-fachen Cross Join gehören (außer im Fall eines einfachen Cross Join).</span><span class="sxs-lookup"><span data-stu-id="1e385-171">Logically, the collections in the `FROM` clause are assumed to be part of an `n`-way cross join (except in the case of a 1-way cross join).</span></span> <span data-ttu-id="1e385-172">Aliase werden in der `FROM`-Klausel von links nach rechts verarbeitet und dem aktuellen Gültigkeitsbereich hinzugefügt, um später auf sie verweisen zu können.</span><span class="sxs-lookup"><span data-stu-id="1e385-172">Aliases in the `FROM` clause are processed left to right, and are added to the current scope for later reference.</span></span> <span data-ttu-id="1e385-173">Es wird angenommen, dass die `FROM`-Klausel ein Zeilenmultiset erzeugt.</span><span class="sxs-lookup"><span data-stu-id="1e385-173">The `FROM` clause is assumed to produce a multiset of rows.</span></span> <span data-ttu-id="1e385-174">Für jedes Objekt in der `FROM`-Klausel ist ein Feld vorhanden, dass ein einzelnes Element dieser Auflistung darstellt.</span><span class="sxs-lookup"><span data-stu-id="1e385-174">There will be one field for each item in the `FROM` clause that represents a single element from that collection item.</span></span>  
  
 <span data-ttu-id="1e385-175">Die `FROM`-Klausel erzeugt logisch eine Zeilenmultimenge vom Row(c, d, e)-Typ. Es wird angenommen, dass die Felder c, d und e den Elementtyp `C`, `D` und `c.Names` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1e385-175">The `FROM` clause logically produces a multiset of rows of type Row(c, d, e) where fields c, d, and e are assumed to be of the element type of `C`, `D`, and `c.Names`.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="1e385-176"> führt einen Alias für jedes einfache `FROM`-Klauselelement im Bereich ein.</span><span class="sxs-lookup"><span data-stu-id="1e385-176"> introduces an alias for each simple `FROM` clause item in scope.</span></span> <span data-ttu-id="1e385-177">Im folgenden FROM-Klauselausschnitt sind die im Bereich eingeführten Namen beispielsweise c, d und e.</span><span class="sxs-lookup"><span data-stu-id="1e385-177">For example, in the following FROM clause snippet, The names introduced into scope are c, d, and e.</span></span>  
  
```  
from (C as c join D as d) cross apply c.Names as e  
```  
  
 <span data-ttu-id="1e385-178">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (im Gegensatz zu [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]) führt die `FROM`-Klausel nur die Aliase im Bereich ein.</span><span class="sxs-lookup"><span data-stu-id="1e385-178">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (unlike [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]), the `FROM` clause only introduces the aliases into scope.</span></span> <span data-ttu-id="1e385-179">Alle Verweise auf Spalten (Eigenschaften) dieser Auflistungen müssen mit dem Alias qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="1e385-179">Any references to columns (properties) of these collections must be qualified with the alias.</span></span>  
  
## <a name="pulling-up-keys-from-nested-queries"></a><span data-ttu-id="1e385-180">Ausführen von Pull-Vorgängen für Schlüssel aus geschachtelten Abfragen</span><span class="sxs-lookup"><span data-stu-id="1e385-180">Pulling Up Keys from Nested Queries</span></span>  
 <span data-ttu-id="1e385-181">Bestimmte Typen von Abfragen, die die Ausführung von Pull-Vorgängen für Schlüssel aus einer geschachtelten Abfrage erfordern, werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1e385-181">Certain types of queries that require pulling up keys from a nested query are not supported.</span></span> <span data-ttu-id="1e385-182">Beispielsweise ist die folgende Abfrage gültig:</span><span class="sxs-lookup"><span data-stu-id="1e385-182">For example, the following query is valid:</span></span>  
  
```  
select c.Orders from Customers as c   
```  
  
 <span data-ttu-id="1e385-183">Die folgende Abfrage ist jedoch ungültig, da die geschachtelte Abfrage nicht über Schlüssel verfügt:</span><span class="sxs-lookup"><span data-stu-id="1e385-183">However, the following query is not valid, because the nested query does not have any keys:</span></span>  
  
```  
select {1} from {2, 3}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e385-184">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e385-184">See Also</span></span>  
 [<span data-ttu-id="1e385-185">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="1e385-185">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="1e385-186">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="1e385-186">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
 [<span data-ttu-id="1e385-187">Strukturierte Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="1e385-187">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
