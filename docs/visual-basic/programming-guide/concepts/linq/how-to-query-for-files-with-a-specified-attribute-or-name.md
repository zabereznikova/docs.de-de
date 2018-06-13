---
title: 'Vorgehensweise: Abfragen von Dateien mit einem angegebenen Attribut oder Namen (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b26026a3-3f43-448f-a582-259997af6be0
ms.openlocfilehash: 7a8314ba6109f25b4bc5f5952b358695844eadab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33642908"
---
# <a name="how-to-query-for-files-with-a-specified-attribute-or-name-visual-basic"></a><span data-ttu-id="2f3e4-102">Vorgehensweise: Abfragen von Dateien mit einem angegebenen Attribut oder Namen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f3e4-102">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>
<span data-ttu-id="2f3e4-103">In diesem Beispiel wird veranschaulicht, wie nach allen Dateien mit einem angegebenen Suffix (z.B. „.txt“) in einer angegebenen Verzeichnisstruktur gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="2f3e4-103">This example shows how to find all files that have a specified file name extension (for example ".txt") in a specified directory tree.</span></span> <span data-ttu-id="2f3e4-104">Es wird auch gezeigt, wie basierend auf dem Zeitpunkt der Erstellung entweder die neueste oder älteste Datei in der Struktur zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2f3e4-104">It also shows how to return either the newest or oldest file in the tree based on the creation time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f3e4-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2f3e4-105">Example</span></span>  
  
```vb  
Module FindFileByExtension  
    Sub Main()  
  
        ' Change the drive\path if necessary  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0"  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(root)  
  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' This query will produce the full path for all .txt files  
        ' under the specified folder including subfolders.  
        ' It orders the list according to the file name.  
        Dim fileQuery = From file In fileList _  
                        Where file.Extension = ".txt" _  
                        Order By file.Name _  
                        Select file  
  
        For Each file In fileQuery  
            Console.WriteLine(file.FullName)  
        Next  
  
        ' Create and execute a new query by using  
        ' the previous query as a starting point.  
        ' fileQuery is not executed again until the  
        ' call to Last  
        Dim fileQuery2 = From file In fileQuery _  
                         Order By file.CreationTime _  
                         Select file.Name, file.CreationTime  
  
        ' Execute the query  
        Dim newestFile = fileQuery2.Last  
  
        Console.WriteLine("\r\nThe newest .txt file is {0}. Creation time: {1}", _  
                newestFile.Name, newestFile.CreationTime)  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
  
    End Sub  
End Module  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2f3e4-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2f3e4-106">Compiling the Code</span></span>  
 <span data-ttu-id="2f3e4-107">Erstellen Sie ein Projekt, das auf .NET Framework, Version 3.5 oder höher mit einem Verweis auf "System.Core.dll" abzielt und einen `Imports` -Anweisung für den "System.Linq"-Namespace.</span><span class="sxs-lookup"><span data-stu-id="2f3e4-107">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a   `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f3e4-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f3e4-108">See Also</span></span>  
 [<span data-ttu-id="2f3e4-109">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f3e4-109">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
 [<span data-ttu-id="2f3e4-110">LINQ and File Directories (Visual Basic) (LINQ und Dateiverzeichnisse (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="2f3e4-110">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
