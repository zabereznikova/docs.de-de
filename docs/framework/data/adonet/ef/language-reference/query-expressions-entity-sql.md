---
title: Abfrageausdrücke (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
ms.openlocfilehash: 4428286890f41573a02daf31a4593d0c8f9ad34b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249275"
---
# <a name="query-expressions-entity-sql"></a>Abfrageausdrücke (Entity SQL)
Ein Abfrageausdruck fasst viele verschiedene Abfrageoperatoren in einer einzigen Syntax zusammen. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]stellt verschiedene Arten von Ausdrücken bereit, einschließlich der folgenden: [Literale](literals-entity-sql.md), [Parameter](parameters-entity-sql.md), [Variablen](variables-entity-sql.md), Operatoren, [Funktionen](functions-entity-sql.md), Mengen Operatoren usw. Weitere Informationen finden Sie unter [Entity SQL Referenz](entity-sql-reference.md).  
  
## <a name="clauses"></a>Klauseln  
 Ein Abfrageausdruck setzt sich aus einer Serie von Klauseln zusammen, die für eine Auflistung von Objekten aufeinander folgende Operationen durchführen. Sie basieren auf denselben Klauseln, die in der standardmäßigen SQL-SELECT-Anweisung gefunden werden: [Select](select-entity-sql.md), [from](from-entity-sql.md), [Where](where-entity-sql.md), [Group by](group-by-entity-sql.md), [have und](having-entity-sql.md) [Order by](order-by-entity-sql.md).  
  
## <a name="scope"></a>Bereich  
 In der FROM-Klausel definierte Namen werden in der Reihenfolge ihres Auftretens (von links nach rechts) in den FROM-Gültigkeitsbereich eingeführt. In der JOIN-Liste können Ausdrücke auf Namen verweisen, die zuvor in der Liste definiert wurden. Öffentliche Eigenschaften von Elementen, die in der from-Klausel identifiziert werden, werden nicht dem from-Bereich hinzugefügt: Auf Sie muss immer durch den Alias qualifizierten Namen verwiesen werden. Üblicherweise werden im FROM-Gültigkeitsbereich alle Teile des SELECT-Ausdrucks berücksichtigt.  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
