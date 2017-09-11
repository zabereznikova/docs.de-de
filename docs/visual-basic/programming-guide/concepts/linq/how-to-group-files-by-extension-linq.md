---
title: 'Gewusst wie: Gruppieren von Dateien nach Erweiterung (LINQ) (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 904dc6d7-7162-4655-a7f4-5785d669bc5a
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8b78cbaf8b0f20c6b7ab14640dffd61e9657dc9b
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-group-files-by-extension-linq-visual-basic"></a><span data-ttu-id="3343a-102">Gewusst wie: Gruppieren von Dateien nach Erweiterung (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3343a-102">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="3343a-103">Dieses Beispiel zeigt, wie LINQ zum Ausführen der erweiterten gruppieren und Sortieren von Operationen mit Listen von Dateien oder Ordnern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3343a-103">This example shows how LINQ can be used to perform advanced grouping and sorting operations on lists of files or folders.</span></span> <span data-ttu-id="3343a-104">Es wird veranschaulicht, wie die Ausgabe im Konsolenfenster mit Seite der <xref:System.Linq.Enumerable.Skip%2A>und <xref:System.Linq.Enumerable.Take%2A>Methoden.</xref:System.Linq.Enumerable.Take%2A> </xref:System.Linq.Enumerable.Skip%2A></span><span class="sxs-lookup"><span data-stu-id="3343a-104">It also shows how to page output in the console window by using the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3343a-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3343a-105">Example</span></span>  
 <span data-ttu-id="3343a-106">Die folgende Abfrage zeigt, wie Sie den Inhalt einer angegebenen Verzeichnisstruktur nach der Erweiterung zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="3343a-106">The following query shows how to group the contents of a specified directory tree by the file name extension.</span></span>  
  
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
  
    ' Pages console diplay for large query results. No more than one group per page.  
    ' This sub specifically works with group queries of FileInfo objects  
    ' but can be modified for any type.  
    Sub PageOutput(ByVal groupQuery, ByVal charsToSkip)  
  
        ' "3" = 1 line for extension key + 1 for "Press any key" + 1 for input cursor.  
        Dim numLines As Integer = Console.WindowHeight - 3  
        ' Flag to indicate whether there are more results to diplay  
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
  
 <span data-ttu-id="3343a-107">Die Ausgabe dieses Programms kann lang sein, abhängig von den Details des lokalen Dateisystems und was die `startFolder` auf festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3343a-107">The output from this program can be long, depending on the details of the local file system and what the `startFolder` is set to.</span></span> <span data-ttu-id="3343a-108">Um alle Ergebnisse anzeigen zu aktivieren, in diesem Beispiel wird veranschaulicht, wie Ergebnisse seitenweise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3343a-108">To enable viewing of all results, this example shows how to page through results.</span></span> <span data-ttu-id="3343a-109">Die gleichen Techniken können auf Windows-und Webanwendungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="3343a-109">The same techniques can be applied to Windows and Web applications.</span></span> <span data-ttu-id="3343a-110">Beachten Sie, dass, da der Code die Elemente in einer Gruppe, die eine geschachtelte Seiten `For Each` Schleife ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3343a-110">Notice that because the code pages the items in a group, a nested `For Each` loop is required.</span></span> <span data-ttu-id="3343a-111">Es gibt auch einige zusätzliche Logik, um die aktuelle Position in der Liste zu berechnen und ermöglichen es dem Benutzer Paging zu stoppen und das Programm zu beenden.</span><span class="sxs-lookup"><span data-stu-id="3343a-111">There is also some additional logic to compute the current position in the list, and to enable the user to stop paging and exit the program.</span></span> <span data-ttu-id="3343a-112">In diesem Fall wird die Pagingabfrage für die zwischengespeicherten Ergebnisse aus der ursprünglichen Abfrage ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3343a-112">In this particular case, the paging query is run against the cached results from the original query.</span></span> <span data-ttu-id="3343a-113">In anderen Kontexten, z. B. LINQ to SQL ist das solches Zwischenspeichern nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3343a-113">In other contexts, such as LINQ to SQL, such caching is not required.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3343a-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="3343a-114">Compiling the Code</span></span>  
 <span data-ttu-id="3343a-115">Erstellen eines Projekts, die auf .NET Framework, Version 3.5 oder höher mit einem Verweis auf System.Core.dll und eine `Imports` -Anweisung für den Namespace "System.Linq".</span><span class="sxs-lookup"><span data-stu-id="3343a-115">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a   `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3343a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3343a-116">See Also</span></span>  
 <span data-ttu-id="3343a-117">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span><span class="sxs-lookup"><span data-stu-id="3343a-117">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span></span>  
<span data-ttu-id="3343a-118"> [LINQ und Dateiverzeichnisse (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span><span class="sxs-lookup"><span data-stu-id="3343a-118"> [LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span></span>
