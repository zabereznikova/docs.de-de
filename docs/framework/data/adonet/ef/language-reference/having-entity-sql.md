---
title: HAVING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
ms.openlocfilehash: 0378aa365351dcd8c6c1b59674d785def1ee2648
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684826"
---
# <a name="having-entity-sql"></a>HAVING (Entity SQL)
Gibt eine Suchbedingung für eine Gruppe oder ein Aggregat an.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a>Argumente  
 `search_condition`  
 Gibt die Suchbedingung für die Gruppe oder das Aggregat an. Wenn HAVING mit GROUP BY ALL verwendet wird, setzt die HAVING-Klausel ALL außer Kraft.  
  
## <a name="remarks"></a>Hinweise  
 Mit der HAVING-Klausel kann für das Ergebnis einer Gruppierung eine zusätzliche Filterbedingung angegeben werden. Wenn Sie im Abfrageausdruck keine GROUP BY-Klausel angeben, wird eine implizite einzelne Gruppe angenommen.  
  
> [!NOTE]
>  HAVING kann verwendet werden, nur mit der [wählen](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) Anweisung. Wenn [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) wird nicht verwendet wird, verhält sich HAVING wie eine WHERE-Klausel.  
  
 Die HAVING-Klausel funktioniert wie die WHERE-Klausel, mit dem Unterschied, dass sie nach dem GROUP BY-Vorgang angewendet wird. Dies bedeutet, dass die HAVING-Klausel nur auf Gruppierungsaliase und Aggregate verweisen kann, wie im folgenden Beispiel veranschaulicht.  
  
```  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 Im vorherigen Beispiel werden die Gruppen auf jene eingeschränkt, die mehrere Produkte umfassen.  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird mit dem HAVING-Operator und dem GROUP BY-Operator eine Suchbedingung für eine Gruppe oder ein Aggregat angegeben. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#HAVING](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#having)]  
  
## <a name="see-also"></a>Siehe auch
- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Abfrageausdrücke](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
