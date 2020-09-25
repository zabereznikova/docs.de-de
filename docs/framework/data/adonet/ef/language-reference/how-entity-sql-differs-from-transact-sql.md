---
title: Unterschiede zwischen Entity SQL und Transact-SQL
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: 9433e7a7ffdc3a7e32900981dca95eefde32f290
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204436"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a><span data-ttu-id="1193c-102">Unterschiede zwischen Entity SQL und Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1193c-102">How Entity SQL differs from Transact-SQL</span></span>

<span data-ttu-id="1193c-103">Dieser Artikel beschreibt die Unterschiede zwischen Entity SQL und Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="1193c-103">This article describes the differences between Entity SQL and Transact-SQL.</span></span>  
  
## <a name="inheritance-and-relationships-support"></a><span data-ttu-id="1193c-104">Unterstützung von Vererbung und Beziehungen</span><span class="sxs-lookup"><span data-stu-id="1193c-104">Inheritance and Relationships Support</span></span>  

 <span data-ttu-id="1193c-105">Entity SQL funktioniert direkt mit konzeptionellen Entitäts Schemas und unterstützt konzeptionelle Modell Funktionen wie Vererbung und Beziehungen.</span><span class="sxs-lookup"><span data-stu-id="1193c-105">Entity SQL works directly with conceptual entity schemas and supports conceptual model features such as inheritance and relationships.</span></span>  
  
 <span data-ttu-id="1193c-106">Bei der Vererbung ist es häufig nützlich, Instanzen eines Untertyps aus einer Auflistung von Instanzen des Obertyps auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="1193c-106">When working with inheritance, it is often useful to select instances of a subtype from a collection of supertype instances.</span></span> <span data-ttu-id="1193c-107">Der [OfType](oftype-entity-sql.md) -Operator in Entity SQL (ähnlich wie `oftype` in c#-Sequenzen) bietet diese Funktion.</span><span class="sxs-lookup"><span data-stu-id="1193c-107">The [oftype](oftype-entity-sql.md) operator in Entity SQL (similar to `oftype` in C# Sequences) provides this capability.</span></span>  
  
## <a name="support-for-collections"></a><span data-ttu-id="1193c-108">Unterstützung von Auflistungen</span><span class="sxs-lookup"><span data-stu-id="1193c-108">Support for Collections</span></span>  

 <span data-ttu-id="1193c-109">Entity SQL behandelt Auflistungen als erstklassige Entitäten.</span><span class="sxs-lookup"><span data-stu-id="1193c-109">Entity SQL treats collections as first-class entities.</span></span> <span data-ttu-id="1193c-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1193c-110">For example:</span></span>  
  
- <span data-ttu-id="1193c-111">In einer `from`-Klausel sind Auflistungsausdrücke gültig.</span><span class="sxs-lookup"><span data-stu-id="1193c-111">Collection expressions are valid in a `from` clause.</span></span>  
  
- <span data-ttu-id="1193c-112">`in` und `exists`-Unterabfragen wurden so verallgemeinert, dass sämtliche Auflistungen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="1193c-112">`in` and `exists` subqueries have been generalized to allow any collections.</span></span>  
  
     <span data-ttu-id="1193c-113">Eine Unterabfrage ist eine Art von Auflistung.</span><span class="sxs-lookup"><span data-stu-id="1193c-113">A subquery is one kind of collection.</span></span> <span data-ttu-id="1193c-114">`e1 in e2` und `exists(e)` sind die Entity SQL-Konstrukte zum Ausführen dieser Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="1193c-114">`e1 in e2` and `exists(e)` are the Entity SQL constructs to perform these operations.</span></span>  
  
- <span data-ttu-id="1193c-115">Mengenoperationen, z. B. `union`, `intersect` und `except`, verarbeiten nun Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="1193c-115">Set operations, such as `union`, `intersect`, and `except`, now operate on collections.</span></span>  
  
- <span data-ttu-id="1193c-116">Joins verarbeiten Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="1193c-116">Joins operate on collections.</span></span>  
  
## <a name="support-for-expressions"></a><span data-ttu-id="1193c-117">Unterstützung von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="1193c-117">Support for Expressions</span></span>  

 <span data-ttu-id="1193c-118">Transact-SQL enthält Unterabfragen (Tabellen) und Ausdrücke (Zeilen und Spalten).</span><span class="sxs-lookup"><span data-stu-id="1193c-118">Transact-SQL has subqueries (tables) and expressions (rows and columns).</span></span>  
  
 <span data-ttu-id="1193c-119">Um Auflistungen und Auflistungen zu unterstützen, stellt Entity SQL alles als Ausdruck dar.</span><span class="sxs-lookup"><span data-stu-id="1193c-119">To support collections and nested collections, Entity SQL makes everything an expression.</span></span> <span data-ttu-id="1193c-120">Entity SQL ist Zusammensetz barer als Transact-SQL – jeder Ausdruck kann überall verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1193c-120">Entity SQL is more composable than Transact-SQL—every expression can be used anywhere.</span></span> <span data-ttu-id="1193c-121">Abfrageausdrücke geben stets Auflistungen der projizierten Typen zurück und können immer verwendet werden, wenn ein Auflistungsausdruck zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="1193c-121">Query expressions always result in collections of the projected types and can be used anywhere a collection expression is allowed.</span></span> <span data-ttu-id="1193c-122">Informationen zu Transact-SQL-Ausdrücken, die in Entity SQL nicht unterstützt werden, finden Sie unter [nicht unterstützte Ausdrücke](unsupported-expressions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1193c-122">For information about Transact-SQL expressions that are not supported in Entity SQL, see [Unsupported Expressions](unsupported-expressions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="1193c-123">Im folgenden sind alle gültigen Entity SQL Abfragen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="1193c-123">The following are all valid Entity SQL queries:</span></span>  
  
```sql  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a><span data-ttu-id="1193c-124">Einheitliche Behandlung von Unterabfragen</span><span class="sxs-lookup"><span data-stu-id="1193c-124">Uniform Treatment of Subqueries</span></span>  

 <span data-ttu-id="1193c-125">Durch die Betonung von Tabellen führt Transact-SQL eine Kontext gesteuerte Interpretation von Unterabfragen durch.</span><span class="sxs-lookup"><span data-stu-id="1193c-125">Given its emphasis on tables, Transact-SQL performs contextual interpretation of subqueries.</span></span> <span data-ttu-id="1193c-126">Beispielsweise wird eine Unterabfrage in der- `from` Klausel als Multimenge (Table) betrachtet.</span><span class="sxs-lookup"><span data-stu-id="1193c-126">For example, a subquery in the `from` clause is considered to be a multiset (table).</span></span> <span data-ttu-id="1193c-127">Dieselbe Unterabfrage in der `select`-Klausel wird hingegen als skalare Unterabfrage aufgefasst.</span><span class="sxs-lookup"><span data-stu-id="1193c-127">But the same subquery used in the `select` clause is considered to be a scalar subquery.</span></span> <span data-ttu-id="1193c-128">Auf ähnliche Weise wird eine Unterabfrage, die auf der linken Seite eines Operators verwendet wird `in` , als skalare Unterabfrage betrachtet, während die Rechte Seite eine Multiset-Unterabfrage sein soll.</span><span class="sxs-lookup"><span data-stu-id="1193c-128">Similarly, a subquery used on the left side of an `in` operator is considered to be a scalar subquery, while the right side is expected to be a multiset subquery.</span></span>  
  
 <span data-ttu-id="1193c-129">Entity SQL beseitigt diese Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="1193c-129">Entity SQL eliminates these differences.</span></span> <span data-ttu-id="1193c-130">Ein Ausdruck verfügt über eine einheitliche vom Kontext unabhängige Auslegung.</span><span class="sxs-lookup"><span data-stu-id="1193c-130">An expression has a uniform interpretation that does not depend on the context in which it is used.</span></span> <span data-ttu-id="1193c-131">Entity SQL betrachtet alle Unterabfragen als multiset-Unterabfragen.</span><span class="sxs-lookup"><span data-stu-id="1193c-131">Entity SQL considers all subqueries to be multiset subqueries.</span></span> <span data-ttu-id="1193c-132">Wenn ein Skalarwert aus der Unterabfrage gewünscht wird, stellt Entity SQL den Operator bereit, der `anyelement` eine Auflistung (in diesem Fall die Unterabfrage) bearbeitet und einen Singleton-Wert aus der Auflistung extrahiert.</span><span class="sxs-lookup"><span data-stu-id="1193c-132">If a scalar value is desired from the subquery, Entity SQL provides the `anyelement` operator that operates on a collection (in this case, the subquery), and extracts a singleton value from the collection.</span></span>  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a><span data-ttu-id="1193c-133">Vermeiden impliziter Koersionen für Unterabfragen</span><span class="sxs-lookup"><span data-stu-id="1193c-133">Avoiding Implicit Coercions for Subqueries</span></span>  

 <span data-ttu-id="1193c-134">Ein Nebeneffekt der einheitlichen Behandlung von Unterabfragen ist die implizite Konvertierung von Unterabfragen zu skalaren Werten.</span><span class="sxs-lookup"><span data-stu-id="1193c-134">A related side effect of uniform treatment of subqueries is implicit conversion of subqueries to scalar values.</span></span> <span data-ttu-id="1193c-135">Insbesondere in Transact-SQL wird eine Multimenge von Zeilen (mit einem einzelnen Feld) implizit in einen skalaren Wert konvertiert, dessen Datentyp dem des Felds entspricht.</span><span class="sxs-lookup"><span data-stu-id="1193c-135">Specifically, in Transact-SQL, a multiset of rows (with a single field) is implicitly converted into a scalar value whose data type is that of the field.</span></span>  
  
 <span data-ttu-id="1193c-136">Entity SQL unterstützt diese implizite Koersion nicht.</span><span class="sxs-lookup"><span data-stu-id="1193c-136">Entity SQL does not support this implicit coercion.</span></span> <span data-ttu-id="1193c-137">Entity SQL stellt den `ANYELEMENT` -Operator bereit, um einen Singleton-Wert aus einer Auflistung zu extrahieren, und eine- `select value` Klausel, um zu vermeiden, dass während eines Abfrage Ausdrucks ein Zeilen Wrapper erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1193c-137">Entity SQL provides the `ANYELEMENT` operator to extract a singleton value from a collection, and a `select value` clause to avoid creating a row-wrapper during a query expression.</span></span>  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a><span data-ttu-id="1193c-138">Select Value: Vermeiden des impliziten Zeilen-Wrappers</span><span class="sxs-lookup"><span data-stu-id="1193c-138">Select Value: Avoiding the Implicit Row Wrapper</span></span>  

 <span data-ttu-id="1193c-139">Die SELECT-Klausel in einer Transact-SQL-Unterabfrage erstellt implizit einen Zeilen Wrapper um die Elemente in der-Klausel.</span><span class="sxs-lookup"><span data-stu-id="1193c-139">The select clause in a Transact-SQL subquery implicitly creates a row wrapper around the items in the clause.</span></span> <span data-ttu-id="1193c-140">Dies bedeutet, dass keine Auflistungen von Skalaren oder Objekten erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="1193c-140">This implies that we cannot create collections of scalars or objects.</span></span> <span data-ttu-id="1193c-141">Transact-SQL lässt eine implizite Koersion zwischen einem `rowtype` -Wert und einem Singleton-Wert desselben Datentyps zu.</span><span class="sxs-lookup"><span data-stu-id="1193c-141">Transact-SQL allows an implicit coercion between a `rowtype` with one field and a singleton value of the same data type.</span></span>  
  
 <span data-ttu-id="1193c-142">Entity SQL stellt die- `select value` Klausel bereit, um die implizite Zeilen Konstruktion zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="1193c-142">Entity SQL provides the `select value` clause to skip the implicit row construction.</span></span> <span data-ttu-id="1193c-143">In einer `select value`-Klausel kann nur ein Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1193c-143">Only one item may be specified in a `select value` clause.</span></span> <span data-ttu-id="1193c-144">Wenn eine solche Klausel verwendet wird, wird kein Zeilen Wrapper um die Elemente in der `select` -Klausel erstellt, und es kann eine Auflistung der gewünschten Form erstellt werden, z `select value a` . b..</span><span class="sxs-lookup"><span data-stu-id="1193c-144">When such a clause is used, no row wrapper is constructed around the items in the `select` clause, and a collection of the desired shape may be produced, for example, `select value a`.</span></span>  
  
 <span data-ttu-id="1193c-145">Entity SQL bietet auch den Zeilenkonstruktor, um beliebige Zeilen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1193c-145">Entity SQL also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="1193c-146">`select` nimmt ein oder mehrere Elemente in der Projektion an und führt zu einem Datensatz mit folgenden Feldern:</span><span class="sxs-lookup"><span data-stu-id="1193c-146">`select` takes one or more elements in the projection and results in a data record with fields:</span></span>  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a><span data-ttu-id="1193c-147">Linkskorrelation und Aliasing</span><span class="sxs-lookup"><span data-stu-id="1193c-147">Left Correlation and Aliasing</span></span>  

 <span data-ttu-id="1193c-148">In Transact-SQL können Ausdrücke in einem bestimmten Bereich (eine einzelne Klausel wie `select` oder `from` ) nicht auf Ausdrücke verweisen, die zuvor im selben Bereich definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1193c-148">In Transact-SQL, expressions in a given scope (a single clause like `select` or `from`) cannot reference expressions defined earlier in the same scope.</span></span> <span data-ttu-id="1193c-149">Einige Dialekte von SQL (einschließlich Transact-SQL) unterstützen eingeschränkte Formen dieser in der- `from` Klausel.</span><span class="sxs-lookup"><span data-stu-id="1193c-149">Some dialects of SQL (including Transact-SQL) do support limited forms of these in the `from` clause.</span></span>  
  
 <span data-ttu-id="1193c-150">Entity SQL verallgemeinert linke Korrelationen in der `from` -Klausel und behandelt diese gleichmäßig.</span><span class="sxs-lookup"><span data-stu-id="1193c-150">Entity SQL generalizes left correlations in the `from` clause, and treats them uniformly.</span></span> <span data-ttu-id="1193c-151">Ausdrücke in der `from`-Klausel können ohne die Verwendung zusätzlicher Syntax auf vorherige Definitionen (Definitionen auf der linken Seite) in derselben Klausel verweisen.</span><span class="sxs-lookup"><span data-stu-id="1193c-151">Expressions in the `from` clause can reference earlier definitions (definitions to the left) in the same clause without the need for additional syntax.</span></span>  
  
 <span data-ttu-id="1193c-152">Entity SQL setzt auch zusätzliche Einschränkungen für Abfragen ein, die `group by` Klauseln einschließen.</span><span class="sxs-lookup"><span data-stu-id="1193c-152">Entity SQL also imposes additional restrictions on queries involving `group by` clauses.</span></span> <span data-ttu-id="1193c-153">Ausdrücke in der `select` -Klausel und- `having` Klausel dieser Abfragen können nur `group by` über ihre Aliase auf die Schlüssel verweisen.</span><span class="sxs-lookup"><span data-stu-id="1193c-153">Expressions in the `select` clause and `having` clause of such queries may only refer to the `group by` keys via their aliases.</span></span> <span data-ttu-id="1193c-154">Das folgende Konstrukt ist in Transact-SQL gültig, aber nicht in Entity SQL:</span><span class="sxs-lookup"><span data-stu-id="1193c-154">The following construct is valid in Transact-SQL but are not in Entity SQL:</span></span>  
  
```sql  
SELECT t.x + t.y FROM T AS t group BY t.x + t.y
```  
  
 <span data-ttu-id="1193c-155">Gehen Sie dazu wie folgt Entity SQL vor:</span><span class="sxs-lookup"><span data-stu-id="1193c-155">To do this in Entity SQL:</span></span>  
  
```sql  
SELET k FROM T AS t GROUP BY (t.x + t.y) AS k
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a><span data-ttu-id="1193c-156">Verweisen auf Spalten (Eigenschaften) von Tabellen (Auflistungen)</span><span class="sxs-lookup"><span data-stu-id="1193c-156">Referencing Columns (Properties) of Tables (Collections)</span></span>  

 <span data-ttu-id="1193c-157">Alle Spalten Verweise in Entity SQL müssen mit dem Tabellenalias qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="1193c-157">All column references in Entity SQL must be qualified with the table alias.</span></span> <span data-ttu-id="1193c-158">Das folgende Konstrukt (vorausgesetzt, dass `a` eine gültige Spalte der Tabelle ist `T` ) ist in Transact-SQL gültig, aber nicht in Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="1193c-158">The following construct (assuming that `a` is a valid column of table `T`) is valid in Transact-SQL but not in Entity SQL.</span></span>  
  
```sql  
SELECT a FROM T
```  
  
 <span data-ttu-id="1193c-159">Das Entity SQL Formular ist</span><span class="sxs-lookup"><span data-stu-id="1193c-159">The Entity SQL form is</span></span>  
  
```sql  
SELECT t.a AS A FROM T AS t
```  
  
 <span data-ttu-id="1193c-160">Die Tabellenaliase sind in der `from`-Klausel optional.</span><span class="sxs-lookup"><span data-stu-id="1193c-160">The table aliases are optional in the `from` clause.</span></span> <span data-ttu-id="1193c-161">Der Name der Tabelle wird als implizites Alias verwendet.</span><span class="sxs-lookup"><span data-stu-id="1193c-161">The name of the table is used as the implicit alias.</span></span> <span data-ttu-id="1193c-162">Entity SQL lässt auch das folgende Formular zu:</span><span class="sxs-lookup"><span data-stu-id="1193c-162">Entity SQL allows the following form as well:</span></span>  
  
```sql  
SELET Tab.a FROM Tab
```  
  
## <a name="navigation-through-objects"></a><span data-ttu-id="1193c-163">Navigieren durch Objekte</span><span class="sxs-lookup"><span data-stu-id="1193c-163">Navigation Through Objects</span></span>  

 <span data-ttu-id="1193c-164">Transact-SQL verwendet die Notation "." zum Verweisen auf Spalten von (einer Zeile) einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1193c-164">Transact-SQL uses the "." notation for referencing columns of (a row of) a table.</span></span> <span data-ttu-id="1193c-165">Entity SQL erweitert diese Schreibweise (aus Programmiersprachen entnommen), um die Navigation durch Eigenschaften eines Objekts zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1193c-165">Entity SQL extends this notation (borrowed from programming languages) to support navigation through properties of an object.</span></span>  
  
 <span data-ttu-id="1193c-166">Wenn z. b `p` . ein Ausdruck vom Typ "Person" ist, ist Folgendes die Entity SQL Syntax zum Verweisen auf die Stadt der Adresse dieser Person.</span><span class="sxs-lookup"><span data-stu-id="1193c-166">For example, if `p` is an expression of type Person, the following is the Entity SQL syntax for referencing the city of the address of this person.</span></span>  
  
```sql  
p.Address.City
```  
  
## <a name="no-support-for-"></a><span data-ttu-id="1193c-167">Keine Unterstützung für \*</span><span class="sxs-lookup"><span data-stu-id="1193c-167">No Support for \*</span></span>  

 <span data-ttu-id="1193c-168">Transact-SQL unterstützt die nicht qualifizierte \* Syntax als Alias für die gesamte Zeile und die qualifizierte \* Syntax (t. \* ) als Verknüpfung für die Felder dieser Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1193c-168">Transact-SQL supports the unqualified \* syntax as an alias for the entire row, and the qualified \* syntax (t.\*) as a shortcut for the fields of that table.</span></span> <span data-ttu-id="1193c-169">Außerdem ermöglicht Transact-SQL ein spezielles count ( \* )-Aggregat, das NULL-Werten enthält.</span><span class="sxs-lookup"><span data-stu-id="1193c-169">In addition, Transact-SQL allows for a special count(\*) aggregate, which includes nulls.</span></span>  
  
 <span data-ttu-id="1193c-170">Entity SQL unterstützt das \*-Konstrukt nicht.</span><span class="sxs-lookup"><span data-stu-id="1193c-170">Entity SQL does not support the \* construct.</span></span> <span data-ttu-id="1193c-171">Transact-SQL-Abfragen der Form `select * from T` und `select T1.* from T1, T2...` können in Entity SQL als `select value t from T as t` `select value t1 from T1 as t1, T2 as t2...` bzw. ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="1193c-171">Transact-SQL queries of the form `select * from T` and `select T1.* from T1, T2...` can be expressed in Entity SQL as `select value t from T as t` and `select value t1 from T1 as t1, T2 as t2...`, respectively.</span></span> <span data-ttu-id="1193c-172">Außerdem behandeln diese Konstrukte Vererbung (Wertersetzbarkeit), während die `select *`-Varianten auf die Eigenschaften des deklarierten Typen auf oberster Ebene eingeschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="1193c-172">Additionally, these constructs handle inheritance (value substitutability), while the `select *` variants are restricted to top-level properties of the declared type.</span></span>  
  
 <span data-ttu-id="1193c-173">Entity SQL unterstützt das `count(*)` Aggregat nicht.</span><span class="sxs-lookup"><span data-stu-id="1193c-173">Entity SQL does not support the `count(*)` aggregate.</span></span> <span data-ttu-id="1193c-174">Verwenden Sie stattdessen `count(0)`.</span><span class="sxs-lookup"><span data-stu-id="1193c-174">Use `count(0)` instead.</span></span>  
  
## <a name="changes-to-group-by"></a><span data-ttu-id="1193c-175">Änderungen an "Group By"</span><span class="sxs-lookup"><span data-stu-id="1193c-175">Changes to Group By</span></span>  

 <span data-ttu-id="1193c-176">Entity SQL unterstützt das Aliasing von `group by` Schlüsseln.</span><span class="sxs-lookup"><span data-stu-id="1193c-176">Entity SQL supports aliasing of `group by` keys.</span></span> <span data-ttu-id="1193c-177">Ausdrücke in der `select`-Klausel und der `having`-Klausel müssen mithilfe dieser Aliase auf die `group by`-Schlüssel verweisen.</span><span class="sxs-lookup"><span data-stu-id="1193c-177">Expressions in the `select` clause and `having` clause must refer to the `group by` keys via these aliases.</span></span> <span data-ttu-id="1193c-178">Dies Entity SQL z. b. die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="1193c-178">For example, this Entity SQL syntax:</span></span>  
  
```sql  
SELECT k1, count(t.a), sum(t.a)
FROM T AS t
GROUP BY t.b + t.c AS k1
```  
  
 <span data-ttu-id="1193c-179">... entspricht folgendem Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="1193c-179">...is equivalent to the following Transact-SQL:</span></span>  
  
```sql  
SELECT b + c, count(*), sum(a)
FROM T
GROUP BY b + c
```  
  
## <a name="collection-based-aggregates"></a><span data-ttu-id="1193c-180">Auflistungsbasierte Aggregate</span><span class="sxs-lookup"><span data-stu-id="1193c-180">Collection-Based Aggregates</span></span>  

 <span data-ttu-id="1193c-181">Entity SQL unterstützt zwei Arten von Aggregaten.</span><span class="sxs-lookup"><span data-stu-id="1193c-181">Entity SQL supports two kinds of aggregates.</span></span>  
  
 <span data-ttu-id="1193c-182">Auflistungsbasierte Aggregate verarbeiten Auflistungen und erstellen das aggregierte Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="1193c-182">Collection-based aggregates operate on collections and produce the aggregated result.</span></span> <span data-ttu-id="1193c-183">Sie können überall in der Abfrage stehen und erfordern keine `group by`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="1193c-183">These can appear anywhere in the query, and do not require a `group by` clause.</span></span> <span data-ttu-id="1193c-184">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1193c-184">For example:</span></span>  
  
```sql  
SELECT t.a AS a, count({1,2,3}) AS b FROM T AS t
```  
  
 <span data-ttu-id="1193c-185">Entity SQL unterstützt auch Aggregate im SQL-Stil.</span><span class="sxs-lookup"><span data-stu-id="1193c-185">Entity SQL also supports SQL-style aggregates.</span></span> <span data-ttu-id="1193c-186">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1193c-186">For example:</span></span>  
  
```sql  
SELECT a, sum(t.b) FROM T AS t GROUP BY t.a AS a
```  
  
## <a name="order-by-clause-usage"></a><span data-ttu-id="1193c-187">Verwendung der "ORDER BY"-Klausel</span><span class="sxs-lookup"><span data-stu-id="1193c-187">ORDER BY Clause Usage</span></span>  

<span data-ttu-id="1193c-188">Transact-SQL lässt `ORDER BY` zu, dass Klauseln nur im obersten Block angegeben werden `SELECT .. FROM .. WHERE` .</span><span class="sxs-lookup"><span data-stu-id="1193c-188">Transact-SQL allows `ORDER BY` clauses to be specified only in the topmost `SELECT .. FROM .. WHERE` block.</span></span> <span data-ttu-id="1193c-189">In Entity SQL können Sie einen eingefügten `ORDER BY` Ausdruck verwenden, der an einer beliebigen Stelle in der Abfrage platziert werden kann, aber die Reihenfolge in einer genetzten Abfrage wird nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="1193c-189">In Entity SQL, you can use a nested `ORDER BY` expression and it can be placed anywhere in the query, but ordering in a nested query is not preserved.</span></span>  
  
```sql  
-- The following query will order the results by the last name  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact AS C1
        ORDER BY C1.LastName  
```  
  
```sql  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="identifiers"></a><span data-ttu-id="1193c-190">Bezeichner</span><span class="sxs-lookup"><span data-stu-id="1193c-190">Identifiers</span></span>  

 <span data-ttu-id="1193c-191">In Transact-SQL basiert der Bezeichnervergleich auf der Sortierung der aktuellen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="1193c-191">In Transact-SQL, identifier comparison is based on the collation of the current database.</span></span> <span data-ttu-id="1193c-192">In Entity SQL wird bei bezeichnerbezeichnerzeichen immer nach Groß-und Kleinschreibung unterschieden (d. h., Entity SQL unterscheidet zwischen Zeichen mit Akzent und Zeichen ohne Akzent; beispielsweise ist "a" nicht gleich "ấ").</span><span class="sxs-lookup"><span data-stu-id="1193c-192">In Entity SQL, identifiers are always case insensitive and accent sensitive (that is, Entity SQL distinguishes between accented and unaccented characters; for example, 'a' is not equal to 'ấ').</span></span> <span data-ttu-id="1193c-193">Entity SQL behandelt Versionen von Buchstaben, die identisch erscheinen, aber aus unterschiedlichen Codepages als verschiedene Zeichen stammen.</span><span class="sxs-lookup"><span data-stu-id="1193c-193">Entity SQL treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="1193c-194">Weitere Informationen finden Sie unter [Eingabe Zeichensatz](input-character-set-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1193c-194">For more information, see [Input Character Set](input-character-set-entity-sql.md).</span></span>  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a><span data-ttu-id="1193c-195">Transact-SQL-Funktionalität ist in Entity SQL nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="1193c-195">Transact-SQL Functionality Not Available in Entity SQL</span></span>  

 <span data-ttu-id="1193c-196">Die folgenden Transact-SQL-Funktionen sind in Entity SQL nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1193c-196">The following Transact-SQL functionality is not available in Entity SQL.</span></span>  
  
 <span data-ttu-id="1193c-197">DML</span><span class="sxs-lookup"><span data-stu-id="1193c-197">DML</span></span>  
 <span data-ttu-id="1193c-198">Entity SQL bietet derzeit keine Unterstützung für DML-Anweisungen (INSERT, Update, DELETE).</span><span class="sxs-lookup"><span data-stu-id="1193c-198">Entity SQL currently provides no support for DML statements (insert, update, delete).</span></span>  
  
 <span data-ttu-id="1193c-199">DDL</span><span class="sxs-lookup"><span data-stu-id="1193c-199">DDL</span></span>  
 <span data-ttu-id="1193c-200">Entity SQL bietet keine Unterstützung für DDL in der aktuellen Version.</span><span class="sxs-lookup"><span data-stu-id="1193c-200">Entity SQL provides no support for DDL in the current version.</span></span>  
  
 <span data-ttu-id="1193c-201">Imperative Programmierung</span><span class="sxs-lookup"><span data-stu-id="1193c-201">Imperative Programming</span></span>  
 <span data-ttu-id="1193c-202">Entity SQL bietet im Gegensatz zu Transact-SQL keine Unterstützung für Imperatives programmieren.</span><span class="sxs-lookup"><span data-stu-id="1193c-202">Entity SQL provides no support for imperative programming, unlike Transact-SQL.</span></span> <span data-ttu-id="1193c-203">Stattdessen sollte eine Programmiersprache verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1193c-203">Use a programming language instead.</span></span>  
  
 <span data-ttu-id="1193c-204">Gruppierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="1193c-204">Grouping Functions</span></span>  
 <span data-ttu-id="1193c-205">Entity SQL bietet noch keine Unterstützung für Gruppierungsfunktionen (z. b. Cube, Rollup und GROUPING_SET).</span><span class="sxs-lookup"><span data-stu-id="1193c-205">Entity SQL does not yet provide support for grouping functions (for example, CUBE, ROLLUP, and GROUPING_SET).</span></span>  
  
 <span data-ttu-id="1193c-206">Analysefunktionen</span><span class="sxs-lookup"><span data-stu-id="1193c-206">Analytic Functions</span></span>  
 <span data-ttu-id="1193c-207">Entity SQL bietet noch keine Unterstützung für analytische Funktionen.</span><span class="sxs-lookup"><span data-stu-id="1193c-207">Entity SQL does not (yet) provide support for analytic functions.</span></span>  
  
 <span data-ttu-id="1193c-208">Integrierte Funktionen, Operatoren</span><span class="sxs-lookup"><span data-stu-id="1193c-208">Built-in Functions, Operators</span></span>  
 <span data-ttu-id="1193c-209">Entity SQL unterstützt eine Teilmenge der integrierten Transact-SQL-Funktionen und-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="1193c-209">Entity SQL supports a subset of Transact-SQL's built in functions and operators.</span></span> <span data-ttu-id="1193c-210">Diese Operatoren und Funktionen werden sehr wahrscheinlich von den großen Speicheranbietern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1193c-210">These operators and functions are likely to be supported by the major store providers.</span></span> <span data-ttu-id="1193c-211">Entity SQL verwendet die Speicher spezifischen Funktionen, die in einem Anbieter Manifest deklariert sind.</span><span class="sxs-lookup"><span data-stu-id="1193c-211">Entity SQL uses the store-specific functions declared in a provider manifest.</span></span> <span data-ttu-id="1193c-212">Darüber hinaus können Sie mit dem Entity Framework integrierte und benutzerdefinierte Speicherfunktionen deklarieren, die Entity SQL verwenden.</span><span class="sxs-lookup"><span data-stu-id="1193c-212">Additionally, the Entity Framework allows you to declare built-in and user-defined existing store functions, for Entity SQL to use.</span></span>  
  
 <span data-ttu-id="1193c-213">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1193c-213">Hints</span></span>  
 <span data-ttu-id="1193c-214">Entity SQL bietet keine Mechanismen für Abfrage Hinweise.</span><span class="sxs-lookup"><span data-stu-id="1193c-214">Entity SQL does not provide mechanisms for query hints.</span></span>  
  
 <span data-ttu-id="1193c-215">Batchabfrageergebnisse</span><span class="sxs-lookup"><span data-stu-id="1193c-215">Batching Query Results</span></span>  
 <span data-ttu-id="1193c-216">Entity SQL unterstützt keine Batch Verarbeitung von Abfrage Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="1193c-216">Entity SQL does not support batching query results.</span></span> <span data-ttu-id="1193c-217">Folgendes ist z. b. ein gültiges Transact-SQL (als Batch gesendet):</span><span class="sxs-lookup"><span data-stu-id="1193c-217">For example, the following is valid Transact-SQL (sending as a batch):</span></span>  
  
```sql  
SELECT * FROM products;
SELECT * FROM catagories;
```  
  
 <span data-ttu-id="1193c-218">Die entsprechende Entity SQL wird jedoch nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1193c-218">However, the equivalent Entity SQL is not supported:</span></span>  
  
```sql  
SELECT value p FROM Products AS p;
SELECT value c FROM Categories AS c;
```  
  
 <span data-ttu-id="1193c-219">Entity SQL unterstützt nur eine Abfrage Anweisung mit Ergebnis Generierung pro Befehl.</span><span class="sxs-lookup"><span data-stu-id="1193c-219">Entity SQL only supports one result-producing query statement per command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1193c-220">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1193c-220">See also</span></span>

- [<span data-ttu-id="1193c-221">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1193c-221">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="1193c-222">Nicht unterstützte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="1193c-222">Unsupported Expressions</span></span>](unsupported-expressions-entity-sql.md)
