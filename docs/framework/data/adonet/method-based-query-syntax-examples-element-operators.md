---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Elementoperatoren (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eedf2fbd-f407-4f62-bb1a-c00eb001b1dd
ms.openlocfilehash: e43208d6ae524a1370b936d42508e9c7a7d196e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149506"
---
# <a name="method-based-query-syntax-examples-element-operators-linq-to-dataset"></a><span data-ttu-id="1781d-102">Beispiele für die methodenbasierte Abfragesyntax: Elementoperatoren (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="1781d-102">Method-Based Query Syntax Examples: Element Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="1781d-103">In den Beispielen in diesem Thema wird gezeigt, wie Sie mit der <xref:System.Linq.Enumerable.First%2A>-Methode und der <xref:System.Linq.Enumerable.ElementAt%2A>-Methode und mithilfe der Abfrageausdruckssyntax <xref:System.Data.DataRow>-Elemente aus einem <xref:System.Data.DataSet> abrufen können.</span><span class="sxs-lookup"><span data-stu-id="1781d-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="1781d-104">Die `FillDataSet` in diesen Beispielen verwendete Methode wird unter [Laden von Daten in ein DataSet](loading-data-into-a-dataset.md)angegeben.</span><span class="sxs-lookup"><span data-stu-id="1781d-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="1781d-105">In den Beispielen in diesem Thema wird auf die Tabellen &lt;legacyBold&gt;Contact&lt;/legacyBold&gt;, &lt;legacyBold&gt;Address&lt;/legacyBold&gt;, &lt;legacyBold&gt;Product&lt;/legacyBold&gt;, &lt;legacyBold&gt;SalesOrderHeader&lt;/legacyBold&gt; und &lt;legacyBold&gt;SalesOrderDetail&lt;/legacyBold&gt; in der &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="1781d-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="1781d-106">Die Beispiele in diesem `using` / `Imports` Thema verwenden die folgenden Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="1781d-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
[!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]

 <span data-ttu-id="1781d-107">Weitere Informationen finden Sie unter [Gewusst wie: Erstellen eines LINQ-zu-DataSet-Projekts in Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="1781d-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="elementat"></a><span data-ttu-id="1781d-108">ElementAt</span><span class="sxs-lookup"><span data-stu-id="1781d-108">ElementAt</span></span>  
  
### <a name="example"></a><span data-ttu-id="1781d-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1781d-109">Example</span></span>  
 <span data-ttu-id="1781d-110">In diesem Beispiel wird die <xref:System.Linq.Enumerable.ElementAt%2A>-Methode verwendet, um die fünfte Adresse abzurufen, bei der `PostalCode` gleich "M4B 1V7" ist.</span><span class="sxs-lookup"><span data-stu-id="1781d-110">This example uses the <xref:System.Linq.Enumerable.ElementAt%2A> method to retrieve the fifth address where `PostalCode` == "M4B 1V7".</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#elementat)]
[!code-vb[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#elementat)]
  
## <a name="first"></a><span data-ttu-id="1781d-111">First (Erster)</span><span class="sxs-lookup"><span data-stu-id="1781d-111">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="1781d-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1781d-112">Example</span></span>  
 <span data-ttu-id="1781d-113">In diesem Beispiel wird die <xref:System.Linq.Enumerable.First%2A>-Methode verwendet, um den ersten Kontakt zurückzugeben, dessen Vorname "Brooke" lautet.</span><span class="sxs-lookup"><span data-stu-id="1781d-113">This example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is 'Brooke'.</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#firstsimple)]
[!code-vb[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#firstsimple)]
  
## <a name="see-also"></a><span data-ttu-id="1781d-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1781d-114">See also</span></span>

- [<span data-ttu-id="1781d-115">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="1781d-115">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="1781d-116">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="1781d-116">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="1781d-117">Übersicht über Standardabfrageoperatoren (C#)</span><span class="sxs-lookup"><span data-stu-id="1781d-117">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="1781d-118">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="1781d-118">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
