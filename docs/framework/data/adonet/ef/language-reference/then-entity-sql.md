---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: c64e440e8cd8f86706db69d923ba7085d0cb3b3a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248992"
---
# <a name="then-entity-sql"></a>THEN (Entity SQL)
Das Ergebnis einer WHEN-Klausel, wenn sie als `true`ausgewertet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
1. Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die PrimitiveType-Ergebnisse](../how-to-execute-a-query-that-returns-primitivetype-results.md)zurückgibt.  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>Siehe auch

- [CASE](case-entity-sql.md)
- [Entity SQL-Referenz](entity-sql-reference.md)
