---
title: Aggregatfunktionen (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: acfd3149-f519-4c6e-8fe1-b21d243a0e58
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ff9462b1a5a6f6f9f4614098c38bb5fab14a5203
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="aggregate-functions-entity-sql"></a>Aggregatfunktionen (Entity SQL)
Ein Aggregat ist ein Sprachkonstrukt, das eine Auflistung als Teil einer Gruppenoperation zu einem Skalar zusammenfasst. Es gibt zwei Arten von [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Aggregaten:  
  
-   [!INCLUDE[esql](../../../../../../includes/esql-md.md)]Auflistungsfunktionen, die an einer beliebigen Stelle in einem Ausdruck verwendet werden können. Hierzu gehört auch die Verwendung von Aggregatfunktionen in Projektionen und Prädikate, die auf Auflistungen angewendet werden. Auflistungsfunktionen sind der bevorzugte Modus zum Angeben von Aggregaten in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
-   Gruppenaggregate in Abfrageausdrücken, die über eine GROUP BY-Klausel verfügen. Wie in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] akzeptieren Gruppenaggregate DISTINCT und ALL als Modifizierer für die Aggregateingabe.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]zunächst versucht, einen Ausdruck als eine Funktion für die Sammlung zu interpretieren und wenn der Ausdruck im Rahmen einer SELECT-Ausdruck wird als Aggregat Gruppe interpretiert.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]definiert einen besonderen Aggregatoperator namens [GROUPPARTITION](../../../../../../docs/framework/data/adonet/ef/language-reference/grouppartition-entity-sql.md). Mit diesem Operator können Sie einen Verweis auf den gruppierten Eingabesatz abrufen. Dies ermöglicht erweiterte Gruppierungsabfragen, wobei die Ergebnisse der GROUP BY-Klausel an anderen Stellen als Gruppenaggregat- oder Auflistungsfunktionen verwendet werden können.  
  
## <a name="collection-functions"></a>Auflistungsfunktionen  
 Auflistungsfunktionen verarbeiten Auflistungen und geben einen Skalarwert zurück. Wenn beispielsweise `orders` eine Auflistung aller `orders` bezeichnet, können Sie das früheste Lieferdatum mit dem folgenden Ausdruck berechnen:  
  
 `min(select value o.ShipDate from LOB.Orders as o)`  
  
## <a name="group-aggregates"></a>Gruppenaggregate  
 Gruppenaggregate werden nach einem Gruppenergebnis berechnet, das von einer GROUP BY-Klausel definiert wurde. Die GROUP BY-Klausel teilt Daten in Gruppen ein. Für jede Gruppe im Ergebnis wird die Aggregatfunktion angewendet, und ein separates Aggregat wird berechnet, indem die Elemente in jeder Gruppe als Eingaben zur Aggregatberechnung verwendet werden. Wird eine GROUP BY-Klausel in einem SELECT-Ausdruck verwendet, dürfen sich in der Projektion, der HAVING- oder ORDER BY-Klausel nur die Namen von Gruppierungsausdrücken, Aggregate oder konstante Ausdrücke befinden.  
  
 Im folgenden Beispiel wird die durchschnittlich bestellte Anzahl für jedes Produkt berechnet.  
  
 `select p, avg(ol.Quantity) from LOB.OrderLines as ol`  
  
 `group by ol.Product as p`  
  
 Gruppenaggregate können im SELECT-Ausdruck ohne explizite GROUP BY-Klausel vorkommen. Alle Elemente werden als einzelne Gruppe behandelt, die der Angabe einer Gruppe auf Grundlage einer Konstante entsprechen.  
  
 `select avg(ol.Quantity) from LOB.OrderLines as ol`  
  
 `select avg(ol.Quantity) from LOB.OrderLines as ol group by 1`  
  
 Ausdrücke, die in der GROUP BY-Klausel verwendet werden, werden mit dem gleichen Namensauflösungsbereich ausgewertet, der für den WHERE-Klauselausdruck sichtbar wäre.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
