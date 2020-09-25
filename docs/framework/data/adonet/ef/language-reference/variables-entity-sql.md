---
title: Variablen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: af6d586a22f14a04bfc7ec339d0aa8e9ba7c66c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180997"
---
# <a name="variables-entity-sql"></a>Variablen (Entity SQL)

## <a name="variable"></a>Variable  

 Ein Variablenausdruck ist ein Verweis auf einen im aktuellen Bereich definierten benannten Ausdruck. Ein Variablen Verweis muss ein gültiger [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Bezeichner sein, wie [er in Bezeichnern](identifiers-entity-sql.md)definiert ist.  
  
 Im folgenden Beispiel wird die Verwendung einer Variablen im Ausdruck dargestellt. Der Buchstabe  in der FROM-Klausel ist die Definition der Variablen. Die Verwendung von  in der SELECT-Klausel stellt den Variablenverweis dar.  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Identifiers (Bezeichner)](identifiers-entity-sql.md)
- [Parameter](parameters-entity-sql.md)
- [Übersicht über Entity SQL](entity-sql-overview.md)
