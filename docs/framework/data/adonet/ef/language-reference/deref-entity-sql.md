---
title: "DEREF (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# DEREF (Entity SQL)
Dereferenziert einen Verweiswert und erstellt das Ergebnis dieser Dereferenzierung.  
  
## Syntax  
  
```  
  
SELECT DEREF ( o.expression) from Table as o;  
```  
  
## Argumente  
 `expression`  
 Jeder gültige Abfrageausdruck, der eine Auflistung zurückgibt.  
  
## Rückgabewert  
 Der Wert der Entität, auf die verwiesen wird.  
  
## Hinweise  
 Der DEREF\-Operator dereferenziert einen Verweiswert und erstellt das Ergebnis dieser Dereferenzierung. Wenn z. B. `r` ein Verweis vom Typ „ref\<T\>“ ist, ist  `Deref` `(r)` ein Ausdruck vom Typ `T` , der die Entität zurückgibt, auf die von `r` verwiesen wird. Wenn der Verweiswert NULL ist oder das Ziel des Verweises nicht existiert, hat das Ergebnis des DEREF\-Operators den Wert NULL.  
  
## Beispiel  
 In der folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Abfrage wird der DEREF\-Operator verwendet, um einen Verweiswert zu dereferenzieren und das Ergebnis dieser Dereferenzierung zu erstellen. Diese Abfrage beruht auf dem "AdventureWorks Sales"\-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType\-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die ExecutePrimitiveTypeQuery\-Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)   
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)   
 [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)   
 [Strukturierte Typen, die NULL\-Werte zulassen](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)