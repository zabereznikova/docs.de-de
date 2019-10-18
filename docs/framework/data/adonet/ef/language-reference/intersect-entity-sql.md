---
title: INTERSECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 93c6fe33-f341-4b52-911e-adf503891951
ms.openlocfilehash: dc7338d176302b8683d541ab0dc715dd8d149c6f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319768"
---
# <a name="intersect-entity-sql"></a>INTERSECT (Entity SQL)
Gibt eine Auflistung aller unterschiedlicher Werte zurück, die sowohl vom Abfrageausdruck auf der linken als auch dem auf der rechten Seite des INTERSECT-Operands zurückgegeben werden. Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ sein wie `expression`.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
expression INTERSECT expression  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Ein beliebiger gültiger Ausdruck, der eine Auflistung für den Vergleich mit einer von einem anderen Abfrageausdruck zurückgegebenen Auflistung zurückgibt.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine Auflistung vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ wie `expression`.  
  
## <a name="remarks"></a>Hinweise  
 INTERSECT ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren. Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet. Informationen zu Rang folgen Informationen für die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Mengen Operatoren finden Sie unter [Ausnahme](except-entity-sql.md)von.  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird der INTERSECT-Operator verwendet, um eine Auflistung aller unterschiedlicher Werte zurückzugeben, die von beiden Abfrageausdrücken auf der linken und der rechten Seite des INTERSECT-Operators zurückgegeben werden. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-sql[DP EntityServices Concepts#INTERSECT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#intersect)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
