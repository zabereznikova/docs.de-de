---
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: 34eac0dfd28d39ec68f084ea10dd46693f44eea3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248791"
---
# <a name="union-entity-sql"></a>UNION (Entity SQL)
Fasst die Ergebnisse von zwei oder mehr Abfragen in einer Auflistung zusammen.  
  
## <a name="syntax"></a>Syntax  
  
```  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Jeder gültige Abfrageausdruck, der eine mit der Auflistung zusammenzufassende Auflistung zurückgibt. Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ wie `expression`sein.  
  
 UNION  
 Gibt an, dass mehrere Auflistungen kombiniert und als einzelne Auflistung zurückgegeben werden sollen.  
  
 ALL  
 Gibt an, dass mehrere Auflistungen kombiniert und als einzelne Auflistung zurückgegeben werden sollen, wobei Duplikate erhalten bleiben. Wenn dies nicht angegeben wird, werden Duplikate aus der Ergebnisauflistung entfernt.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine Auflistung vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ wie `expression`.  
  
## <a name="remarks"></a>Hinweise  
 UNION ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren. Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet. Informationen zur Rangfolge der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengen Operatoren finden Sie unter [Ausnahme](except-entity-sql.md)von.  
  
## <a name="example"></a>Beispiel  
 Die folgende Entity SQL-Abfrage verwendet den UNION ALL-Operator, um die Ergebnisse von zwei Abfragen in einer Auflistung zusammenzufassen. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die StructuralType-Ergebnisse](../how-to-execute-a-query-that-returns-structuraltype-results.md)zurückgibt.  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#UNION](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#union)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
