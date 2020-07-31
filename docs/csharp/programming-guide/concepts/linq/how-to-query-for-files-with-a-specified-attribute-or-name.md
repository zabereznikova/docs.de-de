---
title: 'Vorgehensweise: Abfragen von Dateien mit einem angegebenen Attribut oder Namen (C#)'
description: In diesem Artikel erfahren Sie, wie Sie LINQ in C# verwenden, um Dateien in einer Verzeichnisstruktur zu finden, und entweder die neuste oder die älteste Datei zurückgeben.
ms.date: 07/20/2015
ms.assetid: 560e3879-b0b3-4549-ad02-0a53aff2f83c
ms.openlocfilehash: 9820b96e19d805b792e18ff242e64dfb6cf4a606
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104494"
---
# <a name="how-to-query-for-files-with-a-specified-attribute-or-name-c"></a><span data-ttu-id="0bd65-103">Vorgehensweise: Abfragen von Dateien mit einem angegebenen Attribut oder Namen (C#)</span><span class="sxs-lookup"><span data-stu-id="0bd65-103">How to query for files with a specified attribute or name (C#)</span></span>
<span data-ttu-id="0bd65-104">In diesem Beispiel wird veranschaulicht, wie nach allen Dateien mit einem angegebenen Suffix (z.B. „.txt“) in einer angegebenen Verzeichnisstruktur gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="0bd65-104">This example shows how to find all files that have a specified file name extension (for example ".txt") in a specified directory tree.</span></span> <span data-ttu-id="0bd65-105">Es wird auch gezeigt, wie basierend auf dem Zeitpunkt der Erstellung entweder die neueste oder älteste Datei in der Struktur zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0bd65-105">It also shows how to return either the newest or oldest file in the tree based on the creation time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bd65-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0bd65-106">Example</span></span>  
  
```csharp  
class FindFileByExtension  
{  
    // This query will produce the full path for all .txt files  
    // under the specified folder including subfolders.  
    // It orders the list according to the file name.  
    static void Main()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        //Create the query  
        IEnumerable<System.IO.FileInfo> fileQuery =  
            from file in fileList  
            where file.Extension == ".txt"  
            orderby file.Name  
            select file;  
  
        //Execute the query. This might write out a lot of files!  
        foreach (System.IO.FileInfo fi in fileQuery)  
        {  
            Console.WriteLine(fi.FullName);  
        }  
  
        // Create and execute a new query by using the previous
        // query as a starting point. fileQuery is not
        // executed again until the call to Last()  
        var newestFile =  
            (from file in fileQuery  
             orderby file.CreationTime  
             select new { file.FullName, file.CreationTime })  
            .Last();  
  
        Console.WriteLine("\r\nThe newest .txt file is {0}. Creation time: {1}",  
            newestFile.FullName, newestFile.CreationTime);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0bd65-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0bd65-107">Compiling the Code</span></span>  
  <span data-ttu-id="0bd65-108">Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.</span><span class="sxs-lookup"><span data-stu-id="0bd65-108">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0bd65-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0bd65-109">See also</span></span>

- [<span data-ttu-id="0bd65-110">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="0bd65-110">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
- [<span data-ttu-id="0bd65-111">LINQ und Dateiverzeichnisse (C#)</span><span class="sxs-lookup"><span data-stu-id="0bd65-111">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
