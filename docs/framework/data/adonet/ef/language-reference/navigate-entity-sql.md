---
title: "NAVIGATE (Entity SQL) | Microsoft Docs"
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
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# NAVIGATE (Entity SQL)
Navigiert durch die zwischen Entitäten eingerichteten Beziehungen.  
  
## Syntax  
  
```  
  
navigate(instance-expresssion, [relationship-type], [to-end [, from-end] ])  
```  
  
## Argumente  
 `instance-expresssion`  
 Eine Instanz einer Entität.  
  
 `relationship-type`  
 Der Typname der Beziehung aus der CSDL\-Datei \(Conceptual Schema Definition Language, konzeptionelle Schemadefinitionssprache\). Der `relationship-type` ist als \<Namespace\>.\<Beziehungstypname\> qualifiziert.  
  
 `to`  
 Das Ende der Beziehung.  
  
 `from`  
 Der Anfang der Beziehung.  
  
## Rückgabewert  
 Wenn die Kardinalität des "to"\-Endes "1" beträgt, ist der Rückgabewert `Ref<T>`. Wenn die Kardinalität des "to"\-Endes "n" beträgt, ist der Rückgabewert `Collection<Ref<T>>`.  
  
## Hinweise  
 Beziehungen sind im [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] \(EDM\) Konstrukte der ersten Klasse. Beziehungen können zwischen zwei oder mehr Entitätstypen festgelegt werden, und Benutzer können über die Beziehung von einem Ende \(Entität\) zu einem anderen navigieren.`from` und `to` sind bedingt optional, wenn es keine Mehrdeutigkeit in der Namensauflösung innerhalb der Beziehung gibt.  
  
 NAVIGATE ist im O\- und im C\-Raum gültig.  
  
 Ein Navigationskonstrukt hat die folgende allgemeine Form:  
  
 navigate\(`instance-expresssion`, `relationship-type`, \[ `to-end` \[, `from-end` \] \] \)  
  
 Beispiel:  
  
```  
Select o.Id, navigate(o, OrderCustomer, Customer, Order)  
From LOB.Orders as o  
```  
  
 Dabei ist "OrderCustomer" die `relationship`, und "Customer" und "Order" sind das `to-end` bzw. das `from-end` der Beziehung. Wenn "OrderCustomer" eine n:1\-Beziehung war, ist der Ergebnistyp des Navigationsausdrucks Ref\<Customer\>.  
  
 Eine einfachere Form dieses Ausdrucks ist die Folgende:  
  
```  
Select o.Id, navigate(o, OrderCustomer)  
From LOB.Orders as o  
```  
  
 Entsprechend generiert der Navigationsausdruck in einer Abfrage der folgenden Form eine Collection\<Ref\<Order\>\>.  
  
```  
Select c.Id, navigate(c, OrderCustomer, Order, Customer)  
From LOB.Customers as c  
```  
  
 Der Instanzausdruck muss ein Entitäts\-\/Verweistyp sein.  
  
## Beispiel  
 In der folgenden Entity SQL\-Abfrage wird mithilfe des NAVIGATE\-Operators die zwischen den Entitätstypen "Address" und "SalesOrderHeader" bestehende Beziehung navigiert. Diese Abfrage beruht auf dem "AdventureWorks Sales"\-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [Vorgehensweise: Ausführen einer Abfrage, die StructuralType\-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery`\-Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#NAVIGATE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#navigate)]  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [How to: Navigate Relationships with Navigate Operator](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)