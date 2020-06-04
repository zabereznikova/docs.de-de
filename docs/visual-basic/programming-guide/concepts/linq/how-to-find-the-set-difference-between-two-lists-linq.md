---
title: 'Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ)'
ms.date: 07/20/2015
ms.assetid: b5b25474-10a8-4df6-aab5-75621bb6b68e
ms.openlocfilehash: f533b63b40325b34c5881c1e2f14aa4e576191c7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396596"
---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-visual-basic"></a><span data-ttu-id="6ab01-102">Gewusst wie: Suchen der festgelegten Differenz zwischen zwei Listen (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ab01-102">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="6ab01-103">In diesem Beispiel wird veranschaulicht, wie Sie mit LINQ zwei Listen mit Zeichenfolgen vergleichen und die Zeilen ausgeben, die in names1.txt, aber nicht in names2.txt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="6ab01-103">This example shows how to use LINQ to compare two lists of strings and output those lines that are in names1.txt but not in names2.txt.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="6ab01-104">So erstellen Sie die Datendateien</span><span class="sxs-lookup"><span data-stu-id="6ab01-104">To create the data files</span></span>  
  
1. <span data-ttu-id="6ab01-105">Kopieren Sie names1. txt und names2. txt in ihren Projektmappenordner, wie in Gewusst [wie: kombinieren und Vergleichen von Zeichen folgen Auflistungen (LINQ) (Visual Basic)](how-to-combine-and-compare-string-collections-linq.md)gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6ab01-105">Copy names1.txt and names2.txt to your solution folder as shown in [How to: Combine and Compare String Collections (LINQ) (Visual Basic)](how-to-combine-and-compare-string-collections-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ab01-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6ab01-106">Example</span></span>  
  
```vb  
Class CompareLists  
  
    Shared Sub Main()  
  
        ' Create the IEnumerable data sources.  
        Dim names1 As String() = System.IO.File.ReadAllLines("../../../names1.txt")  
        Dim names2 As String() = System.IO.File.ReadAllLines("../../../names2.txt")  
  
        ' Create the query. Note that method syntax must be used here.  
        Dim differenceQuery = names1.Except(names2)  
        Console.WriteLine("The following lines are in names1.txt but not names2.txt")  
  
        ' Execute the query.  
        For Each name As String In differenceQuery  
            Console.WriteLine(name)  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output:  
' The following lines are in names1.txt but not names2.txt  
' Potra, Cristina  
' Noriega, Fabricio  
' Aw, Kam Foo  
' Toyoshima, Tim  
' Guy, Wey Yuan  
' Garcia, Debra  
```  
  
 <span data-ttu-id="6ab01-107">Einige Typen von Abfrage Vorgängen in Visual Basic, z <xref:System.Linq.Enumerable.Except%2A> . b., <xref:System.Linq.Enumerable.Distinct%2A> , <xref:System.Linq.Enumerable.Union%2A> und <xref:System.Linq.Enumerable.Concat%2A> , können nur in Methoden basierter Syntax ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="6ab01-107">Some types of query operations in Visual Basic, such as <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Concat%2A>, can only be expressed in method-based syntax.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="6ab01-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="6ab01-108">Compile the code</span></span>  
<span data-ttu-id="6ab01-109">Erstellen Sie ein Visual Basic Konsolen Anwendungsprojekt mit einer- `Imports` Anweisung für den System. Linq-Namespace.</span><span class="sxs-lookup"><span data-stu-id="6ab01-109">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6ab01-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ab01-110">See also</span></span>

- [<span data-ttu-id="6ab01-111">LINQ und Zeichenfolgen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ab01-111">LINQ and Strings (Visual Basic)</span></span>](linq-and-strings.md)
