---
title: Parameter (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 5fa050e43e4590f61c3011a1b9bb0937da7032a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632386"
---
# <a name="parameters-entity-sql"></a>Parameter (Entity SQL)
Parameter sind Variablen, die außerhalb von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] definiert werden, üblicherweise über eine Bindungs-API, die von einer Hostsprache verwendet wird. Jeder Parameter hat einen Namen und einen Typ. Parameternamen werden in Abfrageausdrücken mit einem "at" (@)-Symbol als Präfix definiert. Damit sind sie von den Namen von Eigenschaften oder anderen in der Abfrage definierten Namen unterscheidbar.  
  
 Die Bindungs-API der Hostsprache stellt APIs für die Parameterbindung zur Verfügung.  
  
## <a name="example"></a>Beispiel  
  
```  
select c   
      from LOB.Customers as c   
      where c.Name = @name  
```  
  
## <a name="see-also"></a>Siehe auch
- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
