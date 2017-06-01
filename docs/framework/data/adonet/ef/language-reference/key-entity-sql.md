---
title: "KEY (Entity SQL) | Microsoft Docs"
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
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# KEY (Entity SQL)
Extrahiert den Schlüssel eines Verweises oder eines Entitätsausdrucks.  
  
## Syntax  
  
```  
  
KEY(createref_expression)  
```  
  
## Hinweise  
 Ein Entitätsschlüssel enthält in korrekter Reihenfolge die Schlüsselwerte der angegebenen Entität oder des Entitätsverweises. Da viele Entitätenmengen auf demselben Typ basieren können, kann derselbe Schlüssel in jeder Entitätenmenge vorhanden sein. Um einen eindeutigen Verweis abzurufen, verwenden Sie `REF`. Der Rückgabetyp des KEY\-Operators ist ein Zeilentyp, der ein Feld für jeden Schlüssel der Entität in der gleichen Reihenfolge beinhaltet.  
  
 Im folgenden Beispiel wird dem KEY\-Operator ein Verweis auf die BadOrder\-Entität übergeben, und er gibt den Schlüsselteil dieses Verweises zurück. In diesem Fall einen Datensatztyp mit genau einem Feld, das der `Id`\-Eigenschaft entspricht.  
  
```  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )   
from LOB.Orders as o  
```  
  
## Beispiel  
 Die folgende Entity SQL\-Abfrage verwendet den KEY\-Operator, um den Schlüsselteil eines Ausdrucks mit Typverweis zu extrahieren. Diese Abfrage beruht auf dem "AdventureWorks Sales"\-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [Vorgehensweise: Ausführen einer Abfrage, die StructuralType\-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery`\-Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#KEY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#key)]  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)   
 [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)   
 [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)