---
title: Aggregatfunktionen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: acfd3149-f519-4c6e-8fe1-b21d243a0e58
ms.openlocfilehash: 308670f04b9a04b1fff77ece08deb39c8c4081d1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198079"
---
# <a name="aggregate-functions-entity-sql"></a>Aggregatfunktionen (Entity SQL)

Ein Aggregat ist ein Sprachkonstrukt, das eine Auflistung als Teil einer Gruppenoperation zu einem Skalar zusammenfasst. Es gibt zwei Arten von [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Aggregaten:  
  
- [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Sammlungs Funktionen, die an beliebiger Stelle in einem Ausdruck verwendet werden können. Hierzu gehört auch die Verwendung von Aggregatfunktionen in Projektionen und Prädikate, die auf Auflistungen angewendet werden. Auflistungsfunktionen sind der bevorzugte Modus zum Angeben von Aggregaten in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
- Gruppenaggregate in Abfrageausdrücken, die über eine GROUP BY-Klausel verfügen. Wie bei Transact-SQL akzeptieren Gruppen Aggregate unterschiedliche und alle-modifiziererer für die Aggregat Eingabe.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] versucht zunächst, einen Ausdruck als Auflistungs Funktion zu interpretieren, und wenn sich der Ausdruck im Kontext eines SELECT-Ausdrucks befindet, interpretiert er ihn als Gruppen Aggregat.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] definiert einen speziellen Aggregat Operator mit dem Namen [GroupPartition](grouppartition-entity-sql.md). Mit diesem Operator können Sie einen Verweis auf den gruppierten Eingabesatz abrufen. Dies ermöglicht erweiterte Gruppierungsabfragen, wobei die Ergebnisse der GROUP BY-Klausel an anderen Stellen als Gruppenaggregat- oder Auflistungsfunktionen verwendet werden können.  
  
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

- [Funktionen](functions-entity-sql.md)
