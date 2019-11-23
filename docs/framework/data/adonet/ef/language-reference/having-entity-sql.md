---
title: HAVING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
ms.openlocfilehash: 97ed6e06241804bf2f576c910a2235b0cb570bbb
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833729"
---
# <a name="having-entity-sql"></a>HAVING (Entity SQL)
Gibt eine Suchbedingung für eine Gruppe oder ein Aggregat an.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a>Argumente  
 `search_condition`  
 Gibt die Suchbedingung für die zu erfüllende Gruppe oder das Aggregat an. Wenn HAVING mit GROUP BY ALL verwendet wird, setzt die HAVING-Klausel ALL außer Kraft.  
  
## <a name="remarks"></a>Hinweise  
 Mit der HAVING-Klausel kann für das Ergebnis einer Gruppierung eine zusätzliche Filterbedingung angegeben werden. Wenn Sie im Abfrageausdruck keine GROUP BY-Klausel angeben, wird eine implizite einzelne Gruppe angenommen.  
  
> [!NOTE]
> Die Verwendung von kann nur mit der [Select](select-entity-sql.md) -Anweisung erfolgen. Wenn [Group by](group-by-entity-sql.md) nicht verwendet wird, verhält sich wie eine WHERE-Klausel.  
  
Die HAVING-Klausel funktioniert wie die WHERE-Klausel, mit dem Unterschied, dass sie nach dem GROUP BY-Vorgang angewendet wird. Dies bedeutet, dass die "have"-Klausel nur Verweise auf Gruppierungs Aliase und Aggregate erstellen kann, wie im folgenden Beispiel veranschaulicht:
  
```sql  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 Im vorherigen Beispiel werden die Gruppen auf jene eingeschränkt, die mehrere Produkte umfassen.  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird mit dem HAVING-Operator und dem GROUP BY-Operator eine Suchbedingung für eine Gruppe oder ein Aggregat angegeben. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Befolgen Sie das Verfahren unter Gewusst [wie: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-sql[DP EntityServices Concepts#HAVING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#having)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Abfrageausdrücke](query-expressions-entity-sql.md)
