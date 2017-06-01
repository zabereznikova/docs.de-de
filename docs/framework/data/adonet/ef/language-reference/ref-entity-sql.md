---
title: "REF (Entity SQL) | Microsoft Docs"
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
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# REF (Entity SQL)
Gibt einen Verweis auf eine Entitätsinstanz zurück.  
  
## Syntax  
  
```  
  
REF( expression )   
```  
  
## Argumente  
 `expression`  
 Gültige Ausdrücke, die eine Instanz eines Entitätstyps zurückgeben.  
  
## Rückgabewert  
 Ein Verweis auf die angegebene Entitätsinstanz.  
  
## Hinweise  
 Ein Entitätsverweis besteht aus dem Entitätsschlüssel und einem Entitätenmengennamen. Da unterschiedliche Entitätenmengen auf demselben Typ basieren können, kann ein bestimmter Entitätsschlüssel in mehreren Entitätenmengen erscheinen. Ein Entitätsverweis ist jedoch stets eindeutig. Wenn der Eingabeausdruck eine permanente Entität darstellt, wird ein Verweis auf diese Entität zurückgegeben. Wenn der Eingabeausdruck keine permanente Entität ist, wird ein NULL\-Verweis zurückgegeben.  
  
 Wird der Eigenschaftsextraktionsoperator \(.\) für den Zugriff auf eine Eigenschaft verwendet, wird der Verweis automatisch dereferenziert.  
  
## Beispiel  
 Die folgende Entity SQL\-Abfrage verwendet den REF\-Operator, um den Verweis für ein Eingabeentitätsargument zurückzugeben. Dieselbe Abfrage dereferenziert den Verweis, da ein Eigenschaftsextraktionsoperator \(.\) für den Zugriff auf eine Eigenschaft der "Product"\-Entität verwendet wird. Diese Abfrage beruht auf dem "AdventureWorks Sales"\-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType\-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery`\-Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#REF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref)]  
  
## Siehe auch  
 [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)   
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)   
 [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)   
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Typdefinitionen](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)