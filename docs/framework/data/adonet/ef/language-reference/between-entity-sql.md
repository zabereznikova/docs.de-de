---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 2c411fd7fcac9d98323d5fcfb1874f98bc664991
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225260"
---
# <a name="between-entity-sql"></a>BETWEEN (Entity SQL)
Ermittelt, ob der Ergebniswert eines Ausdrucks in einem angegebenen Bereich liegt. Die [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN-Ausdruck hat die gleiche Funktionalität wie die Transact-SQL-BETWEEN-Ausdruck.  
  
## <a name="syntax"></a>Syntax  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Jeder zu testende gültige Ausdruck im Bereich, der durch `begin_expression` und `end_expression` definiert ist. `expression` muss vom gleiche Typ sein wie `begin_expression` und `end_expression`.  
  
 `begin_expression`  
 Jeder gültige Ausdruck. `begin_expression` muss vom gleiche Typ sein wie `expression` und `end_expression`. `begin_expression` muss kleiner als `end_expression`, andernfalls wird der Rückgabewert negiert.  
  
 `end_expression`  
 Jeder gültige Ausdruck. `end_expression` muss vom gleiche Typ sein wie `expression` und `begin_expression`.  
  
 NICHT  
 Gibt an, dass das Ergebnis von BETWEEN negiert werden soll.  
  
 UND  
 Dient als Platzhalter, der anzeigt, dass sich `expression` in dem durch `begin_expression` und `end_expression` festgelegten Bereich befinden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Wenn `expression` zwischen durch den Bereich `begin_expression` und `end_expression`ist, andernfalls `false`. `null` wird zurückgegeben, wenn `expression` ist `null` oder, wenn `begin_expression` oder `end_expression` ist `null`.  
  
## <a name="remarks"></a>Hinweise  
 Um einen Exklusivbereich anzugeben, verwenden Sie die größer als (>) und kleiner-als-Operatoren (<) anstelle von BETWEEN.  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird der BETWEEN-Operator verwendet, um zu ermitteln, ob der Ergebniswert einer Abfrage in einem angegebenen Bereich liegt. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
