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
# <a name="unsupported-expressions"></a><span data-ttu-id="e0dd3-102">Nicht unterstützte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="e0dd3-102">Unsupported expressions</span></span>

<span data-ttu-id="e0dd3-103">In diesem Thema werden Transact-SQL-Ausdrücke beschrieben, die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]in nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="e0dd3-103">This topic describes Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="e0dd3-104">Weitere Informationen finden Sie unter Unterschiede [zwischen Entity SQL und Transact-SQL](how-entity-sql-differs-from-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="e0dd3-104">For more information, see [How Entity SQL Differs from Transact-SQL](how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="e0dd3-105">Quantifizierte Prädikate</span><span class="sxs-lookup"><span data-stu-id="e0dd3-105">Quantified predicates</span></span>

<span data-ttu-id="e0dd3-106">Transact-SQL ermöglicht Konstrukte der folgenden Form:</span><span class="sxs-lookup"><span data-stu-id="e0dd3-106">Transact-SQL allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e0dd3-107">unterstützt solche Konstrukte jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="e0dd3-107">, however, does not support such constructs.</span></span> <span data-ttu-id="e0dd3-108">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] können gleichwertige Ausdrücke wie folgt geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="e0dd3-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="e0dd3-109">\*-Operator</span><span class="sxs-lookup"><span data-stu-id="e0dd3-109">\* operator</span></span>

<span data-ttu-id="e0dd3-110">Transact-SQL unterstützt die Verwendung des Operators \* in der SELECT-Klausel, um anzugeben, dass alle Spalten projiziert werden sollen. Dies wird in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e0dd3-110">Transact-SQL supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="e0dd3-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0dd3-111">See also</span></span>

- [<span data-ttu-id="e0dd3-112">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e0dd3-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="e0dd3-113">Unterschiede zwischen Entity SQL und Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e0dd3-113">How Entity SQL Differs from Transact-SQL</span></span>](how-entity-sql-differs-from-transact-sql.md)
