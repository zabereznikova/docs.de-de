---
title: 'Vorgehensweise: Verwenden von Ausdrucksbaumstrukturen zum Erstellen dynamischer Abfragen (C#)'
ms.date: 07/20/2015
ms.assetid: 52cd44dd-a3ec-441e-b93a-4eca388119c7
ms.openlocfilehash: 6114ec13dd43a7df146b87dda00fba06d6eb870c
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635898"
---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-c"></a><span data-ttu-id="3e7d4-102">Vorgehensweise: Verwenden von Ausdrucksbaumstrukturen zum Erstellen dynamischer Abfragen (C#)</span><span class="sxs-lookup"><span data-stu-id="3e7d4-102">How to use expression trees to build dynamic queries (C#)</span></span>
<span data-ttu-id="3e7d4-103">Ausdrucksbaumstrukturen werden in LINQ dazu verwendet, strukturierte Abfragen für Datenquellen zu repräsentieren, die <xref:System.Linq.IQueryable%601> implementieren.</span><span class="sxs-lookup"><span data-stu-id="3e7d4-103">In LINQ, expression trees are used to represent structured queries that target sources of data that implement <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="3e7d4-104">Der LINQ-Anbieter implementiert z.B. die <xref:System.Linq.IQueryable%601>-Schnittstelle, um relationale Datenspeicher abzufragen.</span><span class="sxs-lookup"><span data-stu-id="3e7d4-104">For example, the LINQ provider implements the <xref:System.Linq.IQueryable%601> interface for querying relational data stores.</span></span> <span data-ttu-id="3e7d4-105">Die Compiler für C# kompilieren Abfragen solcher Datenquellen in Code, der zur Laufzeit eine Ausdrucksbaumstruktur erzeugt.</span><span class="sxs-lookup"><span data-stu-id="3e7d4-105">The C# compiler compiles queries that target such data sources into code that builds an expression tree at runtime.</span></span> <span data-ttu-id="3e7d4-106">Anschließend kann der Abfrageanbieter die Datenstruktur der Ausdrucksbaumstruktur durchlaufen und in eine für die Datenquelle geeignete Abfragesprache übersetzen.</span><span class="sxs-lookup"><span data-stu-id="3e7d4-106">The query provider can then traverse the expression tree data structure and translate it into a query language appropriate for the data source.</span></span>  
  
 <span data-ttu-id="3e7d4-107">Ausdrucksbaumstrukturen werden in LINQ außerdem dazu verwendet, Lambdaausdrücke zu repräsentieren, die Variablen den Typs <xref:System.Linq.Expressions.Expression%601> zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="3e7d4-107">Expression trees are also used in LINQ to represent lambda expressions that are assigned to variables of type <xref:System.Linq.Expressions.Expression%601>.</span></span>  
  
 <span data-ttu-id="3e7d4-108">In diesem Thema wird erläutert, wie Sie Ausdrucksbaumstrukturen verwenden können, um dynamische LINQ-Abfragen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3e7d4-108">This topic describes how to use expression trees to create dynamic LINQ queries.</span></span> <span data-ttu-id="3e7d4-109">Dynamische Abfragen sind nützlich, wenn die Eigenschaften einer Abfrage zur Kompilierzeit nicht bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="3e7d4-109">Dynamic queries are useful when the specifics of a query are not known at compile time.</span></span> <span data-ttu-id="3e7d4-110">Beispielsweise kann eine Anwendung über eine Benutzeroberfläche verfügen, in der der Endbenutzer ein oder mehrere Prädikate zum Filtern der Daten angeben kann.</span><span class="sxs-lookup"><span data-stu-id="3e7d4-110">For example, an application might provide a user interface that enables the end user to specify one or more predicates to filter the data.</span></span> <span data-ttu-id="3e7d4-111">Damit LINQ für Abfragen verwendet werden kann, muss solch eine Anwendung Ausdrucksbaumstrukturen benutzen, um die LINQ-Abfrage zur Laufzeit zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3e7d4-111">In order to use LINQ for querying, this kind of application must use expression trees to create the LINQ query at runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e7d4-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3e7d4-112">Example</span></span>  
 <span data-ttu-id="3e7d4-113">In folgendem Beispiel erfahren Sie, wie Sie Ausdrucksbaumstrukturen zur Konstruktion einer Abfrage anhand einer `IQueryable`-Datenquelle verwenden und diese anschließend ausführen können.</span><span class="sxs-lookup"><span data-stu-id="3e7d4-113">The following example shows you how to use expression trees to construct a query against an `IQueryable` data source and then execute it.</span></span> <span data-ttu-id="3e7d4-114">Im Code wird eine Ausdrucksbaumstruktur erstellt, welche die folgende Abfrage darstellt:</span><span class="sxs-lookup"><span data-stu-id="3e7d4-114">The code builds an expression tree to represent the following query:</span></span>  
  
 ```csharp
 companies.Where(company => (company.ToLower() == "coho winery" || company.Length > 16))
          .OrderBy(company => company)
 ```
  
 <span data-ttu-id="3e7d4-115">Die Factorymethoden im <xref:System.Linq.Expressions>-Namespace werden zum Erstellen von Ausdrucksbaumstrukturen verwendet, die Ausdrücke repräsentieren, aus denen die Abfrage besteht.</span><span class="sxs-lookup"><span data-stu-id="3e7d4-115">The factory methods in the <xref:System.Linq.Expressions> namespace are used to create expression trees that represent the expressions that make up the overall query.</span></span> <span data-ttu-id="3e7d4-116">Die Ausdrücke, die Aufrufe an die Methoden des Standardabfrageoperators repräsentieren, verweisen auf die <xref:System.Linq.Queryable>-Implementierung dieser Methoden.</span><span class="sxs-lookup"><span data-stu-id="3e7d4-116">The expressions that represent calls to the standard query operator methods refer to the <xref:System.Linq.Queryable> implementations of these methods.</span></span> <span data-ttu-id="3e7d4-117">Die letzte Verzeichnisstruktur wird an die <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29>-Implementierung des Anbieters der `IQueryable`-Datenquelle übergeben, um eine ausführbare Abfrage des Typs `IQueryable` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3e7d4-117">The final expression tree is passed to the <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> implementation of the provider of the `IQueryable` data source to create an executable query of type `IQueryable`.</span></span> <span data-ttu-id="3e7d4-118">Sie erhalten die Ergebnisse via Zugriff auf die Auflistung der Abfrageergebnisse.</span><span class="sxs-lookup"><span data-stu-id="3e7d4-118">The results are obtained by enumerating that query variable.</span></span>  
  
```csharp  
// Add a using directive for System.Linq.Expressions.  
  
string[] companies = { "Consolidated Messenger", "Alpine Ski House", "Southridge Video", "City Power & Light",  
                   "Coho Winery", "Wide World Importers", "Graphic Design Institute", "Adventure Works",  
                   "Humongous Insurance", "Woodgrove Bank", "Margie's Travel", "Northwind Traders",  
                   "Blue Yonder Airlines", "Trey Research", "The Phone Company",  
                   "Wingtip Toys", "Lucerne Publishing", "Fourth Coffee" };  
  
// The IQueryable data to query.  
IQueryable<String> queryableData = companies.AsQueryable<string>();  
  
// Compose the expression tree that represents the parameter to the predicate.  
ParameterExpression pe = Expression.Parameter(typeof(string), "company");  
  
// ***** Where(company => (company.ToLower() == "coho winery" || company.Length > 16)) *****  
// Create an expression tree that represents the expression 'company.ToLower() == "coho winery"'.  
Expression left = Expression.Call(pe, typeof(string).GetMethod("ToLower", System.Type.EmptyTypes));  
Expression right = Expression.Constant("coho winery");  
Expression e1 = Expression.Equal(left, right);  
  
// Create an expression tree that represents the expression 'company.Length > 16'.  
left = Expression.Property(pe, typeof(string).GetProperty("Length"));  
right = Expression.Constant(16, typeof(int));  
Expression e2 = Expression.GreaterThan(left, right);  
  
// Combine the expression trees to create an expression tree that represents the  
// expression '(company.ToLower() == "coho winery" || company.Length > 16)'.  
Expression predicateBody = Expression.OrElse(e1, e2);  
  
// Create an expression tree that represents the expression  
// 'queryableData.Where(company => (company.ToLower() == "coho winery" || company.Length > 16))'  
MethodCallExpression whereCallExpression = Expression.Call(  
    typeof(Queryable),  
    "Where",  
    new Type[] { queryableData.ElementType },  
    queryableData.Expression,  
    Expression.Lambda<Func<string, bool>>(predicateBody, new ParameterExpression[] { pe }));  
// ***** End Where *****  
  
// ***** OrderBy(company => company) *****  
// Create an expression tree that represents the expression  
// 'whereCallExpression.OrderBy(company => company)'  
MethodCallExpression orderByCallExpression = Expression.Call(  
    typeof(Queryable),  
    "OrderBy",  
    new Type[] { queryableData.ElementType, queryableData.ElementType },  
    whereCallExpression,  
    Expression.Lambda<Func<string, string>>(pe, new ParameterExpression[] { pe }));  
// ***** End OrderBy *****  
  
// Create an executable query from the expression tree.  
IQueryable<string> results = queryableData.Provider.CreateQuery<string>(orderByCallExpression);  
  
// Enumerate the results.  
foreach (string company in results)  
    Console.WriteLine(company);  
  
/*  This code produces the following output:  
  
    Blue Yonder Airlines  
    City Power & Light  
    Coho Winery  
    Consolidated Messenger  
    Graphic Design Institute  
    Humongous Insurance  
    Lucerne Publishing  
    Northwind Traders  
    The Phone Company  
    Wide World Importers  
*/  
```  
  
 <span data-ttu-id="3e7d4-119">In diesem Code wird in dem an die `Queryable.Where`-Methode übergebenen Prädikat eine feste Anzahl von Ausdrücken verwendet.</span><span class="sxs-lookup"><span data-stu-id="3e7d4-119">This code uses a fixed number of expressions in the predicate that is passed to the `Queryable.Where` method.</span></span> <span data-ttu-id="3e7d4-120">Sie können allerdings eine Anwendung schreiben, die eine variable Zahl von Prädikatausdrücken miteinander vereint; diese Zahl ist von der Benutzereingabe abhängig.</span><span class="sxs-lookup"><span data-stu-id="3e7d4-120">However, you can write an application that combines a variable number of predicate expressions that depends on the user input.</span></span> <span data-ttu-id="3e7d4-121">Sie können auch die Standardabfrageoperatoren variieren, die in der Abfrage aufgerufen werden; dies ist ebenfalls von der Benutzereingabe abhängig.</span><span class="sxs-lookup"><span data-stu-id="3e7d4-121">You can also vary the standard query operators that are called in the query, depending on the input from the user.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3e7d4-122">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="3e7d4-122">Compiling the Code</span></span>  
  
- <span data-ttu-id="3e7d4-123">Binden Sie den System.Linq.Expressions-Namespace ein.</span><span class="sxs-lookup"><span data-stu-id="3e7d4-123">Include the System.Linq.Expressions namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e7d4-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e7d4-124">See also</span></span>

- [<span data-ttu-id="3e7d4-125">Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="3e7d4-125">Expression Trees (C#)</span></span>](./index.md)
- [<span data-ttu-id="3e7d4-126">Ausführen von Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="3e7d4-126">How to execute expression trees (C#)</span></span>](./how-to-execute-expression-trees.md)
- [<span data-ttu-id="3e7d4-127">Dynamisches Festlegen von Prädikatfiltern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="3e7d4-127">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
