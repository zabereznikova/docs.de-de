---
title: Nicht unterstützte Ausdrücke (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: af0e00f470584883b6a65b63f2650c1c359b404c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489861"
---
# <a name="unsupported-expressions"></a><span data-ttu-id="effc9-102">Nicht unterstützte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="effc9-102">Unsupported expressions</span></span>

<span data-ttu-id="effc9-103">Dieses Thema beschreibt die Transact-SQL-Ausdrücke, die nicht unterstützt werden [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="effc9-103">This topic describes Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="effc9-104">Weitere Informationen finden Sie unter [wie Entity SQL unterscheidet sich von Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="effc9-104">For more information, see [How Entity SQL Differs from Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="effc9-105">Quantifizierte Prädikate</span><span class="sxs-lookup"><span data-stu-id="effc9-105">Quantified predicates</span></span>

<span data-ttu-id="effc9-106">Transact-SQL können Konstrukte der folgenden Form:</span><span class="sxs-lookup"><span data-stu-id="effc9-106">Transact-SQL allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="effc9-107">unterstützt solche Konstrukte jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="effc9-107">, however, does not support such constructs.</span></span> <span data-ttu-id="effc9-108">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] können gleichwertige Ausdrücke wie folgt geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="effc9-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="effc9-109">\*-Operator</span><span class="sxs-lookup"><span data-stu-id="effc9-109">\* operator</span></span>

<span data-ttu-id="effc9-110">Transact-SQL unterstützt die Verwendung der \*-Operator in der SELECT-Klausel, um anzugeben, dass alle Spalten herausprojiziert werden sollen. Dies wird in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="effc9-110">Transact-SQL supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="effc9-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="effc9-111">See also</span></span>

- [<span data-ttu-id="effc9-112">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="effc9-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="effc9-113">Unterschiede zwischen Entity SQL und Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="effc9-113">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
