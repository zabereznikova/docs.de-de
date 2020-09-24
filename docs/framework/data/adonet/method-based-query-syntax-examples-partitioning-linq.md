---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Partitionierung (LINQ)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a582c53f-f203-44ae-a797-d7f169a4fbb5
ms.openlocfilehash: 0ef7176ccffb7037a7d4496cc7d4da7991741d38
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147930"
---
# <a name="method-based-query-syntax-examples-partitioning-linq"></a><span data-ttu-id="9bd38-102">Beispiele für die methodenbasierte Abfragesyntax: Partitionierung (LINQ)</span><span class="sxs-lookup"><span data-stu-id="9bd38-102">Method-Based Query Syntax Examples: Partitioning (LINQ</span></span>

<span data-ttu-id="9bd38-103">Die Beispiele in diesem Thema zeigen, wie Sie mit der <xref:System.Linq.Enumerable.Skip%2A>-Methode, der <xref:System.Linq.Enumerable.SkipWhile%2A>-Methode, der <xref:System.Linq.Enumerable.Take%2A>-Methode und der <xref:System.Linq.Enumerable.TakeWhile%2A>-Methode und mithilfe der Abfrageausdruckssyntax ein <xref:System.Data.DataSet> abfragen können.</span><span class="sxs-lookup"><span data-stu-id="9bd38-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A>, <xref:System.Linq.Enumerable.Take%2A>, and <xref:System.Linq.Enumerable.TakeWhile%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="9bd38-104">Die `FillDataSet` in diesen Beispielen verwendete Methode wird beim [Laden von Daten in ein DataSet](loading-data-into-a-dataset.md)angegeben.</span><span class="sxs-lookup"><span data-stu-id="9bd38-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="9bd38-105">In den Beispielen in diesem Thema wird auf die Tabellen &lt;legacyBold&gt;Contact&lt;/legacyBold&gt;, &lt;legacyBold&gt;Address&lt;/legacyBold&gt;, &lt;legacyBold&gt;Product&lt;/legacyBold&gt;, &lt;legacyBold&gt;SalesOrderHeader&lt;/legacyBold&gt; und &lt;legacyBold&gt;SalesOrderDetail&lt;/legacyBold&gt; in der &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="9bd38-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="9bd38-106">In den Beispielen in diesem Thema werden die folgenden- `using` / `Imports` Anweisungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="9bd38-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="9bd38-107">Weitere Informationen finden Sie unter Gewusst [wie: Erstellen eines LINQ to DataSet Projekts in Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="9bd38-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="skip"></a><span data-ttu-id="9bd38-108">Überspringen</span><span class="sxs-lookup"><span data-stu-id="9bd38-108">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="9bd38-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9bd38-109">Example</span></span>  

 <span data-ttu-id="9bd38-110">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Skip%2A>-Methode verwendet, um, mit Ausnahme der ersten fünf Kontakte, alle Kontakte in der `Contact`-Tabelle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9bd38-110">This example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first five contacts of the `Contact` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipsimple)]
 [!code-vb[DP LINQ to DataSet Examples#SkipSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipsimple)]  
  
### <a name="example"></a><span data-ttu-id="9bd38-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9bd38-111">Example</span></span>  

 <span data-ttu-id="9bd38-112">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Skip%2A>-Methode verwendet, um, mit Ausnahme der ersten beiden Adressen, alle Adressen in Seattle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9bd38-112">This example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipnested)]  
  
## <a name="skipwhile"></a><span data-ttu-id="9bd38-113">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="9bd38-113">SkipWhile</span></span>  
  
### <a name="example"></a><span data-ttu-id="9bd38-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9bd38-114">Example</span></span>  

 <span data-ttu-id="9bd38-115">In diesem Beispiel werden die Methoden <xref:System.Linq.Enumerable.OrderBy%2A> und <xref:System.Linq.Enumerable.SkipWhile%2A> verwendet, um aus der `Product`-Tabelle alle Produkte abzurufen, deren Listenpreis größer als 300.00 ist.</span><span class="sxs-lookup"><span data-stu-id="9bd38-115">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.SkipWhile%2A> methods to return products from the `Product` table with a list price greater than 300.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipWhileSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipwhilesimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SkipWhileSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipwhilesimple_mq)]  
  
## <a name="take"></a><span data-ttu-id="9bd38-116">Take</span><span class="sxs-lookup"><span data-stu-id="9bd38-116">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="9bd38-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9bd38-117">Example</span></span>  

 <span data-ttu-id="9bd38-118">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Take%2A>-Methode verwendet, um nur die ersten fünf Kontakte aus der `Contact`-Tabelle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9bd38-118">This example uses the <xref:System.Linq.Enumerable.Take%2A> method to get only the first five contacts from the `Contact` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takesimple)]
 [!code-vb[DP LINQ to DataSet Examples#TakeSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takesimple)]  
  
### <a name="example"></a><span data-ttu-id="9bd38-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9bd38-119">Example</span></span>  

 <span data-ttu-id="9bd38-120">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Take%2A>-Methode verwendet, um die ersten drei Adressen in Seattle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9bd38-120">This example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takenested)]
 [!code-vb[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takenested)]  
  
## <a name="takewhile"></a><span data-ttu-id="9bd38-121">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="9bd38-121">TakeWhile</span></span>  
  
### <a name="example"></a><span data-ttu-id="9bd38-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9bd38-122">Example</span></span>  

 <span data-ttu-id="9bd38-123">In diesem Beispiel werden die Methoden <xref:System.Linq.Enumerable.OrderBy%2A> und <xref:System.Linq.Enumerable.TakeWhile%2A> verwendet, um aus der `Product`-Tabelle alle Produkte abzurufen, deren Listenpreis kleiner als 300.00 ist.</span><span class="sxs-lookup"><span data-stu-id="9bd38-123">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.TakeWhile%2A> to return products from the `Product` table with a list price less than 300.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeWhileSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takewhilesimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#TakeWhileSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takewhilesimple_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="9bd38-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9bd38-124">See also</span></span>

- [<span data-ttu-id="9bd38-125">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="9bd38-125">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="9bd38-126">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="9bd38-126">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="9bd38-127">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="9bd38-127">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="9bd38-128">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="9bd38-128">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
