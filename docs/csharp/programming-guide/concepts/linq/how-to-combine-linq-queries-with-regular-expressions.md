---
title: 'Vorgehensweise: Kombinieren von LINQ-Abfragen mit regulären Ausdrücken (C#)'
ms.date: 07/20/2015
ms.assetid: 6b003b65-20a4-4ca2-929e-2ee3f215aecc
ms.openlocfilehash: 97551f7d9d8cf13f05449c2f825ed4d29eb3d86e
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141408"
---
# <a name="how-to-combine-linq-queries-with-regular-expressions-c"></a><span data-ttu-id="89201-102">Vorgehensweise: Kombinieren von LINQ-Abfragen mit regulären Ausdrücken (C#)</span><span class="sxs-lookup"><span data-stu-id="89201-102">How to combine LINQ queries with regular expressions (C#)</span></span>
<span data-ttu-id="89201-103">In diesem Beispiel wird gezeigt, wie Sie die <xref:System.Text.RegularExpressions.Regex>-Klasse verwenden, um einen regulären Ausdruck für komplexere Übereinstimmungen in Textzeichenfolgen erstellen.</span><span class="sxs-lookup"><span data-stu-id="89201-103">This example shows how to use the <xref:System.Text.RegularExpressions.Regex> class to create a regular expression for more complex matching in text strings.</span></span> <span data-ttu-id="89201-104">Die LINQ-Abfrage erleichtert das Filtern nach genau den Dateien, die Sie mithilfe des regulären Ausdrucks suchen möchten, sowie das Formen der Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="89201-104">The LINQ query makes it easy to filter on exactly the files that you want to search with the regular expression, and to shape the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89201-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89201-105">Example</span></span>  
  
```csharp  
class QueryWithRegEx  
{  
    public static void Main()  
    {  
        // Modify this path as necessary so that it accesses your version of Visual Studio.  
        string startFolder = @"C:\Program Files (x86)\Microsoft Visual Studio 14.0\";  
        // One of the following paths may be more appropriate on your computer.  
        //string startFolder = @"C:\Program Files (x86)\Microsoft Visual Studio\2017\";  
  
        // Take a snapshot of the file system.  
        IEnumerable<System.IO.FileInfo> fileList = GetFiles(startFolder);  
  
        // Create the regular expression to find all things "Visual".  
        System.Text.RegularExpressions.Regex searchTerm =  
            new System.Text.RegularExpressions.Regex(@"Visual (Basic|C#|C\+\+|Studio)");  
  
        // Search the contents of each .htm file.  
        // Remove the where clause to find even more matchedValues!  
        // This query produces a list of files where a match  
        // was found, and a list of the matchedValues in that file.  
        // Note: Explicit typing of "Match" in select clause.  
        // This is required because MatchCollection is not a   
        // generic IEnumerable collection.  
        var queryMatchingFiles =  
            from file in fileList  
            where file.Extension == ".htm"  
            let fileText = System.IO.File.ReadAllText(file.FullName)  
            let matches = searchTerm.Matches(fileText)  
            where matches.Count > 0  
            select new  
            {  
                name = file.FullName,  
                matchedValues = from System.Text.RegularExpressions.Match match in matches  
                                select match.Value  
            };  
  
        // Execute the query.  
        Console.WriteLine("The term \"{0}\" was found in:", searchTerm.ToString());  
  
        foreach (var v in queryMatchingFiles)  
        {  
            // Trim the path a bit, then write   
            // the file name in which a match was found.  
            string s = v.name.Substring(startFolder.Length - 1);  
            Console.WriteLine(s);  
  
            // For this file, write out all the matching strings  
            foreach (var v2 in v.matchedValues)  
            {  
                Console.WriteLine("  " + v2);  
            }  
        }  
  
        // Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    // This method assumes that the application has discovery   
    // permissions for all folders under the specified path.  
    static IEnumerable<System.IO.FileInfo> GetFiles(string path)  
    {  
        if (!System.IO.Directory.Exists(path))  
            throw new System.IO.DirectoryNotFoundException();  
  
        string[] fileNames = null;  
        List<System.IO.FileInfo> files = new List<System.IO.FileInfo>();  
  
        fileNames = System.IO.Directory.GetFiles(path, "*.*", System.IO.SearchOption.AllDirectories);  
        foreach (string name in fileNames)  
        {  
            files.Add(new System.IO.FileInfo(name));  
        }  
        return files;  
    }  
}  
```  
  
 <span data-ttu-id="89201-106">Beachten Sie, dass Sie auch das <xref:System.Text.RegularExpressions.MatchCollection>-Objekt abfragen können, das von einer `RegEx`-Suche zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="89201-106">Note that you can also query the <xref:System.Text.RegularExpressions.MatchCollection> object that is returned by a `RegEx` search.</span></span> <span data-ttu-id="89201-107">In diesem Beispiel wird nur der Wert jeder Übereinstimmung in den Ergebnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="89201-107">In this example only the value of each match is produced in the results.</span></span> <span data-ttu-id="89201-108">Allerdings ist es auch möglich, LINQ zu verwenden, um alle Arten von Filtern, Sortieren und Gruppieren für diese Auflistung ausführen.</span><span class="sxs-lookup"><span data-stu-id="89201-108">However, it is also possible to use LINQ to perform all kinds of filtering, sorting, and grouping on that collection.</span></span> <span data-ttu-id="89201-109">Da <xref:System.Text.RegularExpressions.MatchCollection> eine nicht generische <xref:System.Collections.IEnumerable>-Auflistung ist, müssen Sie den Typ der Bereichsvariable in der Abfrage explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="89201-109">Because <xref:System.Text.RegularExpressions.MatchCollection> is a non-generic <xref:System.Collections.IEnumerable> collection, you have to explicitly state the type of the range variable in the query.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="89201-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="89201-110">Compiling the Code</span></span>  
 <span data-ttu-id="89201-111">Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.</span><span class="sxs-lookup"><span data-stu-id="89201-111">Create a C# console application project with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89201-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89201-112">See also</span></span>

- [<span data-ttu-id="89201-113">LINQ und Zeichenfolgen (C#)</span><span class="sxs-lookup"><span data-stu-id="89201-113">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="89201-114">LINQ und Dateiverzeichnisse (C#)</span><span class="sxs-lookup"><span data-stu-id="89201-114">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
