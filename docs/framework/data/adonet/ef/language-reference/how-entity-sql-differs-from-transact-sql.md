---
title: Unterschiede zwischen Entity SQL und Transact-SQL
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: 299cb9bbe90c72619cf809a8fc673fca456bd6fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150230"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a>Unterschiede zwischen Entity SQL und Transact-SQL
In diesem Thema [!INCLUDE[esql](../../../../../../includes/esql-md.md)] werden die Unterschiede zwischen und Transact-SQL beschrieben.  
  
## <a name="inheritance-and-relationships-support"></a>Unterstützung von Vererbung und Beziehungen  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]arbeitet direkt mit konzeptionellen Entitätsschemas und unterstützt konzeptionelle Modellfeatures wie Vererbung und Beziehungen.  
  
 Bei der Vererbung ist es häufig nützlich, Instanzen eines Untertyps aus einer Auflistung von Instanzen des Obertyps auszuwählen. Der [oftype-Operator](oftype-entity-sql.md) [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in `oftype` (ähnlich wie in C-Sequenzen) stellt diese Funktion bereit.  
  
## <a name="support-for-collections"></a>Unterstützung von Auflistungen  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]behandelt Auflistungen als erstklassige Entitäten. Beispiel:  
  
- In einer `from`-Klausel sind Auflistungsausdrücke gültig.  
  
- `in` und `exists`-Unterabfragen wurden so verallgemeinert, dass sämtliche Auflistungen zulässig sind.  
  
     Eine Unterabfrage ist eine Art von Auflistung. `e1 in e2` und `exists(e)` sind die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Konstrukte zum Ausführen dieser Operationen.  
  
- Mengenoperationen, z. B. `union`, `intersect` und `except`, verarbeiten nun Auflistungen.  
  
- Joins verarbeiten Auflistungen.  
  
## <a name="support-for-expressions"></a>Unterstützung von Ausdrücken  
 Transact-SQL verfügt über Unterabfragen (Tabellen) und Ausdrücke (Zeilen und Spalten).  
  
 Um Auflistungen und verschachtelte Auflistungen zu unterstützen, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] wird alles zum Ausdruck. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]ist komposierbarer als Transact-SQL – jeder Ausdruck kann überall verwendet werden. Abfrageausdrücke geben stets Auflistungen der projizierten Typen zurück und können immer verwendet werden, wenn ein Auflistungsausdruck zulässig ist. Informationen zu Transact-SQL-Ausdrücken, [!INCLUDE[esql](../../../../../../includes/esql-md.md)]die in nicht unterstützt werden, finden Sie unter [Nicht unterstützte Ausdrücke](unsupported-expressions-entity-sql.md).  
  
 Bei den folgenden Abfragen handelt es sich um gültige [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Abfragen:  
  
```sql  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a>Einheitliche Behandlung von Unterabfragen  
 Aufgrund der Betonung von Tabellen führt Transact-SQL eine kontextbezogene Interpretation von Unterabfragen durch. Beispielsweise wird eine Unterabfrage `from` in der Klausel als Multiset (Tabelle) betrachtet. Dieselbe Unterabfrage in der `select`-Klausel wird hingegen als skalare Unterabfrage aufgefasst. In ähnlicher Weise wird eine Unterabfrage, die auf der linken Seite eines `in` Operators verwendet wird, als skalare Unterabfrage betrachtet, während die rechte Seite voraussichtlich eine Unterabfrage mit mehreren Mengen ist.  
  
 In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] existieren diese Unterschiede nicht. Ein Ausdruck verfügt über eine einheitliche vom Kontext unabhängige Auslegung. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]betrachtet alle Unterabfragen als Multiset-Unterabfragen. Wenn ein Skalarwert aus der Unterabfrage gewünscht wird, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt der Operator bereit, der `anyelement` für eine Auflistung (in diesem Fall die Unterabfrage) arbeitet, und extrahiert einen Singleton-Wert aus der Auflistung.  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a>Vermeiden impliziter Koersionen für Unterabfragen  
 Ein Nebeneffekt der einheitlichen Behandlung von Unterabfragen ist die implizite Konvertierung von Unterabfragen zu skalaren Werten. Insbesondere wird in Transact-SQL ein Multisatz von Zeilen (mit einem einzelnen Feld) implizit in einen Skalarwert konvertiert, dessen Datentyp der des Felds ist.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt diese implizite Umwandlung nicht. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt den ANYELEMENT-Operator zum Extrahieren eines Singleton-Werts aus einer Auflistung bereit sowie eine `select value`-Klausel zur Vermeidung der Erstellung eines Zeilen-Wrappers während eines Abfrageausdrucks.  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a>Select Value: Vermeiden des impliziten Zeilen-Wrappers  
 Die select-Klausel in einer Transact-SQL-Unterabfrage erstellt implizit einen Zeilenumschlag um die Elemente in der Klausel. Dies bedeutet, dass keine Auflistungen von Skalaren oder Objekten erstellt werden können. Transact-SQL ermöglicht einen impliziten Zwang zwischen einem Zeilentyp mit einem Feld und einem Singleton-Wert desselben Datentyps.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt die `select value`-Klausel bereit, um die implizite Zeilenkonstruktion unnötig zu machen. In einer `select value`-Klausel kann nur ein Element angegeben werden. Wenn diese Klausel verwendet wird, wird kein Zeilen-Wrapper für die Elemente in der `select`-Klausel erstellt, und eine Auflistung der gewünschten Form kann erstellt werden. Beispiel: `select value a`.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt auch den Zeilenkonstruktor zum Erstellen beliebiger Zeilen bereit. Mit `select` werden ein oder mehrere Elemente in der Projektion übergeben, und das Ergebnis ist ein Datensatz mit folgenden Feldern:  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a>Linkskorrelation und Aliasing  
 In Transact-SQL können Ausdrücke in einem `select` bestimmten `from`Bereich (eine einzelne Klausel wie oder ) nicht auf ausdrücken verweisen, die zuvor im gleichen Bereich definiert wurden. Einige Dialekte von SQL (einschließlich Transact-SQL) unterstützen `from` begrenzte Formen dieser In-Zeichen in der Klausel.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]verallgemeinert linke Korrelationen `from` in der Klausel und behandelt sie einheitlich. Ausdrücke in der `from`-Klausel können ohne die Verwendung zusätzlicher Syntax auf vorherige Definitionen (Definitionen auf der linken Seite) in derselben Klausel verweisen.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] schränkt auch Abfragen, die `group by`-Klauseln enthalten, weiter ein. Ausdrücke `select` in `having` der Klausel und Klausel solcher `group by` Abfragen dürfen nur über ihre Aliase auf die Schlüssel verweisen. Das folgende Konstrukt ist in Transact-SQL [!INCLUDE[esql](../../../../../../includes/esql-md.md)]gültig, jedoch nicht in:  
  
```sql  
SELECT t.x + t.y FROM T AS t group BY t.x + t.y
```  
  
 In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist Folgendes zu verwenden:  
  
```sql  
SELET k FROM T AS t GROUP BY (t.x + t.y) AS k
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a>Verweisen auf Spalten (Eigenschaften) von Tabellen (Auflistungen)  
 Alle Spaltenverweise in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] müssen mit dem Tabellenalias qualifiziert werden. Das folgende Konstrukt `a` (vorausgesetzt, es `T`handelt sich um eine gültige Spalte [!INCLUDE[esql](../../../../../../includes/esql-md.md)]der Tabelle ) ist in Transact-SQL gültig, jedoch nicht in .  
  
```sql  
SELECT a FROM T
```  
  
 Die Form für [!INCLUDE[esql](../../../../../../includes/esql-md.md)] lautet  
  
```sql  
SELECT t.a AS A FROM T AS t
```  
  
 Die Tabellenaliase sind in der `from`-Klausel optional. Der Name der Tabelle wird als implizites Alias verwendet. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] lässt auch das folgende Formular zu:  
  
```sql  
SELET Tab.a FROM Tab
```  
  
## <a name="navigation-through-objects"></a>Navigieren durch Objekte  
 Transact-SQL verwendet die "."-Notation zum Verweisen auf Spalten (einer Zeile) einer Tabelle. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] erweitert diese Schreibweise (wie Programmiersprachen), um die Navigation durch Eigenschaften eines Objekts zu unterstützen.  
  
 Wenn z. B. `p` ein Ausdruck vom Typ "Person" ist, lautet die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Syntax zum Verweisen auf die Stadt und die Adresse dieser Person wie folgt.  
  
```sql  
p.Address.City
```  
  
## <a name="no-support-for-"></a>Keine Unterstützung von *  
 Transact-SQL unterstützt die unqualifizierte * Syntax als Alias für \* die gesamte\*Zeile und die qualifizierte Syntax (t. ) als Verknüpfung für die Felder dieser Tabelle. Darüber hinaus ermöglicht Transact-SQL ein\*spezielles Count( -Aggregat, das nulls enthält.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt nicht das *-Konstrukt. Transact-SQL-Abfragen des `select * from T` `select T1.* from T1, T2...` Formulars und [!INCLUDE[esql](../../../../../../includes/esql-md.md)] `select value t from T as t` können `select value t1 from T1 as t1, T2 as t2...`in bzw. als , ausgedrückt werden. Außerdem behandeln diese Konstrukte Vererbung (Wertersetzbarkeit), während die `select *`-Varianten auf die Eigenschaften des deklarierten Typen auf oberster Ebene eingeschränkt sind.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt nicht die `count(*)`-Aggregate. Verwenden Sie stattdessen `count(0)`.  
  
## <a name="changes-to-group-by"></a>Änderungen an "Group By"  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt Aliasing von `group by`-Schlüsseln. Ausdrücke in der `select`-Klausel und der `having`-Klausel müssen mithilfe dieser Aliase auf die `group by`-Schlüssel verweisen. Beispielsweise ist die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Syntax  
  
```sql  
SELECT k1, count(t.a), sum(t.a)
FROM T AS t
GROUP BY t.b + t.c AS k1
```  
  
 ... entspricht dem folgenden Transact-SQL:  
  
```sql  
SELECT b + c, count(*), sum(a)
FROM T
GROUP BY b + c
```  
  
## <a name="collection-based-aggregates"></a>Auflistungsbasierte Aggregate  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt zwei Arten von Aggregaten.  
  
 Auflistungsbasierte Aggregate verarbeiten Auflistungen und erstellen das aggregierte Ergebnis. Sie können überall in der Abfrage stehen und erfordern keine `group by`-Klausel. Beispiel:  
  
```sql  
SELECT t.a AS a, count({1,2,3}) AS b FROM T AS t
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt auch Aggregate im SQL-Format. Beispiel:  
  
```sql  
SELECT a, sum(t.b) FROM T AS t GROUP BY t.a AS a
```  
  
## <a name="order-by-clause-usage"></a>Verwendung der "ORDER BY"-Klausel  
Transact-SQL `ORDER BY` ermöglicht die Angabe von Klauseln `SELECT .. FROM .. WHERE` nur im obersten Block. In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] können Sie einen `ORDER BY` geschachtelten Ausdruck verwenden, der an einer beliebigen Stelle in der Abfrage platziert werden kann, aber die Reihenfolge in einer geschachtelten Abfrage wird nicht beibehalten.  
  
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
 In Transact-SQL basiert der Bezeichnervergleich auf der Sortierung der aktuellen Datenbank. In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] wird bei Bezeichnern nicht zwischen Groß-/Kleinschreibung unterschieden, Akzentzeichen werden dagegen von den keinen Akzent tragenden Zeichen unterschieden ([!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterscheidet also beispielsweise zwischen 'a' und 'ấ'). [!INCLUDE[esql](../../../../../../includes/esql-md.md)] behandelt Buchstaben, die gleich erscheinen, aber von anderen Codepages stammen. Weitere Informationen finden Sie unter [Eingabezeichensatz](input-character-set-entity-sql.md).  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a>Transact-SQL-Funktionalität ist in Entity SQL nicht verfügbar  
 Die folgende Transact-SQL-Funktionalität [!INCLUDE[esql](../../../../../../includes/esql-md.md)]ist in nicht verfügbar.  
  
 DML  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]bietet derzeit keine Unterstützung für DML-Anweisungen (Einfügen, Aktualisieren, Löschen).  
  
 DDL  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt in der aktuellen Version keine Unterstützung für DDL bereit.  
  
 Imperative Programmierung  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]bietet keine Unterstützung für imperative Programmierung, im Gegensatz zu Transact-SQL. Stattdessen sollte eine Programmiersprache verwendet werden.  
  
 Gruppierungsfunktionen  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt bisher keine Gruppierungsfunktionen wie CUBE, ROLLUP und GROUPING_SET.  
  
 Analysefunktionen  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt (bisher) keine analytischen Funktionen.  
  
 Integrierte Funktionen, Operatoren  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]unterstützt eine Teilmenge der integrierten Funktionen und Operatoren von Transact-SQL. Diese Operatoren und Funktionen werden sehr wahrscheinlich von den großen Speicheranbietern unterstützt. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]verwendet die speicherspezifischen Funktionen, die in einem Anbietermanifest deklariert sind. Darüber hinaus können Sie mit Entity Framework integrierte und benutzerdefinierte [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vorhandene Speicherfunktionen für die Verwendung deklarieren.  
  
 Hinweise  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt keine Mechanismen für Abfragehinweise bereit.  
  
 Batchabfrageergebnisse  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt keine Batchabfrageergebnisse. Das folgende ist z. B. gültig Transact-SQL (als Batch senden):  
  
```sql  
SELECT * FROM products;
SELECT * FROM catagories;
```  
  
 Die äquivalente Anweisung wird in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] jedoch nicht unterstützt:  
  
```sql  
SELECT value p FROM Products AS p;
SELECT value c FROM Categories AS c;
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt nur eine Ergebnisse liefernde Abfrageanweisung pro Befehl.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Entity SQL](entity-sql-overview.md)
- [Nicht unterstützte Ausdrücke](unsupported-expressions-entity-sql.md)
