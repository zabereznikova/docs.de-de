---
title: Kombinieren von LINQ-Abfragen mit regulären Ausdrücken
ms.date: 07/20/2015
ms.assetid: 3da1bd10-b0d8-4d5b-a637-966891c13592
ms.openlocfilehash: a091418be1f7cc30d42a98f80ebae2d36d29b5d8
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337551"
---
# <a name="how-to-combine-linq-queries-with-regular-expressions-visual-basic"></a><span data-ttu-id="4df33-102">Kombinieren von LINQ-Abfragen mit regulären Ausdrücken (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4df33-102">How to combine LINQ queries with regular expressions (Visual Basic)</span></span>

<span data-ttu-id="4df33-103">In diesem Beispiel wird gezeigt, wie Sie die <xref:System.Text.RegularExpressions.Regex>-Klasse verwenden, um einen regulären Ausdruck für komplexere Übereinstimmungen in Textzeichenfolgen erstellen.</span><span class="sxs-lookup"><span data-stu-id="4df33-103">This example shows how to use the <xref:System.Text.RegularExpressions.Regex> class to create a regular expression for more complex matching in text strings.</span></span> <span data-ttu-id="4df33-104">Die LINQ-Abfrage erleichtert das Filtern nach genau den Dateien, die Sie mithilfe des regulären Ausdrucks suchen möchten, sowie das Formen der Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="4df33-104">The LINQ query makes it easy to filter on exactly the files that you want to search with the regular expression, and to shape the results.</span></span>

## <a name="example"></a><span data-ttu-id="4df33-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4df33-105">Example</span></span>

```vb
Imports System.IO
Imports System.Text.RegularExpressions

Class LinqRegExVB

    Shared Sub Main()

        ' Root folder to query, along with all subfolders.
        ' Modify this path as necessary so that it accesses your Visual Studio folder.
        Dim startFolder As String = "C:\Program Files (x86)\Microsoft Visual Studio 14.0\"
        ' One of the following paths may be more appropriate on your computer.
        'Dim startFolder As String = "C:\Program Files (x86)\Microsoft Visual Studio\2017\"

        ' Take a snapshot of the file system.
        Dim fileList As IEnumerable(Of FileInfo) = GetFiles(startFolder)

        ' Create a regular expression to find all things "Visual".
        Dim searchTerm As New Regex("Visual (Basic|C#|C\+\+|Studio)")

        ' Search the contents of each .htm file.
        ' Remove the where clause to find even more matches!
        ' This query produces a list of files where a match
        ' was found, and a list of the matches in that file.
        ' Note: Explicit typing of "Match" in select clause.
        ' This is required because MatchCollection is not a
        ' generic IEnumerable collection.
        Dim queryMatchingFiles = From afile In fileList
                                Where afile.Extension = ".htm"
                                Let fileText = File.ReadAllText(afile.FullName)
                                Let matches = searchTerm.Matches(fileText)
                                Where (matches.Count > 0)
                                Select Name = afile.FullName,
                                       Matches = From match As Match In matches
                                                 Select match.Value

        ' Execute the query.
        Console.WriteLine("The term " & searchTerm.ToString() & " was found in:")

        For Each fileMatches In queryMatchingFiles
            ' Trim the path a bit, then write
            ' the file name in which a match was found.
            Dim s = fileMatches.Name.Substring(startFolder.Length - 1)
            Console.WriteLine(s)

            ' For this file, write out all the matching strings
            For Each match In fileMatches.Matches
                Console.WriteLine("  " + match)
            Next
        Next

        ' Keep the console window open in debug mode
        Console.WriteLine("Press any key to exit")
        Console.ReadKey()
    End Sub

    ' Function to retrieve a list of files. Note that this is a copy
    ' of the file information.
    Shared Function GetFiles(root As String) As IEnumerable(Of FileInfo)
        Return From file In My.Computer.FileSystem.GetFiles(
                   root, FileIO.SearchOption.SearchAllSubDirectories, "*.*")
               Select New FileInfo(file)
    End Function

End Class
```

<span data-ttu-id="4df33-106">Beachten Sie, dass Sie auch das <xref:System.Text.RegularExpressions.MatchCollection>-Objekt abfragen können, das von einer `RegEx`-Suche zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4df33-106">Note that you can also query the <xref:System.Text.RegularExpressions.MatchCollection> object that is returned by a `RegEx` search.</span></span> <span data-ttu-id="4df33-107">In diesem Beispiel wird nur der Wert jeder Übereinstimmung in den Ergebnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4df33-107">In this example only the value of each match is produced in the results.</span></span> <span data-ttu-id="4df33-108">Allerdings ist es auch möglich, LINQ zu verwenden, um alle Arten von Filtern, Sortieren und Gruppieren für diese Auflistung ausführen.</span><span class="sxs-lookup"><span data-stu-id="4df33-108">However, it is also possible to use LINQ to perform all kinds of filtering, sorting, and grouping on that collection.</span></span> <span data-ttu-id="4df33-109">Da <xref:System.Text.RegularExpressions.MatchCollection> eine nicht generische <xref:System.Collections.IEnumerable>-Auflistung ist, müssen Sie den Typ der Bereichsvariable in der Abfrage explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="4df33-109">Because <xref:System.Text.RegularExpressions.MatchCollection> is a non-generic <xref:System.Collections.IEnumerable> collection, you have to explicitly state the type of the range variable in the query.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="4df33-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4df33-110">Compile the code</span></span>

<span data-ttu-id="4df33-111">Erstellen Sie ein Visual Basic Konsolen Anwendungsprojekt, kopieren Sie das Codebeispiel, fügen Sie es ein, und passen Sie den Wert des Start Objekts in den Projekteigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="4df33-111">Create a Visual Basic console application project, copy and paste the code sample, and adjust the Startup object value in the project properties.</span></span>

## <a name="see-also"></a><span data-ttu-id="4df33-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4df33-112">See also</span></span>

- [<span data-ttu-id="4df33-113">LINQ und Zeichen folgen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4df33-113">LINQ and Strings (Visual Basic)</span></span>](linq-and-strings.md)
- [<span data-ttu-id="4df33-114">LINQ and File Directories (Visual Basic) (LINQ und Dateiverzeichnisse (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="4df33-114">LINQ and File Directories (Visual Basic)</span></span>](linq-and-file-directories.md)
