---
title: BETWEEN (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3b27aee261e9195c2cb5f15e369cf26de4c0691a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="between-entity-sql"></a>BETWEEN (Entity SQL)
Ermittelt, ob der Ergebniswert eines Ausdrucks in einem angegebenen Bereich liegt. Die [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN-Ausdruck hat die gleiche Funktionalität wie die Transact-SQL BETWEEN-Ausdruck.  
  
## <a name="syntax"></a>Syntax  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Jeder zu testende gültige Ausdruck im Bereich, der durch `begin_expression` und `end_expression` definiert ist. `expression` muss den gleichen Typ wie `begin_expression` und `end_expression` aufweisen.  
  
 `begin_expression`  
 Jeder gültige Ausdruck. `begin_expression` muss den gleichen Typ wie `expression` und `end_expression` aufweisen. `begin_expression` sollte kleiner als `end_expression` sein, anderenfalls wird der Rückgabewert negiert.  
  
 `end_expression`  
 Jeder gültige Ausdruck. `end_expression` muss den gleichen Typ wie `expression` und `begin_expression` aufweisen.  
  
 NOT  
 Gibt an, dass das Ergebnis von BETWEEN negiert werden soll.  
  
 AND  
 Dient als Platzhalter, der anzeigt, dass sich `expression` in dem durch `begin_expression` und `end_expression` festgelegten Bereich befinden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`, wenn `expression` in dem von `begin_expression` und `end_expression` angegebenen Bereich liegt, anderenfalls `false`. `null` wird zurückgegeben, wenn `expression` entweder `null` ist, oder wenn `begin_expression` oder `end_expression` den Wert `null` aufweisen.  
  
## <a name="remarks"></a>Hinweise  
 Zum Angeben eines Bereichs, der seine Grenzen nicht enthält, sollten anstelle des BETWEEN-Operators die Operatoren "Größer-als" (>) und "Kleiner-als" (<) verwendet werden.  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird der BETWEEN-Operator verwendet, um zu ermitteln, ob der Ergebniswert einer Abfrage in einem angegebenen Bereich liegt. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a>Siehe auch  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
