---
title: 'Vorgehensweise: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (C#)'
ms.date: 07/20/2015
ms.assetid: 7c04d42f-4a78-42c8-9ec8-57ef18fe13a9
ms.openlocfilehash: e6c0cbf523095122be4227bebee8d7a234eba2d0
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69592392"
---
# <a name="how-to-sort-or-filter-text-data-by-any-word-or-field-linq-c"></a><span data-ttu-id="b9165-102">Vorgehensweise: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="b9165-102">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>
<span data-ttu-id="b9165-103">Das folgende Beispiel zeigt, wie Sie Zeilen aus strukturiertem Text nach jedem Feld in der Zeile sortieren können, wie z.B. durch Trennzeichen getrennte Werte.</span><span class="sxs-lookup"><span data-stu-id="b9165-103">The following example shows how to sort lines of structured text, such as comma-separated values, by any field in the line.</span></span> <span data-ttu-id="b9165-104">Das Feld kann dynamisch zur Laufzeit festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b9165-104">The field may be dynamically specified at runtime.</span></span> <span data-ttu-id="b9165-105">Gehen Sie davon aus, dass die Felder in scores.csv die Matrikelnummer eines Studenten repräsentieren, gefolgt von einer Reihe aus vier Testergebnissen.</span><span class="sxs-lookup"><span data-stu-id="b9165-105">Assume that the fields in scores.csv represent a student's ID number, followed by a series of four test scores.</span></span>  
  
### <a name="to-create-a-file-that-contains-data"></a><span data-ttu-id="b9165-106">So erstellen Sie eine Datei, die Daten enthält</span><span class="sxs-lookup"><span data-stu-id="b9165-106">To create a file that contains data</span></span>  
  
1. <span data-ttu-id="b9165-107">Kopieren Sie die Daten aus „scores.csv“ auf dem Artikel [Vorgehensweise: Verknüpfen des Inhalts unterschiedlicher Dateien (LINQ) (C#)](./how-to-join-content-from-dissimilar-files-linq.md), und speichern Sie diese anschließen in Ihren Projektmappenordner.</span><span class="sxs-lookup"><span data-stu-id="b9165-107">Copy the scores.csv data from the topic [How to: Join Content from Dissimilar Files (LINQ) (C#)](./how-to-join-content-from-dissimilar-files-linq.md) and save it to your solution folder.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9165-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9165-108">Example</span></span>  
  
```csharp  
public class SortLines  
{  
    static void Main()  
    {  
        // Create an IEnumerable data source  
        string[] scores = System.IO.File.ReadAllLines(@"../../../scores.csv");  
  
        // Change this to any value from 0 to 4.  
        int sortField = 1;  
  
        Console.WriteLine("Sorted highest to lowest by field [{0}]:", sortField);  
  
        // Demonstrates how to return query from a method.  
        // The query is executed here.  
        foreach (string str in RunQuery(scores, sortField))  
        {  
            Console.WriteLine(str);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    // Returns the query variable, not query results!  
    static IEnumerable<string> RunQuery(IEnumerable<string> source, int num)  
    {  
        // Split the string and sort on field[num]  
        var scoreQuery = from line in source  
                         let fields = line.Split(',')  
                         orderby fields[num] descending  
                         select line;  
  
        return scoreQuery;  
    }  
}  
/* Output (if sortField == 1):  
   Sorted highest to lowest by field [1]:  
    116, 99, 86, 90, 94  
    120, 99, 82, 81, 79  
    111, 97, 92, 81, 60  
    114, 97, 89, 85, 82  
    121, 96, 85, 91, 60  
    122, 94, 92, 91, 91  
    117, 93, 92, 80, 87  
    118, 92, 90, 83, 78  
    113, 88, 94, 65, 91  
    112, 75, 84, 91, 39  
    119, 68, 79, 88, 92  
    115, 35, 72, 91, 70  
 */  
```  
  
 <span data-ttu-id="b9165-109">Dieses Beispiel zeigt außerdem, wie Sie eine Abfragevariable aus einer Methode zurückgeben können.</span><span class="sxs-lookup"><span data-stu-id="b9165-109">This example also demonstrates how to return a query variable from a method.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b9165-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b9165-110">Compiling the Code</span></span>  

<span data-ttu-id="b9165-111">Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.</span><span class="sxs-lookup"><span data-stu-id="b9165-111">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b9165-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9165-112">See also</span></span>

- [<span data-ttu-id="b9165-113">LINQ und Zeichenfolgen (C#)</span><span class="sxs-lookup"><span data-stu-id="b9165-113">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
