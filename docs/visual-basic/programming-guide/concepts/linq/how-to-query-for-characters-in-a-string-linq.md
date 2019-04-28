---
title: 'Vorgehensweise: Abfragen von Zeichen in einer Zeichenfolge (LINQ) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
ms.openlocfilehash: 3f460f635c581eef5655c5707e3dd356e7986d74
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644384"
---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a><span data-ttu-id="e5edc-102">Vorgehensweise: Abfragen von Zeichen in einer Zeichenfolge (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5edc-102">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="e5edc-103">Da die <xref:System.String>-Klasse die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle implementiert, kann jede Zeichenfolge als Folge von Zeichen abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="e5edc-103">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="e5edc-104">Dies ist allerdings kein üblicher Einsatz von LINQ.</span><span class="sxs-lookup"><span data-stu-id="e5edc-104">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="e5edc-105">Verwenden Sie für komplex Musterabgleichvorgänge die <xref:System.Text.RegularExpressions.Regex>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="e5edc-105">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5edc-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e5edc-106">Example</span></span>  
 <span data-ttu-id="e5edc-107">In folgendem Beispiel wird eine Zeichenfolge abgefragt, um die Zahl von enthaltenen numerischen Ziffern zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="e5edc-107">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="e5edc-108">Beachten Sie, dass die Abfrage „wieder verwendet“ wird, nachdem sie zum ersten Mal ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e5edc-108">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="e5edc-109">Dies ist möglich, da die Abfrage selbst keine Ergebnisse speichert.</span><span class="sxs-lookup"><span data-stu-id="e5edc-109">This is possible because the query itself does not store any actual results.</span></span>  
  
```vb  
Class QueryAString  
  
    Shared Sub Main()  
  
        ' A string is an IEnumerable data source.  
        Dim aString As String = "ABCDE99F-J74-12-89A"  
  
        ' Select only those characters that are numbers  
        Dim stringQuery = From ch In aString   
                          Where Char.IsDigit(ch)   
                          Select ch  
        ' Execute the query  
        For Each c As Char In stringQuery  
            Console.Write(c & " ")  
        Next  
  
        ' Call the Count method on the existing query.  
        Dim count As Integer = stringQuery.Count()  
        Console.WriteLine(System.Environment.NewLine & "Count = " & count)  
  
        ' Select all characters before the first '-'  
        Dim stringQuery2 = aString.TakeWhile(Function(c) c <> "-")  
  
        ' Execute the second query  
        For Each ch In stringQuery2  
            Console.Write(ch)  
        Next  
  
        Console.WriteLine(System.Environment.NewLine & "Press any key to exit")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output:  
' 9 9 7 4 1 2 8 9   
' Count = 8  
' ABCDE99F  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e5edc-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e5edc-110">Compiling the Code</span></span>  
 <span data-ttu-id="e5edc-111">Erstellen Sie ein neues Projekt, das auf die .NET Framework-Version 3.5 oder höher ausgelegt ist, mit einer Referenz zu System.Core.dll und einer `Imports`-Anweisung für den System.Linq-Namespace.</span><span class="sxs-lookup"><span data-stu-id="e5edc-111">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5edc-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5edc-112">See also</span></span>

- [<span data-ttu-id="e5edc-113">LINQ und Zeichenfolgen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5edc-113">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
- [<span data-ttu-id="e5edc-114">Vorgehensweise: Kombinieren von LINQ-Abfragen mit regulären Ausdrücken (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5edc-114">How to: Combine LINQ Queries with Regular Expressions (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)
