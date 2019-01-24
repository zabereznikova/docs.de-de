---
title: Nicht unterstützte Ausdrücke (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: a47ff46ca99a84500bc5dfecc19bb31652e9b4b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628019"
---
# <a name="unsupported-expressions"></a>Nicht unterstützte Ausdrücke

In diesem Thema werden die [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]-Ausdrücke beschrieben, die in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nicht unterstützt werden. Weitere Informationen finden Sie unter [wie Entity SQL unterscheidet sich von Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).

## <a name="quantified-predicates"></a>Quantifizierte Prädikate

In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] sind Konstrukte der folgenden Form zulässig:

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

[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] unterstützt die Verwendung des "*"-Operators in der SELECT-Klausel, um anzugeben, dass alle Spalten herausprojiziert werden sollen. Dies wird in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nicht unterstützt.

## <a name="see-also"></a>Siehe auch

- [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [Unterschiede zwischen Entity SQL und Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
