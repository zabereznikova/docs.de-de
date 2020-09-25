---
title: ROW (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 06da96e8-55d7-486c-991a-4e514d837ff9
ms.openlocfilehash: 2ab91d0c6d3c3ed3f88a7f0ddbf3a6c2f36d8b04
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202252"
---
# <a name="row-entity-sql"></a><span data-ttu-id="38ca7-102">ROW (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="38ca7-102">ROW (Entity SQL)</span></span>

<span data-ttu-id="38ca7-103">Erstellt anonyme, strukturell typisierte Datensätze aus einem oder mehreren Werten.</span><span class="sxs-lookup"><span data-stu-id="38ca7-103">Constructs anonymous, structurally typed records from one or more values.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38ca7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="38ca7-104">Syntax</span></span>  
  
```sql  
ROW ( expression [ AS alias ] [,...] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="38ca7-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="38ca7-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="38ca7-106">Ein gültiger Abfrageausdruck, der einen Wert zum Erstellen eines Zeilentyps zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="38ca7-106">Any valid query expression that returns a value to construct in a row type.</span></span>  
  
 `alias`  
 <span data-ttu-id="38ca7-107">Gibt einen Alias für den in einem Zeilentyp angegebenen Wert an.</span><span class="sxs-lookup"><span data-stu-id="38ca7-107">Specifies an alias for the value specified in a row type.</span></span> <span data-ttu-id="38ca7-108">Wenn kein Alias angegeben wird, generiert [!INCLUDE[esql](../../../../../../includes/esql-md.md)] mithilfe der Aliasgenerierungsregeln von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] einen Alias.</span><span class="sxs-lookup"><span data-stu-id="38ca7-108">If an alias is not provided, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to generate an alias based on the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] alias generation rules.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38ca7-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="38ca7-109">Return Value</span></span>  

 <span data-ttu-id="38ca7-110">Ein Zeilentyp.</span><span class="sxs-lookup"><span data-stu-id="38ca7-110">A row type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38ca7-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="38ca7-111">Remarks</span></span>  

 <span data-ttu-id="38ca7-112">Zeilenkonstruktoren werden in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zur Erstellung anonymer, strukturell typisierter Datensätze aus einem oder mehreren Werten verwendet.</span><span class="sxs-lookup"><span data-stu-id="38ca7-112">You use row constructors in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to construct anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="38ca7-113">Beim Ergebnistyp eines Zeilenkonstruktors handelt es sich um einen Zeilentyp, dessen Feldtypen den Typen der zur Erstellung der Zeile verwendeten Werten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="38ca7-113">The result type of a row constructor is a row type whose field types correspond to the types of the values that were used to construct the row.</span></span> <span data-ttu-id="38ca7-114">Im folgenden Ausdruck wird beispielsweise ein Wert vom Typ `Record(a int, b string, c int)`erstellt.</span><span class="sxs-lookup"><span data-stu-id="38ca7-114">For example, the following expression constructs a value of type `Record(a int, b string, c int)`.</span></span>  
  
```sql  
ROW(1 AS a, "abc" AS b, a+34 AS c)  
```  
  
 <span data-ttu-id="38ca7-115">Wenn für einen Ausdruck in einem Zeilenkonstruktor kein Alias angegeben ist, wird vom Entity Framework ein Alias generiert.</span><span class="sxs-lookup"><span data-stu-id="38ca7-115">If you do not provide an alias for an expression in a row constructor, the Entity Framework will try to generate one.</span></span> <span data-ttu-id="38ca7-116">Weitere Informationen finden Sie im Abschnitt "Regeln für das Aliasing" im Thema [Bezeichner](identifiers-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="38ca7-116">For more information, see the "Aliasing Rules" section of the [Identifiers](identifiers-entity-sql.md) topic.</span></span>  
  
 <span data-ttu-id="38ca7-117">Die folgenden Regeln gelten für Ausdrucksaliasing in einem Zeilenkonstruktor:</span><span class="sxs-lookup"><span data-stu-id="38ca7-117">The following rules apply to expression aliasing in a row constructor:</span></span>  
  
- <span data-ttu-id="38ca7-118">Ausdrücke in einem Zeilenkonstruktor können nicht auf andere Aliase im gleichen Konstruktor verweisen.</span><span class="sxs-lookup"><span data-stu-id="38ca7-118">Expressions in a row constructor cannot refer to other aliases in the same constructor.</span></span>  
  
- <span data-ttu-id="38ca7-119">Zwei Ausdrücke im gleichen Zeilenkonstruktor können nicht über den gleichen Alias verfügen.</span><span class="sxs-lookup"><span data-stu-id="38ca7-119">Two expressions in the same row constructor cannot have the same alias.</span></span>  
  
 <span data-ttu-id="38ca7-120">Weitere Informationen zu Abfragekonstruktoren finden Sie unter [Konstruieren von Typen](constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="38ca7-120">For more information about query constructors, see [Constructing Types](constructing-types-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="38ca7-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="38ca7-121">Example</span></span>  

 <span data-ttu-id="38ca7-122">In der folgenden Entity SQL-Abfrage wird der ROW-Operator zur Erstellung anonymer, strukturell typisierter Datensätze verwendet.</span><span class="sxs-lookup"><span data-stu-id="38ca7-122">The following Entity SQL query uses the ROW operator to construct anonymous, structurally typed records.</span></span> <span data-ttu-id="38ca7-123">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="38ca7-123">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="38ca7-124">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="38ca7-124">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="38ca7-125">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="38ca7-125">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="38ca7-126">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="38ca7-126">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#ROW](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#row)]  
  
## <a name="see-also"></a><span data-ttu-id="38ca7-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="38ca7-127">See also</span></span>

- [<span data-ttu-id="38ca7-128">Konstruktionstypen</span><span class="sxs-lookup"><span data-stu-id="38ca7-128">Constructing Types</span></span>](constructing-types-entity-sql.md)
- [<span data-ttu-id="38ca7-129">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="38ca7-129">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="38ca7-130">Typdefinitionen</span><span class="sxs-lookup"><span data-stu-id="38ca7-130">Type Definitions</span></span>](type-definitions-entity-sql.md)
