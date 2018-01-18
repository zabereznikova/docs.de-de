---
title: "Abfrageausdrücke (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 46777cbe47e7d97fd3baaa1353787f33cff9f0aa
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="query-expressions-entity-sql"></a>Abfrageausdrücke (Entity SQL)
Ein Abfrageausdruck fasst viele verschiedene Abfrageoperatoren in einer einzigen Syntax zusammen. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]stellt verschiedene Arten von Ausdrücken, u. a. folgende: [Literale](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md), [Parameter](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md), [Variablen](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md), Operatoren, [Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)Mengenoperatoren und so weiter. Weitere Informationen finden Sie unter [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md).  
  
## <a name="clauses"></a>Klauseln  
 Ein Abfrageausdruck setzt sich aus einer Serie von Klauseln zusammen, die für eine Auflistung von Objekten aufeinander folgende Operationen durchführen. Sie basieren auf denselben Klauseln, die im Standard SQL select-Anweisung gefunden: [wählen](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md), [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [, in denen](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md), [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), [Mit](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md), und [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md).  
  
## <a name="scope"></a>Bereich  
 In der FROM-Klausel definierte Namen werden in der Reihenfolge ihres Auftretens (von links nach rechts) in den FROM-Gültigkeitsbereich eingeführt. In der JOIN-Liste können Ausdrücke auf Namen verweisen, die zuvor in der Liste definiert wurden. Öffentliche Eigenschaften von in der FROM-Klausel festgelegten Elementen werden dem FROM-Gültigkeitsbereich nicht hinzugefügt: Auf sie muss immer mit dem aliasqualifizierten Namen verwiesen werden. Üblicherweise werden im FROM-Gültigkeitsbereich alle Teile des SELECT-Ausdrucks berücksichtigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
