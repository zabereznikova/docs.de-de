---
title: GROUP BY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cf4f4972-4724-4945-ba44-943a08549139
ms.openlocfilehash: 711fbdc2d51177037cf349150c3431de14b11974
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833778"
---
# <a name="group-by-entity-sql"></a>GROUP BY (Entity SQL)
Gibt Gruppen an, in denen von einem Abfrageausdruck ([SELECT](select-entity-sql.md)) zurückgegebene Objekte platziert werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
[ GROUP BY aliasedExpression [ ,...n ] ]  
```  
  
## <a name="arguments"></a>Argumente  
 `aliasedExpression`  
 Jeder gültige Abfrageausdruck, der gruppiert wird. `expression` kann eine Eigenschaft oder ein nicht aggregierter Ausdruck sein, der auf eine von der FROM-Klausel zurückgegebene Eigenschaft verweist. Die Auswertung jedes Ausdrucks in einer GROUP BY-Klausel muss einen Typ ergeben, der auf Gleichheit überprüft werden kann. Bei diesen Typen handelt es sich im Allgemeinen um skalare primitive Typen wie Zahlen, Zeichenfolgen und Datumsangaben. Nach einer Auflistung kann nicht gruppiert werden.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Aggregatfunktionen in der SELECT-Klausel enthalten sind \<Select List >, Group by berechnet einen Zusammenfassungs Wert für jede Gruppe. Wenn GROUP BY angegeben wird, muss jeder Eigenschaftsname jedes Nichtaggregatausdrucks in der Auswahlliste in der GROUP BY-Liste eingeschlossen sein, oder der GROUP BY-Ausdruck muss dem Auswahllistenausdruck genau entsprechen.  
  
> [!NOTE]
> Falls die ORDER BY-Klausel nicht angegeben wird, haben die von der GROUP BY-Klausel zurückgegebenen Gruppen keine feste Reihenfolge. Es wird empfohlen, dass Sie die ORDER BY-Klausel zum Angeben einer bestimmten Reihenfolge von Daten verwenden.  
  
 Wenn eine GROUP BY-Klausel angegeben wird, ob explizit oder implizit (beispielsweise aufgrund einer HAVING-Klausel in der Abfrage), wird der aktuelle Bereich versteckt und ein neuer Bereich eingeführt.  
  
 Die Klauseln SELECT, HAVING und ORDER BY können nicht mehr auf in der FROM-Klausel angegebene Elementnamen verweisen. Es kann nur auf die Gruppierungsausdrücke selbst verwiesen werden. Zu diesem Zweck können den Gruppierungsausdrücken neue Namen (Aliase) zugewiesen werden. Wenn für einen Gruppierungsausdruck kein Alias angegeben wird, versucht [!INCLUDE[esql](../../../../../../includes/esql-md.md)] einen solchen mithilfe der Regeln zur Aliaserstellung zu generieren. Das ist im folgenden Beispiel dargestellt.  
  
 `SELECT g1, g2, ...gn FROM c as c1`  
  
 `GROUP BY e1 as g1, e2 as g2, ...en as gn`  
  
 Ausdrücke in der GROUP BY-Klausel können nicht auf vorher in derselben GROUP BY-Klausel definierte Namen verweisen.  
  
 Zusätzlich zu Gruppierungsnamen können in den Klauseln SELECT, HAVING und ORDER BY auch Aggregate angegeben werden. Ein Aggregat enthält einen Ausdruck, der für jedes Element der Gruppe ausgewertet wird. Der Aggregatoperator führt die Werte aller dieser Ausdrücke zusammen (meist, aber nicht immer, in einen einzelnen Wert). Der Aggregatausdruck kann auf die im übergeordneten Bereich sichtbaren ursprünglichen Elementnamen oder auf die neuen, in der GROUP BY-Klausel selbst eingeführten Namen verweisen. Obwohl die Aggregate in den Klauseln SELECT, HAVING oder ORDER BY stehen, werden sie im selben Bereich wie die Gruppierungsausdrücke ausgewertet. Dies wird im folgenden Beispiel dargestellt.  
  
 `SELECT name, sum(o.Price * o.Quantity) as total`  
  
 `FROM orderLines as o`  
  
 `GROUP BY o.Product as name`  
  
 In dieser Abfrage wird die GROUP BY-Klausel verwendet, um einen nach Produkten aufgeschlüsselten Bericht der Kosten aller bestellten Produkte zu erstellen. Der Name `name` des Produkts wird als Teil des Gruppierungsausdrucks angegeben, und auf diesen Namen wird daraufhin in der SELECT-Liste verwiesen. Weiterhin wird das Aggregat `sum` in der SELECT-Liste angegeben, das intern auf den Preis und die Menge der Auftragsposition verweist.  
  
 Jeder GROUP BY-Schlüsselausdruck muss über mindestens einen Verweis auf den Eingabebereich verfügen:  
  
```sql  
SELECT FROM Persons as P  
GROUP BY Q + P   -- GOOD  
GROUP BY Q   -- BAD  
GROUP BY 1   -- BAD, a constant is not allowed  
```  
  
 Ein Beispiel für die Verwendung von GROUP BY finden Sie unter [HAVING](having-entity-sql.md).  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird der GROUP BY-Operator verwendet, um Gruppen anzugeben, in die Objekte von einer Abfrage zurückgegeben werden. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Befolgen Sie das Verfahren unter Gewusst [wie: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-sql[DP EntityServices Concepts#GROUPBY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#groupby)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Abfrageausdrücke](query-expressions-entity-sql.md)
