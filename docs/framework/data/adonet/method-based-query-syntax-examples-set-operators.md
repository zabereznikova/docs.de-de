---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Set-Operatoren (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
ms.openlocfilehash: f91d009e66f1f0da25e508994040d7e9f80fc681
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147865"
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a><span data-ttu-id="afd32-102">Beispiele für die methodenbasierte Abfragesyntax: Set-Operatoren (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="afd32-102">Method-Based Query Syntax Examples: Set Operators (LINQ to DataSet)</span></span>

<span data-ttu-id="afd32-103">In den Beispielen in diesem Thema wird gezeigt, wie <xref:System.Linq.Enumerable.Distinct%2A> die <xref:System.Linq.Enumerable.Except%2A> Operatoren,, und verwendet werden, <xref:System.Linq.Enumerable.Intersect%2A> <xref:System.Linq.Enumerable.Union%2A> um wertebasierte Vergleichs Vorgänge für Sätze von Daten Zeilen auszuführen.[ Zum Laden von Daten in ein DataSet](loading-data-into-a-dataset.md) finden Sie unter [Vergleichen von DataRows](comparing-datarows-linq-to-dataset.md) mit weiteren Informationen zu <xref:System.Data.DataRowComparer> .</span><span class="sxs-lookup"><span data-stu-id="afd32-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, and <xref:System.Linq.Enumerable.Union%2A> operators to perform value-based comparison operations on sets of data rows.[Loading Data Into a DataSet](loading-data-into-a-dataset.md) See [Comparing DataRows](comparing-datarows-linq-to-dataset.md) for more information on <xref:System.Data.DataRowComparer>.</span></span>  
  
 <span data-ttu-id="afd32-104">Die `FillDataSet` in diesen Beispielen verwendete Methode wird beim [Laden von Daten in ein DataSet](loading-data-into-a-dataset.md)angegeben.</span><span class="sxs-lookup"><span data-stu-id="afd32-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="afd32-105">In den Beispielen in diesem Thema wird auf die Tabellen &lt;legacyBold&gt;Contact&lt;/legacyBold&gt;, &lt;legacyBold&gt;Address&lt;/legacyBold&gt;, &lt;legacyBold&gt;Product&lt;/legacyBold&gt;, &lt;legacyBold&gt;SalesOrderHeader&lt;/legacyBold&gt; und &lt;legacyBold&gt;SalesOrderDetail&lt;/legacyBold&gt; in der &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="afd32-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="afd32-106">In den Beispielen in diesem Thema werden die folgenden- `using` / `Imports` Anweisungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="afd32-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="afd32-107">Weitere Informationen finden Sie unter Gewusst [wie: Erstellen eines LINQ to DataSet Projekts in Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="afd32-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="distinct"></a><span data-ttu-id="afd32-108">Distinct</span><span class="sxs-lookup"><span data-stu-id="afd32-108">Distinct</span></span>  
  
### <a name="example"></a><span data-ttu-id="afd32-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="afd32-109">Example</span></span>  

 <span data-ttu-id="afd32-110">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Distinct%2A>-Methode verwendet, um doppelte Elemente in einer Sequenz zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="afd32-110">This example uses the <xref:System.Linq.Enumerable.Distinct%2A> method to remove duplicate elements in a sequence.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a><span data-ttu-id="afd32-111">Except</span><span class="sxs-lookup"><span data-stu-id="afd32-111">Except</span></span>  
  
### <a name="example"></a><span data-ttu-id="afd32-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="afd32-112">Example</span></span>  

 <span data-ttu-id="afd32-113">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Except%2A>-Methode verwendet, um die Kontakte abzurufen, die zwar in der ersten, nicht aber in der zweiten Tabelle aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="afd32-113">This example uses the <xref:System.Linq.Enumerable.Except%2A> method to return contacts that appear in the first table but not in the second.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a><span data-ttu-id="afd32-114">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="afd32-114">Intersect</span></span>  
  
### <a name="example"></a><span data-ttu-id="afd32-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="afd32-115">Example</span></span>  

 <span data-ttu-id="afd32-116">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Intersect%2A>-Methode verwendet, um die Kontakte abzurufen, die in beiden Tabellen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="afd32-116">This example uses the <xref:System.Linq.Enumerable.Intersect%2A> method to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a><span data-ttu-id="afd32-117">Union</span><span class="sxs-lookup"><span data-stu-id="afd32-117">Union</span></span>  
  
### <a name="example"></a><span data-ttu-id="afd32-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="afd32-118">Example</span></span>  

 <span data-ttu-id="afd32-119">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Union%2A>-Methode verwendet, um die Kontakte abzurufen, die in nur einer der beiden Tabellen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="afd32-119">This example uses the <xref:System.Linq.Enumerable.Union%2A> method to return unique contacts from either of the two tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a><span data-ttu-id="afd32-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="afd32-120">See also</span></span>

- [<span data-ttu-id="afd32-121">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="afd32-121">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="afd32-122">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="afd32-122">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="afd32-123">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="afd32-123">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="afd32-124">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="afd32-124">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
