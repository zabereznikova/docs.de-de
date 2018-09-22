---
title: Mathematische Funktionen
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: e6c58d781d7138f8295f2d0a2f0db110ad4b1dd6
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46697879"
---
# <a name="mathematical-functions"></a><span data-ttu-id="08495-102">Mathematische Funktionen</span><span class="sxs-lookup"><span data-stu-id="08495-102">Mathematical Functions</span></span>

<span data-ttu-id="08495-103">Der .NET Framework-Datenanbieter für SQL Server (SqlClient) stellt mathematische Funktionen bereit, die Berechnungen für als Argumente bereitgestellte Eingabewerte durchführen und einen numerischen Wert als Ergebnis zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="08495-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="08495-104">Diese Funktionen befinden sich im SQLServer-Namespace, der bei der Verwendung von SqlClient verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="08495-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="08495-105">Mit der Namespace-Eigenschaft eines Anbieters kann Entity Framework ermitteln, welches Präfix von diesem Anbieter für bestimmte Konstrukte verwendet wird, z. B. Typen und Funktionen. In der folgenden Tabelle werden die mathematischen Funktionen von SqlClient beschrieben.</span><span class="sxs-lookup"><span data-stu-id="08495-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="08495-106">Abs(Expression)</span><span class="sxs-lookup"><span data-stu-id="08495-106">ABS(expression)</span></span>

<span data-ttu-id="08495-107">Führt die Absolutwertfunktion aus.</span><span class="sxs-lookup"><span data-stu-id="08495-107">Performs the absolute value function.</span></span>

<span data-ttu-id="08495-108">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-108">**Arguments**</span></span>

<span data-ttu-id="08495-109">`expression`: `Int32`,`Int64`, `Double` oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="08495-109">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="08495-110">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-110">**Return Value**</span></span>

<span data-ttu-id="08495-111">Der Absolutwert des angegebenen Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="08495-111">The absolute value of the specified expression.</span></span>

<span data-ttu-id="08495-112">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-112">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="08495-113">ACOS(Expression)</span><span class="sxs-lookup"><span data-stu-id="08495-113">ACOS(expression)</span></span>

<span data-ttu-id="08495-114">Gibt den Arkuskosinuswert des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="08495-114">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="08495-115">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-115">**Arguments**</span></span>

<span data-ttu-id="08495-116">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="08495-116">`expression`: A `Double`.</span></span>

<span data-ttu-id="08495-117">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-117">**Return Value**</span></span>

<span data-ttu-id="08495-118">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="08495-118">A `Double`.</span></span>

<span data-ttu-id="08495-119">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-119">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="08495-120">ASIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="08495-120">ASIN(expression)</span></span>

<span data-ttu-id="08495-121">Gibt den Arkussinuswert des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="08495-121">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="08495-122">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-122">**Arguments**</span></span>

<span data-ttu-id="08495-123">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="08495-123">`expression`: A `Double`.</span></span>

<span data-ttu-id="08495-124">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-124">**Return Value**</span></span>

<span data-ttu-id="08495-125">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="08495-125">A `Double`.</span></span>

<span data-ttu-id="08495-126">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-126">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="08495-127">Atan(Expression)</span><span class="sxs-lookup"><span data-stu-id="08495-127">ATAN(expression)</span></span>

<span data-ttu-id="08495-128">Gibt den Arkustangens-Wert des angegebenen numerischen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="08495-128">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="08495-129">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-129">**Arguments**</span></span>

<span data-ttu-id="08495-130">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="08495-130">`expression`: A `Double`.</span></span>

<span data-ttu-id="08495-131">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-131">**Return Value**</span></span>

<span data-ttu-id="08495-132">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="08495-132">A `Double`.</span></span>

<span data-ttu-id="08495-133">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-133">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="08495-134">ATN2(Expression, Expression)</span><span class="sxs-lookup"><span data-stu-id="08495-134">ATN2(expression, expression)</span></span>

<span data-ttu-id="08495-135">Gibt den Winkel im Bogenmaß (Radiant) zurück, dessen Tangens zwischen den beiden angegebenen numerischen Ausdrücken liegt.</span><span class="sxs-lookup"><span data-stu-id="08495-135">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="08495-136">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-136">**Arguments**</span></span>

<span data-ttu-id="08495-137">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="08495-137">`expression`: A `Double`.</span></span>

<span data-ttu-id="08495-138">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-138">**Return Value**</span></span>

<span data-ttu-id="08495-139">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="08495-139">A `Double`.</span></span>

<span data-ttu-id="08495-140">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-140">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="08495-141">CEILING(Expression)</span><span class="sxs-lookup"><span data-stu-id="08495-141">CEILING(expression)</span></span>

<span data-ttu-id="08495-142">Konvertiert den angegebenen Ausdruck zur kleinsten Ganzzahl, die größer als oder gleich dem Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="08495-142">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="08495-143">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-143">**Arguments**</span></span>

<span data-ttu-id="08495-144">`expression`: `Int32`,`Int64`, `Double` oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="08495-144">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="08495-145">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-145">**Return Value**</span></span>

<span data-ttu-id="08495-146">Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="08495-146">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="08495-147">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-147">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="08495-148">COS(Expression)</span><span class="sxs-lookup"><span data-stu-id="08495-148">COS(expression)</span></span>

<span data-ttu-id="08495-149">Berechnet den trigonometrischen Kosinus des im Bogenmaß angegebenen Winkels.</span><span class="sxs-lookup"><span data-stu-id="08495-149">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="08495-150">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-150">**Arguments**</span></span> 

<span data-ttu-id="08495-151">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="08495-151">`expression`: A `Double`.</span></span> 

<span data-ttu-id="08495-152">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-152">**Return Value**</span></span> 

<span data-ttu-id="08495-153">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="08495-153">A `Double`.</span></span> 

<span data-ttu-id="08495-154">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-154">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="08495-155">COT(Expression)</span><span class="sxs-lookup"><span data-stu-id="08495-155">COT(expression)</span></span>

<span data-ttu-id="08495-156">Berechnet den trigonometrischen Kotangens des im Bogenmaß angegebenen Winkels.</span><span class="sxs-lookup"><span data-stu-id="08495-156">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="08495-157">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-157">**Arguments**</span></span> 

<span data-ttu-id="08495-158">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="08495-158">`expression`: A `Double`.</span></span> 

<span data-ttu-id="08495-159">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-159">**Return Value**</span></span> 

<span data-ttu-id="08495-160">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="08495-160">A `Double`.</span></span> 

<span data-ttu-id="08495-161">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-161">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="08495-162">DEGREES(RADIANS)</span><span class="sxs-lookup"><span data-stu-id="08495-162">DEGREES(radians)</span></span>

<span data-ttu-id="08495-163">Gibt den entsprechenden Winkel in Grad zurück.</span><span class="sxs-lookup"><span data-stu-id="08495-163">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="08495-164">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-164">**Arguments**</span></span> 

<span data-ttu-id="08495-165">`expression`: `Int32`,`Int64`, `Double` oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="08495-165">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="08495-166">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-166">**Return Value**</span></span> 

<span data-ttu-id="08495-167">Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="08495-167">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="08495-168">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-168">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="08495-169">EXP(Expression)</span><span class="sxs-lookup"><span data-stu-id="08495-169">EXP(expression)</span></span>

<span data-ttu-id="08495-170">Berechnet den Exponentialwert des angegebenen numerischen Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="08495-170">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="08495-171">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-171">**Arguments**</span></span> 

<span data-ttu-id="08495-172">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="08495-172">`expression`: A `Double`.</span></span> 

<span data-ttu-id="08495-173">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-173">**Return Value**</span></span> 

<span data-ttu-id="08495-174">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="08495-174">A `Double`.</span></span> 

<span data-ttu-id="08495-175">**Beispiel** `SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="08495-175">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="08495-176">Floor(Expression)</span><span class="sxs-lookup"><span data-stu-id="08495-176">FLOOR(expression)</span></span>

<span data-ttu-id="08495-177">Konvertiert den angegebenen Ausdruck zur größten Ganzzahl, die kleiner als oder gleich dem angegebenen numerischen Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="08495-177">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="08495-178">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-178">**Arguments**</span></span> 

<span data-ttu-id="08495-179">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="08495-179">`expression`: A `Double`.</span></span> 

<span data-ttu-id="08495-180">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-180">**Return Value**</span></span> 

<span data-ttu-id="08495-181">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="08495-181">A `Double`.</span></span> 

<span data-ttu-id="08495-182">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-182">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="08495-183">Log(Expression)</span><span class="sxs-lookup"><span data-stu-id="08495-183">LOG(expression)</span></span>

<span data-ttu-id="08495-184">Berechnet den natürlichen Logarithmus des angegebenen `float`-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="08495-184">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="08495-185">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-185">**Arguments**</span></span> 

<span data-ttu-id="08495-186">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="08495-186">`expression`: A `Double`.</span></span> 

<span data-ttu-id="08495-187">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-187">**Return Value**</span></span> 

<span data-ttu-id="08495-188">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="08495-188">A `Double`.</span></span> 

<span data-ttu-id="08495-189">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-189">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="08495-190">LOG10(Expression)</span><span class="sxs-lookup"><span data-stu-id="08495-190">LOG10(expression)</span></span>

<span data-ttu-id="08495-191">Gibt den Logarithmus zur Basis 10 des angegebenen `Double`-Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="08495-191">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="08495-192">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-192">**Arguments**</span></span> 

<span data-ttu-id="08495-193">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="08495-193">`expression`: A `Double`.</span></span> 

<span data-ttu-id="08495-194">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-194">**Return Value**</span></span> 

<span data-ttu-id="08495-195">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="08495-195">A `Double`.</span></span> 

<span data-ttu-id="08495-196">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-196">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="08495-197">PI)</span><span class="sxs-lookup"><span data-stu-id="08495-197">PI()</span></span>

<span data-ttu-id="08495-198">Gibt den konstanten Wert von Pi als `Double`-Typ zurück.</span><span class="sxs-lookup"><span data-stu-id="08495-198">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="08495-199">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-199">**Return Value**</span></span> 

<span data-ttu-id="08495-200">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="08495-200">A `Double`.</span></span> 

<span data-ttu-id="08495-201">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-201">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a><span data-ttu-id="08495-202">POWER (Numeric_expression, Power_expression)</span><span class="sxs-lookup"><span data-stu-id="08495-202">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="08495-203">Berechnet den Wert eines angegebenen Ausdrucks in einer angegebenen Potenz.</span><span class="sxs-lookup"><span data-stu-id="08495-203">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="08495-204">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-204">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="08495-205">Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="08495-205">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="08495-206">Ein `Double` , das darstellt, der Möglichkeit, die zum Auslösen der `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="08495-206">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="08495-207">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-207">**Return Value**</span></span> 

<span data-ttu-id="08495-208">Der Wert des angegebenen `numeric_expression` zur angegebenen `power_expression`.</span><span class="sxs-lookup"><span data-stu-id="08495-208">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="08495-209">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-209">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="08495-210">RADIANS(Expression)</span><span class="sxs-lookup"><span data-stu-id="08495-210">RADIANS(expression)</span></span>

<span data-ttu-id="08495-211">Konvertiert Grad- in Radiantwerte.</span><span class="sxs-lookup"><span data-stu-id="08495-211">Converts degrees to radians.</span></span> 

<span data-ttu-id="08495-212">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-212">**Arguments**</span></span> 

<span data-ttu-id="08495-213">`expression`: `Int32`,`Int64`, `Double` oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="08495-213">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="08495-214">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-214">**Return Value**</span></span> 

<span data-ttu-id="08495-215">Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="08495-215">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="08495-216">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-216">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="08495-217">Rand([SEED])</span><span class="sxs-lookup"><span data-stu-id="08495-217">RAND([seed])</span></span>

<span data-ttu-id="08495-218">Gibt einen Zufallswert zwischen 0 und 1 zurück.</span><span class="sxs-lookup"><span data-stu-id="08495-218">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="08495-219">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-219">**Arguments**</span></span> 

<span data-ttu-id="08495-220">Der Startwert als ein `Int32`.</span><span class="sxs-lookup"><span data-stu-id="08495-220">The seed value as an `Int32`.</span></span> <span data-ttu-id="08495-221">Ist der seed-Wert nicht angegeben, fügt die Datenbank-Engine von SQL Server einen Zufallsstartwert hinzu.</span><span class="sxs-lookup"><span data-stu-id="08495-221">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="08495-222">Für einen angegebenen Startwert wird immer dasselbe Ergebnis zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="08495-222">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="08495-223">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-223">**Return Value**</span></span> 

<span data-ttu-id="08495-224">Ein zufälliger `Double`-Wert zwischen 0 (null) und 1.</span><span class="sxs-lookup"><span data-stu-id="08495-224">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="08495-225">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-225">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a><span data-ttu-id="08495-226">Round(numeric_expression, Length[,Function])</span><span class="sxs-lookup"><span data-stu-id="08495-226">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="08495-227">Gibt einen numerischen Ausdruck zurück, der auf die angegebene Länge oder Genauigkeit gerundet wurde.</span><span class="sxs-lookup"><span data-stu-id="08495-227">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="08495-228">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-228">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="08495-229">Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="08495-229">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="08495-230">Ein `Int32`, das die Genauigkeit angibt, auf die `numeric_expression` gerundet werden soll.</span><span class="sxs-lookup"><span data-stu-id="08495-230">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="08495-231">Wenn `length` eine positive Zahl ist, wird `numeric_expression` auf die Anzahl der mit `length` angegebenen Dezimalstellen gerundet.</span><span class="sxs-lookup"><span data-stu-id="08495-231">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="08495-232">Wenn `length` eine negative Zahl ist, wird `numeric_expression` auf der linken Seite des Dezimaltrennzeichens gemäß der Angabe von `length` gerundet.</span><span class="sxs-lookup"><span data-stu-id="08495-232">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="08495-233">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="08495-233">Optional.</span></span> <span data-ttu-id="08495-234">Ein `Int32` , das den Typ des auszuführenden Vorgangs darstellt.</span><span class="sxs-lookup"><span data-stu-id="08495-234">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="08495-235">Wenn die Funktion ausgelassen oder weist einen Wert von 0 (Standard), `numeric_expression` wird gerundet.</span><span class="sxs-lookup"><span data-stu-id="08495-235">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="08495-236">Wenn ein anderer Wert als 0 angegeben ist, `numeric_expression` wird abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="08495-236">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="08495-237">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-237">**Return Value**</span></span> 

<span data-ttu-id="08495-238">Der Wert des angegebenen `numeric_expression` zur angegebenen `power_expression`.</span><span class="sxs-lookup"><span data-stu-id="08495-238">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="08495-239">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-239">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="08495-240">Sign(Expression)</span><span class="sxs-lookup"><span data-stu-id="08495-240">SIGN(expression)</span></span> 

<span data-ttu-id="08495-241">Gibt das positive (+1) oder negative Vorzeichen (-1) oder das Vorzeichen 0 (null) des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="08495-241">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="08495-242">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-242">**Arguments**</span></span> 

<span data-ttu-id="08495-243">`expression`: `Int32`, `Int64`, `Double` oder `Decimal`</span><span class="sxs-lookup"><span data-stu-id="08495-243">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="08495-244">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-244">**Return Value**</span></span> 

<span data-ttu-id="08495-245">Ein `Int32`, `Int64`, `Double`, oder `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="08495-245">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="08495-246">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-246">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="08495-247">SIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="08495-247">SIN(expression)</span></span>

<span data-ttu-id="08495-248">Berechnet den trigonometrischen Sinus des angegebenen Winkels im Bogenmaß, und gibt einen `Double`-Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="08495-248">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="08495-249">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-249">**Arguments**</span></span> 

<span data-ttu-id="08495-250">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="08495-250">`expression`: A `Double`.</span></span> 

<span data-ttu-id="08495-251">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-251">**Return Value**</span></span> 

<span data-ttu-id="08495-252">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="08495-252">A `Double`.</span></span> 

<span data-ttu-id="08495-253">**Beispiel** `SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="08495-253">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="08495-254">Sqrt(Expression)</span><span class="sxs-lookup"><span data-stu-id="08495-254">SQRT(expression)</span></span>

<span data-ttu-id="08495-255">Gibt die Quadratwurzel des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="08495-255">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="08495-256">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-256">**Arguments**</span></span> 

<span data-ttu-id="08495-257">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="08495-257">`expression`: A `Double`.</span></span> 

<span data-ttu-id="08495-258">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-258">**Return Value**</span></span> 

<span data-ttu-id="08495-259">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="08495-259">A `Double`.</span></span> 

<span data-ttu-id="08495-260">**Beispiel** `SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="08495-260">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="08495-261">Square(Expression)</span><span class="sxs-lookup"><span data-stu-id="08495-261">SQUARE(expression)</span></span>

<span data-ttu-id="08495-262">Gibt den quadratischen Wert des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="08495-262">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="08495-263">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-263">**Arguments**</span></span> 

<span data-ttu-id="08495-264">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="08495-264">`expression`: A `Double`.</span></span> 

<span data-ttu-id="08495-265">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-265">**Return Value**</span></span> 

<span data-ttu-id="08495-266">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="08495-266">A `Double`.</span></span> 

<span data-ttu-id="08495-267">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-267">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="08495-268">TAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="08495-268">TAN(expression)</span></span>

<span data-ttu-id="08495-269">Berechnet den Tangens eines angegebenen Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="08495-269">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="08495-270">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="08495-270">**Arguments**</span></span> 

<span data-ttu-id="08495-271">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="08495-271">`expression`: `Double`</span></span> 

<span data-ttu-id="08495-272">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="08495-272">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="08495-273">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="08495-273">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="08495-274">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08495-274">See also</span></span>

<span data-ttu-id="08495-275">Weitere Informationen zu den von SqlClient unterstützten mathematischen Funktionen finden Sie in der Dokumentation für die SQL Server-Version, die im SqlClient-Anbietermanifest angegeben wurde:</span><span class="sxs-lookup"><span data-stu-id="08495-275">For more information about the mathematical functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>  
  
<span data-ttu-id="08495-276">**SQLServer 2005:** [mathematische Funktionen (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="08495-276">**SQL Server 2005:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span></span>  
<span data-ttu-id="08495-277">**SQLServer 2008:** [mathematische Funktionen (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="08495-277">**SQL Server 2008:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span></span>  
<span data-ttu-id="08495-278">**SQLServer 2012 und höher:** [mathematische Funktionen (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span><span class="sxs-lookup"><span data-stu-id="08495-278">**SQL Server 2012 and later:** [Mathematical Functions (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span></span>   

 [<span data-ttu-id="08495-279">SqlClient für Entity Framework-Funktionen</span><span class="sxs-lookup"><span data-stu-id="08495-279">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
