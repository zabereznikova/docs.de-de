---
title: 'Vorgehensweise: Abfragen von Dateiduplikaten in einer Verzeichnisstruktur (LINQ)'
ms.date: 07/20/2015
ms.assetid: 387d7c97-95dd-4a50-9761-7e9cf8ae9e6a
ms.openlocfilehash: b37da0a26c8bb4abc885faa7bb0c467e2d7d2347
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396427"
---
# <a name="how-to-query-for-duplicate-files-in-a-directory-tree-linq-visual-basic"></a><span data-ttu-id="72bc0-102">Vorgehensweise: Abfragen von Dateiduplikate in einer Verzeichnisstruktur (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72bc0-102">How to: Query for Duplicate Files in a Directory Tree (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="72bc0-103">Manchmal können sich Dateien mit demselben Namen in mehr als einem Ordner befinden.</span><span class="sxs-lookup"><span data-stu-id="72bc0-103">Sometimes files that have the same name may be located in more than one folder.</span></span> <span data-ttu-id="72bc0-104">Beispielsweise enthalten mehrere Ordner unter dem Installationsordner von Visual Studio eine Datei „readme.htm“.</span><span class="sxs-lookup"><span data-stu-id="72bc0-104">For example, under the Visual Studio installation folder, several folders have a readme.htm file.</span></span> <span data-ttu-id="72bc0-105">Dieses Beispiel zeigt, wie solche mehrfach vorkommenden Dateinamen in einem angegebenen Stammordner abgefragt werden können.</span><span class="sxs-lookup"><span data-stu-id="72bc0-105">This example shows how to query for such duplicate file names under a specified root folder.</span></span> <span data-ttu-id="72bc0-106">Das zweite Beispiel zeigt, wie Dateien abgefragt werden können, deren Größe und Erstellungszeit ebenfalls übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="72bc0-106">The second example shows how to query for files whose size and creation times also match.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72bc0-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="72bc0-107">Example</span></span>  
  
```vb  
Module QueryDuplicateFileNames  
  
    Public Sub Main()  
  
        Dim path As String = "C:\Program Files\Microsoft Visual Studio 9.0\Common7"  
        QueryDuplicates1(path)  
        ' Uncomment to run this query instead  
        ' QueryDuplicates2(path)  
  
    End Sub  
    Sub QueryDuplicates1(ByVal root As String)  
        Dim dir As New System.IO.DirectoryInfo(root)  
        Dim duplicates = From aFile In dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories) _  
                                 Order By aFile.Name _  
                                 Group aFile By aFile.Name Into newGroup = Group _  
                                 Where newGroup.Count() >= 2 _  
                                 Select newGroup  
  
        ' Page the display so that the results can be read.  
        Dim trimLength = root.Length  
        PageOutput(duplicates, trimLength)  
  
    End Sub  
    Sub QueryDuplicates2(ByVal root As String)  
  
        ' This time a composite key is used. This sub finds all files  
        ' that have been copied into multiple subfolders.  
        Dim dir As New System.IO.DirectoryInfo(root)  
  
        Dim duplicates = From aFile In Dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories) _  
                                 Order By aFile.Name _  
                                 Group aFile By aFile.Name, aFile.CreationTime, aFile.Length Into newGroup = Group _  
                                 Where newGroup.Count() >= 2 _  
                                 Select newGroup  
  
        ' Page the display so that the results can be read.  
        Dim trimLength = root.Length  
        PageOutput(duplicates, trimLength)  
  
    End Sub  
    ' Pages console display for large query results. No more than one group per page.  
    ' This sub specifically works with group queries of FileInfo objects  
    ' but can be modified for any type.  
    Sub PageOutput(ByVal groupQuery, ByVal charsToSkip)  
  
        ' "3" = 1 line for extension key + 1 for "Press any key" + 1 for input cursor.  
        Dim numLines As Integer = Console.WindowHeight - 3  
        ' Flag to indicate whether there are more results to display  
        Dim goAgain As Boolean = True  
  
        For Each fg As IEnumerable(Of System.IO.FileInfo) In groupQuery  
            ' Start a new extension at the top of a page.  
            Dim currentLine As Integer = 0  
  
            Do While (currentLine < fg.Count())  
                Console.Clear()  
  
                ' Get the next page of results  
                ' No more than one filename per page  
                Dim resultPage = From file In fg _  
                                Skip currentLine Take numLines  
  
                ' Execute the query. Trim the paths in the output.  
                For Each line In resultPage  
                    Console.WriteLine(vbTab & line.FullName.Substring(charsToSkip))  
                Next  
  
                ' Advance the current position  
                currentLine = numLines + currentLine  
  
                ' Give the user a chance to break out of the loop  
                Console.WriteLine("Press any key for next page or the 'End' key to exit.")  
                Dim key As ConsoleKey = Console.ReadKey().Key  
                If key = ConsoleKey.End Then  
                    goAgain = False  
                    Exit For  
                End If  
            Loop  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="72bc0-108">Die erste Abfrage verwendet einen einfachen Schlüssel, um eine Übereinstimmung zu ermitteln. Somit werden Dateien gefunden, die den gleichen Namen haben, deren Inhalt aber unterschiedlich sein kann.</span><span class="sxs-lookup"><span data-stu-id="72bc0-108">The first query uses a simple key to determine a match; this finds files that have the same name but whose contents might be different.</span></span> <span data-ttu-id="72bc0-109">Die zweite Abfrage verwendet einen zusammengesetzten Schlüssel für den Abgleich von drei Eigenschaften des <xref:System.IO.FileInfo>-Objekts.</span><span class="sxs-lookup"><span data-stu-id="72bc0-109">The second query uses a compound key to match against three properties of the <xref:System.IO.FileInfo> object.</span></span> <span data-ttu-id="72bc0-110">Diese Abfrage hat eine größere Wahrscheinlichkeit, Dateien zu finden, die denselben Namen und ähnliche oder identische Inhalte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="72bc0-110">This query is much more likely to find files that have the same name and similar or identical content.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="72bc0-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="72bc0-111">Compile the code</span></span>  
<span data-ttu-id="72bc0-112">Erstellen Sie ein Visual Basic Konsolen Anwendungsprojekt mit einer- `Imports` Anweisung für den System. Linq-Namespace.</span><span class="sxs-lookup"><span data-stu-id="72bc0-112">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="72bc0-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="72bc0-113">See also</span></span>

- [<span data-ttu-id="72bc0-114">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72bc0-114">LINQ to Objects (Visual Basic)</span></span>](linq-to-objects.md)
- [<span data-ttu-id="72bc0-115">LINQ and File Directories (Visual Basic) (LINQ und Dateiverzeichnisse (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="72bc0-115">LINQ and File Directories (Visual Basic)</span></span>](linq-and-file-directories.md)
