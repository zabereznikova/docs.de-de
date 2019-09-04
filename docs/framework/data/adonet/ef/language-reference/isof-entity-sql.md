---
title: ISOF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: 3b746a82f72fc7f42f9d91ddd0a7d6f4f86ac0bb
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250575"
---
# <a name="isof-entity-sql"></a><span data-ttu-id="ab536-102">ISOF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ab536-102">ISOF (Entity SQL)</span></span>
<span data-ttu-id="ab536-103">Ermittelt, ob der Typ eines Ausdrucks vom angegebenen Typ oder einem seiner Untertypen ist.</span><span class="sxs-lookup"><span data-stu-id="ab536-103">Determines whether the type of an expression is of the specified type or one of its subtypes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab536-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab536-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="ab536-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="ab536-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ab536-106">Ein gültiger Abfrageausdruck, dessen Typ bestimmt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ab536-106">Any valid query expression to determine the type of.</span></span>  
  
 <span data-ttu-id="ab536-107">NICHT</span><span class="sxs-lookup"><span data-stu-id="ab536-107">NOT</span></span>  
 <span data-ttu-id="ab536-108">Negiert das EDM.Boolean-Ergebnis von IS OF.</span><span class="sxs-lookup"><span data-stu-id="ab536-108">Negates the EDM.Boolean result of IS OF.</span></span>  
  
 <span data-ttu-id="ab536-109">ONLY</span><span class="sxs-lookup"><span data-stu-id="ab536-109">ONLY</span></span>  
 <span data-ttu-id="ab536-110">Legt fest, dass von IS OF`true` nur dann `expression` zurückgegeben wird, wenn `type` vom Typ  und nicht von einem seiner Untertypen ist.</span><span class="sxs-lookup"><span data-stu-id="ab536-110">Specifies that IS OF returns `true` only if `expression` is of type `type` and not any of one its subtypes.</span></span>  
  
 `type`  
 <span data-ttu-id="ab536-111">Der Typ, dessen Übereinstimmung mit dem Typ von `expression` überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="ab536-111">The type to test `expression` against.</span></span> <span data-ttu-id="ab536-112">Der Typ muss mit einem Namespace qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="ab536-112">The type must be namespace-qualified.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab536-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ab536-113">Return Value</span></span>  
 <span data-ttu-id="ab536-114">`true`, wenn `expression` vom Typ "T" und "T" entweder ein Basistyp oder ein von `type` abgeleiteter Typ ist. NULL, wenn `expression` zur Laufzeit den Wert NULL hat, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="ab536-114">`true` if `expression` is of type T and T is either a base type, or a derived type of `type`; null if `expression` is null at runtime; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab536-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ab536-115">Remarks</span></span>  
 <span data-ttu-id="ab536-116">Die Ausdrücke `expression IS NOT OF (type)` und `expression IS NOT OF (ONLY type)` `NOT (expression IS OF (type))` sind`NOT (expression IS OF (ONLY type))`syntaktisch Äquivalent zu bzw.</span><span class="sxs-lookup"><span data-stu-id="ab536-116">The expressions `expression IS NOT OF (type)` and `expression IS NOT OF (ONLY type)` are syntactically equivalent to `NOT (expression IS OF (type))` and `NOT (expression IS OF (ONLY type))`, respectively.</span></span>  
  
 <span data-ttu-id="ab536-117">In der folgenden Tabelle wird das Verhalten des `IS OF`-Operators für einige typische und weniger typische Muster dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ab536-117">The following table shows the behavior of `IS OF` operator over some typical- and corner patterns.</span></span> <span data-ttu-id="ab536-118">Alle Ausnahmen werden von der Clientseite ausgelöst, bevor der Anbieter aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="ab536-118">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="ab536-119">Muster</span><span class="sxs-lookup"><span data-stu-id="ab536-119">Pattern</span></span>|<span data-ttu-id="ab536-120">Verhalten</span><span class="sxs-lookup"><span data-stu-id="ab536-120">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="ab536-121">null IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="ab536-121">null IS OF (EntityType)</span></span>|<span data-ttu-id="ab536-122">Löst aus</span><span class="sxs-lookup"><span data-stu-id="ab536-122">Throws</span></span>|  
|<span data-ttu-id="ab536-123">null IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="ab536-123">null IS OF (ComplexType)</span></span>|<span data-ttu-id="ab536-124">Löst aus</span><span class="sxs-lookup"><span data-stu-id="ab536-124">Throws</span></span>|  
|<span data-ttu-id="ab536-125">null IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="ab536-125">null IS OF (RowType)</span></span>|<span data-ttu-id="ab536-126">Löst aus</span><span class="sxs-lookup"><span data-stu-id="ab536-126">Throws</span></span>|  
|<span data-ttu-id="ab536-127">TREAT (null AS EntityType) IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="ab536-127">TREAT (null AS EntityType) IS OF (EntityType)</span></span>|<span data-ttu-id="ab536-128">Gibt DBNull zurück.</span><span class="sxs-lookup"><span data-stu-id="ab536-128">Returns DBNull</span></span>|  
|<span data-ttu-id="ab536-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="ab536-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span></span>|<span data-ttu-id="ab536-130">Löst aus</span><span class="sxs-lookup"><span data-stu-id="ab536-130">Throws</span></span>|  
|<span data-ttu-id="ab536-131">TREAT (null AS RowType) IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="ab536-131">TREAT (null AS RowType) IS OF (RowType)</span></span>|<span data-ttu-id="ab536-132">Löst aus</span><span class="sxs-lookup"><span data-stu-id="ab536-132">Throws</span></span>|  
|<span data-ttu-id="ab536-133">EntityType IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="ab536-133">EntityType IS OF (EntityType)</span></span>|<span data-ttu-id="ab536-134">Gibt True/False zurück.</span><span class="sxs-lookup"><span data-stu-id="ab536-134">Returns true/false</span></span>|  
|<span data-ttu-id="ab536-135">ComplexType IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="ab536-135">ComplexType IS OF (ComplexType)</span></span>|<span data-ttu-id="ab536-136">Löst aus</span><span class="sxs-lookup"><span data-stu-id="ab536-136">Throws</span></span>|  
|<span data-ttu-id="ab536-137">RowType IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="ab536-137">RowType IS OF (RowType)</span></span>|<span data-ttu-id="ab536-138">Löst aus</span><span class="sxs-lookup"><span data-stu-id="ab536-138">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ab536-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ab536-139">Example</span></span>  
 <span data-ttu-id="ab536-140">In der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] folgenden-Abfrage wird der is of-Operator verwendet, um den Typ eines Abfrage Ausdrucks zu ermitteln. Anschließend wird der Treat-Operator verwendet, um ein Objekt des Typs "Kurs" in eine Auflistung von Objekten des Typs "OnsiteCourse" zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ab536-140">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS OF operator to determine the type of a query expression, and then uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="ab536-141">Die Abfrage basiert auf dem [Modell "School"](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ab536-141">The query is based on the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a><span data-ttu-id="ab536-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab536-142">See also</span></span>

- [<span data-ttu-id="ab536-143">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="ab536-143">Entity SQL Reference</span></span>](entity-sql-reference.md)
