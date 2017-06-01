---
title: "UNION (Entity SQL) | Microsoft Docs"
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
  - "ESQL"
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# UNION (Entity SQL)
Fasst die Ergebnisse von zwei oder mehr Abfragen in einer Auflistung zusammen.  
  
## Syntax  
  
```  
  
          expression  
UNION [ ALL ]  
expression  
```  
  
## Argumente  
 `expression`  
 Jeder gültige Abfrageausdruck, der eine mit der Auflistung zusammenzufassende Auflistung zurückgibt. Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ wie `expression` sein.  
  
 UNION  
 Gibt an, dass mehrere Auflistungen kombiniert und als einzelne Auflistung zurückgegeben werden sollen.  
  
 ALL  
 Gibt an, dass mehrere Auflistungen kombiniert und als einzelne Auflistung zurückgegeben werden sollen, wobei Duplikate erhalten bleiben. Wenn dies nicht angegeben wird, werden Duplikate aus der Ergebnisauflistung entfernt.  
  
## Rückgabewert  
 Eine Auflistung vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ wie `expression`.  
  
## Hinweise  
 UNION ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Mengenoperatoren. Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Mengenoperatoren werden von links nach rechts ausgewertet. Informationen zur Rangfolge der [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Mengenoperatoren finden Sie unter [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).  
  
## Beispiel  
 Die folgende Entity SQL\-Abfrage verwendet den UNION ALL\-Operator, um die Ergebnisse von zwei Abfragen in einer Auflistung zusammenzufassen. Diese Abfrage beruht auf dem "AdventureWorks Sales"\-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [Vorgehensweise: Ausführen einer Abfrage, die StructuralType\-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery`\-Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#UNION](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#union)]  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)