---
title: "C#-Funktionen mit LINQ-Unterstützung"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2f5accb188e54e0d3e2b941832637ec33afc26b2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="c-features-that-support-linq"></a><span data-ttu-id="f4594-102">C#-Funktionen mit LINQ-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="f4594-102">C# Features That Support LINQ</span></span>
<span data-ttu-id="f4594-103">Im folgenden Abschnitt werden neue Sprachkonstrukte, die in C# 3.0 eingeführt werden, vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="f4594-103">The following section introduces new language constructs introduced in C# 3.0.</span></span> <span data-ttu-id="f4594-104">Obwohl diese neuen Funktionen zu einem gewissen Grad mit [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfragen verwendet werden, sind sie nicht beschränkt auf [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] und können in jedem Kontext, in dem Sie sie nützlich finden, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f4594-104">Although these new features are all used to a degree with [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, they are not limited to [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] and can be used in any context where you find them useful.</span></span>  
  
## <a name="query-expressions"></a><span data-ttu-id="f4594-105">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="f4594-105">Query Expressions</span></span>  
 <span data-ttu-id="f4594-106">Abfrageausdrücke verwenden eine deklarative Syntax wie SQL oder XQuery, um eine Abfrage über IEnumerable-Sammlungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f4594-106">Queries expressions use a declarative syntax similar to SQL or XQuery to query over IEnumerable collections.</span></span> <span data-ttu-id="f4594-107">Zur Kompilierzeit wird die Abfragesyntax in Methodenaufrufe an eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Implementierung des Anbieters der Erweiterungsmethode des Standardabfrageoperators kompiliert.</span><span class="sxs-lookup"><span data-stu-id="f4594-107">At compile time query syntax is converted to method calls to a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider's implementation of the standard query operator extension methods.</span></span> <span data-ttu-id="f4594-108">Applikationen steuern die Standardabfrageoperatoren, die sich durch Angabe des entsprechenden Namespace mit einer `using`-Anweisung innerhalb des Bereichs befinden.</span><span class="sxs-lookup"><span data-stu-id="f4594-108">Applications control the standard query operators that are in scope by specifying the appropriate namespace with a `using` directive.</span></span> <span data-ttu-id="f4594-109">Der folgende Abfrageausdruck nimmt ein Array von Zeichenfolgen, gruppiert sie nach dem ersten Zeichen in der Zeichenfolge und sortiert die Gruppen.</span><span class="sxs-lookup"><span data-stu-id="f4594-109">The following query expression takes an array of strings, groups them according to the first character in the string, and orders the groups.</span></span>  
  
```  
var query = from str in stringArray  
            group str by str[0] into stringGroup  
            orderby stringGroup.Key  
            select stringGroup;  
```  
  
 <span data-ttu-id="f4594-110">Weitere Informationen finden Sie unter [LINQ-Abfrageausdrücke](../../../../csharp/programming-guide/linq-query-expressions/index.md).</span><span class="sxs-lookup"><span data-stu-id="f4594-110">For more information, see [LINQ Query Expressions](../../../../csharp/programming-guide/linq-query-expressions/index.md).</span></span>  
  
## <a name="implicitly-typed-variables-var"></a><span data-ttu-id="f4594-111">Implizit typisierte Variablen (var)</span><span class="sxs-lookup"><span data-stu-id="f4594-111">Implicitly Typed Variables (var)</span></span>  
 <span data-ttu-id="f4594-112">Anstatt beim Deklarieren und Initialisieren einer Variablen einen Typ explizit anzugeben, können Sie den [var](../../../../csharp/language-reference/keywords/var.md)-Modifizierer verwenden, um den Compiler zum Ableiten und Zuweisen des Typs anzuweisen, wie hier gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f4594-112">Instead of explicitly specifying a type when you declare and initialize a variable, you can use the [var](../../../../csharp/language-reference/keywords/var.md) modifier to instruct the compiler to infer and assign the type, as shown here:</span></span>  
  
```  
var number = 5;  
var name = "Virginia";  
var query = from str in stringArray  
            where str[0] == 'm'  
            select str;  
```  
  
 <span data-ttu-id="f4594-113">Variablen, die als `var` deklariert werden, sind ebenso stark typisiert wie Variablen, deren Typ Sie explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="f4594-113">Variables declared as `var` are just as strongly-typed as variables whose type you specify explicitly.</span></span> <span data-ttu-id="f4594-114">Die Verwendung von `var` macht es möglich, anonyme Typen zu erstellen, aber es kann für jede lokale Variable verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f4594-114">The use of `var` makes it possible to create anonymous types, but it can be used for any local variable.</span></span> <span data-ttu-id="f4594-115">Arrays können auch mit impliziter Typisierung deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="f4594-115">Arrays can also be declared with implicit typing.</span></span>  
  
 <span data-ttu-id="f4594-116">Weitere Informationen finden Sie unter [Implizit typisierte lokale Variablen](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="f4594-116">For more information, see [Implicitly Typed Local Variables](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
## <a name="object-and-collection-initializers"></a><span data-ttu-id="f4594-117">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="f4594-117">Object and Collection Initializers</span></span>  
 <span data-ttu-id="f4594-118">Objekt- und Auflistungsinitialisierer ermöglichen das Initialisieren von Objekten ohne expliziten Aufruf eines Konstruktors für das Objekt.</span><span class="sxs-lookup"><span data-stu-id="f4594-118">Object and collection initializers make it possible to initialize objects without explicitly calling a constructor for the object.</span></span> <span data-ttu-id="f4594-119">Initialisierer werden in der Regel in Abfrageausdrücken verwendet, wenn sie die Quelldaten in einen neuen Datentyp projizieren.</span><span class="sxs-lookup"><span data-stu-id="f4594-119">Initializers are typically used in query expressions when they project the source data into a new data type.</span></span> <span data-ttu-id="f4594-120">In einer Klasse namens `Customer` mit öffentlichen `Name`- und `Phone`-Eigenschaften können Objektinitialisierer wie im folgenden Code verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="f4594-120">Assuming a class named `Customer` with public `Name` and `Phone` properties, the object initializer can be used as in the following code:</span></span>  
  
```  
Customer cust = new Customer { Name = "Mike", Phone = "555-1212" };  
```  
  
 <span data-ttu-id="f4594-121">Weitere Informationen finden Sie unter [Objekt- und Auflistungsinitialisierer](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="f4594-121">For more information, see [Object and Collection Initializers](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
## <a name="anonymous-types"></a><span data-ttu-id="f4594-122">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="f4594-122">Anonymous Types</span></span>  
 <span data-ttu-id="f4594-123">Ein anonymer Typ wird vom Compiler erstellt, und der Typname ist nur für den Compiler verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f4594-123">An anonymous type is constructed by the compiler and the type name is only available to the compiler.</span></span> <span data-ttu-id="f4594-124">Anonyme Typen stellen eine bequeme Möglichkeit zum vorübergehenden Gruppieren einer Reihe von Eigenschaften in einem Abfrageergebnis bereit, ohne einen separaten benannten Typ definieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="f4594-124">Anonymous types provide a convenient way to group a set of properties temporarily in a query result without having to define a separate named type.</span></span> <span data-ttu-id="f4594-125">Anonyme Typen werden mit einem neuen Ausdruck und einem Objektinitialisierer initialisiert, wie hier gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f4594-125">Anonymous types are initialized with a new expression and an object initializer, as shown here:</span></span>  
  
```  
select new {name = cust.Name, phone = cust.Phone};  
```  
  
 <span data-ttu-id="f4594-126">Weitere Informationen finden Sie unter [Anonyme Typen](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="f4594-126">For more information, see [Anonymous Types](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
## <a name="extension-methods"></a><span data-ttu-id="f4594-127">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="f4594-127">Extension Methods</span></span>  
 <span data-ttu-id="f4594-128">Eine Erweiterungsmethode ist eine statische Methode, die einem Typ zugeordnet werden kann, sodass sie aufgerufen werden kann, als ob es sich um eine Instanzmethode für den Typ handeln würde.</span><span class="sxs-lookup"><span data-stu-id="f4594-128">An extension method is a static method that can be associated with a type, so that it can be called as if it were an instance method on the type.</span></span> <span data-ttu-id="f4594-129">Diese Funktion ermöglicht es Ihnen, neue Methoden zu vorhandenen Typen „hinzuzufügen“, ohne sie tatsächlich zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f4594-129">This feature enables you to, in effect, "add" new methods to existing types without actually modifying them.</span></span> <span data-ttu-id="f4594-130">Die Standardabfrageoperatoren sind eine Reihe von Erweiterungsmethoden, die [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfragefunktionen für jeden Typ bieten, der <xref:System.Collections.Generic.IEnumerable%601> implementiert.</span><span class="sxs-lookup"><span data-stu-id="f4594-130">The standard query operators are a set of extension methods that provide [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query functionality for any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  
  
 <span data-ttu-id="f4594-131">Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="f4594-131">For more information, see [Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span>  
  
## <a name="lambda-expressions"></a><span data-ttu-id="f4594-132">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="f4594-132">Lambda Expressions</span></span>  
 <span data-ttu-id="f4594-133">Ein Lambdaausdruck ist eine Inlinefunktion, die den Operator => verwendet, um Eingabeparameter vom Funktionstext zu trennen, und die zur Kompilierzeit in einen Delegaten oder eine Ausdrucksbaumstruktur konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f4594-133">A lambda expression is an inline function that uses the => operator to separate input parameters from the function body and can be converted at compile time to a delegate or an expression tree.</span></span> <span data-ttu-id="f4594-134">In der [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Programmierung erhalten Sie Lambdaausdrücke, wenn Sie direkte Methodenaufrufe für die Standardabfrageoperatoren vornehmen.</span><span class="sxs-lookup"><span data-stu-id="f4594-134">In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] programming, you will encounter lambda expressions when you make direct method calls to the standard query operators.</span></span>  
  
 <span data-ttu-id="f4594-135">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="f4594-135">For more information, see:</span></span>  
  
-   [<span data-ttu-id="f4594-136">Anonyme Funktionen</span><span class="sxs-lookup"><span data-stu-id="f4594-136">Anonymous Functions</span></span>](../../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [<span data-ttu-id="f4594-137">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="f4594-137">Lambda Expressions</span></span>](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
  
-   [<span data-ttu-id="f4594-138">Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="f4594-138">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)  
  
## <a name="auto-implemented-properties"></a><span data-ttu-id="f4594-139">Automatisch implementierte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f4594-139">Auto-Implemented Properties</span></span>  
 <span data-ttu-id="f4594-140">Automatisch implementierte Eigenschaften machen die Eigenschaftendeklaration präziser.</span><span class="sxs-lookup"><span data-stu-id="f4594-140">Auto-implemented properties make property-declaration more concise.</span></span> <span data-ttu-id="f4594-141">Wenn Sie eine Eigenschaft wie im folgenden Beispiel gezeigt deklarieren, wird der Compiler ein privates, anonymes Unterstützungsfeld erstellen, auf das nur durch die Getter und Setter der Eigenschaft zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f4594-141">When you declare a property as shown in the following example, the compiler will create a private, anonymous backing field that is not accessible except through the property getter and setter.</span></span>  
  
```  
public string Name {get; set;}  
```  
  
 <span data-ttu-id="f4594-142">Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f4594-142">For more information, see [Auto-Implemented Properties](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4594-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4594-143">See Also</span></span>  
 [<span data-ttu-id="f4594-144">Language-Integrated Query (LINQ) (Sprachintegrierte Abfrage (LINQ))</span><span class="sxs-lookup"><span data-stu-id="f4594-144">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)
