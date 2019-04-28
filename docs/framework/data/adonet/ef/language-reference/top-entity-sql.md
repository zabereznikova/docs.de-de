---
title: TOP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
ms.openlocfilehash: e7c6cf6b67dc3af29f7ca8fb22af419235a9b833
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879761"
---
# <a name="top-entity-sql"></a><span data-ttu-id="3f72f-102">TOP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3f72f-102">TOP (Entity SQL)</span></span>

<span data-ttu-id="3f72f-103">Der SELECT-Klausel kann hinter dem optionalen ALL/DISTINCT-Modifizierer eine TOP-Unterklausel angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="3f72f-103">The SELECT clause can have an optional TOP sub-clause following the optional ALL/DISTINCT modifier.</span></span> <span data-ttu-id="3f72f-104">Die TOP-Unterklausel gibt an, dass nur der erste Zeilensatz aus dem Abfrageergebnis zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3f72f-104">The TOP sub-clause specifies that only the first set of rows will be returned from the query result.</span></span>

## <a name="syntax"></a><span data-ttu-id="3f72f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f72f-105">Syntax</span></span>

```
[ TOP (n) ]
```

## <a name="arguments"></a><span data-ttu-id="3f72f-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="3f72f-106">Arguments</span></span>

<span data-ttu-id="3f72f-107">`n` Der numerische Ausdruck, der die Anzahl der zurückzugebenden Zeilen angibt.</span><span class="sxs-lookup"><span data-stu-id="3f72f-107">`n` The numeric expression that specifies the number of rows to be returned.</span></span> <span data-ttu-id="3f72f-108">`n` könnte ein einzelnes numerisches Literal oder ein einzelner Parameter sein.</span><span class="sxs-lookup"><span data-stu-id="3f72f-108">`n` could be a single numeric literal or a single parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="3f72f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3f72f-109">Remarks</span></span>

<span data-ttu-id="3f72f-110">Beim TOP-Ausdruck muss es sich entweder um ein einzelnes numerisches Literal oder um einen einzelnen Parameter handeln.</span><span class="sxs-lookup"><span data-stu-id="3f72f-110">The TOP expression must be either a single numeric literal or a single parameter.</span></span> <span data-ttu-id="3f72f-111">Wenn ein konstantes Literal verwendet wird, muss der Literaltyp implizit zu „Edm.Int64“ heraufstufbar sein („byte“, „int16“, „int32“ oder „int64“ oder ein Anbietertyp, der einem zu „Edm.Int64“ heraufstufbaren Typ zugeordnet wird) und über einen Wert verfügen, der größer oder gleich null ist.</span><span class="sxs-lookup"><span data-stu-id="3f72f-111">If a constant literal is used, the literal type must be implicitly promotable to Edm.Int64 (byte, int16, int32 or int64 or any provider type that maps to a type that is promotable to Edm.Int64) and its value must be greater than or equal to zero.</span></span> <span data-ttu-id="3f72f-112">Andernfalls wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="3f72f-112">Otherwise an exception will be raised.</span></span> <span data-ttu-id="3f72f-113">Wird ein Parameter als Ausdruck verwendet, muss der Parametertyp ebenfalls implizit zu „Edm.Int64“ heraufstufbar sein. Es wird jedoch während der Kompilierung keine Überprüfung des tatsächlichen Parameterwerts durchgeführt, da die Parameterwerte spät gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="3f72f-113">If a parameter is used as an expression, the parameter type must also be implicitly promotable to Edm.Int64, but there will be no validation of the actual parameter value during compilation because the parameter values are late bounded.</span></span>

<span data-ttu-id="3f72f-114">Im Folgenden finden Sie ein Beispiel für einen konstanten TOP-Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="3f72f-114">The following is an example of constant TOP expression:</span></span>

```sql
select distinct top(10) c.a1, c.a2 from T as a
```

<span data-ttu-id="3f72f-115">Im folgenden finden ein Beispiel für parametrisierten TOP-Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="3f72f-115">The following is an example of parameterized TOP expression:</span></span>

```sql
select distinct top(@topParam) c.a1, c.a2 from T as a
```

<span data-ttu-id="3f72f-116">Wenn die Abfrage nicht sortiert ist, ist TOP nicht deterministisch.</span><span class="sxs-lookup"><span data-stu-id="3f72f-116">TOP is non-deterministic unless the query is sorted.</span></span> <span data-ttu-id="3f72f-117">Wenn ein deterministisches Ergebnis benötigt wird, sollte die [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) -Unterklausel und die [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) -Unterklausel in der [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) -Klausel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f72f-117">If you require a deterministic result, use the [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses in the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span> <span data-ttu-id="3f72f-118">TOP und SKIP/LIMIT schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="3f72f-118">The TOP and SKIP/LIMIT are mutually exclusive.</span></span>

## <a name="example"></a><span data-ttu-id="3f72f-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3f72f-119">Example</span></span>

<span data-ttu-id="3f72f-120">Die folgende [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage verwendet TOP, um die oberste Zeile, die vom Abfrageergebnis zurückgegeben werden soll, anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3f72f-120">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TOP to specify the top one row to be returned from the query result.</span></span> <span data-ttu-id="3f72f-121">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="3f72f-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3f72f-122">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="3f72f-122">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="3f72f-123">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="3f72f-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="3f72f-124">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="3f72f-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

    [!code-csharp[DP EntityServices Concepts 2#TOP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#top)]

## <a name="see-also"></a><span data-ttu-id="3f72f-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f72f-125">See also</span></span>

- [<span data-ttu-id="3f72f-126">SELECT</span><span class="sxs-lookup"><span data-stu-id="3f72f-126">SELECT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)
- [<span data-ttu-id="3f72f-127">SKIP</span><span class="sxs-lookup"><span data-stu-id="3f72f-127">SKIP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)
- [<span data-ttu-id="3f72f-128">LIMIT</span><span class="sxs-lookup"><span data-stu-id="3f72f-128">LIMIT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)
- [<span data-ttu-id="3f72f-129">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="3f72f-129">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- [<span data-ttu-id="3f72f-130">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="3f72f-130">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
