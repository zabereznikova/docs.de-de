---
title: "! (NOT) (Entity SQL) | Microsoft Docs"
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
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# ! (NOT) (Entity SQL)
Negiert einen `Boolean`\-Ausdruck.  
  
## Syntax  
  
```  
  
NOT boolean_expression  
or  
! boolean_expression  
```  
  
## Argumente  
 `boolean_expression`  
 Jeder gültige Ausdruck, der einen booleschen Wert zurückgibt.  
  
## Hinweise  
 Das Ausrufezeichen \(\!\) hat dieselbe Bedeutung wie der NOT\-Operator.  
  
## Beispiel  
 Die folgende Entity SQL\-Abfrage verwendet den NOT\-Operator, um einen `Boolean`\-Ausdruck zu negieren. Diese Abfrage beruht auf dem "AdventureWorks Sales"\-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [Vorgehensweise: Ausführen einer Abfrage, die StructuralType\-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery`\-Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not)]  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)