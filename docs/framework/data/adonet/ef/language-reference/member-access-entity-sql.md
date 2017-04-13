---
title: ". (Memberzugriff) (Entity SQL) | Microsoft Docs"
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
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# . (Memberzugriff) (Entity SQL)
Der [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Operator für den Memberzugriff ist der Punktoperator \(.\).  Mit dem Operator für den Memberzugriff kann auf den Wert einer Eigenschaft oder eines Felds der Instanz eines strukturellen konzeptionellen Modelltyps zugegriffen werden.  
  
## Syntax  
  
```  
expression.identifier  
```  
  
## Argumente  
 `expression`  
 Eine Instanz eines strukturellen konzeptionellen Modelltyps.  
  
 `identifier`  
 Eine Eigenschaft oder ein Feld einer Objektinstanz.  
  
## Hinweise  
 Mit dem Punktoperator \(.\) können Sie Felder eines Datensatzes extrahieren, ähnlich wie beim Extrahieren der Eigenschaften eines komplexen Typs oder Entitätstyps.  Wenn z. B. "n" vom Typ "Name" ein Member des Typs "Person" ist und "p" eine Instanz des Typs "Person" ist, ist "p.  n" ein zulässiger Memberzugriffsausdruck, der einen Wert des Typs "Name" zurückgibt.  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)