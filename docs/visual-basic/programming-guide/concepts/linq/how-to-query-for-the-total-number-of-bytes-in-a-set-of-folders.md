---
title: 'Gewusst wie: Abfragen der Gesamtzahl von Bytes in einem Ordnersatz (LINQ) (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: bfe85ed2-44dc-4ef1-aac7-241622b80a69
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: bda25acd3065898eeb61dce83d46d7526e825add
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-visual-basic"></a><span data-ttu-id="e816c-102">Gewusst wie: Abfragen der Gesamtzahl von Bytes in einem Ordnersatz (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e816c-102">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="e816c-103">Dieses Beispiel zeigt, wie die Gesamtanzahl der Bytes, die von allen Dateien in einem angegebenen Ordner und allen Unterordnern verwendet abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e816c-103">This example shows how to retrieve the total number of bytes used by all the files in a specified folder and all its subfolders.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e816c-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e816c-104">Example</span></span>  
 <span data-ttu-id="e816c-105">Die <xref:System.Linq.Enumerable.Sum%2A>-Methode fügt die Werte aller Elemente, die im ausgewählten der `select` -Klausel.</xref:System.Linq.Enumerable.Sum%2A></span><span class="sxs-lookup"><span data-stu-id="e816c-105">The <xref:System.Linq.Enumerable.Sum%2A> method adds the values of all the items selected in the `select` clause.</span></span> <span data-ttu-id="e816c-106">Sie können diese Abfrage zum Abrufen von der größten oder kleinsten Datei im angegebenen Verzeichnis durch Aufrufen der <xref:System.Linq.Enumerable.Min%2A>oder die <xref:System.Linq.Enumerable.Max%2A>Methode statt <xref:System.Linq.Enumerable.Sum%2A>.</xref:System.Linq.Enumerable.Sum%2A> </xref:System.Linq.Enumerable.Max%2A> </xref:System.Linq.Enumerable.Min%2A> einfach ändern.</span><span class="sxs-lookup"><span data-stu-id="e816c-106">You can easily modify this query to retrieve the biggest or smallest file in the specified directory tree by calling the <xref:System.Linq.Enumerable.Min%2A> or <xref:System.Linq.Enumerable.Max%2A> method instead of <xref:System.Linq.Enumerable.Sum%2A>.</span></span>  
  
```vb  
Module QueryTotalBytes  
    Sub Main()  
  
        ' Change the drive\path if necessary.  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0\VB"  
  
        'Take a snapshot of the folder contents.  
        ' This method assumes that the application has discovery permissions  
        ' for all folders under the specified path.  
        Dim fileList = My.Computer.FileSystem.GetFiles _  
                  (root, FileIO.SearchOption.SearchAllSubDirectories, "*.*")  
  
        Dim fileQuery = From file In fileList _  
                        Select GetFileLength(file)  
  
        ' Force execution and cache the results to avoid multiple trips to the file system.  
        Dim fileLengths = fileQuery.ToArray()  
  
        ' Find the largest file  
        Dim maxSize = Aggregate aFile In fileLengths Into Max()  
  
        ' Find the total number of bytes  
        Dim totalBytes = Aggregate aFile In fileLengths Into Sum()  
  
        Console.WriteLine("The largest file is " & maxSize & " bytes")  
        Console.WriteLine("There are " & totalBytes & " total bytes in " & _  
                          fileList.Count & " files under " & root)  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
    ' This method is used to catch the possible exception  
    ' that can be raised when accessing the FileInfo.Length property.  
    Function GetFileLength(ByVal filename As String) As Long  
        Dim retval As Long  
        Try  
            Dim fi As New System.IO.FileInfo(filename)  
            retval = fi.Length  
        Catch ex As System.IO.FileNotFoundException  
            ' If a file is no longer present,  
            ' just return zero bytes.   
            retval = 0  
        End Try  
  
        Return retval  
    End Function  
End Module  
```  
  
 <span data-ttu-id="e816c-107">Wenn Sie nur die Anzahl der Bytes in einer angegebenen Verzeichnisstruktur ermittelt haben, können Sie dies tun effizienter ohne Erstellen einer LINQ-Abfrage, die hervorruft, den Aufwand für die Erstellung der Sammlung Liste als Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="e816c-107">If you only have to count the number of bytes in a specified directory tree, you can do this more efficiently without creating a LINQ query, which incurs the overhead of creating the list collection as a data source.</span></span> <span data-ttu-id="e816c-108">Die Nützlichkeit der LINQ-Ansatz wird erhöht, wenn die Abfrage komplexer wird oder wenn Sie mehrere Abfragen für dieselbe Datenquelle ausführen.</span><span class="sxs-lookup"><span data-stu-id="e816c-108">The usefulness of the LINQ approach increases as the query becomes more complex, or when you have to run multiple queries against the same data source.</span></span>  
  
 <span data-ttu-id="e816c-109">Die Abfrage ruft eine separate Methode, um die Dateilänge abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e816c-109">The query calls out to a separate method to obtain the file length.</span></span> <span data-ttu-id="e816c-110">Grund dafür ist die mögliche Ausnahme eintritt, die ausgelöst wird, wenn die Datei gelöscht wurde, in einem anderen Thread nach der <xref:System.IO.FileInfo>Objekt erstellt wurde, im Aufruf von `GetFiles`.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="e816c-110">It does this in order to consume the possible exception that will be raised if the file was deleted on another thread after the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="e816c-111">Obwohl die <xref:System.IO.FileInfo>Objekt bereits erstellt wurde, kann die Ausnahme auftreten, da ein <xref:System.IO.FileInfo>Objekt versucht, aktualisieren Sie die <xref:System.IO.FileInfo.Length%2A>-Eigenschaft mit der aktuellen Länge beim ersten Zugriff auf die Eigenschaft.</xref:System.IO.FileInfo.Length%2A> </xref:System.IO.FileInfo> </xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="e816c-111">Even though the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property with the most current length the first time the property is accessed.</span></span> <span data-ttu-id="e816c-112">Indem diese Operation in einen Try-Catch-Block außerhalb der Abfrage, folgt der Code die Regel vermeiden Vorgänge in Abfragen, die Nebeneffekte verursachen können.</span><span class="sxs-lookup"><span data-stu-id="e816c-112">By putting this operation in a try-catch block outside the query, the code follows the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="e816c-113">Im Allgemeinen geboten große Sorgfalt wenn Ausnahmen sicherstellen, dass eine Anwendung nicht in einem unbekannten Zustand gelassen wird.</span><span class="sxs-lookup"><span data-stu-id="e816c-113">In general, great care must be taken when you consume exceptions to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e816c-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e816c-114">Compiling the Code</span></span>  
 <span data-ttu-id="e816c-115">Erstellen eines Projekts, die auf .NET Framework, Version 3.5 oder höher mit einem Verweis auf System.Core.dll und eine `Imports` -Anweisung für den Namespace "System.Linq".</span><span class="sxs-lookup"><span data-stu-id="e816c-115">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a   `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e816c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e816c-116">See Also</span></span>  
 <span data-ttu-id="e816c-117">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span><span class="sxs-lookup"><span data-stu-id="e816c-117">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span></span>  
<span data-ttu-id="e816c-118"> [LINQ und Dateiverzeichnisse (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span><span class="sxs-lookup"><span data-stu-id="e816c-118"> [LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span></span>
