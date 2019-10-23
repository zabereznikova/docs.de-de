---
title: Variablen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: bb8e6ebe81dacc7ec0f45fdde65b9c18cfd76789
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319200"
---
# <a name="variables-entity-sql"></a>Variablen (Entity SQL)
## <a name="variable"></a>Variable  
 Ein Variablenausdruck ist ein Verweis auf einen im aktuellen Bereich definierten benannten Ausdruck. Ein Variablen Verweis muss ein gültiger [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Bezeichner sein, wie [er in Bezeichnern](identifiers-entity-sql.md)definiert ist.  
  
 Im folgenden Beispiel wird die Verwendung einer Variablen im Ausdruck dargestellt. Der Buchstabe `c` in der FROM-Klausel ist die Definition der Variablen. Die Verwendung von `c` in der SELECT-Klausel stellt den Variablenverweis dar.  
  
```sql  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a>Siehe auch

- [Identifiers (Bezeichner)](identifiers-entity-sql.md)
- [Parameter](parameters-entity-sql.md)
- [Übersicht über Entity SQL](entity-sql-overview.md)
