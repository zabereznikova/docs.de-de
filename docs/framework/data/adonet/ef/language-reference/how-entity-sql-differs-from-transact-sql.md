---
title: Unterschiede zwischen Entity SQL und Transact-SQL
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: 96e2283074b6c69e51bb7fee4d4f257cdb58d615
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615630"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a>Unterschiede zwischen Entity SQL und Transact-SQL

Dieser Artikel beschreibt die Unterschiede zwischen Entity SQL und Transact-SQL.  
  
## <a name="inheritance-and-relationships-support"></a>Unterstützung von Vererbung und Beziehungen  
 Entity SQL funktioniert direkt mit konzeptionellen Entitäts Schemas und unterstützt konzeptionelle Modell Funktionen wie Vererbung und Beziehungen.  
  
 Bei der Vererbung ist es häufig nützlich, Instanzen eines Untertyps aus einer Auflistung von Instanzen des Obertyps auszuwählen. Der [OfType](oftype-entity-sql.md) -Operator in Entity SQL (ähnlich wie `oftype` in c#-Sequenzen) bietet diese Funktion.  
  
## <a name="support-for-collections"></a>Unterstützung von Auflistungen  
 Entity SQL behandelt Auflistungen als erstklassige Entitäten. Beispiel:  
  
- In einer `from`-Klausel sind Auflistungsausdrücke gültig.  
  
- `in` und `exists`-Unterabfragen wurden so verallgemeinert, dass sämtliche Auflistungen zulässig sind.  
  
     Eine Unterabfrage ist eine Art von Auflistung. `e1 in e2`und `exists(e)` sind die Entity SQL-Konstrukte zum Ausführen dieser Vorgänge.  
  
- Mengenoperationen, z. B. `union`, `intersect` und `except`, verarbeiten nun Auflistungen.  
  
- Joins verarbeiten Auflistungen.  
  
## <a name="support-for-expressions"></a>Unterstützung von Ausdrücken  
 Transact-SQL enthält Unterabfragen (Tabellen) und Ausdrücke (Zeilen und Spalten).  
  
 Um Auflistungen und Auflistungen zu unterstützen, stellt Entity SQL alles als Ausdruck dar. Entity SQL ist Zusammensetz barer als Transact-SQL – jeder Ausdruck kann überall verwendet werden. Abfrageausdrücke geben stets Auflistungen der projizierten Typen zurück und können immer verwendet werden, wenn ein Auflistungsausdruck zulässig ist. Informationen zu Transact-SQL-Ausdrücken, die in Entity SQL nicht unterstützt werden, finden Sie unter [nicht unterstützte Ausdrücke](unsupported-expressions-entity-sql.md).  
  
 Im folgenden sind alle gültigen Entity SQL Abfragen aufgeführt:  
  
```sql  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a>Einheitliche Behandlung von Unterabfragen  
 Durch die Betonung von Tabellen führt Transact-SQL eine Kontext gesteuerte Interpretation von Unterabfragen durch. Beispielsweise wird eine Unterabfrage in der- `from` Klausel als Multimenge (Table) betrachtet. Dieselbe Unterabfrage in der `select`-Klausel wird hingegen als skalare Unterabfrage aufgefasst. Auf ähnliche Weise wird eine Unterabfrage, die auf der linken Seite eines Operators verwendet wird `in` , als skalare Unterabfrage betrachtet, während die Rechte Seite eine Multiset-Unterabfrage sein soll.  
  
 Entity SQL beseitigt diese Unterschiede. Ein Ausdruck verfügt über eine einheitliche vom Kontext unabhängige Auslegung. Entity SQL betrachtet alle Unterabfragen als multiset-Unterabfragen. Wenn ein Skalarwert aus der Unterabfrage gewünscht wird, stellt Entity SQL den Operator bereit, der `anyelement` eine Auflistung (in diesem Fall die Unterabfrage) bearbeitet und einen Singleton-Wert aus der Auflistung extrahiert.  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a>Vermeiden impliziter Koersionen für Unterabfragen  
 Ein Nebeneffekt der einheitlichen Behandlung von Unterabfragen ist die implizite Konvertierung von Unterabfragen zu skalaren Werten. Insbesondere in Transact-SQL wird eine Multimenge von Zeilen (mit einem einzelnen Feld) implizit in einen skalaren Wert konvertiert, dessen Datentyp dem des Felds entspricht.  
  
 Entity SQL unterstützt diese implizite Koersion nicht. Entity SQL stellt den `ANYELEMENT` -Operator bereit, um einen Singleton-Wert aus einer Auflistung zu extrahieren, und eine- `select value` Klausel, um zu vermeiden, dass während eines Abfrage Ausdrucks ein Zeilen Wrapper erstellt wird.  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a>Select Value: Vermeiden des impliziten Zeilen-Wrappers  
 Die SELECT-Klausel in einer Transact-SQL-Unterabfrage erstellt implizit einen Zeilen Wrapper um die Elemente in der-Klausel. Dies bedeutet, dass keine Auflistungen von Skalaren oder Objekten erstellt werden können. Transact-SQL lässt eine implizite Koersion zwischen einem `rowtype` -Wert und einem Singleton-Wert desselben Datentyps zu.  
  
 Entity SQL stellt die- `select value` Klausel bereit, um die implizite Zeilen Konstruktion zu überspringen. In einer `select value`-Klausel kann nur ein Element angegeben werden. Wenn eine solche Klausel verwendet wird, wird kein Zeilen Wrapper um die Elemente in der `select` -Klausel erstellt, und es kann eine Auflistung der gewünschten Form erstellt werden, z `select value a` . b..  
  
 Entity SQL bietet auch den Zeilenkonstruktor, um beliebige Zeilen zu erstellen. `select`nimmt ein oder mehrere Elemente in der Projektion an und führt zu einem Datensatz mit folgenden Feldern:  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a>Linkskorrelation und Aliasing  
 In Transact-SQL können Ausdrücke in einem bestimmten Bereich (eine einzelne Klausel wie `select` oder `from` ) nicht auf Ausdrücke verweisen, die zuvor im selben Bereich definiert wurden. Einige Dialekte von SQL (einschließlich Transact-SQL) unterstützen eingeschränkte Formen dieser in der- `from` Klausel.  
  
 Entity SQL verallgemeinert linke Korrelationen in der `from` -Klausel und behandelt diese gleichmäßig. Ausdrücke in der `from`-Klausel können ohne die Verwendung zusätzlicher Syntax auf vorherige Definitionen (Definitionen auf der linken Seite) in derselben Klausel verweisen.  
  
 Entity SQL setzt auch zusätzliche Einschränkungen für Abfragen ein, die `group by` Klauseln einschließen. Ausdrücke in der `select` -Klausel und- `having` Klausel dieser Abfragen können nur `group by` über ihre Aliase auf die Schlüssel verweisen. Das folgende Konstrukt ist in Transact-SQL gültig, aber nicht in Entity SQL:  
  
```sql  
SELECT t.x + t.y FROM T AS t group BY t.x + t.y
```  
  
 Gehen Sie dazu wie folgt Entity SQL vor:  
  
```sql  
SELET k FROM T AS t GROUP BY (t.x + t.y) AS k
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a>Verweisen auf Spalten (Eigenschaften) von Tabellen (Auflistungen)  
 Alle Spalten Verweise in Entity SQL müssen mit dem Tabellenalias qualifiziert werden. Das folgende Konstrukt (vorausgesetzt, dass `a` eine gültige Spalte der Tabelle ist `T` ) ist in Transact-SQL gültig, aber nicht in Entity SQL.  
  
```sql  
SELECT a FROM T
```  
  
 Das Entity SQL Formular ist  
  
```sql  
SELECT t.a AS A FROM T AS t
```  
  
 Die Tabellenaliase sind in der `from`-Klausel optional. Der Name der Tabelle wird als implizites Alias verwendet. Entity SQL lässt auch das folgende Formular zu:  
  
```sql  
SELET Tab.a FROM Tab
```  
  
## <a name="navigation-through-objects"></a>Navigieren durch Objekte  
 Transact-SQL verwendet die Notation "." zum Verweisen auf Spalten von (einer Zeile) einer Tabelle. Entity SQL erweitert diese Schreibweise (aus Programmiersprachen entnommen), um die Navigation durch Eigenschaften eines Objekts zu unterstützen.  
  
 Wenn z. b `p` . ein Ausdruck vom Typ "Person" ist, ist Folgendes die Entity SQL Syntax zum Verweisen auf die Stadt der Adresse dieser Person.  
  
```sql  
p.Address.City
```  
  
## <a name="no-support-for-"></a>Keine Unterstützung für\*  
 Transact-SQL unterstützt die nicht qualifizierte \* Syntax als Alias für die gesamte Zeile und die qualifizierte \* Syntax (t. \* ) als Verknüpfung für die Felder dieser Tabelle. Außerdem ermöglicht Transact-SQL ein spezielles count ( \* )-Aggregat, das NULL-Werten enthält.  
  
 Entity SQL unterstützt das *-Konstrukt nicht. Transact-SQL-Abfragen der Form `select * from T` und `select T1.* from T1, T2...` können in Entity SQL als `select value t from T as t` `select value t1 from T1 as t1, T2 as t2...` bzw. ausgedrückt werden. Außerdem behandeln diese Konstrukte Vererbung (Wertersetzbarkeit), während die `select *`-Varianten auf die Eigenschaften des deklarierten Typen auf oberster Ebene eingeschränkt sind.  
  
 Entity SQL unterstützt das `count(*)` Aggregat nicht. Verwenden Sie stattdessen `count(0)`.  
  
## <a name="changes-to-group-by"></a>Änderungen an "Group By"  
 Entity SQL unterstützt das Aliasing von `group by` Schlüsseln. Ausdrücke in der `select`-Klausel und der `having`-Klausel müssen mithilfe dieser Aliase auf die `group by`-Schlüssel verweisen. Dies Entity SQL z. b. die folgende Syntax:  
  
```sql  
SELECT k1, count(t.a), sum(t.a)
FROM T AS t
GROUP BY t.b + t.c AS k1
```  
  
 ... entspricht folgendem Transact-SQL:  
  
```sql  
SELECT b + c, count(*), sum(a)
FROM T
GROUP BY b + c
```  
  
## <a name="collection-based-aggregates"></a>Auflistungsbasierte Aggregate  
 Entity SQL unterstützt zwei Arten von Aggregaten.  
  
 Auflistungsbasierte Aggregate verarbeiten Auflistungen und erstellen das aggregierte Ergebnis. Sie können überall in der Abfrage stehen und erfordern keine `group by`-Klausel. Beispiel:  
  
```sql  
SELECT t.a AS a, count({1,2,3}) AS b FROM T AS t
```  
  
 Entity SQL unterstützt auch Aggregate im SQL-Stil. Beispiel:  
  
```sql  
SELECT a, sum(t.b) FROM T AS t GROUP BY t.a AS a
```  
  
## <a name="order-by-clause-usage"></a>Verwendung der "ORDER BY"-Klausel  
Transact-SQL lässt `ORDER BY` zu, dass Klauseln nur im obersten Block angegeben werden `SELECT .. FROM .. WHERE` . In Entity SQL können Sie einen eingefügten `ORDER BY` Ausdruck verwenden, der an einer beliebigen Stelle in der Abfrage platziert werden kann, aber die Reihenfolge in einer genetzten Abfrage wird nicht beibehalten.  
  
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
  
## <a name="identifiers"></a>Bezeichner  
 In Transact-SQL basiert der Bezeichnervergleich auf der Sortierung der aktuellen Datenbank. In Entity SQL wird bei bezeichnerbezeichnerzeichen immer nach Groß-und Kleinschreibung unterschieden (d. h., Entity SQL unterscheidet zwischen Zeichen mit Akzent und Zeichen ohne Akzent; beispielsweise ist "a" nicht gleich "ấ"). Entity SQL behandelt Versionen von Buchstaben, die identisch erscheinen, aber aus unterschiedlichen Codepages als verschiedene Zeichen stammen. Weitere Informationen finden Sie unter [Eingabe Zeichensatz](input-character-set-entity-sql.md).  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a>Transact-SQL-Funktionalität ist in Entity SQL nicht verfügbar  
 Die folgenden Transact-SQL-Funktionen sind in Entity SQL nicht verfügbar.  
  
 DML  
 Entity SQL bietet derzeit keine Unterstützung für DML-Anweisungen (INSERT, Update, DELETE).  
  
 DDL  
 Entity SQL bietet keine Unterstützung für DDL in der aktuellen Version.  
  
 Imperative Programmierung  
 Entity SQL bietet im Gegensatz zu Transact-SQL keine Unterstützung für Imperatives programmieren. Stattdessen sollte eine Programmiersprache verwendet werden.  
  
 Gruppierungsfunktionen  
 Entity SQL bietet noch keine Unterstützung für Gruppierungsfunktionen (z. b. Cube, Rollup und GROUPING_SET).  
  
 Analysefunktionen  
 Entity SQL bietet noch keine Unterstützung für analytische Funktionen.  
  
 Integrierte Funktionen, Operatoren  
 Entity SQL unterstützt eine Teilmenge der integrierten Transact-SQL-Funktionen und-Operatoren. Diese Operatoren und Funktionen werden sehr wahrscheinlich von den großen Speicheranbietern unterstützt. Entity SQL verwendet die Speicher spezifischen Funktionen, die in einem Anbieter Manifest deklariert sind. Darüber hinaus können Sie mit dem Entity Framework integrierte und benutzerdefinierte Speicherfunktionen deklarieren, die Entity SQL verwenden.  
  
 Hinweise  
 Entity SQL bietet keine Mechanismen für Abfrage Hinweise.  
  
 Batchabfrageergebnisse  
 Entity SQL unterstützt keine Batch Verarbeitung von Abfrage Ergebnissen. Folgendes ist z. b. ein gültiges Transact-SQL (als Batch gesendet):  
  
```sql  
SELECT * FROM products;
SELECT * FROM catagories;
```  
  
 Die entsprechende Entity SQL wird jedoch nicht unterstützt:  
  
```sql  
SELECT value p FROM Products AS p;
SELECT value c FROM Categories AS c;
```  
  
 Entity SQL unterstützt nur eine Abfrage Anweisung mit Ergebnis Generierung pro Befehl.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Entity SQL](entity-sql-overview.md)
- [Nicht unterstützte Ausdrücke](unsupported-expressions-entity-sql.md)
