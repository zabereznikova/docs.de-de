---
title: Abfrageausdrücke (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
ms.openlocfilehash: 5a200c8fc5adcb6334d0a0ddf290d275de4eb768
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696879"
---
# <a name="query-expressions-entity-sql"></a>Abfrageausdrücke (Entity SQL)
Ein Abfrageausdruck fasst viele verschiedene Abfrageoperatoren in einer einzigen Syntax zusammen. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt verschiedene Arten von Ausdrücken, einschließlich der folgenden: [Literale](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md), [Parameter](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md), [Variablen](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md), Operatoren, [Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md), set-Operatoren und so weiter. Weitere Informationen finden Sie unter [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md).  
  
## <a name="clauses"></a>Klauseln  
 Ein Abfrageausdruck setzt sich aus einer Serie von Klauseln zusammen, die für eine Auflistung von Objekten aufeinander folgende Operationen durchführen. Sie basiert auf denselben Klauseln, die im Standard finden Sie eine SQL-select-Anweisung: [Wählen Sie](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md), [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [, in denen](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md), [GROUP BY-](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md), und [sortiert nach dem](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md).  
  
## <a name="scope"></a>Bereich  
 In der FROM-Klausel definierte Namen werden in der Reihenfolge ihres Auftretens (von links nach rechts) in den FROM-Gültigkeitsbereich eingeführt. In der JOIN-Liste können Ausdrücke auf Namen verweisen, die zuvor in der Liste definiert wurden. Öffentliche Eigenschaften von Elementen, die in der FROM-Klausel identifizierten werden nicht in der FROM-Bereich hinzugefügt: Sie müssen immer durch den aliasqualifizierten Namen verwiesen werden. Üblicherweise werden im FROM-Gültigkeitsbereich alle Teile des SELECT-Ausdrucks berücksichtigt.  
  
## <a name="see-also"></a>Siehe auch
- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
