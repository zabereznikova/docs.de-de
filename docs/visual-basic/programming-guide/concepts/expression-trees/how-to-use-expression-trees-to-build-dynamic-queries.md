---
title: 'Gewusst wie: Verwenden von Ausdrucksbaumstrukturen zum Erstellen dynamischer Abfragen (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8d69be78a9f3568535dffe54e21af80c6eb12f70
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-visual-basic"></a><span data-ttu-id="213b4-102">Gewusst wie: Verwenden von Ausdrucksbaumstrukturen zum Erstellen dynamischer Abfragen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="213b4-102">How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)</span></span>
<span data-ttu-id="213b4-103">In LINQ sind Ausdrucksbaumstrukturen strukturierten Abfragen dieses Ziel Datenquellen dar, die implementieren <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> verwendet.</span><span class="sxs-lookup"><span data-stu-id="213b4-103">In LINQ, expression trees are used to represent structured queries that target sources of data that implement <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="213b4-104">Angenommen, der LINQ-Anbieter implementiert die <xref:System.Linq.IQueryable%601>-Schnittstelle für das Abfragen relationaler Datenspeicher.</xref:System.Linq.IQueryable%601></span><span class="sxs-lookup"><span data-stu-id="213b4-104">For example, the LINQ provider implements the <xref:System.Linq.IQueryable%601> interface for querying relational data stores.</span></span> <span data-ttu-id="213b4-105">Visual Basic-Compiler kompiliert, Abfragen, die diese Datenquellen in Code zu verwenden, die zur Laufzeit eine Ausdrucksbaumstruktur erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="213b4-105">The Visual Basic compiler compiles queries that target such data sources into code that builds an expression tree at runtime.</span></span> <span data-ttu-id="213b4-106">Der Abfrageanbieter kann die Datenstruktur des Ausdruck-Struktur durchlaufen und in eine Abfragesprache entsprechend für die Datenquelle zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="213b4-106">The query provider can then traverse the expression tree data structure and translate it into a query language appropriate for the data source.</span></span>  
  
 <span data-ttu-id="213b4-107">Ausdrucksbaumstrukturen werden auch in LINQ verwendet, Lambda-Ausdrücke dar, die Variablen des Typs <xref:System.Linq.Expressions.Expression%601>.</xref:System.Linq.Expressions.Expression%601> zugewiesen sind</span><span class="sxs-lookup"><span data-stu-id="213b4-107">Expression trees are also used in LINQ to represent lambda expressions that are assigned to variables of type <xref:System.Linq.Expressions.Expression%601>.</span></span>  
  
 <span data-ttu-id="213b4-108">Dieses Thema beschreibt, wie Sie Ausdrucksbaumstrukturen dynamische LINQ-Abfragen erstellen.</span><span class="sxs-lookup"><span data-stu-id="213b4-108">This topic describes how to use expression trees to create dynamic LINQ queries.</span></span> <span data-ttu-id="213b4-109">Dynamische Abfragen sind nützlich, wenn die Einzelheiten einer Abfrage zur Kompilierzeit nicht bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="213b4-109">Dynamic queries are useful when the specifics of a query are not known at compile time.</span></span> <span data-ttu-id="213b4-110">Beispielsweise kann eine Anwendung eine Benutzeroberfläche bereitstellen, mit der der Endbenutzer eines oder mehrere Prädikate zum Filtern der Daten festlegen können.</span><span class="sxs-lookup"><span data-stu-id="213b4-110">For example, an application might provide a user interface that enables the end user to specify one or more predicates to filter the data.</span></span> <span data-ttu-id="213b4-111">LINQ für Abfragen verwenden möchten, muss dieser Anwendungstyp Ausdrucksbaumstrukturen verwenden, die LINQ-Abfrage zur Laufzeit erstellt.</span><span class="sxs-lookup"><span data-stu-id="213b4-111">In order to use LINQ for querying, this kind of application must use expression trees to create the LINQ query at runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="213b4-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="213b4-112">Example</span></span>  
 <span data-ttu-id="213b4-113">Das folgende Beispiel veranschaulicht das Ausdrucksbaumstrukturen verwenden, erstellen Sie eine Abfrage für ein `IQueryable` Datenquelle und dann ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="213b4-113">The following example shows you how to use expression trees to construct a query against an `IQueryable` data source and then execute it.</span></span> <span data-ttu-id="213b4-114">Der Code erstellt eine Ausdrucksbaumstruktur, um die Darstellung der folgenden Abfrage:</span><span class="sxs-lookup"><span data-stu-id="213b4-114">The code builds an expression tree to represent the following query:</span></span>  
  
 `companies.Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16).OrderBy(Function(company) company)`  
  
 <span data-ttu-id="213b4-115">Die Methoden in der <xref:System.Linq.Expressions>Namespace werden zum Erstellen von Ausdrucksbaumstrukturen, die die Ausdrücke darstellen, aus denen die gesamte Abfrage zusammensetzt.</xref:System.Linq.Expressions></span><span class="sxs-lookup"><span data-stu-id="213b4-115">The factory methods in the <xref:System.Linq.Expressions> namespace are used to create expression trees that represent the expressions that make up the overall query.</span></span> <span data-ttu-id="213b4-116">Die Ausdrücke, die Aufrufe an die Standardabfrageoperator-Methoden darstellen, finden Sie in der <xref:System.Linq.Queryable>Implementierungen dieser Methoden.</xref:System.Linq.Queryable></span><span class="sxs-lookup"><span data-stu-id="213b4-116">The expressions that represent calls to the standard query operator methods refer to the <xref:System.Linq.Queryable> implementations of these methods.</span></span> <span data-ttu-id="213b4-117">Die endgültige Ausdrucksbaumstruktur wird zum Übergeben der <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29>Implementierung des Anbieters von den `IQueryable` -Datenquelle, um eine ausführbare Abfrage vom Typ erstellen `IQueryable`.</xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29></span><span class="sxs-lookup"><span data-stu-id="213b4-117">The final expression tree is passed to the <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> implementation of the provider of the `IQueryable` data source to create an executable query of type `IQueryable`.</span></span> <span data-ttu-id="213b4-118">Die Ergebnisse werden abgerufen, indem diese Abfragevariable aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="213b4-118">The results are obtained by enumerating that query variable.</span></span>  
  
<span data-ttu-id="213b4-119"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="213b4-119"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="213b4-120">Dieser Code verwendet eine feste Anzahl von Ausdrücken in das Prädikat, das an die `Queryable.Where` Methode.</span><span class="sxs-lookup"><span data-stu-id="213b4-120">This code uses a fixed number of expressions in the predicate that is passed to the `Queryable.Where` method.</span></span> <span data-ttu-id="213b4-121">Allerdings können Sie eine Anwendung schreiben, die eine Variable Anzahl von Prädikatausdrücken kombiniert, die von der Benutzereingabe abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="213b4-121">However, you can write an application that combines a variable number of predicate expressions that depends on the user input.</span></span> <span data-ttu-id="213b4-122">Sie können auch die Standardabfrageoperatoren variieren, die in der Abfrage abhängig von der Eingabe vom Benutzer aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="213b4-122">You can also vary the standard query operators that are called in the query, depending on the input from the user.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="213b4-123">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="213b4-123">Compiling the Code</span></span>  
  
-   <span data-ttu-id="213b4-124">Erstellen Sie ein neues **Konsolenanwendung** Projekt.</span><span class="sxs-lookup"><span data-stu-id="213b4-124">Create a new **Console Application** project.</span></span>  
  
-   <span data-ttu-id="213b4-125">Fügen Sie einen Verweis auf System.Core.dll hinzu, wenn es nicht bereits verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="213b4-125">Add a reference to System.Core.dll if it is not already referenced.</span></span>  
  
-   <span data-ttu-id="213b4-126">Schließen Sie den System.Linq.Expressions-Namespace.</span><span class="sxs-lookup"><span data-stu-id="213b4-126">Include the System.Linq.Expressions namespace.</span></span>  
  
-   <span data-ttu-id="213b4-127">Kopieren Sie den Code aus dem Beispiel, und fügen Sie ihn in die `Main` `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="213b4-127">Copy the code from the example and paste it into the `Main` `Sub` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="213b4-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="213b4-128">See Also</span></span>  
 <span data-ttu-id="213b4-129">[Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span><span class="sxs-lookup"><span data-stu-id="213b4-129">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span></span>  
<span data-ttu-id="213b4-130"> [Gewusst wie: Ausführen von Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)</span><span class="sxs-lookup"><span data-stu-id="213b4-130"> [How to: Execute Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)</span></span>
