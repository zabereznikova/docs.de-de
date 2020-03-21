---
title: SELECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 9a33bd0d-ded1-41e7-ba3c-305502755e3b
ms.openlocfilehash: de6c497e7d781d705c68092e4a13ee07b727b2b7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149908"
---
# <a name="select-entity-sql"></a>SELECT (Entity SQL)
Gibt die von einer Abfrage zurückgegebenen Elemente an.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
SELECT [ ALL | DISTINCT ] [ topSubclause ] aliasedExpr
      [{ , aliasedExpr }] FROM fromClause [ WHERE whereClause ] [ GROUP BY groupByClause [ HAVING havingClause ] ] [ ORDER BY orderByClause ]  
-- or  
SELECT VALUE [ ALL | DISTINCT ] [ topSubclause ] expr FROM fromClause [ WHERE whereClause ] [ GROUP BY groupByClause [ HAVING havingClause ] ] [ ORDER BY orderByClause  
```  
  
## <a name="arguments"></a>Argumente  
 ALL  
 Gibt an, dass im Resultset Duplikate zulässig sind. ALL ist die Standardeinstellung.  
  
 DISTINCT  
 Gibt an, dass im Resultset nur eindeutige Ergebnisse zulässig sind.  
  
 VALUE  
 Ermöglicht die Angabe nur eines Elements, und fügt keinen Zeilen-Wrapper hinzu.  
  
 `topSubclause`  
 Jeder gültige Ausdruck von der Form `top(expr)`, der die Anzahl der von der Abfrage zurückzugebenden Ergebnisse angibt.  
  
 Mit dem Parameter LIMIT des [ORDER BY-Operators](order-by-entity-sql.md) können Sie auch die ersten n Elemente im Resultset auswählen.  
  
 `aliasedExpr`  
 Ein Ausdruck der Form:  
  
 `expr`als `identifier` &#124;`expr`  
  
 `expr`  
 Ein Literal oder ein Ausdruck.  
  
## <a name="remarks"></a>Bemerkungen  
 Die SELECT-Klausel wird ausgewertet, nachdem die [FROM-,](from-entity-sql.md) [GROUP BY-](group-by-entity-sql.md)und [HAVING-Klauseln](having-entity-sql.md) ausgewertet wurden. Die SELECT-Klausel kann sich nur auf aktuell im Bereich (der FROM-Klausel oder äußerer Bereiche) befindliche Elemente beziehen. Wenn eine GROUP BY-Klausel angegeben wurde, darf die SELECT-Klausel nur auf die Aliase der GROUP BY-Schlüssel verweisen. Verweise auf Elemente der FROM-Klausel sind nur in Aggregatfunktionen zulässig.  
  
 Die Liste von einem oder mehreren auf das SELECT-Schlüsselwort folgenden Abfrageausdrücken wird als Auswahlliste oder Projektion bezeichnet. Die allgemeinste Form der Projektion ist ein einzelner Abfrageausdruck. Durch Auswahl eines Members `member1` aus einer Auflistung `collection1`wird eine neue Auflistung aller Werte `member1` für jedes Objekt in `collection1`erstellt. Dies wird im folgenden Beispiel dargestellt.  
  
```sql  
SELECT collection1.member1 FROM collection1  
```  
  
 Wenn z. B. `customers` eine Auflistung vom Typ `Customer` ist, der über die Eigenschaft `Name` vom Typ `string`verfügt, wird durch die Auswahl von `Name` aus `customers` eine Auflistung von Zeichenfolgen erstellt. Dies wird im folgenden Beispiel dargestellt.  
  
```sql  
SELECT customers.Name FROM customers AS c  
```  
  
 Es kann auch JOIN-Syntax (FULL, INNER, LEFT, OUTER, ON und RIGHT) verwendet werden. ON ist für innere Verknüpfungen erforderlich und bei Cross Joins nicht zulässig.  
  
## <a name="row-and-value-select-clauses"></a>Zeilen- und Wertauswahlklauseln  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt zwei Varianten der SELECT-Klausel. Die erste Variante, die Zeilenauswahl, wird durch das Schlüsselwort SELECT identifiziert und kann verwendet werden, um einen oder mehrere Werte anzugeben, die projiziert werden sollen. Da ein Zeilenumwrapper implizit um die zurückgegebenen Werte hinzugefügt wird, ist das Ergebnis des Abfrageausdrucks immer ein Multiset von Zeilen.  
  
 In jedem Abfrageausdruck in einer Zeilenauswahl muss ein Alias angegeben werden. Wenn kein Alias angegeben wird, generiert[!INCLUDE[esql](../../../../../../includes/esql-md.md)] mithilfe der Aliasgenerierungsregeln einen Alias.  
  
 Die andere Variante der SELECT-Klausel, Wertauswahl, wird durch das SELECT VALUE-Schlüsselwort angegeben. Es ermöglicht die Angabe nur eines Werts, und fügt keinen Zeilen-Wrapper hinzu.  
  
 Eine Zeilenauswahl ist stets mithilfe von VALUE SELECT ausdrückbar. Dies wird im folgenden Beispiel illustriert.  
  
```sql  
SELECT 1 AS a, "abc" AS b FROM C  
SELECT VALUE ROW(1 AS a, "abc" AS b) FROM C
```  
  
## <a name="all-and-distinct-modifiers"></a>Die Modifizierer ALL und DISTINCT  
 Beide Varianten von SELECT in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ermöglichen die Angabe eines ALL-Modifizierers oder eines DISTINCT-Modifizierers. Wenn der DISTINCT-Modifizierer angegeben wird, werden Duplikate aus der vom Abfrageausdruck erstellten Auflistung entfernt (bis zur und einschließlich der SELECT-Klausel). Wenn der ALL-Modifizierer angegeben ist, werden Duplikate nicht entfernt. Dies ist die Standardeinstellung.  
  
## <a name="differences-from-transact-sql"></a>Unterschiede zu Transact-SQL  
 Im Gegensatz zu Transact-SQL unterstützt [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nicht die Verwendung des „*“-Arguments in der SELECT-Klausel.  Stattdessen ermöglicht [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in Abfragen das Herausprojizieren ganzer Datensätze durch Verweise auf die Auflistungsaliase der FROM-Klausel. Dies wird im folgenden Beispiel illustriert.  
  
```sql  
SELECT * FROM T1, T2  
```  
  
 Der vorherige Transact-SQL-Abfrageausdruck [!INCLUDE[esql](../../../../../../includes/esql-md.md)] wird wie folgt ausgedrückt.  
  
```sql  
SELECT a1, a2 FROM T1 AS a1, T2 AS a2  
```  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird der SELECT-Operator verwendet, um die von einer Abfrage zurückzugebenden Elemente anzugeben. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-sql[DP EntityServices Concepts#LESS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Abfrageausdrücke](query-expressions-entity-sql.md)
- [Entity SQL-Referenz](entity-sql-reference.md)
- [Nach oben](top-entity-sql.md)
