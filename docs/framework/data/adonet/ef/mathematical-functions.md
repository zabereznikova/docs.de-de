---
title: Mathematische Funktionen
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: b6f248382f069df59a55e85e9a764b0df700fb26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780314"
---
# <a name="mathematical-functions"></a><span data-ttu-id="d862c-102">Mathematische Funktionen</span><span class="sxs-lookup"><span data-stu-id="d862c-102">Mathematical Functions</span></span>

<span data-ttu-id="d862c-103">Der .NET Framework-Datenanbieter für SQL Server (SqlClient) stellt mathematische Funktionen bereit, die Berechnungen für als Argumente bereitgestellte Eingabewerte durchführen und einen numerischen Wert als Ergebnis zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="d862c-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="d862c-104">Diese Funktionen befinden sich im SQLServer-Namespace, der bei der Verwendung von SqlClient verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="d862c-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="d862c-105">Anhand der Namespaceigenschaft des Anbieters kann Entity Framework ermitteln, welches Präfix von diesem Anbieter für spezifische Konstrukte, wie Typen und Funktionen, verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d862c-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="d862c-106">Die folgende Tabelle beschreibt die SqlClient mathematischen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="d862c-106">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="d862c-107">Abs(Expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-107">ABS(expression)</span></span>

<span data-ttu-id="d862c-108">Führt die Absolutwertfunktion aus.</span><span class="sxs-lookup"><span data-stu-id="d862c-108">Performs the absolute value function.</span></span>

<span data-ttu-id="d862c-109">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-109">**Arguments**</span></span>

<span data-ttu-id="d862c-110">`expression`: Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d862c-110">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="d862c-111">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-111">**Return Value**</span></span>

<span data-ttu-id="d862c-112">Der Absolutwert des angegebenen Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="d862c-112">The absolute value of the specified expression.</span></span>

<span data-ttu-id="d862c-113">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-113">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="d862c-114">ACOS(Expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-114">ACOS(expression)</span></span>

<span data-ttu-id="d862c-115">Gibt den Arkuskosinuswert des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="d862c-115">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="d862c-116">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-116">**Arguments**</span></span>

<span data-ttu-id="d862c-117">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-117">`expression`: A `Double`.</span></span>

<span data-ttu-id="d862c-118">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-118">**Return Value**</span></span>

<span data-ttu-id="d862c-119">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-119">A `Double`.</span></span>

<span data-ttu-id="d862c-120">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-120">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="d862c-121">ASIN(expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-121">ASIN(expression)</span></span>

<span data-ttu-id="d862c-122">Gibt den Arkussinuswert des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="d862c-122">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="d862c-123">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-123">**Arguments**</span></span>

<span data-ttu-id="d862c-124">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-124">`expression`: A `Double`.</span></span>

<span data-ttu-id="d862c-125">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-125">**Return Value**</span></span>

<span data-ttu-id="d862c-126">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-126">A `Double`.</span></span>

<span data-ttu-id="d862c-127">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-127">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="d862c-128">Atan(Expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-128">ATAN(expression)</span></span>

<span data-ttu-id="d862c-129">Gibt den Arkustangens-Wert des angegebenen numerischen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="d862c-129">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="d862c-130">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-130">**Arguments**</span></span>

<span data-ttu-id="d862c-131">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-131">`expression`: A `Double`.</span></span>

<span data-ttu-id="d862c-132">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-132">**Return Value**</span></span>

<span data-ttu-id="d862c-133">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-133">A `Double`.</span></span>

<span data-ttu-id="d862c-134">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-134">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="d862c-135">ATN2(expression, expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-135">ATN2(expression, expression)</span></span>

<span data-ttu-id="d862c-136">Gibt den Winkel im Bogenmaß (Radiant) zurück, dessen Tangens zwischen den beiden angegebenen numerischen Ausdrücken liegt.</span><span class="sxs-lookup"><span data-stu-id="d862c-136">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="d862c-137">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-137">**Arguments**</span></span>

<span data-ttu-id="d862c-138">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-138">`expression`: A `Double`.</span></span>

<span data-ttu-id="d862c-139">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-139">**Return Value**</span></span>

<span data-ttu-id="d862c-140">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-140">A `Double`.</span></span>

<span data-ttu-id="d862c-141">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-141">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="d862c-142">CEILING(expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-142">CEILING(expression)</span></span>

<span data-ttu-id="d862c-143">Konvertiert den angegebenen Ausdruck zur kleinsten Ganzzahl, die größer als oder gleich dem Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="d862c-143">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="d862c-144">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-144">**Arguments**</span></span>

<span data-ttu-id="d862c-145">`expression`: Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d862c-145">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="d862c-146">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-146">**Return Value**</span></span>

<span data-ttu-id="d862c-147">Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d862c-147">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="d862c-148">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-148">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="d862c-149">COS(Expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-149">COS(expression)</span></span>

<span data-ttu-id="d862c-150">Berechnet den trigonometrischen Kosinus des im Bogenmaß angegebenen Winkels.</span><span class="sxs-lookup"><span data-stu-id="d862c-150">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="d862c-151">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-151">**Arguments**</span></span> 

<span data-ttu-id="d862c-152">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-152">`expression`: A `Double`.</span></span> 

<span data-ttu-id="d862c-153">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-153">**Return Value**</span></span> 

<span data-ttu-id="d862c-154">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-154">A `Double`.</span></span> 

<span data-ttu-id="d862c-155">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-155">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="d862c-156">COT(Expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-156">COT(expression)</span></span>

<span data-ttu-id="d862c-157">Berechnet den trigonometrischen Kotangens des im Bogenmaß angegebenen Winkels.</span><span class="sxs-lookup"><span data-stu-id="d862c-157">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="d862c-158">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-158">**Arguments**</span></span> 

<span data-ttu-id="d862c-159">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-159">`expression`: A `Double`.</span></span> 

<span data-ttu-id="d862c-160">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-160">**Return Value**</span></span> 

<span data-ttu-id="d862c-161">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-161">A `Double`.</span></span> 

<span data-ttu-id="d862c-162">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-162">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="d862c-163">DEGREES(RADIANS)</span><span class="sxs-lookup"><span data-stu-id="d862c-163">DEGREES(radians)</span></span>

<span data-ttu-id="d862c-164">Gibt den entsprechenden Winkel in Grad zurück.</span><span class="sxs-lookup"><span data-stu-id="d862c-164">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="d862c-165">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-165">**Arguments**</span></span> 

<span data-ttu-id="d862c-166">`expression`: Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d862c-166">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="d862c-167">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-167">**Return Value**</span></span> 

<span data-ttu-id="d862c-168">Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d862c-168">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="d862c-169">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-169">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="d862c-170">EXP(Expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-170">EXP(expression)</span></span>

<span data-ttu-id="d862c-171">Berechnet den Exponentialwert des angegebenen numerischen Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="d862c-171">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="d862c-172">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-172">**Arguments**</span></span> 

<span data-ttu-id="d862c-173">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-173">`expression`: A `Double`.</span></span> 

<span data-ttu-id="d862c-174">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-174">**Return Value**</span></span> 

<span data-ttu-id="d862c-175">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-175">A `Double`.</span></span> 

<span data-ttu-id="d862c-176">**Beispiel** `SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="d862c-176">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="d862c-177">Floor(Expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-177">FLOOR(expression)</span></span>

<span data-ttu-id="d862c-178">Konvertiert den angegebenen Ausdruck zur größten Ganzzahl, die kleiner als oder gleich dem angegebenen numerischen Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="d862c-178">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="d862c-179">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-179">**Arguments**</span></span> 

<span data-ttu-id="d862c-180">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-180">`expression`: A `Double`.</span></span> 

<span data-ttu-id="d862c-181">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-181">**Return Value**</span></span> 

<span data-ttu-id="d862c-182">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-182">A `Double`.</span></span> 

<span data-ttu-id="d862c-183">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-183">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="d862c-184">Log(Expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-184">LOG(expression)</span></span>

<span data-ttu-id="d862c-185">Berechnet den natürlichen Logarithmus des angegebenen `float`-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="d862c-185">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="d862c-186">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-186">**Arguments**</span></span> 

<span data-ttu-id="d862c-187">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-187">`expression`: A `Double`.</span></span> 

<span data-ttu-id="d862c-188">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-188">**Return Value**</span></span> 

<span data-ttu-id="d862c-189">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-189">A `Double`.</span></span> 

<span data-ttu-id="d862c-190">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-190">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="d862c-191">LOG10(expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-191">LOG10(expression)</span></span>

<span data-ttu-id="d862c-192">Gibt den Logarithmus zur Basis 10 des angegebenen `Double`-Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="d862c-192">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="d862c-193">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-193">**Arguments**</span></span> 

<span data-ttu-id="d862c-194">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-194">`expression`: A `Double`.</span></span> 

<span data-ttu-id="d862c-195">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-195">**Return Value**</span></span> 

<span data-ttu-id="d862c-196">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-196">A `Double`.</span></span> 

<span data-ttu-id="d862c-197">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-197">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="d862c-198">PI()</span><span class="sxs-lookup"><span data-stu-id="d862c-198">PI()</span></span>

<span data-ttu-id="d862c-199">Gibt den konstanten Wert von Pi als `Double`-Typ zurück.</span><span class="sxs-lookup"><span data-stu-id="d862c-199">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="d862c-200">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-200">**Return Value**</span></span> 

<span data-ttu-id="d862c-201">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-201">A `Double`.</span></span> 

<span data-ttu-id="d862c-202">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-202">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a><span data-ttu-id="d862c-203">POWER(numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-203">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="d862c-204">Berechnet den Wert eines angegebenen Ausdrucks in einer angegebenen Potenz.</span><span class="sxs-lookup"><span data-stu-id="d862c-204">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="d862c-205">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-205">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="d862c-206">Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d862c-206">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="d862c-207">Ein `Double` , das darstellt, der Möglichkeit, die zum Auslösen der `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="d862c-207">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="d862c-208">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-208">**Return Value**</span></span> 

<span data-ttu-id="d862c-209">Der Wert des angegebenen `numeric_expression` zur angegebenen `power_expression`.</span><span class="sxs-lookup"><span data-stu-id="d862c-209">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="d862c-210">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-210">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="d862c-211">RADIANS(expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-211">RADIANS(expression)</span></span>

<span data-ttu-id="d862c-212">Konvertiert Grad- in Radiantwerte.</span><span class="sxs-lookup"><span data-stu-id="d862c-212">Converts degrees to radians.</span></span> 

<span data-ttu-id="d862c-213">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-213">**Arguments**</span></span> 

<span data-ttu-id="d862c-214">`expression`: Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d862c-214">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="d862c-215">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-215">**Return Value**</span></span> 

<span data-ttu-id="d862c-216">Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d862c-216">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="d862c-217">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-217">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="d862c-218">Rand([SEED])</span><span class="sxs-lookup"><span data-stu-id="d862c-218">RAND([seed])</span></span>

<span data-ttu-id="d862c-219">Gibt einen Zufallswert zwischen 0 und 1 zurück.</span><span class="sxs-lookup"><span data-stu-id="d862c-219">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="d862c-220">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-220">**Arguments**</span></span> 

<span data-ttu-id="d862c-221">Der Startwert als ein `Int32`.</span><span class="sxs-lookup"><span data-stu-id="d862c-221">The seed value as an `Int32`.</span></span> <span data-ttu-id="d862c-222">Ist der seed-Wert nicht angegeben, fügt die Datenbank-Engine von SQL Server einen Zufallsstartwert hinzu.</span><span class="sxs-lookup"><span data-stu-id="d862c-222">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="d862c-223">Für einen angegebenen Startwert wird immer dasselbe Ergebnis zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d862c-223">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="d862c-224">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-224">**Return Value**</span></span> 

<span data-ttu-id="d862c-225">Ein zufälliger `Double`-Wert zwischen 0 (null) und 1.</span><span class="sxs-lookup"><span data-stu-id="d862c-225">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="d862c-226">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-226">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a><span data-ttu-id="d862c-227">ROUND(numeric_expression, length[,function])</span><span class="sxs-lookup"><span data-stu-id="d862c-227">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="d862c-228">Gibt einen numerischen Ausdruck zurück, der auf die angegebene Länge oder Genauigkeit gerundet wurde.</span><span class="sxs-lookup"><span data-stu-id="d862c-228">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="d862c-229">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-229">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="d862c-230">Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d862c-230">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="d862c-231">Ein `Int32`, das die Genauigkeit angibt, auf die `numeric_expression` gerundet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d862c-231">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="d862c-232">Wenn `length` eine positive Zahl ist, wird `numeric_expression` auf die Anzahl der mit `length` angegebenen Dezimalstellen gerundet.</span><span class="sxs-lookup"><span data-stu-id="d862c-232">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="d862c-233">Wenn `length` eine negative Zahl ist, wird `numeric_expression` auf der linken Seite des Dezimaltrennzeichens gemäß der Angabe von `length` gerundet.</span><span class="sxs-lookup"><span data-stu-id="d862c-233">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="d862c-234">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="d862c-234">Optional.</span></span> <span data-ttu-id="d862c-235">Ein `Int32` , das den Typ des auszuführenden Vorgangs darstellt.</span><span class="sxs-lookup"><span data-stu-id="d862c-235">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="d862c-236">Wenn die Funktion ausgelassen oder weist einen Wert von 0 (Standard), `numeric_expression` wird gerundet.</span><span class="sxs-lookup"><span data-stu-id="d862c-236">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="d862c-237">Wenn ein anderer Wert als 0 angegeben ist, `numeric_expression` wird abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="d862c-237">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="d862c-238">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-238">**Return Value**</span></span> 

<span data-ttu-id="d862c-239">Der Wert des angegebenen `numeric_expression` zur angegebenen `power_expression`.</span><span class="sxs-lookup"><span data-stu-id="d862c-239">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="d862c-240">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-240">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="d862c-241">Sign(Expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-241">SIGN(expression)</span></span> 

<span data-ttu-id="d862c-242">Gibt das positive (+1) oder negative Vorzeichen (-1) oder das Vorzeichen 0 (null) des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="d862c-242">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="d862c-243">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-243">**Arguments**</span></span> 

<span data-ttu-id="d862c-244">`expression`: `Int32`, `Int64`, `Double` oder `Decimal`</span><span class="sxs-lookup"><span data-stu-id="d862c-244">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="d862c-245">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-245">**Return Value**</span></span> 

<span data-ttu-id="d862c-246">Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d862c-246">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="d862c-247">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-247">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="d862c-248">SIN(expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-248">SIN(expression)</span></span>

<span data-ttu-id="d862c-249">Berechnet den trigonometrischen Sinus des angegebenen Winkels im Bogenmaß, und gibt einen `Double`-Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="d862c-249">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="d862c-250">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-250">**Arguments**</span></span> 

<span data-ttu-id="d862c-251">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-251">`expression`: A `Double`.</span></span> 

<span data-ttu-id="d862c-252">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-252">**Return Value**</span></span> 

<span data-ttu-id="d862c-253">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-253">A `Double`.</span></span> 

<span data-ttu-id="d862c-254">**Beispiel** `SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="d862c-254">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="d862c-255">SQRT(expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-255">SQRT(expression)</span></span>

<span data-ttu-id="d862c-256">Gibt die Quadratwurzel des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="d862c-256">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="d862c-257">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-257">**Arguments**</span></span> 

<span data-ttu-id="d862c-258">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-258">`expression`: A `Double`.</span></span> 

<span data-ttu-id="d862c-259">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-259">**Return Value**</span></span> 

<span data-ttu-id="d862c-260">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-260">A `Double`.</span></span> 

<span data-ttu-id="d862c-261">**Beispiel** `SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="d862c-261">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="d862c-262">Square(Expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-262">SQUARE(expression)</span></span>

<span data-ttu-id="d862c-263">Gibt den quadratischen Wert des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="d862c-263">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="d862c-264">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-264">**Arguments**</span></span> 

<span data-ttu-id="d862c-265">`expression`: EIN `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-265">`expression`: A `Double`.</span></span> 

<span data-ttu-id="d862c-266">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-266">**Return Value**</span></span> 

<span data-ttu-id="d862c-267">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="d862c-267">A `Double`.</span></span> 

<span data-ttu-id="d862c-268">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-268">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="d862c-269">TAN(expression)</span><span class="sxs-lookup"><span data-stu-id="d862c-269">TAN(expression)</span></span>

<span data-ttu-id="d862c-270">Berechnet den Tangens eines angegebenen Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="d862c-270">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="d862c-271">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d862c-271">**Arguments**</span></span> 

<span data-ttu-id="d862c-272">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="d862c-272">`expression`: `Double`</span></span> 

<span data-ttu-id="d862c-273">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d862c-273">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="d862c-274">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d862c-274">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="d862c-275">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d862c-275">See also</span></span>

<span data-ttu-id="d862c-276">Weitere Informationen zu den von SqlClient unterstützten mathematischen Funktionen finden Sie in der Dokumentation für die SQL Server-Version, die im SqlClient-Anbietermanifest angegeben wurde:</span><span class="sxs-lookup"><span data-stu-id="d862c-276">For more information about the mathematical functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>

- <span data-ttu-id="d862c-277">**SQL Server 2005:** [Mathematische Funktionen (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="d862c-277">**SQL Server 2005:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span></span>
- <span data-ttu-id="d862c-278">**SQL Server 2008:** [Mathematische Funktionen (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="d862c-278">**SQL Server 2008:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span></span>
- <span data-ttu-id="d862c-279">**SQLServer 2012 und höher:** [Mathematische Funktionen (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span><span class="sxs-lookup"><span data-stu-id="d862c-279">**SQL Server 2012 and later:** [Mathematical Functions (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span></span>

- [<span data-ttu-id="d862c-280">SqlClient für Entity Framework-Funktionen</span><span class="sxs-lookup"><span data-stu-id="d862c-280">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
