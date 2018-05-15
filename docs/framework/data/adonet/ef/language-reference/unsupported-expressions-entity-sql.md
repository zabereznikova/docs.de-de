---
title: Nicht unterstützte Ausdrücke (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: 6d1746bb51af4795f09c47f808cf9a29d0370f18
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="unsupported-expressions"></a><span data-ttu-id="272ee-102">Nicht unterstützte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="272ee-102">Unsupported expressions</span></span>

<span data-ttu-id="272ee-103">In diesem Thema werden die [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]-Ausdrücke beschrieben, die in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="272ee-103">This topic describes [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="272ee-104">Weitere Informationen finden Sie unter [wie Entity SQL unterscheidet sich von Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="272ee-104">For more information, see [How Entity SQL Differs from Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="272ee-105">Quantifizierte Prädikate</span><span class="sxs-lookup"><span data-stu-id="272ee-105">Quantified predicates</span></span>

<span data-ttu-id="272ee-106">In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] sind Konstrukte der folgenden Form zulässig:</span><span class="sxs-lookup"><span data-stu-id="272ee-106">[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="272ee-107"> unterstützt solche Konstrukte jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="272ee-107">, however, does not support such constructs.</span></span> <span data-ttu-id="272ee-108">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] können gleichwertige Ausdrücke wie folgt geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="272ee-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal > e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="272ee-109">\*-Operator</span><span class="sxs-lookup"><span data-stu-id="272ee-109">\* operator</span></span>

[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="272ee-110"> unterstützt die Verwendung des "\*"-Operators in der SELECT-Klausel, um anzugeben, dass alle Spalten herausprojiziert werden sollen. Dies wird in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="272ee-110"> supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="272ee-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="272ee-111">See also</span></span>

[<span data-ttu-id="272ee-112">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="272ee-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
[<span data-ttu-id="272ee-113">Unterschiede zwischen Entity SQL und Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="272ee-113">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)  
