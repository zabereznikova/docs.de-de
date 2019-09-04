---
title: Parameter (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 723e40f523f8bb573e0ffcb1863ed0c082ea9d8d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249588"
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

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Übersicht über Entity SQL](entity-sql-overview.md)
