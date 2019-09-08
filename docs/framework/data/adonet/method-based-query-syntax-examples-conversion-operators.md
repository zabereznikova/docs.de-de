---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Konvertierungs Operatoren (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a084c16b-9b55-4690-aefd-f8e0810a92c3
ms.openlocfilehash: 3e2a72a2bb0921828bdd90fe437987fddfc995b5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783690"
---
# <a name="method-based-query-syntax-examples-conversion-operators-linq-to-dataset"></a><span data-ttu-id="49cd2-102">Beispiele für die methodenbasierte Abfragesyntax: Konvertierungs Operatoren (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="49cd2-102">Method-Based Query Syntax Examples: Conversion Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="49cd2-103">In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der Methoden <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> und <xref:System.Linq.Enumerable.ToList%2A> einen Abfrageausdruck sofort ausführen können.</span><span class="sxs-lookup"><span data-stu-id="49cd2-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A>, and <xref:System.Linq.Enumerable.ToList%2A> methods to immediately execute a query expression.</span></span>  
  
 <span data-ttu-id="49cd2-104">Die `FillDataSet` in diesen Beispielen verwendete Methode wird beim [Laden von Daten in ein DataSet](loading-data-into-a-dataset.md)angegeben.</span><span class="sxs-lookup"><span data-stu-id="49cd2-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="49cd2-105">In den Beispielen in diesem Thema wird auf die Tabellen &lt;legacyBold&gt;Contact&lt;/legacyBold&gt;, &lt;legacyBold&gt;Address&lt;/legacyBold&gt;, &lt;legacyBold&gt;Product&lt;/legacyBold&gt;, &lt;legacyBold&gt;SalesOrderHeader&lt;/legacyBold&gt; und &lt;legacyBold&gt;SalesOrderDetail&lt;/legacyBold&gt; in der &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="49cd2-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="49cd2-106">In den Beispielen in diesem Thema werden die `using` folgenden / `Imports` -Anweisungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="49cd2-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="49cd2-107">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie in Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md)ein LINQ to DataSet Projekt.</span><span class="sxs-lookup"><span data-stu-id="49cd2-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="toarray"></a><span data-ttu-id="49cd2-108">ToArray</span><span class="sxs-lookup"><span data-stu-id="49cd2-108">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="49cd2-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="49cd2-109">Example</span></span>  
 <span data-ttu-id="49cd2-110">In diesem Beispiel wird die <xref:System.Linq.Enumerable.ToArray%2A>-Methode verwendet, um ein Array sofort in eine Sequenz umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="49cd2-110">This example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#toarray)]
 [!code-vb[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="49cd2-111">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="49cd2-111">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="49cd2-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="49cd2-112">Example</span></span>  
 <span data-ttu-id="49cd2-113">In diesem Beispiel wird die <xref:System.Linq.Enumerable.ToDictionary%2A>-Methode verwendet, um eine Sequenz und einen zugehörigen Schlüsselausdruck sofort in ein Wörterbuch umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="49cd2-113">This example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="49cd2-114">ToList</span><span class="sxs-lookup"><span data-stu-id="49cd2-114">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="49cd2-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="49cd2-115">Example</span></span>  
 <span data-ttu-id="49cd2-116">In diesem Beispiel wird die <xref:System.Linq.Enumerable.ToList%2A>-Methode verwendet, um eine Sequenz sofort in eine <xref:System.Collections.Generic.List%601> umzuwandeln, wobei `T` vom Typ <xref:System.Data.DataRow> ist.</span><span class="sxs-lookup"><span data-stu-id="49cd2-116">This example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#tolist)]
 [!code-vb[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="49cd2-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49cd2-117">See also</span></span>

- [<span data-ttu-id="49cd2-118">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="49cd2-118">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="49cd2-119">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="49cd2-119">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="49cd2-120">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="49cd2-120">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="49cd2-121">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="49cd2-121">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
