---
title: 'Vorgehensweise: Gruppieren von Dateien nach Erweiterung (LINQ) (C#)'
description: In diesem Artikel erfahren Sie, wie Sie LINQ verwenden, um erweiterte Gruppierungs- und Sortierungsvorgänge für Listen mit Dateien oder Ordnern in C# durchzuführen. In diesem Beispiel wird zeigt, wie Sie Ausgaben in der Konsole in Seiten einteilen können.
ms.date: 07/20/2015
ms.assetid: 21a98320-a5a1-4981-82d8-6a637e7d9018
ms.openlocfilehash: c17328980c20dd6ec32e8d0ce176081122443344
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91159045"
---
# <a name="how-to-group-files-by-extension-linq-c"></a><span data-ttu-id="50223-104">Vorgehensweise: Gruppieren von Dateien nach Erweiterung (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="50223-104">How to group files by extension (LINQ) (C#)</span></span>

<span data-ttu-id="50223-105">In dieses Beispiel wird veranschaulicht, wie Sie mithilfe von LINQ erweiterte Gruppierungs- und Sortiervorgänge mit Datei- oder Ordnerlisten ausführen können.</span><span class="sxs-lookup"><span data-stu-id="50223-105">This example shows how LINQ can be used to perform advanced grouping and sorting operations on lists of files or folders.</span></span> <span data-ttu-id="50223-106">Es zeigt auch, wie der Bildlauf für die Ausgabe im Konsolenfenster mithilfe der Methoden <xref:System.Linq.Enumerable.Skip%2A> und <xref:System.Linq.Enumerable.Take%2A> durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="50223-106">It also shows how to page output in the console window by using the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50223-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="50223-107">Example</span></span>  

 <span data-ttu-id="50223-108">Die folgende Abfrage zeigt, wie Sie den Inhalt einer angegebenen Verzeichnisstruktur nach der Dateierweiterung gruppieren.</span><span class="sxs-lookup"><span data-stu-id="50223-108">The following query shows how to group the contents of a specified directory tree by the file name extension.</span></span>  
  
```csharp  
class GroupByExtension  
{  
    // This query will sort all the files under the specified folder  
    //  and subfolder into groups keyed by the file extension.  
    private static void Main()  
    {  
        // Take a snapshot of the file system.  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\Common7";  
  
        // Used in WriteLine to trim output lines.  
        int trimLength = startFolder.Length;  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        // Create the query.  
        var queryGroupByExt =  
            from file in fileList  
            group file by file.Extension.ToLower() into fileGroup  
            orderby fileGroup.Key  
            select fileGroup;  
  
        // Display one group at a time. If the number of
        // entries is greater than the number of lines  
        // in the console window, then page the output.  
        PageOutput(trimLength, queryGroupByExt);  
    }  
  
    // This method specifically handles group queries of FileInfo objects with string keys.  
    // It can be modified to work for any long listings of data. Note that explicit typing  
    // must be used in method signatures. The groupbyExtList parameter is a query that produces  
    // groups of FileInfo objects with string keys.  
    private static void PageOutput(int rootLength,  
                                    IEnumerable<System.Linq.IGrouping<string, System.IO.FileInfo>> groupByExtList)  
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
                Console.WriteLine(filegroup.Key == String.Empty ? "[none]" : filegroup.Key);  
  
                // Get 'numLines' number of items starting at number 'currentLine'.  
                var resultPage = filegroup.Skip(currentLine).Take(numLines);  
  
                //Execute the resultPage query  
                foreach (var f in resultPage)  
                {  
                    Console.WriteLine("\t{0}", f.FullName.Substring(rootLength));  
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
  
 <span data-ttu-id="50223-109">Die Ausgabe dieses Programms kann je nach den Details des lokalen Dateisystems und der Einstellung für `startFolder` lang sein.</span><span class="sxs-lookup"><span data-stu-id="50223-109">The output from this program can be long, depending on the details of the local file system and what the `startFolder` is set to.</span></span> <span data-ttu-id="50223-110">Um alle Ergebnisse anzuzeigen, wird in diesem Beispiel gezeigt, wie Sie Ergebnisse seitenweise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="50223-110">To enable viewing of all results, this example shows how to page through results.</span></span> <span data-ttu-id="50223-111">Die gleichen Techniken können auf Windows- und Webanwendungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="50223-111">The same techniques can be applied to Windows and Web applications.</span></span> <span data-ttu-id="50223-112">Beachten Sie, dass eine geschachtelte `foreach`-Schleife erforderlich ist, da der Code die Elemente in einer Gruppe seitenweise anzeigt.</span><span class="sxs-lookup"><span data-stu-id="50223-112">Notice that because the code pages the items in a group, a nested `foreach` loop is required.</span></span> <span data-ttu-id="50223-113">Es ist auch sinnvoll, die aktuelle Position in der Liste berechnen zu können und es dem Benutzer zu ermöglichen, das seitenweise Anzeigen anzuhalten und das Programm zu beenden.</span><span class="sxs-lookup"><span data-stu-id="50223-113">There is also some additional logic to compute the current position in the list, and to enable the user to stop paging and exit the program.</span></span> <span data-ttu-id="50223-114">In diesem speziellen Fall wird die Abfrage zum seitenweise Anzeigen gegen die zwischengespeicherten Ergebnisse aus der ursprünglichen Abfrage ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="50223-114">In this particular case, the paging query is run against the cached results from the original query.</span></span> <span data-ttu-id="50223-115">In anderen Kontexten wie LINQ to SQL ist ein solches Zwischenspeichern nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="50223-115">In other contexts, such as LINQ to SQL, such caching is not required.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="50223-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="50223-116">Compiling the Code</span></span>  

 <span data-ttu-id="50223-117">Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.</span><span class="sxs-lookup"><span data-stu-id="50223-117">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50223-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50223-118">See also</span></span>

- [<span data-ttu-id="50223-119">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="50223-119">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
- [<span data-ttu-id="50223-120">LINQ und Dateiverzeichnisse (C#)</span><span class="sxs-lookup"><span data-stu-id="50223-120">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
