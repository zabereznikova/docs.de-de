---
title: Nicht unterstützte Ausdrücke (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: 956fe117eb0c59392c3999046bc70deaed268ac6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248778"
---
# <a name="unsupported-expressions"></a>Nicht unterstützte Ausdrücke

In diesem Thema werden Transact-SQL-Ausdrücke beschrieben, die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]in nicht unterstützt werden. Weitere Informationen finden Sie unter Unterschiede [zwischen Entity SQL und Transact-SQL](how-entity-sql-differs-from-transact-sql.md).

## <a name="quantified-predicates"></a>Quantifizierte Prädikate

Transact-SQL ermöglicht Konstrukte der folgenden Form:

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt solche Konstrukte jedoch nicht. In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] können gleichwertige Ausdrücke wie folgt geschrieben werden:

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a>*-Operator

Transact-SQL unterstützt die Verwendung des Operators * in der SELECT-Klausel, um anzugeben, dass alle Spalten projiziert werden sollen. Dies wird in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nicht unterstützt.

## <a name="see-also"></a>Siehe auch

- [Übersicht über Entity SQL](entity-sql-overview.md)
- [Unterschiede zwischen Entity SQL und Transact-SQL](how-entity-sql-differs-from-transact-sql.md)
