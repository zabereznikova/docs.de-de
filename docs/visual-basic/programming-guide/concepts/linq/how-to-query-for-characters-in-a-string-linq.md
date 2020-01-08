---
title: 'Gewusst wie: Abfragen von Zeichen in einer Zeichenfolge (LINQ)'
ms.date: 07/20/2015
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
ms.openlocfilehash: 2f306a488610aaa5775210eba3d7312b092545a7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345525"
---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a><span data-ttu-id="1f9cf-102">Gewusst wie: Abfragen von Zeichen in einer Zeichenfolge (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f9cf-102">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="1f9cf-103">Da die <xref:System.String>-Klasse die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle implementiert, kann jede Zeichenfolge als Folge von Zeichen abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="1f9cf-103">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="1f9cf-104">Dies ist allerdings kein üblicher Einsatz von LINQ.</span><span class="sxs-lookup"><span data-stu-id="1f9cf-104">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="1f9cf-105">Verwenden Sie für komplex Musterabgleichvorgänge die <xref:System.Text.RegularExpressions.Regex>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="1f9cf-105">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>

## <a name="example"></a><span data-ttu-id="1f9cf-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1f9cf-106">Example</span></span>

<span data-ttu-id="1f9cf-107">In folgendem Beispiel wird eine Zeichenfolge abgefragt, um die Zahl von enthaltenen numerischen Ziffern zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="1f9cf-107">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="1f9cf-108">Beachten Sie, dass die Abfrage „wieder verwendet“ wird, nachdem sie zum ersten Mal ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="1f9cf-108">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="1f9cf-109">Dies ist möglich, da die Abfrage selbst keine Ergebnisse speichert.</span><span class="sxs-lookup"><span data-stu-id="1f9cf-109">This is possible because the query itself does not store any actual results.</span></span>

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

## <a name="compile-the-code"></a><span data-ttu-id="1f9cf-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="1f9cf-110">Compile the code</span></span>

<span data-ttu-id="1f9cf-111">Erstellen Sie ein Visual Basic Konsolen Anwendungsprojekt mit einer `Imports`-Anweisung für den System. Linq-Namespace.</span><span class="sxs-lookup"><span data-stu-id="1f9cf-111">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f9cf-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f9cf-112">See also</span></span>

- [<span data-ttu-id="1f9cf-113">LINQ und Zeichen folgen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f9cf-113">LINQ and Strings (Visual Basic)</span></span>](linq-and-strings.md)
- [<span data-ttu-id="1f9cf-114">Kombinieren von LINQ-Abfragen mit regulären Ausdrücken (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f9cf-114">How to combine LINQ queries with regular expressions (Visual Basic)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)
