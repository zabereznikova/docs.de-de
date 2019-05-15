---
title: 'Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b5b25474-10a8-4df6-aab5-75621bb6b68e
ms.openlocfilehash: a5c08e270059cd4ab127051d091deff221091fbc
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593464"
---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-visual-basic"></a><span data-ttu-id="9112f-102">Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9112f-102">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="9112f-103">In diesem Beispiel wird veranschaulicht, wie Sie mit LINQ zwei Listen mit Zeichenfolgen vergleichen und die Zeilen ausgeben, die in names1.txt, aber nicht in names2.txt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="9112f-103">This example shows how to use LINQ to compare two lists of strings and output those lines that are in names1.txt but not in names2.txt.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="9112f-104">So erstellen Sie die Datendateien</span><span class="sxs-lookup"><span data-stu-id="9112f-104">To create the data files</span></span>  
  
1. <span data-ttu-id="9112f-105">Kopieren Sie die Dateien „names1.txt“ und „names2.txt“ in den Projektmappenordner, wie unter [Vorgehensweise: Verbinden und Vergleichen von Zeichenfolgenauflistungen (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md).</span><span class="sxs-lookup"><span data-stu-id="9112f-105">Copy names1.txt and names2.txt to your solution folder as shown in [How to: Combine and Compare String Collections (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9112f-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9112f-106">Example</span></span>  
  
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
  
 <span data-ttu-id="9112f-107">Einige Arten von Abfrageoperationen in Visual Basic wird z. B. <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, und <xref:System.Linq.Enumerable.Concat%2A>, nur in methodenbasierter Syntax ausgedrückt werden können.</span><span class="sxs-lookup"><span data-stu-id="9112f-107">Some types of query operations in Visual Basic, such as <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Concat%2A>, can only be expressed in method-based syntax.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9112f-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="9112f-108">Compiling the Code</span></span>  
<span data-ttu-id="9112f-109">Erstellen Sie ein Konsolenanwendungsprojekt für VB.NET, mit einem `Imports` -Anweisung für den Namespace "System.Linq".</span><span class="sxs-lookup"><span data-stu-id="9112f-109">Create a VB.NET console application project, with an `Imports` statement for the System.Linq namespace.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9112f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9112f-110">See also</span></span>

- [<span data-ttu-id="9112f-111">LINQ und Zeichenfolgen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9112f-111">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
