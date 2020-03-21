---
title: 'Gewusst wie: Abfragen der Gesamtzahl an Bytes in einem Ordnersatz (LINQ)'
ms.date: 07/20/2015
ms.assetid: bfe85ed2-44dc-4ef1-aac7-241622b80a69
ms.openlocfilehash: 25e2c2894d9feccf42ee92bdddd17d8558779e6c
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266975"
---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-visual-basic"></a>Gewusst wie: Abfragen der Gesamtzahl der Bytes in einem Ordnersatz (LINQ) (Visual Basic)
Dieses Beispiel zeigt, wie die Gesamtanzahl der Bytes, die von allen Dateien in einem angegebenen Ordner und allen Unterordnern verwendet werden, abgerufen wird.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Linq.Enumerable.Sum%2A>-Methode fügt die Werte aller Elemente hinzu, die in der `select`-Klausel ausgewählt wurden. Sie können diese Abfrage leicht modifizieren, um die größte oder kleinste Datei in der angegebenen Verzeichnisstruktur abzurufen, indem Sie die <xref:System.Linq.Enumerable.Min%2A>- oder <xref:System.Linq.Enumerable.Max%2A>-Methode statt der <xref:System.Linq.Enumerable.Sum%2A>-Methode verwenden.  
  
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
  
 Wenn Sie nur die Anzahl der Bytes in einer angegebenen Verzeichnisstruktur ermitteln wollen, können Sie dies ohne LINQ-Abfrage effizienter tun, da diese zunächst die Listenauflistung als Datenquelle erstellt, was Mehraufwand verursacht. Die Nützlichkeit des LINQ-Ansatzes wird erhöht, wenn die Abfrage komplexer wird oder wenn Sie mehrere Abfragen für dieselbe Datenquelle ausführen.  
  
 Die Abfrage ruft eine separate Methode auf, um die Dateilänge zu erhalten. Dadurch wird die mögliche Ausnahme abgefangen, die ausgelöst wird, wenn die Datei auf einem anderen Thread gelöscht wurde, nachdem das <xref:System.IO.FileInfo>-Objekt im Aufruf von `GetFiles` erstellt wurde. Obwohl das <xref:System.IO.FileInfo>-Objekt bereits erstellt wurde, kann die Ausnahme auftreten, weil ein <xref:System.IO.FileInfo>-Objekt versucht, seine <xref:System.IO.FileInfo.Length%2A>-Eigenschaft mit der aktuellsten Länge beim ersten Zugriff auf die Eigenschaft zu aktualisieren. Indem dieser Vorgang in einen Try-Catch-Block außerhalb der Abfrage erfolgt, folgt der Code der Regel zum Vermeiden von Vorgängen in Abfragen, die Nebeneffekte verursachen können. Im Allgemeinen ist beim Abfangen von Ausnahmen große Sorgfalt geboten, um sicherzustellen, dass Anwendungen nicht in einem unbekannten Zustand verbleiben.  
  
## <a name="compile-the-code"></a>Kompilieren des Codes  
Erstellen Sie ein Visual Basic-Konsolenanwendungsprojekt mit einer `Imports` Anweisung für den System.Linq-Namespace.
  
## <a name="see-also"></a>Weitere Informationen

- [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- [LINQ and File Directories (Visual Basic) (LINQ und Dateiverzeichnisse (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
