---
title: 'Vorgehensweise: Abfragen der größten Datei oder der größten Dateien in einer Verzeichnisstruktur (LINQ) (C#)'
description: Dieses C#-Beispiel zeigt fünf LINQ-Abfragen mit Bezug auf die Dateigröße in Byte. Sie können diese Abfragen so bearbeiten, dass andere Eigenschaften des FileInfo-Objekts abgefragt werden.
ms.date: 07/20/2015
ms.assetid: 20c8a917-0552-4514-b489-0b8b6a4c3b4c
ms.openlocfilehash: c06c6017d6fd1efd6412729c5df63a2b819908a6
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104373"
---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-c"></a>Vorgehensweise: Abfragen der größten Datei oder der größten Dateien in einer Verzeichnisstruktur (LINQ) (C#)
Dieses Beispiel zeigt fünf Abfragen mit Bezug auf die Dateigröße in Bytes:  
  
- So rufen Sie die Größe in Bytes der größten Datei ab  
  
- So rufen Sie die Größe in Bytes der kleinsten Datei ab  
  
- So rufen Sie das <xref:System.IO.FileInfo>-Objekt der größten oder kleinsten Datei aus einem oder mehreren Ordnern unter einem bestimmten Stammordner ab  
  
- So rufen Sie eine Sequenz ab, wie z.B. die 10 größten Dateien  
  
- So ordnen Sie Dateien in Gruppen auf Grundlage ihrer Dateigröße in Bytes und ignorieren dabei die Dateien, die kleiner als eine angegebene Größe sind  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel enthält fünf separate Abfragen, die zeigen, wie Sie Dateien je nach ihrer Dateigröße in Bytes abfragen und gruppieren. Sie können diese Beispiele ganz einfach verändern, um die Abfrage auf eine andere Eigenschaft des <xref:System.IO.FileInfo>-Objekts anzuwenden.  
  
```csharp  
class QueryBySize  
{  
    static void Main(string[] args)  
    {  
        QueryFilesBySize();  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    private static void QueryFilesBySize()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        //Return the size of the largest file  
        long maxSize =  
            (from file in fileList  
             let len = GetFileLength(file)  
             select len)  
             .Max();  
  
        Console.WriteLine("The length of the largest file under {0} is {1}",  
            startFolder, maxSize);  
  
        // Return the FileInfo object for the largest file  
        // by sorting and selecting from beginning of list  
        System.IO.FileInfo longestFile =  
            (from file in fileList  
             let len = GetFileLength(file)  
             where len > 0  
             orderby len descending  
             select file)  
            .First();  
  
        Console.WriteLine("The largest file under {0} is {1} with a length of {2} bytes",  
                            startFolder, longestFile.FullName, longestFile.Length);  
  
        //Return the FileInfo of the smallest file  
        System.IO.FileInfo smallestFile =  
            (from file in fileList  
             let len = GetFileLength(file)  
             where len > 0  
             orderby len ascending  
             select file).First();  
  
        Console.WriteLine("The smallest file under {0} is {1} with a length of {2} bytes",  
                            startFolder, smallestFile.FullName, smallestFile.Length);  
  
        //Return the FileInfos for the 10 largest files  
        // queryTenLargest is an IEnumerable<System.IO.FileInfo>  
        var queryTenLargest =  
            (from file in fileList  
             let len = GetFileLength(file)  
             orderby len descending  
             select file).Take(10);  
  
        Console.WriteLine("The 10 largest files under {0} are:", startFolder);  
  
        foreach (var v in queryTenLargest)  
        {  
            Console.WriteLine("{0}: {1} bytes", v.FullName, v.Length);  
        }  
  
        // Group the files according to their size, leaving out  
        // files that are less than 200000 bytes.
        var querySizeGroups =  
            from file in fileList  
            let len = GetFileLength(file)  
            where len > 0  
            group file by (len / 100000) into fileGroup  
            where fileGroup.Key >= 2  
            orderby fileGroup.Key descending  
            select fileGroup;  
  
        foreach (var filegroup in querySizeGroups)  
        {  
            Console.WriteLine(filegroup.Key.ToString() + "00000");  
            foreach (var item in filegroup)  
            {  
                Console.WriteLine("\t{0}: {1}", item.Name, item.Length);  
            }  
        }  
    }  
  
    // This method is used to swallow the possible exception  
    // that can be raised when accessing the FileInfo.Length property.  
    // In this particular case, it is safe to swallow the exception.  
    static long GetFileLength(System.IO.FileInfo fi)  
    {  
        long retval;  
        try  
        {  
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
  
 Um mindestens ein abgeschlossenes <xref:System.IO.FileInfo>-Objekt zurückzugeben, muss die Abfrage jedes in der Datenquelle untersuchen und die Objekte dann nach Wert ihrer Length-Eigenschaft sortieren. Anschließend kann das einzelne Objekt oder die Sequenz mit den größten Längen zurückgegeben werden. Verwenden Sie <xref:System.Linq.Enumerable.First%2A>, um das erste Element in einer Liste zurückzugeben. Verwenden Sie <xref:System.Linq.Enumerable.Take%2A>, um die ersten n Elemente zurückzugeben. Geben Sie eine absteigende Sortierreihenfolge an, um die kleinsten Elemente zu Beginn der Liste anzuzeigen.  
  
 Die Abfrage ruft eine separate Methode zum Abrufen der Dateigröße in Bytes auf, um die mögliche Ausnahme zu verwenden, die in dem Fall ausgelöst wird, wenn eine Datei auf einem anderen Thread im Zeitraum, in dem das <xref:System.IO.FileInfo>-Objekt im Aufruf an `GetFiles` erstellt wurde, gelöscht wurde. Obwohl das <xref:System.IO.FileInfo>-Objekt bereits erstellt wurde, kann die Ausnahme auftreten, weil ein <xref:System.IO.FileInfo>-Objekt versucht, seine <xref:System.IO.FileInfo.Length%2A>-Eigenschaft mithilfe der aktuellsten Größe in Bytes beim ersten Zugriff auf die Eigenschaft zu aktualisieren. Indem dieser Vorgang in einen Try-Catch-Block außerhalb der Abfrage erfolgt, folgt der Code der Regel zum Vermeiden von Vorgängen in Abfragen, die Nebeneffekte verursachen können. Im Allgemeinen ist beim Abfangen von Ausnahmen große Sorgfalt geboten, damit einen Anwendung nicht in einem unbekannten Zustand gelassen wird.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.

## <a name="see-also"></a>Siehe auch

- [LINQ to Objects (C#)](./linq-to-objects.md)
- [LINQ und Dateiverzeichnisse (C#)](./linq-and-file-directories.md)
