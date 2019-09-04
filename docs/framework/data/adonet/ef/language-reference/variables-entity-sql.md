---
title: Variablen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: 5be9c80c2fce877f179d79f6b2c22f11e31e65a0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248691"
---
# <a name="variables-entity-sql"></a>Variablen (Entity SQL)
## <a name="variable"></a>Variable  
 Ein Variablenausdruck ist ein Verweis auf einen im aktuellen Bereich definierten benannten Ausdruck. Ein Variablen Verweis muss ein gültiger [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Bezeichner sein, wie er in [Bezeichnern](identifiers-entity-sql.md)definiert ist.  
  
 Im folgenden Beispiel wird die Verwendung einer Variablen im Ausdruck dargestellt. Der Buchstabe `c` in der FROM-Klausel ist die Definition der Variablen. Die Verwendung von `c` in der SELECT-Klausel stellt den Variablenverweis dar.  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a>Siehe auch

- [Identifiers (Bezeichner)](identifiers-entity-sql.md)
- [Parameter](parameters-entity-sql.md)
- [Übersicht über Entity SQL](entity-sql-overview.md)
