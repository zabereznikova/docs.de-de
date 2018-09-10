---
title: 'Vorgehensweise: Abfragen der Gesamtzahl von Bytes in einem Ordnersatz (LINQ) (C#)'
ms.date: 07/20/2015
ms.assetid: a01bd1d4-133c-4ca2-aa4e-e93e81d6076c
ms.openlocfilehash: 7a11e30a41ce171d516d3ea00a0e8664efe33520
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44185927"
---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-c"></a>Vorgehensweise: Abfragen der Gesamtzahl von Bytes in einem Ordnersatz (LINQ) (C#)
Dieses Beispiel zeigt, wie die Gesamtanzahl der Bytes, die von allen Dateien in einem angegebenen Ordner und allen Unterordnern verwendet werden, abgerufen wird.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Linq.Enumerable.Sum%2A>-Methode fügt die Werte aller Elemente hinzu, die in der `select`-Klausel ausgewählt wurden. Sie können diese Abfrage leicht modifizieren, um die größte oder kleinste Datei in der angegebenen Verzeichnisstruktur abzurufen, indem Sie die <xref:System.Linq.Enumerable.Min%2A>- oder <xref:System.Linq.Enumerable.Max%2A>-Methode statt der <xref:System.Linq.Enumerable.Sum%2A>-Methode verwenden.  
  
```csharp  
class QuerySize  
{  
    public static void Main()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\VC#";  
  
        // Take a snapshot of the file system.  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<string> fileList = System.IO.Directory.GetFiles(startFolder, "*.*", System.IO.SearchOption.AllDirectories);  
  
        var fileQuery = from file in fileList  
                        select GetFileLength(file);  
  
        // Cache the results to avoid multiple trips to the file system.  
        long[] fileLengths = fileQuery.ToArray();  
  
        // Return the size of the largest file  
        long largestFile = fileLengths.Max();  
  
        // Return the total number of bytes in all the files under the specified folder.  
        long totalBytes = fileLengths.Sum();  
  
        Console.WriteLine("There are {0} bytes in {1} files under {2}",  
            totalBytes, fileList.Count(), startFolder);  
        Console.WriteLine("The largest files is {0} bytes.", largestFile);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit.");  
        Console.ReadKey();  
    }  
  
    // This method is used to swallow the possible exception  
    // that can be raised when accessing the System.IO.FileInfo.Length property.  
    static long GetFileLength(string filename)  
    {  
        long retval;  
        try  
        {  
            System.IO.FileInfo fi = new System.IO.FileInfo(filename);  
            retval = fi.Length;  
        }  
        catch (System.IO.FileNotFoundException)  
        {  
            // If a file is no longer present,  
            // just add zero bytes to the total.  
            retval = 0;  
        }  
        return retval;  
    }  
}  
```  
  
 Wenn Sie nur die Anzahl der Bytes in einer angegebenen Verzeichnisstruktur ermitteln wollen, können Sie dies ohne LINQ-Abfrage effizienter tun, da diese zunächst die Listenauflistung als Datenquelle erstellt, was Mehraufwand verursacht. Die Nützlichkeit des LINQ-Ansatzes wird erhöht, wenn die Abfrage komplexer wird oder wenn Sie mehrere Abfragen für dieselbe Datenquelle ausführen.  
  
 Die Abfrage ruft eine separate Methode auf, um die Dateilänge zu erhalten. Dadurch wird die mögliche Ausnahme abgefangen, die ausgelöst wird, wenn die Datei auf einem anderen Thread gelöscht wurde, nachdem das <xref:System.IO.FileInfo>-Objekt im Aufruf von `GetFiles` erstellt wurde. Obwohl das <xref:System.IO.FileInfo>-Objekt bereits erstellt wurde, kann die Ausnahme auftreten, weil ein <xref:System.IO.FileInfo>-Objekt versucht, seine <xref:System.IO.FileInfo.Length%2A>-Eigenschaft mit der aktuellsten Länge beim ersten Zugriff auf die Eigenschaft zu aktualisieren. Indem dieser Vorgang in einen Try-Catch-Block außerhalb der Abfrage erfolgt, folgt der Code der Regel zum Vermeiden von Vorgängen in Abfragen, die Nebeneffekte verursachen können. Im Allgemeinen ist beim Abfangen von Ausnahmen große Sorgfalt geboten, um sicherzustellen, dass Anwendungen nicht in einem unbekannten Zustand verbleiben.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen Sie ein Projekt, das die .NET Framework-Version 3.5 oder höher verwendet, mit einem Verweis auf System.Core.dll und `using`-Direktiven für System.Linq- und System.IO-Namespaces.  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)  
- [LINQ und Dateiverzeichnisse (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
