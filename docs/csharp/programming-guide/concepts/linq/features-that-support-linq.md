---
title: C#-Funktionen mit LINQ-Unterstützung
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
ms.openlocfilehash: 51cc24fd8054b87b6c92a02450420a9c4abef525
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50191089"
---
# <a name="c-features-that-support-linq"></a><span data-ttu-id="82d48-102">C#-Funktionen mit LINQ-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="82d48-102">C# Features That Support LINQ</span></span>
<span data-ttu-id="82d48-103">Im folgenden Abschnitt werden neue Sprachkonstrukte, die in C# 3.0 eingeführt werden, vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="82d48-103">The following section introduces new language constructs introduced in C# 3.0.</span></span> <span data-ttu-id="82d48-104">Obwohl diese neuen Funktionen zu einem gewissen Grad mit [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfragen verwendet werden, sind sie nicht beschränkt auf [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] und können in jedem Kontext, in dem Sie sie nützlich finden, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="82d48-104">Although these new features are all used to a degree with [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, they are not limited to [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] and can be used in any context where you find them useful.</span></span>  
  
## <a name="query-expressions"></a><span data-ttu-id="82d48-105">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="82d48-105">Query Expressions</span></span>  
 <span data-ttu-id="82d48-106">Abfrageausdrücke verwenden eine deklarative Syntax wie SQL oder XQuery, um eine Abfrage über IEnumerable-Sammlungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="82d48-106">Query expressions use a declarative syntax similar to SQL or XQuery to query over IEnumerable collections.</span></span> <span data-ttu-id="82d48-107">Zur Kompilierzeit wird die Abfragesyntax in Methodenaufrufe an eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Implementierung des Anbieters der Erweiterungsmethode des Standardabfrageoperators kompiliert.</span><span class="sxs-lookup"><span data-stu-id="82d48-107">At compile time query syntax is converted to method calls to a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider's implementation of the standard query operator extension methods.</span></span> <span data-ttu-id="82d48-108">Applikationen steuern die Standardabfrageoperatoren, die sich durch Angabe des entsprechenden Namespace mit einer `using`-Anweisung innerhalb des Bereichs befinden.</span><span class="sxs-lookup"><span data-stu-id="82d48-108">Applications control the standard query operators that are in scope by specifying the appropriate namespace with a `using` directive.</span></span> <span data-ttu-id="82d48-109">Der folgende Abfrageausdruck nimmt ein Array von Zeichenfolgen, gruppiert sie nach dem ersten Zeichen in der Zeichenfolge und sortiert die Gruppen.</span><span class="sxs-lookup"><span data-stu-id="82d48-109">The following query expression takes an array of strings, groups them according to the first character in the string, and orders the groups.</span></span>  
  
```csharp  
var query = from str in stringArray  
            group str by str[0] into stringGroup  
            orderby stringGroup.Key  
            select stringGroup;  
```  
  
 <span data-ttu-id="82d48-110">Weitere Informationen finden Sie unter [LINQ-Abfrageausdrücke](../../../../csharp/programming-guide/linq-query-expressions/index.md).</span><span class="sxs-lookup"><span data-stu-id="82d48-110">For more information, see [LINQ Query Expressions](../../../../csharp/programming-guide/linq-query-expressions/index.md).</span></span>  
  
## <a name="implicitly-typed-variables-var"></a><span data-ttu-id="82d48-111">Implizit typisierte Variablen (var)</span><span class="sxs-lookup"><span data-stu-id="82d48-111">Implicitly Typed Variables (var)</span></span>  
 <span data-ttu-id="82d48-112">Anstatt beim Deklarieren und Initialisieren einer Variablen einen Typ explizit anzugeben, können Sie den [var](../../../../csharp/language-reference/keywords/var.md)-Modifizierer verwenden, um den Compiler zum Ableiten und Zuweisen des Typs anzuweisen, wie hier gezeigt:</span><span class="sxs-lookup"><span data-stu-id="82d48-112">Instead of explicitly specifying a type when you declare and initialize a variable, you can use the [var](../../../../csharp/language-reference/keywords/var.md) modifier to instruct the compiler to infer and assign the type, as shown here:</span></span>  
  
```csharp  
var number = 5;  
var name = "Virginia";  
var query = from str in stringArray  
            where str[0] == 'm'  
            select str;  
```  
  
 <span data-ttu-id="82d48-113">Variablen, die als `var` deklariert werden, sind ebenso stark typisiert wie Variablen, deren Typ Sie explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="82d48-113">Variables declared as `var` are just as strongly-typed as variables whose type you specify explicitly.</span></span> <span data-ttu-id="82d48-114">Die Verwendung von `var` macht es möglich, anonyme Typen zu erstellen, dies ist jedoch nur für lokale Variablen möglich.</span><span class="sxs-lookup"><span data-stu-id="82d48-114">The use of `var` makes it possible to create anonymous types, but it can be used only for local variables.</span></span> <span data-ttu-id="82d48-115">Arrays können auch mit impliziter Typisierung deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="82d48-115">Arrays can also be declared with implicit typing.</span></span>  
  
 <span data-ttu-id="82d48-116">Weitere Informationen finden Sie unter [Implizit typisierte lokale Variablen](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="82d48-116">For more information, see [Implicitly Typed Local Variables](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
## <a name="object-and-collection-initializers"></a><span data-ttu-id="82d48-117">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="82d48-117">Object and Collection Initializers</span></span>  
 <span data-ttu-id="82d48-118">Objekt- und Auflistungsinitialisierer ermöglichen das Initialisieren von Objekten ohne expliziten Aufruf eines Konstruktors für das Objekt.</span><span class="sxs-lookup"><span data-stu-id="82d48-118">Object and collection initializers make it possible to initialize objects without explicitly calling a constructor for the object.</span></span> <span data-ttu-id="82d48-119">Initialisierer werden in der Regel in Abfrageausdrücken verwendet, wenn sie die Quelldaten in einen neuen Datentyp projizieren.</span><span class="sxs-lookup"><span data-stu-id="82d48-119">Initializers are typically used in query expressions when they project the source data into a new data type.</span></span> <span data-ttu-id="82d48-120">In einer Klasse namens `Customer` mit öffentlichen `Name`- und `Phone`-Eigenschaften können Objektinitialisierer wie im folgenden Code verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="82d48-120">Assuming a class named `Customer` with public `Name` and `Phone` properties, the object initializer can be used as in the following code:</span></span>  
  
```csharp  
Customer cust = new Customer { Name = "Mike", Phone = "555-1212" };  
```  
<span data-ttu-id="82d48-121">Wenn Sie mit der `Customer`-Klasse fortfahren, gehen Sie davon aus, dass eine Datenquelle namens `IncomingOrders` vorhanden ist, und dass für jede Bestellung mit einem großen `OrderSize`-Wert ein neues `Customer`-Element basierend auf dieser Bestellung erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="82d48-121">Continuing with our `Customer` class, assume that there is a data source called `IncomingOrders`, and that for each order with a large `OrderSize`, we would like to create a new `Customer` based off of that order.</span></span> <span data-ttu-id="82d48-122">Eine LINQ-Abfrage kann auf dieser Datenquelle ausgeführt werden und verwendet die Objektinitialisierung, um eine Auflistung zu füllen:</span><span class="sxs-lookup"><span data-stu-id="82d48-122">A LINQ query can be executed on this data source and use object initialization to fill a collection:</span></span>
```csharp
var newLargeOrderCustomers = from o in IncomingOrders
                            where o.OrderSize > 5
                            select new Customer { Name = o.Name, Phone = o.Phone };
```
<span data-ttu-id="82d48-123">Die Datenquelle kann mehr Eigenschaften im Hintergrund haben als die Klasse `Customer`, z.B. `OrderSize`, aber bei der Objektinitialisierung werden die von der Abfrage zurückgegebenen Daten in den gewünschten Datentyp umgewandelt. Wählen Sie die Daten aus, die für Ihre Klasse relevant sind.</span><span class="sxs-lookup"><span data-stu-id="82d48-123">The data source may have more properties lying under the hood than the `Customer` class such as `OrderSize`, but with object initialization, the data returned from the query is molded into the desired data type; we choose the data that is relevant to our class.</span></span> <span data-ttu-id="82d48-124">Daher verfügen wir jetzt über ein `IEnumerable`-Element, das mit den neuen gewünschten `Customer`-Informationen gefüllt ist.</span><span class="sxs-lookup"><span data-stu-id="82d48-124">As a result, we now have an `IEnumerable` filled with the new `Customer`s we wanted.</span></span> <span data-ttu-id="82d48-125">Das oben Geschilderte kann auch in der Methodensyntax von LINQ geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="82d48-125">The above can also be written in LINQ's method syntax:</span></span>
```csharp
var newLargeOrderCustomers = IncomingOrders.Where(x => x.OrderSize > 5).Select(y => new Customer { Name = y.Name, Phone = y.Phone });
```
 <span data-ttu-id="82d48-126">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="82d48-126">For more information, see:</span></span>
 
 - [<span data-ttu-id="82d48-127">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="82d48-127">Object and Collection Initializers</span></span>](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

 - [<span data-ttu-id="82d48-128">Abfrageausdruckssyntax für Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="82d48-128">Query Expression Syntax for Standard Query Operators</span></span>](../../../../csharp/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)

## <a name="anonymous-types"></a><span data-ttu-id="82d48-129">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="82d48-129">Anonymous Types</span></span>  
 <span data-ttu-id="82d48-130">Ein anonymer Typ wird vom Compiler erstellt, und der Typname ist nur für den Compiler verfügbar.</span><span class="sxs-lookup"><span data-stu-id="82d48-130">An anonymous type is constructed by the compiler and the type name is only available to the compiler.</span></span> <span data-ttu-id="82d48-131">Anonyme Typen stellen eine bequeme Möglichkeit zum vorübergehenden Gruppieren einer Reihe von Eigenschaften in einem Abfrageergebnis bereit, ohne einen separaten benannten Typ definieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="82d48-131">Anonymous types provide a convenient way to group a set of properties temporarily in a query result without having to define a separate named type.</span></span> <span data-ttu-id="82d48-132">Anonyme Typen werden mit einem neuen Ausdruck und einem Objektinitialisierer initialisiert, wie hier gezeigt:</span><span class="sxs-lookup"><span data-stu-id="82d48-132">Anonymous types are initialized with a new expression and an object initializer, as shown here:</span></span>  
  
```csharp
select new {name = cust.Name, phone = cust.Phone};  
```  
  
 <span data-ttu-id="82d48-133">Weitere Informationen finden Sie unter [Anonyme Typen](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="82d48-133">For more information, see [Anonymous Types](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
## <a name="extension-methods"></a><span data-ttu-id="82d48-134">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="82d48-134">Extension Methods</span></span>  
 <span data-ttu-id="82d48-135">Eine Erweiterungsmethode ist eine statische Methode, die einem Typ zugeordnet werden kann, sodass sie aufgerufen werden kann, als ob es sich um eine Instanzmethode für den Typ handeln würde.</span><span class="sxs-lookup"><span data-stu-id="82d48-135">An extension method is a static method that can be associated with a type, so that it can be called as if it were an instance method on the type.</span></span> <span data-ttu-id="82d48-136">Diese Funktion ermöglicht es Ihnen, neue Methoden zu vorhandenen Typen „hinzuzufügen“, ohne sie tatsächlich zu ändern.</span><span class="sxs-lookup"><span data-stu-id="82d48-136">This feature enables you to, in effect, "add" new methods to existing types without actually modifying them.</span></span> <span data-ttu-id="82d48-137">Die Standardabfrageoperatoren sind eine Reihe von Erweiterungsmethoden, die [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfragefunktionen für jeden Typ bieten, der <xref:System.Collections.Generic.IEnumerable%601> implementiert.</span><span class="sxs-lookup"><span data-stu-id="82d48-137">The standard query operators are a set of extension methods that provide [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query functionality for any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  
  
 <span data-ttu-id="82d48-138">Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="82d48-138">For more information, see [Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span>  
  
## <a name="lambda-expressions"></a><span data-ttu-id="82d48-139">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="82d48-139">Lambda Expressions</span></span>  
 <span data-ttu-id="82d48-140">Ein Lambdaausdruck ist eine Inlinefunktion, die den Operator => verwendet, um Eingabeparameter vom Funktionstext zu trennen, und die zur Kompilierzeit in einen Delegaten oder eine Ausdrucksbaumstruktur konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="82d48-140">A lambda expression is an inline function that uses the => operator to separate input parameters from the function body and can be converted at compile time to a delegate or an expression tree.</span></span> <span data-ttu-id="82d48-141">In der [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Programmierung erhalten Sie Lambdaausdrücke, wenn Sie direkte Methodenaufrufe für die Standardabfrageoperatoren vornehmen.</span><span class="sxs-lookup"><span data-stu-id="82d48-141">In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] programming, you will encounter lambda expressions when you make direct method calls to the standard query operators.</span></span>  
  
 <span data-ttu-id="82d48-142">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="82d48-142">For more information, see:</span></span>  
  
-   [<span data-ttu-id="82d48-143">Anonyme Funktionen</span><span class="sxs-lookup"><span data-stu-id="82d48-143">Anonymous Functions</span></span>](../../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [<span data-ttu-id="82d48-144">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="82d48-144">Lambda Expressions</span></span>](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
  
-   [<span data-ttu-id="82d48-145">Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="82d48-145">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)  
   
## <a name="see-also"></a><span data-ttu-id="82d48-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82d48-146">See Also</span></span>

- [<span data-ttu-id="82d48-147">Language-Integrated Query (LINQ) (Sprachintegrierte Abfrage (LINQ))</span><span class="sxs-lookup"><span data-stu-id="82d48-147">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)
