---
title: Generieren von SQL aus Befehlsstrukturen – Best Practices
ms.date: 03/30/2017
ms.assetid: 71ef6a24-4c4f-4254-af3a-ffc0d855b0a8
ms.openlocfilehash: 869722b91550855a184a74e706271c3e2d417b84
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039999"
---
# <a name="generating-sql-from-command-trees---best-practices"></a><span data-ttu-id="4ad71-102">Generieren von SQL aus Befehlsstrukturen – Best Practices</span><span class="sxs-lookup"><span data-stu-id="4ad71-102">Generating SQL from Command Trees - Best Practices</span></span>

<span data-ttu-id="4ad71-103">Mit Befehlsstrukturen für Ausgabeabfragen werden Abfragen so modelliert, dass diese in SQL ausgedrückt werden können.</span><span class="sxs-lookup"><span data-stu-id="4ad71-103">Output query command trees closely model queries expressible in SQL.</span></span> <span data-ttu-id="4ad71-104">Beim Generieren von SQL anhand einer Ausgabebefehlsstruktur treten für die Anbieterwriter jedoch bestimmte allgemeine Probleme auf.</span><span class="sxs-lookup"><span data-stu-id="4ad71-104">However, there are certain common challenges for provider writers when generating SQL from an output command tree.</span></span> <span data-ttu-id="4ad71-105">Diese Probleme werden im Rahmen dieses Themas erläutert.</span><span class="sxs-lookup"><span data-stu-id="4ad71-105">This topic discusses these challenges.</span></span> <span data-ttu-id="4ad71-106">Im nächsten Thema wird anhand des Beispielanbieters aufgezeigt, wie diese Probleme gelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="4ad71-106">In the next topic, the sample provider shows how to address these challenges.</span></span>

## <a name="group-dbexpression-nodes-in-a-sql-select-statement"></a><span data-ttu-id="4ad71-107">Gruppieren von "DbExpression"-Knoten in einer SQL SELECT-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4ad71-107">Group DbExpression Nodes in a SQL SELECT Statement</span></span>

<span data-ttu-id="4ad71-108">Eine typische SQL-Anweisung verfügt über eine geschachtelte Struktur in folgender Form:</span><span class="sxs-lookup"><span data-stu-id="4ad71-108">A typical SQL statement has a nested structure of the following shape:</span></span>

```sql
SELECT …
FROM …
WHERE …
GROUP BY …
ORDER BY …
```

<span data-ttu-id="4ad71-109">Eine oder mehrere Klauseln sind möglicherweise leer.</span><span class="sxs-lookup"><span data-stu-id="4ad71-109">One or more clauses may be empty.</span></span>  <span data-ttu-id="4ad71-110">Eine geschachtelte SELECT-Anweisung kann in allen Zeilen auftreten.</span><span class="sxs-lookup"><span data-stu-id="4ad71-110">A nested SELECT statement could occur in any of the lines.</span></span>

<span data-ttu-id="4ad71-111">Eine mögliche Übersetzung einer Abfragebefehlsstruktur in eine SQL SELECT-Anweisung erzeugt für jeden relationalen Operatoren jeweils eine Unterabfrage.</span><span class="sxs-lookup"><span data-stu-id="4ad71-111">A possible translation of a query command tree into a SQL SELECT statement would produce one subquery for every relational operator.</span></span> <span data-ttu-id="4ad71-112">Dies führt jedoch zu unnötigen geschachtelten Unterabfragen, die nur schwer zu lesen sind.</span><span class="sxs-lookup"><span data-stu-id="4ad71-112">However, that would lead to unnecessary nested subqueries that would be difficult to read.</span></span>  <span data-ttu-id="4ad71-113">In einigen Datenspeichern verläuft die Abfrage daher möglicherweise unbefriedigend.</span><span class="sxs-lookup"><span data-stu-id="4ad71-113">On some data stores, the query may perform poorly.</span></span>

<span data-ttu-id="4ad71-114">Beachten Sie als Beispiel die folgende Abfragebefehlsstruktur</span><span class="sxs-lookup"><span data-stu-id="4ad71-114">As an example, consider the following query command tree</span></span>

```csharp
Project (
a.x,
   a = Filter(
      b.y = 5,
      b = Scan("TableA")
   )
)
```

<span data-ttu-id="4ad71-115">Bei einer ineffizienten Übersetzung wird Folgendes erzeugt:</span><span class="sxs-lookup"><span data-stu-id="4ad71-115">An inefficient translation would produce:</span></span>

```sql
SELECT a.x
FROM (   SELECT *
         FROM TableA as b
         WHERE b.y = 5) as a
```

<span data-ttu-id="4ad71-116">Beachten Sie, dass aus allen relationalen Ausdrucksknoten neue SQL SELECT-Anweisungen werden.</span><span class="sxs-lookup"><span data-stu-id="4ad71-116">Note that every relational expression node becomes a new SQL SELECT statement.</span></span>

<span data-ttu-id="4ad71-117">Daher ist es wichtig, so viele Ausdrucksknoten wie möglich in einer einzelnen SQL SELECT-Anweisung zu aggregieren, um Fehler zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="4ad71-117">Therefore, it is important to aggregate as many expression nodes as possible into a single SQL SELECT statement while preserving correctness.</span></span>

<span data-ttu-id="4ad71-118">Das Ergebnis einer solchen Aggregation für das oben angeführte Beispiel lautet:</span><span class="sxs-lookup"><span data-stu-id="4ad71-118">The result of such aggregation for the example presented above would be:</span></span>

```sql
SELECT b.x
FROM TableA as b
WHERE b.y = 5
```

## <a name="flatten-joins-in-a-sql-select-statement"></a><span data-ttu-id="4ad71-119">Vereinfachen von Joins in einer SQL SELECT-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4ad71-119">Flatten Joins in a SQL SELECT Statement</span></span>

<span data-ttu-id="4ad71-120">Eine Möglichkeit, mehrere Knoten in einer SQL SELECT-Anweisung zu aggregieren, ist das Aggregieren mehrerer Joinausdrücke in einer einzelnen SQL SELECT-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4ad71-120">One case of aggregating multiple nodes into a single SQL SELECT statement is aggregating multiple join expressions into a single SQL SELECT statement.</span></span> <span data-ttu-id="4ad71-121">"DbJoinExpression" stellt einen einzelnen Join zwischen zwei Eingaben dar.</span><span class="sxs-lookup"><span data-stu-id="4ad71-121">DbJoinExpression represents a single join between two inputs.</span></span> <span data-ttu-id="4ad71-122">Als Teil einer einzelnen SQL SELECT-Anweisung können jedoch mehrere Joins angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4ad71-122">However, as part of a single SQL SELECT statement, more than one join can be specified.</span></span> <span data-ttu-id="4ad71-123">In diesem Fall werden die Joins in der angegebenen Reihenfolge ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4ad71-123">In that case the joins are performed in the order specified.</span></span>

<span data-ttu-id="4ad71-124">Linke Joinelemente (Joins, die als linke untergeordnete Elemente eines anderen Joins angezeigt werden) können einfacher in einer einzelnen SQL SELECT-Anweisung vereinfacht werden.</span><span class="sxs-lookup"><span data-stu-id="4ad71-124">Left spine joins, (joins that appear as a left child of another join) can be more easily flattened into a single SQL SELECT statement.</span></span> <span data-ttu-id="4ad71-125">Beachten Sie als Beispiel die folgende Abfragebefehlsstruktur:</span><span class="sxs-lookup"><span data-stu-id="4ad71-125">For example, consider the following query command tree:</span></span>

```csharp
InnerJoin(
   a = LeftOuterJoin(
   b = Extent("TableA")
   c = Extent("TableB")
   ON b.y = c.x ),
   d = Extent("TableC")
   ON a.b.y = d.z
)
```

<span data-ttu-id="4ad71-126">Dies kann ordnungsgemäß übersetzt werden in:</span><span class="sxs-lookup"><span data-stu-id="4ad71-126">This can be correctly translated into:</span></span>

```sql
SELECT *
FROM TableA as b
LEFT OUTER JOIN TableB as c ON b.y = c.x
INNER JOIN TableC as d ON b.y = d.z
```

<span data-ttu-id="4ad71-127">Wenn es sich nicht um linke Joinelemente handelt, ist die Vereinfachung komplizierter und sollte daher nicht versucht werden.</span><span class="sxs-lookup"><span data-stu-id="4ad71-127">However, non-left spine joins cannot easily be flattened, and you should not try to flatten them.</span></span> <span data-ttu-id="4ad71-128">Beachten Sie z. B. die Joins in der folgenden Abfragebefehlsstruktur:</span><span class="sxs-lookup"><span data-stu-id="4ad71-128">For example, the joins in the following query command tree:</span></span>

```csharp
InnerJoin(
   a = Extent("TableA")
   b = LeftOuterJoin(
   c = Extent("TableB")
   d = Extent("TableC")
   ON c.y = d.x),
   ON a.z = b.c.y
)
```

<span data-ttu-id="4ad71-129">Diese würden in eine SQL SELECT-Anweisung mit einer Unterabfrage übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="4ad71-129">Would be translated to a SQL SELECT statement with a sub-query.</span></span>

```sql
SELECT *
FROM TableA as a
INNER JOIN (SELECT *
   FROM TableB as c
   LEFT OUTER JOIN TableC as d
   ON c.y = d.x) as b
ON b.y = d.z
```

## <a name="input-alias-redirecting"></a><span data-ttu-id="4ad71-130">Eingabealiasumleitung</span><span class="sxs-lookup"><span data-stu-id="4ad71-130">Input Alias Redirecting</span></span>

<span data-ttu-id="4ad71-131">Beachten Sie zur Erklärung der Eingabealiasumleitung die Struktur der relationalen Ausdrücke, z. B. von "DbFilterExpression", "DbProjectExpression", "DbCrossJoinExpression", "DbJoinExpression", "DbSortExpression", "DbGroupByExpression", "DbApplyExpression" und "DbSkipExpression".</span><span class="sxs-lookup"><span data-stu-id="4ad71-131">To explain input alias redirecting, consider the structure of the relational expressions, such as DbFilterExpression, DbProjectExpression, DbCrossJoinExpression, DbJoinExpression, DbSortExpression, DbGroupByExpression, DbApplyExpression, and DbSkipExpression.</span></span>

<span data-ttu-id="4ad71-132">Jeder dieser Typen verfügt über mindestens eine Eingabeeigenschaft, die eine Eingabeauflistung beschreibt, sowie über eine Bindungsvariable, die den einzelnen Eingaben entspricht, die verwendet werden, um während eines Auflistungsdurchlaufs die jeweiligen Elemente dieser Eingabe darzustellen.</span><span class="sxs-lookup"><span data-stu-id="4ad71-132">Each of these types has one or more Input properties that describe an input collection, and a binding variable corresponding to each input is used to represent each element of that input during a collection traversal.</span></span> <span data-ttu-id="4ad71-133">Die Bindungsvariable wird verwendet, wenn auf das Eingabeelement verwiesen wird, z. B. in der "Predicate"-Eigenschaft von "DbFilterExpression" oder der "Projection"-Eigenschaft von "DbProjectExpression".</span><span class="sxs-lookup"><span data-stu-id="4ad71-133">The binding variable is used when referring to the input element, for example in the Predicate property of a DbFilterExpression or the Projection property of a DbProjectExpression.</span></span>

<span data-ttu-id="4ad71-134">Beim Aggregieren mehrerer relationaler Ausdrucksknoten in einer einzelnen SQL SELECT-Anweisung und beim Auswerten eines Ausdrucks, der Teil eines relationalen Ausdrucks ist (z. B. ein Teil der „Projection“-Eigenschaft von DbProjectExpression), handelt es sich bei der verwendeten Bindungsvariable möglicherweise nicht um den Alias der Eingabe, da mehrere Ausdrucksbindungen an einen einzelnen Bereich umgeleitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4ad71-134">When aggregating more relational expression nodes into a single SQL SELECT statement, and evaluating an expression that is part of a relational expression (for example part of the Projection property of a DbProjectExpression) the binding variable that it uses may not be the same as the alias of the input, as multiple expression bindings would have to be redirected to a single extent.</span></span>  <span data-ttu-id="4ad71-135">Dieses Problem wird als Aliasumbenennung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4ad71-135">This problem is called alias renaming.</span></span>

<span data-ttu-id="4ad71-136">Beachten Sie das erste Beispiel in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="4ad71-136">Consider the first example in this topic.</span></span> <span data-ttu-id="4ad71-137">Bei der naiven Übersetzung trifft beim Übersetzen von „Projektion a.x (DbPropertyExpression(a, x))“ die Übersetzung in `a.x` zu, da der Alias der Eingabe als „a“ definiert wurde, sodass dieser mit der Bindungsvariable übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="4ad71-137">If doing the naïve translation and translating the Projection a.x (DbPropertyExpression(a, x)), it is correct to translate it into `a.x` because we have aliased the input as "a" to match the binding variable.</span></span>  <span data-ttu-id="4ad71-138">Wenn jedoch beide Knoten in einer einzelnen SQL SELECT-Anweisung aggregiert werden, müssen Sie denselben "DbPropertyExpression" in `b.x` übersetzen, da der Alias der Eingabe als "b" definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="4ad71-138">However, when aggregating both the nodes into a single SQL SELECT statement, you need to translate the same DbPropertyExpression into `b.x`, as the input has been aliased with "b".</span></span>

## <a name="join-alias-flattening"></a><span data-ttu-id="4ad71-139">Joinaliasvereinfachung</span><span class="sxs-lookup"><span data-stu-id="4ad71-139">Join Alias Flattening</span></span>

<span data-ttu-id="4ad71-140">Im Gegensatz zu anderen relationalen Ausdrücken einer Ausgabebefehlsstruktur gibt „DbJoinExpression“ einen Ergebnistyp aus, bei dem es sich um eine Zeile mit zwei Spalten handelt, die jeweils einer der Eingaben entsprechen.</span><span class="sxs-lookup"><span data-stu-id="4ad71-140">Unlike any other relational expression in an output command tree, the DbJoinExpression outputs a result type that is a row consisting of two columns, each of which corresponds to one of the inputs.</span></span> <span data-ttu-id="4ad71-141">Wenn ein DbPropertyExpression erstellt wird, um auf eine skalare Eigenschaft zuzugreifen, die von einem Join stammt, wird er über einem anderen DbPropertyExpression.</span><span class="sxs-lookup"><span data-stu-id="4ad71-141">When a DbPropertyExpression is built to access a scalar property originating from a join, it is over another DbPropertyExpression.</span></span>

<span data-ttu-id="4ad71-142">Beachten Sie z. B. "a.b.y" in Beispiel 2 und "b.c.y" in Beispiel 3.</span><span class="sxs-lookup"><span data-stu-id="4ad71-142">Examples include "a.b.y" in example 2 and "b.c.y" in example 3.</span></span> <span data-ttu-id="4ad71-143">In den entsprechenden SQL-Anweisungen werden diese jedoch als "b.y" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4ad71-143">However in the corresponding SQL statements these are referred as "b.y".</span></span> <span data-ttu-id="4ad71-144">Dieses erneute Aliasing wird als Joinaliasvereinfachung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4ad71-144">This re-aliasing is called join alias flattening.</span></span>

## <a name="column-name-and-extent-alias-renaming"></a><span data-ttu-id="4ad71-145">Spaltennamen- und Blockaliasumbenennung</span><span class="sxs-lookup"><span data-stu-id="4ad71-145">Column Name and Extent Alias Renaming</span></span>

<span data-ttu-id="4ad71-146">Wenn eine SQL SELECT-Abfrage, die einen Join enthält, mit einer Projektion abgeschlossen werden muss, kann beim Auflisten aller beteiligten Spalten der Eingaben ein Namenskonflikt auftreten, da möglicherweise mehrere Eingaben denselben Spaltennamen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4ad71-146">If a SQL SELECT query that has a join has to be completed with a projection, when enumerating all the participating columns from the inputs, a name collision may occur, as more than one input may have the same column name.</span></span> <span data-ttu-id="4ad71-147">Verwenden Sie einen anderen Spaltennamen, um den Konflikt zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="4ad71-147">Use a different name for the column to avoid the collision.</span></span>

<span data-ttu-id="4ad71-148">Auch beim Vereinfachen von Joins verfügen die beteiligten Tabellen (oder Unterabfragen) möglicherweise über miteinander in Konflikt stehende Aliase, die umbenannt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4ad71-148">Also, when flattening joins, participating tables (or subqueries) may have colliding aliases in which case these need to be renamed.</span></span>

## <a name="avoid-select-"></a><span data-ttu-id="4ad71-149">Vermeiden von SELECT \*</span><span class="sxs-lookup"><span data-stu-id="4ad71-149">Avoid SELECT \*</span></span>

<span data-ttu-id="4ad71-150">Verwenden Sie zum Auswählen aus Basistabellen nicht `SELECT *`.</span><span class="sxs-lookup"><span data-stu-id="4ad71-150">Do not use `SELECT *` to select from base tables.</span></span> <span data-ttu-id="4ad71-151">Das Speichermodell in einer Entity Framework Anwendung darf nur eine Teilmenge der Spalten enthalten, die in der Datenbanktabelle enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4ad71-151">The storage model in an Entity Framework application may only include a subset of the columns that are in the database table.</span></span> <span data-ttu-id="4ad71-152">In diesem Fall führt `SELECT *` möglicherweise zu einem falschen Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="4ad71-152">In this case, `SELECT *` may produce an incorrect result.</span></span> <span data-ttu-id="4ad71-153">Stattdessen sollten Sie alle beteiligten Spalten mithilfe des Spaltennamens des Ergebnistyps der teilnehmenden Ausdrücke angeben.</span><span class="sxs-lookup"><span data-stu-id="4ad71-153">Instead, you should specify all participating columns by using the column names from the result type of the participating expressions.</span></span>

## <a name="reuse-of-expressions"></a><span data-ttu-id="4ad71-154">Wiederverwendung von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="4ad71-154">Reuse of Expressions</span></span>

<span data-ttu-id="4ad71-155">Ausdrücke können in der vom Entity Framework übergebenen Abfrage Befehlsstruktur wieder verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4ad71-155">Expressions may be reused in the query command tree passed by the Entity Framework.</span></span> <span data-ttu-id="4ad71-156">Es sollte nicht davon ausgegangen werden, dass die einzelnen Ausdrücke in der Abfragebefehlsstruktur nur einmal vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="4ad71-156">Do not assume that each expression appears only once in the query command tree.</span></span>

## <a name="mapping-primitive-types"></a><span data-ttu-id="4ad71-157">Zuordnen von primitiven Typen</span><span class="sxs-lookup"><span data-stu-id="4ad71-157">Mapping Primitive Types</span></span>

<span data-ttu-id="4ad71-158">Wenn Sie konzeptionelle Typen (EDM) Anbietertypen zuordnen, sollte die Zuordnung zum allgemeinsten Typ (Int32) erfolgen, sodass alle möglichen Werte geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="4ad71-158">When mapping conceptual (EDM) types to provider types, you should map to the widest type (Int32) so that all possible values fit.</span></span> <span data-ttu-id="4ad71-159">Vermeiden Sie außerdem die Zuordnung zu Typen, die nicht für viele Vorgänge verwendet werden können, wie z. b. BLOB-Typen (z. b. `ntext` in SQL Server).</span><span class="sxs-lookup"><span data-stu-id="4ad71-159">Also, avoid mapping to types that cannot be used for many operations, like BLOB types (for example, `ntext` in SQL Server).</span></span>

## <a name="see-also"></a><span data-ttu-id="4ad71-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ad71-160">See also</span></span>

- [<span data-ttu-id="4ad71-161">SQL-Generierung</span><span class="sxs-lookup"><span data-stu-id="4ad71-161">SQL Generation</span></span>](sql-generation.md)
