---
title: 'Vorgehensweise: Abfragen der Gesamtzahl an Bytes in einem Ordnersatz (LINQ) (C#)'
ms.date: 07/20/2015
ms.assetid: a01bd1d4-133c-4ca2-aa4e-e93e81d6076c
ms.openlocfilehash: 04eed82041dc3c0818b0205f5198abe6e9eb228e
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65585679"
---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-c"></a><span data-ttu-id="e7559-102">Vorgehensweise: Abfragen der Gesamtzahl an Bytes in einem Ordnersatz (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="e7559-102">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (C#)</span></span>
<span data-ttu-id="e7559-103">Dieses Beispiel zeigt, wie die Gesamtanzahl der Bytes, die von allen Dateien in einem angegebenen Ordner und allen Unterordnern verwendet werden, abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e7559-103">This example shows how to retrieve the total number of bytes used by all the files in a specified folder and all its subfolders.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7559-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7559-104">Example</span></span>  
 <span data-ttu-id="e7559-105">Die <xref:System.Linq.Enumerable.Sum%2A>-Methode fügt die Werte aller Elemente hinzu, die in der `select`-Klausel ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="e7559-105">The <xref:System.Linq.Enumerable.Sum%2A> method adds the values of all the items selected in the `select` clause.</span></span> <span data-ttu-id="e7559-106">Sie können diese Abfrage leicht modifizieren, um die größte oder kleinste Datei in der angegebenen Verzeichnisstruktur abzurufen, indem Sie die <xref:System.Linq.Enumerable.Min%2A>- oder <xref:System.Linq.Enumerable.Max%2A>-Methode statt der <xref:System.Linq.Enumerable.Sum%2A>-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7559-106">You can easily modify this query to retrieve the biggest or smallest file in the specified directory tree by calling the <xref:System.Linq.Enumerable.Min%2A> or <xref:System.Linq.Enumerable.Max%2A> method instead of <xref:System.Linq.Enumerable.Sum%2A>.</span></span>  
  
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
  
 <span data-ttu-id="e7559-107">Wenn Sie nur die Anzahl der Bytes in einer angegebenen Verzeichnisstruktur ermitteln wollen, können Sie dies ohne LINQ-Abfrage effizienter tun, da diese zunächst die Listenauflistung als Datenquelle erstellt, was Mehraufwand verursacht.</span><span class="sxs-lookup"><span data-stu-id="e7559-107">If you only have to count the number of bytes in a specified directory tree, you can do this more efficiently without creating a LINQ query, which incurs the overhead of creating the list collection as a data source.</span></span> <span data-ttu-id="e7559-108">Die Nützlichkeit des LINQ-Ansatzes wird erhöht, wenn die Abfrage komplexer wird oder wenn Sie mehrere Abfragen für dieselbe Datenquelle ausführen.</span><span class="sxs-lookup"><span data-stu-id="e7559-108">The usefulness of the LINQ approach increases as the query becomes more complex, or when you have to run multiple queries against the same data source.</span></span>  
  
 <span data-ttu-id="e7559-109">Die Abfrage ruft eine separate Methode auf, um die Dateilänge zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e7559-109">The query calls out to a separate method to obtain the file length.</span></span> <span data-ttu-id="e7559-110">Dadurch wird die mögliche Ausnahme abgefangen, die ausgelöst wird, wenn die Datei auf einem anderen Thread gelöscht wurde, nachdem das <xref:System.IO.FileInfo>-Objekt im Aufruf von `GetFiles` erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e7559-110">It does this in order to consume the possible exception that will be raised if the file was deleted on another thread after the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="e7559-111">Obwohl das <xref:System.IO.FileInfo>-Objekt bereits erstellt wurde, kann die Ausnahme auftreten, weil ein <xref:System.IO.FileInfo>-Objekt versucht, seine <xref:System.IO.FileInfo.Length%2A>-Eigenschaft mit der aktuellsten Länge beim ersten Zugriff auf die Eigenschaft zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e7559-111">Even though the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property with the most current length the first time the property is accessed.</span></span> <span data-ttu-id="e7559-112">Indem dieser Vorgang in einen Try-Catch-Block außerhalb der Abfrage erfolgt, folgt der Code der Regel zum Vermeiden von Vorgängen in Abfragen, die Nebeneffekte verursachen können.</span><span class="sxs-lookup"><span data-stu-id="e7559-112">By putting this operation in a try-catch block outside the query, the code follows the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="e7559-113">Im Allgemeinen ist beim Abfangen von Ausnahmen große Sorgfalt geboten, um sicherzustellen, dass Anwendungen nicht in einem unbekannten Zustand verbleiben.</span><span class="sxs-lookup"><span data-stu-id="e7559-113">In general, great care must be taken when you consume exceptions to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e7559-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e7559-114">Compiling the Code</span></span>  
<span data-ttu-id="e7559-115">Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.</span><span class="sxs-lookup"><span data-stu-id="e7559-115">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e7559-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7559-116">See also</span></span>

- [<span data-ttu-id="e7559-117">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="e7559-117">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)
- [<span data-ttu-id="e7559-118">LINQ und Dateiverzeichnisse (C#)</span><span class="sxs-lookup"><span data-stu-id="e7559-118">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
