---
title: 'Beispiele für die Abfrageausdruckssyntax: Einschränkung (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1daf42c2-c9f4-4cda-b291-7641b9c6d3fe
ms.openlocfilehash: 04a7b2027ac956d14086f94527b10d253749949d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794666"
---
# <a name="query-expression-syntax-examples-restriction-linq-to-dataset"></a><span data-ttu-id="5d01b-102">Beispiele für die Abfrageausdruckssyntax: Einschränkung (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="5d01b-102">Query Expression Syntax Examples: Restriction (LINQ to DataSet)</span></span>
<span data-ttu-id="5d01b-103">In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der <xref:System.Linq.Enumerable.Where%2A>-Methode und der Abfrageausdruckssyntax ein <xref:System.Data.DataSet> abfragen können.</span><span class="sxs-lookup"><span data-stu-id="5d01b-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Where%2A> method to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="5d01b-104">Die `FillDataSet` in diesen Beispielen verwendete Methode wird beim [Laden von Daten in ein DataSet](loading-data-into-a-dataset.md)angegeben.</span><span class="sxs-lookup"><span data-stu-id="5d01b-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="5d01b-105">In den Beispielen in diesem Thema wird auf die Tabellen &lt;legacyBold&gt;Contact&lt;/legacyBold&gt;, &lt;legacyBold&gt;Address&lt;/legacyBold&gt;, &lt;legacyBold&gt;Product&lt;/legacyBold&gt;, &lt;legacyBold&gt;SalesOrderHeader&lt;/legacyBold&gt; und &lt;legacyBold&gt;SalesOrderDetail&lt;/legacyBold&gt; in der &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="5d01b-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="5d01b-106">In den Beispielen in diesem Thema werden die `using` folgenden / `Imports` -Anweisungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="5d01b-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
[!code-csharp[DP LINQ to DataSetExamples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]        
  
 <span data-ttu-id="5d01b-107">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie in Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md)ein LINQ to DataSet Projekt.</span><span class="sxs-lookup"><span data-stu-id="5d01b-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="where"></a><span data-ttu-id="5d01b-108">Where</span><span class="sxs-lookup"><span data-stu-id="5d01b-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="5d01b-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d01b-109">Example</span></span>  
 <span data-ttu-id="5d01b-110">In diesem Beispiel werden alle Onlinebestellungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5d01b-110">This example returns all online orders.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]  
 [!code-vb[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)]     
  
### <a name="example"></a><span data-ttu-id="5d01b-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d01b-111">Example</span></span>  
 <span data-ttu-id="5d01b-112">In diesem Beispiel werden die Aufträge zurückgegeben, bei denen die Bestellmenge größer als 2 und kleiner als 6 ist.</span><span class="sxs-lookup"><span data-stu-id="5d01b-112">This example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where2)]  
 [!code-vb[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where2)]     
  
### <a name="example"></a><span data-ttu-id="5d01b-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d01b-113">Example</span></span>  
 <span data-ttu-id="5d01b-114">In diesem Beispiel werden alle Produkte mit roter Farbe zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5d01b-114">This example returns all red colored products.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]  
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]     
  
### <a name="example"></a><span data-ttu-id="5d01b-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d01b-115">Example</span></span>  
 <span data-ttu-id="5d01b-116">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Where%2A>-Methode verwendet, um Aufträge zu finden, die nach dem 1. Dezember 2002 eingegangen sind. Anschließend kommt die <xref:System.Data.DataRow.GetChildRows%2A>-Methode zum Einsatz, um die Details zu den einzelnen Aufträgen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5d01b-116">This example uses the <xref:System.Linq.Enumerable.Where%2A> method to find orders that were made after December 1, 2002 and then uses the <xref:System.Data.DataRow.GetChildRows%2A> method to get the details for each order.</span></span>  
  
 [!code-csharp[DP LINQ to DataSetExamples#WhereDrillDown](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#wheredrilldown)]       
 [!code-vb[DP LINQ to DataSet Examples#WhereDrillDown](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#wheredrilldown)]  
  
## <a name="see-also"></a><span data-ttu-id="5d01b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d01b-117">See also</span></span>

- [<span data-ttu-id="5d01b-118">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="5d01b-118">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="5d01b-119">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="5d01b-119">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="5d01b-120">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="5d01b-120">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="5d01b-121">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="5d01b-121">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
