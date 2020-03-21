---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: a0f5dd19c439861451b1e88c3ae35f9f265288fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150492"
---
# <a name="between-entity-sql"></a>BETWEEN (Entity SQL)
Ermittelt, ob der Ergebniswert eines Ausdrucks in einem angegebenen Bereich liegt. Der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN-Ausdruck hat die gleiche Funktionalität wie der Transact-SQL BETWEEN-Ausdruck.  
  
## <a name="syntax"></a>Syntax  
  
```csharp  
expression [ NOT ] BETWEEN begin_expression AND end_expression
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Jeder zu testende gültige Ausdruck im Bereich, der durch `begin_expression` und `end_expression` definiert ist. `expression` muss den gleichen Typ wie `begin_expression` und `end_expression` aufweisen.  
  
 `begin_expression`  
 Beliebiger gültiger Ausdruck. `begin_expression` muss den gleichen Typ wie `expression` und `end_expression` aufweisen. `begin_expression` sollte kleiner als `end_expression` sein, anderenfalls wird der Rückgabewert negiert.  
  
 `end_expression`  
 Beliebiger gültiger Ausdruck. `end_expression` muss den gleichen Typ wie `expression` und `begin_expression` aufweisen.  
  
 NICHT  
 Gibt an, dass das Ergebnis von BETWEEN negiert werden soll.  
  
 AND  
 Dient als Platzhalter, der anzeigt, dass sich `expression` in dem durch `begin_expression` und `end_expression` festgelegten Bereich befinden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`, wenn `expression` in dem von `begin_expression` und `end_expression` angegebenen Bereich liegt, anderenfalls `false`. `null` wird zurückgegeben, wenn `expression` entweder `null` ist, oder wenn `begin_expression` oder `end_expression` den Wert `null` aufweisen.  
  
## <a name="remarks"></a>Bemerkungen  
 Um einen exklusiven Bereich anzugeben, verwenden Sie die Operatoren größer als (>) und kleiner als (<) anstelle von BETWEEN.  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird der BETWEEN-Operator verwendet, um zu ermitteln, ob der Ergebniswert einer Abfrage in einem angegebenen Bereich liegt. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Referenz](entity-sql-reference.md)
