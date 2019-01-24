---
title: Unterschiede zwischen Entity SQL und Transact-SQL
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: f193a3f7441a8bf7efacf07d8a9eb18362d7f91d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635961"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a><span data-ttu-id="02186-102">Unterschiede zwischen Entity SQL und Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="02186-102">How Entity SQL Differs from Transact-SQL</span></span>
<span data-ttu-id="02186-103">Dieses Thema beschreibt die Unterschiede zwischen [!INCLUDE[esql](../../../../../../includes/esql-md.md)] und [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02186-103">This topic describes the differences between [!INCLUDE[esql](../../../../../../includes/esql-md.md)] and [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span>  
  
## <a name="inheritance-and-relationships-support"></a><span data-ttu-id="02186-104">Unterstützung von Vererbung und Beziehungen</span><span class="sxs-lookup"><span data-stu-id="02186-104">Inheritance and Relationships Support</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-105">verwendet direkt konzeptionelle Entitätsschemas und unterstützt Features konzeptioneller Modelle, wie Vererbung und Beziehungen.</span><span class="sxs-lookup"><span data-stu-id="02186-105">works directly with conceptual entity schemas and supports conceptual model features such as inheritance and relationships.</span></span>  
  
 <span data-ttu-id="02186-106">Bei der Vererbung ist es häufig nützlich, Instanzen eines Untertyps aus einer Auflistung von Instanzen des Obertyps auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="02186-106">When working with inheritance, it is often useful to select instances of a subtype from a collection of supertype instances.</span></span> <span data-ttu-id="02186-107">Die [Oftype](../../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) -Operator in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (ähnlich wie `oftype` in C# Sequenzen) möglich.</span><span class="sxs-lookup"><span data-stu-id="02186-107">The [oftype](../../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operator in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (similar to `oftype` in C# Sequences) provides this capability.</span></span>  
  
## <a name="support-for-collections"></a><span data-ttu-id="02186-108">Unterstützung von Auflistungen</span><span class="sxs-lookup"><span data-stu-id="02186-108">Support for Collections</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-109">behandelt Auflistungen als Entitäten erster Klasse.</span><span class="sxs-lookup"><span data-stu-id="02186-109">treats collections as first-class entities.</span></span> <span data-ttu-id="02186-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="02186-110">For example:</span></span>  
  
-   <span data-ttu-id="02186-111">In einer `from`-Klausel sind Auflistungsausdrücke gültig.</span><span class="sxs-lookup"><span data-stu-id="02186-111">Collection expressions are valid in a `from` clause.</span></span>  
  
-   <span data-ttu-id="02186-112">`in` und `exists`-Unterabfragen wurden so verallgemeinert, dass sämtliche Auflistungen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="02186-112">`in` and `exists` subqueries have been generalized to allow any collections.</span></span>  
  
     <span data-ttu-id="02186-113">Eine Unterabfrage ist eine Art von Auflistung.</span><span class="sxs-lookup"><span data-stu-id="02186-113">A subquery is one kind of collection.</span></span> <span data-ttu-id="02186-114">`e1 in e2` und `exists(e)` sind die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Konstrukte zum Ausführen dieser Operationen.</span><span class="sxs-lookup"><span data-stu-id="02186-114">`e1 in e2` and `exists(e)` are the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] constructs to perform these operations.</span></span>  
  
-   <span data-ttu-id="02186-115">Mengenoperationen, z. B. `union`, `intersect` und `except`, verarbeiten nun Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="02186-115">Set operations, such as `union`, `intersect`, and `except`, now operate on collections.</span></span>  
  
-   <span data-ttu-id="02186-116">Joins verarbeiten Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="02186-116">Joins operate on collections.</span></span>  
  
## <a name="support-for-expressions"></a><span data-ttu-id="02186-117">Unterstützung von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="02186-117">Support for Expressions</span></span>  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] <span data-ttu-id="02186-118">verfügt über Unterabfragen (Tabellen) und Ausdrücke (Zeilen und Spalten).</span><span class="sxs-lookup"><span data-stu-id="02186-118">has subqueries (tables) and expressions (rows and columns).</span></span>  
  
 <span data-ttu-id="02186-119">Zur Unterstützung von Auflistungen und geschachtelten Auflistungen [!INCLUDE[esql](../../../../../../includes/esql-md.md)] alles als Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="02186-119">To support collections and nested collections, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] makes everything an expression.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-120">ist zusammensetzbarer als [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], d. h., jeder Ausdruck kann überall verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="02186-120">is more composable than [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]—every expression can be used anywhere.</span></span> <span data-ttu-id="02186-121">Abfrageausdrücke geben stets Auflistungen der projizierten Typen zurück und können immer verwendet werden, wenn ein Auflistungsausdruck zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="02186-121">Query expressions always result in collections of the projected types and can be used anywhere a collection expression is allowed.</span></span> <span data-ttu-id="02186-122">Informationen zu [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] Ausdrücke, die nicht unterstützt werden [!INCLUDE[esql](../../../../../../includes/esql-md.md)], finden Sie unter [nicht unterstützte Ausdrücke](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="02186-122">For information about [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)], see [Unsupported Expressions](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="02186-123">Bei den folgenden Abfragen handelt es sich um gültige [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Abfragen:</span><span class="sxs-lookup"><span data-stu-id="02186-123">The following are all valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries:</span></span>  
  
```  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}   
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a><span data-ttu-id="02186-124">Einheitliche Behandlung von Unterabfragen</span><span class="sxs-lookup"><span data-stu-id="02186-124">Uniform Treatment of Subqueries</span></span>  
 <span data-ttu-id="02186-125">Der Schwerpunkt auf Tabellen, erhält [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] führt Unterabfragen in Ihrem Kontext interpretiert.</span><span class="sxs-lookup"><span data-stu-id="02186-125">Given its emphasis on tables, [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] performs contextual interpretation of subqueries.</span></span> <span data-ttu-id="02186-126">Beispielsweise eine Unterabfrage in der `from` Klausel gilt eine Multimenge (Tabelle).</span><span class="sxs-lookup"><span data-stu-id="02186-126">For example, a subquery in the `from` clause is considered to be a multiset (table).</span></span> <span data-ttu-id="02186-127">Dieselbe Unterabfrage in der `select`-Klausel wird hingegen als skalare Unterabfrage aufgefasst.</span><span class="sxs-lookup"><span data-stu-id="02186-127">But the same subquery used in the `select` clause is considered to be a scalar subquery.</span></span> <span data-ttu-id="02186-128">Auf ähnliche Weise eine Unterabfrage, die auf der linken Seite des verwendet eine `in` Operator gilt als skalare Unterabfrage, während die rechte Seite erwartet wird ein multiset Unterabfrage sein.</span><span class="sxs-lookup"><span data-stu-id="02186-128">Similarly, a subquery used on the left side of an `in` operator is considered to be a scalar subquery, while the right side is expected to be a multiset subquery.</span></span>  
  
 <span data-ttu-id="02186-129">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] existieren diese Unterschiede nicht.</span><span class="sxs-lookup"><span data-stu-id="02186-129">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] eliminates these differences.</span></span> <span data-ttu-id="02186-130">Ein Ausdruck verfügt über eine einheitliche vom Kontext unabhängige Auslegung.</span><span class="sxs-lookup"><span data-stu-id="02186-130">An expression has a uniform interpretation that does not depend on the context in which it is used.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-131">betrachtet alle Unterabfragen multimengenabfragen.</span><span class="sxs-lookup"><span data-stu-id="02186-131">considers all subqueries to be multiset subqueries.</span></span> <span data-ttu-id="02186-132">Ggf. ein skalarer Wert aus der Unterabfrage wird [!INCLUDE[esql](../../../../../../includes/esql-md.md)] bietet die `anyelement` Operator, der eine Auflistung (in diesem Fall die Unterabfrage) ausgeführt wird, extrahiert einen Singleton-Wert aus der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="02186-132">If a scalar value is desired from the subquery, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides the `anyelement` operator that operates on a collection (in this case, the subquery), and extracts a singleton value from the collection.</span></span>  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a><span data-ttu-id="02186-133">Vermeiden impliziter Koersionen für Unterabfragen</span><span class="sxs-lookup"><span data-stu-id="02186-133">Avoiding Implicit Coercions for Subqueries</span></span>  
 <span data-ttu-id="02186-134">Ein Nebeneffekt der einheitlichen Behandlung von Unterabfragen ist die implizite Konvertierung von Unterabfragen zu skalaren Werten.</span><span class="sxs-lookup"><span data-stu-id="02186-134">A related side effect of uniform treatment of subqueries is implicit conversion of subqueries to scalar values.</span></span> <span data-ttu-id="02186-135">In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] wird eine Multimenge von Zeilen (mit einem einzelnen Feld) implizit in einen skalaren Wert konvertiert, dessen Datentyp mit dem des Felds übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="02186-135">Specifically, in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], a multiset of rows (with a single field) is implicitly converted into a scalar value whose data type is that of the field.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-136">unterstützt diese implizite Umwandlung nicht.</span><span class="sxs-lookup"><span data-stu-id="02186-136">does not support this implicit coercion.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-137">stellt den ANYELEMENT-Operator zum Extrahieren eines Singleton-Werts aus einer Auflistung bereit sowie eine `select value`-Klausel zur Vermeidung der Erstellung eines Zeilen-Wrappers während eines Abfrageausdrucks.</span><span class="sxs-lookup"><span data-stu-id="02186-137">provides the ANYELEMENT operator to extract a singleton value from a collection, and a `select value` clause to avoid creating a row-wrapper during a query expression.</span></span>  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a><span data-ttu-id="02186-138">Wert auswählen: Vermeiden die impliziten Zeilen-Wrappers</span><span class="sxs-lookup"><span data-stu-id="02186-138">Select Value: Avoiding the Implicit Row Wrapper</span></span>  
 <span data-ttu-id="02186-139">Die select-Klausel in einer [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] -Unterabfrage erstellt implizit einen Zeilen-Wrapper für die Elemente in der Klausel.</span><span class="sxs-lookup"><span data-stu-id="02186-139">The select clause in a [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] subquery implicitly creates a row wrapper around the items in the clause.</span></span> <span data-ttu-id="02186-140">Dies bedeutet, dass keine Auflistungen von Skalaren oder Objekten erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="02186-140">This implies that we cannot create collections of scalars or objects.</span></span> [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] <span data-ttu-id="02186-141">ermöglicht eine implizite Koersion zwischen einem Zeilentyp mit einem Feld und einem Singletonwert des gleichen Datentyps an.</span><span class="sxs-lookup"><span data-stu-id="02186-141">allows an implicit coercion between a rowtype with one field, and a singleton value of the same data type.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-142">stellt die `select value`-Klausel bereit, um die implizite Zeilenkonstruktion unnötig zu machen.</span><span class="sxs-lookup"><span data-stu-id="02186-142">provides the `select value` clause to skip the implicit row construction.</span></span> <span data-ttu-id="02186-143">In einer `select value`-Klausel kann nur ein Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="02186-143">Only one item may be specified in a `select value` clause.</span></span> <span data-ttu-id="02186-144">Wenn diese Klausel verwendet wird, wird kein Zeilen-Wrapper für die Elemente in der `select`-Klausel erstellt, und eine Auflistung der gewünschten Form kann erstellt werden. Beispiel: `select value a`.</span><span class="sxs-lookup"><span data-stu-id="02186-144">When such a clause is used, no row wrapper is constructed around the items in the `select` clause, and a collection of the desired shape may be produced, for example: `select value a`.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-145">stellt auch den Zeilenkonstruktor zum Erstellen beliebiger Zeilen bereit.</span><span class="sxs-lookup"><span data-stu-id="02186-145">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="02186-146">Mit `select` werden ein oder mehrere Elemente in der Projektion übergeben, und das Ergebnis ist ein Datensatz mit folgenden Feldern:</span><span class="sxs-lookup"><span data-stu-id="02186-146">`select` takes one or more elements in the projection and results in a data record with fields, as follows:</span></span>  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a><span data-ttu-id="02186-147">Linkskorrelation und Aliasing</span><span class="sxs-lookup"><span data-stu-id="02186-147">Left Correlation and Aliasing</span></span>  
 <span data-ttu-id="02186-148">In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] können Ausdrücke in einem bestimmten Bereich (eine einzelne Klausel wie `select` oder `from`) nicht auf Ausdrücke verweisen, die vorher im selben Bereich definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="02186-148">In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], expressions in a given scope (a single clause like `select` or `from`) cannot reference expressions defined earlier in the same scope.</span></span> <span data-ttu-id="02186-149">Einige Dialekte von SQL (einschließlich [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]) unterstützen sie in der `from`-Klausel in beschränktem Umfang.</span><span class="sxs-lookup"><span data-stu-id="02186-149">Some dialects of SQL (including [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]) do support limited forms of these in the `from` clause.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-150">verallgemeinert Linkskorrelationen in der `from` -Klausel, und behandelt sie einheitlich.</span><span class="sxs-lookup"><span data-stu-id="02186-150">generalizes left correlations in the `from` clause, and treats them uniformly.</span></span> <span data-ttu-id="02186-151">Ausdrücke in der `from`-Klausel können ohne die Verwendung zusätzlicher Syntax auf vorherige Definitionen (Definitionen auf der linken Seite) in derselben Klausel verweisen.</span><span class="sxs-lookup"><span data-stu-id="02186-151">Expressions in the `from` clause can reference earlier definitions (definitions to the left) in the same clause without the need for additional syntax.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-152">schränkt auch Abfragen, die `group by`-Klauseln enthalten, weiter ein.</span><span class="sxs-lookup"><span data-stu-id="02186-152">also imposes additional restrictions on queries involving `group by` clauses.</span></span> <span data-ttu-id="02186-153">Ausdrücke in der `select` Klausel und `having` -Klausel solcher Abfragen nur bezieht sich möglicherweise auf die `group by` Schlüssel mithilfe ihrer Aliase.</span><span class="sxs-lookup"><span data-stu-id="02186-153">Expressions in the `select` clause and `having` clause of such queries may only refer to the `group by` keys via their aliases.</span></span> <span data-ttu-id="02186-154">Das folgende Konstrukt ist in gültiger [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] jedoch nicht in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="02186-154">The following construct is valid in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] but are not in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span></span>  
  
```  
select t.x + t.y from T as t group by t.x + t.y  
```  
  
 <span data-ttu-id="02186-155">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist Folgendes zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="02186-155">To do this in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span></span>  
  
```  
select k from T as t group by (t.x + t.y) as k  
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a><span data-ttu-id="02186-156">Verweisen auf Spalten (Eigenschaften) von Tabellen (Auflistungen)</span><span class="sxs-lookup"><span data-stu-id="02186-156">Referencing Columns (Properties) of Tables (Collections)</span></span>  
 <span data-ttu-id="02186-157">Alle Spaltenverweise in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] müssen mit dem Tabellenalias qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="02186-157">All column references in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] must be qualified with the table alias.</span></span> <span data-ttu-id="02186-158">Das folgende Konstrukt (vorausgesetzt, dass `a` ist eine gültige Spalte der Tabelle `T`) gilt in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] jedoch nicht in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02186-158">The following construct (assuming that `a` is a valid column of table `T`) is valid in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] but not in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
```  
select a from T  
```  
  
 <span data-ttu-id="02186-159">Die Form für [!INCLUDE[esql](../../../../../../includes/esql-md.md)] lautet</span><span class="sxs-lookup"><span data-stu-id="02186-159">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] form is</span></span>  
  
```  
select t.a as A from T as t  
```  
  
 <span data-ttu-id="02186-160">Die Tabellenaliase sind in der `from`-Klausel optional.</span><span class="sxs-lookup"><span data-stu-id="02186-160">The table aliases are optional in the `from` clause.</span></span> <span data-ttu-id="02186-161">Der Name der Tabelle wird als implizites Alias verwendet.</span><span class="sxs-lookup"><span data-stu-id="02186-161">The name of the table is used as the implicit alias.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-162">lässt auch das folgende Formular zu:</span><span class="sxs-lookup"><span data-stu-id="02186-162">allows the following form as well:</span></span>  
  
```  
select Tab.a from Tab  
```  
  
## <a name="navigation-through-objects"></a><span data-ttu-id="02186-163">Navigieren durch Objekte</span><span class="sxs-lookup"><span data-stu-id="02186-163">Navigation Through Objects</span></span>  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] <span data-ttu-id="02186-164">verwendet die "."-Schreibweise zum Verweisen auf Spalten (Zeilen) einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="02186-164">uses the "." notation for referencing columns of (a row of) a table.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-165">erweitert diese Schreibweise (wie Programmiersprachen), um die Navigation durch Eigenschaften eines Objekts zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="02186-165">extends this notation (borrowed from programming languages) to support navigation through properties of an object.</span></span>  
  
 <span data-ttu-id="02186-166">Wenn z. B. `p` ein Ausdruck vom Typ "Person" ist, lautet die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Syntax zum Verweisen auf die Stadt und die Adresse dieser Person wie folgt.</span><span class="sxs-lookup"><span data-stu-id="02186-166">For example, if `p` is an expression of type Person, the following is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] syntax for referencing the city of the address of this person.</span></span>  
  
```  
p.Address.City   
```  
  
## <a name="no-support-for-"></a><span data-ttu-id="02186-167">Keine Unterstützung von \*</span><span class="sxs-lookup"><span data-stu-id="02186-167">No Support for \*</span></span>  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] <span data-ttu-id="02186-168">unterstützt die unqualifizierte \*-Syntax als Alias für die gesamte Zeile und die qualifizierte \* Syntax (t\*) als Abkürzung für die Felder dieser Tabelle.</span><span class="sxs-lookup"><span data-stu-id="02186-168">supports the unqualified \* syntax as an alias for the entire row, and the qualified \* syntax (t.\*) as a shortcut for the fields of that table.</span></span> <span data-ttu-id="02186-169">Darüber hinaus [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] ermöglicht eine spezielle Anzahl (\*) Aggregat, das Nullen einschließt.</span><span class="sxs-lookup"><span data-stu-id="02186-169">In addition, [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] allows for a special count(\*) aggregate, which includes nulls.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-170">unterstützt nicht das \*-Konstrukt.</span><span class="sxs-lookup"><span data-stu-id="02186-170">does not support the \* construct.</span></span> [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="02186-171">-Abfragen der Formulare `select * from T` und `select T1.* from T1, T2...` können in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] als `select value t from T as t` und `select value t1 from T1 as t1, T2 as t2...` ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="02186-171">queries of the form `select * from T` and `select T1.* from T1, T2...` can be expressed in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as `select value t from T as t` and `select value t1 from T1 as t1, T2 as t2...`, respectively.</span></span> <span data-ttu-id="02186-172">Außerdem behandeln diese Konstrukte Vererbung (Wertersetzbarkeit), während die `select *`-Varianten auf die Eigenschaften des deklarierten Typen auf oberster Ebene eingeschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="02186-172">Additionally, these constructs handle inheritance (value substitutability), while the `select *` variants are restricted to top-level properties of the declared type.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-173">unterstützt nicht die `count(*)`-Aggregate.</span><span class="sxs-lookup"><span data-stu-id="02186-173">does not support the `count(*)` aggregate.</span></span> <span data-ttu-id="02186-174">Verwenden Sie stattdessen `count(0)`.</span><span class="sxs-lookup"><span data-stu-id="02186-174">Use `count(0)` instead.</span></span>  
  
## <a name="changes-to-group-by"></a><span data-ttu-id="02186-175">Änderungen an "Group By"</span><span class="sxs-lookup"><span data-stu-id="02186-175">Changes to Group By</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-176">unterstützt Aliasing von `group by`-Schlüsseln.</span><span class="sxs-lookup"><span data-stu-id="02186-176">supports aliasing of `group by` keys.</span></span> <span data-ttu-id="02186-177">Ausdrücke in der `select`-Klausel und der `having`-Klausel müssen mithilfe dieser Aliase auf die `group by`-Schlüssel verweisen.</span><span class="sxs-lookup"><span data-stu-id="02186-177">Expressions in the `select` clause and `having` clause must refer to the `group by` keys via these aliases.</span></span> <span data-ttu-id="02186-178">Beispielsweise ist die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Syntax</span><span class="sxs-lookup"><span data-stu-id="02186-178">For example, this [!INCLUDE[esql](../../../../../../includes/esql-md.md)] syntax:</span></span>  
  
```  
select k1, count(t.a), sum(t.a)  
from T as t  
group by t.b + t.c as k1  
```  
  
 <span data-ttu-id="02186-179">...entspricht folgender [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="02186-179">...is equivalent to the following [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]:</span></span>  
  
```  
select b + c, count(*), sum(a)   
from T  
group by b + c  
```  
  
## <a name="collection-based-aggregates"></a><span data-ttu-id="02186-180">Auflistungsbasierte Aggregate</span><span class="sxs-lookup"><span data-stu-id="02186-180">Collection-Based Aggregates</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-181">unterstützt zwei Arten von Aggregaten.</span><span class="sxs-lookup"><span data-stu-id="02186-181">supports two kinds of aggregates.</span></span>  
  
 <span data-ttu-id="02186-182">Auflistungsbasierte Aggregate verarbeiten Auflistungen und erstellen das aggregierte Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="02186-182">Collection-based aggregates operate on collections and produce the aggregated result.</span></span> <span data-ttu-id="02186-183">Sie können überall in der Abfrage stehen und erfordern keine `group by`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="02186-183">These can appear anywhere in the query, and do not require a `group by` clause.</span></span> <span data-ttu-id="02186-184">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="02186-184">For example:</span></span>  
  
```  
select t.a as a, count({1,2,3}) as b from T as t     
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-185">unterstützt auch Aggregate im SQL-Format.</span><span class="sxs-lookup"><span data-stu-id="02186-185">also supports SQL-style aggregates.</span></span> <span data-ttu-id="02186-186">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="02186-186">For example:</span></span>  
  
```  
select a, sum(t.b) from T as t group by t.a as a  
```  
  
## <a name="order-by-clause-usage"></a><span data-ttu-id="02186-187">Verwendung der "ORDER BY"-Klausel</span><span class="sxs-lookup"><span data-stu-id="02186-187">ORDER BY Clause Usage</span></span>  
 <span data-ttu-id="02186-188">In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] können ORDER BY-Klauseln nur im obersten SELECT ..</span><span class="sxs-lookup"><span data-stu-id="02186-188">[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] allows ORDER BY clauses to be specified only in the topmost SELECT ..</span></span> <span data-ttu-id="02186-189">FROM .</span><span class="sxs-lookup"><span data-stu-id="02186-189">FROM ..</span></span> <span data-ttu-id="02186-190">WHERE-Block angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="02186-190">WHERE block.</span></span> <span data-ttu-id="02186-191">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] können ORDER BY-Ausdrücke geschachtelt und überall in der Abfrage platziert werden. Die Reihenfolge in einer geschachtelten Abfrage wird jedoch nicht erhalten.</span><span class="sxs-lookup"><span data-stu-id="02186-191">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] you can use a nested ORDER BY expression and it can be placed anywhere in the query, but ordering in a nested query is not preserved.</span></span>  
  
```  
-- The following query will order the results by the last name  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="identifiers"></a><span data-ttu-id="02186-192">Bezeichner</span><span class="sxs-lookup"><span data-stu-id="02186-192">Identifiers</span></span>  
 <span data-ttu-id="02186-193">In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] basiert der Bezeichnervergleich auf der Sortierreihenfolge der aktuellen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="02186-193">In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], identifier comparison is based on the collation of the current database.</span></span> <span data-ttu-id="02186-194">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] wird bei Bezeichnern nicht zwischen Groß-/Kleinschreibung unterschieden, Akzentzeichen werden dagegen von den keinen Akzent tragenden Zeichen unterschieden ([!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterscheidet also beispielsweise zwischen 'a' und 'ấ').</span><span class="sxs-lookup"><span data-stu-id="02186-194">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], identifiers are always case insensitive and accent sensitive (that is, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] distinguishes between accented and unaccented characters; for example, 'a' is not equal to 'ấ').</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-195">behandelt Buchstaben, die gleich erscheinen, aber von anderen Codepages stammen.</span><span class="sxs-lookup"><span data-stu-id="02186-195">treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="02186-196">Weitere Informationen finden Sie unter [Eingabe Zeichensatz](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="02186-196">For more information, see [Input Character Set](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md).</span></span>  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a><span data-ttu-id="02186-197">Transact-SQL-Funktionalität ist in Entity SQL nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="02186-197">Transact-SQL Functionality Not Available in Entity SQL</span></span>  
 <span data-ttu-id="02186-198">Die folgende [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]-Funktionalität ist in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="02186-198">The following [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] functionality is not available in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
 <span data-ttu-id="02186-199">DML</span><span class="sxs-lookup"><span data-stu-id="02186-199">DML</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-200">bietet derzeit keine Unterstützung für DML-Anweisungen (einfügen, aktualisieren und löschen).</span><span class="sxs-lookup"><span data-stu-id="02186-200">currently provides no support for DML statements (insert, update, delete).</span></span>  
  
 <span data-ttu-id="02186-201">DDL</span><span class="sxs-lookup"><span data-stu-id="02186-201">DDL</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-202">stellt in der aktuellen Version keine Unterstützung für DDL bereit.</span><span class="sxs-lookup"><span data-stu-id="02186-202">provides no support for DDL in the current version.</span></span>  
  
 <span data-ttu-id="02186-203">Imperative Programmierung</span><span class="sxs-lookup"><span data-stu-id="02186-203">Imperative Programming</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-204">stellt im Gegensatz zu [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] keine Unterstützung für die imperative Programmierung bereit.</span><span class="sxs-lookup"><span data-stu-id="02186-204">provides no support for imperative programming, unlike [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="02186-205">Stattdessen sollte eine Programmiersprache verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="02186-205">Use a programming language instead.</span></span>  
  
 <span data-ttu-id="02186-206">Gruppierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="02186-206">Grouping Functions</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-207">unterstützt bisher keine Gruppierungsfunktionen wie CUBE, ROLLUP und GROUPING_SET.</span><span class="sxs-lookup"><span data-stu-id="02186-207">does not yet provide support for grouping functions (for example, CUBE, ROLLUP, and GROUPING_SET).</span></span>  
  
 <span data-ttu-id="02186-208">Analytische Funktionen</span><span class="sxs-lookup"><span data-stu-id="02186-208">Analytic Functions</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-209">unterstützt (bisher) keine analytischen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="02186-209">does not (yet) provide support for analytic functions.</span></span>  
  
 <span data-ttu-id="02186-210">Integrierte Funktionen, Operatoren</span><span class="sxs-lookup"><span data-stu-id="02186-210">Built-in Functions, Operators</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-211">unterstützt eine Teilmenge der [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]der integrierten Funktionen und Operatoren.</span><span class="sxs-lookup"><span data-stu-id="02186-211">supports a subset of [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]'s built in functions and operators.</span></span> <span data-ttu-id="02186-212">Diese Operatoren und Funktionen werden sehr wahrscheinlich von den großen Speicheranbietern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="02186-212">These operators and functions are likely to be supported by the major store providers.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-213">verwendet die in einem Anbietermanifest deklarierten speicherspezifischen Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="02186-213">uses the store-specific functions declared in a provider manifest.</span></span> <span data-ttu-id="02186-214">Darüber hinaus die [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] ermöglicht es Ihnen, deklarieren Sie integrierte und benutzerdefinierte Speicherfunktionen für [!INCLUDE[esql](../../../../../../includes/esql-md.md)] verwenden.</span><span class="sxs-lookup"><span data-stu-id="02186-214">Additionally, the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] allows you to declare built-in and user-defined existing store functions, for [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to use.</span></span>  
  
 <span data-ttu-id="02186-215">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02186-215">Hints</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-216">stellt keine Mechanismen für Abfragehinweise bereit.</span><span class="sxs-lookup"><span data-stu-id="02186-216">does not provide mechanisms for query hints.</span></span>  
  
 <span data-ttu-id="02186-217">Batchabfrageergebnisse</span><span class="sxs-lookup"><span data-stu-id="02186-217">Batching Query Results</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-218">unterstützt keine Batchabfrageergebnisse.</span><span class="sxs-lookup"><span data-stu-id="02186-218">does not support batching query results.</span></span> <span data-ttu-id="02186-219">Beispielsweise ist Folgendes gültig [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] (als Batch gesendet):</span><span class="sxs-lookup"><span data-stu-id="02186-219">For example, the following is valid [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] (sending as a batch):</span></span>  
  
```  
select * from products;  
select * from catagories;  
```  
  
 <span data-ttu-id="02186-220">Die äquivalente Anweisung wird in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] jedoch nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="02186-220">However, the equivalent [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not supported:</span></span>  
  
```  
Select value p from Products as p;  
Select value c from Categories as c;  
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="02186-221">unterstützt nur eine Ergebnisse liefernde Abfrageanweisung pro Befehl.</span><span class="sxs-lookup"><span data-stu-id="02186-221">only supports one result-producing query statement per command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02186-222">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02186-222">See also</span></span>
- [<span data-ttu-id="02186-223">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="02186-223">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="02186-224">Nicht unterstützte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="02186-224">Unsupported Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md)
