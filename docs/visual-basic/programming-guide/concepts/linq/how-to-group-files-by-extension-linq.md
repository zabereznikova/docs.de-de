---
title: 'Gewusst wie: Gruppieren von Dateien nach Erweiterung (LINQ)'
ms.date: 07/20/2015
ms.assetid: 904dc6d7-7162-4655-a7f4-5785d669bc5a
ms.openlocfilehash: 67beec0d3681bf7f0b04d9a402566076fd27ceba
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347482"
---
# <a name="how-to-group-files-by-extension-linq-visual-basic"></a><span data-ttu-id="608de-102">Gewusst wie: Gruppieren von Dateien nach Erweiterung (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="608de-102">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="608de-103">In dieses Beispiel wird veranschaulicht, wie Sie mithilfe von LINQ erweiterte Gruppierungs- und Sortiervorgänge mit Datei- oder Ordnerlisten ausführen können.</span><span class="sxs-lookup"><span data-stu-id="608de-103">This example shows how LINQ can be used to perform advanced grouping and sorting operations on lists of files or folders.</span></span> <span data-ttu-id="608de-104">Es zeigt auch, wie der Bildlauf für die Ausgabe im Konsolenfenster mithilfe der Methoden <xref:System.Linq.Enumerable.Skip%2A> und <xref:System.Linq.Enumerable.Take%2A> durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="608de-104">It also shows how to page output in the console window by using the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="608de-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="608de-105">Example</span></span>  
 <span data-ttu-id="608de-106">Die folgende Abfrage zeigt, wie Sie den Inhalt einer angegebenen Verzeichnisstruktur nach der Dateierweiterung gruppieren.</span><span class="sxs-lookup"><span data-stu-id="608de-106">The following query shows how to group the contents of a specified directory tree by the file name extension.</span></span>  
  
```vb  
Module GroupByExtension  
    Public Sub Main()  
  
        ' Root folder to query, along with all subfolders.  
        Dim startFolder As String = "C:\program files\Microsoft Visual Studio 9.0\VB\"  
  
        ' Used in WriteLine() to skip over startfolder in output lines.  
        Dim rootLength As Integer = startFolder.Length  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(startFolder)  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' Create the query.  
        Dim queryGroupByExt = From file In fileList _  
                          Group By file.Extension.ToLower() Into fileGroup = Group _  
                          Order By ToLower _  
                          Select fileGroup  
  
        ' Execute the query. By storing the result we can  
        ' page the display with good performance.  
        Dim groupByExtList = queryGroupByExt.ToList()  
  
        ' Display one group at a time. If the number of   
        ' entries is greater than the number of lines  
        ' in the console window, then page the output.  
        Dim trimLength = startFolder.Length  
        PageOutput(groupByExtList, trimLength)  
  
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
                Console.WriteLine(fg(0).Extension)  
  
                ' Get the next page of results  
                ' No more than one filename per page  
                Dim resultPage = From file In fg _  
                                Skip currentLine Take numLines  
  
                ' Execute the query. Trim the display output.  
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
  
 <span data-ttu-id="608de-107">Die Ausgabe dieses Programms kann je nach den Details des lokalen Dateisystems und der Einstellung für `startFolder` lang sein.</span><span class="sxs-lookup"><span data-stu-id="608de-107">The output from this program can be long, depending on the details of the local file system and what the `startFolder` is set to.</span></span> <span data-ttu-id="608de-108">Um alle Ergebnisse anzuzeigen, wird in diesem Beispiel gezeigt, wie Sie Ergebnisse seitenweise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="608de-108">To enable viewing of all results, this example shows how to page through results.</span></span> <span data-ttu-id="608de-109">Die gleichen Techniken können auf Windows- und Webanwendungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="608de-109">The same techniques can be applied to Windows and Web applications.</span></span> <span data-ttu-id="608de-110">Beachten Sie, dass eine geschachtelte `For Each`-Schleife erforderlich ist, da der Code die Elemente in einer Gruppe seitenweise anzeigt.</span><span class="sxs-lookup"><span data-stu-id="608de-110">Notice that because the code pages the items in a group, a nested `For Each` loop is required.</span></span> <span data-ttu-id="608de-111">Es ist auch sinnvoll, die aktuelle Position in der Liste berechnen zu können und es dem Benutzer zu ermöglichen, das seitenweise Anzeigen anzuhalten und das Programm zu beenden.</span><span class="sxs-lookup"><span data-stu-id="608de-111">There is also some additional logic to compute the current position in the list, and to enable the user to stop paging and exit the program.</span></span> <span data-ttu-id="608de-112">In diesem speziellen Fall wird die Abfrage zum seitenweise Anzeigen gegen die zwischengespeicherten Ergebnisse aus der ursprünglichen Abfrage ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="608de-112">In this particular case, the paging query is run against the cached results from the original query.</span></span> <span data-ttu-id="608de-113">In anderen Kontexten wie LINQ to SQL ist ein solches Zwischenspeichern nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="608de-113">In other contexts, such as LINQ to SQL, such caching is not required.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="608de-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="608de-114">Compile the code</span></span>  
<span data-ttu-id="608de-115">Erstellen Sie ein Visual Basic Konsolen Anwendungsprojekt mit einer `Imports`-Anweisung für den System. Linq-Namespace.</span><span class="sxs-lookup"><span data-stu-id="608de-115">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="608de-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="608de-116">See also</span></span>

- [<span data-ttu-id="608de-117">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="608de-117">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- [<span data-ttu-id="608de-118">LINQ and File Directories (Visual Basic) (LINQ und Dateiverzeichnisse (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="608de-118">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
