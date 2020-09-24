---
title: Parameter (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 759452902461e1a460b69774bb33f92bbd532ed0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177513"
---
# <a name="parameters-entity-sql"></a>Parameter (Entity SQL)

Parameter sind Variablen, die außerhalb von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] definiert werden, üblicherweise über eine Bindungs-API, die von einer Hostsprache verwendet wird. Jeder Parameter hat einen Namen und einen Typ. Parameternamen werden in Abfrageausdrücken mit einem "at" (@)-Symbol als Präfix definiert. Damit sind sie von den Namen von Eigenschaften oder anderen in der Abfrage definierten Namen unterscheidbar.  
  
 Die Bindungs-API der Hostsprache stellt APIs für die Parameterbindung zur Verfügung.  
  
## <a name="example"></a>Beispiel  
  
```sql  
SELECT c
      FROM LOB.Customers AS c
      WHERE c.Name = @name  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Übersicht über Entity SQL](entity-sql-overview.md)
