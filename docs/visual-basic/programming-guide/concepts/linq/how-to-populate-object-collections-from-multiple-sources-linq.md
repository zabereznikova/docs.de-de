---
title: 'Gewusst wie: Füllen von Objektauflistungen aus mehreren Quellen (LINQ)'
ms.date: 06/22/2018
ms.assetid: 63062a22-e6a9-42c0-b357-c7c965f58f33
ms.openlocfilehash: 74a2a0f71e575136f1758f72f9a8db72549a9489
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346975"
---
# <a name="how-to-populate-object-collections-from-multiple-sources-linq-visual-basic"></a><span data-ttu-id="e9c9f-102">Gewusst wie: Auffüllen von Objekt Auflistungen aus mehreren Quellen (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9c9f-102">How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="e9c9f-103">In diesem Beispiel erfahren Sie, wie Sie Daten aus unterschiedlichen Quellen in einer Sequenz aus neuen Typen zusammenführen können.</span><span class="sxs-lookup"><span data-stu-id="e9c9f-103">This example shows how to merge data from different sources into a sequence of new types.</span></span>

> [!NOTE]
> <span data-ttu-id="e9c9f-104">Versuchen Sie nicht, Daten im Arbeitsspeicher oder Daten im Dateisystem mit Daten, die sich noch in der Datenbank befinden, zusammenzuführen.</span><span class="sxs-lookup"><span data-stu-id="e9c9f-104">Don't try to join in-memory data or data in the file system with data that is still in a database.</span></span> <span data-ttu-id="e9c9f-105">Derartige domänenübergreifende Verknüpfungen können aufgrund von möglichen unterschiedlichen Definitionen von Verknüpfungsvorgänge für Datenbankabfragen und anderen Quelltypen zu undefinierten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="e9c9f-105">Such cross-domain joins can yield undefined results because of different ways in which join operations might be defined for database queries and other types of sources.</span></span> <span data-ttu-id="e9c9f-106">Zusätzlich kann eine derartige Verknüpfung eine Ausnahme außerhalb des Speichers verursachen, wenn die Datenmenge in der Datenbank groß genug ist.</span><span class="sxs-lookup"><span data-stu-id="e9c9f-106">Additionally, there is a risk that such an operation could cause an out-of-memory exception if the amount of data in the database is large enough.</span></span> <span data-ttu-id="e9c9f-107">Um Daten aus einer Datenbank mit Daten im Arbeitsspeicher zu verknüpfen, rufen Sie zuerst `ToList` oder `ToArray` in der Datenbankabfrage auf, und führen Sie dann die Verknüpfung in der zurückgegebenen Auflistung durch.</span><span class="sxs-lookup"><span data-stu-id="e9c9f-107">To join data from a database to in-memory data, first call `ToList` or `ToArray` on the database query, and then perform the join on the returned collection.</span></span>

## <a name="to-create-the-data-file"></a><span data-ttu-id="e9c9f-108">So erstellen Sie die Datendatei</span><span class="sxs-lookup"><span data-stu-id="e9c9f-108">To create the data file</span></span>

- <span data-ttu-id="e9c9f-109">Kopieren Sie die Dateien "Names. csv" und "Scores. csv" in Ihren Projektordner, wie unter Gewusst [wie: Verknüpfen von Inhalten aus unterschiedlichen Dateien (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e9c9f-109">Copy the names.csv and scores.csv files into your project folder, as described in [How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md).</span></span>

## <a name="example"></a><span data-ttu-id="e9c9f-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e9c9f-110">Example</span></span>

<span data-ttu-id="e9c9f-111">In folgendem Beispiel erfahren Sie, wie Sie einen benannten Typ `Student` zum Speichern zusammengeführter Daten aus zwei Zeichenfolgeauflistungen, die Arbeitsblätter im .csv-Format simulieren, im Arbeitsspeicher verwenden könne.</span><span class="sxs-lookup"><span data-stu-id="e9c9f-111">The following example shows how to use a named type `Student` to store merged data from two in-memory collections of strings that simulate spreadsheet data in .csv format.</span></span> <span data-ttu-id="e9c9f-112">Die erste Zeichenfolgeauflistung stellt die Namen der Studenten und deren Matrikelnummer dar, und die zweite Zeichenfolgeauflistung stellt die Matrikelnummer (in der ersten Spalte) und vier Prüfungsergebnisse dar.</span><span class="sxs-lookup"><span data-stu-id="e9c9f-112">The first collection of strings represents the student names and IDs, and the second collection represents the student ID (in the first column) and four exam scores.</span></span> <span data-ttu-id="e9c9f-113">Die Matrikelnummer wird als Fremdschlüssel verwendet.</span><span class="sxs-lookup"><span data-stu-id="e9c9f-113">The ID is used as the foreign key.</span></span>

```vb
Imports System.Collections.Generic
Imports System.Linq

Class Student
    Public FirstName As String
    Public LastName As String
    Public ID As Integer
    Public ExamScores As List(Of Integer)
End Class

Class PopulateCollection

    Shared Sub Main()

        ' Merge content from spreadsheets into a list of Student objects.

        ' These data files are defined in How to: Join Content from
        ' Dissimilar Files (LINQ).

        ' Each line of names.csv consists of a last name, a first name, and an
        ' ID number, separated by commas. For example, Omelchenko,Svetlana,111
        Dim names As String() = System.IO.File.ReadAllLines("../../../names.csv")

        ' Each line of scores.csv consists of an ID number and four test
        ' scores, separated by commas. For example, 111, 97, 92, 81, 60
        Dim scores As String() = System.IO.File.ReadAllLines("../../../scores.csv")

        ' The following query merges the content of two dissimilar spreadsheets
        ' based on common ID values.
        ' Multiple From clauses are used instead of a Join clause
        ' in order to store the results of scoreLine.Split.
        ' Note the dynamic creation of a list of integers for the
        ' ExamScores member. The first item is skipped in the split string
        ' because it is the student ID, not an exam score.
        Dim queryNamesScores = From nameLine In names
                          Let splitName = nameLine.Split(New Char() {","})
                          From scoreLine In scores
                          Let splitScoreLine = scoreLine.Split(New Char() {","})
                          Where Convert.ToInt32(splitName(2)) = Convert.ToInt32(splitScoreLine(0))
                          Select New Student() With {
                               .FirstName = splitName(1), .LastName = splitName(0), .ID = splitName(2),
                               .ExamScores = (From scoreAsText In splitScoreLine Skip 1
                                             Select Convert.ToInt32(scoreAsText)).ToList()}

        ' Optional. Store the query results for faster access in future
        ' queries. This could be useful with very large data files.
        Dim students As List(Of Student) = queryNamesScores.ToList()

        ' Display each student's name and exam score average.
        For Each s In students
            Console.WriteLine("The average score of " & s.FirstName & " " &
                              s.LastName & " is " & s.ExamScores.Average())
        Next

        ' Keep console window open in debug mode.
        Console.WriteLine("Press any key to exit.")
        Console.ReadKey()
    End Sub
End Class

' Output:
' The average score of Svetlana Omelchenko is 82.5
' The average score of Claire O'Donnell is 72.25
' The average score of Sven Mortensen is 84.5
' The average score of Cesar Garcia is 88.25
' The average score of Debra Garcia is 67
' The average score of Fadi Fakhouri is 92.25
' The average score of Hanying Feng is 88
' The average score of Hugo Garcia is 85.75
' The average score of Lance Tucker is 81.75
' The average score of Terry Adams is 85.25
' The average score of Eugene Zabokritski is 83
' The average score of Michael Tucker is 92
```

<span data-ttu-id="e9c9f-114">In der Klausel der [SELECT-Klausel](../../../../visual-basic/language-reference/queries/select-clause.md) wird ein Objektinitialisierer verwendet, um jedes neue `Student` Objekt mithilfe der Daten aus den beiden Quellen zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="e9c9f-114">In the [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md) clause, an object initializer is used to instantiate each new `Student` object by using the data from the two sources.</span></span>

<span data-ttu-id="e9c9f-115">Wenn Sie die Ergebnisse einer Abfrage nicht speichern müssen, können anonyme Typen praktischer als benannte Typen sein.</span><span class="sxs-lookup"><span data-stu-id="e9c9f-115">If you don't have to store the results of a query, anonymous types can be more convenient than named types.</span></span> <span data-ttu-id="e9c9f-116">Benannte Typen sind für die Übergabe von Abfrageergebnissen außerhalb der Methode, in der die Abfrage ausgeführt wird, erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e9c9f-116">Named types are required if you pass the query results outside the method in which the query is executed.</span></span> <span data-ttu-id="e9c9f-117">In folgendem Beispiel wird die gleiche Aufgabe wie im vorherigen Beispiel ausgeführt; allerdings werden statt benannter anonyme Typen verwendet:</span><span class="sxs-lookup"><span data-stu-id="e9c9f-117">The following example performs the same task as the previous example, but uses anonymous types instead of named types:</span></span>

```vb
' Merge the data by using an anonymous type.
' Note the dynamic creation of a list of integers for the
' ExamScores member. We skip 1 because the first string
' in the array is the student ID, not an exam score.
Dim queryNamesScores2 =
    From nameLine In names
    Let splitName = nameLine.Split(New Char() {","})
    From scoreLine In scores
    Let splitScoreLine = scoreLine.Split(New Char() {","})
    Where Convert.ToInt32(splitName(2)) = Convert.ToInt32(splitScoreLine(0))
    Select New With
           {.Last = splitName(0),
            .First = splitName(1),
            .ExamScores = (From scoreAsText In splitScoreLine Skip 1
                           Select Convert.ToInt32(scoreAsText)).ToList()}

' Display each student's name and exam score average.
For Each s In queryNamesScores2
    Console.WriteLine("The average score of " & s.First & " " &
                      s.Last & " is " & s.ExamScores.Average())
Next
```

## <a name="see-also"></a><span data-ttu-id="e9c9f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9c9f-118">See also</span></span>

- [<span data-ttu-id="e9c9f-119">LINQ und Zeichen folgen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9c9f-119">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
