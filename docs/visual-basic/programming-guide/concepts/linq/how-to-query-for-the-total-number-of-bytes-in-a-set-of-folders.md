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
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 668a8a4d89f7b81c3aef9b4e1a46ad749c4a8341
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-visual-basic"></a>Gewusst wie: Abfragen der Gesamtzahl von Bytes in einem Ordnersatz (LINQ) (Visual Basic)
Dieses Beispiel zeigt, wie die Gesamtanzahl der Bytes, die von allen Dateien in einem angegebenen Ordner und allen Unterordnern verwendet abgerufen wird.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Linq.Enumerable.Sum%2A>-Methode fügt die Werte aller Elemente, die im ausgewählten der `select` -Klausel.</xref:System.Linq.Enumerable.Sum%2A> Sie können diese Abfrage zum Abrufen von der größten oder kleinsten Datei im angegebenen Verzeichnis durch Aufrufen der <xref:System.Linq.Enumerable.Min%2A>oder die <xref:System.Linq.Enumerable.Max%2A>Methode statt <xref:System.Linq.Enumerable.Sum%2A>.</xref:System.Linq.Enumerable.Sum%2A> </xref:System.Linq.Enumerable.Max%2A> </xref:System.Linq.Enumerable.Min%2A> einfach ändern.  
  
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
  
 Wenn Sie nur die Anzahl der Bytes in einer angegebenen Verzeichnisstruktur ermittelt haben, können Sie dies tun effizienter ohne Erstellen einer LINQ-Abfrage, die hervorruft, den Aufwand für die Erstellung der Sammlung Liste als Datenquelle. Die Nützlichkeit der LINQ-Ansatz wird erhöht, wenn die Abfrage komplexer wird oder wenn Sie mehrere Abfragen für dieselbe Datenquelle ausführen.  
  
 Die Abfrage ruft eine separate Methode, um die Dateilänge abzurufen. Grund dafür ist die mögliche Ausnahme eintritt, die ausgelöst wird, wenn die Datei gelöscht wurde, in einem anderen Thread nach der <xref:System.IO.FileInfo>Objekt erstellt wurde, im Aufruf von `GetFiles`.</xref:System.IO.FileInfo> Obwohl die <xref:System.IO.FileInfo>Objekt bereits erstellt wurde, kann die Ausnahme auftreten, da ein <xref:System.IO.FileInfo>Objekt versucht, aktualisieren Sie die <xref:System.IO.FileInfo.Length%2A>-Eigenschaft mit der aktuellen Länge beim ersten Zugriff auf die Eigenschaft.</xref:System.IO.FileInfo.Length%2A> </xref:System.IO.FileInfo> </xref:System.IO.FileInfo> Indem diese Operation in einen Try-Catch-Block außerhalb der Abfrage, folgt der Code die Regel vermeiden Vorgänge in Abfragen, die Nebeneffekte verursachen können. Im Allgemeinen geboten große Sorgfalt wenn Ausnahmen sicherstellen, dass eine Anwendung nicht in einem unbekannten Zustand gelassen wird.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen eines Projekts, die auf .NET Framework, Version 3.5 oder höher mit einem Verweis auf System.Core.dll und eine `Imports` -Anweisung für den Namespace "System.Linq".  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)   
 [LINQ und Dateiverzeichnisse (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
