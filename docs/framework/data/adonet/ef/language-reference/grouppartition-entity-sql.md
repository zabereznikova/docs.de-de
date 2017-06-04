---
title: "GROUPPARTITION (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d0482e9b-086c-451c-9dfa-ccb024a9efb6
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# GROUPPARTITION (Entity SQL)
Gibt eine Auflistung von Argumentwerten zurück, die für die aktuelle Gruppenpartition projiziert werden, auf die sich das Aggregat bezieht. Das `GroupPartition`\-Aggregat ist ein gruppenbasiertes Aggregat und weist kein auflistungsbasiertes Formular auf.  
  
## Syntax  
  
```  
  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## Argumente  
 `expression`  
 Beliebiger [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Ausdruck.  
  
## Hinweise  
 Die folgende Abfrage erzeugt eine Liste von Produkten und eine Auflistung von Reihenfolgenzeilenmengen für jedes Produkt:  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 Die folgenden zwei Abfragen stimmen semantisch überein:  
  
```  
select p, Sum(GroupPartition(ol.Quantity)) from LOB.OrderLines as ol  
  group by ol.Product as p  
select p, Sum(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 Der `GROUPPARTITION`\-Operator kann in Verbindung mit benutzerdefinierten Aggregatfunktionen verwendet werden.  
  
 `GROUPPARTITION` ist ein besonderer Aggregatoperator, der einen Verweis auf den gruppierten Eingabesatz beinhaltet. Dieser Verweis kann an einer beliebigen Stelle in der Abfrage verwendet werden, an der sich GROUP BY innerhalb des Bereichs befindet. Beispiel:  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 Bei einem regulären GROUP BY werden die Ergebnisse des Gruppiervorgangs ausgeblendet. Sie können die Ergebnisse nur in einer Aggregatfunktion verwenden. Zum Anzeigen der Ergebnisse des Gruppiervorgangs müssen die Ergebnisse des Gruppiervorgangs und des Eingabesets mithilfe einer Unterabfrage korreliert werden. Die folgenden beiden Abfragen sind gleichwertig:  
  
```  
select p, (select q from GroupPartition(ol.Quantity) as q) from LOB.OrderLines as ol group by ol.Product as p  
select p, (select ol.Quantity as q from LOB.OrderLines as ol2 where ol2.Product = p) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 Wie im Beispiel gezeigt, wird durch den GROUPPARTITION\-Aggregatoperator das Abrufen einen Verweises auf den Eingabesatz nach dem Gruppiervorgang vereinfacht.  
  
 Der GROUPPARTITION\-Operator kann bei Verwendung des [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Parameters einen beliebigen `expression`\-Ausdruck im Operator angeben.  
  
 Zum Beispiel sind die folgenden Eingabeausdrücke für die Gruppenpartition gültig:  
  
```  
select groupkey, GroupPartition(b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(1) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(a + b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({a + b}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({42}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(b > a) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
```  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die GROUPPARTITION\-Klausel mit der GROUP BY\-Klausel verwendet wird. Die GROUP BY\-Klausel gruppiert `SalesOrderHeader`\-Entitäten nach `Contact`. Die GROUPPARTITION\-Klausel projiziert dann für jede Gruppe die `TotalDue`\-Eigenschaft, woraus sich eine Auflistung von Dezimalwerten ergibt.  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]