---
title: ISOF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: 3cbbc9b6feda1bde104ed2c95d4dca274b090028
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202278"
---
# <a name="isof-entity-sql"></a><span data-ttu-id="2f406-102">ISOF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2f406-102">ISOF (Entity SQL)</span></span>

<span data-ttu-id="2f406-103">Ermittelt, ob der Typ eines Ausdrucks vom angegebenen Typ oder einem seiner Untertypen ist.</span><span class="sxs-lookup"><span data-stu-id="2f406-103">Determines whether the type of an expression is of the specified type or one of its subtypes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f406-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f406-104">Syntax</span></span>  
  
```sql  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="2f406-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="2f406-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="2f406-106">Ein gültiger Abfrageausdruck, dessen Typ bestimmt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f406-106">Any valid query expression to determine the type of.</span></span>  
  
 <span data-ttu-id="2f406-107">NICHT</span><span class="sxs-lookup"><span data-stu-id="2f406-107">NOT</span></span>  
 <span data-ttu-id="2f406-108">Negiert das EDM.Boolean-Ergebnis von IS OF.</span><span class="sxs-lookup"><span data-stu-id="2f406-108">Negates the EDM.Boolean result of IS OF.</span></span>  
  
 <span data-ttu-id="2f406-109">ONLY</span><span class="sxs-lookup"><span data-stu-id="2f406-109">ONLY</span></span>  
 <span data-ttu-id="2f406-110">Legt fest, dass von IS OF nur dann  zurückgegeben wird, wenn  vom Typ  und nicht von einem seiner Untertypen ist.</span><span class="sxs-lookup"><span data-stu-id="2f406-110">Specifies that IS OF returns `true` only if `expression` is of type `type` and not any of one its subtypes.</span></span>  
  
 `type`  
 <span data-ttu-id="2f406-111">Der Typ, dessen Übereinstimmung mit dem Typ von `expression` überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f406-111">The type to test `expression` against.</span></span> <span data-ttu-id="2f406-112">Der Typ muss mit einem Namespace qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="2f406-112">The type must be namespace-qualified.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f406-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2f406-113">Return Value</span></span>  

 <span data-ttu-id="2f406-114">`true`, wenn `expression` vom Typ "T" und "T" entweder ein Basistyp oder ein von `type` abgeleiteter Typ ist. NULL, wenn `expression` zur Laufzeit den Wert NULL hat, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="2f406-114">`true` if `expression` is of type T and T is either a base type, or a derived type of `type`; null if `expression` is null at runtime; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f406-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2f406-115">Remarks</span></span>  

 <span data-ttu-id="2f406-116">Die Ausdrücke `expression IS NOT OF (type)` und `expression IS NOT OF (ONLY type)` sind syntaktisch Äquivalent zu `NOT (expression IS OF (type))` `NOT (expression IS OF (ONLY type))` bzw..</span><span class="sxs-lookup"><span data-stu-id="2f406-116">The expressions `expression IS NOT OF (type)` and `expression IS NOT OF (ONLY type)` are syntactically equivalent to `NOT (expression IS OF (type))` and `NOT (expression IS OF (ONLY type))`, respectively.</span></span>  
  
 <span data-ttu-id="2f406-117">In der folgenden Tabelle wird das Verhalten des `IS OF`-Operators für einige typische und weniger typische Muster dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2f406-117">The following table shows the behavior of `IS OF` operator over some typical- and corner patterns.</span></span> <span data-ttu-id="2f406-118">Alle Ausnahmen werden von der Clientseite ausgelöst, bevor der Anbieter aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="2f406-118">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="2f406-119">Muster</span><span class="sxs-lookup"><span data-stu-id="2f406-119">Pattern</span></span>|<span data-ttu-id="2f406-120">Verhalten</span><span class="sxs-lookup"><span data-stu-id="2f406-120">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="2f406-121">null IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="2f406-121">null IS OF (EntityType)</span></span>|<span data-ttu-id="2f406-122">Löst aus</span><span class="sxs-lookup"><span data-stu-id="2f406-122">Throws</span></span>|  
|<span data-ttu-id="2f406-123">null IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="2f406-123">null IS OF (ComplexType)</span></span>|<span data-ttu-id="2f406-124">Löst aus</span><span class="sxs-lookup"><span data-stu-id="2f406-124">Throws</span></span>|  
|<span data-ttu-id="2f406-125">null IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="2f406-125">null IS OF (RowType)</span></span>|<span data-ttu-id="2f406-126">Löst aus</span><span class="sxs-lookup"><span data-stu-id="2f406-126">Throws</span></span>|  
|<span data-ttu-id="2f406-127">TREAT (null AS EntityType) IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="2f406-127">TREAT (null AS EntityType) IS OF (EntityType)</span></span>|<span data-ttu-id="2f406-128">Gibt DBNull zurück.</span><span class="sxs-lookup"><span data-stu-id="2f406-128">Returns DBNull</span></span>|  
|<span data-ttu-id="2f406-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="2f406-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span></span>|<span data-ttu-id="2f406-130">Löst aus</span><span class="sxs-lookup"><span data-stu-id="2f406-130">Throws</span></span>|  
|<span data-ttu-id="2f406-131">TREAT (null AS RowType) IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="2f406-131">TREAT (null AS RowType) IS OF (RowType)</span></span>|<span data-ttu-id="2f406-132">Löst aus</span><span class="sxs-lookup"><span data-stu-id="2f406-132">Throws</span></span>|  
|<span data-ttu-id="2f406-133">EntityType IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="2f406-133">EntityType IS OF (EntityType)</span></span>|<span data-ttu-id="2f406-134">Gibt True/False zurück.</span><span class="sxs-lookup"><span data-stu-id="2f406-134">Returns true/false</span></span>|  
|<span data-ttu-id="2f406-135">ComplexType IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="2f406-135">ComplexType IS OF (ComplexType)</span></span>|<span data-ttu-id="2f406-136">Löst aus</span><span class="sxs-lookup"><span data-stu-id="2f406-136">Throws</span></span>|  
|<span data-ttu-id="2f406-137">RowType IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="2f406-137">RowType IS OF (RowType)</span></span>|<span data-ttu-id="2f406-138">Löst aus</span><span class="sxs-lookup"><span data-stu-id="2f406-138">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2f406-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2f406-139">Example</span></span>  

 <span data-ttu-id="2f406-140">In der folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage wird der is of-Operator verwendet, um den Typ eines Abfrage Ausdrucks zu ermitteln. Anschließend wird der Treat-Operator verwendet, um ein Objekt des Typs "Kurs" in eine Auflistung von Objekten des Typs "OnsiteCourse" zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="2f406-140">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS OF operator to determine the type of a query expression, and then uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="2f406-141">Die Abfrage basiert auf dem [Modell "School"](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="2f406-141">The query is based on the [School Model](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 <span data-ttu-id="2f406-142">[! Code-SQL [DP entityservices Concepts # TREAT_ISOF] ~/Samples/Snippets/TSQL/VS_Snippets_Data/DP entityservices Concepts/TQL/EntitySql. SQL # treat_isof)]</span><span class="sxs-lookup"><span data-stu-id="2f406-142">[!code-sql[DP EntityServices Concepts#TREAT_ISOF]~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#treat_isof)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f406-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f406-143">See also</span></span>

- [<span data-ttu-id="2f406-144">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="2f406-144">Entity SQL Reference</span></span>](entity-sql-reference.md)
