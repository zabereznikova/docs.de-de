---
title: 'Vorgehensweise: Abfragen der größten Datei oder der größten Dateien in einer Verzeichnisstruktur (LINQ) (C#)'
ms.date: 07/20/2015
ms.assetid: 20c8a917-0552-4514-b489-0b8b6a4c3b4c
ms.openlocfilehash: dee501dc8d0cabd718307b45c99ca049ae4250aa
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344562"
---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-c"></a><span data-ttu-id="900c8-102">Vorgehensweise: Abfragen der größten Datei oder der größten Dateien in einer Verzeichnisstruktur (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="900c8-102">How to query for the largest file or files in a directory tree (LINQ) (C#)</span></span>
<span data-ttu-id="900c8-103">Dieses Beispiel zeigt fünf Abfragen mit Bezug auf die Dateigröße in Bytes:</span><span class="sxs-lookup"><span data-stu-id="900c8-103">This example shows five queries related to file size in bytes:</span></span>  
  
- <span data-ttu-id="900c8-104">So rufen Sie die Größe in Bytes der größten Datei ab</span><span class="sxs-lookup"><span data-stu-id="900c8-104">How to retrieve the size in bytes of the largest file.</span></span>  
  
- <span data-ttu-id="900c8-105">So rufen Sie die Größe in Bytes der kleinsten Datei ab</span><span class="sxs-lookup"><span data-stu-id="900c8-105">How to retrieve the size in bytes of the smallest file.</span></span>  
  
- <span data-ttu-id="900c8-106">So rufen Sie das <xref:System.IO.FileInfo>-Objekt der größten oder kleinsten Datei aus einem oder mehreren Ordnern unter einem bestimmten Stammordner ab</span><span class="sxs-lookup"><span data-stu-id="900c8-106">How to retrieve the <xref:System.IO.FileInfo> object largest or smallest file from one or more folders under a specified root folder.</span></span>  
  
- <span data-ttu-id="900c8-107">So rufen Sie eine Sequenz ab, wie z.B. die 10 größten Dateien</span><span class="sxs-lookup"><span data-stu-id="900c8-107">How to retrieve a sequence such as the 10 largest files.</span></span>  
  
- <span data-ttu-id="900c8-108">So ordnen Sie Dateien in Gruppen auf Grundlage ihrer Dateigröße in Bytes und ignorieren dabei die Dateien, die kleiner als eine angegebene Größe sind</span><span class="sxs-lookup"><span data-stu-id="900c8-108">How to order files into groups based on their file size in bytes, ignoring files that are less than a specified size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="900c8-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="900c8-109">Example</span></span>  
 <span data-ttu-id="900c8-110">Das folgende Beispiel enthält fünf separate Abfragen, die zeigen, wie Sie Dateien je nach ihrer Dateigröße in Bytes abfragen und gruppieren.</span><span class="sxs-lookup"><span data-stu-id="900c8-110">The following example contains five separate queries that show how to query and group files, depending on their file size in bytes.</span></span> <span data-ttu-id="900c8-111">Sie können diese Beispiele ganz einfach verändern, um die Abfrage auf eine andere Eigenschaft des <xref:System.IO.FileInfo>-Objekts anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="900c8-111">You can easily modify these examples to base the query on some other property of the <xref:System.IO.FileInfo> object.</span></span>  
  
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
  
 <span data-ttu-id="900c8-112">Um mindestens ein abgeschlossenes <xref:System.IO.FileInfo>-Objekt zurückzugeben, muss die Abfrage jedes in der Datenquelle untersuchen und die Objekte dann nach Wert ihrer Length-Eigenschaft sortieren.</span><span class="sxs-lookup"><span data-stu-id="900c8-112">To return one or more complete <xref:System.IO.FileInfo> objects, the query first must examine each one in the data source, and then sort them by the value of their Length property.</span></span> <span data-ttu-id="900c8-113">Anschließend kann das einzelne Objekt oder die Sequenz mit den größten Längen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="900c8-113">Then it can return the single one or the sequence with the greatest lengths.</span></span> <span data-ttu-id="900c8-114">Verwenden Sie <xref:System.Linq.Enumerable.First%2A>, um das erste Element in einer Liste zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="900c8-114">Use <xref:System.Linq.Enumerable.First%2A> to return the first element in a list.</span></span> <span data-ttu-id="900c8-115">Verwenden Sie <xref:System.Linq.Enumerable.Take%2A>, um die ersten n Elemente zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="900c8-115">Use <xref:System.Linq.Enumerable.Take%2A> to return the first n number of elements.</span></span> <span data-ttu-id="900c8-116">Geben Sie eine absteigende Sortierreihenfolge an, um die kleinsten Elemente zu Beginn der Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="900c8-116">Specify a descending sort order to put the smallest elements at the start of the list.</span></span>  
  
 <span data-ttu-id="900c8-117">Die Abfrage ruft eine separate Methode zum Abrufen der Dateigröße in Bytes auf, um die mögliche Ausnahme zu verwenden, die in dem Fall ausgelöst wird, wenn eine Datei auf einem anderen Thread im Zeitraum, in dem das <xref:System.IO.FileInfo>-Objekt im Aufruf an `GetFiles` erstellt wurde, gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="900c8-117">The query calls out to a separate method to obtain the file size in bytes in order to consume the possible exception that will be raised in the case where a file was deleted on another thread in the time period since the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="900c8-118">Obwohl das <xref:System.IO.FileInfo>-Objekt bereits erstellt wurde, kann die Ausnahme auftreten, weil ein <xref:System.IO.FileInfo>-Objekt versucht, seine <xref:System.IO.FileInfo.Length%2A>-Eigenschaft mithilfe der aktuellsten Größe in Bytes beim ersten Zugriff auf die Eigenschaft zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="900c8-118">Even through the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property by using the most current size in bytes the first time the property is accessed.</span></span> <span data-ttu-id="900c8-119">Indem dieser Vorgang in einen Try-Catch-Block außerhalb der Abfrage erfolgt, folgt der Code der Regel zum Vermeiden von Vorgängen in Abfragen, die Nebeneffekte verursachen können.</span><span class="sxs-lookup"><span data-stu-id="900c8-119">By putting this operation in a try-catch block outside the query, we follow the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="900c8-120">Im Allgemeinen ist beim Abfangen von Ausnahmen große Sorgfalt geboten, damit einen Anwendung nicht in einem unbekannten Zustand gelassen wird.</span><span class="sxs-lookup"><span data-stu-id="900c8-120">In general, great care must be taken when consuming exceptions, to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="900c8-121">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="900c8-121">Compiling the Code</span></span>  
<span data-ttu-id="900c8-122">Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.</span><span class="sxs-lookup"><span data-stu-id="900c8-122">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="900c8-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="900c8-123">See also</span></span>

- [<span data-ttu-id="900c8-124">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="900c8-124">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
- [<span data-ttu-id="900c8-125">LINQ und Dateiverzeichnisse (C#)</span><span class="sxs-lookup"><span data-stu-id="900c8-125">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
