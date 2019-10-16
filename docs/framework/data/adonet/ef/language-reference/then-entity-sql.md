---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: ba01a978c53b58f7e6c1ac9bc42a97277ac64bbc
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319281"
---
# <a name="then-entity-sql"></a>THEN (Entity SQL)
Das Ergebnis einer WHEN-Klausel, wenn sie als `true`ausgewertet wird.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a>Argumente  
 `when_expression`  
 Jeder gültige boolesche Ausdruck.  
  
 `then_expression`  
 Jeder gültige Abfrageausdruck, der eine Auflistung zurückgibt.  
  
## <a name="remarks"></a>Hinweise  
 Falls `when_expression` zum Wert `true`ausgewertet wird, ist das Ergebnis der entsprechende `then-expression`. Wird keine der WHEN-Bedingungen erfüllt, wird der `else-expression` ausgewertet. Wenn jedoch kein `else-expression`vorhanden ist, ist das Ergebnis NULL.  
  
 Ein Beispiel finden Sie unter [Case](case-entity-sql.md).  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird der CASE-Ausdruck zur Auswertung einer Reihe von `Boolean` -Ausdrücken verwendet. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Befolgen Sie das Verfahren unter Gewusst [wie: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-sql[DP EntityServices Concepts#CASE_WHEN_THEN_ELSE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#case_when_then_else)]  
  
## <a name="see-also"></a>Siehe auch

- [CASE](case-entity-sql.md)
- [Entity SQL-Referenz](entity-sql-reference.md)
