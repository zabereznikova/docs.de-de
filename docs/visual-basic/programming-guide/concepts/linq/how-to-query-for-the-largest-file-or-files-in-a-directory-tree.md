---
title: 'Gewusst wie: Abfragen der größten Datei oder der größten Dateien in einer Verzeichnisstruktur (LINQ)'
ms.date: 07/20/2015
ms.assetid: 8c1c9f0c-95dd-4222-9be2-9ec026a13e81
ms.openlocfilehash: 723a42e79f1def171a08b28986049ffa04945fc4
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266988"
---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-visual-basic"></a>How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic) (Gewusst wie: Abfragen der größten Datei oder der größten Dateien in einer Verzeichnisstruktur (LINQ) (Visual Basic))
Dieses Beispiel zeigt fünf Abfragen mit Bezug auf die Dateigröße in Bytes:  
  
- So rufen Sie die Größe in Bytes der größten Datei ab  
  
- So rufen Sie die Größe in Bytes der kleinsten Datei ab  
  
- So rufen Sie das <xref:System.IO.FileInfo>-Objekt der größten oder kleinsten Datei aus einem oder mehreren Ordnern unter einem bestimmten Stammordner ab  
  
- So rufen Sie eine Sequenz ab, wie z.B. die 10 größten Dateien  
  
- So ordnen Sie Dateien in Gruppen auf Grundlage ihrer Dateigröße in Bytes und ignorieren dabei die Dateien, die kleiner als eine angegebene Größe sind  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel enthält fünf separate Abfragen, die zeigen, wie Sie Dateien je nach ihrer Dateigröße in Bytes abfragen und gruppieren. Sie können diese Beispiele ganz einfach verändern, um die Abfrage auf eine andere Eigenschaft des <xref:System.IO.FileInfo>-Objekts anzuwenden.  
  
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
  
 Um mindestens ein abgeschlossenes <xref:System.IO.FileInfo>-Objekt zurückzugeben, muss die Abfrage jedes in der Datenquelle untersuchen und die Objekte dann nach Wert ihrer Length-Eigenschaft sortieren. Anschließend kann das einzelne Objekt oder die Sequenz mit den größten Längen zurückgegeben werden. Verwenden Sie <xref:System.Linq.Enumerable.First%2A>, um das erste Element in einer Liste zurückzugeben. Verwenden Sie <xref:System.Linq.Enumerable.Take%2A>, um die ersten n Elemente zurückzugeben. Geben Sie eine absteigende Sortierreihenfolge an, um die kleinsten Elemente zu Beginn der Liste anzuzeigen.  
  
 Die Abfrage ruft eine separate Methode zum Abrufen der Dateigröße in Bytes auf, um die mögliche Ausnahme zu verwenden, die in dem Fall ausgelöst wird, wenn eine Datei auf einem anderen Thread im Zeitraum, in dem das <xref:System.IO.FileInfo>-Objekt im Aufruf an `GetFiles` erstellt wurde, gelöscht wurde. Obwohl das <xref:System.IO.FileInfo>-Objekt bereits erstellt wurde, kann die Ausnahme auftreten, weil ein <xref:System.IO.FileInfo>-Objekt versucht, seine <xref:System.IO.FileInfo.Length%2A>-Eigenschaft mithilfe der aktuellsten Größe in Bytes beim ersten Zugriff auf die Eigenschaft zu aktualisieren. Indem dieser Vorgang in einen Try-Catch-Block außerhalb der Abfrage erfolgt, folgt der Code der Regel zum Vermeiden von Vorgängen in Abfragen, die Nebeneffekte verursachen können. Im Allgemeinen ist beim Abfangen von Ausnahmen große Sorgfalt geboten, damit einen Anwendung nicht in einem unbekannten Zustand gelassen wird.  
  
## <a name="compile-the-code"></a>Kompilieren des Codes  
Erstellen Sie ein Visual Basic-Konsolenanwendungsprojekt mit einer `Imports` Anweisung für den System.Linq-Namespace.
  
## <a name="see-also"></a>Weitere Informationen

- [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- [LINQ and File Directories (Visual Basic) (LINQ und Dateiverzeichnisse (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
