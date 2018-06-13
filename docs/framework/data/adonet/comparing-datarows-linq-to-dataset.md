---
title: Vergleichen von DataRows (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fe0eadf-297b-487c-8d4b-7816753c2883
ms.openlocfilehash: 79fc91092badfd871a1409e2ee602272f3eae100
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756279"
---
# <a name="comparing-datarows-linq-to-dataset"></a><span data-ttu-id="bdd1a-102">Vergleichen von DataRows (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="bdd1a-102">Comparing DataRows (LINQ to DataSet)</span></span>
[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]<span data-ttu-id="bdd1a-103"> definiert verschiedene Mengenoperatoren, um Quellelemente zu vergleichen und zu sehen, ob sie gleich sind.</span><span class="sxs-lookup"><span data-stu-id="bdd1a-103"> defines various set operators to compare source elements to see if they are equal.</span></span> <span data-ttu-id="bdd1a-104">Der [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] stellt die folgenden Mengenoperatoren bereit:</span><span class="sxs-lookup"><span data-stu-id="bdd1a-104">[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] provides the following set operators:</span></span>  
  
-   <xref:System.Linq.Enumerable.Distinct%2A>  
  
-   <xref:System.Linq.Enumerable.Union%2A>  
  
-   <xref:System.Linq.Enumerable.Intersect%2A>  
  
-   <xref:System.Linq.Enumerable.Except%2A>  
  
 <span data-ttu-id="bdd1a-105">Diese Operatoren vergleichen Quellelemente, indem sie für jede Auflistung von Elementen die Methoden <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> und <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="bdd1a-105">These operators compare source elements by calling the <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> and <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> methods on each collection of elements.</span></span> <span data-ttu-id="bdd1a-106">Im Falle einer <xref:System.Data.DataRow> führen diese Operatoren einen Verweisvergleich aus, was für Mengenoperationen bei tabellarischen Daten im Allgemeinen nicht ideal ist.</span><span class="sxs-lookup"><span data-stu-id="bdd1a-106">In the case of a <xref:System.Data.DataRow>, these operators perform a reference comparison, which is generally not the ideal behavior for set operations over tabular data.</span></span> <span data-ttu-id="bdd1a-107">Bei Mengenoperationen soll in der Regel ermittelt werden, ob die Elementwerte gleich sind, nicht die Elementverweise.</span><span class="sxs-lookup"><span data-stu-id="bdd1a-107">For set operations, you usually want to determine whether the element values are equal and not the element references.</span></span> <span data-ttu-id="bdd1a-108">Deshalb wurde <xref:System.Data.DataRowComparer> um die [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Klasse erweitert.</span><span class="sxs-lookup"><span data-stu-id="bdd1a-108">Therefore, the <xref:System.Data.DataRowComparer> class has been added to [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="bdd1a-109">Diese Klasse kann verwendet werden, um Zeilenwerte zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="bdd1a-109">This class can be used to compare row values.</span></span>  
  
 <span data-ttu-id="bdd1a-110">Die <xref:System.Data.DataRowComparer>-Klasse enthält eine Wertvergleichimplementierung für <xref:System.Data.DataRow>, sodass diese Klasse für Mengenoperationen wie <xref:System.Linq.Enumerable.Distinct%2A> verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="bdd1a-110">The <xref:System.Data.DataRowComparer> class contains a value comparison implementation for <xref:System.Data.DataRow>, so this class can be used for set operations such as <xref:System.Linq.Enumerable.Distinct%2A>.</span></span> <span data-ttu-id="bdd1a-111">Diese Klasse kann nicht direkt instanziiert werden. Stattdessen muss die <xref:System.Data.DataRowComparer.Default%2A>-Eigenschaft verwendet werden, damit eine <xref:System.Data.DataRowComparer%601>-Instanz zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bdd1a-111">This class cannot be directly instantiated; instead, the <xref:System.Data.DataRowComparer.Default%2A> property must be used to return an instance of the <xref:System.Data.DataRowComparer%601>.</span></span> <span data-ttu-id="bdd1a-112">Dann wird die <xref:System.Data.DataRowComparer%601.Equals%2A>-Methode aufgerufen, und die beiden miteinander zu vergleichenden <xref:System.Data.DataRow>-Objekte werden als Eingabeparameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="bdd1a-112">The <xref:System.Data.DataRowComparer%601.Equals%2A> method is then called and the two <xref:System.Data.DataRow> objects to be compared are passed in as input parameters.</span></span> <span data-ttu-id="bdd1a-113">Die <xref:System.Data.DataRowComparer%601.Equals%2A>-Methode gibt `true` zurück, wenn der sortierte Satz von Spaltenwerten in beiden <xref:System.Data.DataRow>-Objekten gleich ist. Anderenfalls wird `false` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bdd1a-113">The <xref:System.Data.DataRowComparer%601.Equals%2A> method returns `true` if the ordered set of column values in both <xref:System.Data.DataRow> objects are equal; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdd1a-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bdd1a-114">Example</span></span>  
 <span data-ttu-id="bdd1a-115">In diesem Beispiel wird `Intersect` verwendet, um Kontakte abzurufen, die in beiden Tabellen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="bdd1a-115">This example uses `Intersect` to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
### <a name="example"></a><span data-ttu-id="bdd1a-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bdd1a-116">Example</span></span>  
 <span data-ttu-id="bdd1a-117">Im folgenden Beispiel werden zwei Zeilen miteinander verglichen, und es werden ihre Hashcodes abgerufen.</span><span class="sxs-lookup"><span data-stu-id="bdd1a-117">The following example compares two rows and gets their hash codes.</span></span>  
  
 [!code-vb[DP LINQ to DataSet Examples#CompareDifferentRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#comparedifferentrows)]  
  
## <a name="see-also"></a><span data-ttu-id="bdd1a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdd1a-118">See Also</span></span>  
 <xref:System.Data.DataRowComparer>  
 [<span data-ttu-id="bdd1a-119">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="bdd1a-119">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="bdd1a-120">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="bdd1a-120">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
