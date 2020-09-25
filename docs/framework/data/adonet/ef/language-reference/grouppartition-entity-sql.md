---
title: GROUPPARTITION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d0482e9b-086c-451c-9dfa-ccb024a9efb6
ms.openlocfilehash: 11abebeac682fed9e3a007986bb2f5c7bdb80f16
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204475"
---
# <a name="grouppartition-entity-sql"></a>GROUPPARTITION (Entity SQL)

Gibt eine Auflistung von Argumentwerten zurück, die für die aktuelle Gruppenpartition projiziert werden, auf die sich das Aggregat bezieht. Das `GroupPartition` -Aggregat ist ein gruppenbasiertes Aggregat und weist kein auflistungsbasiertes Formular auf.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## <a name="arguments"></a>Argumente  

 `expression`  
 Beliebiger [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Ausdruck.  
  
## <a name="remarks"></a>Bemerkungen  

 Die folgende Abfrage erzeugt eine Liste von Produkten und eine Auflistung von Reihenfolgenzeilenmengen für jedes Produkt:  
  
```sql  
SELECT p, GroupPartition(ol.Quantity) FROM LOB.OrderLines AS ol
  GROUP BY ol.Product AS p
```  
  
 Die folgenden zwei Abfragen stimmen semantisch überein:  
  
```sql  
SELECT p, Sum(GroupPartition(ol.Quantity)) FROM LOB.OrderLines AS ol
  GROUP BY ol.Product AS p
SELET p, Sum(ol.Quantity) FROM LOB.OrderLines AS ol
  group by ol.Product as p  
```  
  
 Der `GROUPPARTITION` -Operator kann in Verbindung mit benutzerdefinierten Aggregatfunktionen verwendet werden.  
  
`GROUPPARTITION` ist ein besonderer Aggregatoperator, der einen Verweis auf den gruppierten Eingabesatz beinhaltet. Dieser Verweis kann an einer beliebigen Stelle in der Abfrage verwendet werden, an der sich GROUP BY innerhalb des Bereichs befindet. Zum Beispiel:
  
```sql  
SELECT p, GroupPartition(ol.Quantity) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
```  
  
 Bei einem regulären `GROUP BY` werden die Ergebnisse der Gruppierung ausgeblendet. Sie können die Ergebnisse nur in einer Aggregatfunktion verwenden. Zum Anzeigen der Ergebnisse des Gruppiervorgangs müssen die Ergebnisse des Gruppiervorgangs und des Eingabesets mithilfe einer Unterabfrage korreliert werden. Die folgenden beiden Abfragen sind gleichwertig:  
  
```sql  
SELET p, (SELECT q FROM GroupPartition(ol.Quantity) AS q) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
SELECT p, (SELECT ol.Quantity AS q FROM LOB.OrderLines AS ol2 WHERE ol2.Product = p) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
```  
  
 Wie im Beispiel gezeigt, wird durch den GROUPPARTITION-Aggregatoperator das Abrufen einen Verweises auf den Eingabesatz nach dem Gruppiervorgang vereinfacht.  
  
 Der GROUPPARTITION-Operator kann bei Verwendung des [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Parameters einen beliebigen `expression` -Ausdruck im Operator angeben.  
  
 Zum Beispiel sind die folgenden Eingabeausdrücke für die Gruppenpartition gültig:  
  
```sql  
SELECT groupkey, GroupPartition(b) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition(1) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition(a + b) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition({a + b}) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
SELECT groupkey, GroupPartition({42}) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
SELECT groupkey, GroupPartition(b > a) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
```  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird gezeigt, wie die GROUPPARTITION-Klausel mit der GROUP BY-Klausel verwendet wird. Die GROUP BY-Klausel gruppiert `SalesOrderHeader` -Entitäten nach `Contact`. Die GROUPPARTITION-Klausel projiziert dann für jede Gruppe die `TotalDue` -Eigenschaft, woraus sich eine Auflistung von Dezimalwerten ergibt.  
  
 [!code-sql[DP EntityServices Concepts#Collection_GroupPartition](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#collection_grouppartition)]
