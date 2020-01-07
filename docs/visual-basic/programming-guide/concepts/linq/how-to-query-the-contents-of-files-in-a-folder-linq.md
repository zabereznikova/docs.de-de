---
title: Abfragen des Inhalts von Dateien in einem Ordner (LINQ)
ms.date: 07/20/2015
ms.assetid: edacbcd3-f3e4-4429-a8be-28a58dc0dd70
ms.openlocfilehash: 3ad5fd6c893d590d46be67e6320ac5b915829f4b
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346047"
---
# <a name="how-to-query-the-contents-of-files-in-a-folder-linq-visual-basic"></a><span data-ttu-id="e2525-102">Abfragen des Inhalts von Dateien in einem Ordner (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2525-102">How to query the contents of files in a folder (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="e2525-103">Dieses Beispiel zeigt, wie Sie die Abfrage über alle Dateien in einer angegebenen Verzeichnisstruktur durchführen, jede Datei öffnen, und ihre Inhalte überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e2525-103">This example shows how to query over all the files in a specified directory tree, open each file, and inspect its contents.</span></span> <span data-ttu-id="e2525-104">Diese Technik kann zum Erstellen von Indizes oder umgekehrten Indizes des Inhalts einer Verzeichnisstruktur verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e2525-104">This type of technique could be used to create indexes or reverse indexes of the contents of a directory tree.</span></span> <span data-ttu-id="e2525-105">In diesem Beispiel wird eine einfache Zeichenfolgensuche ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e2525-105">A simple string search is performed in this example.</span></span> <span data-ttu-id="e2525-106">Komplexere Formen des Mustervergleichs können jedoch mit einem regulären Ausdruck ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e2525-106">However, more complex types of pattern matching can be performed with a regular expression.</span></span> <span data-ttu-id="e2525-107">Weitere Informationen finden Sie unter Gewusst [wie: Kombinieren von LINQ-Abfragen mit regulären Ausdrücken (Visual Basic)](how-to-combine-linq-queries-with-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e2525-107">For more information, see [How to: Combine LINQ Queries with Regular Expressions (Visual Basic)](how-to-combine-linq-queries-with-regular-expressions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2525-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e2525-108">Example</span></span>  
  
```vb
Imports System.IO

Module Module1  
    'QueryContents  
    Public Sub Main()  
  
        ' Modify this path as necessary.  
        Dim startFolder = "C:\Program Files (x86)\Microsoft Visual Studio 14.0"  

        ' Take a snapshot of the folder contents.
        Dim dir As New DirectoryInfo(startFolder)
        Dim fileList = dir.GetFiles("*.*", SearchOption.AllDirectories)

        Dim searchTerm = "Welcome"

        ' Search the contents of each file.
        ' A regular expression created with the RegEx class
        ' could be used instead of the Contains method.
        Dim queryMatchingFiles = From file In fileList _
                                 Where file.Extension = ".html" _
                                 Let fileText = GetFileText(file.FullName) _
                                 Where fileText.Contains(searchTerm) _
                                 Select file.FullName

        Console.WriteLine("The term " & searchTerm & " was found in:")

        ' Execute the query.
        For Each filename In queryMatchingFiles
            Console.WriteLine(filename)
        Next

        ' Keep the console window open in debug mode.
        Console.WriteLine("Press any key to exit")
        Console.ReadKey()

    End Sub

    ' Read the contents of the file. This is done in a separate
    ' function in order to handle potential file system errors.
    Function GetFileText(name As String) As String

        ' If the file has been deleted, the right thing
        ' to do in this case is return an empty string.
        Dim fileContents = String.Empty

        ' If the file has been deleted since we took
        ' the snapshot, ignore it and return the empty string.
        If File.Exists(name) Then
            fileContents = File.ReadAllText(name)
        End If

        Return fileContents

    End Function
End Module
```

## <a name="compile-the-code"></a><span data-ttu-id="e2525-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e2525-109">Compile the code</span></span>

<span data-ttu-id="e2525-110">Erstellen Sie ein Visual Basic Konsolen Anwendungsprojekt, kopieren Sie das Codebeispiel, fügen Sie es ein, und passen Sie den Wert des Start Objekts in den Projekteigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="e2525-110">Create a Visual Basic console application project, copy and paste the code sample, and adjust the Startup object value in the project properties.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2525-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2525-111">See also</span></span>

- [<span data-ttu-id="e2525-112">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2525-112">LINQ to Objects (Visual Basic)</span></span>](linq-to-objects.md)
- [<span data-ttu-id="e2525-113">LINQ and File Directories (Visual Basic) (LINQ und Dateiverzeichnisse (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="e2525-113">LINQ and File Directories (Visual Basic)</span></span>](linq-and-file-directories.md)
