---
title: "Gewusst wie: Abfragen der größten Datei oder Dateien in einer Verzeichnisstruktur (LINQ) (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: 8c1c9f0c-95dd-4222-9be2-9ec026a13e81
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
ms.openlocfilehash: 95c5197b2cb66745201ceac89b78fe67b95ecb75
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-visual-basic"></a><span data-ttu-id="8e84f-102">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic) (Gewusst wie: Abfragen der größten Datei oder der größten Dateien in einer Verzeichnisstruktur (LINQ) (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="8e84f-102">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="8e84f-103">Dieses Beispiel zeigt fünf Abfragen in Bezug auf die Dateigröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="8e84f-103">This example shows five queries related to file size in bytes:</span></span>  
  
-   <span data-ttu-id="8e84f-104">So rufen Sie die Größe in Bytes der größten Datei ab.</span><span class="sxs-lookup"><span data-stu-id="8e84f-104">How to retrieve the size in bytes of the largest file.</span></span>  
  
-   <span data-ttu-id="8e84f-105">So rufen Sie die Größe in Bytes der kleinsten Datei ab.</span><span class="sxs-lookup"><span data-stu-id="8e84f-105">How to retrieve the size in bytes of the smallest file.</span></span>  
  
-   <span data-ttu-id="8e84f-106">Gewusst wie: Abrufen der <xref:System.IO.FileInfo>Objektdatei größten oder kleinsten aus einem oder mehreren Ordnern unter einem angegebenen Stammordner.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="8e84f-106">How to retrieve the <xref:System.IO.FileInfo> object largest or smallest file from one or more folders under a specified root folder.</span></span>  
  
-   <span data-ttu-id="8e84f-107">So rufen Sie eine Sequenz, wie z. B. die 10 größten Dateien ab.</span><span class="sxs-lookup"><span data-stu-id="8e84f-107">How to retrieve a sequence such as the 10 largest files.</span></span>  
  
-   <span data-ttu-id="8e84f-108">So ordnen Sie Dateien in Gruppen auf Grundlage ihrer Dateigröße in Bytes, der Dateien, die kleiner als eine angegebene Größe werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="8e84f-108">How to order files into groups based on their file size in bytes, ignoring files that are less than a specified size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e84f-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8e84f-109">Example</span></span>  
 <span data-ttu-id="8e84f-110">Das folgende Beispiel enthält fünf separate Abfragen, die zeigen, wie Sie Abfragen und Gruppendateien, abhängig von ihrer Dateigröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="8e84f-110">The following example contains five separate queries that show how to query and group files, depending on their file size in bytes.</span></span> <span data-ttu-id="8e84f-111">Sie können diese Beispiele, um die Abfrage auf eine andere Eigenschaft des problemlos ändern die <xref:System.IO.FileInfo>Objekt.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="8e84f-111">You can easily modify these examples to base the query on some other property of the <xref:System.IO.FileInfo> object.</span></span>  
  
```vb  
Module QueryBySize  
    Sub Main()  
  
        ' Change the drive\path if necessary  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0"  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(root)  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' Return the size of the largest file  
        Dim maxSize = Aggregate aFile In fileList Into Max(GetFileLength(aFile))  
  
        'Dim maxSize = fileLengths.Max  
        Console.WriteLine("The length of the largest file under {0} is {1}", _  
                          root, maxSize)  
  
        ' Return the FileInfo object of the largest file  
        ' by sorting and selecting from the beginning of the list  
        Dim filesByLengDesc = From file In fileList _  
                              Let filelength = GetFileLength(file) _  
                              Where filelength > 0 _  
                              Order By filelength Descending _  
                              Select file  
  
        Dim longestFile = filesByLengDesc.First  
  
        Console.WriteLine("The largest file under {0} is {1} with a length of {2} bytes", _  
                          root, longestFile.FullName, longestFile.Length)  
  
        Dim smallestFile = filesByLengDesc.Last  
  
        Console.WriteLine("The smallest file under {0} is {1} with a length of {2} bytes", _  
                                root, smallestFile.FullName, smallestFile.Length)  
  
        ' Return the FileInfos for the 10 largest files  
        ' Based on a previous query, but nothing is executed  
        ' until the For Each statement below.  
        Dim tenLargest = From file In filesByLengDesc Take 10  
  
        Console.WriteLine("The 10 largest files under {0} are:", root)  
  
        For Each fi As System.IO.FileInfo In tenLargest  
            Console.WriteLine("{0}: {1} bytes", fi.FullName, fi.Length)  
        Next  
  
        ' Group files according to their size,  
        ' leaving out the ones under 200K  
        Dim sizeGroups = From file As System.IO.FileInfo In fileList _  
                         Where file.Length > 0 _  
                         Let groupLength = file.Length / 100000 _  
                         Group file By groupLength Into fileGroup = Group _  
                         Where groupLength >= 2 _  
                         Order By groupLength Descending  
  
        For Each group In sizeGroups  
            Console.WriteLine(group.groupLength + "00000")  
  
            For Each item As System.IO.FileInfo In group.fileGroup  
                Console.WriteLine("   {0}: {1}", item.Name, item.Length)  
            Next  
        Next  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
  
    End Sub  
  
    ' This method is used to catch the possible exception  
    ' that can be raised when accessing the FileInfo.Length property.  
    ' In this particular case, it is safe to ignore the exception.  
    Function GetFileLength(ByVal fi As System.IO.FileInfo) As Long  
        Dim retval As Long  
        Try  
            retval = fi.Length  
        Catch ex As FileNotFoundException  
            ' If a file is no longer present,  
            ' just return zero bytes.   
            retval = 0  
        End Try  
  
        Return retval  
    End Function  
End Module  
```  
  
 <span data-ttu-id="8e84f-112">Zurückgeben, führen Sie eine oder mehrere <xref:System.IO.FileInfo>Objekte, die Abfrage zuerst prüft jedes einzelne Objekt in der Datenquelle, und sie dann den Wert der Length-Eigenschaft sortieren.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="8e84f-112">To return one or more complete <xref:System.IO.FileInfo> objects, the query first must examine each one in the data source, and then sort them by the value of their Length property.</span></span> <span data-ttu-id="8e84f-113">Anschließend kann das einzelne Objekt oder die Sequenz mit den größten Längen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8e84f-113">Then it can return the single one or the sequence with the greatest lengths.</span></span> <span data-ttu-id="8e84f-114">Mit <xref:System.Linq.Enumerable.First%2A>auf das erste Element in einer Liste zurück.</xref:System.Linq.Enumerable.First%2A></span><span class="sxs-lookup"><span data-stu-id="8e84f-114">Use <xref:System.Linq.Enumerable.First%2A> to return the first element in a list.</span></span> <span data-ttu-id="8e84f-115">Verwendung <xref:System.Linq.Enumerable.Take%2A>auf die ersten n Elemente zurückzugeben.</xref:System.Linq.Enumerable.Take%2A></span><span class="sxs-lookup"><span data-stu-id="8e84f-115">Use <xref:System.Linq.Enumerable.Take%2A> to return the first n number of elements.</span></span> <span data-ttu-id="8e84f-116">Geben Sie eine absteigende Sortierreihenfolge die kleinsten Elemente am Anfang der Liste platzieren.</span><span class="sxs-lookup"><span data-stu-id="8e84f-116">Specify a descending sort order to put the smallest elements at the start of the list.</span></span>  
  
 <span data-ttu-id="8e84f-117">Die Abfrage ruft eine separate Methode zum Abrufen der Dateigröße in Bytes, die mögliche Ausnahme eintritt, die in dem Fall ausgelöst werden, in dem eine Datei in einem anderen Thread in der Zeit gelöscht wurde, die <xref:System.IO.FileInfo>Objekt erstellt wurde, im Aufruf von `GetFiles`.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="8e84f-117">The query calls out to a separate method to obtain the file size in bytes in order to consume the possible exception that will be raised in the case where a file was deleted on another thread in the time period since the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="8e84f-118">Auch die <xref:System.IO.FileInfo>Objekt bereits erstellt wurde, kann die Ausnahme auftreten, da ein <xref:System.IO.FileInfo>Objekt versucht, aktualisieren Sie die <xref:System.IO.FileInfo.Length%2A>Eigenschaft, indem die aktuellste Größe in Bytes beim ersten Zugriff auf die Eigenschaft.</xref:System.IO.FileInfo.Length%2A> </xref:System.IO.FileInfo> </xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="8e84f-118">Even through the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property by using the most current size in bytes the first time the property is accessed.</span></span> <span data-ttu-id="8e84f-119">Indem diese Operation in einen Try-Catch-Block außerhalb der Abfrage, folgen wir die Regel vermeiden Vorgänge in Abfragen, die Nebeneffekte verursachen können.</span><span class="sxs-lookup"><span data-stu-id="8e84f-119">By putting this operation in a try-catch block outside the query, we follow the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="8e84f-120">Im Allgemeinen geboten große Sorgfalt beim Behandeln von Ausnahmen sicherstellen, dass eine Anwendung nicht in einem unbekannten Zustand gelassen wird.</span><span class="sxs-lookup"><span data-stu-id="8e84f-120">In general, great care must be taken when consuming exceptions, to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8e84f-121">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="8e84f-121">Compiling the Code</span></span>  
 <span data-ttu-id="8e84f-122">Erstellen eines Projekts, die auf .NET Framework, Version 3.5 oder höher mit einem Verweis auf System.Core.dll und eine `Imports` -Anweisung für den Namespace "System.Linq".</span><span class="sxs-lookup"><span data-stu-id="8e84f-122">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e84f-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e84f-123">See Also</span></span>  
 <span data-ttu-id="8e84f-124">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span><span class="sxs-lookup"><span data-stu-id="8e84f-124">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span></span>  
<span data-ttu-id="8e84f-125"> [LINQ und Dateiverzeichnisse (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span><span class="sxs-lookup"><span data-stu-id="8e84f-125"> [LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span></span>
