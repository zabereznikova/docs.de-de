---
title: 'Vorgehensweise: Abfragen von Dateiduplikaten in einer Verzeichnisstruktur (LINQ) (C#)'
description: In diesem Artikel erfahren Sie, wie Sie LINQ in C# verwenden, um doppelte Dateinamen in unterschiedlichen Verzeichnissen abzufragen, und wie Sie Dateien abfragen, deren Größen und LastWriteTime-Eigenschaften ebenfalls übereinstimmen.
ms.date: 07/20/2015
ms.assetid: 1ff5562b-0d30-46d1-b426-a04e8f78c840
ms.openlocfilehash: 87874fdb5bcfd66ffecf3379e315dfa019e89898
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176291"
---
# <a name="how-to-query-for-duplicate-files-in-a-directory-tree-linq-c"></a><span data-ttu-id="829cb-103">Vorgehensweise: Abfragen von Dateiduplikaten in einer Verzeichnisstruktur (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="829cb-103">How to query for duplicate files in a directory tree (LINQ) (C#)</span></span>

<span data-ttu-id="829cb-104">Manchmal können sich Dateien mit demselben Namen in mehr als einem Ordner befinden.</span><span class="sxs-lookup"><span data-stu-id="829cb-104">Sometimes files that have the same name may be located in more than one folder.</span></span> <span data-ttu-id="829cb-105">Beispielsweise enthalten mehrere Ordner unter dem Installationsordner von Visual Studio eine Datei „readme.htm“.</span><span class="sxs-lookup"><span data-stu-id="829cb-105">For example, under the Visual Studio installation folder, several folders have a readme.htm file.</span></span> <span data-ttu-id="829cb-106">Dieses Beispiel zeigt, wie solche mehrfach vorkommenden Dateinamen in einem angegebenen Stammordner abgefragt werden können.</span><span class="sxs-lookup"><span data-stu-id="829cb-106">This example shows how to query for such duplicate file names under a specified root folder.</span></span> <span data-ttu-id="829cb-107">Das zweite Beispiel zeigt, wie Dateien abgefragt werden können, deren Größe und LastWrite-Zeiten ebenfalls übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="829cb-107">The second example shows how to query for files whose size and LastWrite times also match.</span></span>  
  
## <a name="example"></a><span data-ttu-id="829cb-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="829cb-108">Example</span></span>  
  
```csharp  
class QueryDuplicateFileNames  
{  
    static void Main(string[] args)  
    {  
        // Uncomment QueryDuplicates2 to run that query.  
        QueryDuplicates();  
        // QueryDuplicates2();  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit.");  
        Console.ReadKey();  
    }  
  
    static void QueryDuplicates()  
    {  
        // Change the root drive or folder if necessary  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        // used in WriteLine to keep the lines shorter  
        int charsToSkip = startFolder.Length;  
  
        // var can be used for convenience with groups.  
        var queryDupNames =  
            from file in fileList  
            group file.FullName.Substring(charsToSkip) by file.Name into fileGroup  
            where fileGroup.Count() > 1  
            select fileGroup;  
  
        // Pass the query to a method that will  
        // output one page at a time.  
        PageOutput<string, string>(queryDupNames);  
    }  
  
    // A Group key that can be passed to a separate method.  
    // Override Equals and GetHashCode to define equality for the key.  
    // Override ToString to provide a friendly name for Key.ToString()  
    class PortableKey  
    {  
        public string Name { get; set; }  
        public DateTime LastWriteTime { get; set; }  
        public long Length { get; set; }  
  
        public override bool Equals(object obj)  
        {  
            PortableKey other = (PortableKey)obj;  
            return other.LastWriteTime == this.LastWriteTime &&  
                   other.Length == this.Length &&  
                   other.Name == this.Name;  
        }  
  
        public override int GetHashCode()  
        {  
            string str = $"{this.LastWriteTime}{this.Length}{this.Name}";
            return str.GetHashCode();  
        }  
        public override string ToString()  
        {  
            return $"{this.Name} {this.Length} {this.LastWriteTime}";
        }  
    }  
    static void QueryDuplicates2()  
    {  
        // Change the root drive or folder if necessary.  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\Common7";  
  
        // Make the lines shorter for the console display  
        int charsToSkip = startFolder.Length;  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        // Note the use of a compound key. Files that match  
        // all three properties belong to the same group.  
        // A named type is used to enable the query to be  
        // passed to another method. Anonymous types can also be used  
        // for composite keys but cannot be passed across method boundaries  
        //
        var queryDupFiles =  
            from file in fileList  
            group file.FullName.Substring(charsToSkip) by  
                new PortableKey { Name = file.Name, LastWriteTime = file.LastWriteTime, Length = file.Length } into fileGroup  
            where fileGroup.Count() > 1  
            select fileGroup;  
  
        var list = queryDupFiles.ToList();  
  
        int i = queryDupFiles.Count();  
  
        PageOutput<PortableKey, string>(queryDupFiles);  
    }  
  
    // A generic method to page the output of the QueryDuplications methods  
    // Here the type of the group must be specified explicitly. "var" cannot  
    // be used in method signatures. This method does not display more than one  
    // group per page.  
    private static void PageOutput<K, V>(IEnumerable<System.Linq.IGrouping<K, V>> groupByExtList)  
    {  
        // Flag to break out of paging loop.  
        bool goAgain = true;  
  
        // "3" = 1 line for extension + 1 for "Press any key" + 1 for input cursor.  
        int numLines = Console.WindowHeight - 3;  
  
        // Iterate through the outer collection of groups.  
        foreach (var filegroup in groupByExtList)  
        {  
            // Start a new extension at the top of a page.  
            int currentLine = 0;  
  
            // Output only as many lines of the current group as will fit in the window.  
            do  
            {  
                Console.Clear();  
                Console.WriteLine("Filename = {0}", filegroup.Key.ToString() == String.Empty ? "[none]" : filegroup.Key.ToString());  
  
                // Get 'numLines' number of items starting at number 'currentLine'.  
                var resultPage = filegroup.Skip(currentLine).Take(numLines);  
  
                //Execute the resultPage query  
                foreach (var fileName in resultPage)  
                {  
                    Console.WriteLine("\t{0}", fileName);  
                }  
  
                // Increment the line counter.  
                currentLine += numLines;  
  
                // Give the user a chance to escape.  
                Console.WriteLine("Press any key to continue or the 'End' key to break...");  
                ConsoleKey key = Console.ReadKey().Key;  
                if (key == ConsoleKey.End)  
                {  
                    goAgain = false;  
                    break;  
                }  
            } while (currentLine < filegroup.Count());  
  
            if (goAgain == false)  
                break;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="829cb-109">Die erste Abfrage verwendet einen einfachen Schlüssel, um eine Übereinstimmung zu ermitteln. Somit werden Dateien gefunden, die den gleichen Namen haben, deren Inhalt aber unterschiedlich sein kann.</span><span class="sxs-lookup"><span data-stu-id="829cb-109">The first query uses a simple key to determine a match; this finds files that have the same name but whose contents might be different.</span></span> <span data-ttu-id="829cb-110">Die zweite Abfrage verwendet einen zusammengesetzten Schlüssel für den Abgleich von drei Eigenschaften des <xref:System.IO.FileInfo>-Objekts.</span><span class="sxs-lookup"><span data-stu-id="829cb-110">The second query uses a compound key to match against three properties of the <xref:System.IO.FileInfo> object.</span></span> <span data-ttu-id="829cb-111">Diese Abfrage hat eine größere Wahrscheinlichkeit, Dateien zu finden, die denselben Namen und ähnliche oder identische Inhalte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="829cb-111">This query is much more likely to find files that have the same name and similar or identical content.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="829cb-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="829cb-112">Compiling the Code</span></span>  

 <span data-ttu-id="829cb-113">Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.</span><span class="sxs-lookup"><span data-stu-id="829cb-113">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="829cb-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="829cb-114">See also</span></span>

- [<span data-ttu-id="829cb-115">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="829cb-115">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
- [<span data-ttu-id="829cb-116">LINQ und Dateiverzeichnisse (C#)</span><span class="sxs-lookup"><span data-stu-id="829cb-116">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
