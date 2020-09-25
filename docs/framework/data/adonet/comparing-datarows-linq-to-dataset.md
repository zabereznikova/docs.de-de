---
title: Vergleichen von DataRows (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fe0eadf-297b-487c-8d4b-7816753c2883
ms.openlocfilehash: 8cce52734c83e42312d71806d4151ef21e4df0ba
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203799"
---
# <a name="comparing-datarows-linq-to-dataset"></a><span data-ttu-id="20921-102">Vergleichen von DataRows (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="20921-102">Comparing DataRows (LINQ to DataSet)</span></span>

<span data-ttu-id="20921-103">Language-Integrated Query (LINQ) definiert verschiedene Mengen Operatoren zum Vergleichen von Quell Elementen, um festzustellen, ob Sie gleich sind.</span><span class="sxs-lookup"><span data-stu-id="20921-103">Language-Integrated Query (LINQ) defines various set operators to compare source elements to see if they are equal.</span></span> <span data-ttu-id="20921-104">LINQ stellt die folgenden Mengen Operatoren bereit:</span><span class="sxs-lookup"><span data-stu-id="20921-104">LINQ provides the following set operators:</span></span>  
  
- <xref:System.Linq.Enumerable.Distinct%2A>  
  
- <xref:System.Linq.Enumerable.Union%2A>  
  
- <xref:System.Linq.Enumerable.Intersect%2A>  
  
- <xref:System.Linq.Enumerable.Except%2A>  
  
 <span data-ttu-id="20921-105">Diese Operatoren vergleichen Quellelemente, indem sie für jede Auflistung von Elementen die Methoden <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> und <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="20921-105">These operators compare source elements by calling the <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> and <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> methods on each collection of elements.</span></span> <span data-ttu-id="20921-106">Im Falle einer <xref:System.Data.DataRow> führen diese Operatoren einen Verweisvergleich aus, was für Mengenoperationen bei tabellarischen Daten im Allgemeinen nicht ideal ist.</span><span class="sxs-lookup"><span data-stu-id="20921-106">In the case of a <xref:System.Data.DataRow>, these operators perform a reference comparison, which is generally not the ideal behavior for set operations over tabular data.</span></span> <span data-ttu-id="20921-107">Bei Mengenoperationen soll in der Regel ermittelt werden, ob die Elementwerte gleich sind, nicht die Elementverweise.</span><span class="sxs-lookup"><span data-stu-id="20921-107">For set operations, you usually want to determine whether the element values are equal and not the element references.</span></span> <span data-ttu-id="20921-108">Daher wurde die- <xref:System.Data.DataRowComparer> Klasse LINQ to DataSet hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="20921-108">Therefore, the <xref:System.Data.DataRowComparer> class has been added to LINQ to DataSet.</span></span> <span data-ttu-id="20921-109">Diese Klasse kann verwendet werden, um Zeilenwerte zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="20921-109">This class can be used to compare row values.</span></span>  
  
 <span data-ttu-id="20921-110">Die <xref:System.Data.DataRowComparer>-Klasse enthält eine Wertvergleichimplementierung für <xref:System.Data.DataRow>, sodass diese Klasse für Mengenoperationen wie <xref:System.Linq.Enumerable.Distinct%2A> verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="20921-110">The <xref:System.Data.DataRowComparer> class contains a value comparison implementation for <xref:System.Data.DataRow>, so this class can be used for set operations such as <xref:System.Linq.Enumerable.Distinct%2A>.</span></span> <span data-ttu-id="20921-111">Diese Klasse kann nicht direkt instanziiert werden. Stattdessen muss die <xref:System.Data.DataRowComparer.Default%2A>-Eigenschaft verwendet werden, damit eine <xref:System.Data.DataRowComparer%601>-Instanz zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="20921-111">This class cannot be directly instantiated; instead, the <xref:System.Data.DataRowComparer.Default%2A> property must be used to return an instance of the <xref:System.Data.DataRowComparer%601>.</span></span> <span data-ttu-id="20921-112">Dann wird die <xref:System.Data.DataRowComparer%601.Equals%2A>-Methode aufgerufen, und die beiden miteinander zu vergleichenden <xref:System.Data.DataRow>-Objekte werden als Eingabeparameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="20921-112">The <xref:System.Data.DataRowComparer%601.Equals%2A> method is then called and the two <xref:System.Data.DataRow> objects to be compared are passed in as input parameters.</span></span> <span data-ttu-id="20921-113">Die <xref:System.Data.DataRowComparer%601.Equals%2A>-Methode gibt `true` zurück, wenn der sortierte Satz von Spaltenwerten in beiden <xref:System.Data.DataRow>-Objekten gleich ist. Anderenfalls wird `false` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="20921-113">The <xref:System.Data.DataRowComparer%601.Equals%2A> method returns `true` if the ordered set of column values in both <xref:System.Data.DataRow> objects are equal; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20921-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="20921-114">Example</span></span>  

 <span data-ttu-id="20921-115">In diesem Beispiel wird `Intersect` verwendet, um Kontakte abzurufen, die in beiden Tabellen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="20921-115">This example uses `Intersect` to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
### <a name="example"></a><span data-ttu-id="20921-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="20921-116">Example</span></span>  

 <span data-ttu-id="20921-117">Im folgenden Beispiel werden zwei Zeilen miteinander verglichen, und es werden ihre Hashcodes abgerufen.</span><span class="sxs-lookup"><span data-stu-id="20921-117">The following example compares two rows and gets their hash codes.</span></span>  
  
 [!code-vb[DP LINQ to DataSet Examples#CompareDifferentRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#comparedifferentrows)]  
  
## <a name="see-also"></a><span data-ttu-id="20921-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20921-118">See also</span></span>

- <xref:System.Data.DataRowComparer>
- [<span data-ttu-id="20921-119">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="20921-119">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="20921-120">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="20921-120">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
