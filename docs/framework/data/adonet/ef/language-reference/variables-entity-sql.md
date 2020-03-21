---
title: Variablen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: 88ee41bc08711cf84b8b2e273c9ac0f4267d1d34
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149816"
---
# <a name="variables-entity-sql"></a>Variablen (Entity SQL)
## <a name="variable"></a>Variable  
 Ein Variablenausdruck ist ein Verweis auf einen im aktuellen Bereich definierten benannten Ausdruck. Ein Variablenverweis muss [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ein gültiger Bezeichner sein, wie in [Identifiers](identifiers-entity-sql.md)definiert.  
  
 Im folgenden Beispiel wird die Verwendung einer Variablen im Ausdruck dargestellt. Der Buchstabe  in der FROM-Klausel ist die Definition der Variablen. Die Verwendung von  in der SELECT-Klausel stellt den Variablenverweis dar.  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Identifiers (Bezeichner)](identifiers-entity-sql.md)
- [Parameter](parameters-entity-sql.md)
- [Übersicht über Entity SQL](entity-sql-overview.md)
