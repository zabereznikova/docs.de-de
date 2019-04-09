---
title: Kanonische Mathematikfunktionen
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: f575785bb198251ef50ba3563e736946253c9526
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228769"
---
# <a name="math-canonical-functions"></a><span data-ttu-id="6fc88-102">Kanonische Mathematikfunktionen</span><span class="sxs-lookup"><span data-stu-id="6fc88-102">Math Canonical Functions</span></span>

<span data-ttu-id="6fc88-103">Entity SQL enthält die folgenden kanonische mathematische Funktionen:</span><span class="sxs-lookup"><span data-stu-id="6fc88-103">Entity SQL includes the following math canonical functions:</span></span>
  
## <a name="absvalue"></a><span data-ttu-id="6fc88-104">Abs(Wert)</span><span class="sxs-lookup"><span data-stu-id="6fc88-104">Abs(value)</span></span>

<span data-ttu-id="6fc88-105">Gibt den Absolutwert von `value` zurück.</span><span class="sxs-lookup"><span data-stu-id="6fc88-105">Returns the absolute value of `value`.</span></span>

**<span data-ttu-id="6fc88-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="6fc88-106">Arguments</span></span>**

<span data-ttu-id="6fc88-107">Ein `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, und `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6fc88-107">An `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, and `Decimal`.</span></span>

**<span data-ttu-id="6fc88-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6fc88-108">Return Value</span></span>**

<span data-ttu-id="6fc88-109">Der `value`-Typ.</span><span class="sxs-lookup"><span data-stu-id="6fc88-109">The type of `value`.</span></span>

**<span data-ttu-id="6fc88-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6fc88-110">Example</span></span>**

`Abs(-2)`

## <a name="ceilingvalue"></a><span data-ttu-id="6fc88-111">Ceiling (Wert)</span><span class="sxs-lookup"><span data-stu-id="6fc88-111">Ceiling(value)</span></span>

<span data-ttu-id="6fc88-112">Gibt die kleinste ganze Zahl zurück, die nicht kleiner als `value` ist.</span><span class="sxs-lookup"><span data-stu-id="6fc88-112">Returns the smallest integer that is not less than `value`.</span></span>

**<span data-ttu-id="6fc88-113">Argumente</span><span class="sxs-lookup"><span data-stu-id="6fc88-113">Arguments</span></span>**

<span data-ttu-id="6fc88-114">Ein `Single`, `Double`, und `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6fc88-114">A `Single`, `Double`, and `Decimal`.</span></span>

**<span data-ttu-id="6fc88-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6fc88-115">Return Value</span></span>**

<span data-ttu-id="6fc88-116">Der `value`-Typ.</span><span class="sxs-lookup"><span data-stu-id="6fc88-116">The type of `value`.</span></span>

**<span data-ttu-id="6fc88-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6fc88-117">Example</span></span>**

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a><span data-ttu-id="6fc88-118">Floor (Wert)</span><span class="sxs-lookup"><span data-stu-id="6fc88-118">Floor(value)</span></span>

<span data-ttu-id="6fc88-119">Gibt die größte ganze Zahl zurück, die nicht größer als `value` ist.</span><span class="sxs-lookup"><span data-stu-id="6fc88-119">Returns the largest integer that is not greater than `value`.</span></span>

**<span data-ttu-id="6fc88-120">Argumente</span><span class="sxs-lookup"><span data-stu-id="6fc88-120">Arguments</span></span>**

<span data-ttu-id="6fc88-121">Ein `Single`, `Double`, und `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6fc88-121">A `Single`, `Double`, and `Decimal`.</span></span>

**<span data-ttu-id="6fc88-122">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6fc88-122">Return Value</span></span>**

<span data-ttu-id="6fc88-123">Der `value`-Typ.</span><span class="sxs-lookup"><span data-stu-id="6fc88-123">The type of `value`.</span></span>

**<span data-ttu-id="6fc88-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6fc88-124">Example</span></span>**

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a><span data-ttu-id="6fc88-125">Power(Wert, Exponent)</span><span class="sxs-lookup"><span data-stu-id="6fc88-125">Power(value, exponent)</span></span>

<span data-ttu-id="6fc88-126">Gibt das Ergebnis der angegebenen `value` an die angegebene `exponent` zurück.</span><span class="sxs-lookup"><span data-stu-id="6fc88-126">Returns the result of the specified `value` to the specified `exponent`.</span></span>

**<span data-ttu-id="6fc88-127">Argumente</span><span class="sxs-lookup"><span data-stu-id="6fc88-127">Arguments</span></span>**

|  |  |
|--|--|
|`value` | <span data-ttu-id="6fc88-128">Ein `Int32, Int64, Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6fc88-128">An `Int32, Int64, Double`, or `Decimal`.</span></span> |
|`exponent` | <span data-ttu-id="6fc88-129">Ein `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6fc88-129">An `Int64`, `Double`, or `Decimal`.</span></span> |

**<span data-ttu-id="6fc88-130">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6fc88-130">Return Value</span></span>**

<span data-ttu-id="6fc88-131">Der `value`-Typ.</span><span class="sxs-lookup"><span data-stu-id="6fc88-131">The type of `value`.</span></span>

**<span data-ttu-id="6fc88-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6fc88-132">Example</span></span>**

`Power(748.58,2)`

## <a name="roundvalue"></a><span data-ttu-id="6fc88-133">Round (Wert)</span><span class="sxs-lookup"><span data-stu-id="6fc88-133">Round(value)</span></span>

<span data-ttu-id="6fc88-134">Gibt `value` gerundet zur nächsten Ganzzahl zurück.</span><span class="sxs-lookup"><span data-stu-id="6fc88-134">Returns the integer portion of `value`, rounded to the nearest integer.</span></span>

**<span data-ttu-id="6fc88-135">Argumente</span><span class="sxs-lookup"><span data-stu-id="6fc88-135">Arguments</span></span>**

<span data-ttu-id="6fc88-136">Ein `Single`, `Double`, und `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6fc88-136">A `Single`, `Double`, and `Decimal`.</span></span>

**<span data-ttu-id="6fc88-137">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6fc88-137">Return Value</span></span>**

<span data-ttu-id="6fc88-138">Der `value`-Typ.</span><span class="sxs-lookup"><span data-stu-id="6fc88-138">The type of `value`.</span></span>

**<span data-ttu-id="6fc88-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6fc88-139">Example</span></span>**

`Round(748.58)`

## <a name="roundvalue-digits"></a><span data-ttu-id="6fc88-140">Round(Wert, Ziffern)</span><span class="sxs-lookup"><span data-stu-id="6fc88-140">Round(value, digits)</span></span>

<span data-ttu-id="6fc88-141">Gibt den `value` auf die nächstliegenden angegebenen `digits` gerundet zurück.</span><span class="sxs-lookup"><span data-stu-id="6fc88-141">Returns the `value`, rounded to the nearest specified `digits`.</span></span>

**<span data-ttu-id="6fc88-142">Argumente</span><span class="sxs-lookup"><span data-stu-id="6fc88-142">Arguments</span></span>**

|  |  |
|--|--|
|`value`|`Double` <span data-ttu-id="6fc88-143">oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6fc88-143">or `Decimal`.</span></span>|
|`digits`|`Int16` <span data-ttu-id="6fc88-144">oder `Int32`.</span><span class="sxs-lookup"><span data-stu-id="6fc88-144">or `Int32`.</span></span>|

**<span data-ttu-id="6fc88-145">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6fc88-145">Return Value</span></span>**

<span data-ttu-id="6fc88-146">Der `value`-Typ.</span><span class="sxs-lookup"><span data-stu-id="6fc88-146">The type of `value`.</span></span>

**<span data-ttu-id="6fc88-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6fc88-147">Example</span></span>**

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a><span data-ttu-id="6fc88-148">Truncate(Wert, Ziffern)</span><span class="sxs-lookup"><span data-stu-id="6fc88-148">Truncate(value, digits)</span></span>

<span data-ttu-id="6fc88-149">Gibt den `value` auf die nächstliegenden angegebenen `digits` gekürzt zurück.</span><span class="sxs-lookup"><span data-stu-id="6fc88-149">Returns the `value`, truncated to the nearest specified `digits`.</span></span>

**<span data-ttu-id="6fc88-150">Argumente</span><span class="sxs-lookup"><span data-stu-id="6fc88-150">Arguments</span></span>**

|  |  |
|--|--|
|`value`|`Double` <span data-ttu-id="6fc88-151">oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6fc88-151">or `Decimal`.</span></span>|
|`digits`|`Int16` <span data-ttu-id="6fc88-152">oder `Int32`.</span><span class="sxs-lookup"><span data-stu-id="6fc88-152">or `Int32`.</span></span>|

**<span data-ttu-id="6fc88-153">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6fc88-153">Return Value</span></span>**

<span data-ttu-id="6fc88-154">Der `value`-Typ.</span><span class="sxs-lookup"><span data-stu-id="6fc88-154">The type of `value`.</span></span>

**<span data-ttu-id="6fc88-155">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6fc88-155">Example</span></span>**

`Truncate(748.58,1)`  
  
 <span data-ttu-id="6fc88-156">Diese Funktionen geben `null` zurück, wenn die Eingabe `null` ist.</span><span class="sxs-lookup"><span data-stu-id="6fc88-156">These functions will return `null` if given `null` input.</span></span>  
  
 <span data-ttu-id="6fc88-157">Entsprechende Funktionen sind für den verwalteten Anbieter des Microsoft SQL-Clients verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6fc88-157">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="6fc88-158">Weitere Informationen finden Sie unter [SqlClient für Entity Framework-Funktionen](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="6fc88-158">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fc88-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fc88-159">See also</span></span>

- [<span data-ttu-id="6fc88-160">Kanonische Funktionen</span><span class="sxs-lookup"><span data-stu-id="6fc88-160">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
