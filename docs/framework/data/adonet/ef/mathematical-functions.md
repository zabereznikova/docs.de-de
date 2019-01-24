---
title: Mathematische Funktionen
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: d8d766cb1416a9a07476175364fe568d81fd9b25
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652266"
---
# <a name="mathematical-functions"></a><span data-ttu-id="40a83-102">Mathematische Funktionen</span><span class="sxs-lookup"><span data-stu-id="40a83-102">Mathematical Functions</span></span>

<span data-ttu-id="40a83-103">Der .NET Framework-Datenanbieter für SQL Server (SqlClient) stellt mathematische Funktionen bereit, die Berechnungen für als Argumente bereitgestellte Eingabewerte durchführen und einen numerischen Wert als Ergebnis zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="40a83-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="40a83-104">Diese Funktionen befinden sich im SQLServer-Namespace, der bei der Verwendung von SqlClient verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="40a83-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="40a83-105">Anhand der Namespaceigenschaft des Anbieters kann Entity Framework ermitteln, welches Präfix von diesem Anbieter für spezifische Konstrukte, wie Typen und Funktionen, verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="40a83-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="40a83-106">Die folgende Tabelle beschreibt die SqlClient mathematischen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="40a83-106">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="40a83-107">Abs(Expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-107">ABS(expression)</span></span>

<span data-ttu-id="40a83-108">Führt die Absolutwertfunktion aus.</span><span class="sxs-lookup"><span data-stu-id="40a83-108">Performs the absolute value function.</span></span>

<span data-ttu-id="40a83-109">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-109">**Arguments**</span></span>

<span data-ttu-id="40a83-110">`expression`: Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="40a83-110">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="40a83-111">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-111">**Return Value**</span></span>

<span data-ttu-id="40a83-112">Der Absolutwert des angegebenen Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="40a83-112">The absolute value of the specified expression.</span></span>

<span data-ttu-id="40a83-113">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-113">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="40a83-114">ACOS(Expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-114">ACOS(expression)</span></span>

<span data-ttu-id="40a83-115">Gibt den Arkuskosinuswert des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="40a83-115">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="40a83-116">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-116">**Arguments**</span></span>

<span data-ttu-id="40a83-117">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-117">`expression`: A `Double`.</span></span>

<span data-ttu-id="40a83-118">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-118">**Return Value**</span></span>

<span data-ttu-id="40a83-119">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-119">A `Double`.</span></span>

<span data-ttu-id="40a83-120">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-120">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="40a83-121">ASIN(expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-121">ASIN(expression)</span></span>

<span data-ttu-id="40a83-122">Gibt den Arkussinuswert des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="40a83-122">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="40a83-123">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-123">**Arguments**</span></span>

<span data-ttu-id="40a83-124">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-124">`expression`: A `Double`.</span></span>

<span data-ttu-id="40a83-125">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-125">**Return Value**</span></span>

<span data-ttu-id="40a83-126">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-126">A `Double`.</span></span>

<span data-ttu-id="40a83-127">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-127">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="40a83-128">Atan(Expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-128">ATAN(expression)</span></span>

<span data-ttu-id="40a83-129">Gibt den Arkustangens-Wert des angegebenen numerischen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="40a83-129">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="40a83-130">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-130">**Arguments**</span></span>

<span data-ttu-id="40a83-131">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-131">`expression`: A `Double`.</span></span>

<span data-ttu-id="40a83-132">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-132">**Return Value**</span></span>

<span data-ttu-id="40a83-133">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-133">A `Double`.</span></span>

<span data-ttu-id="40a83-134">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-134">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="40a83-135">ATN2(expression, expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-135">ATN2(expression, expression)</span></span>

<span data-ttu-id="40a83-136">Gibt den Winkel im Bogenmaß (Radiant) zurück, dessen Tangens zwischen den beiden angegebenen numerischen Ausdrücken liegt.</span><span class="sxs-lookup"><span data-stu-id="40a83-136">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="40a83-137">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-137">**Arguments**</span></span>

<span data-ttu-id="40a83-138">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-138">`expression`: A `Double`.</span></span>

<span data-ttu-id="40a83-139">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-139">**Return Value**</span></span>

<span data-ttu-id="40a83-140">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-140">A `Double`.</span></span>

<span data-ttu-id="40a83-141">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-141">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="40a83-142">CEILING(expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-142">CEILING(expression)</span></span>

<span data-ttu-id="40a83-143">Konvertiert den angegebenen Ausdruck zur kleinsten Ganzzahl, die größer als oder gleich dem Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="40a83-143">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="40a83-144">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-144">**Arguments**</span></span>

<span data-ttu-id="40a83-145">`expression`: Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="40a83-145">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="40a83-146">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-146">**Return Value**</span></span>

<span data-ttu-id="40a83-147">Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="40a83-147">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="40a83-148">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-148">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="40a83-149">COS(Expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-149">COS(expression)</span></span>

<span data-ttu-id="40a83-150">Berechnet den trigonometrischen Kosinus des im Bogenmaß angegebenen Winkels.</span><span class="sxs-lookup"><span data-stu-id="40a83-150">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="40a83-151">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-151">**Arguments**</span></span> 

<span data-ttu-id="40a83-152">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-152">`expression`: A `Double`.</span></span> 

<span data-ttu-id="40a83-153">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-153">**Return Value**</span></span> 

<span data-ttu-id="40a83-154">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-154">A `Double`.</span></span> 

<span data-ttu-id="40a83-155">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-155">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="40a83-156">COT(Expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-156">COT(expression)</span></span>

<span data-ttu-id="40a83-157">Berechnet den trigonometrischen Kotangens des im Bogenmaß angegebenen Winkels.</span><span class="sxs-lookup"><span data-stu-id="40a83-157">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="40a83-158">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-158">**Arguments**</span></span> 

<span data-ttu-id="40a83-159">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-159">`expression`: A `Double`.</span></span> 

<span data-ttu-id="40a83-160">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-160">**Return Value**</span></span> 

<span data-ttu-id="40a83-161">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-161">A `Double`.</span></span> 

<span data-ttu-id="40a83-162">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-162">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="40a83-163">DEGREES(RADIANS)</span><span class="sxs-lookup"><span data-stu-id="40a83-163">DEGREES(radians)</span></span>

<span data-ttu-id="40a83-164">Gibt den entsprechenden Winkel in Grad zurück.</span><span class="sxs-lookup"><span data-stu-id="40a83-164">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="40a83-165">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-165">**Arguments**</span></span> 

<span data-ttu-id="40a83-166">`expression`: Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="40a83-166">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="40a83-167">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-167">**Return Value**</span></span> 

<span data-ttu-id="40a83-168">Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="40a83-168">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="40a83-169">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-169">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="40a83-170">EXP(Expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-170">EXP(expression)</span></span>

<span data-ttu-id="40a83-171">Berechnet den Exponentialwert des angegebenen numerischen Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="40a83-171">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="40a83-172">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-172">**Arguments**</span></span> 

<span data-ttu-id="40a83-173">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-173">`expression`: A `Double`.</span></span> 

<span data-ttu-id="40a83-174">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-174">**Return Value**</span></span> 

<span data-ttu-id="40a83-175">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-175">A `Double`.</span></span> 

<span data-ttu-id="40a83-176">**Beispiel** `SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="40a83-176">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="40a83-177">Floor(Expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-177">FLOOR(expression)</span></span>

<span data-ttu-id="40a83-178">Konvertiert den angegebenen Ausdruck zur größten Ganzzahl, die kleiner als oder gleich dem angegebenen numerischen Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="40a83-178">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="40a83-179">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-179">**Arguments**</span></span> 

<span data-ttu-id="40a83-180">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-180">`expression`: A `Double`.</span></span> 

<span data-ttu-id="40a83-181">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-181">**Return Value**</span></span> 

<span data-ttu-id="40a83-182">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-182">A `Double`.</span></span> 

<span data-ttu-id="40a83-183">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-183">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="40a83-184">Log(Expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-184">LOG(expression)</span></span>

<span data-ttu-id="40a83-185">Berechnet den natürlichen Logarithmus des angegebenen `float`-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="40a83-185">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="40a83-186">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-186">**Arguments**</span></span> 

<span data-ttu-id="40a83-187">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-187">`expression`: A `Double`.</span></span> 

<span data-ttu-id="40a83-188">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-188">**Return Value**</span></span> 

<span data-ttu-id="40a83-189">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-189">A `Double`.</span></span> 

<span data-ttu-id="40a83-190">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-190">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="40a83-191">LOG10(expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-191">LOG10(expression)</span></span>

<span data-ttu-id="40a83-192">Gibt den Logarithmus zur Basis 10 des angegebenen `Double`-Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="40a83-192">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="40a83-193">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-193">**Arguments**</span></span> 

<span data-ttu-id="40a83-194">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-194">`expression`: A `Double`.</span></span> 

<span data-ttu-id="40a83-195">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-195">**Return Value**</span></span> 

<span data-ttu-id="40a83-196">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-196">A `Double`.</span></span> 

<span data-ttu-id="40a83-197">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-197">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="40a83-198">PI()</span><span class="sxs-lookup"><span data-stu-id="40a83-198">PI()</span></span>

<span data-ttu-id="40a83-199">Gibt den konstanten Wert von Pi als `Double`-Typ zurück.</span><span class="sxs-lookup"><span data-stu-id="40a83-199">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="40a83-200">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-200">**Return Value**</span></span> 

<span data-ttu-id="40a83-201">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-201">A `Double`.</span></span> 

<span data-ttu-id="40a83-202">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-202">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a><span data-ttu-id="40a83-203">POWER(numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-203">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="40a83-204">Berechnet den Wert eines angegebenen Ausdrucks in einer angegebenen Potenz.</span><span class="sxs-lookup"><span data-stu-id="40a83-204">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="40a83-205">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-205">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="40a83-206">Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="40a83-206">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="40a83-207">Ein `Double` , das darstellt, der Möglichkeit, die zum Auslösen der `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="40a83-207">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="40a83-208">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-208">**Return Value**</span></span> 

<span data-ttu-id="40a83-209">Der Wert des angegebenen `numeric_expression` zur angegebenen `power_expression`.</span><span class="sxs-lookup"><span data-stu-id="40a83-209">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="40a83-210">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-210">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="40a83-211">RADIANS(expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-211">RADIANS(expression)</span></span>

<span data-ttu-id="40a83-212">Konvertiert Grad- in Radiantwerte.</span><span class="sxs-lookup"><span data-stu-id="40a83-212">Converts degrees to radians.</span></span> 

<span data-ttu-id="40a83-213">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-213">**Arguments**</span></span> 

<span data-ttu-id="40a83-214">`expression`: Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="40a83-214">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="40a83-215">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-215">**Return Value**</span></span> 

<span data-ttu-id="40a83-216">Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="40a83-216">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="40a83-217">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-217">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="40a83-218">Rand([SEED])</span><span class="sxs-lookup"><span data-stu-id="40a83-218">RAND([seed])</span></span>

<span data-ttu-id="40a83-219">Gibt einen Zufallswert zwischen 0 und 1 zurück.</span><span class="sxs-lookup"><span data-stu-id="40a83-219">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="40a83-220">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-220">**Arguments**</span></span> 

<span data-ttu-id="40a83-221">Der Startwert als ein `Int32`.</span><span class="sxs-lookup"><span data-stu-id="40a83-221">The seed value as an `Int32`.</span></span> <span data-ttu-id="40a83-222">Ist der seed-Wert nicht angegeben, fügt die Datenbank-Engine von SQL Server einen Zufallsstartwert hinzu.</span><span class="sxs-lookup"><span data-stu-id="40a83-222">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="40a83-223">Für einen angegebenen Startwert wird immer dasselbe Ergebnis zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="40a83-223">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="40a83-224">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-224">**Return Value**</span></span> 

<span data-ttu-id="40a83-225">Ein zufälliger `Double`-Wert zwischen 0 (null) und 1.</span><span class="sxs-lookup"><span data-stu-id="40a83-225">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="40a83-226">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-226">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a><span data-ttu-id="40a83-227">ROUND(numeric_expression, length[,function])</span><span class="sxs-lookup"><span data-stu-id="40a83-227">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="40a83-228">Gibt einen numerischen Ausdruck zurück, der auf die angegebene Länge oder Genauigkeit gerundet wurde.</span><span class="sxs-lookup"><span data-stu-id="40a83-228">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="40a83-229">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-229">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="40a83-230">Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="40a83-230">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="40a83-231">Ein `Int32`, das die Genauigkeit angibt, auf die `numeric_expression` gerundet werden soll.</span><span class="sxs-lookup"><span data-stu-id="40a83-231">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="40a83-232">Wenn `length` eine positive Zahl ist, wird `numeric_expression` auf die Anzahl der mit `length` angegebenen Dezimalstellen gerundet.</span><span class="sxs-lookup"><span data-stu-id="40a83-232">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="40a83-233">Wenn `length` eine negative Zahl ist, wird `numeric_expression` auf der linken Seite des Dezimaltrennzeichens gemäß der Angabe von `length` gerundet.</span><span class="sxs-lookup"><span data-stu-id="40a83-233">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="40a83-234">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="40a83-234">Optional.</span></span> <span data-ttu-id="40a83-235">Ein `Int32` , das den Typ des auszuführenden Vorgangs darstellt.</span><span class="sxs-lookup"><span data-stu-id="40a83-235">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="40a83-236">Wenn die Funktion ausgelassen oder weist einen Wert von 0 (Standard), `numeric_expression` wird gerundet.</span><span class="sxs-lookup"><span data-stu-id="40a83-236">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="40a83-237">Wenn ein anderer Wert als 0 angegeben ist, `numeric_expression` wird abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="40a83-237">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="40a83-238">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-238">**Return Value**</span></span> 

<span data-ttu-id="40a83-239">Der Wert des angegebenen `numeric_expression` zur angegebenen `power_expression`.</span><span class="sxs-lookup"><span data-stu-id="40a83-239">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="40a83-240">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-240">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="40a83-241">Sign(Expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-241">SIGN(expression)</span></span> 

<span data-ttu-id="40a83-242">Gibt das positive (+1) oder negative Vorzeichen (-1) oder das Vorzeichen 0 (null) des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="40a83-242">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="40a83-243">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-243">**Arguments**</span></span> 

<span data-ttu-id="40a83-244">`expression`: `Int32`, `Int64`, `Double` oder `Decimal`</span><span class="sxs-lookup"><span data-stu-id="40a83-244">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="40a83-245">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-245">**Return Value**</span></span> 

<span data-ttu-id="40a83-246">Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="40a83-246">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="40a83-247">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-247">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="40a83-248">SIN(expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-248">SIN(expression)</span></span>

<span data-ttu-id="40a83-249">Berechnet den trigonometrischen Sinus des angegebenen Winkels im Bogenmaß, und gibt einen `Double`-Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="40a83-249">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="40a83-250">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-250">**Arguments**</span></span> 

<span data-ttu-id="40a83-251">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-251">`expression`: A `Double`.</span></span> 

<span data-ttu-id="40a83-252">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-252">**Return Value**</span></span> 

<span data-ttu-id="40a83-253">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-253">A `Double`.</span></span> 

<span data-ttu-id="40a83-254">**Beispiel** `SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="40a83-254">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="40a83-255">SQRT(expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-255">SQRT(expression)</span></span>

<span data-ttu-id="40a83-256">Gibt die Quadratwurzel des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="40a83-256">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="40a83-257">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-257">**Arguments**</span></span> 

<span data-ttu-id="40a83-258">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-258">`expression`: A `Double`.</span></span> 

<span data-ttu-id="40a83-259">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-259">**Return Value**</span></span> 

<span data-ttu-id="40a83-260">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-260">A `Double`.</span></span> 

<span data-ttu-id="40a83-261">**Beispiel** `SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="40a83-261">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="40a83-262">Square(Expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-262">SQUARE(expression)</span></span>

<span data-ttu-id="40a83-263">Gibt den quadratischen Wert des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="40a83-263">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="40a83-264">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-264">**Arguments**</span></span> 

<span data-ttu-id="40a83-265">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-265">`expression`: A `Double`.</span></span> 

<span data-ttu-id="40a83-266">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-266">**Return Value**</span></span> 

<span data-ttu-id="40a83-267">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="40a83-267">A `Double`.</span></span> 

<span data-ttu-id="40a83-268">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-268">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="40a83-269">TAN(expression)</span><span class="sxs-lookup"><span data-stu-id="40a83-269">TAN(expression)</span></span>

<span data-ttu-id="40a83-270">Berechnet den Tangens eines angegebenen Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="40a83-270">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="40a83-271">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40a83-271">**Arguments**</span></span> 

<span data-ttu-id="40a83-272">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="40a83-272">`expression`: `Double`</span></span> 

<span data-ttu-id="40a83-273">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40a83-273">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="40a83-274">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40a83-274">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="40a83-275">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40a83-275">See also</span></span>

<span data-ttu-id="40a83-276">Weitere Informationen zu den von SqlClient unterstützten mathematischen Funktionen finden Sie in der Dokumentation für die SQL Server-Version, die im SqlClient-Anbietermanifest angegeben wurde:</span><span class="sxs-lookup"><span data-stu-id="40a83-276">For more information about the mathematical functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>  

<span data-ttu-id="40a83-277">**SQL Server 2005:** [Mathematische Funktionen (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="40a83-277">**SQL Server 2005:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span></span>  
<span data-ttu-id="40a83-278">**SQL Server 2008:** [Mathematische Funktionen (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="40a83-278">**SQL Server 2008:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span></span>  
<span data-ttu-id="40a83-279">**SQLServer 2012 und höher:** [Mathematische Funktionen (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span><span class="sxs-lookup"><span data-stu-id="40a83-279">**SQL Server 2012 and later:** [Mathematical Functions (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span></span>   

- [<span data-ttu-id="40a83-280">SqlClient für Entity Framework-Funktionen</span><span class="sxs-lookup"><span data-stu-id="40a83-280">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
