---
title: SELECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 9a33bd0d-ded1-41e7-ba3c-305502755e3b
ms.openlocfilehash: 93eea5d539e943c57ed7c6236caa854486ac238e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505108"
---
# <a name="select-entity-sql"></a>SELECT (Entity SQL)
Gibt die von einer Abfrage zurückgegebenen Elemente an.  
  
## <a name="syntax"></a>Syntax  
  
```  
SELECT [ ALL | DISTINCT ] [ topSubclause ] aliasedExpr   
      [{ , aliasedExpr }] FROM fromClause [ WHERE whereClause ] [ GROUP BY groupByClause [ HAVING havingClause ] ] [ ORDER BY orderByClause ]  
or  
SELECT VALUE [ ALL | DISTINCT ] [ topSubclause ] expr FROM fromClause [ WHERE whereClause ] [ GROUP BY groupByClause [ HAVING havingClause ] ] [ ORDER BY orderByClause  
```  
  
## <a name="arguments"></a>Argumente  
 ALL  
 Gibt an, dass im Resultset Duplikate zulässig sind. ALL ist der Standardwert.  
  
 DISTINCT  
 Gibt an, dass im Resultset nur eindeutige Ergebnisse zulässig sind.  
  
 VALUE  
 Ermöglicht die Angabe nur eines Elements, und fügt keinen Zeilen-Wrapper hinzu.  
  
 `topSubclause`  
 Jeder gültige Ausdruck, der die Anzahl der von der Form der Abfrage zurückzugebenden Ergebnisse angibt `top(expr)`.  
  
 Die LIMIT-Parameter, der die [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) -Operators können ebenfalls die ersten n Elemente im Resultset zu wählen.  
  
 `aliasedExpr`  
 Ein Ausdruck der Form:  
  
 `expr` als `identifier`&#124; `expr`  
  
 `expr`  
 Ein Literal oder ein Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Die SELECT-Klausel wird ausgewertet, nachdem die [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), und [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md) Klauseln ausgewertet wurden. Die SELECT-Klausel kann sich nur auf aktuell im Bereich (der FROM-Klausel oder äußerer Bereiche) befindliche Elemente beziehen. Wenn eine GROUP BY-Klausel angegeben wurde, darf die SELECT-Klausel nur auf die Aliase der GROUP BY-Schlüssel verweisen. Verweise auf Elemente der FROM-Klausel sind nur in Aggregatfunktionen zulässig.  
  
 Die Liste von einem oder mehreren auf das SELECT-Schlüsselwort folgenden Abfrageausdrücken wird als Auswahlliste oder Projektion bezeichnet. Die allgemeinste Form der Projektion ist ein einzelner Abfrageausdruck. Durch Auswahl eines Members `member1` aus einer Auflistung `collection1`wird eine neue Auflistung aller Werte `member1` für jedes Objekt in `collection1`erstellt. Dies wird im folgenden Beispiel dargestellt.  
  
```  
SELECT collection1.member1 FROM collection1  
```  
  
 Wenn z. B. `customers` eine Auflistung vom Typ `Customer` ist, der über die Eigenschaft `Name` vom Typ `string`verfügt, wird durch die Auswahl von `Name` aus `customers` eine Auflistung von Zeichenfolgen erstellt. Dies wird im folgenden Beispiel dargestellt.  
  
```  
SELECT customers.Name FROM customers AS c  
```  
  
 Es kann auch JOIN-Syntax (FULL, INNER, LEFT, OUTER, ON und RIGHT) verwendet werden. ON ist für innere Verknüpfungen erforderlich und bei Cross Joins nicht zulässig.  
  
## <a name="row-and-value-select-clauses"></a>Zeilen- und Wertauswahlklauseln  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt zwei Varianten der SELECT-Klausel. Die erste Variante, Zeilenauswahl, wird durch das SELECT-Schlüsselwort angegeben und kann zur Angabe von einem oder mehreren Werten verwendet werden, die herausprojiziert werden sollen. Da die zurückgegebenen Werte implizit mit einem Zeilen-Wrapper umschlossen werden, ist das Ergebnis des Abfrageausdrucks stets ein Multiset von Zeilen.  
  
 In jedem Abfrageausdruck in einer Zeilenauswahl muss ein Alias angegeben werden. Wenn kein Alias angegeben wird, generiert[!INCLUDE[esql](../../../../../../includes/esql-md.md)] mithilfe der Aliasgenerierungsregeln einen Alias.  
  
 Die andere Variante der SELECT-Klausel, Wertauswahl, wird durch das SELECT VALUE-Schlüsselwort angegeben. Es ermöglicht die Angabe nur eines Werts, und fügt keinen Zeilen-Wrapper hinzu.  
  
 Eine Zeilenauswahl ist stets mithilfe von VALUE SELECT ausdrückbar. Dies wird im folgenden Beispiel illustriert.  
  
```  
SELECT 1 AS a, "abc" AS b FROM C  
SELECT VALUE ROW(1 AS a, "abc" AS b) FROM C   
```  
  
## <a name="all-and-distinct-modifiers"></a>Die Modifizierer ALL und DISTINCT  
 Beide Varianten von SELECT in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ermöglichen die Angabe eines ALL-Modifizierers oder eines DISTINCT-Modifizierers. Wenn der DISTINCT-Modifizierer angegeben wird, werden Duplikate aus der vom Abfrageausdruck erstellten Auflistung entfernt (bis zur und einschließlich der SELECT-Klausel). Wenn der ALL-Modifizierer angegeben ist, werden Duplikate nicht entfernt. Dies ist die Standardeinstellung.  
  
## <a name="differences-from-transact-sql"></a>Unterschiede zu Transact-SQL  
 Im Gegensatz zu Transact-SQL unterstützt [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nicht die Verwendung des „*“-Arguments in der SELECT-Klausel.  Stattdessen ermöglicht [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in Abfragen das Herausprojizieren ganzer Datensätze durch Verweise auf die Auflistungsaliase der FROM-Klausel. Dies wird im folgenden Beispiel illustriert.  
  
```  
SELECT * FROM T1, T2  
```  
  
 Der vorherige [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] -Abfrageausdruck wird in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] wie folgt ausgedrückt.  
  
```  
SELECT a1, a2 FROM T1 AS a1, T2 AS a2  
```  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird der SELECT-Operator verwendet, um die von einer Abfrage zurückzugebenden Elemente anzugeben. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less)]  
  
## <a name="see-also"></a>Siehe auch  
 [Abfrageausdrücke](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
