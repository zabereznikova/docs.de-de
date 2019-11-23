---
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: 27fc23a2be47ea00eff20aa8d2f559af5ae90387
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833902"
---
# <a name="deref-entity-sql"></a>DEREF (Entity SQL)
Dereferenziert einen Verweiswert und erstellt das Ergebnis dieser Dereferenzierung.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
SELECT DEREF ( o.expression ) FROM Table AS o;
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Jeder gültige Abfrageausdruck, der eine Auflistung zurückgibt.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Wert der Entität, auf die verwiesen wird.  
  
## <a name="remarks"></a>Hinweise  
 Der DEREF-Operator dereferenziert einen Verweiswert und erstellt das Ergebnis dieser Dereferenzierung. Wenn `r` z. b. ein Verweis vom Typ Ref\<t > ist, ist `Deref(r)` ein Ausdruck vom Typ `T`, der die Entität ergibt, auf die von `r`verwiesen wird. Wenn der Verweiswert NULL ist oder das Ziel des Verweises nicht existiert, hat das Ergebnis des DEREF-Operators den Wert NULL.  
  
## <a name="example"></a>Beispiel  
 In der folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage wird der DEREF-Operator verwendet, um einen Verweiswert zu dereferenzieren und das Ergebnis dieser Dereferenzierung zu erstellen. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Befolgen Sie das Verfahren unter Gewusst [wie: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die ExecutePrimitiveTypeQuery-Methode:  
  
 [!code-sql[DP EntityServices Concepts#DEREF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#deref)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
- [REF](ref-entity-sql.md)
- [CREATEREF](createref-entity-sql.md)
- [KEY](key-entity-sql.md)
- [Strukturierte Typen, die NULL-Werte zulassen](nullable-structured-types-entity-sql.md)
