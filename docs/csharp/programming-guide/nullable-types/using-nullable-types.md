---
title: "Verwenden von auf NULL festlegbaren Typen (C# Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0721d9f60abc4e158135d6b050953b3e63ab8cb5
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="using-nullable-types-c-programming-guide"></a><span data-ttu-id="40047-102">Verwenden von auf NULL festlegbaren Typen (C# Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="40047-102">Using Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="40047-103">Auf NULL festlegbare Typen können alle Werte eines zugrundeliegenden Typs und einen zusätzlichen [NULL](../../../csharp/language-reference/keywords/null.md)-Wert darstellen.</span><span class="sxs-lookup"><span data-stu-id="40047-103">Nullable types can represent all the values of an underlying type, and an additional [null](../../../csharp/language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="40047-104">Auf NULL festlegbare Typen können auf zwei verschiedene Arten deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="40047-104">Nullable types are declared in one of two ways:</span></span>  
  
 `System.Nullable<T> variable`  
  
 <span data-ttu-id="40047-105">- oder - </span><span class="sxs-lookup"><span data-stu-id="40047-105">-or-</span></span>  
  
 `T? variable`  
  
 <span data-ttu-id="40047-106">`T` ist der zugrundeliegende Typ des Typs, der NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="40047-106">`T` is the underlying type of the nullable type.</span></span> <span data-ttu-id="40047-107">`T` kann jeder Werttyp, auch `struct`, sein; allerdings kann es kein Verweistyp sein.</span><span class="sxs-lookup"><span data-stu-id="40047-107">`T` can be any value type including `struct`; it cannot be a reference type.</span></span>  
  
 <span data-ttu-id="40047-108">Denken Sie z.B. an eine normalen Boolesche Variable, die zwei Werte aufweisen kann: TRUE und FALSE; so ähnlich verhält es sich auch mit dem Einsatz eines Typs, der NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="40047-108">For an example of when you might use a nullable type, consider how an ordinary Boolean variable can have two values: true and false.</span></span> <span data-ttu-id="40047-109">Es gibt keinen Wert, der für „nicht definiert“ steht.</span><span class="sxs-lookup"><span data-stu-id="40047-109">There is no value that signifies "undefined".</span></span> <span data-ttu-id="40047-110">In den meisten Programmierungsanwendungen – allen voran Datenbankinteraktionen – können Variablen in einem nicht definierten Zustand vorkommen.</span><span class="sxs-lookup"><span data-stu-id="40047-110">In many programming applications, most notably database interactions, variables can occur in an undefined state.</span></span> <span data-ttu-id="40047-111">Ein Feld in einer Datenbank kann z.B. die Werte TRUE und FALSE enthalten; ebenso kann es aber auch gar keinen Wert enthalten.</span><span class="sxs-lookup"><span data-stu-id="40047-111">For example, a field in a database may contain the values true or false, but it may also contain no value at all.</span></span> <span data-ttu-id="40047-112">Ebenso können Verweistypen auf `null` festgelegt werden, um zu kennzeichnen, dass sie nicht initialisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="40047-112">Similarly, reference types can be set to `null` to indicate that they are not initialized.</span></span>  
  
 <span data-ttu-id="40047-113">Durch diese Ungleichheit kann weiteres Programmieren erforderlich sein: zusätzliche Variablen zum Speichern von Zustandsinformationen, der Einsatz von besonderen Werten usw.</span><span class="sxs-lookup"><span data-stu-id="40047-113">This disparity can create extra programming work, with additional variables used to store state information, the use of special values, and so on.</span></span> <span data-ttu-id="40047-114">Mit dem Modifizierer für Typen, die NULL-Werte zulassen, kann C# value-type-Variablen erstellen, die einen nicht definierten Wert kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="40047-114">The nullable type modifier enables C# to create value-type variables that indicate an undefined value.</span></span>  
  
## <a name="examples-of-nullable-types"></a><span data-ttu-id="40047-115">Beispiele für Typen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="40047-115">Examples of Nullable Types</span></span>  
 <span data-ttu-id="40047-116">Jeder Werttyp kann als Grundlage für einen Typ, der NULL-Werte zulässt, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="40047-116">Any value type may be used as the basis for a nullable type.</span></span> <span data-ttu-id="40047-117">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="40047-117">For example:</span></span>  
  
 <span data-ttu-id="40047-118">[!code-cs[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="40047-118">[!code-cs[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]</span></span>  
  
## <a name="the-members-of-nullable-types"></a><span data-ttu-id="40047-119">Member von Typen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="40047-119">The Members of Nullable Types</span></span>  
 <span data-ttu-id="40047-120">Jede Instanz eines Typs, der auf NULL festgelegt werden kann, hat zwei öffentliche schreibgeschützte Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="40047-120">Each instance of a nullable type has two public read-only properties:</span></span>  
  
-   `HasValue`  
  
     <span data-ttu-id="40047-121">`HasValue` ist vom Typ `bool`.</span><span class="sxs-lookup"><span data-stu-id="40047-121">`HasValue` is of type `bool`.</span></span> <span data-ttu-id="40047-122">Es wird auf `true` festgelegt, wenn die Variable einen Wert enthält, der ungleich NULL ist.</span><span class="sxs-lookup"><span data-stu-id="40047-122">It is set to `true` when the variable contains a non-null value.</span></span>  
  
-   `Value`  
  
     <span data-ttu-id="40047-123">`Value` hat denselben Typ wie der zugrunde liegende Typ.</span><span class="sxs-lookup"><span data-stu-id="40047-123">`Value` is of the same type as the underlying type.</span></span> <span data-ttu-id="40047-124">Wenn `HasValue` `true` ist, enthält `Value` einen sinnvollen Wert.</span><span class="sxs-lookup"><span data-stu-id="40047-124">If `HasValue` is `true`, `Value` contains a meaningful value.</span></span> <span data-ttu-id="40047-125">Wenn `HasValue` auf `false` festgelegt ist, wird bei Zugriff auf `Value` eine <xref:System.InvalidOperationException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="40047-125">If `HasValue` is `false`, accessing `Value` will throw a <xref:System.InvalidOperationException>.</span></span>  
  
 <span data-ttu-id="40047-126">Der `HasValue`-Member in diesem Beispiel wird dazu verwendet, zu prüfen, ob eine Variable einen Wert enthält, bevor er diesen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="40047-126">In this example, the `HasValue` member is used to test whether the variable contains a value before it tries to display it.</span></span>  
  
 <span data-ttu-id="40047-127">[!code-cs[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="40047-127">[!code-cs[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]</span></span>  
  
 <span data-ttu-id="40047-128">Das Prüfen auf einen Wert kann auch wie im folgenden Beispiel durchgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="40047-128">Testing for a value can also be done as in the following example:</span></span>  
  
 <span data-ttu-id="40047-129">[!code-cs[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="40047-129">[!code-cs[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]</span></span>  
  
## <a name="explicit-conversions"></a><span data-ttu-id="40047-130">Explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="40047-130">Explicit Conversions</span></span>  
 <span data-ttu-id="40047-131">Ein Typ, der NULL-Werte zulässt, kann in einen gängigen Typ umgewandelt werden; dies können Sie entweder durch eine explizite Umwandlung oder mithilfe der `Value`-Eigenschaft erzielen.</span><span class="sxs-lookup"><span data-stu-id="40047-131">A nullable type can be cast to a regular type, either explicitly with a cast, or by using the `Value` property.</span></span> <span data-ttu-id="40047-132">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="40047-132">For example:</span></span>  
  
 <span data-ttu-id="40047-133">[!code-cs[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="40047-133">[!code-cs[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]</span></span>  
  
 <span data-ttu-id="40047-134">Wenn eine benutzerdefinierte Konvertierung zwischen zwei Datentypen definiert ist, kann die gleiche Konvertierung auch mit der Version dieser Datentypen verwendet werden, die NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="40047-134">If a user-defined conversion is defined between two data types, the same conversion can also be used with the nullable versions of these data types.</span></span>  
  
## <a name="implicit-conversions"></a><span data-ttu-id="40047-135">Implizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="40047-135">Implicit Conversions</span></span>  
 <span data-ttu-id="40047-136">Eine Variable mit einem Typ, der NULL-Werte zulässt, kann wie in folgendem Beispiel mit dem Schlüsselwort `null` auf NULL festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="40047-136">A variable of nullable type can be set to null with the `null` keyword, as shown in the following example:</span></span>  
  
 <span data-ttu-id="40047-137">[!code-cs[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="40047-137">[!code-cs[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]</span></span>  
  
 <span data-ttu-id="40047-138">Die Konvertierung von einem gängigen in einen auf NULL-festlegbaren Typ ist implizit.</span><span class="sxs-lookup"><span data-stu-id="40047-138">The conversion from an ordinary type to a nullable type, is implicit.</span></span>  
  
 <span data-ttu-id="40047-139">[!code-cs[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="40047-139">[!code-cs[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]</span></span>  
  
## <a name="operators"></a><span data-ttu-id="40047-140">Operatoren</span><span class="sxs-lookup"><span data-stu-id="40047-140">Operators</span></span>  
 <span data-ttu-id="40047-141">Die vordefinierten unären und binären Operatoren und alle benutzerdefinierten Operatoren für Werttypen können auch von auf NULL festlegbaren Typen verwende werden.</span><span class="sxs-lookup"><span data-stu-id="40047-141">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by nullable types.</span></span> <span data-ttu-id="40047-142">Die Operatoren erzeugen einen NULL-Wert, wenn die Operanden NULL sind; andernfalls verwenden die Operatoren den enthaltenen Wert zur Berechnung eines Ergebnisses.</span><span class="sxs-lookup"><span data-stu-id="40047-142">These operators produce a null value if the operands are null; otherwise, the operator uses the contained value to calculate the result.</span></span> <span data-ttu-id="40047-143">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="40047-143">For example:</span></span>  
  
 <span data-ttu-id="40047-144">[!code-cs[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="40047-144">[!code-cs[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]</span></span>  
  
 <span data-ttu-id="40047-145">Wenn Sie Vergleiche mit auf NULL-festlegbaren Typen durchführen, ergeben alle Vergleiche `false`, nur `!=` nicht (ungleich), wenn der Wert von lediglich einem auf NULL festlegbaren Wert NULL ist.</span><span class="sxs-lookup"><span data-stu-id="40047-145">When you perform comparisons with nullable types, if the value of one of the nullable types is null and the other is not, all comparisons evaluate to `false` except for `!=` (not equal).</span></span> <span data-ttu-id="40047-146">Es ist wichtig, dass Sie nicht davon ausgehen, dass der entgegengesetzte Fall `true` zurückgeben würde, nur wenn ein Vergleich `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="40047-146">It is important not to assume that because a particular comparison returns `false`, the opposite case returns `true`.</span></span> <span data-ttu-id="40047-147">Im folgenden Beispiel ist 10 weder größer noch kleiner noch gleich NULL.</span><span class="sxs-lookup"><span data-stu-id="40047-147">In the following example, 10 is not greater than, less than, nor equal to null.</span></span> <span data-ttu-id="40047-148">Nur `num1 != num2` ergibt `true`.</span><span class="sxs-lookup"><span data-stu-id="40047-148">Only `num1 != num2` evaluates to `true`.</span></span>  
  
 <span data-ttu-id="40047-149">[!code-cs[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="40047-149">[!code-cs[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]</span></span>  
  
 <span data-ttu-id="40047-150">Ein Gleichheitsvergleich zweier auf NULL festlegbarer Typen, die beide NULL sind, ergibt `true`.</span><span class="sxs-lookup"><span data-stu-id="40047-150">An equality comparison of two nullable types that are both null evaluates to `true`.</span></span>  
  
## <a name="the--operator"></a><span data-ttu-id="40047-151">Der ??-</span><span class="sxs-lookup"><span data-stu-id="40047-151">The ??</span></span> <span data-ttu-id="40047-152">Operator</span><span class="sxs-lookup"><span data-stu-id="40047-152">Operator</span></span>  
 <span data-ttu-id="40047-153">Der `??`-Operator definiert einen Standardwert, der zurückgegeben wird, wenn ein auf NULL festlegbarer Typ einem nicht auf NULL festlegbaren Typ zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="40047-153">The `??` operator defines a default value that is returned when a nullable type is assigned to a non-nullable type.</span></span>  
  
 <span data-ttu-id="40047-154">[!code-cs[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="40047-154">[!code-cs[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]</span></span>  
  
 <span data-ttu-id="40047-155">Dieser Operator kann auch mit mehreren auf NULL festlegbaren Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="40047-155">This operator can also be used with multiple nullable types.</span></span> <span data-ttu-id="40047-156">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="40047-156">For example:</span></span>  
  
 <span data-ttu-id="40047-157">[!code-cs[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="40047-157">[!code-cs[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]</span></span>  
  
## <a name="the-bool-type"></a><span data-ttu-id="40047-158">Der „bool?“-Typ</span><span class="sxs-lookup"><span data-stu-id="40047-158">The bool? type</span></span>  
 <span data-ttu-id="40047-159">Der `bool?`-Typ, der NULL-Werte zulässt, kann drei verschiedene Werte enthalten: [TRUE](../../../csharp/language-reference/keywords/true.md), [FALSE](../../../csharp/language-reference/keywords/false.md) und [NULL](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="40047-159">The `bool?` nullable type can contain three different values: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) and [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="40047-160">Weitere Informationen zur Umwandlung von „bool?“ in „bool“ finden Sie unter [Vorgehensweise: Sichere Umwandlung von bool? in bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span><span class="sxs-lookup"><span data-stu-id="40047-160">For information about how to cast from a bool? to a bool, see [How to: Safely Cast from bool? to bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span></span>  
  
 <span data-ttu-id="40047-161">Boolesche Werte, die auf NULL festgelegt werden können, verhalten sich ähnlich wie der in SQL verwendete Boolesche Variablentyp.</span><span class="sxs-lookup"><span data-stu-id="40047-161">Nullable Booleans are like the Boolean variable type that is used in SQL.</span></span> <span data-ttu-id="40047-162">Folgende vordefinierte Operatoren stehen zur Verfügung, um sicherzustellen, dass die von den Operatoren `&` und `|` erzeugten Ergebnisse zu dem dreiwertigen Booleschen Typ in SQL passen:</span><span class="sxs-lookup"><span data-stu-id="40047-162">To ensure that the results produced by the `&` and `|` operators are consistent with the three-valued Boolean type in SQL, the following predefined operators are provided:</span></span>  
  
 `bool? operator &(bool? x, bool? y)`  
  
 `bool? operator |(bool? x, bool? y)`  
  
 <span data-ttu-id="40047-163">Die Ergebnisse dieser Operatoren sind in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="40047-163">The results of these operators are listed in the following table:</span></span>  
  
|<span data-ttu-id="40047-164">X</span><span class="sxs-lookup"><span data-stu-id="40047-164">X</span></span>|<span data-ttu-id="40047-165">u</span><span class="sxs-lookup"><span data-stu-id="40047-165">y</span></span>|<span data-ttu-id="40047-166">x&y</span><span class="sxs-lookup"><span data-stu-id="40047-166">x&y</span></span>|<span data-ttu-id="40047-167">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="40047-167">x&#124;y</span></span>|  
|-------|-------|---------|--------------|  
|<span data-ttu-id="40047-168">true</span><span class="sxs-lookup"><span data-stu-id="40047-168">true</span></span>|<span data-ttu-id="40047-169">true</span><span class="sxs-lookup"><span data-stu-id="40047-169">true</span></span>|<span data-ttu-id="40047-170">true</span><span class="sxs-lookup"><span data-stu-id="40047-170">true</span></span>|<span data-ttu-id="40047-171">true</span><span class="sxs-lookup"><span data-stu-id="40047-171">true</span></span>|  
|<span data-ttu-id="40047-172">true</span><span class="sxs-lookup"><span data-stu-id="40047-172">true</span></span>|<span data-ttu-id="40047-173">false</span><span class="sxs-lookup"><span data-stu-id="40047-173">false</span></span>|<span data-ttu-id="40047-174">false</span><span class="sxs-lookup"><span data-stu-id="40047-174">false</span></span>|<span data-ttu-id="40047-175">true</span><span class="sxs-lookup"><span data-stu-id="40047-175">true</span></span>|  
|<span data-ttu-id="40047-176">true</span><span class="sxs-lookup"><span data-stu-id="40047-176">true</span></span>|<span data-ttu-id="40047-177">NULL</span><span class="sxs-lookup"><span data-stu-id="40047-177">null</span></span>|<span data-ttu-id="40047-178">NULL</span><span class="sxs-lookup"><span data-stu-id="40047-178">null</span></span>|<span data-ttu-id="40047-179">true</span><span class="sxs-lookup"><span data-stu-id="40047-179">true</span></span>|  
|<span data-ttu-id="40047-180">false</span><span class="sxs-lookup"><span data-stu-id="40047-180">false</span></span>|<span data-ttu-id="40047-181">true</span><span class="sxs-lookup"><span data-stu-id="40047-181">true</span></span>|<span data-ttu-id="40047-182">false</span><span class="sxs-lookup"><span data-stu-id="40047-182">false</span></span>|<span data-ttu-id="40047-183">true</span><span class="sxs-lookup"><span data-stu-id="40047-183">true</span></span>|  
|<span data-ttu-id="40047-184">false</span><span class="sxs-lookup"><span data-stu-id="40047-184">false</span></span>|<span data-ttu-id="40047-185">false</span><span class="sxs-lookup"><span data-stu-id="40047-185">false</span></span>|<span data-ttu-id="40047-186">false</span><span class="sxs-lookup"><span data-stu-id="40047-186">false</span></span>|<span data-ttu-id="40047-187">false</span><span class="sxs-lookup"><span data-stu-id="40047-187">false</span></span>|  
|<span data-ttu-id="40047-188">false</span><span class="sxs-lookup"><span data-stu-id="40047-188">false</span></span>|<span data-ttu-id="40047-189">NULL</span><span class="sxs-lookup"><span data-stu-id="40047-189">null</span></span>|<span data-ttu-id="40047-190">false</span><span class="sxs-lookup"><span data-stu-id="40047-190">false</span></span>|<span data-ttu-id="40047-191">NULL</span><span class="sxs-lookup"><span data-stu-id="40047-191">null</span></span>|  
|<span data-ttu-id="40047-192">NULL</span><span class="sxs-lookup"><span data-stu-id="40047-192">null</span></span>|<span data-ttu-id="40047-193">true</span><span class="sxs-lookup"><span data-stu-id="40047-193">true</span></span>|<span data-ttu-id="40047-194">NULL</span><span class="sxs-lookup"><span data-stu-id="40047-194">null</span></span>|<span data-ttu-id="40047-195">true</span><span class="sxs-lookup"><span data-stu-id="40047-195">true</span></span>|  
|<span data-ttu-id="40047-196">NULL</span><span class="sxs-lookup"><span data-stu-id="40047-196">null</span></span>|<span data-ttu-id="40047-197">false</span><span class="sxs-lookup"><span data-stu-id="40047-197">false</span></span>|<span data-ttu-id="40047-198">false</span><span class="sxs-lookup"><span data-stu-id="40047-198">false</span></span>|<span data-ttu-id="40047-199">NULL</span><span class="sxs-lookup"><span data-stu-id="40047-199">null</span></span>|  
|<span data-ttu-id="40047-200">NULL</span><span class="sxs-lookup"><span data-stu-id="40047-200">null</span></span>|<span data-ttu-id="40047-201">NULL</span><span class="sxs-lookup"><span data-stu-id="40047-201">null</span></span>|<span data-ttu-id="40047-202">NULL</span><span class="sxs-lookup"><span data-stu-id="40047-202">null</span></span>|<span data-ttu-id="40047-203">NULL</span><span class="sxs-lookup"><span data-stu-id="40047-203">null</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40047-204">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40047-204">See Also</span></span>  
 <span data-ttu-id="40047-205">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="40047-205">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="40047-206">[Typen, die NULL-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="40047-206">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 <span data-ttu-id="40047-207">[Boxing von Typen mit NULL-Werten](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md) </span><span class="sxs-lookup"><span data-stu-id="40047-207">[Boxing Nullable Types](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md) </span></span>  
 [<span data-ttu-id="40047-208">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="40047-208">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)

