---
title: Unterschiede zwischen Entity SQL und Transact-SQL
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: e0af0a415d812337d6abf449e9ee170526c3df0c
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833720"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a>Unterschiede zwischen Entity SQL und Transact-SQL
In diesem Thema werden die unter [!INCLUDE[esql](../../../../../../includes/esql-md.md)] schiede zwischen und Transact-SQL beschrieben.  
  
## <a name="inheritance-and-relationships-support"></a>Unterstützung von Vererbung und Beziehungen  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]arbeitet direkt mit konzeptionellen Entitäts Schemas und unterstützt konzeptionelle Modell Funktionen wie Vererbung und Beziehungen.  
  
 Bei der Vererbung ist es häufig nützlich, Instanzen eines Untertyps aus einer Auflistung von Instanzen des Obertyps auszuwählen. Diese Funktion wird vom [OfType](oftype-entity-sql.md) -Operator [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in C# (ähnlich wie `oftype` in Sequenzen) bereitstellt.  
  
## <a name="support-for-collections"></a>Unterstützung von Auflistungen  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]behandelt Auflistungen als erstklassige Entitäten. Zum Beispiel:  
  
- In einer `from`-Klausel sind Auflistungsausdrücke gültig.  
  
- `in` und `exists`-Unterabfragen wurden so verallgemeinert, dass sämtliche Auflistungen zulässig sind.  
  
     Eine Unterabfrage ist eine Art von Auflistung. `e1 in e2` und `exists(e)` sind die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Konstrukte zum Ausführen dieser Operationen.  
  
- Mengenoperationen, z. B. `union`, `intersect` und `except`, verarbeiten nun Auflistungen.  
  
- Joins verarbeiten Auflistungen.  
  
## <a name="support-for-expressions"></a>Unterstützung von Ausdrücken  
 Transact-SQL enthält Unterabfragen (Tabellen) und Ausdrücke (Zeilen und Spalten).  
  
 Um Auflistungen und Auflistungen [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zu unterstützen, macht alles einen Ausdruck. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]ist Zusammensetz barer als Transact-SQL – jeder Ausdruck kann überall verwendet werden. Abfrageausdrücke geben stets Auflistungen der projizierten Typen zurück und können immer verwendet werden, wenn ein Auflistungsausdruck zulässig ist. Informationen zu Transact-SQL-Ausdrücken, die in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]nicht unterstützt werden, finden Sie unter [nicht unterstützte Ausdrücke](unsupported-expressions-entity-sql.md).  
  
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
 Durch die Betonung von Tabellen führt Transact-SQL eine Kontext gesteuerte Interpretation von Unterabfragen durch. Beispielsweise wird eine Unterabfrage in der `from` -Klausel als Multimenge (Table) betrachtet. Dieselbe Unterabfrage in der `select`-Klausel wird hingegen als skalare Unterabfrage aufgefasst. Auf ähnliche Weise wird eine Unterabfrage, die auf der linken `in` Seite eines Operators verwendet wird, als skalare Unterabfrage betrachtet, während die Rechte Seite eine Multiset-Unterabfrage sein soll.  
  
 In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] existieren diese Unterschiede nicht. Ein Ausdruck verfügt über eine einheitliche vom Kontext unabhängige Auslegung. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]betrachtet alle Unterabfragen als multiset-Unterabfragen. Wenn ein Skalarwert aus der Unterabfrage gewünscht wird, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt den `anyelement` Operator bereit, der für eine Auflistung (in diesem Fall die Unterabfrage) arbeitet, und extrahiert einen Singleton-Wert aus der Auflistung.  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a>Vermeiden impliziter Koersionen für Unterabfragen  
 Ein Nebeneffekt der einheitlichen Behandlung von Unterabfragen ist die implizite Konvertierung von Unterabfragen zu skalaren Werten. Insbesondere in Transact-SQL wird eine Multimenge von Zeilen (mit einem einzelnen Feld) implizit in einen skalaren Wert konvertiert, dessen Datentyp dem des Felds entspricht.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt diese implizite Umwandlung nicht. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt den ANYELEMENT-Operator zum Extrahieren eines Singleton-Werts aus einer Auflistung bereit sowie eine `select value`-Klausel zur Vermeidung der Erstellung eines Zeilen-Wrappers während eines Abfrageausdrucks.  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a>Wert auswählen: Vermeiden des impliziten Zeilen Wrappers  
 Die SELECT-Klausel in einer Transact-SQL-Unterabfrage erstellt implizit einen Zeilen Wrapper um die Elemente in der-Klausel. Dies bedeutet, dass keine Auflistungen von Skalaren oder Objekten erstellt werden können. Transact-SQL lässt eine implizite Koersion zwischen einem RowType mit einem Feld und einem Singleton-Wert desselben Datentyps zu.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt die `select value`-Klausel bereit, um die implizite Zeilenkonstruktion unnötig zu machen. In einer `select value`-Klausel kann nur ein Element angegeben werden. Wenn diese Klausel verwendet wird, wird kein Zeilen-Wrapper für die Elemente in der `select`-Klausel erstellt, und eine Auflistung der gewünschten Form kann erstellt werden. Beispiel: `select value a`.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt auch den Zeilenkonstruktor zum Erstellen beliebiger Zeilen bereit. Mit `select` werden ein oder mehrere Elemente in der Projektion übergeben, und das Ergebnis ist ein Datensatz mit folgenden Feldern:  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a>Linkskorrelation und Aliasing  
 In Transact-SQL können Ausdrücke in einem bestimmten Bereich (eine einzelne Klausel wie `select` oder `from`) nicht auf Ausdrücke verweisen, die zuvor im selben Bereich definiert wurden. Einige Dialekte von SQL (einschließlich Transact-SQL) unterstützen eingeschränkte Formen dieser in der `from` -Klausel.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]generalisiert linke Korrelationen in `from` der-Klausel und behandelt diese gleichmäßig. Ausdrücke in der `from`-Klausel können ohne die Verwendung zusätzlicher Syntax auf vorherige Definitionen (Definitionen auf der linken Seite) in derselben Klausel verweisen.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] schränkt auch Abfragen, die `group by`-Klauseln enthalten, weiter ein. Ausdrücke in der `select` -Klausel `having` und-Klausel dieser Abfragen können nur über Ihre `group by` Aliase auf die Schlüssel verweisen. Das folgende Konstrukt ist in Transact-SQL gültig, aber nicht in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:  
  
```sql  
SELECT t.x + t.y FROM T AS t group BY t.x + t.y
```  
  
 In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist Folgendes zu verwenden:  
  
```sql  
SELET k FROM T AS t GROUP BY (t.x + t.y) AS k
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a>Verweisen auf Spalten (Eigenschaften) von Tabellen (Auflistungen)  
 Alle Spaltenverweise in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] müssen mit dem Tabellenalias qualifiziert werden. Das folgende Konstrukt (vorausgesetzt `a` , dass eine gültige Spalte der `T`Tabelle ist) ist in Transact-SQL gültig, [!INCLUDE[esql](../../../../../../includes/esql-md.md)]aber nicht in.  
  
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
 Transact-SQL verwendet die Notation "." zum Verweisen auf Spalten von (einer Zeile) einer Tabelle. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] erweitert diese Schreibweise (wie Programmiersprachen), um die Navigation durch Eigenschaften eines Objekts zu unterstützen.  
  
 Wenn z. B. `p` ein Ausdruck vom Typ "Person" ist, lautet die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Syntax zum Verweisen auf die Stadt und die Adresse dieser Person wie folgt.  
  
```sql  
p.Address.City   
```  
  
## <a name="no-support-for-"></a>Keine Unterstützung von *  
 Transact-SQL unterstützt die nicht qualifizierte *-Syntax als Alias für die gesamte Zeile und die \* qualifizierte Syntax (t\*.) als Verknüpfung für die Felder dieser Tabelle. Außerdem ermöglicht Transact-SQL ein spezielles count (\*)-Aggregat, das NULL-Werten enthält.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt nicht das *-Konstrukt. Transact-SQL-Abfragen der Form `select * from T` und `select T1.* from T1, T2...` können in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] als `select value t from T as t` `select value t1 from T1 as t1, T2 as t2...`bzw. ausgedrückt werden. Außerdem behandeln diese Konstrukte Vererbung (Wertersetzbarkeit), während die `select *`-Varianten auf die Eigenschaften des deklarierten Typen auf oberster Ebene eingeschränkt sind.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt nicht die `count(*)`-Aggregate. Verwenden Sie stattdessen `count(0)`.  
  
## <a name="changes-to-group-by"></a>Änderungen an "Group By"  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt Aliasing von `group by`-Schlüsseln. Ausdrücke in der `select`-Klausel und der `having`-Klausel müssen mithilfe dieser Aliase auf die `group by`-Schlüssel verweisen. Beispielsweise ist die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Syntax  
  
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
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt zwei Arten von Aggregaten.  
  
 Auflistungsbasierte Aggregate verarbeiten Auflistungen und erstellen das aggregierte Ergebnis. Sie können überall in der Abfrage stehen und erfordern keine `group by`-Klausel. Zum Beispiel:  
  
```sql  
SELECT t.a AS a, count({1,2,3}) AS b FROM T AS t
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt auch Aggregate im SQL-Format. Zum Beispiel:  
  
```sql  
SELECT a, sum(t.b) FROM T AS t GROUP BY t.a AS a
```  
  
## <a name="order-by-clause-usage"></a>Verwendung der "ORDER BY"-Klausel  
Transact-SQL ermöglicht, dass `ORDER BY`-Klauseln nur im obersten `SELECT .. FROM .. WHERE`-Block angegeben werden. In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] können Sie einen `ORDER BY`-Ausdruck verwenden, der an beliebiger Stelle in der Abfrage platziert werden kann, aber die Reihenfolge in einer genetzten Abfrage wird nicht beibehalten.  
  
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
 In Transact-SQL basiert der Bezeichnervergleich auf der Sortierung der aktuellen Datenbank. In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] wird bei Bezeichnern nicht zwischen Groß-/Kleinschreibung unterschieden, Akzentzeichen werden dagegen von den keinen Akzent tragenden Zeichen unterschieden ([!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterscheidet also beispielsweise zwischen 'a' und 'ấ'). [!INCLUDE[esql](../../../../../../includes/esql-md.md)] behandelt Buchstaben, die gleich erscheinen, aber von anderen Codepages stammen. Weitere Informationen finden Sie unter [Eingabe Zeichensatz](input-character-set-entity-sql.md).  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a>Transact-SQL-Funktionalität ist in Entity SQL nicht verfügbar  
 Die folgenden Transact-SQL-Funktionen sind in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]nicht verfügbar.  
  
 DML  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]bietet derzeit keine Unterstützung für DML-Anweisungen (INSERT, Update, DELETE).  
  
 DDL  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt in der aktuellen Version keine Unterstützung für DDL bereit.  
  
 Imperative Programmierung  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]bietet im Gegensatz zu Transact-SQL keine Unterstützung für Imperatives programmieren. Stattdessen sollte eine Programmiersprache verwendet werden.  
  
 Gruppierungsfunktionen  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt bisher keine Gruppierungsfunktionen wie CUBE, ROLLUP und GROUPING_SET.  
  
 Analytische Funktionen  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt (bisher) keine analytischen Funktionen.  
  
 Integrierte Funktionen, Operatoren  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]unterstützt eine Teilmenge der integrierten Transact-SQL-Funktionen und-Operatoren. Diese Operatoren und Funktionen werden sehr wahrscheinlich von den großen Speicheranbietern unterstützt. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]verwendet die Speicher spezifischen Funktionen, die in einem Anbieter Manifest deklariert sind. Darüber hinaus können Sie mit dem Entity Framework integrierte und benutzerdefinierte Speicherfunktionen deklarieren, die verwendet werden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sollen.  
  
 Hinweise  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt keine Mechanismen für Abfragehinweise bereit.  
  
 Batchabfrageergebnisse  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt keine Batchabfrageergebnisse. Folgendes ist z. b. ein gültiges Transact-SQL (als Batch gesendet):  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Entity SQL](entity-sql-overview.md)
- [Nicht unterstützte Ausdrücke](unsupported-expressions-entity-sql.md)
