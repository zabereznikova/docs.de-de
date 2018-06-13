---
title: Verwenden von auf NULL festlegbaren Typen (C# Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: d2fe0f34c45d3de0516a71ca5ed4dc807df4bf93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336920"
---
# <a name="using-nullable-types-c-programming-guide"></a><span data-ttu-id="656a1-102">Verwenden von auf NULL festlegbaren Typen (C# Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="656a1-102">Using Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="656a1-103">Auf NULL festlegbare Typen können alle Werte eines zugrundeliegenden Typs und einen zusätzlichen [NULL](../../../csharp/language-reference/keywords/null.md)-Wert darstellen.</span><span class="sxs-lookup"><span data-stu-id="656a1-103">Nullable types can represent all the values of an underlying type, and an additional [null](../../../csharp/language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="656a1-104">Auf NULL festlegbare Typen können auf zwei verschiedene Arten deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="656a1-104">Nullable types are declared in one of two ways:</span></span>  
  
 `System.Nullable<T> variable`  
  
 <span data-ttu-id="656a1-105">- oder - </span><span class="sxs-lookup"><span data-stu-id="656a1-105">-or-</span></span>  
  
 `T? variable`  
  
 <span data-ttu-id="656a1-106">`T` ist der zugrundeliegende Typ des Typs, der NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="656a1-106">`T` is the underlying type of the nullable type.</span></span> <span data-ttu-id="656a1-107">`T` kann jeder Werttyp, auch `struct`, sein; allerdings kann es kein Verweistyp sein.</span><span class="sxs-lookup"><span data-stu-id="656a1-107">`T` can be any value type including `struct`; it cannot be a reference type.</span></span>  
  
 <span data-ttu-id="656a1-108">Denken Sie z.B. an eine normalen Boolesche Variable, die zwei Werte aufweisen kann: TRUE und FALSE; so ähnlich verhält es sich auch mit dem Einsatz eines Typs, der NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="656a1-108">For an example of when you might use a nullable type, consider how an ordinary Boolean variable can have two values: true and false.</span></span> <span data-ttu-id="656a1-109">Es gibt keinen Wert, der für „nicht definiert“ steht.</span><span class="sxs-lookup"><span data-stu-id="656a1-109">There is no value that signifies "undefined".</span></span> <span data-ttu-id="656a1-110">In den meisten Programmierungsanwendungen – allen voran Datenbankinteraktionen – können Variablen in einem nicht definierten Zustand vorkommen.</span><span class="sxs-lookup"><span data-stu-id="656a1-110">In many programming applications, most notably database interactions, variables can occur in an undefined state.</span></span> <span data-ttu-id="656a1-111">Ein Feld in einer Datenbank kann z.B. die Werte TRUE und FALSE enthalten; ebenso kann es aber auch gar keinen Wert enthalten.</span><span class="sxs-lookup"><span data-stu-id="656a1-111">For example, a field in a database may contain the values true or false, but it may also contain no value at all.</span></span> <span data-ttu-id="656a1-112">Ebenso können Verweistypen auf `null` festgelegt werden, um zu kennzeichnen, dass sie nicht initialisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="656a1-112">Similarly, reference types can be set to `null` to indicate that they are not initialized.</span></span>  
  
 <span data-ttu-id="656a1-113">Durch diese Ungleichheit kann weiteres Programmieren erforderlich sein: zusätzliche Variablen zum Speichern von Zustandsinformationen, der Einsatz von besonderen Werten usw.</span><span class="sxs-lookup"><span data-stu-id="656a1-113">This disparity can create extra programming work, with additional variables used to store state information, the use of special values, and so on.</span></span> <span data-ttu-id="656a1-114">Mit dem Modifizierer für Typen, die NULL-Werte zulassen, kann C# value-type-Variablen erstellen, die einen nicht definierten Wert kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="656a1-114">The nullable type modifier enables C# to create value-type variables that indicate an undefined value.</span></span>  
  
## <a name="examples-of-nullable-types"></a><span data-ttu-id="656a1-115">Beispiele für Typen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="656a1-115">Examples of Nullable Types</span></span>  
 <span data-ttu-id="656a1-116">Jeder Werttyp kann als Grundlage für einen Typ, der NULL-Werte zulässt, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="656a1-116">Any value type may be used as the basis for a nullable type.</span></span> <span data-ttu-id="656a1-117">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="656a1-117">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]  
  
## <a name="the-members-of-nullable-types"></a><span data-ttu-id="656a1-118">Member von Typen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="656a1-118">The Members of Nullable Types</span></span>  
 <span data-ttu-id="656a1-119">Jede Instanz eines Typs, der auf NULL festgelegt werden kann, hat zwei öffentliche schreibgeschützte Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="656a1-119">Each instance of a nullable type has two public read-only properties:</span></span>  
  
-   `HasValue`  
  
     <span data-ttu-id="656a1-120">`HasValue` ist vom Typ `bool`.</span><span class="sxs-lookup"><span data-stu-id="656a1-120">`HasValue` is of type `bool`.</span></span> <span data-ttu-id="656a1-121">Es wird auf `true` festgelegt, wenn die Variable einen Wert enthält, der ungleich NULL ist.</span><span class="sxs-lookup"><span data-stu-id="656a1-121">It is set to `true` when the variable contains a non-null value.</span></span>  
  
-   `Value`  
  
     <span data-ttu-id="656a1-122">`Value` hat denselben Typ wie der zugrunde liegende Typ.</span><span class="sxs-lookup"><span data-stu-id="656a1-122">`Value` is of the same type as the underlying type.</span></span> <span data-ttu-id="656a1-123">Wenn `HasValue` `true` ist, enthält `Value` einen sinnvollen Wert.</span><span class="sxs-lookup"><span data-stu-id="656a1-123">If `HasValue` is `true`, `Value` contains a meaningful value.</span></span> <span data-ttu-id="656a1-124">Wenn `HasValue` auf `false` festgelegt ist, wird bei Zugriff auf `Value` eine <xref:System.InvalidOperationException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="656a1-124">If `HasValue` is `false`, accessing `Value` will throw a <xref:System.InvalidOperationException>.</span></span>  
  
 <span data-ttu-id="656a1-125">Der `HasValue`-Member in diesem Beispiel wird dazu verwendet, zu prüfen, ob eine Variable einen Wert enthält, bevor er diesen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="656a1-125">In this example, the `HasValue` member is used to test whether the variable contains a value before it tries to display it.</span></span>  
  
 [!code-csharp[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]  
  
 <span data-ttu-id="656a1-126">Das Prüfen auf einen Wert kann auch wie im folgenden Beispiel durchgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="656a1-126">Testing for a value can also be done as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]  
  
## <a name="explicit-conversions"></a><span data-ttu-id="656a1-127">Explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="656a1-127">Explicit Conversions</span></span>  
 <span data-ttu-id="656a1-128">Ein Typ, der NULL-Werte zulässt, kann in einen gängigen Typ umgewandelt werden; dies können Sie entweder durch eine explizite Umwandlung oder mithilfe der `Value`-Eigenschaft erzielen.</span><span class="sxs-lookup"><span data-stu-id="656a1-128">A nullable type can be cast to a regular type, either explicitly with a cast, or by using the `Value` property.</span></span> <span data-ttu-id="656a1-129">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="656a1-129">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]  
  
 <span data-ttu-id="656a1-130">Wenn eine benutzerdefinierte Konvertierung zwischen zwei Datentypen definiert ist, kann die gleiche Konvertierung auch mit der Version dieser Datentypen verwendet werden, die NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="656a1-130">If a user-defined conversion is defined between two data types, the same conversion can also be used with the nullable versions of these data types.</span></span>  
  
## <a name="implicit-conversions"></a><span data-ttu-id="656a1-131">Implizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="656a1-131">Implicit Conversions</span></span>  
 <span data-ttu-id="656a1-132">Eine Variable mit einem Typ, der NULL-Werte zulässt, kann wie in folgendem Beispiel mit dem Schlüsselwort `null` auf NULL festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="656a1-132">A variable of nullable type can be set to null with the `null` keyword, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]  
  
 <span data-ttu-id="656a1-133">Die Konvertierung von einem gängigen in einen auf NULL-festlegbaren Typ ist implizit.</span><span class="sxs-lookup"><span data-stu-id="656a1-133">The conversion from an ordinary type to a nullable type, is implicit.</span></span>  
  
 [!code-csharp[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]  
  
## <a name="operators"></a><span data-ttu-id="656a1-134">Operatoren</span><span class="sxs-lookup"><span data-stu-id="656a1-134">Operators</span></span>  
 <span data-ttu-id="656a1-135">Die vordefinierten unären und binären Operatoren und alle benutzerdefinierten Operatoren für Werttypen können auch von auf NULL festlegbaren Typen verwende werden.</span><span class="sxs-lookup"><span data-stu-id="656a1-135">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by nullable types.</span></span> <span data-ttu-id="656a1-136">Die Operatoren erzeugen einen NULL-Wert, wenn die Operanden NULL sind; andernfalls verwenden die Operatoren den enthaltenen Wert zur Berechnung eines Ergebnisses.</span><span class="sxs-lookup"><span data-stu-id="656a1-136">These operators produce a null value if the operands are null; otherwise, the operator uses the contained value to calculate the result.</span></span> <span data-ttu-id="656a1-137">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="656a1-137">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]  
  
 <span data-ttu-id="656a1-138">Wenn Sie Vergleiche mit auf NULL-festlegbaren Typen durchführen, ergeben alle Vergleiche `false`, nur `!=` nicht (ungleich), wenn der Wert von lediglich einem auf NULL festlegbaren Wert NULL ist.</span><span class="sxs-lookup"><span data-stu-id="656a1-138">When you perform comparisons with nullable types, if the value of one of the nullable types is null and the other is not, all comparisons evaluate to `false` except for `!=` (not equal).</span></span> <span data-ttu-id="656a1-139">Es ist wichtig, dass Sie nicht davon ausgehen, dass der entgegengesetzte Fall `true` zurückgeben würde, nur wenn ein Vergleich `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="656a1-139">It is important not to assume that because a particular comparison returns `false`, the opposite case returns `true`.</span></span> <span data-ttu-id="656a1-140">Im folgenden Beispiel ist 10 weder größer noch kleiner noch gleich NULL.</span><span class="sxs-lookup"><span data-stu-id="656a1-140">In the following example, 10 is not greater than, less than, nor equal to null.</span></span> <span data-ttu-id="656a1-141">Nur `num1 != num2` ergibt `true`.</span><span class="sxs-lookup"><span data-stu-id="656a1-141">Only `num1 != num2` evaluates to `true`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]  
  
 <span data-ttu-id="656a1-142">Ein Gleichheitsvergleich zweier auf NULL festlegbarer Typen, die beide NULL sind, ergibt `true`.</span><span class="sxs-lookup"><span data-stu-id="656a1-142">An equality comparison of two nullable types that are both null evaluates to `true`.</span></span>  
  
## <a name="the--operator"></a><span data-ttu-id="656a1-143">Der ??-</span><span class="sxs-lookup"><span data-stu-id="656a1-143">The ??</span></span> <span data-ttu-id="656a1-144">Operator</span><span class="sxs-lookup"><span data-stu-id="656a1-144">Operator</span></span>  
 <span data-ttu-id="656a1-145">Der `??`-Operator definiert einen Standardwert, der zurückgegeben wird, wenn ein auf NULL festlegbarer Typ einem nicht auf NULL festlegbaren Typ zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="656a1-145">The `??` operator defines a default value that is returned when a nullable type is assigned to a non-nullable type.</span></span>  
  
 [!code-csharp[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]  
  
 <span data-ttu-id="656a1-146">Dieser Operator kann auch mit mehreren auf NULL festlegbaren Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="656a1-146">This operator can also be used with multiple nullable types.</span></span> <span data-ttu-id="656a1-147">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="656a1-147">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]  
  
## <a name="the-bool-type"></a><span data-ttu-id="656a1-148">Der „bool?“-Typ</span><span class="sxs-lookup"><span data-stu-id="656a1-148">The bool? type</span></span>  
 <span data-ttu-id="656a1-149">Der `bool?`-Typ, der NULL-Werte zulässt, kann drei verschiedene Werte enthalten: [TRUE](../../../csharp/language-reference/keywords/true.md), [FALSE](../../../csharp/language-reference/keywords/false.md) und [NULL](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="656a1-149">The `bool?` nullable type can contain three different values: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) and [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="656a1-150">Weitere Informationen zur Umwandlung von „bool?“ in „bool“ finden Sie unter [Vorgehensweise: Sichere Umwandlung von bool? in bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span><span class="sxs-lookup"><span data-stu-id="656a1-150">For information about how to cast from a bool? to a bool, see [How to: Safely Cast from bool? to bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span></span>  
  
 <span data-ttu-id="656a1-151">Boolesche Werte, die auf NULL festgelegt werden können, verhalten sich ähnlich wie der in SQL verwendete Boolesche Variablentyp.</span><span class="sxs-lookup"><span data-stu-id="656a1-151">Nullable Booleans are like the Boolean variable type that is used in SQL.</span></span> <span data-ttu-id="656a1-152">Folgende vordefinierte Operatoren stehen zur Verfügung, um sicherzustellen, dass die von den Operatoren `&` und `|` erzeugten Ergebnisse zu dem dreiwertigen Booleschen Typ in SQL passen:</span><span class="sxs-lookup"><span data-stu-id="656a1-152">To ensure that the results produced by the `&` and `|` operators are consistent with the three-valued Boolean type in SQL, the following predefined operators are provided:</span></span>  
  
 `bool? operator &(bool? x, bool? y)`  
  
 `bool? operator |(bool? x, bool? y)`  
  
 <span data-ttu-id="656a1-153">Die Ergebnisse dieser Operatoren sind in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="656a1-153">The results of these operators are listed in the following table:</span></span>  
  
|<span data-ttu-id="656a1-154">X</span><span class="sxs-lookup"><span data-stu-id="656a1-154">X</span></span>|<span data-ttu-id="656a1-155">u</span><span class="sxs-lookup"><span data-stu-id="656a1-155">y</span></span>|<span data-ttu-id="656a1-156">x&y</span><span class="sxs-lookup"><span data-stu-id="656a1-156">x&y</span></span>|<span data-ttu-id="656a1-157">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="656a1-157">x&#124;y</span></span>|  
|-------|-------|---------|--------------|  
|<span data-ttu-id="656a1-158">true</span><span class="sxs-lookup"><span data-stu-id="656a1-158">true</span></span>|<span data-ttu-id="656a1-159">true</span><span class="sxs-lookup"><span data-stu-id="656a1-159">true</span></span>|<span data-ttu-id="656a1-160">true</span><span class="sxs-lookup"><span data-stu-id="656a1-160">true</span></span>|<span data-ttu-id="656a1-161">true</span><span class="sxs-lookup"><span data-stu-id="656a1-161">true</span></span>|  
|<span data-ttu-id="656a1-162">true</span><span class="sxs-lookup"><span data-stu-id="656a1-162">true</span></span>|<span data-ttu-id="656a1-163">False</span><span class="sxs-lookup"><span data-stu-id="656a1-163">false</span></span>|<span data-ttu-id="656a1-164">false</span><span class="sxs-lookup"><span data-stu-id="656a1-164">false</span></span>|<span data-ttu-id="656a1-165">true</span><span class="sxs-lookup"><span data-stu-id="656a1-165">true</span></span>|  
|<span data-ttu-id="656a1-166">true</span><span class="sxs-lookup"><span data-stu-id="656a1-166">true</span></span>|<span data-ttu-id="656a1-167">NULL</span><span class="sxs-lookup"><span data-stu-id="656a1-167">null</span></span>|<span data-ttu-id="656a1-168">NULL</span><span class="sxs-lookup"><span data-stu-id="656a1-168">null</span></span>|<span data-ttu-id="656a1-169">true</span><span class="sxs-lookup"><span data-stu-id="656a1-169">true</span></span>|  
|<span data-ttu-id="656a1-170">False</span><span class="sxs-lookup"><span data-stu-id="656a1-170">false</span></span>|<span data-ttu-id="656a1-171">true</span><span class="sxs-lookup"><span data-stu-id="656a1-171">true</span></span>|<span data-ttu-id="656a1-172">False</span><span class="sxs-lookup"><span data-stu-id="656a1-172">false</span></span>|<span data-ttu-id="656a1-173">true</span><span class="sxs-lookup"><span data-stu-id="656a1-173">true</span></span>|  
|<span data-ttu-id="656a1-174">False</span><span class="sxs-lookup"><span data-stu-id="656a1-174">false</span></span>|<span data-ttu-id="656a1-175">False</span><span class="sxs-lookup"><span data-stu-id="656a1-175">false</span></span>|<span data-ttu-id="656a1-176">False</span><span class="sxs-lookup"><span data-stu-id="656a1-176">false</span></span>|<span data-ttu-id="656a1-177">False</span><span class="sxs-lookup"><span data-stu-id="656a1-177">false</span></span>|  
|<span data-ttu-id="656a1-178">False</span><span class="sxs-lookup"><span data-stu-id="656a1-178">false</span></span>|<span data-ttu-id="656a1-179">NULL</span><span class="sxs-lookup"><span data-stu-id="656a1-179">null</span></span>|<span data-ttu-id="656a1-180">False</span><span class="sxs-lookup"><span data-stu-id="656a1-180">false</span></span>|<span data-ttu-id="656a1-181">NULL</span><span class="sxs-lookup"><span data-stu-id="656a1-181">null</span></span>|  
|<span data-ttu-id="656a1-182">NULL</span><span class="sxs-lookup"><span data-stu-id="656a1-182">null</span></span>|<span data-ttu-id="656a1-183">true</span><span class="sxs-lookup"><span data-stu-id="656a1-183">true</span></span>|<span data-ttu-id="656a1-184">NULL</span><span class="sxs-lookup"><span data-stu-id="656a1-184">null</span></span>|<span data-ttu-id="656a1-185">true</span><span class="sxs-lookup"><span data-stu-id="656a1-185">true</span></span>|  
|<span data-ttu-id="656a1-186">NULL</span><span class="sxs-lookup"><span data-stu-id="656a1-186">null</span></span>|<span data-ttu-id="656a1-187">False</span><span class="sxs-lookup"><span data-stu-id="656a1-187">false</span></span>|<span data-ttu-id="656a1-188">False</span><span class="sxs-lookup"><span data-stu-id="656a1-188">false</span></span>|<span data-ttu-id="656a1-189">NULL</span><span class="sxs-lookup"><span data-stu-id="656a1-189">null</span></span>|  
|<span data-ttu-id="656a1-190">NULL</span><span class="sxs-lookup"><span data-stu-id="656a1-190">null</span></span>|<span data-ttu-id="656a1-191">NULL</span><span class="sxs-lookup"><span data-stu-id="656a1-191">null</span></span>|<span data-ttu-id="656a1-192">NULL</span><span class="sxs-lookup"><span data-stu-id="656a1-192">null</span></span>|<span data-ttu-id="656a1-193">NULL</span><span class="sxs-lookup"><span data-stu-id="656a1-193">null</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="656a1-194">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="656a1-194">See Also</span></span>  
 [<span data-ttu-id="656a1-195">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="656a1-195">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="656a1-196">Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="656a1-196">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="656a1-197">Boxing von Typen mit Nullwerten</span><span class="sxs-lookup"><span data-stu-id="656a1-197">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
 [<span data-ttu-id="656a1-198">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="656a1-198">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
