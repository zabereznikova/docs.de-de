---
title: 'Vorgehensweise: Aufteilen einer Datei in mehrere Dateien durch Verwenden von Gruppen (LINQ) (C#)'
ms.date: 07/20/2015
ms.assetid: 8179b91c-d778-4e57-884f-77fe5a8e4e40
ms.openlocfilehash: 934b6385a8634c23a4e29098367c9aaa7355f11c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347321"
---
# <a name="how-to-split-a-file-into-many-files-by-using-groups-linq-c"></a><span data-ttu-id="ce2a1-102">Vorgehensweise: Aufteilen einer Datei in mehrere Dateien durch Verwenden von Gruppen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="ce2a1-102">How to split a file into many files by using groups (LINQ) (C#)</span></span>
<span data-ttu-id="ce2a1-103">Dieses Beispiel zeigt eine Möglichkeit, den Inhalt von zwei Dateien zusammenführen und dann einen Satz von neuen Dateien zu erstellen, die die Daten auf neue Weise organisieren.</span><span class="sxs-lookup"><span data-stu-id="ce2a1-103">This example shows one way to merge the contents of two files and then create a set of new files that organize the data in a new way.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="ce2a1-104">So erstellen Sie die Datendateien</span><span class="sxs-lookup"><span data-stu-id="ce2a1-104">To create the data files</span></span>  
  
1. <span data-ttu-id="ce2a1-105">Kopieren Sie diese Namen in eine Textdatei namens „names1.txt“, und speichern Sie sie in Ihrem Projektordner:</span><span class="sxs-lookup"><span data-stu-id="ce2a1-105">Copy these names into a text file that is named names1.txt and save it in your project folder:</span></span>  
  
    ```text  
    Bankov, Peter  
    Holm, Michael  
    Garcia, Hugo  
    Potra, Cristina  
    Noriega, Fabricio  
    Aw, Kam Foo  
    Beebe, Ann  
    Toyoshima, Tim  
    Guy, Wey Yuan  
    Garcia, Debra  
    ```  
  
2. <span data-ttu-id="ce2a1-106">Kopieren Sie diese Namen in eine Textdatei namens „names2.txt“, und speichern Sie sie in Ihrem Projektordner: Beachten Sie, dass die zwei Dateien einige Namen gemeinsam haben.</span><span class="sxs-lookup"><span data-stu-id="ce2a1-106">Copy these names into a text file that is named names2.txt and save it in your project folder: Note that the two files have some names in common.</span></span>  
  
    ```text  
    Liu, Jinghao  
    Bankov, Peter  
    Holm, Michael  
    Garcia, Hugo  
    Beebe, Ann  
    Gilchrist, Beth  
    Myrcha, Jacek  
    Giakoumakis, Leo  
    McLin, Nkenge  
    El Yassir, Mehdi  
    ```  
  
## <a name="example"></a><span data-ttu-id="ce2a1-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce2a1-107">Example</span></span>  
  
```csharp  
class SplitWithGroups  
{  
    static void Main()  
    {  
        string[] fileA = System.IO.File.ReadAllLines(@"../../../names1.txt");  
        string[] fileB = System.IO.File.ReadAllLines(@"../../../names2.txt");  
  
        // Concatenate and remove duplicate names based on  
        // default string comparer  
        var mergeQuery = fileA.Union(fileB);  
  
        // Group the names by the first letter in the last name.  
        var groupQuery = from name in mergeQuery  
                         let n = name.Split(',')  
                         group name by n[0][0] into g  
                         orderby g.Key  
                         select g;  
  
        // Create a new file for each group that was created  
        // Note that nested foreach loops are required to access  
        // individual items with each group.  
        foreach (var g in groupQuery)  
        {  
            // Create the new file name.  
            string fileName = @"../../../testFile_" + g.Key + ".txt";  
  
            // Output to display.  
            Console.WriteLine(g.Key);  
  
            // Write file.  
            using (System.IO.StreamWriter sw = new System.IO.StreamWriter(fileName))  
            {  
                foreach (var item in g)  
                {  
                    sw.WriteLine(item);  
                    // Output to console for example purposes.  
                    Console.WriteLine("   {0}", item);  
                }  
            }  
        }  
        // Keep console window open in debug mode.  
        Console.WriteLine("Files have been written. Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:   
    A  
       Aw, Kam Foo  
    B  
       Bankov, Peter  
       Beebe, Ann  
    E  
       El Yassir, Mehdi  
    G  
       Garcia, Hugo  
       Guy, Wey Yuan  
       Garcia, Debra  
       Gilchrist, Beth  
       Giakoumakis, Leo  
    H  
       Holm, Michael  
    L  
       Liu, Jinghao  
    M  
       Myrcha, Jacek  
       McLin, Nkenge  
    N  
       Noriega, Fabricio  
    P  
       Potra, Cristina  
    T  
       Toyoshima, Tim  
 */  
```  
  
 <span data-ttu-id="ce2a1-108">Das Programm schreibt eine separate Datei für jede Gruppe im gleichen Ordner wie die Datendateien.</span><span class="sxs-lookup"><span data-stu-id="ce2a1-108">The program writes a separate file for each group in the same folder as the data files.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ce2a1-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ce2a1-109">Compiling the Code</span></span>

<span data-ttu-id="ce2a1-110">Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.</span><span class="sxs-lookup"><span data-stu-id="ce2a1-110">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ce2a1-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce2a1-111">See also</span></span>

- [<span data-ttu-id="ce2a1-112">LINQ und Zeichenfolgen (C#)</span><span class="sxs-lookup"><span data-stu-id="ce2a1-112">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="ce2a1-113">LINQ und Dateiverzeichnisse (C#)</span><span class="sxs-lookup"><span data-stu-id="ce2a1-113">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
