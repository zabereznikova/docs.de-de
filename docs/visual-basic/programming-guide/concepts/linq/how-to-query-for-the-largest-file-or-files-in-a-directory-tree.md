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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 055cbdd5a5903417ab382d390e1215f0319c0b5a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-visual-basic"></a>How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic) (Gewusst wie: Abfragen der größten Datei oder der größten Dateien in einer Verzeichnisstruktur (LINQ) (Visual Basic))
Dieses Beispiel zeigt fünf Abfragen in Bezug auf die Dateigröße in Bytes.  
  
-   So rufen Sie die Größe in Bytes der größten Datei ab.  
  
-   So rufen Sie die Größe in Bytes der kleinsten Datei ab.  
  
-   Gewusst wie: Abrufen der <xref:System.IO.FileInfo>Objektdatei größten oder kleinsten aus einem oder mehreren Ordnern unter einem angegebenen Stammordner.</xref:System.IO.FileInfo>  
  
-   So rufen Sie eine Sequenz, wie z. B. die 10 größten Dateien ab.  
  
-   So ordnen Sie Dateien in Gruppen auf Grundlage ihrer Dateigröße in Bytes, der Dateien, die kleiner als eine angegebene Größe werden ignoriert.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel enthält fünf separate Abfragen, die zeigen, wie Sie Abfragen und Gruppendateien, abhängig von ihrer Dateigröße in Bytes. Sie können diese Beispiele, um die Abfrage auf eine andere Eigenschaft des problemlos ändern die <xref:System.IO.FileInfo>Objekt.</xref:System.IO.FileInfo>  
  
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
  
 Zurückgeben, führen Sie eine oder mehrere <xref:System.IO.FileInfo>Objekte, die Abfrage zuerst prüft jedes einzelne Objekt in der Datenquelle, und sie dann den Wert der Length-Eigenschaft sortieren.</xref:System.IO.FileInfo> Anschließend kann das einzelne Objekt oder die Sequenz mit den größten Längen zurückgegeben werden. Mit <xref:System.Linq.Enumerable.First%2A>auf das erste Element in einer Liste zurück.</xref:System.Linq.Enumerable.First%2A> Verwendung <xref:System.Linq.Enumerable.Take%2A>auf die ersten n Elemente zurückzugeben.</xref:System.Linq.Enumerable.Take%2A> Geben Sie eine absteigende Sortierreihenfolge die kleinsten Elemente am Anfang der Liste platzieren.  
  
 Die Abfrage ruft eine separate Methode zum Abrufen der Dateigröße in Bytes, die mögliche Ausnahme eintritt, die in dem Fall ausgelöst werden, in dem eine Datei in einem anderen Thread in der Zeit gelöscht wurde, die <xref:System.IO.FileInfo>Objekt erstellt wurde, im Aufruf von `GetFiles`.</xref:System.IO.FileInfo> Auch die <xref:System.IO.FileInfo>Objekt bereits erstellt wurde, kann die Ausnahme auftreten, da ein <xref:System.IO.FileInfo>Objekt versucht, aktualisieren Sie die <xref:System.IO.FileInfo.Length%2A>Eigenschaft, indem die aktuellste Größe in Bytes beim ersten Zugriff auf die Eigenschaft.</xref:System.IO.FileInfo.Length%2A> </xref:System.IO.FileInfo> </xref:System.IO.FileInfo> Indem diese Operation in einen Try-Catch-Block außerhalb der Abfrage, folgen wir die Regel vermeiden Vorgänge in Abfragen, die Nebeneffekte verursachen können. Im Allgemeinen geboten große Sorgfalt beim Behandeln von Ausnahmen sicherstellen, dass eine Anwendung nicht in einem unbekannten Zustand gelassen wird.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen eines Projekts, die auf .NET Framework, Version 3.5 oder höher mit einem Verweis auf System.Core.dll und eine `Imports` -Anweisung für den Namespace "System.Linq".  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)   
 [LINQ und Dateiverzeichnisse (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
